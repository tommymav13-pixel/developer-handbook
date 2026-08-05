# Create a new repository

Use this workflow when you start a project locally.

## Step 1

```powershell
mkdir my-project
cd my-project
```

## Step 2

```powershell
git init
```

## Step 3

Create your files.

## Step 4

```powershell
git add .
git commit -m "Initial commit"
```

## Step 5

Create an empty GitHub repository.

## Step 6

```powershell
git remote add origin https://github.com/USERNAME/my-project.git
git branch -M main
git push -u origin main
```