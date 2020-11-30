---
title: Theme planning - Testing in release
created: '2020-11-26T08:05:10.436Z'
modified: '2020-11-30T14:49:44.411Z'
---

# Theme planning - Testing in release
## Testing Product Release
> "What testers do when their ream takes time to plan their release"  

__Formål:__  
Store planer følger ikke den agile tankegang, men for at planlægge sprints har man samtidig brug for et overblik over projektet for at kunne se brug og relevans:

1. Hvad er kerneydelsen af produktet?
    - need vs. nice
    - hvad er Minimal Viable Product?
    - Deadlines
2. Hvilke andre teams skal involveres for at udvikle produktet?
    - Grafik, front/backend, eksterne teams, speciel hardware
    - Er der nogen ventetider?
3. Hvilket behov for test har produktet? UAT, UNIT, UI m.f.
    - Hvilke test er vigtigst
    - start med det minimale behov, men husk at teste på kerne
4. Hvornår er dealine og hvordan opbygges sprints
    - En endelige deadline
    - længde på sprints 
    - hvor store må hver opgave være

## Sizing stories - not estimating
- Test af stories
  * stor uenighed viser at man ikke har ens opfattelse af opgaven

## User Story - Sizing
  - Hvad er konteksten til en user story
  - sammenhængen til andre usecases => hvilke usecases er den pågældende usecase afhængig af?

1. Læs og beskriv story til PO => har man samme forståelse
2. Opdel en story i mindre dele:
    - Design og grafik
    - Funktionalitet ved frontend
    - Funktionalitet ved backend
    - Test, både automatiske og user
    - Release, merging m.m.
3. Brug planning poker for at tjekke om man har samme forståelse/sizing
4. Husk estimat kommer først i sprint

## Prioritering
- Hvad er `need to have`? 
- hvad er `nice to have`?


* Ny teknologi tager tid at lære og bør derfor prioriteres tidligt i forløbet
* Risikovurdering ved stories. (ukendte ting der kan eksplodere i tid)
* Definering af test til de kendte stories
* Tredjeparts involvering kan koste tid (ventetid). Start tidligt med disse opgaver.

## Testpan
Testplan er til en tidlig udgave af hvornår hvilke stories vil kunne testes.  
Man vil ikke kunne lave en detaljeret testplan...

Planlæg følgende:
1. Typer af test
2. CI/CD
3. Test miljø / dev Ops
4. Testdata
5. Mulighed for rapportering af testresultat

## Code coverage
Hvor meget kode afdækkes af tests.
