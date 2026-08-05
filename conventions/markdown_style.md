# Markdown Style Guide

This document describes the Markdown conventions used across my repositories.

Consistent Markdown improves readability, navigation and maintainability.

---

## General Principles

- Use clear and descriptive headings.
- Keep formatting simple.
- Prefer readability over decoration.
- Use consistent naming and spacing.
- Keep documentation easy to update.
- Avoid unnecessary visual clutter.

---

## File Names

Use `snake_case` for regular Markdown files.

Examples:

```text
reading_list.md
soft_skills.md
commit_messages.md
markdown_style.md
```

Use established uppercase names for conventional repository files.

Examples:

```text
README.md
CHANGELOG.md
CONTRIBUTING.md
LICENSE
```

---

## Document Title

Use one level-one heading at the top of each document.

```markdown
# Markdown Style Guide
```

Do not use multiple level-one headings in the same document.

Use level-two and level-three headings for subsections.

```markdown
## Headings

### Heading Levels
```

Avoid skipping heading levels.

Prefer:

```markdown
# Title

## Section

### Subsection
```

Avoid:

```markdown
# Title

#### Subsection
```

---

## Line Length

Aim for a maximum line length of approximately 80 characters in source files.

Break long prose at a natural point:

```markdown
This repository documents my transition from science education to software
engineering.
```

GitHub renders these lines as one paragraph.

Do not add a dash merely because a sentence continues on the next source
line.

---

## Paragraphs

Separate paragraphs with one blank line.

```markdown
This is the first paragraph.

This is the second paragraph.
```

A single line break inside a paragraph usually does not create a new
paragraph in rendered Markdown.

---

## Lists

Use hyphens for unordered lists.

```markdown
- Python
- Git
- PowerShell
```

Use numbers for ordered steps.

```markdown
1. Check the repository status.
2. Stage the intended changes.
3. Create a commit.
4. Push the commit.
```

Keep list items grammatically consistent.

Prefer:

```markdown
- Create repositories.
- Write documentation.
- Test Python scripts.
```

Avoid mixing forms:

```markdown
- Creating repositories.
- Write documentation.
- Python scripts are tested.
```

---

## Nested Lists

Indent nested items consistently with four spaces.

```markdown
- Development tools
    - Git
    - GitHub
    - VS Code
- Programming
    - Python
```

Use nested lists only when they improve the structure.

---

## Emphasis

Use bold text sparingly for important terms.

```markdown
Use **kebab-case** for repository names.
```

Use italics for book titles or limited emphasis.

```markdown
I am currently studying *Python Crash Course*.
```

Avoid excessive bold, italics or combined emphasis.

---

## Inline Code

Use single backticks for:

- Commands
- File names
- Directory names
- Variables
- Short code fragments

Examples:

```markdown
Run `git status` before committing.

Open the `README.md` file.

Navigate to the `skills/` directory.
```

---

## Code Blocks

Use fenced code blocks with a language identifier.

````text
```python
message = "Hello, world!"
print(message)
```