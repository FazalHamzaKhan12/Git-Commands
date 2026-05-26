# Git Add & Commit

## What it does
- `add` → stages file (marks them ready to save)
- 'commit' → save a snapshot(backup) of staged files 

---

## Stage a single file

```bash
git add filename.txt
```

---

## Stage all changed files

```bash
git add .
```

---

## Commit with a message

```bash
git commit -m "your message here"
```

---

## Stage + Commit Togather in one command

```bash
git commit -am "your message here"
```

> Only works for files already tracked by Git (not new files).

## How it flows

```
Working Directory  →  git add  →  Staging Area  →  git commit  →  Repository
   (your edits)                   (ready files)                  (saved snapshot)
```

---

## Quick Tips
- Write clear commit messages: `"Add login page"` not `"update"`  
- Commit often — small saves are easier to undo  
- Never commit broken code