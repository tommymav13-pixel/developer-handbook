# PowerShell Basic Commands

## Purpose

This document contains the basic PowerShell commands used for navigation,
file management, inspecting the filesystem, and working with development
projects.

Full cmdlet names are preferred when learning, documenting, and writing
scripts. Aliases can be used for faster interactive terminal work.

---

## Navigation

### Show Current Location

```powershell
Get-Location
```

Common alias:

```powershell
pwd
```

Example:

```powershell
PS C:\Users\tommy\Documents> Get-Location
```

---

### Change Directory

```powershell
Set-Location path
```

Common alias:

```powershell
cd path
```

Examples:

```powershell
cd .\programming
cd ..
cd C:\Users\tommy\Documents
```

Useful path notation:

| Syntax | Meaning |
| --- | --- |
| `.` | Current directory |
| `..` | Parent directory |
| `.\folder` | Folder relative to current location |
| `C:\path` | Absolute path |

---

## Inspect Files and Directories

### Get-ChildItem

```powershell
Get-ChildItem
```

Lists files and directories in the current location.

Common aliases:

```powershell
dir
ls
gci
```

Examples:

```powershell
Get-ChildItem
Get-ChildItem .\_inbox
Get-ChildItem *.pdf
Get-ChildItem -File
Get-ChildItem -Directory
Get-ChildItem -Force
Get-ChildItem -Recurse
```

Search using a wildcard:

```powershell
Get-ChildItem ".\_inbox\*Darwin*"
```

Wildcards such as `*` are useful when the complete filename is not known.

---

## Create Files

### New-Item

```powershell
New-Item filename.txt
```

Alias:

```powershell
ni filename.txt
```

Create a Python file:

```powershell
New-Item example.py
```

Explicit form:

```powershell
New-Item -ItemType File example.py
```

---

## Create Directories

A directory can be created with:

```powershell
mkdir new-folder
```

The explicit PowerShell form is:

```powershell
New-Item -ItemType Directory new-folder
```

Example:

```powershell
New-Item -ItemType Directory quantum-mechanics
```

---

## Copy Items

### Copy-Item

```powershell
Copy-Item source destination
```

Example:

```powershell
Copy-Item .\example.py .\backup\
```

---

## Move Items

### Move-Item

```powershell
Move-Item source destination
```

Example:

```powershell
Move-Item .\book.pdf .\physics\
```

A pipeline can be used when selecting files dynamically:

```powershell
Get-ChildItem ".\_inbox\*Einstein*" |
    Move-Item -Destination ".\pdf\non-fiction\science\physics\relativity"
```

This separates:

1. selecting the file;
2. passing the resulting object through the pipeline;
3. moving the object to its destination.

---

## Rename Items

### Rename-Item

```powershell
Rename-Item old-name new-name
```

Example:

```powershell
Rename-Item `
    ".\Old Book Name.pdf" `
    "author_book_title.pdf"
```

It can also be combined with `Get-ChildItem`:

```powershell
Get-ChildItem "*Einstein*" |
    Rename-Item -NewName "albert_einstein_relativity.pdf"
```

This is useful when the original filename is long or inconvenient to type.

---

## Remove Items

### Remove-Item

```powershell
Remove-Item path
```

Example:

```powershell
Remove-Item .\old_file.txt
```

Use deletion commands carefully because they modify the filesystem.

Before deleting a file selected with wildcards, inspect the result first:

```powershell
Get-ChildItem "*duplicate*"
```

Then remove it only after confirming the selection.

---

## Directory Trees

Display a directory structure:

```powershell
tree
```

Include files:

```powershell
tree /F
```

This is useful for inspecting project and library structures.

---

## Open Files and Directories

### Start-Process

```powershell
Start-Process path
```

Common alias:

```powershell
start
```

Open the current directory in File Explorer:

```powershell
start .
```

Open a PDF:

```powershell
start .\book.pdf
```

---

## Visual Studio Code

Open the current directory:

```powershell
code .
```

Open a specific file:

```powershell
code example.py
```

Open the Developer Handbook:

```powershell
code C:\Users\tommy\Documents\programming\developer-handbook
```

---

## Discover Commands

### Get-Command

Show available PowerShell commands:

```powershell
Get-Command
```

Search for commands:

```powershell
Get-Command *Item*
```

Example:

```powershell
Get-Command *Process*
```

---

## Inspect Aliases

Show all aliases:

```powershell
Get-Alias
```

Inspect a specific alias:

```powershell
Get-Alias dir
```

Find aliases associated with a cmdlet:

```powershell
Get-Alias -Definition Get-ChildItem
```

Detailed alias documentation is maintained separately in:

```text
aliases.md
```

---

## Getting Help

PowerShell provides built-in documentation through `Get-Help`.

```powershell
Get-Help Get-ChildItem
```

Show examples:

```powershell
Get-Help Get-ChildItem -Examples
```

Show more detailed documentation:

```powershell
Get-Help Get-ChildItem -Detailed
```

This is useful when learning an unfamiliar cmdlet or parameter.

---

## Core Commands to Remember

| Cmdlet | Purpose |
| --- | --- |
| `Get-Location` | Show current location |
| `Set-Location` | Change location |
| `Get-ChildItem` | Inspect files and directories |
| `New-Item` | Create files or directories |
| `Copy-Item` | Copy files or directories |
| `Move-Item` | Move files or directories |
| `Rename-Item` | Rename files or directories |
| `Remove-Item` | Remove files or directories |
| `Start-Process` | Open files, directories, or processes |
| `Get-Command` | Discover commands |
| `Get-Alias` | Inspect aliases |
| `Get-Help` | Read PowerShell documentation |

---

## Current Working Pattern

A common filesystem workflow is:

```powershell
Get-ChildItem
```

Then narrow the selection:

```powershell
Get-ChildItem ".\_inbox\*Einstein*"
```

Verify that the correct item was selected.

Then perform the filesystem operation:

```powershell
Get-ChildItem ".\_inbox\*Einstein*" |
    Move-Item -Destination ".\pdf\non-fiction\science\physics\relativity"
```

The general pattern is:

```text
inspect → select → verify → modify
```

This reduces mistakes when working with files from the terminal.