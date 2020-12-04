---
tags: [Store Systemer]
title: Distribuering
created: '2020-11-25T08:36:08.809Z'
modified: '2020-12-04T08:32:23.857Z'
---

# Distribuering
De fire søjler i OOP
"a pie" => abstraction, polymorfism, inheritance, 

## Faser i udvikling

1. Systemanalyse
    * Beskrive formål => app dele
2. Systemdesign
    * arkitektur (subsystemer, flow), platform
    * "off-shelf" komponenter (abstraktion)
3. Objektdesign
    * Applikationsobjekter + "off-shelf"-komponenter

## Objektdesign
- Genbrug
- Service specifikation
- Object model
  * Restrukturering
  * Optimering
- Objektdesign er ikke sekventielt

## Genbrugsproces
- Omhandler nedarvning (inheritance)
  * Super- og subclass (base class => derived class)
- Opnås igennem generalisering
- Målet er at undgå redundans

## OOD: Design Pattern
1. Unikt navn
1. beskriv problemet
1. Klasser og interfaces der indgår i løsningen
1. Analysere konsekvenser
    * Hvilke problemer kan man komme ud for

Problemet er at alt bliver grupperet og veldefineret (og derfor låst), hvordan opnår man fleksibilitet (så der er plads til udvidelser og ny teknologi)
- Løsning: forudse ændringer => medtag i design

## Frameworks:
- Infrastruktur: intern brug
- Middleware: integration
- Enterprise Apps: specialiserede

Ovenstående kan generelt inddeles i:
- White box: nedarvning
- Black box: interfaces

## Konklusion
I forbindelse med design af store systemer vær opmærksom på:
- Design det rigtigt fra starten (struktur + objekter)
- Bland (Mix and match)
  - både egne komponenter og andres hvis de løser det rigtige problemstillinger
- Opdater
