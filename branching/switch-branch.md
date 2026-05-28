# Swtich Branch

## What does switching mean?

Your files on screen **actually change** when you switch branches.
Git swaps out the files to match whichever branch you move to.

```
You are on: main         →   git switch feature-login   →   Now on: feature-login
(sees main's files)                                          (sees feature's files)
```

Don't worry — nothing is deleted. Git saves everything.

---

## Swtich to an existing branch

```bash
git switch feature-login
```

---

## Old way (still works)

```bash
git checkout feature-login
```

---

## Check which branch you're on 

```bash
git branch
```

> The branch with `*` in front is your current one.

---

## Switch back to main

```bash
git switch main
```

---

## Warning - Unsaved Changes

If you changed files but didn't commit, Git may **block** the switch:

```
error: your local changes would be overwritten by checkout.
```

**Fix — Option 1:** Commit your changes first
```bash
git add .
git commit -m "save work in progress"
git switch main
```

**Fix — Option 2:** Stash your changes temporarily
```bash
git stash
git switch main
# come back later: git stash pop
```

---

## Quick Tip
Always know which branch you're on before making changes.  
Run `git branch` or check your terminal — most terminals show the branch name.
#