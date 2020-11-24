---
title: Database eksamen
created: '2020-11-24T09:21:32.106Z'
modified: '2020-11-24T10:12:36.678Z'
---

# Database eksamen
## 1.
- Forklar ER-diagrammets dele
- attributter + datatyper + null vs not nulls
- constraints + keys



## 2.
```
Describe stored procedures and how are they created. Elaborate on scenarios where they should be used/not used.
How do stored procedures differ from Views, Triggers and Functions?
```
- Hvordan bygger man en Stored procedure + eksempel
  - parametre, retur værdier
- forskelle mellem SP og Views og Trigger og fuctions (programmering inden i SQL Server)
  - hvornår bruger man hvad?
  - fordele og ulemper om de forskellige muligheder

## 3. 
```
What are database transactions and when to use them? 
How is ACID related to transactions? 
Explain concurrency and isolation levels.
```

- Hvad er en transaktion
  - typer af transaktioner
  - sammensat af flere transaktioner (queries)
  - Acid egenskaberne (i forbindelse med transactions)
  - isoleringsniveauer
    - read phenomenons + locking
- pessimistic vs optimistic locking

## 4. 
```
How can a database and SQL queries be optimized? 
What is indexing and what types are there? 
How is relational algebra related to the optimization process?
Show practical examples.
```

- Lave begrænsede datasæt via queries
  - query optimizer i MSSMS
  - indexes + mere om dette
- sammenligne relationel algebra med en egentlig SQL query.

## 5.
```
What is a Data Warehouse? Explain difference between OLTP and OLAP. When to use a DW?  
Pros and cons
```

- Beskrivelse af DW, hvad det bruges til
- hvornår bruger man hvilken type database til DW
- beskriv OLTP / OLAP
- star/snowflake modelling

## 6. 
```
NoSQL databases are increasingly being used, argue why and provide examples.  
What types of NoSQL systems are there?  
Compare a NoSQL system like MongoDB with relational DBMS.
```

Easy of use, The data can be structured the same way as you want to use it.

- Key/Value store
- Document
- Graph



