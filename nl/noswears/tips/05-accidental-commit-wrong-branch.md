---
tags: tip
title: Oeps, ik heb op de verkeerde branch gecommit!
id: accidental-commit-wrong-branch
order: 5
---

```git
# rol de laatste commit terug, maar behoud de wijzigingen.
git reset HEAD~ --soft
git stash
# Ga naar de juiste branch
git checkout name-of-the-correct-branch
git stash pop
git add . # or add individual files
git commit -m "your message here"
# Nu zitten je wijzigingen in de juiste branch
```

Een boel mensen hebben voorgesteld om `cherry-pick` te gebruiken in deze situatie. Ook een goede mogelijkheid, dus kies wat in jouw situatie de beste oplossing is!


```git
git checkout name-of-the-correct-branch
# pak de laatste commit op master
git cherry-pick master
# verwijder het uit master
git checkout master
git reset HEAD~ --hard
```
