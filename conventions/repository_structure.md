# Repository Structure

This document describes the standard structure I use for GitHub repositories.

A consistent repository structure improves readability, maintainability and
collaboration.

---

# Purpose

Every repository should have a clear purpose and a predictable layout.

A visitor should quickly understand:

- What the project does
- How to use it
- Where to find documentation
- Where the source code is located

---

# Standard Repository Structure

```text
project-name/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/
├── images/
├── src/
├── tests/
│
└── requirements.txt
```

Not every project requires every directory.

---

# Core Files

## README.md

The main entry point of the repository.

Should describe:

- Purpose
- Features
- Installation
- Usage
- Technologies
- Project status
- License

---

## LICENSE

Defines how others may use the project.

Preferred:

- MIT License

---

## .gitignore

Specifies which files Git should ignore.

Examples:

- __pycache__/
- .venv/
- *.pyc

---

# Common Directories

## docs/

Project documentation.

Examples:

- User guides
- Architecture
- API documentation

---

## images/

Images used in documentation.

Examples:

- Screenshots
- Diagrams
- Logos

---

## src/

Application source code.

---

## tests/

Automated tests.

---

# Repository Types

Learning Repository

```text
README.md
images/
chapter_01/
chapter_02/
chapter_03/
```

Portfolio Repository

```text
README.md
about/
cv/
learning/
projects/
skills/
images/
```

Python Project

```text
README.md
src/
tests/
images/
requirements.txt
```

---

# Best Practices

- Keep the root directory clean.
- Group related files.
- Separate documentation from source code.
- Keep repository names descriptive.
- Follow consistent naming conventions.

---

# Current Convention

Every repository should contain at least:

- README.md
- .gitignore (when appropriate)
- LICENSE (when appropriate)

Additional directories are added only when they improve project structure.