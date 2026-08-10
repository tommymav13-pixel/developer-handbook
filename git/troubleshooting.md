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
