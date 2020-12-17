---
tags: [Eksamen, Microservice, Store Systemer]
title: Microservices
created: '2020-12-12T09:20:09.621Z'
modified: '2020-12-12T12:25:33.001Z'
---

# Microservices
## Terminologi
Service Types:
- Data Service
  - forbinder til en data source - ikke kun database
- Business Service
  - Ordredomænet kræver og bearbejder data fra services:
    - customer
    - product
    - inventory
- Translation service
  - en indkapsling af en 3. parts service
  - facade indtil microservice arkitekturen
- Edge service
  - servicing data to users and external services
  - web view
  - slim down payload for mobile devices
  - modify payload to fit the need of a 3. party contractor

Platform:
- platformen indeholder alt hvad dine løsningen skal bruge
- runtime for service
  - datacentre og virtualisering
- supplerende services (ancillary services)
  - externe services som bruges i forbindelse med den platform man vælger
    - message queues
    - cash services
    - authentication / authorization
- operational components
  - såsom logging og monitorering
  - vigtig detalje i kritiske systemer
- diagnostic components
  - diagnosticering, troubleshoot, improve system performance

## Cloud native
- arkitektonisk stil
- designet til at fremme operationen i cloud
  - externalizing configuration
  - fokus på skalerbarhed
  - hurtig startup
  - håndtere immediate shutdowns yndefuldt
- fokus på pprtable og skalerbare applikationer
  - portable: deploy app overalt i verden uden ændringer
  - skalerbarhed: app er designet til at enten i sig selv, eller sammen med flere instanser af sig selv
- kan køres i eet datacenter, men er klar til flere

MS og Cloud native fokuserer begge på Scalability 

## Decomposition of a system
- Functional Use Patterns / Decomposition Patterns
  - Domain based / domain driven design
    - Start med modellen, ikke databasen 
      - Bounded Context
    - hvilke actions skal domænet håndtere
    - byg services, contract first
- Business Process based
  - giver higher-level business funktioner 
    - kan genbruges forskellige steder i organisationen
  - ingen adgang til datastore/db
  - opbygning:
    - identificer den process der skal exposes
    - identificer de datadomains du skal consume
    - definer api som håndterer disse business processes
      - fokus på contract
      - action-pattern
    - Wire service
- Atomic transaction based
  - opbygget omkring transaktion over flere dataservices
    - hvis eventual consistency ikke er acceptabelt
  - Stor drawback at man kan skulle samle nogle databaser.
  - det "mudrer vandene" i distribuerede systemer og skaber "forstoppelse"

- Decomposition Strategies
  - Strangler pattern
    - opdeling af en monolit
    - "Kvæl" afhængigheder inden i monolitten og læg dem ud i egne services, en efter end
    - udtræk funktionalitet fra monolittet og erstat det med en microservice
  - Sidecar pattern
    - off-load processes to another module
    - fjerner duplikeret kode der ligger i flere services
      - logning
      - monitorering
      - netværksservices
    - forbundet til en parent-service
      - selve side-car servicen kan bruges til forskellige parents

## Integration Patterns
Gateway pattern:
- Problem: Alle klienter der kan tilgå alle services vil skabe kaos
- skaber en facade/proxy for klienter til at styre klienters adgang inden i systemet
  - kan stå for en offentlig og konsistent kontrakt udadtil, mens de interne kontrakter i systemet kan ændre sig

Process Aggregator Pattern: 
- er et Orchestration Pattern
- koordinerer flere business process services i et endpoint
  - dvs. flere business processer køres i samme kald
  - der skabes et kombineret svar tilbage
- hjælper til at overholde dry-princippet
- pas på - kan skabe blokerende kald i systemet - use with caution

Edge Pattern:
- tager højde for klienten - web-klienter har andre behov end mobil-klienter

## Operational Patterns
- Log Aggregation Pattern
  - Vi skal vide hvad der sker (især ved fejl)
  - logs er uvurderlige under drift
  - Der skal være en konsistent struktur i logs - fælles taksonomier
  - I MicroServices er der logs overalt
  - Log skal kunne bearbejdes så man nemt kan komme frem til problemer
  - Indexering af logs for at kunne søge nemt igennem dem
  - off the shelf componenter
- Metrics Aggregation Patterns
  - Problem: Need to see what is going on with the system
  - Taksonomi
  - off the shelf componenter
  - metrics shipping
  - Dashboards
    - High Level Dashboard for systems wide health
    - Detailed Dashboard for per-service health
    - inject event, deployments - maybe user events
    - runbooks for alarms => how to troubleshoot the alarms
- Tracing Patterns
  - Hjælper med at genetablere en call stack over et distribueret system
    - Skal vise kaldet fra yderst til inderst
  - brug off the shelf componenter og standarder


### Externalized Configuration
- ikke nødvendig i Microservice, men nødvendig ved cloud-native
- brug værktøjer som gør det nemt at finde og manipulere systemets miljøvariabler
- Beskyt SECRETS, men sørg for at DEVOPS/Drift har adgang til det i tilfælde af fejl


### Service Discovery
- Problem: What service do I call?
- central location of all services
- advertise what they offer
- find what you need
- Consume the URI from the discovery engive. not config








