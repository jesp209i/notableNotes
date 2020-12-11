---
tags: [Eksamen, Testing]
title: Testing Eksamensspørgsmål 3
created: '2020-12-09T07:53:08.165Z'
modified: '2020-12-10T21:25:07.710Z'
---

# Testing Eksamensspørgsmål 3
- Hvad er data-driven test?
- Hvilken quadrant i test-quadranten af Brian Marick’s, indeholder data-driven test?
- Hvad er mocking og hvordan kan man med fordel bruge mocking ifm. testing af samme quadrant som DDT.
- Vis i semesterprojektet hvordan i har brugt mocking og DDT.

## Data driven Tests
Metode til at teste forskelligt data på dit logik.
- Det bruges typisk på unit-test niveau
- men det kan også bruges til at lave integration testing.

DDT giver mulighed for at genbruge testlogik på flere forskellige data-situationer
 - dermed får du testet om dit program har den forventede behavior i alle cases
 - forskellige cases kan betyde at der tages en anden path i koden, så du kan opnå højere code coverage
 - Domæneeksperter, eksempelvis Busines folk og testere kan stå for indsamling af relevant testdata

### Maricks Test Kvadranter
indsamlingen af testdata Q2-aktivitet
- user stories
- examples

Skrive og vedligeholde test Q1-aktivitet

DDT bør bruges til at bygge bro mellem udviklere og domæneeksperter. 

Den tekniske implementering:  
Testene bliver til metoder som tager imod parametre - eksempler følgere senere

## Mocking
Testing handler om at opnå kontrol over produktet og højne slutproduktets kvalitet.
- Tests bør være hurtige at afvikle, så de ikke bliver en hæmsko for udviklene.
- De skal være overskuelige, så andre udviklere ved hvad der sker. (Test er dokumentation)
  - dvs. de bør være simple og sigende!

Derfor handler Test om kontrol:  
De fleste klumper af kode er afhængig af anden kode for at kunne give de resultater vi forventer af det.
- afhængigheder er kompleksitet!

Med Mocking kan vi styre disse afhængigheder og nedbringe kompleksiteten
- I stedet for den konkrete afhængighed, bruger vi simpelthen en testdouble som vi selv kontrollerer.
- På den måde kan man i højere grad fokusere på mindre bidder af koden, og sikre at den fungerer som den skal.

Frameworks
- Moq - bruges til at erstatte en afhængighed
- Fixture - fylder objekter med falsk data (når det ikke er vigtigt hvad der er i objekterne)


Og nu nogle eksempler:

## Sem-proj med mocking og ddt
Først mocking  
fokus på `mediator.Setup(...)`
- en query får en tom response der svarer til en 404!

Data Driven  
Metoden tager en parameter ind - parametren er relevant for casen... (nu er det ikke den vildeste logik der testes her)
- For hver `InlineData` kører den samme test (genbrug)
- eksempel på en anden slags testdouble (Fixture)



