# Java Basics

This document contains basic Java syntax and programming concepts encountered during Java study and practice.

## Basic program structure

A simple Java program can look like this:

```java
public class MyFirstApp {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

A Java application is organized into classes.

The entry point of a basic Java application is:

```java
public static void main(String[] args)
```

Execution starts in the `main()` method.

## Statements

Java statements generally end with a semicolon:

```java
System.out.println("Hello, Java!");
```

Forgetting the semicolon where one is required results in a compilation error.

## Variables

Variables store values that can be used and changed by a program.

Java requires the variable type to be declared.

Example:

```java
int bottles = 10;
String word = "bottles";
```

Here:

* `int` is the type for an integer value.
* `String` is the type for text.
* `bottles` and `word` are variable names.

Values can later be reassigned:

```java
bottles = 9;
word = "bottle";
```

## Conditional statements

An `if` statement executes code only when its condition evaluates to `true`.

```java
if (bottles == 1) {
    word = "bottle";
}
```

An `if`/`else` structure can choose between two alternatives:

```java
if (bottles == 1) {
    word = "bottle";
} else {
    word = "bottles";
}
```

## Comparison operators

Comparison operators can be used inside conditions.

Examples:

```text
==    equal to
!=    not equal to
<     less than
>     greater than
<=    less than or equal to
>=    greater than or equal to
```

Example:

```java
if (bottles > 0) {
    System.out.println("There are bottles on the wall.");
}
```

## While loops

A `while` loop repeats code as long as its condition remains `true`.

```java
int bottles = 3;

while (bottles > 0) {
    System.out.println(bottles + " bottles");
    bottles = bottles - 1;
}
```

The condition is checked before every iteration.

A variable used in the condition must eventually change if the loop is supposed to terminate.

Otherwise, the program can create an infinite loop.

## Printing output

Use:

```java
System.out.println("Hello");
```

to print a line to the console.

Variables and strings can be combined using `+`:

```java
System.out.println(bottles + " " + word);
```

For example, if:

```java
int bottles = 1;
String word = "bottle";
```

the output is:

```text
1 bottle
```

## Blocks

Curly braces define blocks of code:

```java
if (bottles > 0) {
    System.out.println("Still going.");
}
```

Blocks are used with constructs such as classes, methods, conditions, and loops.

Consistent indentation makes the structure easier to read.

## Case sensitivity

Java is case-sensitive.

For example:

```text
String
string
```

are not the same identifier.

The standard Java text type is:

```java
String
```

with a capital `S`.

## Basic mental model

For the programs covered so far:

```text
class
└── main()
    ├── declare variables
    ├── evaluate conditions
    ├── execute statements
    ├── repeat code with loops
    └── print output
```

More advanced Java concepts should be added to this handbook only after they are encountered and practiced.

## Related documentation

* `setup.md` — Java development environment
* `compilation.md` — compiling and running Java programs
