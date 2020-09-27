---
tags: [Kravspecifikation-arkitektur-kvalitet.pdf, Store Systemer]
title: Kravspecifikation
created: '2020-09-25T07:12:10.121Z'
modified: '2020-09-26T08:49:55.636Z'
---

# Kravspecifikation
- 25. september

Skab en fælles forståelse omkring hvad der skal udvikles blandt:
- Udviklere
- Kunde
- Brugere

## Hvad er et krav?
  - Hvad et system skal kunne (iflg Kunden)
- To vigtige aktiviteter
  - kravindsamling
    - Hvem er brugerne
    - Hvilke aktiviteter/funktionalitet skal understøttes
      - Use cases skrives med brugerne
      - finpudses
    - forbind usecases
    - blive enige om ikke funktionelle krav
  - Analyse

## Fælles applikationsdesign
  - Joined Application Design (JAD) = workshops
    - Klarlæg kravene rimelig specifikt
    - opsplit projektet i delkomponenter
    - stil en masse uddybende spørgsmål
      - stil flere uddybende spørgsmål
      - tålmodighed i forbindelse med kravindsamlingen
  - Rapid Application Design (RAD) = genbrug

## Udfordringer ved Kravindsamling:
- domæneviden
- domænefroståelse 
  - fortolker man domæneviden korrekt
  - har interessenterne også samme domæneforståelse
  - Stil uddybende spørgsmål og stil flere uddybende spørgsmål

### Værktøjer til kravindsamling:
- Scenarier (eksempler på interaktion mellem slutbruger og system)
- Use cases (en scenarie-klasse)

Der arbejdes i et naturligt sprog som alle forstår!

- Udviklerne "tegner" og "oversætter" virkeligheden
  - ==> Modellering
  - lave fælles forståelse
- Der testes vha. prototyper

## Kravtyper: (FURPS)
- funktionelle (F-)
  - funktionaliteter i produktet
- nonfunktionelle (-URPS)
  - Usability
  - Reliability
  - Performance
  - Supportability
- Andre krav (tilføjet) (kan også være en del af non funktionelle krav)
  - Hård krav fra kunden
  - (eksempelvis skal køre Linux, eller skal samarbejde med et eller andet system)
- use cases
  - workflow
  - konkrete mål for enten brugere eller eksterne system kald
- scenarier
  - grupperinger af lignende use cases

