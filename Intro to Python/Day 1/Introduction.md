# What is Python?

Python is a popular programming language created by Guido van Rossum and released in 1991. It is a versatile language used for various purposes, including:

- **Web Development (Server-side)**
- **Software Development**
- **Mathematics**
- **System Scripting**

## What can Python do?

Python is a versatile language that can perform a wide range of tasks:

- Create web applications on a server.
- Work alongside software to create workflows.
- Connect to database systems and read/modify files.
- Handle big data and perform complex mathematical operations.
- Support rapid prototyping and production-ready software development.

## Why Python?

Python is a popular choice for many reasons:

- It works on different platforms (Windows, Mac, Linux, Raspberry Pi, etc.).
- It has a simple syntax that resembles the English language.
- Python allows developers to write programs with fewer lines of code compared to some other programming languages.
- It operates on an interpreter system, allowing code to be executed as soon as it's written, making prototyping quick.
- Python can be used in procedural, object-oriented, or functional programming styles.

### Good to Know

- The most recent major version of Python is Python 3, which is used in this tutorial. Python 2 is still popular but is no longer updated except for security updates.

- Python can be written in a text editor, or you can use an Integrated Development Environment (IDE) such as Thonny, PyCharm, NetBeans, or Eclipse for managing larger collections of Python files.

## Python Syntax Compared to Other Languages

Python was designed for readability and has some unique characteristics:

- It uses new lines to complete a command, unlike languages that often use semicolons or parentheses.
- Python relies on indentation (whitespace) to define scope, such as the scope of loops, functions, and classes, while other languages often use curly braces for this purpose.

# Python Escape Sequences

In Python, escape sequences are special characters used to represent non-printable or special characters within a string. They are prefixed with a backslash (`\`). Here are some common Python escape sequences:

- **`\n`**: Newline
  - Inserts a new line character, causing text after it to start on a new line.

- **`\t`**: Tab
  - Inserts a horizontal tab character, often used to create an indentation.

- **`\\`**: Backslash
  - Inserts a literal backslash character.

- **`\'`**: Single Quote
  - Inserts a single quote character within a string defined with single quotes.

- **`\"`**: Double Quote
  - Inserts a double quote character within a string defined with double quotes.

- **`\r`**: Carriage Return
  - Represents a carriage return character.

- **`\b`**: Backspace
  - Represents a backspace character, typically moving the cursor back one position.

- **`\f`**: Formfeed
  - Represents a formfeed character, used to advance to the next page or section of text.

- **`\v`**: Vertical Tab
  - Represents a vertical tab character, often used for vertical alignment.

- **`\xhh`**: Hexadecimal Escape
  - Represents a character using its hexadecimal ASCII value, where `hh` is the two-digit hexadecimal value.

- **`\uhhhh` or `\Uhhhhhhhh`**: Unicode Escape
  - Represents a character using its Unicode code point, where `hhhh` is a four-digit or `hhhhhhhh` is an eight-digit hexadecimal value.

- **`\N{name}`**: Named Unicode Escape
  - Represents a character using its Unicode name.

## Examples:

```python
print("Hello\nWorld")  # Newline
print("This is a tab:\tTabbed Text")
print("Insert a backslash: \\")
print("She said, \"Hello!\"")
print("This is a carriage return.\rReturning...")
print("This is a\bBackspace")
print("This is a\fFormfeed")
print("This is a\vVertical Tab")
print("This is a Unicode character: \u03B1")  # Greek small letter alpha
print("This is a named Unicode character: \N{GREEK SMALL LETTER ALPHA}")
```
# Python Comments

Comments in Python are used to provide explanations and documentation within the code. They are ignored by the Python interpreter and are intended for human readers to understand the code.

## Single-Line Comments

Single-line comments are used for brief explanations on a single line. They are created using the `#` symbol, and any text following `#` on the same line is considered a comment.

```python
# This is a single-line comment
print("Hello, World")  # This is also a comment after code

