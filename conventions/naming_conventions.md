# Naming Conventions

This document describes the naming conventions used across my software
projects.

Following consistent naming conventions improves readability,
maintainability and collaboration.

---

# General Principles

- Use descriptive names.
- Be consistent.
- Avoid abbreviations unless they are widely accepted.
- Prefer readability over brevity.

---

# GitHub Repositories

Use **kebab-case**.

Examples:

```text
developer-portfolio
developer-handbook
python-crash-course-3e
```

Reason:

- Easy to read.
- Common convention on GitHub.
- Produces clean URLs.

---

# Directories

Use lowercase directory names.

For multi-word directories, prefer **kebab-case**.

Examples:

```text
projects/
learning/
images/
about/
skills/

python-projects/
machine-learning/
```

---

# Markdown Files

Use **snake_case**.

Examples:

```text
reading_list.md
soft_skills.md
timeline.md
roadmap.md
naming_conventions.md
version_numbers.md
legal_documents.md
```

Special Markdown files follow common GitHub conventions.

Examples:

```text
README.md
LICENSE
CHANGELOG.md
CONTRIBUTING.md
```

---

# Python Files

Follow PEP 8.

Use **snake_case**.

Examples:

```text
weather_api.py
expense_tracker.py
reading_list.py
```

---

# Python Packages

Use **snake_case**.

Examples:

```text
statistics_tools
data_processing
```

---

# Python Classes

Use **PascalCase**.

Examples:

```python
ExpenseTracker
WeatherAnalyzer
GitRepository
```

---

# Python Functions

Use **snake_case**.

Examples:

```python
calculate_average()
load_data()
save_file()
```

---

# Variables

Use **snake_case**.

Examples:

```python
student_count
learning_path
current_score
```

---

# Constants

Use **UPPER_CASE**.

Examples:

```python
MAX_ITERATIONS
DEFAULT_TIMEOUT
PI
```

---

# Git Branches

Use **kebab-case**.

Examples:

```text
main
develop
feature/github-profile
feature/devops-roadmap
bugfix/readme-links
```

---

# Commit Messages

Use short, imperative sentences.

Examples:

```text
Add developer portfolio

Update README

Fix markdown formatting

Refactor Git workflow documentation
```

---

# Future Conventions

Topics to document later:

- Docker image names
- Environment variables
- Database naming
- API naming
- REST endpoints
- Test naming