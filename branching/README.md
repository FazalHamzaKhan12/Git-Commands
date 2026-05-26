# Git Branching

## What is a Branch? (Simple English)

Imagine you're writing an essay on your computer.  
Before trying something risky, you make a **copy of the file** — so the original is safe.

That's exactly what a branch is.

```
main branch      →  your safe, working project
feature branch   →  your copy to try new things
```

If your experiment works → merge it back into main.  
If it fails → just delete the branch. Main is untouched.

---

## The Big Picture

```
main:       A ──── B ──── C ─────────── F   (always working)
                           \           /
feature-login:              D ──── E        (your experiment)
```

- `A B C` = original commits on main
- `D E`   = your new work on the branch
- `F`     = merged back — work is done!

---

## Files in This Folder

| # | File | What you learn |
|---|------|----------------|
| 1 | `create-branch.md` | Make a new branch |
| 2 | `switch-branch.md` | Move between branches |
| 3 | `rename-branch.md` | Fix a branch name |
| 4 | `push-branch.md` | Share your branch to GitHub |
| 5 | `delete-branch.md` | Clean up finished branches |

---

## Learning Order

```
1. create-branch   → make your first branch
2. switch-branch   → learn to move between branches
3. push-branch     → put your branch on GitHub
4. rename-branch   → fix mistakes in naming
5. delete-branch   → clean up when done
```

---

## Most Used Commands (Quick Glance)

```bash
git switch -c feature-login     # create + switch in one step
git switch main                 # go back to main
git branch                      # see all branches
git push -u origin feature-login # push branch to GitHub
git branch -d feature-login     # delete after merging
```

---

## Before You Start

Make sure you know these from `basics/` first:

- `add-commit.md` → you need to commit before switching branches
- `status-log.md` → always check which branch you're on
- `push-pull.md`  → needed for `push-branch.md`

---

> One branch = one task. Keep it focused and your project stays clean.
