# Daily workflow

## Waarom deze workflow?

Doelen:

- Terminalgebruik automatiseren.
- Git als standaard onderdeel van iedere programmeersessie.
- Altijd werken met de meest recente versie van een repository.
- Een consistente routine ontwikkelen.

## Start

1. Open PowerShell.
2. Ga naar de juiste repository.
3. Controleer de huidige locatie.

```powershell
pwd
dir
```

## PowerShell Functions

## Doel

Een consistente dagelijkse workflow om efficiënt tussen projecten te wisselen en
altijd met een actuele repository te werken.

### Gebruik

Python Crash Course:

```powershell
pcc
```

Developer Handbook:

```powershell
handbook
```

### Definitie

```powershell
function pcc {
    Set-Location "<Path to your programming folder>"
    git status
}

function handbook {
    Set-Location "<Path to your programming folder>"
    git status
}
```

Deze functies navigeren automatisch naar de juiste repository en voeren direct 
uit:

```powershell
git status
```

## Repository openen

Python Crash Course:

```powershell
pcc
git pull
code .
```

Developer Handbook:

```powershell
handbook
git pull
code .
```

## Nieuwe opdracht

### Nieuwe map (indien nodig)

```powershell
mkdir <project>\<chapter>\<exercise>
cd <project>\<chapter>\<exercise>
```

### Nieuw Python-bestand

```powershell
New-Item exercise.py -ItemType File
```

### Controle

```powershell
dir
```

### Bestand openen

```powershell
code exercise.py
```

of, wanneer de map nog niet geopend is:

```powershell
code .
```

## Tijdens het programmeren

- Programmeer.
- Test.
- Controleer wijzigingen.

```powershell
git status
git diff
```

## Afronden

```powershell
git status
git add .
git commit -m "Beschrijving van de wijziging"
git push
git status
```

De sessie is klaar wanneer `git status` meldt:

```
nothing to commit, working tree clean
```

## Bekijk geschiedenis:

```powershell
git log --oneline -5
```

Dan zie je direct je laatste vijf versies.