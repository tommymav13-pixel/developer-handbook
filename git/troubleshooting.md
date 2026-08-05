# Git Troubleshooting

This document contains solutions for common Git problems.

Always begin by checking the repository state.

```powershell
git status
```

---

## Git Is Not Recognized

Error:

```text
git is not recognized as the name of a cmdlet
```

Possible causes:

- Git is not installed.
- Git is not included in the system `PATH`.
- The terminal was opened before Git was installed.

Check:

```powershell
git --version
```

Possible solution:

1. Install Git.
2. Restart PowerShell or VS Code.
3. Verify the installation again.

---

## Not a Git Repository

Error:

```text
fatal: not a git repository
```

Cause:

The current directory does not contain a `.git` directory.

Check the current location:

```powershell
pwd
```

Show hidden files:

```powershell
dir -Force
```

Move to the correct repository:

```powershell
cd <repository-path>
```

---

## Remote Origin Already Exists

Error:

```text
fatal: remote origin already exists
```

Inspect the current remote:

```powershell
git remote -v
```

Update the URL:

```powershell
git remote set-url origin <repository-url>
```

Do not add a second `origin`.

---

## No Upstream Branch

Error:

```text
fatal: The current branch has no upstream branch
```

Solution:

```powershell
git push -u origin main
```

For another branch:

```powershell
git push -u origin <branch-name>
```

---

## Push Rejected

Possible message:

```text
Updates were rejected because the remote contains work that you do not have
locally.
```

First download and integrate the remote changes:

```powershell
git pull
```

Then try again:

```powershell
git push
```

Do not force-push unless the consequences are understood.

---

## Uncommitted Changes Block Branch Switching

Git may refuse to switch branches because local changes would be overwritten.

Options:

### Commit the changes

```powershell
git add .
git commit -m "Save current work"
```

### Temporarily stash the changes

```powershell
git stash
```

Then switch:

```powershell
git switch <branch-name>
```

Restore the changes later:

```powershell
git stash pop
```

---

## Accidentally Staged a File

Unstage the file:

```powershell
git restore --staged <file>
```

The working copy remains unchanged.

---

## Accidentally Modified a File

Discard local unstaged changes:

```powershell
git restore <file>
```

Warning: this removes the local changes from that file.

---

## Deleted and New Files After Renaming a Directory

Git may initially display moved files as deleted and untracked.

Stage all changes:

```powershell
git add .
```

Then inspect:

```powershell
git status
```

Git may recognize the operation as a rename after staging.

---

## Merge Conflict

Check the affected files:

```powershell
git status
```

Open each conflicting file and remove conflict markers:

```text
<<<<<<<
=======
>>>>>>>
```

Then stage and commit the resolution:

```powershell
git add <file>
git commit
```

Abort when necessary:

```powershell
git merge --abort
```

---

## Unrelated Histories

Possible error:

```text
fatal: refusing to merge unrelated histories
```

This may happen when both the local and remote repository were initialized
separately.

Possible command:

```powershell
git pull origin main --allow-unrelated-histories
```

Use this only when the two histories genuinely need to be combined.

Cloning an existing remote repository usually avoids this issue.

---

## Wrong Repository URL

Inspect:

```powershell
git remote -v
```

Correct it:

```powershell
git remote set-url origin <correct-repository-url>
```

---

## Authentication Failure

Possible causes:

- The account is not authenticated.
- Credentials are outdated.
- The repository is private.
- The current account lacks access.

Possible steps:

1. Verify the repository URL.
2. Verify repository access in GitHub.
3. Sign in again through Git Credential Manager.
4. Retry the command.

---

## Repository Contains Sensitive Information

Do not assume that deleting a file in a new commit completely removes it from
history.

Immediate actions:

1. Revoke exposed passwords or tokens.
2. Replace compromised credentials.
3. Remove the sensitive material.
4. Investigate Git history cleanup.
5. Avoid pushing further until the exposure is understood.

Never commit:

- Passwords.
- API keys.
- Access tokens.
- Private keys.
- Personal legal information.
- Confidential documents.

---

## Diagnostic Commands

Use these commands when investigating a problem:

```powershell
pwd
dir -Force
git status
git branch
git remote -v
git log --oneline
git diff
```

---

## Troubleshooting Order

Use this sequence:

1. Read the complete error message.
2. Run `git status`.
3. Confirm the current directory.
4. Confirm the current branch.
5. Inspect the remote configuration.
6. Review recent changes.
7. Choose the least destructive solution.

---

## Current Convention

I avoid destructive commands until I understand:

- The current repository state.
- Which files will change.
- Whether local work may be lost.
- Whether the remote history will be affected.