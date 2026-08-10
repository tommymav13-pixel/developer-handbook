# Create a New Repository

This document describes the workflow for creating a new Git repository locally
and connecting it to GitHub.

Use this workflow when starting a new project on the local computer.

---

## 1. Create the Project Directory

Create a new directory:

```powershell id="s6w0cu"
mkdir my-project
```

Move into it:

```powershell id="7h2xje"
cd my-project
```

Verify the current location:

```powershell id="e2q7mn"
Get-Location
```

---

## 2. Initialize Git

Initialize a Git repository:

```powershell id="u5k1vh"
git init
```

This creates the hidden `.git` directory that Git uses to store repository
information and history.

Verify the repository:

```powershell id="p9f4bt"
git status
```

---

## 3. Create the Initial Project Files

Typical initial files include:

```text id="2ivh13"
README.md
.gitignore
LICENSE
```

The exact files depend on the project.

For example:

```powershell id="6rj8ow"
New-Item -ItemType File -Path README.md
New-Item -ItemType File -Path .gitignore
```

Create the initial project structure before making the first commit when
practical.

---

## 4. Review the Repository

Inspect the files:

```powershell id="hd7j3k"
dir -Force
```

Check Git:

```powershell id="8lznmq"
git status
```

Review the files before staging them.

Make sure that sensitive information, generated files, and files that should be
ignored are not accidentally included.

---

## 5. Create the Initial Commit

Stage the intended files:

```powershell id="41wq0g"
git add .
```

Check the staging area:

```powershell id="5b2ydm"
git status
```

Optionally inspect the staged changes:

```powershell id="09vx3r"
git diff --staged
```

Create the first commit:

```powershell id="p3xyqo"
git commit -m "Initial commit"
```

---

## 6. Create the GitHub Repository

Create a new repository on GitHub.

When the project has already been initialized locally, create the GitHub
repository without adding conflicting initial files where possible.

For example, avoid independently creating another README if the local
repository already contains one.

This helps prevent separate local and remote histories.

---

## 7. Connect the Remote Repository

Add the GitHub repository as the `origin` remote:

```powershell id="k4c9nf"
git remote add origin https://github.com/USERNAME/my-project.git
```

Verify the remote:

```powershell id="z8r1dh"
git remote -v
```

---

## 8. Set the Main Branch

Rename the current branch to `main` when necessary:

```powershell id="6f9m2a"
git branch -M main
```

Verify:

```powershell id="3c7wyh"
git branch
```

---

## 9. Push to GitHub

Push the local branch and configure its upstream:

```powershell id="0vr5kx"
git push -u origin main
```

The `-u` option establishes the relationship between the local `main` branch
and `origin/main`.

After this initial push, future pushes can normally use:

```powershell id="j4hf6c"
git push
```

---

## 10. Verify the Repository

Check the final state:

```powershell id="95v0me"
git status
```

A synchronized repository should normally report:

```text id="ix4b7j"
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

Also verify the commit history:

```powershell id="h7c1qy"
git log --oneline
```

---

## Complete Workflow

```text id="x5rwne"
Create project directory
        ↓
git init
        ↓
Create project files
        ↓
git status
        ↓
git add <files>
        ↓
git diff --staged
        ↓
git commit
        ↓
Create empty GitHub repository
        ↓
git remote add origin <URL>
        ↓
git remote -v
        ↓
git branch -M main
        ↓
git push -u origin main
        ↓
git status
```

---

## Important Distinction

Creating a Git repository locally and creating a repository on GitHub are
separate operations.

```text id="f0k2za"
Local repository
       │
       │ git push
       ↓
GitHub repository
```

The remote named `origin` connects the local repository to its GitHub
counterpart.

---

## Related Documentation

* `basic_workflow.md` — standard Git development workflow
* `clone_repository.md` — cloning an existing repository
* `github.md` — GitHub-related concepts and workflows
* `troubleshooting.md` — common Git problems and solutions
