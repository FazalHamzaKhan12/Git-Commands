# Git Config

## What it does
Sets your identity and preferences for Git on your machine.

----

## Set your name

```bash
git config --global user.name "Your Name"
```

## Example:

```bash
git config --global user.name "Fazal Hamza Khan"
```

## Set your email

```bash
git config --global user.email "you@example.com"
```

## Example:

```bash
git config --global user.name "theunknown.pak@gmail.com"
```

## Set default branch name to main

```bash
git config --global init.defaultBranch main
```

## Set VS Code as default editor

```bash
git config --global coreeditor "code --wait"
```

## View all your settings

```bash
git config --list
```

## View a specific setting

```bash
git config user.name
```

## Where config is saved
| Flag       | Scope         | File location              |
|------------|---------------|----------------------------|
| `--global` | Your user      | `~/.gitconfig`             |
| `--local`  | Current repo   | `.git/config`              |
| `--system` | All users      | `/etc/gitconfig`           |


## Quick Tip
Run the name + email setup **once** after installing Git.  
Git attaches your name/email to every commit you make.
