---
tags: [LinkedInLearning, Store Systemer]
title: Requirement Elicitation and Analysis
created: '2020-10-09T06:47:58.491Z'
modified: '2020-10-09T13:09:41.497Z'
---

# Requirement Elicitation and Analysis

## Elicitation and Analysis Overview
Elicit = indhentning / frembringelse
- opdagelse og udvikling af tankerne om hvad der skal bygges

Analyse
- Analyse af den information der er indhentet, og skabe meningsfulde modeller, spørgsmål og diagrammer, der hjælper holder til at indhente mere information.


- Hvad analyserer man:
  * Folk der bruger systemer og hvordan de bruger det
  * data, regler og scenarios der styrer brugernes adfærd og behov
  * Andre der kan blive påvirket af systemet
- analyse skal være med til at frembringe:
  * den viden man har
  * den viden som udviklingsholdet mangler
    - der laves mere elicitation så uvidenhed omdannes til viden
- analyse skal få brugerne til at tænke og analyse deres eget system
  * de er selv med til at udvikle 
  * de fortæller alt de har brug for i systemet
  * de afslører hvilke aspekter der er de vigtigste

Manglende analyse/elicitation skaber:
- defects
- missed requirements
- scope creep
- over-engineered features
- frustrated users

Man skal kunne forstå tingene der indgår i et system:
- Data
- folk
- processer
- regler
- politikker

Elicit => analyze => elicit

Stille spørgsmål er `eliciting`, og for derefter at sammesætte viden for at opdage flere spørgsmål er `analyse`.

### Graden af detaljer
- Første lag
  * hjælp stakeholders med at forstå hvorfor en løsning er vigtig
  * hvilke muligheder skaber dette?
  * skaber en delt forståelse af formålet => samme mindset og retning i det fortsatte arbejde
- Andet lag
  * Forstå brugernes mål når de benytter produktet
  * hver mål beskrives ud fra `who/what/why` eller `role/goal/benefit`
- tredje lag
  * forstå hvert mål (fra andet lag), for at tilvejebringe yderligere detaljer
- fjerde lag
  * forstå detaljerne der er nødvendige for hvert mål
    - data, regler, brugergrænseflade, automatisering, interface med andre systemer osv...

### Mindset til denne fase
1. fokuser på at bygge det rigtige til kunder, brugere og forretning
2. arbejd sammen med stakeholders, og hjælp stakeholders til at få formidlet sine behov
  - Det er sjældent at de italesatte krav fra stakeholders, er de eneste krav.
  - vi skal prøve at få resten ud af dem.
    * Vi skal snakke og tegne for at klarlægge alle krav, og gøre det usagte til noget sagt.
3. Forstå og omfagn din rolle som facilitator til at få skabt beslutninger i requirement-processen
  - hjælp virksomheden til at tage de rette beslutninger, i forhold til det produkt de vil have
  - hjælp udviklerne til at tage se rette beslutninger, når de skal til at bygge produktet

---
## Elicitation Techniques
Opdage og udtrække information som giver holdet en dyb, delt forståelse af kundens og forretningens behov.

Bruges til at finde
- krav
- behov
- risiko
- afhængigheder
- antagelser
- muligheder

Kunden ser på produktet med andre øje end udviklerne gør, derfor skal de hjælpes til at tænke og snakke om de rigtige emner. Dette er for at frembringe endnu bedre ideer end der var i starten.
1. Approach can include planned and unplanned activities.
2. Techiniques can vary by level of formality.
3. You need to do research to elicit.

### Interview
Kan bruges til to overordnede ting:
- relationship building tool
- Deeper dive into the details of someone's domain or scope of work

For at lave effektive interview, nedbrydes dette til 3 steps:
- Forbered
  * Hvem skal interviewes, og hvordan opnår man en forbindelse til dem?
  * Hvad skal interviewets udbytte være?
  * to tyder af spørgsmål:
    - inddragende spørgsmål der åbner op for dialog
    - uddybende spørgsmål der skal tilvejebringe flere detaljer
- Udfør interview
  * Opbyg relationen lidt, inden man kommer til formålet med interviewet
  * Hav 3 til 5 spørgsmål klar til et 60 minutters interview.
    - oprethold et godt flow, som ikke bliver for rigidt eller struktureret
    - opfang interviewet i nogle reminder-bullets i stedet for at skrive alt der bliver sagt ned
- Opfølgning
  * Få respondenten til at verificere at du har opfanget de vigtigste punkter under interviewet
  * Mød dem og få dem til at verificere en model du har kreeret på baggrund af interviewet

