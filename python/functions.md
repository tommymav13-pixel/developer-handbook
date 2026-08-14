# Python Functions

This document describes the basic use of functions in Python, including
parameters, arguments, docstrings, and passing lists to functions.

## Purpose

Functions are reusable blocks of code designed to perform a specific task.

Functions help to:

* avoid repeating code;
* divide programs into smaller logical components;
* improve readability;
* make code easier to maintain and test;
* separate different responsibilities within a program.

## Defining a Function

A function is defined using the `def` keyword.

```python
def greet_user():
    print("Hello!")
```

The function definition contains:

* the `def` keyword;
* the function name;
* parentheses `()`;
* a colon `:`;
* an indented function body.

Defining a function does not execute it.

## Calling a Function

A function is executed by calling it:

```python
greet_user()
```

The complete example is:

```python
def greet_user():
    print("Hello!")


greet_user()
```

Output:

```text
Hello!
```

## Parameters and Arguments

A function can receive information.

A **parameter** is a variable defined in the function definition:

```python
def greet_user(username):
    print(f"Hello, {username}!")
```

Here, `username` is a parameter.

An **argument** is the value passed to the function when it is called:

```python
greet_user("Tommy")
```

Here, `"Tommy"` is an argument.

The relationship is:

```text
Function definition
        ↓
parameter
        ↓
def greet_user(username)


Function call
        ↓
argument
        ↓
greet_user("Tommy")
```

## Multiple Parameters

A function can define multiple parameters:

```python
def describe_pet(animal_type, pet_name):
    print(f"I have a {animal_type}.")
    print(f"My {animal_type}'s name is {pet_name}.")
```

The function can then receive multiple arguments:

```python
describe_pet("cat", "Vimmer")
```

Each argument is associated with a parameter.

With positional arguments, their order matters:

```text
"cat"       → animal_type
"Vimmer"    → pet_name
```

## Docstrings

A docstring describes the purpose of a function.

```python
def greet_user(username):
    """Display a simple greeting."""
    print(f"Hello, {username}!")
```

A docstring is placed immediately after the function definition.

Docstrings help make functions easier to understand and document.

## Passing Lists to Functions

Lists can be passed to functions like other Python objects.

For example:

```python
def show_messages(messages):
    """Display each message in a list."""
    for message in messages:
        print(message)
```

Call the function with a list:

```python
messages = [
    "I love Python",
    "Java is fun!",
    "I wish to become a programmer!",
]

show_messages(messages)
```

The parameter `messages` refers to the list passed to the function.

## Modifying Lists in Functions

A function can modify a list that is passed to it.

For example:

```python
def send_messages(messages, sent_messages):
    """Send each message and move it to sent_messages."""
    while messages:
        current_message = messages.pop()
        print(f"Sending message: {current_message}")
        sent_messages.append(current_message)
```

The function:

1. receives two lists;
2. removes a message from `messages` using `pop()`;
3. stores that message in `current_message`;
4. appends the message to `sent_messages`;
5. repeats until `messages` is empty.

Example:

```python
messages = [
    "I love Python",
    "Java is fun!",
    "I wish to become a programmer!",
]

sent_messages = []

send_messages(messages, sent_messages)
```

Because `pop()` modifies the list passed to the function, the original
`messages` list becomes empty.

The process can be represented as:

```text
messages
    ↓
send_messages()
    ↓
pop()
    ↓
current_message
    ↓
append()
    ↓
sent_messages
```

## Preventing a Function from Modifying the Original List

Sometimes the original list should remain unchanged.

A copy can be passed to the function instead:

```python
send_messages(messages[:], sent_messages)
```

The slice:

```python
messages[:]
```

creates a shallow copy of the list.

The function can modify this new list without removing elements from the
original `messages` list.

Conceptually:

```text
messages
    │
    ├──────────────→ original list remains available
    │
    ↓
messages[:]
    ↓
shallow copy
    ↓
send_messages()
    ↓
pop()
    ↓
copy is modified
```

Compare:

```python
send_messages(messages, sent_messages)
```

with:

```python
send_messages(messages[:], sent_messages)
```

In the first case, the function operates on the original list.

In the second case, the function operates on a new list created by slicing.

## Separating Responsibilities

Different functions can be responsible for different tasks.

For example:

```python
def send_messages(messages, sent_messages):
    """Send each message and move it to sent_messages."""
    while messages:
        current_message = messages.pop()
        print(f"Sending message: {current_message}")
        sent_messages.append(current_message)


def show_sent_messages(sent_messages):
    """Show all the messages that were sent."""
    print("\nThe following messages have been sent:")

    for completed_message in sent_messages:
        print(completed_message)
```

Here:

```text
send_messages()
      ↓
processes and moves messages

show_sent_messages()
      ↓
displays completed messages
```

Keeping different responsibilities in separate functions makes the program
easier to understand and modify.

## Key Principles

* Define functions with `def`.
* Call a function by using its name followed by parentheses.
* Parameters are defined by the function.
* Arguments are supplied when the function is called.
* Functions can accept multiple parameters.
* Use docstrings to describe what functions do.
* Lists can be passed to functions.
* Functions can modify mutable objects such as lists.
* Pass a copy when the original list should remain unchanged.
* Use separate functions for logically separate responsibilities.

## Related Documentation

* `pep8.md` — Python style conventions
* `useful_patterns.md` — reusable Python programming patterns