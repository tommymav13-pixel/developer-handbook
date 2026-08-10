# PEP 8

## Purpose

PEP 8 is the official style guide for Python code.

Its purpose is to promote consistent and readable Python code.

---

## Indentation

* Use 4 spaces per indentation level.
* Do not use tabs for indentation.
* Keep indentation consistent throughout the codebase.

Example:

```python id="1p26nk"
if age >= 18:
    print("Adult")
```

---

## Line Length

PEP 8 recommends:

* a maximum of 79 characters for code;
* a maximum of 72 characters for long comments and docstrings.

VS Code is configured with a ruler at column 80 as a visual guideline.

---

## Naming Conventions

Use standard Python naming conventions:

```text id="qcv70a"
variables     snake_case
functions     snake_case
classes       PascalCase
constants     UPPER_CASE_WITH_UNDERSCORES
```

Examples:

```python id="2lf6az"
user_name = "Tom"
maximum_attempts = 3

def calculate_total():
    pass


class UserAccount:
    pass


MAX_CONNECTIONS = 10
```

Choose descriptive names that clearly communicate the purpose of a variable, function, or class.

---

## Whitespace

Use spaces around operators:

```python id="78hs4b"
age = 30
total = price + tax
```

Avoid:

```python id="s3ynkh"
age=30
total=price+tax
```

Do not add unnecessary spaces immediately inside parentheses:

```python id="05klsv"
print(name)
```

Avoid:

```python id="ks89pa"
print( name )
```

---

## Blank Lines

Use blank lines to organize code into logical sections.

In small scripts, blank lines can be used to visually separate different steps of a program.

Avoid excessive use of blank lines.

---

## Readability

Readability is more important than making code as compact as possible.

Code is often read more frequently than it is written. Write code so that its purpose remains understandable when revisiting it later.

When following a PEP 8 recommendation would reduce readability, there may be a valid reason to deviate from it.

---

## Personal VS Code Settings

For Python development:

* indentation: 4 spaces;
* tabs are avoided;
* Format on Save is enabled;
* ruler at column 80.

The ruler is a visual guideline. The recommended maximum line length for Python code according to PEP 8 is 79 characters.
