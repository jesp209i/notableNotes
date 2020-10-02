---
tags: [Context, Cross-Functional Flow, Flowchart, Functional Flow, LinkedInLearning, Process Map, Store Systemer]
title: Business Modeling
created: '2020-10-02T07:08:56.753Z'
modified: '2020-10-02T14:52:01.940Z'
---

# Business Modeling

Før der kan laves ændringer bør man forstå hvordan organisationen passer ind i det overordnede billede.

## Definition: Business Process modeling
1. indfang serier af processer
  * hvordan er de indbyrtes forbundede
2. visuel repræsentation
  * identificer:
    - __Hvem__
    - gør __Hvad__ 
    - __hvornår__ / i hvilken rækkefølge
3. Identificer behov

Business modeller bruges til:
- at vise den nuværende tilstand
- definere den fremtidige tilstand
- identificere "gaps" mellem de to tilstande på en måde der kan forstås af de fleste

The value business process modeling represents to the organization is to visually demonstrate the flow of activities between various stakeholders, and the interaction that enables outcomes to be achived.

Stakeholder = actor (i modelleringssprog) kan være en person, en afdeling, et system, eller en ekstern entitet til organisationen.

Fordele ved proces modellering:
- sikrer en forståelse af hvordan en organisation:
  * kører sin forretning
  * udfører sine aktiviteter lige nu 
  * relaterer til verden udenfor 
- identificerer områder i forretningsprocesserne som ikke er klare
  * Dermed kan ansvarsområder gøres tydeligere igennem hele processen
- Identificerer komplekse business processer
  * tillader at de kan nedbrydes til mere overskuelige processer
  * hjælper med at identificere steder hvor processerne ikke er effektive
- Modellerne fungerer som dokumentation
  * kan hjælpe med at skabe læringsmaterialer ved et skifte mellem "ny" og "gammel"

## Modellerings værktøjer
Proces modellering fanger  sammenhængende mellem folk, processer, aktiviteter og systemer.

