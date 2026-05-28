# Git Merging

## What is Merging? (Simple English)

You made a branch, did your work, and now you want to  
**bring it back into main**.

That's merging — combining two branches into one.

```
main:      A ── B ── C ─────────── M   ← merged!
                      \           /
feature:               D ── E ───
```

---

## Files in This Folder

| # | File | What you learn |
|---|------|----------------|
| 1 | `fast-forward.md` | The simplest type of merge |
| 2 | `merge-commit.md` | Regular merge with a commit |
| 3 | `squash-merge.md` | Combine all commits into one clean commit |
| 4 | `merge-conflicts.md` | Fix clashes when two branches changed the same thing |
| 5 | `abort-merge.md` | Cancel a merge that went wrong |
| 6 | `merge-vs-rebase.md` | Merge vs Rebase — what's the difference |

---

## Learning Order

```
1. fast-forward     → simplest merge, no conflicts
2. merge-commit     → normal everyday merge
3. squash-merge     → cleaner history trick
4. merge-conflicts  → the scary one — but easy once you see it
5. abort-merge      → escape when things go wrong
6. merge-vs-rebase  → understand the bigger picture
```

---

## Most Used Commands (Quick Glance)

```bash
git switch main               # always merge INTO main
git merge feature-login       # bring feature into main
git merge --no-ff feature-login   # force a merge commit
git merge --squash feature-login  # squash all commits into one
git merge --abort             # cancel a merge gone wrong
```

---

## Before You Start

Make sure you know these from `basics/` and `branching/` first:

- `add-commit.md`   → merging requires committed work
- `create-branch.md` → you need a branch to merge
- `switch-branch.md` → you switch to main before merging

---

## One Rule to Remember

> Always merge **into** the branch you want to update.  
> Switch to `main` first, then run `git merge`.

```bash
git switch main          ← you are here
git merge feature-login  ← pulling feature INTO main
```
