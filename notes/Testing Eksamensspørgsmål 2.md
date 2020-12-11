---
tags: [Eksamen, Testing]
title: Testing Eksamensspørgsmål 2
created: '2020-12-09T07:53:08.165Z'
modified: '2020-12-10T21:16:35.158Z'
---

# Testing Eksamensspørgsmål 2
- Hvad er Unit-testing?
- Hvordan kan man bruge unit-testing til at forbedre kvaliteten af software.
- Hvad er Fluent Assertion og hvilke fordele og ulemper kan der være ved at bruge det sammenlignet med Xunit eller anden test-framework
- Hvad er Test driven development, TDD, og hvordan bruges det ifm. unit-test.
- Forklar hvordan du har brugt TDD ifm semesterprojektet og fremvis koden for nogle af de unit-test der kom ud af TDD.

## Unit-testing
Hvad er en unit
- isolerede stykker af kode
- Funktionsniveau
- Properties (med logik i getter / setter)

Unit og komponent test skal
- forståelse for opgaven udvikleren sidder med
   - fokus på story
- guide mod rette design
- holde koden så simpel som mulig

Unittestene skal bekræfte at koden fungerer nede i det laveste niveau  
Komponenttestene er med til at bekræfte at det overordnede system design er iorden

Sammen = solidt fundament på produktet

## Fluent-Assertions pro/con
- et Assertion framework ovenpå mstest eller xunit
- Testene får et mere læsevenligt flow 
  - i mange tilfælde også for ikke tekniske personer

- har nogle beskrivende beskeder når tests fejler
  - som inkluderer hele fejlscopet, ikke kun linjen med fejlen
  - Klare fejlbeskeder gør det nemmere at rette fejl!
 
  Ulemper:
  - En ny dependency
  - nyt framework man skal lære

## XUNIT
sammenligning af syntaks øverst

## vs. Fluent Assertion
fejlbesked
## TDD
- Skriv testen først og se den fejle
- Skriv nok kode til at testen går igennem
- refactor!

Testene skal guide udvikler mod målet med story.
- når testene først er på plads giver det et sikkerhedsnet mod nye ændringer.

## Kode
Ikke direkte TDD, men test understøttet development.
- kravene sagde at man organisation var valgfri på et makerspace, men dette er den oprindelige test
- der blev udviddet med en test der tjekkede at organisationen ikke var sat

