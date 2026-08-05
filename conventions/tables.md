# Tables

This document describes the conventions for using tables in Markdown
documentation.

Tables provide a compact and structured way to present information.

---

# When to Use Tables

Use tables when comparing multiple items with the same properties.

Good examples include:

- Commands
- Keyboard shortcuts
- Naming conventions
- Version history
- Feature comparisons
- Configuration options

---

# When NOT to Use Tables

Do not use tables when:

- Long explanations are required.
- The content is mostly prose.
- A simple list is easier to read.

Prefer lists for tutorials and step-by-step instructions.

---

# Basic Table Structure

```text
| Column | Description |
|--------|-------------|
| Item | Example |
```

Result:

| Column | Description |
|--------|-------------|
| Item | Example |

---

# Alignment

Default:

```text
| Name | Description |
|------|-------------|
```

Left aligned:

```text
| Name | Description |
|:-----|:------------|
```

Center aligned:

```text
| Name | Description |
|:----:|:-----------:|
```

Right aligned:

```text
| Name | Description |
|-----:|------------:|
```

---

# Examples

## PowerShell Commands

| Command | Description |
|---------|-------------|
| `pwd` | Show the current directory |
| `dir` | List files and directories |
| `cd` | Change directory |
| `mkdir` | Create a new directory |

---

## Git Commands

| Command | Description |
|---------|-------------|
| `git status` | Show repository status |
| `git add .` | Stage all changes |
| `git commit` | Create a commit |
| `git push` | Push changes to GitHub |

---

## Naming Conventions

| Item | Convention |
|------|------------|
| Repository | kebab-case |
| Directory | lowercase |
| Markdown file | snake_case |
| Python file | snake_case |
| Class | PascalCase |
| Function | snake_case |
| Variable | snake_case |
| Constant | UPPER_CASE |

---

# Best Practices

- Keep tables concise.
- Use descriptive column headers.
- Keep similar information in the same column.
- Align comparable values.
- Avoid overly wide tables.
- Prefer readability over completeness.

---

# Current Convention

I use tables primarily for:

- Command references
- Naming conventions
- Skill overviews
- Project summaries
- Feature comparisons
- Status tracking