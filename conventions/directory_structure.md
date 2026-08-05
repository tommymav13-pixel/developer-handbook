# Directory Structure

This document describes how directories are organized within a project.

Directories should group related content and remain easy to navigate.

---

# Purpose

Good directory structures make projects easier to:

- Understand
- Navigate
- Maintain
- Expand

---

# General Principles

- Keep directory names descriptive.
- Use lowercase names.
- Use kebab-case for multi-word directories.
- Avoid deeply nested folders when possible.

---

# Typical Project Structure

```text
project/
│
├── docs/
├── images/
├── src/
├── tests/
└── README.md
```

---

# Documentation Projects

```text
developer-handbook/
│
├── git/
├── powershell/
├── python/
├── conventions/
├── vscode/
└── README.md
```

---

# Portfolio Projects

```text
developer-portfolio/
│
├── about/
├── cv/
├── learning/
├── projects/
├── skills/
├── images/
└── README.md
```

---

# Python Learning Projects

```text
python-crash-course/
│
├── chapter_01/
├── chapter_02/
├── chapter_03/
├── exercises/
└── README.md
```

---

# Group Related Files

Good

```text
skills/
│
├── python.md
├── git.md
├── github.md
└── linux.md
```

Poor

```text
python.md
git.md
linux.md
roadmap.md
timeline.md
README.md
```

Everything stored in the project root becomes difficult to navigate.

---

# Keep the Root Clean

The root directory should contain only important files and major folders.

Avoid placing every file directly in the root.

---

# Naming

Preferred:

```text
images/
learning/
projects/
skills/
```

Avoid:

```text
New Folder/
Stuff/
Misc/
```

---

# Scalability

Create new directories only when they improve organization.

Avoid unnecessary complexity in small projects.

---

# Current Convention

My projects are organized around logical topics rather than file types.

Each directory should have a single, well-defined purpose.

Documentation grows together with the project instead of being added at the
end.