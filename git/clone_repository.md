# Clone an existing GitHub repository

Use this workflow when the repository already exists on GitHub and you want a 
local copy.

## Example

Repository:

```
https://github.com/tommymav13-pixel/developer-portfolio.git
```

## Step 1

Go to the directory where you want the repository.

```powershell
cd C:\Users\tommy\Documents\programming
```

## Step 2

Clone the repository.

```powershell
git clone https://github.com/tommymav13-pixel/developer-portfolio.git
```

## Step 3

Open the repository.

```powershell
cd developer-portfolio
```

## Step 4

Verify everything is correct.

```powershell
git status
```

Expected output:

```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

---

## Why clone instead of git init?

Use **git clone** when the repository already exists on GitHub.

Advantages:

- Downloads the complete repository
- Automatically configures the remote (`origin`)
- Downloads the commit history
- Downloads the default branch
- Avoids unnecessary setup