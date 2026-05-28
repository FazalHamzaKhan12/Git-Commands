# Merge vs Rebase

## The Simple Idea

Both do the **same job** - bring changes from one branch into another.
But they do it in **completely different ways**.

---

## Real Life Analogy

> You and your friend are both editing the same Google Doc separately.

**Merge** = you combine both versions and write a note:
*"combined both edits on Monday"*

**Rebase** = you take your edits and pretend you wrote them
**after** your friend finished - clean, no combination note.

---

## Visual — What Actually Happens

### Situation (starting point)

```
main:          A ── B ── C
                          \
feature:                   D ── E
```

---

### After git merge

```
main:    A ── B ── C ────────── M   ← M = merge commit (extra commit)
                    \          /
feature:             D ── E ──
```

- Keeps full history of both branches
- Adds an extra **merge commit** `M`
- History looks like a river splitting and joining

---

### After git rebase

```
main:    A ── B ── C ── D' ── E'    ← D and E are replayed on top of C
```

- No merge commit
- Looks like the work was always done in one straight line
- History is **clean and linear**

---

## Side by Side Comparison

| | Merge | Rebase |
|---|---|---|
| History | Full — shows every branch | Clean — straight line |
| Merge commit | Yes — adds one | No |
| Safe for shared branches | ✅ Yes | ⚠️ Risky |
| Good for | Team branches, pull requests | Personal/local cleanup |
| Keeps original commits | ✅ Yes | ❌ Rewrites them |

---

## How to Merge

```bash
git switch main
git merge feature-login
```

Git combines the branches and creates a merge commit.

---

## How to Rebase

```bash
git switch feature-login
git rebase main
```

Git takes your commits and replays them on top of main.

---

## The Golden Rule of Rebase

> ⚠️ Never rebase a branch that others are also using.

Rebase **rewrites commit history**.  
If someone else has a copy of your branch, their history and yours will conflict badly.

**Safe to rebase:** your own local branch, not pushed yet  
**Never rebase:** `main`, `develop`, or any shared branch

---

## When to Use Which

Use **merge** when:
- Working with a team
- Opening a pull request on GitHub
- You want to preserve the full history

Use **rebase** when:
- Cleaning up your own local commits before pushing
- You want a straight, readable history
- Working alone on a feature branch

---

## Beginner Advice

Start with **merge** — it's safe and simple.  
Learn rebase once you're comfortable with branching and merging.

```
Beginner  →  use merge always
Intermediate  →  use rebase for local cleanup only
```

---

## Quick Glance

```bash
# Merge (safe, keeps history)
git switch main
git merge feature-login

# Rebase (clean, rewrites history)
git switch feature-login
git rebase main
```
