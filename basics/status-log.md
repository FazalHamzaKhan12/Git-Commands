# Git Status & Log

## What they do
- `status` → shows what's changed right now
- `log`    → shows the history of commits

---

## See current status

```bash
git status
```

Output means:
- `Untracked`  → new file, Git doesn't know about it yet
- `Modified`   → file changed but not staged
- `Staged`     → ready to commit (green)

---

## See short status (cleaner output)

```bash
git status -s
```

---

## See full commit history

```bash
git log
```

---

## See compact history (one line each)

```bash
git log --oneline
```

---

## See history with a visual branch graph

```bash
git log --oneline --graph --all
```

---

## See changes in the last N commits

```bash
git log -3 --oneline
# Shows last 3 commits
```

---

## Quick Tip
Run `git status` before and after every command while learning.  
It helps you understand exactly what Git is doing.