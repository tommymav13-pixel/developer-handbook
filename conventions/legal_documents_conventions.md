# Legal Documents

This document describes the conventions used for organizing legal documents.

Consistent naming improves readability, sorting and referencing.

---

# Purpose

Legal documents should be:

- Easy to identify.
- Easy to sort.
- Easy to reference.
- Consistent across all legal cases.

---

# Naming Convention

Use the following format:

```text
NN_Bijlage_X_Beschrijving.pdf
```

Example:

```text
01_Bijlage_1_Feitenrelaas.pdf
02_Bijlage_2_Fotos.pdf
03_Bijlage_3_Emailcorrespondentie.pdf
04_Bijlage_4_Arbeidsovereenkomst.pdf
```

Benefits:

- Automatic sorting.
- Clear document descriptions.
- Easy referencing in legal correspondence.

---

# Numbering

Number every attachment.

Preferred:

```text
01_
02_
03_
04_
```

Instead of:

```text
1_
2_
3_
```

Using two digits improves consistency and leaves room for future additions.

---

# File Names

Use descriptive names.

Good:

```text
02_Bijlage_4_Arbeidsovereenkomst.pdf
```

```text
07_Bijlage_8_Getuigenverklaring.pdf
```

Avoid:

```text
Document.pdf
Scan.pdf
Nieuw.pdf
```

---

# Dates

Use the ISO 8601 standard.

```text
YYYY-MM-DD
```

Example:

```text
2026-08-04
```

Avoid:

```text
04-08-2026
```

Benefits:

- Chronological sorting.
- International standard.
- Works correctly in Windows Explorer.
- Consistent across operating systems.

---

# Versions

When multiple versions exist, use version numbers.

Examples:

```text
Sommatiebrief_v01.pdf
Sommatiebrief_v02.pdf
Sommatiebrief_v03.pdf
```

Avoid:

```text
Sommatiebrief_nieuw.pdf
Sommatiebrief_definitief.pdf
Sommatiebrief_echt_definitief.pdf
```

---

# File Format

Preferred:

```text
PDF
```

Reasons:

- Preserves formatting.
- Difficult to modify accidentally.
- Universally supported.
- Suitable for legal proceedings.

---

# Directory Structure

Example:

```text
Legal_Case/
│
├── Correspondence/
├── Evidence/
├── Attachments/
├── Court/
└── Timeline/
```

---

# Current Convention

I use:

- ISO 8601 dates (`YYYY-MM-DD`)
- Sequential numbering
- Descriptive filenames
- Version numbers
- PDF for finalized documents