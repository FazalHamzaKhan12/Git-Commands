# Squash Merge

## What is it?

You worked on a feature and made 10 messy commits like:

```
"wip"
"fix typo"
"trying again"
"ok this works maybe"
"final fix for real"
```

Squash merge takes **all those commits** and squashes them into
**one Single clean commit** on main.

Main sees neat history. Nobody sees your messy in-between saves.

---

## Visual

### Before squash merge

```
main:      A ── B ── C
                      \
feature:               D ── E ── F ── G   (4 messy commits)
```

### After squash merge

```
main:      A ── B ── C ── S    ← S = one clean commit with all changes
```

`D E F G` never appear in main's history. Clean!

---

## How to do it

```bash
git switch main
git merge --squash feature-login
git commit -m "Add login feature"
```

> `--squash` stages all the changes but doesn't commit yet.  
> You write one clean commit message yourself.


## Step by step clearly

```bash
# 1. Go to main
git switch main

# 2. Squash all feature commits into staging area
git merge --squash feature-login

# 3. Commit with a clean message
git commit -m "Add login feature"

# 4. Delete the feature branch (it's not auto-merged)
git branch -D feature-login
```

> ⚠️ Use `-D` (force delete) because squash doesn't create a real merge,  
> so Git thinks the branch is "unmerged".

---

## Regular merge vs Squash merge

```
Regular merge:
main → A ── B ── C ── D ── E ── F ── G ── M   (all commits visible)

Squash merge:
main → A ── B ── C ── S                        (one clean commit)
```

---

## When to use squash

✅ Your branch has messy WIP(work in progress) commits  
✅ You want main history to stay readable  
✅ Small features or bug fixes  

❌ Don't squash when commit history on the branch is important to keep  
❌ Don't squash shared branches others depend on

---

## Quick Tip
Write a **good squash commit message** — it's the only record of the work.  
Example: `"Add user login with email and password validation"`  
Not just: `"login stuff"`
