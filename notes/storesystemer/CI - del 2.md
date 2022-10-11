---
tags: [Store Systemer]
title: CI - del 2
created: '2020-12-04T08:29:16.682Z'
modified: '2020-12-04T10:07:19.647Z'
---

# CI - del 2
## GIT
__Opret aliaser__  
[Git alias](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases)
  
__Nice kommandoer__  
```
git log --oneline
git commit --amend
```
## GIT braching strategi
- Lås main branch
- "arbejd" på en develop-branch
- branchs ud til feature-branches - afspeljer en story
- develop-branchen udgives til en release branch
  - Release er den endelige version inden udgivelse til main-branch
- hotfixes - rettelse i master
  - fejl rettes, merges ind i main og develop, og måske release, hvis der kører et release.

# Arkitektur
- Arkitektur er forskellig fra implementering.
- Programmeringssprog er "implementering"
- For at kunne anbefalde en arkitektur skal man vide Hvad er organisationen og dere processer
  - Tænk arkitektur som bokse 
    - => bare "database", ikk MSSQL, det er en implementeringsdatalje
    - Man skal være uafhængig af "vendors" (specifikke produkter)

# Applikationsopdeling
 - Frontend / Backend
 - Komponenter:
   - DNS
   - Load Balancer - efterbehov
   - Web server
   - Database(r)
   - Caching server
   - Job queues
   - Full-Text Search Engine
   - Cloud Storage
   - CDN

## Scale cube
- X-axis - horizontal duplication
  - klon servicen
- Y-axis - functional decomposition
  - Scale by splitting different things
- Z-axis - data partitioning
  - Scaler ved at splitte ting der ligner hinanden
    - eksempel: fremium brugere vs. betalende brugere
      - => bruger lignende services, men er splittet på to forskellige services.
### Skalering på DB:
- Vertikal skalering => flere ressourcer, "mere jern"
- Horizontal skalering => primary/secondary

# Statefull / Stateless
- Statefull
  - klienten rammer præcis samme service
- Stateless
  - klienten kan ramme hvilken som helst service

# CI/CD (Continuous Integration/Delivery/Deployment)
- Afleverer løbende værdi

Forskellen mellem CD og CD
- Delivery => alt bliver løbende udgivet
- Deployment => der er et menneske der godkender en udgivelse
  

1. Versionskontrol
    - Source code Management - GIT
2. Continuous Integration
    - Test og lignende
    - checker at en feature branch kan merges til main
3. Continuous Delivery
4. Continuous Deployment


