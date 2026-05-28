# Rename a Branch

## Why renmae a branch?

You made a typo, or the branch name no longer fits the work.
Renaming keeps your repo clean and readable.

---

## Rename your CURRENT branch

```bash
git branch -m new-name
```

Example - you're on `featre=login` (typo), fix it:
```bash
git branch -m feature-login
```

---

## Rename a Different Branch (without switching to it)

```bash
git branch -m old-name new-name
```

---

## If the branch is on Github too

After renmaing locally, update Github:

```bash
# 1. Push the renamed branch to GitHub
git push origin new-name

# 2. Delete the old branch name from GitHub
git push origin --delete old-name

# 3. Update your local tracking link
git branch -u origin/new-name new-name
```

---

## Renaming main → (special case)

```bash
git branch -m master main          # rename locally
git push origin main               # push new name
git push origin --delete master    # remove old name
```

---

## Quick Tip
If others are using the same branch, tell them before renaming.  
They'll need to update their local copy too.
