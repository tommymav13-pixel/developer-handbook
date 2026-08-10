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

## Push Rejected Because the Remote Contains Changes

Possible message:

```text
! [rejected] main -> main (fetch first)
Updates were rejected because the remote contains work that you do not have
locally.
```

### Cause

The remote branch contains commits that are not present in the local branch.

This can happen when:

* changes were made directly on GitHub;
* the repository was modified from another computer;
* another contributor pushed changes;
* the local repository has not been synchronized recently.

Do not immediately force-push.

### 1. Check the current state

```powershell
git status
```

Make sure local work is understood before integrating remote changes.

### 2. Fetch remote information

```powershell
git fetch
```

`git fetch` downloads information about remote commits without immediately
integrating them into the current branch.

### 3. Inspect the difference

Compare the local branch with the remote branch:

```powershell
git log --oneline --graph --decorate --all
```

A more focused comparison can also be made with:

```powershell
git log HEAD..origin/main --oneline
```

This shows commits available on `origin/main` that are not present in the
current local branch.

### 4. Integrate the remote changes

When the remote changes are understood:

```powershell
git pull
```

Resolve merge conflicts if Git reports any.

### 5. Push again

After the local branch contains the remote changes:

```powershell
git push
```

### General principle

When a push is rejected because the remote contains newer work:

```text
Push rejected
      ↓
git status
      ↓
git fetch
      ↓
inspect remote changes
      ↓
git pull
      ↓
resolve conflicts if necessary
      ↓
git push
```

Avoid `git push --force` unless rewriting remote history is intentional and the
consequences are fully understood.

---

## Uncommitted Changes Block Branch Switching

Git may refuse to switch branches because local changes would be overwritten.

Options:

### Commit the changes

```powershell
git add <files>
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

## File Is Both Staged and Modified

`git status` may show the same file under both:

```text
Changes to be committed:
    modified: example.md

Changes not staged for commit:
    modified: example.md
```

### Cause

The file was staged and then modified again.

For example:

```text
Edit file
    ↓
git add example.md
    ↓
Edit file again
```

Git now has:

```text
Working directory      newer version
Staging area           previously staged version
```

The next commit will contain only the staged version unless the newer changes
are staged as well.

### Inspect the differences

View unstaged changes:

```powershell
git diff
```

View staged changes:

```powershell
git diff --staged
```

### Include the latest version

Stage the file again:

```powershell
git add example.md
```

Then verify:

```powershell
git status
```

The file should now appear only under:

```text
Changes to be committed:
```

### General principle

`git add` does not permanently track all future changes to a file.

It copies the current state of the file into the staging area. Changes made
afterward must be staged separately if they should be included in the same
commit.

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