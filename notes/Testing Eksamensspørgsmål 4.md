---
tags: [Eksamen, Testing]
title: Testing Eksamensspørgsmål 4
created: '2020-12-09T07:53:08.165Z'
modified: '2020-12-10T22:11:38.527Z'
---

# Testing Eksamensspørgsmål 4
- Hvad er Business facing tests?
- Hvordan kan business facing tests forbedre udviklingen for en backend-udvikler?
- Hvor høre Business facing test, der har til formål at hjælpe programmøren, hjemme i Brian Marick’s quadrant og hvorfor?
- Hvordan kan man udvikle business facing test, så det bliver automatiseret.
- Vis eksempel fra semesterprojektet, hvor i har brugt business facing test. Hvis du har automatiseret en sådan test vil jeg gerne se dette.

## Business Facing test
forstå forretningen / domænet!

Der er to dimensioner i dette:
- Er vores forståelse af domænet og krav der stilles til løsningen korrekt? (Q2)
- Tilsvarer den løsningen vi leverer, kundens ønsker, eller skal der tilpasses? (Q3)

Feedback-loop fra begge Q til udviklerne - det agilt
- for at sikre at det er det rigtige produkt der leveres.
- Udviklernes domæneforståelse skal skabes ved gode aktiviteter i Q3 og Q2
Eventuelle misforståelse bør fanges af Q2 aktiviteter og ved produktdemoer i Q3


Reviews af scenarios og stories er med til at formidle viden - og forhåbentlig skabe forståelse

TEST: Udviklernes Poker planning afslører om der er delt forståelse, hvis ikke kan den story blive sendt tilbage til tegnebrættet

Produktdemo => User Acceptance test (var det, det vi ville have?)
            => Prototypes ^^

## Gherkin
speciel syntaks => forretningsfolk => skrive tests  
=> udviklerne => “rigtige softwaretest”

Gherkin syntaksen ligger tæt på almindelig engelsk:
- Teksten må kun beskrive adfærd - så ikke nogen detaljer om UI
- Det er forretningsfolk der skriver dette - ikke udviklere!

Er også beregnet til at bygge bro mellem faggrupperne
 - skabe en fælles forståelse
 - udbygge udviklernes domæneforståelse også

Elementerne der indgår i gherkin syntaks:
  - Scenarios
    - Overordnet beskrivelse af situationen
  - Given
    - Udgangspunktet ved starten af scenarie
  - When (ikke brugt her)
    - Det event som starter scenariet
  - Then
    - Det forventede udfald af scenariet

## SpecFlow
Automatiserer Gherkin testene:
- her er der et eksempel!

Krav:
- Stringent struktur i Gherkin beskrivelserne

Ulempen:
- er syntaksen
- endnu en dependency
- kan være besværligt at vedligeholde for udviklerne

## DDT
Data Driven Test
- Opbygningen af test er meget nær hvad vi er vant til
- domæneeksperterne står for data til testene
- data kan komme fra flere kilder (så længe det er digitalt)
  - Man kan bruge en dataopsamling som domænebrugerne føler sig tryg ved.




