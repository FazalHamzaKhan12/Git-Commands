# Push Branch to Remote

## What does this mean?

When you create a branch locally, it only exists **on your computer**.  
To share it on GitHub (or work on another machine), you need to push it.

```
Your Computer          GitHub
─────────────          ──────
feature-login    →     feature-login  (after push)
```

---

## Push a local branch to GitHub

```bash
git push origin feature-login
```

---

## Push AND set upstream (recommended)

```bash
git push -u origin feature-login
```

> `-u` links your local branch to the remote one.  
> After this, you can just type `git push` or `git pull` — no extras needed.

---

## Check if your branch is linked to remote

```bash
git branch -vv
```

Output:
```
* feature-login  a3b2c1d [origin/feature-login] add login form
  main           f1e2d3c [origin/main] initial commit
```

The part in `[ ]` shows the remote link.

---

## Pull a branch someone else pushed

```bash
git fetch origin
git switch feature-login
```

> `fetch` downloads the info, `switch` moves you onto it.

---

## Quick Tip
Always use `git push -u origin branch-name` the **first time** you push a branch.  
After that, plain `git push` is enough.
