# Git Init

## What it does
Turns a normal folder into a Git repository (starts tracking your files)

## Initialize a new repo

```bash
git init
```

> Run this inside you project folder. where you want to create the Git Repo

---

## Initialize with a name (creates a new folder)

```bash
git init my-project
```

---

## Check it worked

```bash
ls -a
# its command for checking the hiddens files inside your folder
# You should see a hidden .git folder
```

---

## Quick Tip
You only run `git init` **once** per project.
If you're copying someone else's project, use `git clone` instead.