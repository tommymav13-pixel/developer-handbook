# Daily Development Workflow

This document describes the standard workflow used when working on development
projects and repositories.

## Purpose

The workflow is designed to:

* make terminal usage part of daily development;
* use Git consistently during programming sessions;
* verify repository state before making changes;
* keep local and remote repositories synchronized;
* create focused and understandable commits;
* develop a repeatable development routine.

---

## Start a Development Session

Open PowerShell and navigate to the relevant repository.

Verify the current location:

```powershell id="d1w8hc"
Get-Location
```

Inspect the directory if necessary:

```powershell id="f7m2kp"
dir
```

Then check the Git repository:

```powershell id="v9q4sb"
git status
```

---

## PowerShell Navigation Functions

PowerShell functions are used to quickly navigate to frequently used
repositories and directories.

Current functions include:

```text id="y5n3wr"
pcc          Python Crash Course repository
handbook     Developer Handbook repository
portfolio    Developer Portfolio repository
books        Books directory
```

Example usage:

```powershell id="r8x1md"
handbook
```

Repository navigation functions can also immediately run:

```powershell id="k2c7vn"
git status
```

This provides immediate feedback about the current repository state.

---

## Open a Repository

Example:

```powershell id="z4b9fq"
pcc
git status
code .
```

Or:

```powershell id="h6s2jy"
handbook
git status
code .
```

If the repository may contain remote changes, synchronize before starting new
work.

For example:

```powershell id="t3p8lx"
git pull
```

Before pulling, make sure that local uncommitted changes will not interfere
with synchronization.

---

## Create Files and Directories

Create a directory when needed:

```powershell id="a7v4gc"
New-Item -ItemType Directory -Path <directory-name>
```

Create a file:

```powershell id="m1q6dk"
New-Item -ItemType File -Path <filename>
```

For example:

```powershell id="w9f3bz"
New-Item -ItemType File -Path exercise.py
```

Verify the result:

```powershell id="c5r8np"
dir
```

---

## Open the Project

Open the current directory in VS Code:

```powershell id="g2k7mv"
code .
```

Or open a specific file:

```powershell id="p4x9hs"
code exercise.py
```

---

## During Development

Follow a short development cycle:

```text id="n8d1qt"
Edit
  ↓
Save
  ↓
Run or test
  ↓
Inspect
  ↓
Edit again
```

Regularly inspect the repository:

```powershell id="u6j3fw"
git status
```

View unstaged changes:

```powershell id="e9m5kc"
git diff
```

This makes it easier to understand exactly what has changed before creating a
commit.

---

## Stage Changes

Stage specific files when possible:

```powershell id="b3v7rx"
git add <filename>
```

Example:

```powershell id="q1h8zn"
git add README.md
```

Stage a directory:

```powershell id="s5k2dp"
git add python
```

To intentionally stage all changes:

```powershell id="l7c4wg"
git add .
```

Use `git add .` only when all current changes belong to the intended commit.

---

## Verify the Staging Area

Check which files are staged:

```powershell id="f2n9yb"
git status
```

Inspect the actual staged changes:

```powershell id="x8r3mh"
git diff --staged
```

This is the final review before creating a commit.

### Important

`git add` stages the current version of a file.

If the file is modified again after running `git add`, the new changes are not
automatically staged.

Run `git add` again to update the staged version:

```powershell id="j4w6qs"
git add <filename>
```

---

## Commit Changes

Create a commit with a concise description of the change:

```powershell id="v1p7dt"
git commit -m "Describe the change"
```

Prefer commit messages that describe what the commit accomplishes.

Example:

```powershell id="k9g2fc"
git commit -m "Update Python documentation"
```

---

## Push to GitHub

Push the commit to the remote repository:

```powershell id="r3m8vx"
git push
```

Then verify the repository state:

```powershell id="d6q1kn"
git status
```

A completed session should normally end with:

```text id="y7t4bp"
nothing to commit, working tree clean
```

---

## Review Recent History

Display recent commits:

```powershell id="a2f9sj"
git log --oneline -5
```

This provides a compact overview of the five most recent commits.

---

## Standard Workflow

The complete workflow can be summarized as:

```text id="h5x8mr"
Navigate to repository
        ↓
git status
        ↓
Synchronize if necessary
        ↓
Open project
        ↓
Edit and test ←──────────────┐
        ↓                    │
git status                   │
        ↓                    │
git diff                     │
        ↓                    │
git add <files>              │
        ↓                    │
git diff --staged            │
        ↓                    │
git commit ──────────────────┘
        ↓
git push
        ↓
git status
```

The goal is not to execute commands mechanically, but to understand the state
of the repository at each stage.
