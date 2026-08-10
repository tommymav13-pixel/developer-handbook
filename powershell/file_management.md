# PowerShell File Management

This document contains common PowerShell commands for creating, inspecting, moving, copying, renaming, and deleting files and directories.

---

## Current Directory

Display the current location:

```powershell id="f48q2k"
Get-Location
```

Change directory:

```powershell id="0v7y2c"
Set-Location C:\Users\username\Documents
```

The commonly used alias is:

```powershell id="j9l2e4"
cd C:\Users\username\Documents
```

Move to the parent directory:

```powershell id="d3gk8n"
cd ..
```

---

## Create a Directory

Create a new directory:

```powershell id="k2m7qa"
New-Item -ItemType Directory -Path project-name
```

A shorter alternative is:

```powershell id="w8r1cf"
mkdir project-name
```

Example:

```powershell id="m5u9zp"
mkdir java
```

---

## Create a File

Create an empty file:

```powershell id="v3f7hx"
New-Item -ItemType File -Path README.md
```

Example:

```powershell id="q6p2sd"
New-Item -ItemType File -Path python\useful_patterns.md
```

---

## List Files and Directories

Display the contents of the current directory:

```powershell id="x4t8bn"
Get-ChildItem
```

Common alias:

```powershell id="c7y1kl"
dir
```

List contents recursively:

```powershell id="a9s5wj"
Get-ChildItem -Recurse
```

or:

```powershell id="p2h6mv"
dir -Recurse
```

---

## Show Hidden Items

Include hidden items:

```powershell id="e1n4rg"
Get-ChildItem -Force
```

This can be useful for inspecting hidden directories such as:

```text id="t6b3qy"
.git
```

---

## Directory Tree

Display a hierarchical directory structure:

```powershell id="r8v2fk"
tree
```

Include files:

```powershell id="z5m1dp"
tree /F
```

`tree` is a Windows command that can also be executed from PowerShell.

---

## Move a File

Move a file to another location:

```powershell id="g7k4sc"
Move-Item file.txt destination\
```

Example:

```powershell id="n1q9wb"
Move-Item notes.txt archive\
```

The same command can also be used to move directories.

---

## Copy a File

Copy a file:

```powershell id="u3d8hp"
Copy-Item file.txt destination\
```

Example:

```powershell id="l6f2xa"
Copy-Item README.md backup\
```

To copy a directory and its contents recursively:

```powershell id="b9r5vj"
Copy-Item source\ destination\ -Recurse
```

---

## Rename a File or Directory

Rename an item:

```powershell id="h4c7nm"
Rename-Item old_name.txt new_name.txt
```

Example:

```powershell id="s2k8qe"
Rename-Item old-project new-project
```

---

## Delete a File

Delete a file:

```powershell id="y5p1gz"
Remove-Item file.txt
```

Example:

```powershell id="f8w3kd"
Remove-Item temporary.txt
```

---

## Delete a Directory

Delete an empty directory:

```powershell id="m7v4br"
Remove-Item directory-name
```

Delete a directory and its contents recursively:

```powershell id="q1x6th"
Remove-Item directory-name -Recurse
```

Use recursive deletion carefully.

---

## Open Files with VS Code

Open a specific file:

```powershell id="d4n9yc"
code README.md
```

Open the current directory as a VS Code workspace:

```powershell id="k6s2wf"
code .
```

---

## Inspect Before Modifying

Before moving, renaming, or deleting multiple files, inspect the target items first.

For example:

```powershell id="a3j7pm"
Get-ChildItem
```

or:

```powershell id="v9h5rx"
Get-ChildItem -Recurse
```

This reduces the risk of modifying the wrong files.

A useful general workflow is:

```text id="c8q1zn"
Inspect
   ↓
Select
   ↓
Modify
   ↓
Verify
```

After making changes, inspect the directory again to confirm the result.

---

## Quick Reference

```text id="w2f8kg"
Get-Location                  Current directory
Set-Location                  Change directory
cd                            Change directory
New-Item                      Create file or directory
Get-ChildItem                 List items
dir                           Alias for Get-ChildItem
Get-ChildItem -Force          Include hidden items
Get-ChildItem -Recurse        List recursively
tree                          Display directory tree
tree /F                       Display tree including files
Move-Item                     Move item
Copy-Item                     Copy item
Rename-Item                   Rename item
Remove-Item                   Delete item
code .                        Open current directory in VS Code
```

---

## Related Documentation

* `basic_commands.md` — general PowerShell commands
* `aliases.md` — PowerShell aliases
* `file_selection_and_wildcards.md` — selecting files and using wildcards
