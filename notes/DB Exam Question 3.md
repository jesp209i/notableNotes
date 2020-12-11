---
tags: [Database, Eksamen]
title: DB Exam Question 3
created: '2020-12-05T08:19:27.183Z'
modified: '2020-12-05T10:11:15.023Z'
---

# DB Exam Question 3
```
What are database transactions and when to use them? 
How is ACID related to transactions? 
Explain concurrency and isolation levels.
```
Et SQL-statement er principielt en transaktion. Men når man vil udføre flere statements sammen, statements som også hører sammen, så bliver de pakket ind i en transaktion. Enten udføres hele transaktionen uden fejl, eller, i tilfælde af fejl, vil hele transaktionen blive rullet tilbage. Enten hele transaktionen eller intet af transaktionen. Bank eksempel med overførsler mellem to konti.  
Vi vil udføre en samling af handlinger, uden at andre må arbejde på de samme objekter samtidig.
Atomic  
-	Alt i transaktionen hører sammen

Consistent
-	Uanset udfaldet af transaktionen, så er data i databasen valid og konsistent
    -	Intrigriteten af constraints er overholdt

Isolated
-	Andre kilder kan ikke ændre på tilstanden af det data vi ændrer, imens vi ændrer det

Durable
-	Dataen bliver skrevet til databasen, og kan hentes frem igen

Isolation Levels og Phantom Reads

# Preventable read phenomena
Den nemmeste måde at definere forskellene mellem de forskellige ANSI isolation levels er ved at beskrive det sæt af egenskaber som enten er tilladte eller forbudte afhængig af hvilket isolation level der bruges. De tre engenskaber, der også kaldes "preventable read phenomena" er:
* __Dirty reads__
* __Non-repeatable reads__
* __Phantom reads__

## Dirty reads
Denne egenskab opstår når en transaktion læser data der ikke er committed. Hvis en transaktion har ændret data, men ikke committed ændringen, og en anden transaktion har tilladelse til at aflæse det ændrede data, er der en større sandsynlighed for at data aflæses i en ikke konsistens tilstand.

## Non-repeatable reads
En aflæsning er ikke-gentagbar hvis en query får forskellige værdier når det samme data aflæses i to separate aflæsningen indenfor samme transaktion. Dette kan se når en anden transaktion opdaterer det samme data, efter den første aflæsning, men før aflæsning nr to.

## Phantom reads
Denne egenskab opstår når medlemsantal af et sæt ændrer sig. Dette kan kun ske i en query med et predicate, eksempelvis som  `WHERE count_of_widgets < 10`.

Fantomet opstår når to select statements, med samme predicate, i samme transaktion, får forskellige antal resultatrækker.
# Transaction Isolation
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

# Fra klassen:
```
- Hvad er en transaktion
  - typer af transaktioner
  - sammensat af flere transaktioner (queries)
  - Acid egenskaberne (i forbindelse med transactions)
  - isoleringsniveauer
    - read phenomenons + locking
- pessimistic vs optimistic locking
```

