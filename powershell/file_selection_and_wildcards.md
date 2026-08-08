# File Selection and Wildcards in PowerShell

PowerShell provides several ways to work with files without manually typing
complete filenames.

This is especially useful when filenames are long or contain spaces.

## Tab completion

PowerShell can automatically complete filenames and paths.

Start typing part of a path:

```powershell
Move-Item .\_inbox\Fred
```

Then press `Tab`.

PowerShell attempts to complete the filename. Press `Tab` repeatedly to cycle
through possible matches.

Tab completion is useful when there is one clearly identifiable file.

## Wildcards

The `*` wildcard represents zero or more characters.

For example:

```powershell
Get-ChildItem .\_inbox\*Frederic*
```

This returns files whose names contain `Frederic`.

A more specific search can be used when multiple files match:

```powershell
Get-ChildItem ".\_inbox\*Frederic*2001*.pdf"
```

Wildcards make it unnecessary to manually type long filenames.

## Check before modifying

Before using a wildcard with a command that modifies files, first check which
files the wildcard selects.

For example:

```powershell
Get-ChildItem ".\_inbox\*Frederic*2001*.pdf"
```

If the result contains exactly the intended file, the same selection can be
used for another operation.

This is especially important with commands such as:

- `Move-Item`
- `Rename-Item`
- `Remove-Item`

Be particularly careful with `Remove-Item`, because a broad wildcard can
select and delete multiple files.

## Using the pipeline

`Get-ChildItem` can select a file and pass the resulting object to another
command through the pipeline (`|`).

Example:

```powershell
Get-ChildItem ".\_inbox\*Frederic*2001*.pdf" |
    Move-Item -Destination ".\pdf\non-fiction\sports-and-fitness\strength-training\frederic_delavier_strength_training_anatomy_2e.pdf"
```

The process is:

```text
Get-ChildItem
    ↓
find matching file
    ↓
|
    ↓
pass file object to Move-Item
    ↓
move and rename file
```

This avoids manually entering the complete original filename.

## Paths containing spaces

Paths or filenames containing spaces should be enclosed in quotes.

Example:

```powershell
Get-ChildItem ".\folder\Long File Name.pdf"
```

Without quotes, PowerShell may interpret parts of the filename as separate
arguments.

For example, a filename such as:

```text
Frederic Delavier - Strength Training Anatomy.pdf
```

should be referenced as:

```powershell
".\Frederic Delavier - Strength Training Anatomy.pdf"
```

## Moving and renaming simultaneously

`Move-Item` can move and rename a file in a single operation.

General pattern:

```powershell
Move-Item "source_path" "destination_path\new_filename.ext"
```

Example:

```powershell
Move-Item ".\_inbox\book.pdf" ".\pdf\non-fiction\subject\author_title_2e.pdf"
```

There is no need to run `Rename-Item` first when the final destination and
filename are already known.

## Practical workflow

When organizing files with long or inconsistent filenames, use the following
workflow:

```text
1. Search
2. Verify
3. Move or rename
4. Verify destination
```

For example:

```powershell
Get-ChildItem ".\_inbox\*keyword*"
```

Verify that the correct file is returned.

Then:

```powershell
Get-ChildItem ".\_inbox\*keyword*" |
    Move-Item -Destination ".\destination\new_filename.pdf"
```

Finally:

```powershell
Get-ChildItem ".\destination"
```

## General rule

Do not manually type a complete filename when a safer and more efficient
selection method is available.

Prefer:

- Tab completion for quickly completing known paths;
- wildcards for searching by partial filename;
- `Get-ChildItem` for verifying matches;
- the pipeline for passing selected files to other commands.

Always verify wildcard matches before modifying or deleting files.