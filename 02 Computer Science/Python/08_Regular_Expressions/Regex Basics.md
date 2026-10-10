# Python Regular Expressions (Regex Basics)

## 1. What is Regex?

**Regular expressions (Regex)** are patterns used to search, match, extract, split, and replace text.

Python provides the built-in `re` module for working with regular expressions.

### Common Use Cases

- Searching for specific words or patterns.
    
- Extracting numbers, emails, and other text.
    
- Validating input formats.
    
- Replacing text.
    
- Splitting strings using patterns.
	

---

## 2. Importing the `re` Module

```
import re
```

The `re` module is built into Python, so no installation is required.

---

## 3. Basic Regex Functions

|Function|Purpose|
|---|---|
|`re.search()`|Finds the first match anywhere in a string.|
|`re.match()`|Checks for a match at the beginning of a string.|
|`re.fullmatch()`|Checks whether the entire string matches a pattern.|
|`re.findall()`|Returns all non-overlapping matches as a list.|
|`re.finditer()`|Returns an iterator of match objects.|
|`re.sub()`|Replaces matching text.|
|`re.split()`|Splits text using a pattern.|

### Example: `re.search()`

```
import re

text = "Python is a programming language."

result = re.search("programming", text)

if result:
    print("Match found!")
```

**Output:**

```
Match found!
```

---

## 4. Common Regex Metacharacters

Metacharacters have special meanings in regex patterns.

| Pattern | Meaning                                         | Example                      |      |      |
| ------- | ----------------------------------------------- | ---------------------------- | ---- | ---- |
| `.`     | Any character except newline by default         | `a.c` matches `abc` or `a7c` |      |      |
| `^`     | Start of string                                 | `^Hello`                     |      |      |
| `$`     | End of string                                   | `world$`                     |      |      |
| `*`     | Zero or more repetitions                        | `ab*c`                       |      |      |
| `+`     | One or more repetitions                         | `ab+c`                       |      |      |
| `?`     | Zero or one repetition                          | `colou?r`                    |      |      |
| `{n}`   | Exactly `n` repetitions                         | `\d{3}`                      |      |      |
| `{n,m}` | Between `n` and `m` repetitions                 | `\d{2,4}`                    |      |      |
| `[]`    | Character class                                 | `[aeiou]`                    |      |      |
| `\`     | Escape character or start of a special sequence | `\.` matches a literal dot   |      |      |
| `       | `                                               | Alternation (OR)             | `cat | dog` |
| `()`    | Grouping                                        | `(ab)+`                      |      |      |

---

## 5. Common Character Classes

|Pattern|Meaning|
|---|---|
|`\d`|A digit; equivalent to `\D`'s opposite|
|`\D`|A non-digit|
|`\w`|A Unicode word character, generally letters, digits, and underscore|
|`\W`|A character that is not a word character|
|`\s`|Whitespace, such as spaces, tabs, and newlines|
|`\S`|A non-whitespace character|

### Example

```
import re

text = "Python 123"

print(re.findall(r"\d", text))
print(re.findall(r"\w+", text))
print(re.findall(r"\s", text))
```

**Output:**

```
['1', '2', '3']
['Python', '123']
[' ']
```

---

## 6. Using `re.findall()`

`re.findall()` returns all non-overlapping matches.

```
import re

text = "My marks are 85, 90, and 78."

numbers = re.findall(r"\d+", text)

print(numbers)
```

**Output:**

```
['85', '90', '78']
```

The pattern `\d+` matches one or more consecutive digits.

Note that the results are strings. Convert them to integers when needed:

```
marks = [int(value) for value in numbers]

print(marks)
```

**Output:**

```
[85, 90, 78]
```

---

## 7. Using `re.match()` and `re.fullmatch()`

### `re.match()`

Checks for a match at the beginning of a string.

```
import re

text = "Python programming"

result = re.match(r"Python", text)

print(result.group() if result else "No match")
```

**Output:**

```
Python
```

### `re.fullmatch()`

Checks whether the entire string matches the pattern.

```
import re

print(bool(re.fullmatch(r"\d+", "12345")))
print(bool(re.fullmatch(r"\d+", "123abc")))
```

**Output:**

```
True
False
```

Use `fullmatch()` when the whole input must follow a specified pattern.

---

## 8. Using `re.sub()`

`re.sub()` replaces every non-overlapping match by default.

```
import re

text = "Python 123 is easy 456"

result = re.sub(r"\d+", "#", text)

print(result)
```

**Output:**

```
Python # is easy #
```

---

## 9. Using `re.split()`

`re.split()` splits a string wherever the pattern matches.

```
import re

text = "apple,banana;orange mango"

result = re.split(r"[,;\s]+", text)

print(result)
```

**Output:**

```
['apple', 'banana', 'orange', 'mango']
```

The pattern splits on one or more commas, semicolons, or whitespace characters.

---

## 10. Using Raw Strings

Regex patterns often contain backslashes. Python raw strings, written with an `r` prefix, make these patterns easier to read.

```
pattern = r"\d+"
```

Prefer raw strings for regex patterns when practical. For example, `r"\d+"` clearly expresses the regex pattern for one or more digits.

---

## 11. Using Groups

Parentheses create capturing groups that allow you to extract parts of a match.

```
import re

text = "Date: 2026-10-10"

result = re.search(r"(\d{4})-(\d{2})-(\d{2})", text)

if result:
    print("Year:", result.group(1))
    print("Month:", result.group(2))
    print("Day:", result.group(3))
```

**Output:**

```
Year: 2026
Month: 10
Day: 10
```

- `group(0)` returns the entire match.
    
- `group(1)` returns the first capturing group.
    
- `group(2)` returns the second capturing group.
    

---

## 12. Using Regex Flags

Flags change how a pattern behaves.

|Flag|Purpose|
|---|---|
|`re.IGNORECASE` or `re.I`|Makes matching case-insensitive.|
|`re.MULTILINE` or `re.M`|Makes `^` and `$` work at line boundaries.|
|`re.DOTALL` or `re.S`|Allows `.` to match newline characters too.|

### Example

```
import re

text = "Python is GREAT"

result = re.search(r"great", text, re.IGNORECASE)

print(result.group() if result else "No match")
```

**Output:**

```
GREAT
```

---

## 13. Practical Example: Extract Email-Like Text

```
import re

text = "Contact us at support@example.com"

pattern = r"[\w.+-]+@[\w-]+(?:\.[\w-]+)+"

emails = re.findall(pattern, text)

print(emails)
```

**Output:**

```
['support@example.com']
```

This pattern extracts common email-like strings, but it is not a complete email-address validator. For production validation, use a purpose-built validation approach.

---

## 14. Key Points

- Regex patterns describe text-matching rules.
    
- Python's built-in `re` module provides regex functionality.
    
- Use raw strings such as `r"\d+"` for readable patterns.
    
- Use `search()` to find a match anywhere and `fullmatch()` to validate an entire string.
    
- Use `findall()` to collect matches, `sub()` to replace text, and `split()` to split text.
    
- Character classes and quantifiers help define matching rules.
    
- Capturing groups let you extract specific parts of a match.
    
- Regex can be powerful, but complicated patterns should be tested carefully.