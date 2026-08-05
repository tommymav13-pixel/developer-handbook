# Links

This document describes the conventions for using links in Markdown
documentation.

Links should be descriptive, reliable and easy to understand.

---

# Purpose

Links are used to:

- Navigate documentation
- Reference repositories
- Reference official documentation
- Connect related documents

---

# Internal Links

Use relative paths for links inside the same repository.

Example:

```markdown
[Git Guide](../git/git.md)
```

Benefits:

- Continue to work locally.
- Continue to work on GitHub.
- Do not depend on a specific domain.

---

# Repository Links

Use repository URLs when referring to another repository.

Example:

```markdown
[Developer Portfolio](https://github.com/tommymav13-pixel/developer-portfolio)
```

---

# External Links

Use descriptive link text.

Good:

```markdown
[Python Documentation](https://docs.python.org/3/)
```

Avoid:

```markdown
[Click here](https://docs.python.org/3/)
```

The reader should understand the destination before opening the link.

---

# Email Links

Example:

```markdown
<example@email.com>
```

---

# Section Links

Markdown automatically generates anchor links for headings.

Example heading:

```markdown
## Installation
```

Can be linked as:

```markdown
[Installation](#installation)
```

---

# Relative Paths

Examples:

```markdown
[README](../README.md)

[Portfolio](../../developer-portfolio/README.md)

[Git Guide](../git/git.md)
```

Prefer relative paths whenever possible.

---

# Link Best Practices

- Use descriptive text.
- Keep links up to date.
- Avoid duplicate links.
- Prefer official documentation.
- Test links periodically.

---

# Official Documentation

Whenever possible, link directly to official documentation.

Examples:

- Python Documentation
- Git Documentation
- GitHub Docs
- Microsoft Learn

Avoid unofficial sources when official documentation is available.

---

# Current Convention

I use:

- Relative links within repositories.
- Repository URLs between repositories.
- Official documentation whenever available.
- Descriptive link text instead of generic wording.