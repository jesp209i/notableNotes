---
tags: [Store Systemer]
title: CI - del 2
created: '2020-12-04T08:29:16.682Z'
modified: '2020-12-04T09:02:06.345Z'
---

# CI - del 2
## GIT
__Opret aliaser__  
[Git alias](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases)


__Nice kommandoer__  
```
git log --oneline
git commit --amend
```

## GIT braching strategi
- Lås main branch
- "arbejd" på en develop-branch
- branchs ud til feature-branches - afspeljer en story
- develop-branchen udgives til en release branch
  - Release er den endelige version inden udgivelse til main-branch
- hotfixes - rettelse i master
  - fejl rettes, merges ind i main og develop, og måske release, hvis der kører et release.
