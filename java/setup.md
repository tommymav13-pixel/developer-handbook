# Java Setup

This document describes the basic Java development setup used for local Java development on Windows.

## Current environment

* Operating system: Windows 11
* Shell: PowerShell
* Editor: Visual Studio Code
* JDK: Oracle JDK 25 LTS

## JDK and JRE

The Java Development Kit (JDK) contains the tools required to develop Java applications.

Important components include:

* `java` — runs Java programs
* `javac` — compiles Java source code
* Java runtime components required to execute compiled programs

For development, install a **JDK**, not only a runtime environment.

## Verify the installation

After installing the JDK, open PowerShell and run:

```powershell
java --version
```

Then verify that the Java compiler is available:

```powershell
javac --version
```

Example:

```text
java 25.0.4
javac 25.0.4
```

Both commands should point to compatible Java versions.

## PATH

Windows must be able to locate the Java executables.

If `java` or `javac` is not recognized, check whether the JDK `bin` directory is available through the system `PATH`.

A typical installation contains a directory similar to:

```text
C:\Program Files\Java\jdk-25\bin
```

After changing environment variables, restart PowerShell or Visual Studio Code before testing the commands again.

## Basic development check

Create a Java source file:

```text
MyFirstApp.java
```

Compile it with:

```powershell
javac MyFirstApp.java
```

A successful compilation creates:

```text
MyFirstApp.class
```

Run the compiled program with:

```powershell
java MyFirstApp
```

Do not include `.class` when running the program.

## Troubleshooting checklist

If Java does not run correctly:

1. Check `java --version`.
2. Check `javac --version`.
3. Verify that a JDK is installed.
4. Check the system `PATH`.
5. Restart the terminal after changing environment variables.
6. Confirm that the current directory contains the source or compiled file.

## Related documentation

* `compilation.md` — compiling and running Java programs
* `basics.md` — basic Java syntax and concepts
