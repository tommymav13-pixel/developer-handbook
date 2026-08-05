# Versioning

This document describes the versioning conventions used across my projects.

Consistent version numbers improve organization, traceability and document
management.

---

# Purpose

Version numbers make it possible to:

- Track revisions.
- Restore older versions.
- Identify the latest document.
- Avoid ambiguous filenames.

---

# Naming Convention

Use the following format:

```text
v01
v02
v03
```

Always use two digits.

Examples:

```text
v01
v02
v10
v25
```

---

# File Naming

Append the version number to the filename.

Examples:

```text
cv_v01.pdf
cv_v02.pdf
developer_handbook_v03.pdf
project_plan_v05.docx
```

---

# Avoid

Do not use descriptive version names.

Avoid:

```text
cv_new.pdf
cv_final.pdf
cv_final_final.pdf
cv_really_final.pdf
cv_latest.pdf
```

These names quickly become confusing.

---

# Working Documents

Increase the version number whenever a meaningful revision has been made.

Example:

```text
proposal_v01.docx
proposal_v02.docx
proposal_v03.docx
```

---

# Final Documents

When a document is finalized, keep the version number.

Example:

```text
employment_contract_v03.pdf
```

Avoid renaming it to:

```text
employment_contract_final.pdf
```

The version number already identifies the latest revision.

---

# Major vs Minor Versions

For most personal projects, sequential version numbers are sufficient.

Example:

```text
v01
v02
v03
```

If needed in larger projects:

```text
v1.0
v1.1
v1.2
v2.0
```

---

# Git Repositories

Git already stores version history.

Do not create filenames such as:

```text
script_v07.py
```

Instead:

```text
script.py
```

and let Git manage the history.

Version numbers are mainly intended for exported documents such as:

- PDF
- DOCX
- XLSX
- Presentations

---

# Benefits

Using consistent version numbers:

- Improves file organization.
- Prevents duplicate filenames.
- Makes chronological sorting easier.
- Reduces confusion.
- Works well with Git and cloud storage.

---

# Current Convention

I use:

- Two-digit version numbers (`v01`, `v02`, `v03`)
- Sequential numbering
- No descriptive version names
- Git for source code version history
- Version numbers primarily for exported documents