# PowerShell Aliases

## Purpose

PowerShell aliases are short alternative names for cmdlets.

They are useful for fast interactive terminal use, while full cmdlet names are
generally preferred in scripts and documentation because they are more explicit.

---

## Inspect Aliases

Show all available aliases:

```powershell
Get-Alias
```

Find the command behind a specific alias:

```powershell
Get-Alias dir
Get-Alias ls
Get-Alias start
```

Find aliases for a cmdlet:

```powershell
Get-Alias -Definition Get-ChildItem
```

For example:

```powershell
Get-Alias -Definition Get-ChildItem
```

Common results include:

```text
dir
gci
ls
```

---

## Frequently Used Aliases

| Alias | Command | Purpose |
| --- | --- | --- |
| `dir` | `Get-ChildItem` | List files and directories |
| `gci` | `Get-ChildItem` | List files and directories |
| `ls` | `Get-ChildItem` | List files and directories |
| `cd` | `Set-Location` | Change the current directory |
| `pwd` | `Get-Location` | Show the current directory |
| `start` | `Start-Process` | Start a process or open a file |
| `cat` | `Get-Content` | Display file contents |
| `cp` | `Copy-Item` | Copy an item |
| `mv` | `Move-Item` | Move an item |
| `rm` | `Remove-Item` | Remove an item |
| `rni` | `Rename-Item` | Rename an item |
| `clear` | `Clear-Host` | Clear the terminal |
| `cls` | `Clear-Host` | Clear the terminal |

---

## Start-Process

`Start-Process` starts a process or opens a file using its associated
application.

Example:

```powershell
Start-Process file.pdf
```

The commonly used alias is:

```powershell
start file.pdf
```

Examples:

```powershell
start .
start .\book.pdf
start https://github.com
```

`start .` opens the current directory in File Explorer.

---

## Aliases in Pipelines

Aliases can also be used inside pipelines.

Full cmdlet version:

```powershell
Get-ChildItem ".\_inbox\*Darwin*" |
    Move-Item -Destination ".\pdf\non-fiction\science\biology\evolution"
```

Short interactive version:

```powershell
gci ".\_inbox\*Darwin*" |
    mv -Destination ".\pdf\non-fiction\science\biology\evolution"
```

The full version is generally clearer in scripts and documentation.

---

## Convention

Use aliases primarily for:

- interactive terminal work;
- quick navigation;
- exploratory commands.

Prefer full cmdlet names for:

- scripts;
- reusable functions;
- Developer Handbook examples;
- commands where readability matters.

Example:

```powershell
Get-ChildItem -Recurse
```

instead of:

```powershell
dir -Recurse
```

Both work, but the first makes the underlying PowerShell command explicit.

---

## Personal Workflow

Aliases I currently use frequently:

```powershell
dir
cd
pwd
start
```

I increasingly use full cmdlet names when working with pipelines:

```powershell
Get-ChildItem
Move-Item
Rename-Item
Remove-Item
```

This makes it easier to understand which PowerShell objects and commands are
being used.

---

## Note About `mkdir`

`mkdir` is commonly used to create directories in PowerShell.

Example:

```powershell
mkdir new-folder
```

However, `mkdir` is not simply an alias in the same way that `dir` is an alias
for `Get-ChildItem`.

For documentation and scripts, prefer the explicit form:

```powershell
New-Item -ItemType Directory new-folder
```

---

## Custom Navigation Functions

Custom navigation functions such as:

```powershell
function pcc {
    Set-Location "C:\Users\tommy\Documents\programming\python-crash-course-3e"
}
```

are not aliases.

They are user-defined PowerShell functions and belong in the PowerShell
profile.

Examples include:

```powershell
function pcc {
    Set-Location "C:\Users\tommy\Documents\programming\python-crash-course-3e"
}

function handbook {
    Set-Location "C:\Users\tommy\Documents\programming\developer-handbook"
}

function portfolio {
    Set-Location "C:\Users\tommy\Documents\programming\developer-portfolio"
}
```

These functions should be documented separately, for example in:

```text
powershell/profile.md
```

Useful profile commands include:

```powershell
$PROFILE
notepad $PROFILE
. $PROFILE
```

The final command reloads the current PowerShell profile without restarting the
terminal.