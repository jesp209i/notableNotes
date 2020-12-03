---
tags: [Agile Testing Quadrants, Testing]
title: Agile Testing Quadrants
created: '2020-11-30T08:29:11.240Z'
modified: '2020-12-03T10:28:20.613Z'
---

# Agile Testing Quadrants
- Alle beskrivelser i kvadranterne fungerer kun som vejledende, dvs. der er ingen regler for hvad man `SKAL` have med i en kvadrant.
- Kvadranternes nummerering betyder ikke at man skal tage dem i den rækkefølge.
- kvadranterne giver et overblik, som skal guide til at lave en god teststrategi
  - Brug kvadranterne under Planning, Udvikling og Release

## Q1 - Techonology facing / Guide development
Indeholder testtyper:
- Unit
  - Hvor kommer accept kriterier fra?
    - retningslinjer for test
    - Use case skal beskrive formålet
    - Scenariet beskriver happy path og fejlbeskeder
- Integration
  - tester mellem alle componenter, eller 2 componenter
- Component
  - 
  - En hel microservice (indeholder flere units)

Denne Kvadrant skal have de fleste test (i antal)
- Testene er skrevet i forbindelse med udviklingen
- testenes funktion er at bekræfte at funktionaliteten virker under udvikling

## Q2 - Business facing / Guide development
Disse tests kan både være automatiske eller manuelle
- Testene er med til at besvare spørgsmål og opdage information om applikationen
  - Dette er med til at validere features (om det er de rigtige features)


Automatiske test:
- Functional
- UI

Manuelle test:
- Prototyper / mockups / simulering

Disse tests udføres under og efter udvikling
- De automatiserede test bør includeres i `definition of done`

## Q3 - Business facing / Critique product
Her er der en hovedvægt på manuelle tests, men visse tests kan stadig automatiseres
- Kvadranten skaber feedback omkring applikationens nuværende tilstand
- Giver en forståelse om brugeres oplevelse med produktet

Typer af tests her:
- Exploratory
- Usability
- A/B

## Q4 - Techonology facing / Critique product
Alle test her er automatiserede
- De enkelte tests implementeres på baggrund af krav og deres prioritet:
  - Hvis der er et krav om at applikationen skal være hurtig, er performance testing vigtig.
  - Hvis sikkerhed er vigtigt, vil sikkerhedstest have en prioritet...
- Testene producerer målepunkter, som kan visualiseres og analyseres 
  - Dette bruges til at beslutte tiltag hvis der er uhensigtsmæssige udsving

Typer af tests:
- Performance / load
- Security
- Reliability
