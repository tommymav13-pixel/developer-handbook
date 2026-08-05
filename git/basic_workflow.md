# Basic Git Workflow

This document describes the Git workflow I use for most software projects.

The goal is to create a consistent and reliable development process.

---

# Standard Workflow

## 1. Check the repository status

```powershell
git status
```

Review modified, new and deleted files.

---

## 2. Review changes

```powershell
git diff
```

Inspect changes before staging.

---

## 3. Stage changes

Stage all changes:

```powershell
git add .
```

Or stage individual files:

```powershell
git add README.md
```

---

## 4. Create a commit

```powershell
git commit -m "Add Git workflow documentation"
```

Use a clear, descriptive commit message.

---

## 5. Push changes

```powershell
git push
```

Upload commits to GitHub.

---

# Starting an Existing Repository

Clone the repository:

```powershell
git clone <repository-url>
```

Move into the project:

```powershell
cd repository-name
```

Download the latest changes:

```powershell
git pull
```

---

# Useful Commands

| Command | Purpose |
|---------|---------|
| `git status` | Check repository status |
| `git diff` | Review changes |
| `git add` | Stage files |
| `git commit` | Create a commit |
| `git push` | Upload commits |
| `git pull` | Download remote changes |
| `git clone` | Clone an existing repository |
| `git fetch` | Download remote changes without merging |
| `git stash` | Temporarily save uncommitted work |

---

# Best Practices

- Check `git status` frequently.
- Review changes with `git diff`.
- Create small, focused commits.
- Write meaningful commit messages.
- Push changes regularly.

---

# Current Workflow

My typical workflow is:

```text
git status
      ↓
git diff
      ↓
git add
      ↓
git commit
      ↓
git push
```