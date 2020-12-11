---
tags: [Database, Eksamen]
title: DB Exam Question 1 wip
created: '2020-11-24T09:21:32.106Z'
modified: '2020-12-05T19:06:50.887Z'
---

# DB Exam Question 1 wip
```
Explain how ER diagrams are used in data modelling and planning of your database. How does data modelling relate to normal forms?  
What are constraints and keys used for?
```
- Forklar ER-diagrammets dele
- attributter + datatyper + null vs not nulls
- constraints + keys


en db er en samling af relateret information som er organiseret så man nemt kan:
- tilgå data
- håndtere data
- opdatere data


typer af relationer mellem tabeller
- 1:1
- 1:m
- n:m

Et Makerspace har en adresse
Et Makerspace kan være del af en Organisation
En organisation har en adresse
et makerspace og en organisation _`kan dele`_ eller _`have hver sin`_ adresse


flow:
- konceptionel del => requirement analysis
  - beskrivelser af relationer og constraints
- logisk model => data modellering
  - entiteter
  - attributter
  - relationer mellem entiteter
- fysisk model (incl typer og eksempelvis "not null"-constraints)

ER-diagram kan hjælpe med at skabe queries

Constraints:
- Key
  - Primary skal være unik
  - Foreign ska
- Domain
  - not null
  - unique
  - størrelse på kolonner
- Referensial
