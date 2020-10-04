---
tags: [Database]
title: Relationel Algebra
created: '2020-10-03T14:24:16.266Z'
modified: '2020-10-03T18:01:19.726Z'
---

# Relationel Algebra
## Mængdeoperationer
### Union
$R \bigcup S$ (Foreningsmængden)
- Relation med tupler fra R og S med evt. duplicater fjernet

Bemærk iøvrigt at relationen er kommutativ:
- $R \bigcup S =S \bigcup  R$

### Difference
$R - S$ (Mængdedifferensen)
- Relation med tupler fra R men ikke fra S

Operationen er __ikke__ kommutativ fordi:
- $R - S \neg= S-R$

### Intersection
R $\bigcap$ S (Fællesmængden)
- Relation med tupler som findes både i R og S

Bemærk iøvrigt at relationen er kommutativ:
- $R \bigcap S = S \bigcap R$

### Kartesisk Produkt
R $\times$ S
- Skaber en relation der indeholder alle kombinationer af tupler fra to relationer

## Relationelle operationer
Selektion og Projektion kan bruges i kombination.

### Selektion
Udvælg en selektion (et udsnit) af en relation (en tabel)
* $\sigma_{betingelse(r)}(R)$

__Sammenligningsoperatorer:__
| Lig med | Mindre end | Større end | Mindre end eller lig med | Større end eller lig med | Forskellig fra |
|---|---|---|---|---|---|
| = | < | > | $\le$ | $\ge$ | $\not=$|

__Logiske operatorer:__
| Og | Eller | Ikke |
|---|---|---|
| $\wedge$ | $\vee$ | $\neg$ |

### Projektion
Udvælger bestemte attributter (kolonner) fra en relation (tabel)
* $\Pi_{attributliste}(R)$

## Aggregatfunktioner
Aggregatfunktioner er operationer, der opererer på en af relationens attributter vertikalt gennem dens tupler:
- SUM
- MINIMUM (MIN)
- MAXIMUM (MAX)
- AVERAGE, MEAN, MEDIAN (AVG, MEAN, MED)
- COUNT
* $ℑ{funktionsnavn}(R)$

## Join-operationer

- Generisk Join
  - sammenføjer to relationer til en. Join-operationens argumenter er attributnavn fra begge relationer.
  * $R \Join S$

| Relation1 | Operator | Kondition | Relation2 |
|---|---|---|---|
|ANSAT | $\Join$ | Navn = Navn | PRIVAT |

- Natural Join
  - Som Generisk join, men her er duplikate attributter fjernet.
  * $R ∗ S$

| Relation1 | Operator | Relation2 |
|---|---|---|
|ANSAT | $\Join$ | PRIVAT |

- Outer Join
  - Left Outer Join
    - Medtager alle tupler fra venstre relation, men kun de tupler fra højre relation som opfylder sammenfalds-konditionen med venstre
    * $\sqsupset\Join$

| Relation1 | Operator | Relation2 |
|---|---|---|
|ANSAT | $\sqsupset\Join$ | PRIVAT |

  - Right Outer Join
    - Medtager alle tupler fra højre relation, men kun de tupler fra venstre relation som opfylder sammenfalds-konditionen med højre
    * $\Join\sqsubset$

| Relation1 | Operator | Relation2 |
|---|---|---|
|ANSAT | $\Join\sqsubset$ | PRIVAT |

  - Full Outer Join
    - Medtager alle tupler fra begge relationer, uanset om de opfylder sammenfalds-konditionen med hinanden
    * $\sqsupset\Join\sqsubset$

| Relation1 | Operator | Relation2 |
|---|---|---|
|ANSAT | $\sqsupset\Join\sqsubset$ | PRIVAT |

- Outer Union
```
Forklaring mangler
```
  * $R \bigcup* S$


