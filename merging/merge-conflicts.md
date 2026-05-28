# Merge Conflicts

## What is a Conflict?

A conflict happens when **two branches changed the same line**
in the same file - and Git doesn't know which version to keep.

Git stops and says: *"I can't decide - you choose."*

It's not an error. It's Git asking for your help.

---

## When does it happen?

```
main:     changed line 5 of login.html → "Submit"
feature:  changed line 5 of login.html → "Login Now"

Git: "Both changed the same line — which one is correct?"
```

---

## What a conflict looks like inside a file

Git edits your file and adds markers:

```
<<<<<<< HEAD
Submit
=======
Login Now
>>>>>>> feature-login
```

| Part | Meaning |
|------|---------|
| `<<<<<<< HEAD` | Start of YOUR current branch's version |
| `=======` | Divider between the two versions |
| `>>>>>>> feature-login` | End of the incoming branch's version |

---

## How to fix a conflict - step by step

**Step 1 — See which files have conflicts**
```bash
git status
```
Conflicted files show as `both modified`.

**Step 2 — Open the file and fix it**

Remove the markers and keep what you want:

```html
<!-- Before (conflicted) -->
<<<<<<< HEAD
Submit
=======
Login Now
>>>>>>> feature-login

<!-- After (your decision) -->
Login Now
```

You can also combine both if needed:
```html
Submit / Login Now
```

**Step 3 — Mark as resolved**
```bash
git add login.html
```

**Step 4 — Complete the merge**
```bash
git commit
```

Git auto-fills a merge commit message — save and close the editor.

---


## Full example

```bash
git switch main
git merge feature-login      # conflict happens here

# Fix the file manually in your editor

git add login.html           # mark as resolved
git commit                   # finish the merge
```

---

## Use VS Code to fix conflicts (easier)

VS Code shows conflicts with buttons:
- **Accept Current Change** → keep main's version
- **Accept Incoming Change** → keep feature's version
- **Accept Both Changes** → keep both
- **Compare Changes** → see them side by side

Just click — no need to delete markers manually.

---

## Abort if it gets too messy

```bash
git merge --abort
```

This cancels the merge completely and goes back to before you started.  
See `abort-merge.md` for more.

---

## Quick Tips
- Conflicts look scary but they're just a file edit
- Fix one file at a time
- Always run `git status` to track which files still need fixing
- When in doubt → `git merge --abort` and start fresh

