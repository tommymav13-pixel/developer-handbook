# GitHub

This document describes how I use GitHub together with Git.

Git is the local version control system. GitHub hosts remote repositories and
supports collaboration, documentation and portfolio development.

---

## Main Uses

I use GitHub to:

- Store remote copies of repositories.
- Publish software projects.
- Maintain my developer portfolio.
- Document my learning process.
- Review repository history.
- Share projects with recruiters and developers.

---

## Git and GitHub

Git and GitHub are related, but they are not the same tool.

| Tool | Purpose |
|------|---------|
| Git | Tracks changes locally |
| GitHub | Hosts Git repositories online |

Git can be used without GitHub.

GitHub repositories normally use Git for version control.

---

## Creating a Repository

A repository can be created:

1. Locally first.
2. On GitHub first.

When the repository already exists on GitHub, use:

```powershell
git clone <repository-url>
```

When the project starts locally, use:

```powershell
git init
```

Then connect it to GitHub:

```powershell
git remote add origin <repository-url>
git branch -M main
git push -u origin main
```

---

## Remote Repository

The default name for the primary remote repository is:

```text
origin
```

View configured remotes:

```powershell
git remote -v
```

Example output:

```text
origin  https://github.com/username/project.git (fetch)
origin  https://github.com/username/project.git (push)
```

---

## Repository Visibility

GitHub repositories can be:

| Visibility | Meaning |
|------------|---------|
| Public | Anyone can view the repository |
| Private | Only authorized users can view it |

Portfolio projects should usually be public unless they contain private,
licensed or sensitive material.

---

## README

The `README.md` file is the main entry point of a repository.

It should explain:

- What the project is.
- Why it exists.
- How it is structured.
- How it can be used.
- What its current status is.

---

## Profile Repository

A repository with exactly the same name as the GitHub username can contain a
special profile `README.md`.

That README is displayed on the GitHub profile page.

---

## Repository Description

A repository description should be short and specific.

Example:

```text
Personal developer portfolio showcasing projects, skills and continuous
learning.
```

---

## Topics

GitHub topics help classify repositories.

Possible examples:

```text
python
learning
portfolio
documentation
git
powershell
```

Only add topics that accurately describe the repository.

---

## Pinned Repositories

Pinned repositories appear prominently on a GitHub profile.

Priority should be given to:

- Strong independent projects.
- The developer portfolio.
- The developer handbook.
- Relevant learning repositories.

---

## Issues

GitHub Issues can be used to:

- Track bugs.
- Plan improvements.
- Record tasks.
- Discuss changes.

Issues are useful when a project becomes too large for an informal to-do
list.

---

## Pull Requests

Pull requests propose changes from one branch to another.

They support:

- Reviewing changes.
- Discussing implementation.
- Running automated checks.
- Merging approved work.

Pull requests are especially important in collaborative projects.

---

## Current Convention

I use GitHub as:

- A remote repository host.
- A developer portfolio.
- A documentation platform.
- A record of continuous technical development.