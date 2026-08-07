# File System Conventions

## Naming

Use descriptive, predictable names.

Prefer:

- lowercase
- kebab-case for general directories and documentation
- project-specific conventions when applicable

Examples:

`developer-handbook/`
`file-system.md`
`language-learning/`

## Directory structure

Organize directories by responsibility or domain rather than file type.

Prefer:

`career/applications/2026/`

over:

`pdf-files/`
`word-files/`

## Temporary files

Temporary files should have an explicit lifecycle.

Examples:

- Downloads are temporary.
- Unclassified files go into an inbox.
- Obsolete material can be archived or deleted.

## Project conventions

Project-specific conventions take precedence over general conventions.

For example, an existing educational resource or framework may prescribe its
own directory structure.

## Avoid ambiguous names

Avoid:

`new`
`final`
`final2`
`test123`
`untitled`

Prefer names that communicate purpose.

## General principle

A filesystem should make the expected location of a file predictable.

Good organization reduces the need to search for files.

## Book Library

The book library is stored separately from projects, source code, study
assignments, and other working files.

The general structure is:

```text
books/
├── ereader/
├── pdf/
└── _inbox/
```

### Reading format

Books are first separated according to their primary reading format and
workflow.

- `ereader/` contains books intended for an e-reader, primarily EPUB files.
- `pdf/` contains PDF books intended primarily for reading or reference on a
  computer.
- `_inbox/` temporarily contains books that have not yet been classified and
  renamed.

This separation is intentional. PDF files are generally read on a computer,
while EPUB files can be transferred to an e-reader without also transferring
the PDF collection.

### Fiction and non-fiction

Within each format, books are first divided into:

```text
fiction/
non-fiction/
```

Example:

```text
books/
├── ereader/
│   ├── fiction/
│   └── non-fiction/
└── pdf/
    ├── fiction/
    └── non-fiction/
```

### Subject classification

Non-fiction books are classified according to their primary subject.

Examples of top-level subject categories include:

```text
non-fiction/
├── economics/
├── education/
├── history/
├── language-and-writing/
├── mathematics/
├── personal-development/
├── politics/
├── programming/
├── psychology/
├── science/
└── sociology/
```

Create additional subject categories only when they are needed by the actual
collection.

### Subject subdirectories

Large subjects can be divided into more specific disciplines.

For example:

```text
mathematics/
├── algebra/
├── calculus/
├── discrete-mathematics/
├── foundations/
├── geometry/
├── linear-algebra/
├── probability/
├── secondary-education/
├── statistics/
└── topology/
```

Another example:

```text
economics/
├── accounting/
├── econometrics/
├── environmental-economics/
├── finance/
├── international-economics/
├── macroeconomics/
├── marketing/
└── microeconomics/
```

Programming books can similarly be organized by technical subject:

```text
programming/
├── algorithms/
├── computer-science/
├── databases/
├── linux/
├── python/
└── software-engineering/
```

### Directory depth

Do not create unnecessary directory depth.

A new subdirectory should normally be created when:

- multiple books belong to a distinct subject;
- the category is expected to remain useful;
- the additional level makes books easier to find.

Empty directories for major, intentionally planned categories are acceptable,
but the filesystem should not attempt to predict every possible future
category.

### Classification rule

Classify a book according to its primary subject rather than every topic or
method that appears in the book.

Examples:

```text
Python Crash Course
→ programming/python/

A First Course in Probability
→ mathematics/probability/

Introduction to Econometrics
→ economics/econometrics/

Environmental Valuation with Discrete Choice Experiments
→ economics/environmental-economics/
```

When a book could reasonably belong to multiple categories, use the category
that best represents its primary purpose or intended use.

### Resources and projects

External resources and personal work remain separate.

For example:

```text
books/pdf/non-fiction/programming/python/
└── eric_matthes_python_crash_course_3e.pdf
```

contains the external book, while:

```text
programming/python-crash-course-3e/
└── python_work/
```

contains personal exercises and source code based on the book.

Do not store external books inside project repositories merely because they
are used by that project.

### Inbox workflow

New or unsorted books can temporarily be placed in:

```text
books/_inbox/
```

The intended workflow is:

```text
new book
→ _inbox
→ review
→ rename
→ classify
→ move to permanent directory
```

The `_inbox/` directory is temporary storage and should be reviewed
periodically.

### General principle

The library structure should be:

- predictable;
- subject-based;
- easy to navigate;
- consistent between formats where practical;
- only as deep as necessary.

The taxonomy should remain stable unless the actual collection demonstrates
that a different structure would make retrieval easier.