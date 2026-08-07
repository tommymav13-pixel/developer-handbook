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

## Books

Book filenames use `snake_case`.

### General format

The default naming convention is:

```text
author_title_edition.ext
```

Example:

```text
eric_matthes_python_crash_course_3e.pdf
```

Use lowercase letters and underscores between words.

### Authors

Use the author's first and last name when known.

Example:

```text
eric_matthes_python_crash_course_3e.pdf
```

For books with multiple authors, include the authors when this results in a
reasonable filename.

Examples:

```text
gerard_buskes_arnoud_van_rooij_topological_spaces.pdf
margaret_lial_john_hornsby_college_algebra_and_trigonometry_7e.pdf
```

When a book has many authors, use only the primary or first author.

Example:

```text
petr_mariel_environmental_valuation_with_discrete_choice_experiments.pdf
```

Do not create excessively long filenames solely to preserve a complete author
list.

### Titles

Use the recognizable full title when practical.

Example:

```text
sheldon_ross_a_first_course_in_probability_10e.pdf
```

Remove punctuation that is unnecessary for identifying the title.

Convert spaces and separators to underscores.

For example:

```text
Design and Analysis of Experiments and Observational Studies Using R
```

becomes:

```text
design_and_analysis_of_experiments_and_observational_studies_using_r
```

### Editions

Include the edition when it is known and relevant.

Use:

```text
1e
2e
3e
4e
...
```

Examples:

```text
james_stewart_calculus_8e.pdf
sheldon_ross_a_first_course_in_probability_10e.pdf
luciano_ramalho_fluent_python_2e.pdf
```

Do not add an edition when it is unknown.

Do not guess an edition from the publication year.

### Series and related files

For books that form part of a series, prioritize filenames that keep related
files together when sorted alphabetically.

Example:

```text
getal_en_ruimte_vwo_d_deel_1_11e.pdf
getal_en_ruimte_vwo_d_deel_1_11e_uitwerkingen.pdf
getal_en_ruimte_vwo_d_deel_2_11e.pdf
getal_en_ruimte_vwo_d_deel_2_11e_uitwerkingen.pdf
```

When an answer book or solutions file belongs to a specific edition, include
the edition in both filenames when known.

Example:

```text
book_title_11e.pdf
book_title_11e_uitwerkingen.pdf
```

### Download metadata

Remove download-specific and bibliographic metadata that does not improve
normal file identification.

Normally omit:

- download source;
- download hashes;
- ISBN;
- publisher;
- repository identifiers;
- unnecessary collection or series information;
- publication year when the edition already identifies the version.

Avoid filenames such as:

```text
Introduction to Topology Third Edition Dover Books on Mathematics Bert
Mendelson Dover Publications 1990 ISBN 978... Annas Archive.pdf
```

Prefer:

```text
bert_mendelson_introduction_to_topology_3e.pdf
```

### Publication years

Publication years are normally omitted.

Prefer:

```text
james_stewart_calculus_8e.pdf
```

instead of:

```text
james_stewart_calculus_8e_2016.pdf
```

Include a year only when it is necessary to distinguish otherwise ambiguous
files.

### Filename length

Keep filenames descriptive but reasonably short.

Long automatically generated filenames can:

- reduce readability;
- make files harder to navigate;
- make command-line operations inconvenient;
- contribute to Windows path-length problems.

Retain information that helps identify, search, or sort the book and remove
metadata that does not serve those purposes.

### Special collections

Some files are better identified by a series or institutional title than by
an individual author.

In these cases, prioritize predictable sorting over strict adherence to the
default author-first format.

Example:

```text
getal_en_ruimte_vwo_d_deel_1_11e.pdf
```

rather than forcing an author list into the filename.

### File extensions

Preserve the actual file extension.

Examples:

```text
author_title_2e.pdf
author_title_2e.epub
```

The extension is not written into the descriptive portion of the filename.

### General rule

The default structure is:

```text
author_title_edition.ext
```

A book filename should be:

- descriptive;
- concise;
- predictable;
- searchable;
- sortable;
- free of unnecessary download metadata.

When the default convention produces an unnecessarily complicated filename,
prioritize clarity and retrieval over rigid adherence to the pattern.

# Future Conventions

Topics to document later:

- Docker image names
- Environment variables
- Database naming
- API naming
- REST endpoints
- Test naming