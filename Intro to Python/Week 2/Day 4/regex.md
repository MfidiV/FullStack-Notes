# Regex

Regular expressions, often abbreviated as regex or regexp, are a powerful and flexible way to search, match, and manipulate text based on patterns. In Python, regular expressions are supported through the re module, which provides functions for working with regular expressions. Here's an introduction to Python regular expressions


Regular expressions (regex or regexp) are powerful tools for pattern matching and text manipulation. They provide a way to search, extract, and manipulate text based on patterns. Here's a brief introduction to regex.

## Basics of Regex

- **Literals**: Match literal characters, e.g., `a` matches the letter "a."

- **Metacharacters**: Special characters with predefined meanings, e.g., `.` (matches any character), `*` (matches zero or more), `+` (matches one or more), `()` (groups patterns).

- **Ranges**: Specify a range of characters inside square brackets, e.g., `[a-z]` matches lowercase letters.

- **Character Classes**: Match any character from a predefined class, e.g., `[0-9]` matches any digit.

## Common Metacharacters

- `.`: Matches any character except a newline.

- `*`: Matches zero or more occurrences of the preceding character.

- `+`: Matches one or more occurrences of the preceding character.

- `?`: Matches zero or one occurrence of the preceding character.

## Anchors

- `^`: Matches the start of a line.

- `$`: Matches the end of a line.

## Quantifiers

- `{m,n}`: Matches between m and n occurrences of the preceding character or group.

## Predefined Classes

- `\d`: Matches any digit (0-9).

- `\w`: Matches any word character (alphanumeric and underscore).

- `\s`: Matches any whitespace character.

## Flags

- `re.I` (or `re.IGNORECASE`): Makes pattern matching case-insensitive.

- `re.S` (or `re.DOTALL`): Allows the dot `.` to match any character, including a newline.

- `re.M` (or `re.MULTILINE`): Allows `^` and `$` to match the start/end of each line within multi-line text.

## Common Regex Use Cases

- Parsing: Identifying and extracting pieces of text that match certain criteria.

- Searching: Locating substrings based on a specific pattern.

- Searching and replacing: Finding and replacing specified words or patterns.

- Splitting strings: Dividing a string based on a delimiter or pattern.

- Validation: Checking whether data adheres to a specific format (e.g., email validation).

## Example of Email Validation

Here's an example of using regex to validate an email address:

```python
import re

def is_valid_email(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return bool(re.match(pattern, email))
