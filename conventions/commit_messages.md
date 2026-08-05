# Commit Message Conventions

This document describes the conventions used for Git commit messages across
my repositories.

Clear commit messages make project history easier to understand, review and
maintain.

---

## General Principles

A good commit message should:

- Describe one logical change.
- Be short and specific.
- Explain what changed.
- Use consistent wording.
- Avoid vague descriptions.

---

## Preferred Style

Use the imperative mood.

The message should read as if it completes this sentence:

> If applied, this commit will ...

Examples:

```text
Add project roadmap
Update Python skill overview
Fix broken README link
Remove outdated certification entry
Refactor PowerShell navigation functions
```

Avoid:

```text
Added project roadmap
Updating files
Made some changes
Fixed stuff
Work in progress
```

---

## Commit Message Structure

For small changes, use one concise subject line:

```text
Add Markdown style guide
```

For larger changes, use a subject line and an optional description:

```text
Add portfolio project documentation

Create project pages for the developer handbook, portfolio and Python
learning repository.
```

---

## Subject Line

The subject line should:

- Start with a capital letter.
- Begin with an action verb.
- Usually remain below 50 characters.
- Not end with a period.
- Describe the main change.

Examples:

```text
Add Git workflow documentation
Update portfolio timeline
Fix Markdown headings
Rename skills directory
```

---

## Common Action Verbs

| Verb | Use |
|------|-----|
| `Add` | Introduce a new file, feature or section |
| `Update` | Change or expand existing content |
| `Fix` | Correct an error or defect |
| `Remove` | Delete unnecessary content |
| `Rename` | Change a file, directory or identifier name |
| `Refactor` | Improve structure without changing behaviour |
| `Document` | Add or improve documentation |
| `Configure` | Change project or tool configuration |
| `Test` | Add or update tests |
| `Merge` | Combine branches |

---

## Examples by Category

### Documentation

```text
Add Git naming conventions
Update PowerShell command reference
Fix Markdown formatting
Document repository cloning workflow
```

### Python

```text
Add conditional exercise
Refactor guest list script
Fix incorrect loop condition
Rename variable for clarity
```

### Portfolio

```text
Add developer philosophy
Update technical skills
Create project index
Remove placeholder certification
```

### Repository Maintenance

```text
Add MIT license
Update .gitignore
Rename repository files
Configure Python formatter
```

---

## One Logical Change Per Commit

Prefer:

```text
Add Linux learning plan
```

followed by:

```text
Update portfolio README links
```

Instead of combining unrelated work:

```text
Add Linux plan and fix README and update CV
```

Small, focused commits are easier to review and reverse.

---

## Commit Frequency

Create a commit when:

- A logical task is complete.
- A document section has been meaningfully updated.
- A working code change has been tested.
- A clear milestone has been reached.

Do not commit after every individual keystroke.

Do not wait until many unrelated changes have accumulated.

---

## Checking Changes Before Committing

Use:

```powershell
git status
git diff
```

Then stage the intended changes:

```powershell
git add <file>
```

Review staged changes when necessary:

```powershell
git diff --staged
```

Create the commit:

```powershell
git commit -m "Add Markdown style guide"
```

---

## Avoid Sensitive Information

Never include confidential or personal information in commit messages.

Avoid mentioning:

- Passwords
- Access tokens
- Private email content
- Legal case details
- Personal addresses
- Other sensitive information

Remember that commit history may remain visible even after files are changed.

---

## Current Convention

My current convention is:

```text
<Action verb> <specific change>
```

Examples:

```text
Add portfolio roadmap
Update Git skill overview
Fix broken internal link
Rename reading list file
```

This convention may evolve as I gain more experience with professional Git
workflows.