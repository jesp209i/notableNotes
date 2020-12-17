---
tags: [Eksamen, Testing]
title: Testing Exam Question 5
created: '2020-12-09T07:53:08.165Z'
modified: '2020-12-12T07:53:40.316Z'
---

# Testing Exam Question 5
- Hvordan vil dit anbefalede test-setup se ud ifm. semesterprojektet?.
- Fremvis en figur der viser anbefalet setup af miljøet med fokus på backend. (server, API, cloud og evt. database m.m.)
- Forklar dine valg og fremvis eksempler fra semesterprojekt der har givet dig grunden til de valg du har lavet i din testplan.


## Test setup
Vi bruger test kvadranterne til at få overblik over hvilke behov vi umiddelbart har for at lave fyldestgørende test
- Kvadranterne giver nogle gode perspektiver for at komme godt rundt om produktet.
- man skal ikke bruge alt! - tilpas til opgaven

## Setup
- Simpelt setup
- simple behov

komponenter  =>  WebAPI og SQL server. =>  andre står for frontend

Udvikling:
- lokalt - database i en docker
- Github til versionskontrol
   - Github actions til CI
   - CD efter 2x reviews + accept
- Deployment til Azure

## Q1
- Koden er bygget op efter SOLID principperne
- Vi benytter frameworks til at lave testdoubles, til at gøre testene “simplere”
- Fluent assertions til læsevenlige tests - og overskuelige fejlmeddelelser

Kommer ind i CI pipeline

## Q2
Planning poker til at teste om alle har forstået kravene til opgaven, hvis ikke så skal den gøres tydeligere

Data Driven Tests
- Test defineres og data indsamles til formålet - af domæneeksperterne
- Software Test skrives af udviklerne

Gherkin
- Test skrives af domæneeksperterne
- Software test skrives af udviklerne

Software test tilføjes til CI magen til i sidste kvadrant

## Kode
Fixture!  
FluentAssertions

## Q3
Der opsættes brugsscenarier
- Skaber grundlaget for stories i Q2

API-testing / Exploratory igennem Swagger interfacet
  - Hvor godt håndterer api’et random input 
  - Kan det tåle at input kommer i tilfældig rækkefølge

## Q4
Etabler en baseline på performance og Load for at følge udviklingen produktet gennemgår
Lav plan for opgraderinger og planlæg hvornår dette skal ske

- Sikr dine brugeres data <= måske ikke alle højeste prioritet i dette system
- Standarter for Kodekvalitet og krav til review
- Forbindelse mellem service og db og frontend
- Monitorering => Elma.io + Azure

## Code Review
Review af koden i github
- Fælles projekt ejerskab igennem review
  - alle ved hvad alle har lavet (ihvertfald overordnet)
- github forlængelse af holdets kommunikation => højner kodens kvalitet
  - tillid => tør at give konstruktiv kritik og åbne diskussioner


