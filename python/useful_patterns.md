# Useful Python Patterns

This document contains reusable Python patterns encountered during study and practice.

The purpose is not to document all Python syntax, but to collect patterns that are useful across different programs.

## Looping through a list

Use a `for` loop to process each item in a list:

```python id="j0eq4w"
names = ["Alice", "Bob", "Charlie"]

for name in names:
    print(name)
```

The loop variable `name` refers to one item at a time.

## Looping through a dictionary

A dictionary stores key-value pairs.

```python id="9g8kfo"
person = {
    "first_name": "John",
    "last_name": "Doe",
    "age": 30,
}
```

Loop through both keys and values with `.items()`:

```python id="a92z8q"
for key, value in person.items():
    print(f"{key}: {value}")
```

Loop through only the keys:

```python id="d15r3w"
for key in person:
    print(key)
```

or explicitly:

```python id="u58pxe"
for key in person.keys():
    print(key)
```

Loop through only the values:

```python id="bg94tk"
for value in person.values():
    print(value)
```

## Storing dictionaries in a list

Multiple related dictionaries can be stored inside a list.

```python id="10aj7k"
person_01 = {
    "first_name": "John",
    "last_name": "Doe",
    "age": 30,
}

person_02 = {
    "first_name": "Jack",
    "last_name": "Black",
    "age": 34,
}

people = [person_01, person_02]
```

Each element of `people` is now a dictionary.

Loop through them with:

```python id="s0m95l"
for person in people:
    print(person["first_name"])
    print(person["last_name"])
    print(person["age"])
```

### Important distinction

These are not equivalent:

```python id="55xdpt"
people = [person_01, person_02]
```

and:

```python id="npdyo9"
people = ["person_01", "person_02"]
```

The first list contains references to dictionaries.

The second list contains strings.

Therefore:

```python id="vj7c4e"
people[0]["first_name"]
```

works when `people[0]` is a dictionary, but not when `people[0]` is the string `"person_01"`.

## Choosing meaningful loop variables

The loop variable represents the current item being processed.

For example:

```python id="al4d9k"
for person in people:
    print(person["first_name"])
```

Here:

```text id="7kw1zr"
people  -> collection of people
person  -> one person from that collection
```

Using singular and plural names can make loops easier to understand.

Other examples:

```python id="07c69r"
for city in cities:
    ...

for user in users:
    ...

for alien in aliens:
    ...
```

## While loops

A `while` loop repeats as long as a condition remains `True`.

```python id="5ry2fc"
number = 1

while number <= 5:
    print(number)
    number += 1
```

The variable involved in the condition must normally change during the loop.

Otherwise, the loop may continue indefinitely.

## User input

Use `input()` to request information from the user:

```python id="21lmqw"
name = input("What is your name? ")

print(f"Hello, {name}!")
```

`input()` returns a string.

For numerical input, explicit conversion may be required:

```python id="jwe76t"
age = int(input("How old are you? "))
```

## Combining input with a while loop

`input()` and `while` can be combined to create interactive programs.

```python id="l0qexk"
message = ""

while message != "quit":
    message = input("Enter a message: ")

    if message != "quit":
        print(message)
```

This pattern allows a program to continue accepting input until a specific condition is met.

## General principle

Before writing a loop, identify:

1. What collection or condition controls the loop?
2. What does the loop variable represent?
3. What should happen during each iteration?
4. What causes the loop to stop?

Clear answers to these questions make loops easier to design and debug.
