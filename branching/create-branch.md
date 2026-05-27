# Create a Branch

## What is a Branch?

Think of your project like a **book**.
The `main` branch is the **original copy**.

When you create a branch → you make a **side copy** to write new stuff.
If it goes wrong → the original is **safe**.
If it goes well → you can **merge it back** into the original.

```
main:     A --- B --- C
                       \
new-branch:             D --- E
```

---

## Create a branch

```bash
git branch feature-login
```

> Juust creates it. You're still on your current branch.

---

## Create & swtich to it immediately

```bash
git status -c feature-login
```

> `-c` means "create". This is the modern way — use this one.

---

## Old way (still work)

```bash
git chekcout -b feature-login
```

---

## See all branches

```bash
git branch
```

---

## See all branches including remote

```bash
git branch -a
```

---

## Quick Tips
- Name branches clearly: `feature-login`, `fix-navbar`, `update-readme`  
- One branch = one task. Don't mix two things in one branch  
- `main` should always have working code — do your work in branches
