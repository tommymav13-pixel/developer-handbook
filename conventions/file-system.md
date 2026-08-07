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