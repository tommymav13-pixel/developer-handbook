# Code Blocks

## Purpose

Use language-specific code blocks whenever possible.

This improves:

- Readability
- Syntax highlighting
- Documentation quality
- GitHub rendering

---

## Plain Text

Use for:

- File names
- Folder structures
- Version numbers
- General examples

```text
developer-handbook/
├── git/
├── python/
└── workflows/
```

```text
cv_v01.pdf
cv_v02.pdf
```

---

## PowerShell

Use for PowerShell commands.

```powershell
git status
git add .
git commit -m "Update handbook"
git push
```

---

## Python

Use for Python code.

```python
for number in range(5):
    print(number)
```

---

## Bash

Use for Linux or Git Bash commands.

```bash
mkdir project
cd project
git init
```

---

## JSON

Use for JSON data.

```json
{
    "name": "Tommy",
    "language": "Python"
}
```

---

## YAML

Use for YAML configuration files.

```yaml
name: Python
version: 3.14
```

---

## Markdown

Use for Markdown examples.

````markdown
# Title

## Subtitle

- Item 1
- Item 2
```` 

---

## Principle 

Always use the most appropriate language identifier. 

If no programming language applies, use: 
```text 
text 
```