### Brainstorming
Brainstorming emner:
- stakeholders der påvirkes
- features i løsningen
- løsningsmuligheder
- alternativer
- risiko
- måder hvorpå man kan løse problemstillinger
- brugeres reaktioner og følelser
- scenarier og særtilfælde

Husk at en effektiv session kræver planlægning og effektive teknikker.
- Individuel brainstorming
- gruppe brainstorming

Brug materialer til at aktivere folk til brainstorming, for at folk kan være aktive og anonyme, så både introverte og ekstroverte kan deltage:
- flip charts
- post its
- andre materialer

### Observation
Forstå et problem, se hvordan en person løser problemer og hør personen fortælle om de følelser der aktiveres i forbindelse med opgaven.
- Hvad tænkes der på imens produktet bruges?
- Hvilke beslutninger tager de imens de bevæger sig igennem systemet?
- iagttag om der bruges andre værktøjer som ikke er en del af systemet.
- virker systemet som forventet (i brugerens perspektiv)

Der er to typer af observation:
- Passiv:
  * Der bliver ikke interageret med brugeren
  * Forstå brugerens process og følelser
  * hvornår er de frustrerede og hvornår er de glade/tilfredse
- Aktiv:
  * Arbejder sammen med brugeren
  * Stiller spørgsmål undervejs for at forstå og bekræfte hvad vi ser
  * tager længere tid og afbryder brugeren

I begge tilfælde, hold øje med:
- brugerens følelser imens systemet bruges
- bruger de anden viden end det som pruduktet tilbyder?
- bruger de viden fra et andet system, et stykke papir, eller bliver der taget beslutninger på baggrund af viden de allerede har?
- Hvornår tar de beslutningerne og hvad påvirker dem?

### Experiments
Brug eksperimenter til at opdage blinde vinkler i analyse/elicitation.
- Test ideer, formodninger og nøgleteorier, der dikterer kravene til produktet eller systemet.

Det er en god ide at lave eksperienter hvis:
- krav er svære at definere
- krav bliver ved med at ændre sig

For at planlægge et eksperiment, skal man være klar over hvad man gerne vil lære noget om
- Hvad vil du præcist lære noget om? (indskrænk undersøgelsen til det relevante område)
- design eksperimentet til at ramme så præcist ned i det relevante område som muligt
### Workshops
Workshops skal bruges til at udvinde relevant information.
- High impact collaboration med stakeholders
- deep dialog
- udforskning af ideer og detaljer

Workshop forberedelse:
- Definer målet med workshoppen
  * hvad for noget information har vi brug for, for at kunne fortsætte
  * hvordan vil workshoppen også give værdi til de stakeholders der deltager
- Hvem skal deltage i workshoppen, og hvad er deres rolle?
  * diskuter workshoppens dagsorden og stakeholders rolle med dem inden, så de forstår hvad de selv får ud af det
- Design workshoppen
  * punkter på en dagsorden er ikke nok til at facilitere god dialog og tankeprocesser

Som Workshop facilitator:
- udtræk den information der er nødvendig for at nå dit mål
- vær neutral i faciliteringen
- understøt idegenerering 
  * start med at tænke bredt først
  * efterfølgende trækkes ideerne ind til mere konkrete punkter
- nogle ideer skal parkeres, og først trækkes frem igen på et andet tidspunkt
- holde workshoppen fokuseret, og ikke distraheret på andre mål

Workshop opfølgning:
- del værdihulde artefakter med deltagerne
  * hvad er den mindste mængde information der kan bruges til at trigger folks erindring om workshoppen
- dokumenter betydelige handlings punkter, betydelige beslutninger og modeller, diagrammer eller lister som giver værdi

---
## Analysis Techniques
Analyse skal belyse hvordan hænger tingene sammen på baggrund af elicitation. Hvilke mål opnås og hvordan disse opnås.
- Frembringer detaljer der ikke har været tænkt på
- undgå at overkomplicere produktet med detaljer som brugerne ikke behøver eller er ligeglade med

Analyse består af:
- tanker
- dialog
- modellering
- diagram
- organisering

### Process models
Skal være simple:
- Hvad bliver modelleret?
  * den nuværende tilstand
  * den fremtidige tilstand
- arbejd dig lagvist ned i systemet
  * start med modeller i high level og arbejd ned i lagene med flere detaljer gradvist
  * navngiv processer og aktivitetet ud fra et "verbum + substantiv" format
- vær specifik og fokuser på handlinger

### Context diagrams
Se under ["Business Modeling" overskriften "Context diagram"](Business Modeling.md)

### User stories and story mapping
- User stories
  * holder pladsen for en fremtidig samtale
  * Består af `who/what/why`
  - Accept kriterier:
    * Viser detaljerne af hvordan en succesful handling i en story ser ud, fra brugerens synspunkt
  - Hvis user story bliver for stor (indeholder mange funktionaliteter) skal den splittes til flere mindre stories
