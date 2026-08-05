# Git Commands

This document contains a practical reference for commonly used Git commands.

---

## Repository Information

### Check repository status

```powershell
git status
```

Shows:

- Current branch.
- Modified files.
- Staged files.
- Untracked files.

### View configured remotes

```powershell
git remote -v
```

### View commit history

```powershell
git log
```

Compact version:

```powershell
git log --oneline
```

---

## Starting a Repository

### Initialize a local repository

```powershell
git init
```

### Clone an existing repository

```powershell
git clone <repository-url>
```

### Connect a local repository to GitHub

```powershell
git remote add origin <repository-url>
```

### Rename the current branch to main

```powershell
git branch -M main
```

---

## Reviewing Changes

### Show unstaged changes

```powershell
git diff
```

### Show staged changes

```powershell
git diff --staged
```

### Show changes in a specific file

```powershell
git diff <file>
```

---

## Staging Changes

### Stage one file

```powershell
git add <file>
```

Example:

```powershell
git add README.md
```

### Stage all changes

```powershell
git add .
```

### Stage deleted files and modifications

```powershell
git add -u
```

---

## Committing

### Create a commit

```powershell
git commit -m "Add Git command reference"
```

### Commit tracked changes directly

```powershell
git commit -am "Update documentation"
```

This does not include new, untracked files.

---

## Synchronizing

### Push commits

```powershell
git push
```

### First push with upstream branch

```powershell
git push -u origin main
```

### Pull remote changes

```powershell
git pull
```

### Download remote information without merging

```powershell
git fetch
```

---

## Branches

### List local branches

```powershell
git branch
```

### Create a branch

```powershell
git branch <branch-name>
```

### Switch branches

```powershell
git switch <branch-name>
```

### Create and switch to a branch

```powershell
git switch -c <branch-name>
```

### Delete a merged branch

```powershell
git branch -d <branch-name>
```

### Force-delete a branch

```powershell
git branch -D <branch-name>
```

Use force deletion carefully.

---

## Merging

### Switch to the destination branch

```powershell
git switch main
```

### Merge another branch

```powershell
git merge <branch-name>
```

---

## Undoing Changes

### Discard unstaged changes in one file

```powershell
git restore <file>
```

### Unstage a file

```powershell
git restore --staged <file>
```

### Restore all unstaged changes

```powershell
git restore .
```

Use restore commands carefully because local work may be lost.

---

## Stashing

### Temporarily store changes

```powershell
git stash
```

### List stashes

```powershell
git stash list
```

### Reapply the latest stash

```powershell
git stash pop
```

### Apply without deleting the stash

```powershell
git stash apply
```

---

## File Movement

When possible, use Git-aware commands.

### Rename or move a file

```powershell
git mv old_name.md new_name.md
```

### Remove a tracked file

```powershell
git rm <file>
```

Git can also detect renames after regular PowerShell file operations once the
changes are staged.

---

## Common Workflow

```powershell
git status
git diff
git add .
git diff --staged
git commit -m "Describe the change"
git push
```

---

## Current Convention

I prefer:

- Reviewing changes before staging.
- Creating small, focused commits.
- Using meaningful imperative commit messages.
- Checking `git status` frequently.