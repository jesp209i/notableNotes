---
tags: [Database, Eksamen]
title: DB Exam Question 5
created: '2020-11-24T09:21:32.106Z'
modified: '2020-12-05T08:23:34.766Z'
---

# DB Exam Question 5
```
What is a Data Warehouse? Explain difference between OLTP and OLAP. When to use a DW?  
Pros and cons
```
#### Fra klassen:
```
- Beskrivelse af DW, hvad det bruges til
- hvornår bruger man hvilken type database til DW
- beskriv OLTP / OLAP
- star/snowflake modelling
```

Approaches to processing data
- OLTP - Online Transaction Processing
  - eksempel
    - find en bogs pris
    - opdater seneste kundes transaktion
    - holder styr på ansattes timer
  - fokus på "daglig" operation
  - har et applikations-orienteret design
  - data: up-to-date, operational
  - størrelse: snapshots, gigabytes
  - queries: simple transaktioner og hyppige updates
  - users: thousands (bruges af mange i en virksomhed, og måske virksomhedens kunder i en eller anden forstand)
  - traditionel operationel database (SQL eller NoSQL)
- OLAP - Online Analytical Processing
  - eksempel
    - beregn hvilke bøger der har bedst dækningsgrad
    - Find de mest loyale kunder
    - beslutte hvem der er månedens medarbejder
  - fokus på business beslutninger
  - har et subjekt-orienteret design (sidste kvartals salg)
  - consolidated, historical
  - størrelse: arkiv, terrabytes
  - queries: komplekse, aggregerede forespørgsler og sjældne updates
  - users: hundreds (virksomhedens analyse og data scientists)
  - OLAP is Data Warehouse
    - Fact table
    - Dimension table
    
Eksempel baseret på Semester projekt?
noget med deltagere til events
