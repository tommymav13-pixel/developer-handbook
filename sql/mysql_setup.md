# MySQL Setup

This document describes the basic MySQL development setup on Windows and common checks for verifying that the MySQL server is available.

## Current environment

* Operating system: Windows 11
* Shell: PowerShell
* Database system: MySQL 8.0
* Practice database: Sakila

## MySQL components

A basic local MySQL development environment consists of several components.

### MySQL Server

MySQL Server is the database server that stores and manages databases.

The server must be installed, configured, and running before applications or command-line clients can connect to it.

### MySQL client

The MySQL command-line client can be used to connect to a running MySQL server and execute SQL statements.

A typical installation contains the executable in a directory similar to:

```text id="q91kpa"
C:\Program Files\MySQL\MySQL Server 8.0\bin
```

## Verify the installation

Check whether the MySQL executable is available:

```powershell id="6d3ftg"
mysql --version
```

If the executable is not available through `PATH`, navigate directly to the MySQL `bin` directory:

```powershell id="md09qr"
cd "C:\Program Files\MySQL\MySQL Server 8.0\bin"
```

Then run:

```powershell id="vy1h7s"
.\mysql.exe --version
```

## Windows service

MySQL Server commonly runs as a Windows service.

List MySQL-related services with:

```powershell id="zfgmmj"
Get-Service *mysql*
```

Do not assume that the service is named `MySQL80`.

The actual service name depends on how MySQL was installed and configured.

Once the correct service name is known, its status can be inspected with:

```powershell id="h8bgjp"
Get-Service <service-name>
```

A service can be started with:

```powershell id="cc67qn"
Start-Service <service-name>
```

Administrative privileges may be required.

## Troubleshooting: service not found

A command such as:

```powershell id="84sg6n"
Get-Service MySQL80
```

may return an error indicating that no service with that name exists.

Similarly:

```powershell id="3m6g2o"
net start MySQL80
```

may report an invalid service name.

This does not necessarily mean that MySQL itself is broken.

Possible causes include:

* MySQL Server has not been fully configured.
* The Windows service was not created.
* The service uses a different name.
* Only some MySQL components were installed.

First inspect the available services:

```powershell id="fh4kyi"
Get-Service *mysql*
```

Then verify the MySQL installation and configuration rather than repeatedly trying an assumed service name.

## Connect to MySQL

Once the server is running, connect using the MySQL client.

For example:

```powershell id="e2vbds"
mysql -u root -p
```

The options mean:

```text id="p28nuc"
-u    username
-p    prompt for password
```

After pressing Enter, MySQL asks for the password separately.

Avoid placing passwords directly in commands or storing them in source code.

## Verify the connection

After connecting successfully, MySQL displays its command prompt:

```text id="9p5rwl"
mysql>
```

A simple check is:

```sql id="v0ipqy"
SHOW DATABASES;
```

This displays the databases available to the current user.

## Practice database: Sakila

Sakila is a sample database provided for learning and practicing MySQL.

After installation, verify that it is available:

```sql id="6khkm7"
SHOW DATABASES;
```

Select it with:

```sql id="kqd4yi"
USE sakila;
```

Then inspect its tables:

```sql id="wyc8dt"
SHOW TABLES;
```

Sakila can be used to practice querying a realistic relational database without creating an entire dataset manually.

## Security

Database credentials should not be committed to Git repositories.

Avoid storing passwords in:

* Markdown documentation
* source code
* configuration files tracked by Git
* shell scripts committed to a repository

Use secure credential management when credentials need to be stored.

## Troubleshooting checklist

If MySQL cannot be accessed:

1. Verify that MySQL Server is installed.
2. Check `mysql --version`.
3. Search for MySQL Windows services with `Get-Service *mysql*`.
4. Verify that the server service is running.
5. Check the username and connection settings.
6. Confirm that the correct password is being used.
7. Verify the installation/configuration with MySQL Installer if necessary.

## Related documentation

* `sql_basics.md` — basic SQL statements and relational database concepts
