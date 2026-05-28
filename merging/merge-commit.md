# Merge Commit

## What is it?

A **regular merge** — used when both branches have new commits.  
Git combines the two branches and creates a special **merge commit** to record it.

Think of it like two roads joining into one.  
The merge commit is the **junction point**.

---

## Visual

### Before merge

```
main:      A ── B ── C ── F        ← F is new on main
                      \
feature:               D ── E     ← D and E are your work
```
Both branches moved forward. Git can't just slide the pointer.  
It needs to **combine** them.

### After merge commit

```
main:      A ── B ── C ── F ── M   ← M is the merge commit
                      \       /
feature:               D ── E
```

`M` has **two parents** — `F` from main and `E` from feature.

---

## How to do it

```bash
git switch main          # step 1 — go to main
git merge feature-login  # step 2 — merge feature into main
```

Git opens your editor to write a merge commit message.
Default message is fine - just save and close.

---

## Skip the editor (use default message)

```bash
git merge feature-login --no-edit
```

---

## Force a merge commit (even on fast-forward cases)

```bash
git merge --no-ff feature-login
```

> Good for teams — makes it clear a feature branch was used.

---

## See the merge in history

```bash
git log --oneline --graph
```

Output:
```
*   a1b2c3d Merge branch 'feature-login'
|\
| * e4f5g6h add login form
| * d7e8f9g add login route
* | c1d2e3f update homepage
|/
* b4c5d6e initial commit
```

The `|\` shape is the branch splitting and merging.

---

## After merging — clean up

```bash
git branch -d feature-login          # delete local branch
git push origin --delete feature-login  # delete from GitHub
```

---

## Quick Tip
A merge commit is not a bad thing.  
It tells the full honest story of your project history.  
Use `--no-ff` in teams so every feature merge is clearly visible.