Diagramtyperne listes her i en rækkefølge hvor der startes meget high-level, og bevæger sig ned i mere low level diagrammer der viser flere detaljer.
* [Context Diagram](#context-diagram)
  - High level der viser organisationens overordnede interaktion omverdenen
* [Functional Flow Diagram](#functional-flow-diagram)
  - Viser den overordnede interaktione mellem organisationens afdelinger/funktionsområder
* [Cross-Functional Flow Diagram](#cross-functional-flow-diagram)
  - Viser interaktionernes flow mellem afdelinger/funktionsområder i forbindelse med en process.
* [Flowchart Diagram](#flowchart-diagram)
  - Viser den enkelte aktørs arbejdsflow

---

## Context diagram:
Viser organisationens interaktioner med omverdenen:
- Tilbyder et overordnet high-level billede
- Fungerer som en check-liste
- Fungerer som et overbliksbillede i forhold til omverdenen
  * Giver overblik over relationer til eksterne entiteter

### Formålet med diagrammet
* giver forståelse for hvorfor en relation eksisterer
  - uderligere skabes forståelse for hvorfor afdelinger/funktionsområder eksisterer internt i organisationen, da disse er nødvendige for at understøtte en ekstern relation/interaktion
* Kan give overblikket over scopet af et nyt projekt:
  - Giver et overordnet overblik over hvordan projektet påvirker organisationen
  - Dermed kan man nemt identificere de relationer der skal ændres i forbindelse med projektet
    - Disse ændringer giver scope og danner baggrund for analyse med henblik på hvad der skal ske i forbindelse med projektet
* Som nyansat er context diagrammet en god måde at få overblik over organisationen, samt dens interaktioner
  

### Diagrammets indhold
![Context Diagram](./BigSystems/ContextDiagram.png)

- Organisationen er i midten (cirkel)
  * Det er her du kan styre processer
- udenom er de eksterne entiteter som har interaktioner med organisationen (firkanter)
  * Deres processer skal ikke modelleres
  * Du kan ikke kontrollere deres processer
- der går pile (frem og tilbage) mellem organisation og hver entitet 
  * Pilen indikeret retningen på flowet
  * På hver pil er der en label fortæller hvilken type interaktion pilen repræsenterer; eksempelvis:
    - Matrialer, fakturaer (pil fra leverandør entitet mod organisation) (inputs)
    - Ordrer, betalinger (pil fra organisation mod leverandør entitet) (outputs)
    - Bemærk at der på en pil er angivet flere flows
      * Dette er for at højne læsbarheden og diagrammets simplicitet
  * Vi er kun interesserede i pile til og fra vores organisation
- Der bør være både input og output fra hver entitet til organisationen

### Vær opmærksom på
- Der kan optages for meget data, så diagrammet bliver uoverskueligt
  * Hvis der er entiteter interagerer med organisationen på en overordnet ens måde, så slå dem sammen.
- Context Diagrammer kan ikke:
  * indikere intern funktionalitet
  * indikere timing eller system operationer
  * opfange alle relationer

---

## Functional Flow Diagram
Viser funktionsområder eller stakeholders der er interne i organisationen samt deres overordnede arbejdsflow imellem hver især.
- Fortæller ikke noget om ___hvordan___ arbejdsflowet udføres

### Formålet med diagrammet
- identificerer målgrupper i organisationen
- kan bruges til at validere stakeholdere (har man fat i den rette afdeling/funktion)

Gode spørgsmål til at hjælpe med analysen:
- hvem udfører/har ansvaret for aktiviteter
- hvad foranlediger en aktivitet
- hvor lang tid tar en aktivitet

### Diagrammets indhold
![Functional Flow Diagram](./BigSystems/FunctionalFlowDiagram.png)

- Diagrammet starter altid med en stakeholder (typisk en kunde eller en anden ekstern entitet) der starter en transaktion
- Man kan så se hvilke funktionsområder er indgår i transaktionen
- pile mellem funktionsområder indikerer interaktionerne mellem dem
  - labels på pilene forklarer hvad der bliver udvekslet mellem områderne
    * information
    * data
    * aktiviteter

### Vær opmærksom på
Du får problemer hvis:
- der er manglende validering af tidligere steps (Context diagrammet)
- FFD ikke er valideret og derfor mangler der at blive modelleret områder
  * pas på med antagelser om bestemte funktionsområder bør indgå
- hold diagrammet på et overordnet niveau

---

## Cross-Functional Flow Diagram
Kendes også som aktivitetsdiagrammer eller swimlane diagrams.

Diagrammet viser en proces, hvor det er tydeligt angivet, hvornår en given aktør, skal udføre en bestemt aktivitet, for at processen kan fortsætte og til sidst gennemgøres.

### Formålet med diagrammet
- identificer komplekse processer
  * og nedbryd dem til mere overskuelige processer
  * flere efterfølgende steps i en afdeling kan samles til en subproces
    * subprocesser dokumenteres i sine egne dokumenter
- identificer unødvendige ruter i processen (hvor arbejdet måske går frem og tilbage mellem afdelinger)
- identificerer ineffektivitet

### Diagrammets indhold
![Cross-Functional Flow Diagram](./BigSystems/CrossFunctionalFlowDiagram.png)

Diagramstrukturen gør det nemt at se den individuelle aktørs aktiviteter og se de interaktioner der krydser funktionsområder.

Disse diagrammer gør det meget nemt at vise hvordan en proces gennemføres fra start til slut, samt hvad hver stakeholder/aktør har brug for, for at kunne gennemføre aktiviteten

__Typiske Diagram elementer:__
* cirkel - "terminator"
   - indikerer start og slut på en process
* rektangel - "process box"
  - indikerer en handling
* rektangel med paralelle linjer - "sub process"
  - indikerer en gruppering af handlinger
  - dokumenteret som en seperat process
* plus-symbol i box
  - indikerer at der er mere info til den pågældende handling
* diamant - "decision"
  - indikerer at der skal tages en beslutning her, som påvirker hvordan processen fortsætter
* pile - "connectors"
  - indikerer den rækkefølge handlingerne skal udføres i
  - viser samtidig læseren i hvilken rækkefølge diagrammet skal læses

Dette er bare et udsnit - uanset hvordan kan gør, bør man være konsekvent i alle sine dokumenter.

### Vær opmærksom på
- man skal ikke modellere uden at forstå funktionsområderne
- pas på med for mange detaljer
  * grupper aktiviter til subprocesser
- hold diagrammet til omkring 16 aktiviteter for at undgå for stor detaljerigdom
- brug kun et begrænset antal af diagram elementer
  * modellerings software tilbyder mange typer af elementer - det giver et forvirrende indtryk og gør det svært at læse dine diagrammer hvis alle mulighederne benyttes. 
- del diagrammerne med stakeholders
  * planlæg workshops til modellering, reworks og yderligere samtaler
  * Send dokumentation til stakeholderes forud for workshops og kræv at de kommer og er forberedte
  * Versionskontrol med diagrammerne
  * stakeholderne validerer og godkender de endelige diagrammer

---

## Flowchart Diagram
- også kendt som __Process Maps__

Dokumenterer et aktivitetsflows udførsel for en aktør. (Low level)

### Formålet med diagrammet
- kan både laves som:
  * tilstanden er idag
  * en fremtidig tilstand

Model til at analyse tilstanden idag (KRAC-modellen):
- __K__ eep (behold aktivitet)
- __R__ emove (fjern aktivitet)
- __A__ dd (tilføj aktivitet)
- __C__ hange (ændre aktivitet)

Forskellem mellem tilstanden idag og en fremtidig tilstand skaber et sæt af krav der skal opfyldes for ændringen kan gennemføres:
- identificer ændringerne og analyser indvirkningen på eksisterende funktionsområder

Fordele:
- nedbryd komplekse processer
- identificer ineffektivitet
- fungerer som en "single source of truth"
- Diagrammet kan hjælpe med at skabe nye læringsmaterialer og dokumentation til slutbrugere
  * Diagrammet er grundlæggende en step-by-step guide for en bruger i et bestemt flow

### Diagrammets indhold
![Flowchart Diagram](./BigSystems/FlowchartDiagram.png)

- Viser den individuelle aktørs handleringer i et flow.
- Flowchart diagrammet refererer tilbage til et __Cross-Functional Flow Diagram__
  * sagt omvendt: Et flowchart er en subprocess i et Cross-Functional Flow Diagram
- Der er ingen interaktioner med andre funktionsområder
- Bruger nogle af de samme diagram elementer som Cross-Functional Flow

### Vær opmærksom på
- undgå at lave en hybridversion af CFFD og FD
- forstå den bagvedliggende kontekst inden modelleringen starter

---

Baseret på: [LinkedIn Learning: Business analysis foundations](https://www.linkedin.com/learning/business-analysis-foundations-business-process-modeling/)








