---
tags: [ACID, Concurrency, Database, ebook_SQL_Server_concurrency_K_Delaney.pdf, Transactions]
title: Concurrency and Transactions
created: '2020-09-18T12:13:23.618Z'
modified: '2020-09-19T09:36:17.942Z'
---

# Concurrency and Transactions
Uanset om man bruger en optimistisk eller pessimistik concurrency model, opstår der konflikter når flere sessioner "sloges" om at modificere det samme data samtidigt. I disse situationer, kan der opstå flere stride om ressourcerne og data intrigritets problemer, såsom:
* __Preventable read phenomena__
  - ANSI SQL standarden definerer tre fænomener ('dirty read', 'non-repeatable read og 'phantom read') som enten tillades eller forhindres alt efter hvilket isolation level ('READ UNCOMMITTED', 'READ COMMITTED', 'REPEATABLE READ' eller 'SERIALIZABLE') der benyttes
* __Lost updates__
  - En session overskriver ved et uheld modifikationerne fra en anden session
* __Excessive blocking__
  - Der opstår en kø af blokerede processer, som sætter pres på ressourcerne og skaber uakseptable forsinkelser for slutbrugerne
* __Deadlocks__
  - Gensidigt blokerende sessioner der gør det umuligt at lave videre databehandling.

## Pessimistic Versus Optimistic Concurrency
SQL Server bruger en pessimistisk tilgang til concurrency per default.

Med pessimistisk concurrency undgår man konflikter ved at sætte låse når:
- der aflæses data, så andre sessioner ikke kan modificere dem samtidigt
- der modificeres data, så andre sessioner hverken kan modificere eller aflæse data samtidigt

`Readers blocks writers and writers blocks readers`

SQL Server imødekommer potentielle problemer mellem competing transaktioner ved at implementere en specifik transaction isolation level (se senere). Hver af de tre mest brugte ANSI standard isolation levels (READ COMMITTED, REPEATABLE READ og SERIALIZABLE) er implementeret pessimistisk i SQL Server:
- Med 'READ COMMITTED' bliver der brugt delte og eksklusive låse til at undgå interferens mellem samtidige transaktioner.
- Med 'REPEATABLE READ' og 'SERIALIZABLE' holdes der på låse i længere perioder, for i højere grad at kunne minimere eller eliminere mulig interferens. Ulempen her er at jo længere tid sessioner holder på låse, des mindre samtidighed vil man opnå. 

I den optimistiske version, er antagelsen at der er få konfliktende data modifikationer i systemet, så det er usandsynligt at en transaktion modificerer data som en anden transaktion også modificerer. 

Til at opnå optimistisk concurrency er default behavior at benytte en teknologi der hedder 'row versioning', der er tilgængelig i SQL Server via en af de snapshot-baserede isolation levels. SQL Server vedligeholder en timestamped version gemt i tempdb databasen, der indeholder alle tidligere committede versioner af data rækkerne.

Hvis en transaktion støder på en eksklusiv lås på noget data den vil læse, vil den, i stedet for at vente på at låsen ophæves, via versions tabellen finde den version af rækken som passer med hvornår transaktionen startede.

På SNAPSHOT baserede isolation levels vil optimistiske SELECT operationer ikke låse rækken, da der aflæses fra versions tabellen. Dermed bliver data modificerende operationer ikke blokeret hvis der er en aflæsning igang.

## Transactions
### Transaction properties
En transaktion defineres som et "unit of work" - en eller flere opgaver der tilsammen udgør en "alt eller intet" operation. Hvis transaktionen afbrydes (og derfor ikke alle opgaver i transaktionen bliver fuldført), skal systemet behandle transaktionen som om den aldrig blev udført.

En transaktion har fire grundlæggende egenskaber, kaldet ACID-properties, som garanterer validiteten af data efter en given transaktion er færdigbehandlet.

* __Atomicity__
  - En transaktion behandles som et "unit of work". Hvis ikke hele transaktionen kan fuldføres, bør systemet ikke afspejle nogle dele af transaktionen. Dette gælder uanset transaktionens størrelse.
* __Consistency__
  - En transaktion efterlader data i en meningsfuld tilstand når den er fuldført. I relationelle databaser betyder det at alle relationer/constraints og den referencielle integritet overholdes.
* __Isolation__
  - Ændringerne fra en transaktion, må ikke påvirke ændringerne i en anden transaktion. Hver enkelt transaktion skal udføres som om det var systemets eneste opgave.
* __Durability__
  - Når en transaktion er færdig, er dens effekt permanent og kan genskabes.

SQL Server garanterer i udgangspunktet kun 3 ud af 4 (ACD). Hvis I skal garanteres også kræver det en højere Isolation Level. 

### Transaction scope
Der findes 4 forskellige måder at beskrive start og slut på en transaktion. De to er tilgængelige per default, og de to sidste er tilgængelige under særlige tilfælde

* __auto-commit__ - default type
  - enhver enkeltstående data modificerende operation. Det vil sige alle INSERT, UPDATE eller DELETE statements bliver automatisk til en transaktion, uanset mængden af rækker der påvirkes af den enkelte statement
* __explicit__ - default type
  - Transaktioner der eksplicit defineres med kommandoerne `BEGIN TRANSACTION` i starten og enten `COMMIT TRANSACTION` eller `ROLLBACK TRANSACTION` til at vise slutningen af transaktionen. Mellem `BEGIN` og `COMMIT/ROLLBACK` står der almindelige SQL statements. Der vil også indgå SQL til at afgøre om transaktionen skal afsluttes med COMMIT eller ROLLBACK.
* __implicit__ - ikke default type
  - Når denne scopes benyttes bruges alle DML statements som en del af en transaction, indtil dette afsluttes med `COMMIT TRANSACTION` eller `ROLLBACK TRANSACTION`.
  - Bruges primært at udviklere som kommer fra andre dbms'er der håndterer transactions anderledes end MSSQL.
  - Skal slåes til med `SET IMPLICIT_TRANSACTIONS ON`
* __batch-scoped__ - ikke default type
  - Anmod om batch-scoped transaktioner ved at anmode om `Multiple Active Result Sets` i klientens forbindelsesstreng. I en sådan forbindelse vil SQL Server lave en rollback hvis en transaktion bliver startet, men aldrig gennemført med en `COMMIT TRAN`. Scopen er beregnet til at undgå application deadlock.

## Transaction Isolation
Alle transaktioner kører i et transaction isolation level, som afgør hvor følsom din applikation er for ændringer forårsaget af andre brugeres transaktioner, og hvor længe SQL Server skal holde på låse der beskytter mod disse ændringer. ANSI SQL standarden definerer fire niveauer af isolation for transaktioner.

* __READ UNCOMMITTED__
  - tillader 'dirty reads', 'non-repeatable reads' og 'phantom reads'
* __READ COMMITTED__
  - forhindrer 'dirty reads', men tillader 'non-repeatable reads' og 'phantom reads'
* __REPEATABLE READ__
  - forhindrer 'dirty reads' og 'non-repeatable reads', men tillader 'phantom reads'
* __SERIALIZABLE__
  - forhindrer alle read fænomener

Med undtagelse af READ UNCOMMITTED er hver af disse isolation levels pessimistiske af natur. 
Det betyder at SQL Server vil bruge delte og eksklusive låse for at undgå:
- at data kan læses imens det er ved at blive ændret
- at data kan ændres imens det er er ved at blive læst

## Controlling the isolation level
SQL Servers standardindstilling på isolation level er 'READ COMMITTED', men en applikation kan overskrive denne indstilling ved at bruge følgende kommando:
```SQL
SET TRANSACTION ISOLATION LEVEL
  [READ UNCOMMITTED | READ COMMITTED | REPEATABLE READ | SNAPSHOT | SERIALIZABLE]
```

SET kommandoen styrer isolation level for alle queries over den nuværende forbindelse, indtil isolation level bliver ændret eller forbindelsen bliver afbrudt. Det vil sige at på enhver ny forbindelse til databasen vil isolation level være 'READ COMMITTED' igen.

## Preventable read phenomena
Den nemmeste måde at definere forskellene mellem de forskellige ANSI isolation levels er ved at beskrive det sæt af egenskaber som enten er tilladte eller forbudte afhængig af hvilket isolation level der bruges. De tre engenskaber, der også kaldes "preventable read phenomena" er:
* __Dirty reads__
* __Non-repeatable reads__
* __Phantom reads__

### Dirty reads
Denne egenskab opstår når en transaktion læser data der ikke er committed. Hvis en transaktion har ændret data, men ikke committed ændringen, og en anden transaktion har tilladelse til at aflæse det ændrede data, er der en større sandsynlighed for at data aflæses i en ikke konsistens tilstand.

### Non-repeatable reads
En aflæsning er ikke-gentagbar hvis en query får forskellige værdier når det samme data aflæses i to separate aflæsningen indenfor samme transaktion. Dette kan se når en anden transaktion opdaterer det samme data, efter den første aflæsning, men før aflæsning nr to.

### Phantom reads
Denne egenskab opstår når medlemsantal af et sæt ændrer sig. Dette kan kun ske i en query med et predicate, eksempelvis som  `WHERE count_of_widgets < 10`.

Fantomet opstår når to select statements, med samme predicate, i samme transaktion, får forskellige antal resultatrækker.

## Transaction isolation levels

| | Transaction Isolation Level | Dirty Read | Non-repeatable Read | Phantoms | Concurrency Model |
|---|---|---|---|---|---|
| 1. | READ UNCOMMITTED | Yes | Yes | Yes | Pessimistic |
| 2.1 | READ COMMITTED | No | Yes | Yes | Pessimistic |
| 2.2 | READ COMMITTED SNAPSHOT | No | Yes | Yes | Optimistic |
| 3. | REPEATABLE READ | No | No | Yes | Pessimistic |
| 4. | SNAPSHOT | No | No | Yes | Optimistic |
| 5. | SERIALIZABLE | No | No | Yes | Pessimistic |

Punkt 2.1 'READ COMMITTED' er default i SQL Server (dvs den pessimistiske version). Hvis man aktiverer READ COMMITTED SNAPSHOT får man en optimistisk version som bruger tempdb.














