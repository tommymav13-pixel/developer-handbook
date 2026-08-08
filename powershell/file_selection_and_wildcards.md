# File Selection and Wildcards in PowerShell

PowerShell provides several ways to select and manipulate files without
manually typing complete filenames.

This is especially useful when working with:

- long filenames;
- inconsistent filenames;
- files containing spaces;
- large directories;
- files that need to be renamed and reorganized.

## Tab completion

PowerShell can automatically complete filenames and paths.

Start typing part of a path:

```powershell
Get-ChildItem .\_inbox\Fish
```

Then press `Tab`.

PowerShell attempts to complete the filename or path. Press `Tab` repeatedly
to cycle through possible matches.

Tab completion is useful when the beginning of the filename is already known.

## Wildcards

The `*` wildcard represents zero or more characters.

Instead of typing a complete filename such as:

```text
Fisher, Ronald Aylmer - The design of experiments-Hafner Publishing Company (1966).pdf
```

search for a recognizable part of the filename:

```powershell
Get-ChildItem ".\_inbox\*Fisher*"
```

A more specific pattern can be used when necessary:

```powershell
Get-ChildItem ".\_inbox\*Fisher*design*experiments*.pdf"
```

This makes it unnecessary to manually reproduce long or inconsistent
filenames.

## Check before modifying

Before using a wildcard with a command that modifies files, first check which
files the wildcard selects.

For example:

```powershell
Get-ChildItem ".\_inbox\*Fisher*"
```

If the output contains exactly the intended file, the same selection can be
used for another operation.

This is particularly important with:

- `Move-Item`;
- `Rename-Item`;
- `Remove-Item`.

Be especially careful with `Remove-Item`. A broad wildcard can select multiple
files.

A useful workflow is:

```text
search
    ↓
inspect matches
    ↓
modify
    ↓
verify result
```

## Using the pipeline

`Get-ChildItem` returns filesystem objects.

These objects can be passed directly to another PowerShell command through the
pipeline operator (`|`).

For example:

```powershell
Get-ChildItem ".\_inbox\*Fisher*design*experiments*.pdf" |
    Move-Item -Destination ".\pdf\non-fiction\mathematics\statistics\ronald_fisher_the_design_of_experiments.pdf"
```

The operation can be understood as:

```text
Get-ChildItem
    ↓
find matching file
    ↓
|
    ↓
pass FileInfo object
    ↓
Move-Item
    ↓
move and rename file
```

The complete original filename does not need to be entered manually.

## Paths containing spaces

Paths and filenames containing spaces should be enclosed in quotation marks.

For example:

```powershell
Get-ChildItem ".\_inbox\Fisher, Ronald Aylmer - The design of experiments-Hafner Publishing Company (1966).pdf"
```

Without quotation marks, PowerShell can interpret parts of the filename as
separate arguments.

Using wildcards often makes the command considerably shorter:

```powershell
Get-ChildItem ".\_inbox\*Fisher*"
```

## Relative paths

Relative paths are resolved from the current working directory.

The current directory can be displayed with:

```powershell
Get-Location
```

or:

```powershell
pwd
```

The notation:

```text
.\
```

means:

```text
current directory
```

For example, when the current directory is:

```text
C:\Users\tommy\Documents\books
```

this path:

```powershell
.\_inbox\
```

refers to:

```text
C:\Users\tommy\Documents\books\_inbox\
```

and:

```powershell
.\pdf\non-fiction\mathematics\statistics\
```

refers to:

```text
C:\Users\tommy\Documents\books\pdf\non-fiction\mathematics\statistics\
```

A relative path does not automatically search other directories for a matching
folder name.

## Moving and renaming simultaneously

`Move-Item` can move and rename a file in a single operation.

General syntax:

```powershell
Move-Item "source" "destination\new_filename.ext"
```

For example:

```powershell
Move-Item ".\_inbox\book.pdf" `
    ".\pdf\non-fiction\mathematics\statistics\author_title.pdf"
```

There is no need to run `Rename-Item` separately when both the final directory
and final filename are already known.

The same operation can be combined with file selection:

```powershell
Get-ChildItem ".\_inbox\*Fisher*design*experiments*.pdf" |
    Move-Item -Destination ".\pdf\non-fiction\mathematics\statistics\ronald_fisher_the_design_of_experiments.pdf"
```

## Verify the destination

After moving a file, verify that it exists at the expected destination.

For example:

```powershell
Get-ChildItem ".\pdf\non-fiction\mathematics\statistics\*Fisher*"
```

Or inspect the entire directory:

```powershell
Get-ChildItem ".\pdf\non-fiction\mathematics\statistics\"
```

This creates a simple verification cycle:

```text
select
→ verify selection
→ modify
→ verify destination
```

## Practical workflow

When organizing files with long or inconsistent filenames:

### 1. Find the file

```powershell
Get-ChildItem ".\_inbox\*Fisher*"
```

### 2. Verify the match

Confirm that the output contains the intended file.

### 3. Move and rename

```powershell
Get-ChildItem ".\_inbox\*Fisher*design*experiments*.pdf" |
    Move-Item -Destination ".\pdf\non-fiction\mathematics\statistics\ronald_fisher_the_design_of_experiments.pdf"
```

### 4. Verify the result

```powershell
Get-ChildItem ".\pdf\non-fiction\mathematics\statistics\*Fisher*"
```

## Safety rule

Never assume that a wildcard selects only one file.

Before performing a destructive or modifying operation, inspect the selection:

```powershell
Get-ChildItem ".\path\*pattern*"
```

Only after verifying the result should the same pattern be used with commands
such as:

```powershell
Move-Item
Rename-Item
Remove-Item
```

## General rule

Do not manually type a complete filename when a safer and more efficient
selection method is available.

Prefer:

- Tab completion for completing known paths;
- wildcards for partial filename matching;
- `Get-ChildItem` for inspecting selections;
- the pipeline for passing filesystem objects between commands;
- `Move-Item` for moving and renaming in one operation;
- verification before and after modifying files.

The general pattern is:

```text
find → verify → modify → verify
```