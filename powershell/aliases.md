# Aliases

## Commando

Get-Alias

Toont alle beschikbare aliassen.

---

## Veelgebruikte aliassen

ls → Get-ChildItem

dir → Get-ChildItem

cd → Set-Location

pwd → Get-Location

mkdir → New-Item

---

## Waarom?

PowerShell gebruikt volledige cmdletnamen.

Aliassen maken dagelijks gebruik sneller.

Voor scripts gebruik je meestal de volledige cmdlets.

## Persoonlijke inzichten

- Ik oefen PowerShell bewust vanuit de terminal.
- Ik maak Python-bestanden via New-Item.
- Ik wil terminalgebruik automatiseren zodat ik minder afhankelijk ben van de 
muis.

# PowerShell Navigation Functions

## Purpose

Use small PowerShell functions to quickly navigate between frequently used projects.

---

## Python Crash Course

```powershell
function pcc {
    Set-Location "C:\Users\tommy\Documents\programming\python-crash-course-3e"
}
```

---

## Developer Handbook

```powershell
function handbook {
    Set-Location "C:\Users\tommy\Documents\programming\developer-handbook"
}
```

---

## Developer Portfolio

```powershell
function portfolio {
    Set-Location "C:\Users\tommy\Documents\programming\developer-portfolio"
}
```

---

## Reload the profile

```powershell
. $PROFILE
```

---

## Verify

```powershell
portfolio
pwd
```