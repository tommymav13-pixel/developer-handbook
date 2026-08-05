# Git Merge

This document describes the basic Git merge workflow.

A merge combines changes from one branch into another branch.

---

## Basic Concept

Suppose a feature was developed on:

```text
feature-profile
```

and should be added to:

```text
main
```

The destination branch is `main`.

The source branch is `feature-profile`.

---

## Basic Merge Workflow

### 1. Check the current status

```powershell
git status
```

Commit or stash unfinished work before switching branches.

### 2. Switch to the destination branch

```powershell
git switch main
```

### 3. Update the destination branch

```powershell
git pull
```

### 4. Merge the source branch

```powershell
git merge feature-profile
```

### 5. Verify the result

```powershell
git status
git log --oneline
```

### 6. Push the merged branch

```powershell
git push
```

---

## Fast-Forward Merge

A fast-forward merge occurs when the destination branch has no new commits
since the feature branch was created.

Git can move the destination branch pointer forward without creating a merge
commit.

---

## Merge Commit

A merge commit may be created when both branches contain separate commits.

This commit records that two development histories were combined.

---

## Merge Conflicts

A conflict occurs when Git cannot automatically combine changes.

Example:

```text
CONFLICT (content): Merge conflict in README.md
```

Git adds conflict markers:

```text
<<<<<<< HEAD
Content from the current branch
=======
Content from the branch being merged
>>>>>>> feature-profile
```

Resolve the conflict by:

1. Reviewing both versions.
2. Keeping or combining the correct content.
3. Removing all conflict markers.
4. Saving the file.
5. Staging the resolved file.
6. Completing the merge commit.

Commands:

```powershell
git add README.md
git commit
```

---

## Abort a Merge

To stop an unfinished merge:

```powershell
git merge --abort
```

This normally returns the repository to its pre-merge state.

---

## Delete the Feature Branch

After a successful merge:

```powershell
git branch -d feature-profile
```

Delete the remote branch when appropriate:

```powershell
git push origin --delete feature-profile
```

---

## Recommended Workflow

```text
Create branch
      ↓
Make changes
      ↓
Test changes
      ↓
Commit changes
      ↓
Switch to main
      ↓
Pull latest changes
      ↓
Merge branch
      ↓
Push main
      ↓
Delete merged branch
```

---

## Best Practices

- Commit or stash changes before merging.
- Update the destination branch first.
- Review changes before the merge.
- Test the project after merging.
- Delete branches only after confirming the merge.
- Do not ignore unresolved conflict markers.

---

## Current Convention

For personal projects, I use short-lived feature branches and merge them into
`main` after the work is complete and tested.