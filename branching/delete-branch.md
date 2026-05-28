# Delete a Branch

## When to delete a branch?

After your branch is **merged into main** and the work is done,  
the branch is no longer needed. Clean it up to keep things tidy.

```
main:     A --- B --- C --- D (merged!)
                       \   /
feature:                E--   ← safe to delete now
```

---

## Delete a merged branch (safe delete)

```bash
git branch -d feature-login
```

> Git will **refuse** to delete if the branch is not yet merged.  
> This protects you from losing unmerged work.

---

## Force delete (even if not merged)

```bash
git branch -D feature-login
```

> Use this only when you're sure you don't need the branch anymore.  
> ⚠️ Unmerged commits will be lost.

---

## Delete a remote branch (on GitHub)

```bash
git push origin --delete feature-login
```

---

## Check what's been merged (safe to delete)

```bash
git branch --merged
```

---

## Check what's NOT merged yet (be careful)

```bash
git branch --no-merged
```

---

## Full cleanup flow

```bash
git switch main                        # go to main first
git pull                               # get latest
git branch --merged                    # see what's done
git branch -d feature-login            # delete the merged one
git push origin --delete feature-login # remove from GitHub too
```

---

## Quick Tip
You **cannot** delete the branch you're currently on.  
Switch to `main` first, then delete.
