# Git Clone

## What it does
Downloads a copy of a remote repository to your computer.

---

## Clone a repo

```bash
git clone https://github.com/user/repo.git
```

> This creates a new folder with the project inside.

---

## Clone into a specific folder name

```bash
git clone https://github.com/user/repo.git my-folder
```

---

## Clone a specific branch only

```bash
git clone -b main https://github.com/user/repo.git
```

---

## Check after cloning

```bash
cd repo
git log --oneline
# Shows the commit history
```

---

## Quick Tip
After cloning, Git automatically sets `origin` as the remote name  
pointing to the URL you cloned from.
