---
title: Branches
teaching: 5
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- What are branches?

::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: questions

- Understand what branches are and when to use them

::::::::::::::::::::::::::::::::::::::::::::::::::

::: instructor
Using the slides, explain what branches are and when to use them.
You can choose to introduce the commands here, but we will practice with the git commands in the next episode as well.
:::

## What are branches and when to use them?
Have a look at 
[these slides introducing branches](https://esciencecenter-digital-skills.github.io/digital-skills-slides/modules/git-lesson/branches).


## Commands related to branches
Here are some commands related to branches that you often use in practice.

Create a new branch and switch onto it:
```commandline
git switch -c new-branch-name
```
```output
Switched to a new branch 'new-branch-name'
```

Switch to an existing branch, for example back to `main`:
```commandline
git switch main
```
```output
Switched to branch 'main'
```

Often while working on a branch, the main branch has changes that you want to apply to the branch you are working on.
You can do this by pulling changes from the main branch into the branch that you are working on:
```comandline
git switch branch-name # Make sure you are on the branch into which you want to pull changes from main
git pull origin main
```

:::::::::::::::::::::::::::::::::::::::: keypoints

- A branch represents an independent line of development.
- Subsequent changes are considered to belong to that branch.

::::::::::::::::::::::::::::::::::::::::::::::::::


