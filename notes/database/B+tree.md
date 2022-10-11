---
tags: [Database, index]
title: B+tree
created: '2020-09-26T08:52:48.202Z'
modified: '2020-12-05T08:27:30.229Z'
---

# B+tree

Big O = Algoritmic effeciency
- Different steps get added
  - O(a+b)
- Drop Constants
  - O(2n) => O(n)
- Different inputs => different variables
  - O(a*b)
- drop non-dominate terms
  - O(n^2) <= O(n+n^2) 

Indeksering
- Mange rækker er gemt i databasen
- Mange forespørgsler tilgår kun en lille del af rækkerne
- Skal kunne ændre på rækkerne: insert, update og delete
- Kan ikke tage databasen offline for at reorganisere filerne databasen består af

=> Mål: tilgå så lidt data som muligt


## To typer af indeksering:
- clustered (standard i mssql)
  - direkte adgang til data
  - Best practice er at bruge kolonner hvor WHERE clause og JOINS indgår i queries
  - Der kan kun være et clustered index i en tabel
- non clustered
  - Pointers til data
  - Laver tabeller i baggrunden, som indeholder den type sortering man vil opnå med indexet.
  - tabellen peger på de relevante rækker i den rigtige tabel

Index-navngivning: `IX_[tabel]_[kolonne]`

## Sparse index
 - clustered index
## Dense index






b-tree (n)
n er antallet af pointers per node









