# Abort a Merge

## What does it do?

Something went wrong during a merge - too many conflicts,
wrong branch, or you just changed your mind.

`git merge --abort` = **undo the merge completely**
and go back to exactly how things were before you started.

Like pressing **Cancel** on the whole merge

---

## How to abort

```bash
git merge --abort
```

That's it. Git restores everything.

---

## When can you use it? 

Only while a merge is **in progress** (not finished yet).
If conflicts appeared and you haven't committed yet → you can abort.

```bash
git merge feature-login    # conflict happens, Git pauses
# you decide to cancel
git merge --abort          # back to normal, nothing changed
```

---

## How to check if a merge is in progress

```bash
git status
```

If you see this → a merge is in progress:
```
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)
```

If you see normal output → no merge in progress, abort won't work.

---

## What abort does NOT do

❌ It does NOT undo a merge that was **already committed**  
❌ It does NOT work after `git commit`

If you already committed the merge and want to undo it → use `git revert` or `git reset`.  
See `undo/` folder for that.

---

## Alternative — start fresh on conflicts

Sometimes it's easier to:

```bash
git merge --abort          # cancel merge
git switch feature-login   # go back to your branch
# fix things on the branch first
git switch main
git merge feature-login    # try merging again
```

---

## Quick Tip
If conflicts feel overwhelming → just abort.  
Take a breath, understand the two branches, then try again.  
Aborting is always safe — nothing is lost.
