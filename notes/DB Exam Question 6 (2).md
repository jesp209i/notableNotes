---
tags: [Database, Eksamen]
title: DB Exam Question 6
created: '2020-11-24T09:21:32.106Z'
modified: '2020-12-05T11:18:28.657Z'
---

# DB Exam Question 6
```
NoSQL databases are increasingly being used, argue why and provide examples.  
What types of NoSQL systems are there?  
Compare a NoSQL system like MongoDB with relational DBMS.
```
Det er nemt at bruge NoSQL - intet skema, bare læg data ind i databasen.  
Strukturer eventuelt data så det ser ud på samme måde som når du skal bruge det igen.
CQRS => Queries i NoSQL

NoSQL er designet til at kunne distribueres nemt

Typer af NoSQL
- Key/Value store (DynamoDB)
- Document (MongoDB, CouchDB)
- Graph (Neo4j)
- Wide Column (Google Bigtable)

Forskelle og ligheder mellem NoSQL (Mongo) og SQL
- SQL har records, Mongo har documents
- I SQL er der flere tabeller og disse har muligvis relation til hinanden
  - dette minimerer redundans (hvis man følger NF)
  - Men det er sværere at skalere over flere servere
    - Data er tilgengæld konsistente
- Mongo har embedded documents (dokumenter inde i dokumenter) - eller referencer til andre dokumenter
  - Der er større tilbøjelighed for redundante data - måske ligger det samme i flere dokumenter
  - Men Mongo er designet til at skalere
    - Data er ikke garanteret konsistente - men det bliver de over tid (eventual consistency)
- ACID og BASE principperne (SQL vs. NoSQL)
