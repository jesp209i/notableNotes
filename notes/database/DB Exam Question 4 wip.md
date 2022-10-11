---
tags: [Database, Eksamen]
title: DB Exam Question 4 wip
created: '2020-11-24T09:21:32.106Z'
modified: '2020-12-05T13:48:26.196Z'
---

# DB Exam Question 4 wip
## 4. 
```
How can a database and SQL queries be optimized? 
What is indexing and what types are there? 
How is relational algebra related to the optimization process?
Show practical examples.
```
På DB-niveau
- Database => horizontal skalering
- Sharding => 

Indeksering
- Mange rækker er gemt i databasen
- Mange forespørgsler tilgår kun en lille del af rækkerne
- Skal kunne ændre på rækkerne: insert, update og delete
- Kan ikke tage databasen offline for at reorganisere filerne databasen består af

=> Mål: tilgå så lidt data som muligt

`PRIMARY KEY` og `UNIQUE` constraints skaber typisk indexes (nonclustered).
- I tilfældet med `PRIMARY KEY` skabes et clustered index, men kun hvis der ikke allerede er et clustered index på tabellen. 
  - `PRIMARY KEY`-indexet kan sagtens være nonclustered
- I tilfældet med `UNIQUE` skabes et nonclustered index


## To typer af indeksering:
- clustered (standard i mssql)
  - direkte adgang til data
  - Best practice er at bruge kolonner hvor WHERE clause og JOINS indgår i queries
  - Der kan kun være et clustered index i en tabel - som bestemmer sorteringen i tabellen
- non clustered
  - Pointers til data (row locator)
  - Laver tabeller i baggrunden, som indeholder den type sortering man vil opnå med indexet.
  - tabellen peger på de relevante rækker i den rigtige tabel

##
- OLTP
  - Database med en forventelig høj mængde af transaktioner hvor data ændres
  - Brug Clustered index og kun få velvalgte nonclustered index
    - Du får et performance hit, ved mange nonclustered indexes
    - reindex ved hver ændring :(
- OLAP
  - Database hvor data sjældent ændres, men meget ofte queries
  - Brug en masse unclustered indexes til at optimere queries
    - Du får et performance gain ved mange nonclustered indexes
    - Da der er sjældne writes til databasen, bliver data kun sjældent reindexeret :) 

# LIKE Query vs Full Text Search
Full Text Search kræver at der er et index på tabellen til netop dette formål.  
Full Text Search er sprog specifikt  
De kolonner i tabellen som der skal kunne søges på bliver:
- Tokenized - hvert ord bliver til en token som peger på de rækker og kolonner som ordet forekommer i
- stopord - almindelige gængse fyldord fjernes desuden helt fra listen af tokens
- stemming - ord begrænses ned til ordet grundstamme. Husene => hus. Løbende => løb
- reverse index - "ordværdien" peger på de relevante rækker hvor ordet indgår
- når man søger, bliver ens søgestreng også udsat for ovenstående før der kigges i indexet


#### Fra klassen:
```
- Lave begrænsede datasæt via queries
  - query optimizer i MSSMS
  - indexes + mere om dette
- sammenligne relationel algebra med en egentlig SQL query.
```

