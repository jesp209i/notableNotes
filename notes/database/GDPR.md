---
tags: [Database, developers-guide-to-gdpr.pdf]
title: GDPR
created: '2020-10-04T07:05:33.390Z'
modified: '2020-10-04T09:30:29.534Z'
---

# GDPR

## Hvem påvirker det?
- Alle (virksomheder) der opsamler data der kan forbindes til en person i EU
- Alle virksomheder der tilbyder goder eller services til, og/eller iagttager opførslen af EU data subjekter, uanset om de har fysisk tilstedeværelse i EU.
  * Dvs virksomheder udenfor EU som handler med borgere i EU er forpligtet til at overholde GDPR
- Virksomheder med applikationer der holder/indsamler personlig information om en person.
- GDPR handler ikke kun om data opsamlet i et computer-program, men al opsamlet personligt data uanset hvordan det opsamlet eller gemt.

## Hvilke data handler det om?
- alle data der direkte eller indirekte kan bruges til at identificere en person:
  * Navn, foto, emailadresse
  * aliaser/nicknames på sociale netværk eller posteringer herpå
  * bankdetaljer
  * sundhedsdata
  * IP-adresser
  * observeret data:
    - opførsel eller brugsmønstre

For udviklere betyder dette at data privacy skal indarbejdes som krav, og tages med i alle forretningsprocesserne i en applikation.

Man må stadig opsamle alt det data man vil, MEN!
- Man skal have et veldefineret formål med at indsamle data.
  * VIGTIGT!! Man må ikke opsamle data som man TROR der kan være brug for, eller som man måske SENERE får brug for.
- Brugere skal:
  * informeres om indsamlingen
  * eksplicit godkende ovenstående

Udviklere skal strukturere deres dataprocesser med effektive pseudonymization strategier.

Der er ikke nogen former for begrænsninger på hvilke typer applikationer der må bygges, men GDPR placerer brugerens behov for privatliv højere end virksomhedens forretningsmål.

## Hvornår gælder reglerne fra?
Fra den 25. maj 2018 kan GDPR håndhæves af myndighederne.

Alle applikationer skal indsamle brugerens accept før der må indsamles data, og det skal fra starten være tydeligt hvordan denne data bruges.
- Det er ikke tilstrækkeligt at beskrive hvad data bruges til under paragraf 23.r3.A i et "terms and conditions" dokument.
- Data politikkerne skal være forklaret i klart og tydeligt sprog og være nemt for brugere at gennemlæse
- brugeres skal desuden kunne trække sig fra aftalen når/hvis de vil

GDPR specificerer en brugers ret til at tilgå deres data. Dette betyder at det for en bruger skal være muligt at få:
- En kopi af deres aktuelle data
- en beskrivelse af hvordan data bliver brugt
- en forklaring af hvordan datapunkter paseret på algoritmer bliver dannet

Desuden har en bruger ret til at blive "glemt"
- Udviklere skal vide hvordan de håndterer dette:
  * enten ved at slette alt brugerdata
  * eller ved at afkoble brugerdata fra brugerens identitet

Hvis der sker et data breach, har virksomheden maksimalt 72 timer til at gøre brugere opmærksom på dette, fra tidspunktet hvor de bliver opmærksomme på den uauthoriserede adgang.

## Hvor gælder reglerne?
Reglerne gælder på alle steps mellem virksomheden og brugeren.
- Data Privacy skal beskyttes på en konsistent måde fra første kontaktpunkt (website eller app eksempelvis), og videre til alle servere/databaser/andet derimellem.
  * Det betyder at tredjeparts leverandører (der på en eller anden måde er involveret i ovenstående) også skal beskytte dine brugeres privatliv.
  * Både virksomhed og tredjeparts leverandør kan få bøder for overtrædelser

Koordiner med tredjeparts leverandører så brugere kan få indblik i det opsamlede data. Når en bruger anmoder om at få sit data udleveret skal dette ske indenfor rimelig tid

## Hvorfor er det vigtigt?
Udviklere skal opretholde en balancegang mellem forretningskrav og privacykrav.

## Bonus: Hvad skal man spørge tredjeparts leverandører om?
For at sikre sig at de også er compliant med GDPR. Dette gælder naturligvis kun hvis leverandøren indgår applikationens environment på den ene eller anden måde.

Leverandører skal kunne levere en klart defineret, dokumenteret strategi for:
- Hvilke processer der sørger for at GDPR overholdes
- Hvad deres sikkerhedsframework er
- Hvordan de håndterer data

Hvis ovenstående ikke er iorden kan du udsætte din virksomhed for ricisi.

### Spørgsmål til leverandører:
- Hvor er jeres servere og computere placeret fysisk? Er det muligt at vælge hvilken lokation man benytter?
  * Selv ved en cloud service kan den fysiske placering af serverne have betydning for hvordan GDPR påvirker dig.
- Hvordan sørger deres platform for at pseudonymisere brugerdata i forbindelse med integrationer til eksterne systemer?
  * Når brugerdata integreres med deres system, er det nye data så personidentificerbart, eller er det forbundet til et alias? Jo mere afkoblet, des sikrere vil det være.
- Hvad er planen for underretning i tilfælde af brud på data?
  * Det er vigtigt da din virksomhed skal underrette dine brugerne indenfor 72 timer. Leverandøren skal have mulighed for at underrette dig så du kan leve op det dette krav.
- Hvordan overholder de dine brugeres ret til at få adgang til sine data, eller retten til at blive "glemt"?
  * Hvordan koordinerer din virksomhed med leverandøren, så brugeren kan se sine data, eller anmode om at blive slettet/glemt.

### Spørgsmål til Identity og Access Management leverandører
Spørgsmål til at klarlægge hvordan sikkerhed og data privacy håndteres.
- Hvad er deres default password begrænsninger, og kan disse justeres?
  * Der bør være et mangfoldigt sæt af krav, og det skal være muligt at tilpasse dem efter behov.
- Hvilken password-hash bruger de, og benytter de unikke salt og/eller pepper-værdier?
  * Moderne standard hash-algiritmer såsom SHA-3, Bcrypt, PBKDF2 og Scrypt er designet til at gøre bruteforce angreb mere besværlige. Hvis de bruger standard MD5, så løb!
- Hvor besværligt er det at forøge hash'ens intensitet ved nye brugere? og ved eksisterende brugere?
  * Hackere udvikler hele tiden mere sofistikerede metoder og computeres ydeevne er konstant stigende. Vil deres system kunne tilpasses til at beskytte mod nye typer angreb?
- Er deres database direkte tilgængelig udenfor deres system?
  * Begrænsning af adgang til databasen, er første skridt i forsvaret imod exploits og angreb.
- Er forespørgsler indenfor systemet sikre? Hvor robust er din authentication for interne API kald?
  * Ved at bruge en variation af authentication credentials indeni systemet kan der tilføjes et yderligere lag af sikkerhed og begrænse hvad der kan udføres hvis en hacker opnår adgang.



