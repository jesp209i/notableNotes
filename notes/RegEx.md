---
title: RegEx
created: '2020-12-27T16:40:46.152Z'
modified: '2020-12-29T13:17:13.442Z'
---

# RegEx
- /abc/ finder første forekomst af "abc" i søgeteksten
- /abc/g finder alle forekomster af "abc" i søgeteksten
- /abc/i som første, men er ligeglad med case (case insensitive)
- /abc/m 

## Metakarakterer
Metakarakterer er specielle og bruges til at opbygge det mønster som regex skal finde i din søgetekst

| Meta | Beskrivelse |
|---|---|
| . (punktum) | Wildcard |
| \ (backslash) | Bruges til at escape den næste metakarakter - hvis man skal bruge karakteren som en "rigtig" karakter, ikke som metakarakter |
| - | Character Range, virker kun i firmatklammer. Eksempel: [0-9], [a-z] eller [A-Z]|
| [] | Definere et karaktersæt der skal matches på, en af karaktererne i klammerne matcher med en karakter i søgeteksten |
| ^ | Negate - må ikke matche de angivne karakterer i et sæt. Eksempel: [^1-9] |
| * | foregående tegn, nul eller flere gange |
| + | foregående tegn, en eller flere gange |
| ? | foregående tegn, nul eller en gang |
| {} | foregående tegn, gentaget {min, max} gange. eller kun {x} gange, eller fra {x,} til uendelig gange |
| ^ $ | start af streng/linje og slut på streng/linje  |
| \A \Z | Start af en streng, aldring slutningen af en linje, slut på en streng, aldrig slutningen af linjen |
| \| | alternation, match med udtrykket til højre eller til venstre for \|-tegnet |
| () |  gruppering af metakarakterer |
| \b \B | angiver en "wordboundary", angiver en "ikke-wordboundary" | 
| : ||
| ! ||
| = ||

## Karaktersæt shorthands
| Shorthand | Meaning | Equivalent |
|---|---|---|
| \d | ciffer | [0-9] |
| \w | Word character | [a-zA-Z0-9_] |
| \s | whitespace | [ \t\r\n] |
| \D | ikke ciffer | [^0-9] |
| \W | ikke Word character | [^a-zA-Z0-9_] |
| \S | ikke whitespace | [^ \t\r\n] |


## opgave
- hvor mange afsnit starter med I
  - /^I\b/ 4 matches
- hvor mange afsnit slutter med et spørgsmålstegn
  - /\?$/ 1 match
- match alle ord med 15 tegn, incl ord med bindestreg
  -  /\b[\w|-]{15}\b/gm 3 match














