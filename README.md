# Developer Handbook

A personal software development knowledge base documenting concepts,
conventions, commands, tools, and workflows encountered during my development
journey.

The handbook is intended as a practical reference rather than a complete
programming guide. It grows as new concepts are learned, practiced, and applied.

## Purpose

The main goals of this repository are to:

* document reusable development workflows;
* maintain references for frequently used commands;
* record programming and repository conventions;
* document solutions to problems encountered during development;
* preserve useful programming patterns and technical concepts;
* reduce dependence on external references for frequently used knowledge.

## Topics

The handbook currently covers:

* Git and GitHub;
* PowerShell;
* Python;
* Java;
* SQL and MySQL;
* Visual Studio Code;
* Markdown;
* development conventions;
* development workflows.

Additional topics can be added as they become relevant through study and
practical development.

## Repository Structure

```text id="f6fxv2"
developer-handbook/
├── conventions/
├── git/
├── java/
├── markdown/
├── notes/
├── powershell/
├── python/
├── sql/
├── vscode/
└── workflows/
```

### `conventions/`

General conventions for files, directories, repositories, Markdown, commit
messages, versioning, and other development-related standards.

### `git/`

Git and GitHub workflows, commands, branching, merging, repository creation,
cloning, and troubleshooting.

### `java/`

Java development environment, compilation process, and programming concepts.

### `markdown/`

Markdown syntax and formatting references.

### `notes/`

Supporting notes, reading material, ideas, and resources related to software
development.

### `powershell/`

PowerShell commands, aliases, file management, file selection, and command-line
workflows.

### `python/`

Python conventions, useful programming patterns, and language-specific
reference material.

### `sql/`

SQL concepts, MySQL setup, and database-related reference material.

### `vscode/`

Visual Studio Code configuration and keyboard shortcuts.

### `workflows/`

Reusable workflows for daily development, project creation, and project
organization.

## Documentation Principles

Documentation in this repository should be:

* concise enough to use as a quick reference;
* based primarily on concepts that have been encountered and practiced;
* based on knowledge that can be understood, explained, and applied;
* written in English;
* organized so that each topic has one primary location;
* updated when workflows or understanding change;
* supported by practical examples where useful.

The handbook should document reusable knowledge rather than duplicate complete
books, courses, or external documentation.

## Development Approach

This handbook grows from practical study and development work.

New documentation should represent knowledge that has been encountered,
understood, and considered useful enough to retain for future reference.

```text id="3cw3ko"
Lesson / development work
        ↓
What did I actually learn?
        ↓
Can I explain it myself?
        ↓
Is it reusable technical knowledge?
       / \
     no   yes
     ↓     ↓
   skip   Does it already exist?
              / \
            yes  no
             ↓    ↓
          update  add
              \  /
               ↓
        developer-handbook
```

### Knowledge Before Documentation

The handbook is not intended to collect information simply because it is
available.

Before technical information is added, I should be able to understand and
explain the underlying concept. When I encounter something I do not yet
understand, the preferred approach is to investigate it until I can explain
the concept rather than documenting it without understanding it.

The goal is therefore not:

```text id="j94n63"
Find information → store information
```

but:

```text id="1knppg"
Learn → understand → apply → document → reuse
```

Documentation can also expose gaps in understanding. If I cannot clearly
explain a concept, that is a signal that further study or practice may be
needed.

### AI-Assisted Learning and Documentation

AI tools may be used to support the development of this handbook, including:

* explaining unfamiliar concepts;
* reviewing technical accuracy;
* improving structure and clarity;
* reviewing English technical writing;
* identifying missing information;
* assisting with repetitive documentation work.

AI-generated or AI-assisted material should not be accepted automatically.

Technical content should be read, evaluated, and understood before it becomes
part of the handbook. When a concept is not understood, the objective is to
study the underlying concept rather than simply preserve the generated
explanation.

As my technical knowledge and technical writing skills develop, the objective
is to increasingly produce initial explanations independently and use AI
primarily for review, feedback, and refinement.

### Independent Technical Writing Workflow

The handbook also serves as a place to practice technical writing in English.

For selected concepts encountered during study, the initial explanation should
be written independently before using AI for feedback or review.

```text id="wbmt35"
Technical concept from current study
        ↓
Write the explanation independently in English
        ↓
Review the first draft
        ↓
Check:
- technical accuracy
- grammar
- terminology
- structure
        ↓
Request AI feedback
        ↓
Revise independently
        ↓
Verify the final explanation
        ↓
Commit
```

The purpose of this workflow is not only to produce good documentation, but
also to develop the ability to explain technical concepts clearly without
relying on generated text.

### AI Assistance Progression

AI assistance should gradually shift from content generation toward review as
technical knowledge and writing ability improve.

```text id="55kb5b"
Phase 1 — Assisted Documentation

AI drafts
    ↓
Analyze
    ↓
Verify understanding
    ↓
Validate and edit


Phase 2 — Independent Drafting

Write independently
    ↓
AI provides detailed review
    ↓
Revise independently


Phase 3 — Independent Revision

Write independently
    ↓
Review independently
    ↓
AI identifies remaining problems
    ↓
Correct independently


Phase 4 — Final Review Only

Write independently
    ↓
Review independently
    ↓
AI performs final technical/language review
    ↓
Commit
```

Progression between phases is based on demonstrated ability rather than a fixed
calendar.

The long-term objective is not to eliminate useful development tools, but to
ensure that they augment technical ability rather than substitute for it.

### Principle

The value of this handbook is not determined by whether every sentence was
written without assistance.

Its value depends on whether the documented knowledge is understood, can be
explained, and can be applied in practice.
