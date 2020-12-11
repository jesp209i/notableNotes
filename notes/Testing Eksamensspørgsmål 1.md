---
tags: [Eksamen, Testing]
title: Testing Eksamensspørgsmål 1
created: '2020-12-09T07:53:08.165Z'
modified: '2020-12-10T20:42:19.669Z'
---

# Testing Eksamensspørgsmål 1
- Forklar hvad SOLID er og hvordan det har indflydelse på test.
- Hvilken quadrant i test-quadranten af Brian Marick’s, har SOLID primært indflydelse på og hvorfor.
- Hvad er Chaos Engineering. Hvad kan det bruges til ifm. forbedre kvaliteten i software. 
    - Hvor ligger Chaos engineering i test-kvadranten?
- Vis eksempler fra semesterprojektet, hvor du overholder mindst 3 af principperne i SOLID.

## Solid
Solid giver nogle principper for at lave testbar og genbrugelig kode:
- hvordan klasser skal designes
- hvordan man styrer afhængigheder
- Det tvinger dig til at tænke over opbygningen af din kode  
- SRP
   - En klasse skal kun have et formål
- OCP
   - Åben for udvidelse, men lukket for ændring!
   - Interface (lukket for ændring) => implementering (udvidelse) 
- LSP
   - Subtyper skal kunne udskiftes hvis de opfylder en fælles supertype
   - Handler om at hver subtype implementerer en opførsel som tilsvarer hensigten i supertypen, hvis ikke er det en violation
   - Amimal(Speak) => snail og Animal(Speak) => Parrot
- ISP
   - Split interfaces op i flere interfaces, når HELE det oprindelige interface ikke giver mening at implementere i en konkret klasse
- DIP
   - Lad kode afhænge af abstraktioner, ikke af konkrete implementeringer

## Chaos engineering
Man undersøger hvor robust et system er, ved at udsætte det for nogle forskellige forhold.
- Det teknisk setup
    - Mist forbindelse til en disk
    - Fuld load på CPU
- Konfiguration i forbindelse med fallback / safety net systemer
    - Nedlæg services i systemet

Skal give drifts folk en ide om hvor der skal sættes ind for at holde systemet kørende
- Det højner overall systemets resiliens

## Test kvadranter
I STQ ligger SOLID meget nært til koden og udviklerne - Q1 (supporting team/ tech-facing)
- Trækker sportil Q4
    -Maintainability + code reviews

Chaos Engineering Kritisere produktet med en teknisk vinkel - så er vi i kvadrant 4!

## kode SOLID
Tager udgangspunkt i måden hvorpå vi bruger validators i vores kode.

For at vi kan genbruge validators har lavet et interface som der valideres imod (i steder for en konkret implementering)
- Klasserne er opbygget til kun at have et ansvar 
  - valideringen som “ligner” at den hører til klassen, har et andet ansvar og er flyttet ud => single responsibility principle
- Interfaces kan implementeres af flere forskellige klasser (extension) 
  - men interfacet er lukket for modification nu (Open/Closed Principle)
- Ved at bruge interfacet kan vi sende forskellige typer ind i validatoren 
  - så længe de overholder interfacet => Liskovs Substitution Principle
- Vi har nogle klasser hvor der er sammenfald imellem properties, men hvor klasserne har forskellige valideringsbehov
  - Delt ud på flere interfaces som der kan valideres på efter behov  => Interface Segregation Principle
- Samme eksempel: ved at bruge Interfaces har vi ikke nogen direkte dependencies på implementeringer - kun på abstraktioner => Dependency Inversion

