---
tags: [Agile Testing Quadrants, Testing]
title: Q4 - Business test
created: '2020-11-18T08:07:50.219Z'
modified: '2020-11-30T13:02:54.611Z'
---

# Q4 - Business test
I Q4 er produktet ikke længere under udvikling, men overholder det de teknologiske krav der vil blive stillet i forbindelse med brug.  
Evaluer om der opnås den korrekte "business value".
- Performance og Load Testing
- Security Testing
  - bliver der kommunikeret korrekt mellem komponenter (krypteret)
  - er data (som kodeord) i databasen i klartekst
- "ility" testing
  - maintainability
  - interoperability
  - compatibility
  - reliability
  - installability

## Udfordringen i Q4
Kunden forventer performance, pålidelighed og sikkerhed bliver taget hånd om. Men 
Security og Performance kræver cross-functional ansvarlighed, dvs. kunden har ansvar for at sætte krav til dette, udvikler har ansvar for vejledning om disse ting.  
Hvis kunden ikke bliver vejled om dette, kan det hurtigt blive udeladt fra test og udviklingsplanen, men det kræver tid og ressourcer at teste og udbedre.

## Hvem udfører tests i Q4?
- Performance testes af specialister
  - hvad er normalt brug
  - opsætning af load-test
  - database begrænsninger
  - Brug scenarier til at opstille relevante brugssituationer:
    - "Som brugeren Abby, har jeg brug for at hente rapport X in mindre end 20 sekunder, så jeg har mulighed for at tage en beslutning hurtigt"
    - Ovenstående giver mulighed for at teste, tilpasse/optimere så kravet kan imødekommes

- sikkerhed testes af specialister (hacking-skills)
  - er der sikker kommunikation
  - kan applikationen kompromiteres ved angreb?
  - hvis en "sikkerhedstest" kan laves som en test der ligger i q1-3, så bør den placeres der, og ikke indgå her  
  
- Brug værktøjer i CI-pipeline til at lave køde analyse (overholdes kodestandarder)
- Kør de tungere tests (load/performance) sjældnere end Unittests og lignende, men ofte nok til at man kan bruge rapporten til noget, hvis der er noget der skal rettes til.

- Værktøjer som Nessus eller Gremlin til at stressteste forskellige aspekter af applikationen. (Chaos engineering)

## "-ility" test
### Maintainability
- kode vedligehold
- database / data

### Interoperability

### Compatibility

### Reliability

### Installability



