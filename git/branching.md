# Git Branching

This document describes the branching workflow I use in Git projects.

Branches make it possible to develop changes separately from the stable
version of a project.

---

## Purpose

Branches are useful for:

- Developing new features.
- Fixing bugs.
- Testing changes safely.
- Keeping `main` stable.
- Separating unrelated work.

---

## Main Branch

The default branch is:

```text
main
```

The `main` branch should contain the stable and current version of the
project.

For small learning exercises, I may work directly on `main`.

For larger or riskier changes, I use a separate branch.

---

## When to Create a Branch

Create a new branch when:

- Adding a meaningful feature.
- Refactoring multiple files.
- Experimenting with an approach.
- Fixing a bug that requires several changes.
- Working on documentation separately.
- Changing repository structure.

A separate branch is usually unnecessary for:

- Correcting a small spelling error.
- Updating one short sentence.
- Making a simple and low-risk change.

---

## Branch Naming Convention

Use lowercase **kebab-case**.

Examples:

```text
feature/add-project-index
feature/create-login-page
fix/broken-readme-link
docs/update-git-workflow
refactor/reorganize-directories
```

Recommended prefixes:

| Prefix | Purpose |
|--------|---------|
| `feature/` | Add new functionality |
| `fix/` | Correct a bug or error |
| `docs/` | Change documentation |
| `refactor/` | Improve structure without changing behaviour |
| `test/` | Add or update tests |
| `chore/` | Perform maintenance or configuration work |

---

## View Branches

Show local branches:

```powershell
git branch
```

Show local and remote branches:

```powershell
git branch -a
```

The current branch is marked with an asterisk.

---

## Create and Switch to a Branch

Preferred command:

```powershell
git switch -c <branch-name>
```

Example:

```powershell
git switch -c docs/update-branching-guide
```

This command:

1. Creates the branch.
2. Switches to the new branch.

---

## Switch Between Branches

Switch to an existing branch:

```powershell
git switch <branch-name>
```

Example:

```powershell
git switch main
```

Before switching, check the repository status:

```powershell
git status
```

Commit or stash unfinished work when necessary.

---

## Development Workflow

A typical branch workflow is:

```text
Update main
    ↓
Create branch
    ↓
Make changes
    ↓
Review and test
    ↓
Commit changes
    ↓
Push branch
    ↓
Merge into main
    ↓
Delete branch
```

---

## Step-by-Step Workflow

### 1. Switch to main

```powershell
git switch main
```

### 2. Download the latest changes

```powershell
git pull
```

### 3. Create a new branch

```powershell
git switch -c docs/update-branching-guide
```

### 4. Make and review changes

```powershell
git status
git diff
```

### 5. Stage the changes

```powershell
git add branching.md
```

### 6. Commit the changes

```powershell
git commit -m "Update Git branching guide"
```

### 7. Push the branch

For the first push:

```powershell
git push -u origin docs/update-branching-guide
```

After the upstream branch has been configured:

```powershell
git push
```

### 8. Merge the branch

Switch to `main`:

```powershell
git switch main
```

Update `main`:

```powershell
git pull
```

Merge the branch:

```powershell
git merge docs/update-branching-guide
```

Push the updated `main` branch:

```powershell
git push
```

---

## Delete a Merged Branch

Delete the local branch:

```powershell
git branch -d docs/update-branching-guide
```

Delete the remote branch when appropriate:

```powershell
git push origin --delete docs/update-branching-guide
```

Use the lowercase `-d` option for branches that have already been merged.

---

## Uncommitted Changes

Git may prevent branch switching when local changes would be overwritten.

Options:

### Commit the work

```powershell
git add .
git commit -m "Save current work"
```

### Temporarily store the work

```powershell
git stash
```

Switch branches:

```powershell
git switch main
```

Restore the saved work later:

```powershell
git stash pop
```

---

## Branches in Learning Projects

For small Python Crash Course exercises, working directly on `main` is
acceptable because:

- The changes are small.
- The repository is personal.
- The risk is limited.
- The workflow remains simple.

I still use branches when a change involves:

- Several files.
- Repository restructuring.
- Significant documentation updates.
- New standalone projects.
- Experimental code.

---

## Best Practices

- Start new branches from an updated `main`.
- Use one branch for one logical purpose.
- Use descriptive branch names.
- Keep branches short-lived.
- Commit completed units of work.
- Test changes before merging.
- Delete branches after a successful merge.
- Avoid combining unrelated changes in one branch.

---

## Current Convention

My current branching convention is:

- Use `main` for stable work.
- Work directly on `main` for small, low-risk learning exercises.
- Use short-lived branches for substantial changes.
- Name branches with a descriptive prefix and kebab-case.
- Merge completed and tested branches into `main`.
- Delete branches after confirming the merge.