# Fast Forward Merge

## What is it?

The **easiest** type of merge. No conflicts, no extra commits.

It happens when **main hasn't changed** while you were working on your branch.
Git simply moves the main pointer forward to your latest commit.

Like a bookmark - main just slides forward to catch up.

---

## Visual

### Before merge

```
main: A ── B ── C
                      \
feature:               D ── E
```

main stopped at `C`. Feature added `D` and `E`.
Main has no new commits of its own.

### After fast-forward merge

```
main:      A ── B ── C ── D ── E
                                ↑
                              main (moved forward)
```

No merge commit created. History stays clean and straight.

## How to do it

```bash
git switch main
git merge feature-login
```

If fast-forward is possible, Git does it **automatically**.

Output looks like:
```
Updating c3d4e5f..a1b2c3d
Fast-forward
 login.html | 20 +++
```

---

## Force a merge commit (even if fast-forward is possible)

```bash
git merge --no-ff feature-login
```

> Use this when you want to keep a visible record that a branch existed.  
> Teams often use this rule so history is easier to read.

---

## Disable fast-forward globally (team setting)

```bash
git config --global merge.ff false
```

---

## When does fast-forward NOT happen?

When main got new commits while you were on your branch:

```
main:      A ── B ── C ── F   ← F is new on main
                      \
feature:               D ── E
```

Now Git has to do a real **merge commit** instead.  
See `merge-commit.md` for that.

---

## Quick Tip
Fast-forward is Git's way of saying:  
*"There's nothing to combine — I'll just move the pointer forward."*  
It's the cleanest outcome you can get from a merge.