- Story map
  * viser et kort over hvordan User Stories er relaterede til hinanden
  - viser eksempelvis hvordan splittede stories hænger sammen

Disse værktøjer kan benyttes til at opdage huller i vores viden

### Decision tables
Bruges til at organisere og vise logik der ligger til baggrund for beslutninger

Lav overskrifter der repræsentere hver beslutning - ideelt er hver beslutning i "ja/nej" format:

Eksempel fra LinkedInLearning:
| | Perferred customer? | Order over $50? | Standard? (no rush) | shipping cost|
|---|---|---|---|---|
|1.| yes | yes | yes | $0 |
|2.| yes | yes | no | $20 |
|3.| yes | no | no | $20 |
|4.| no | no | no | $20 |
|5.| no | yes | no | $0 |
|6.| no | yes | yes | $0 |
|7.| no | no | yes | $20 |
|8.| yes | no | yes | $0 |

### Data flow diagrams
Visuelt hjælpemiddel til at vise processer og det data der går igennem dem.
- data flow er det primære fokus

### State and sequence diagrams
State diagram fortæller noget om hvilken tilstand et objekt kan være i.
- Hvilke forskellige tilstande kan objektet have.
- Hvad forårsager en tilstandsændring?

Sequence diagram
- viser interaktionen mellem folk og forskellige dele af systemet
- hjælper med til at skabe en fælles forståelse af hvordan forskellige beskeder sendes mellem folk og systemerne.
  * Man der dermed lettere afklare hvornår der forventes svar på en besked

---
## Tailoring to the Project or Product Type
### nyt produkt
Hvor starter man med dette hvis det er et helt nyt produkt?
- forstå det behov produktet skal dække og hvilke mål der hører hertil.
- Hvad er successkriteriet?
- Hvorfor bruger vi en masse tid og penge på en ny løsning?
  * desuden:
  - hvilke udfordringer er der ved den nuværende situation/løsning?

1. Udarbejd et context diagram:
  - hjælper med at identificere de målgrupper der er til det kommenede produkt
2. Udarbejd en processmodel der viser nuværende og fremtidige processer
  - opnår en fælles forståelse på holdet om de forventede forandringer den nye løsning bringer med sig.
  - den fremtidige processmodel bruges til elicitation og analysis

Hold dig til visionen der følger med løsningen:
- visionen skal være i fokus i alle diskutioner på holdet.

### eksisterende produkt
Hvordan sikrer man at man arbejder på det rette når man tilføjer ny funktionalitet til et system?
- analyser backlog for at identificere mønstre:
  * Hjælper det enkelte item os med at bevæge os fremad, eller holder det os i fortiden?
  * Findes der gentagelser, konflikter eller mange items der er relateret til en bestemt del af projektet?
  * bliver den samme problemstilling rapporteret ofte på forskellige måder?
  * Hvad er årsagen til hvert problem?
  * Hvilke problemstillinger begrænser den værdi brugerne opnår ved at bruge løsningen?

Udfør elicitation med den bruger der har forespurgt noget funktionalitet eller oplevet en fejl.
- undersøg alternative måder hvorpå forespørgsler kan løses

### indkøb af ny software
Brugere og organisationen skal tilpasse sig til processen i den nye software i stedet for at tilpasse softwaren. Dette vil spare organisationen en masse penge og ikke skabe en masse bekymringer senere.

Arbejdet med kravindsamling er lidt anderledes når man arbejder med indkøbt software
1. Fokuser på brugerne, og de mål de skal opnå ved at bruge systemet
  * Det er upraktisk/ikke muligt at ændre i indkøbt software
  * derfor er det ikke nødvendigt at overveje tekniske eller funktionelle detaljer
  * Det vigtigste: Softwaren SKAL understøtte at brugernes aktiviteter.
    - brugeren tilpasser sin arbejdsprocess til softwaren, ikke omvendt
2. Forstå forretningsregler, logik, politik og beslutninger som du vil have system til at udføre/overholde
  * Sikr dig at det indkøbte system er i stand til dette og kan konfigureres til at imødekomme.
3. Overvej hvordan det indkøbte software definerer og forbinder data
  * prebuilt software har predefineret datadefinitioner, antagelser og relationer som ofte er forskellige fra organisationens
  * Disse forskelle er vigtige at forstå før systemet implementeres
4. Definer forretningens formål med integrationen, hvilke processer der understøttes og hvordan brugerne påvirker med og uden integrationen.

Baseret på: [LinkedIn Learning: Requirement Elicitation and Analysis](https://www.linkedin.com/learning/requirements-elicitation-and-analysis/)
