# Basic Git Workflow

This document describes the standard Git workflow used for most software
projects.

The goal is to understand and control the state of the repository throughout
the development process.

---

## Repository States

A basic Git workflow involves several different states:

```text
Working directory
       ↓
   git add
       ↓
Staging area
       ↓
  git commit
       ↓
Local repository
       ↓
   git push
       ↓
Remote repository
```

Understanding these states is important because `git add`, `git commit`, and
`git push` perform different operations.

---

## 1. Check Repository Status

```powershell
git status
```

Use `git status` frequently to inspect:

* modified files;
* untracked files;
* staged changes;
* deleted files;
* the current branch;
* synchronization with the remote branch.

---

## 2. Review Changes

Before staging changes:

```powershell
git diff
```

This displays changes in the working directory that have not yet been staged.

---

## 3. Stage Changes

Stage a specific file:

```powershell
git add README.md
```

Stage a directory:

```powershell
git add python
```

Stage all current changes:

```powershell
git add .
```

Prefer staging specific files when creating a focused commit.

Use `git add .` when all current changes intentionally belong to the same
commit.

---

## 4. Review Staged Changes

After staging:

```powershell
git status
```

Then inspect the actual staged changes:

```powershell
git diff --staged
```

This shows the changes that will be included in the next commit.

---

## 5. Create a Commit

Create a commit:

```powershell
git commit -m "Update Git workflow documentation"
```

A commit stores the staged snapshot in the local Git repository.

Use a concise message that describes what the commit accomplishes.

---

## Staging Is a Snapshot

Running `git add` stages the current version of a file.

If the file is modified again after staging, Git can contain both:

* a staged version;
* newer unstaged changes.

For example:

```text
Edit file
    ↓
git add file
    ↓
Edit file again
    ↓
Staged version + unstaged changes
```

Run:

```powershell
git status
```

to inspect this situation.

To include the latest changes in the next commit, stage the file again:

```powershell
git add <filename>
```

This updates the staged snapshot.

---

## 6. Continue Development or Push

A commit does not need to be pushed immediately.

After creating a logical commit, development can continue:

```text
Edit and test ←──────────────┐
      ↓                      │
git status                   │
      ↓                      │
git diff                     │
      ↓                      │
git add <files>              │
      ↓                      │
git diff --staged            │
      ↓                      │
git commit ──────────────────┘
      ↓
git push
```

This allows several focused local commits to be created before pushing them to
the remote repository.

---

## 7. Push Commits

Push local commits to the remote repository:

```powershell
git push
```

`git push` transfers commits that exist locally but are not yet available on
the corresponding remote branch.

Multiple local commits can be transferred with a single push.

---

## 8. Verify Repository State

After pushing:

```powershell
git status
```

A clean and synchronized repository commonly reports:

```text
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

---

## Starting with an Existing Repository

Clone an existing remote repository:

```powershell
git clone <repository-url>
```

Move into the repository:

```powershell
cd repository-name
```

Inspect its state:

```powershell
git status
```

Before beginning new work, synchronize when necessary:

```powershell
git pull
```

---

## Standard Workflow

The core workflow is:

```text
git status
      ↓
git diff
      ↓
git add <files>
      ↓
git status
      ↓
git diff --staged
      ↓
git commit
      ↓
continue development
      or
      ↓
git push
      ↓
git status
```

---

## Useful Commands

| Command             | Purpose                                            |
| ------------------- | -------------------------------------------------- |
| `git status`        | Inspect the repository state                       |
| `git diff`          | Review unstaged changes                            |
| `git diff --staged` | Review staged changes                              |
| `git add`           | Add changes to the staging area                    |
| `git commit`        | Store a staged snapshot locally                    |
| `git push`          | Send local commits to a remote repository          |
| `git pull`          | Fetch and integrate remote changes                 |
| `git fetch`         | Download remote information without integrating it |
| `git clone`         | Create a local copy of an existing repository      |
| `git log`           | Inspect commit history                             |
| `git stash`         | Temporarily store uncommitted changes              |

---

## Best Practices

* Check `git status` frequently.
* Review changes before staging.
* Review staged changes before committing.
* Stage intentionally rather than automatically.
* Create small, focused commits.
* Write meaningful commit messages.
* Push completed work regularly.
* Understand the repository state before executing Git commands.

---

## Related Documentation

* `branching.md` — working with branches
* `merge.md` — merging Git branches
* `troubleshooting.md` — common Git problems and solutions
* `../workflows/daily_workflow.md` — complete daily development workflow
