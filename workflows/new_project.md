# New Project Workflow

## Structuur

1. Kies een duidelijke repositorynaam.
2. Gebruik lowercase met dashes.

Voorbeeld:

```
stock-analyzer
```

## Lokaal

Maak een projectmap.

Initialiseer git

```powershell
git init
```

Maak een README.

## GitHub

- Nieuwe repository
- Public
- Geen README toevoegen als die lokaal al bestaat.
- MIT License indien geschikt.

## Eerste commit

```powershell
git init
git add .
git commit -m "Initial commit"
git remote add origin ...
git push -u origin main
```

## Eerste bestanden

README.md

.gitignore (indien nodig)

src/

docs/
