# Git Push & Pull

## What they do
- `push` → uploads your commits to remote (GitHub etc.)
- `pull` → downloads + merges latest changes from remote

---

## Push to remote

```bash
git push origin main
```

> `origin` = remote name | `main` = branch name

---

## Push for the first time (set upstream)

```bash
git push -u origin main
```

> After this, you can just type `git push` next time.

---

## Pull latest changes

```bash
git pull origin main
```

---

## Pull (short version after upstream is set)

```bash
git pull
```

---

## How it flows

```
Your Computer                        GitHub (Remote)
─────────────                        ───────────────
  git push   ──────────────────────>   saves your commits
  git pull   <──────────────────────   gets their commits
```

---

## Quick Tips
- Always `git pull` before you start working to avoid conflicts  
- Always `git pull` before `git push` if others use the same repo  
- If push is rejected → pull first, fix conflicts, then push

