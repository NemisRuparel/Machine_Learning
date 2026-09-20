# String Formatting

**String formatting** is used to insert values into a string and control how the output is displayed.

---

## String Concatenation

Strings can be joined using the `+` operator.

```python
name = "Nemis"
age = 19

print("My name is " + name + " and I am " + str(age) + " years old.")
```

**Output:**

```text
My name is Nemis and I am 20 years old.
```

---

## `format()` Method

The `format()` method is used to insert values into a string using `{}` placeholders.

```python
name = "Nemis"
age = 20

print("My name is {} and I am {} years old.".format(name, age))
```

**Output:**

```text
My name is Nemis and I am 20 years old.
```

---

# F-String

An **f-string** is a convenient way to insert variables and expressions directly into a string.

An f-string is created by placing `f` before the string.

```python
name = "Nemis"
age = 20

print(f"My name is {name} and I am {age} years old.")
```

**Output:**

```text
My name is Nemis and I am 20 years old.
```

---

## Expressions in F-Strings

Expressions can also be written inside `{}`.

```python
a = 10
b = 20

print(f"Sum = {a + b}")
```

**Output:**

```text
Sum = 30
```

---

## Formatting Numbers

F-strings can be used to control the number of decimal places.

```python
price = 99.5678

print(f"Price: {price:.2f}")
```

**Output:**

```text
Price: 99.57
```

`.2f` means to display the number with **2 decimal places**.

---

# String Methods

String methods are built-in methods used to perform operations on strings.

---

## `upper()`

Converts all characters to uppercase.

```python
text = "hello world"

print(text.upper())
```

**Output:**

```text
HELLO WORLD
```

---

## `lower()`

Converts all characters to lowercase.

```python
text = "HELLO WORLD"

print(text.lower())
```

**Output:**

```text
hello world
```

---

## `capitalize()`

Converts the first character to uppercase.

```python
text = "hello world"

print(text.capitalize())
```

**Output:**

```text
Hello world
```

---

## `title()`

Converts the first character of each word to uppercase.

```python
text = "hello world"

print(text.title())
```

**Output:**

```text
Hello World
```

---

## `strip()`

Removes leading and trailing whitespace.

```python
text = "   Hello World   "

print(text.strip())
```

**Output:**

```text
Hello World
```

---

## `replace()`

Replaces a part of a string with another value.

```python
text = "I like Java"

print(text.replace("Java", "Python"))
```

**Output:**

```text
I like Python
```

---

## `split()`

Splits a string into a list.

```python
text = "Python is easy"

print(text.split())
```

**Output:**

```text
['Python', 'is', 'easy']
```

---

## `join()`

Joins elements of a sequence into a string.

```python
words = ["Python", "is", "easy"]

print(" ".join(words))
```

**Output:**

```text
Python is easy
```

---

## `find()`

Returns the index of the first occurrence of a substring.

```python
text = "Python Programming"

print(text.find("Programming"))
```

**Output:**

```text
7
```

---

## `count()`

Returns the number of occurrences of a substring.

```python
text = "banana"

print(text.count("a"))
```

**Output:**

```text
3
```

---

## `startswith()`

Checks whether a string starts with a specified value.

```python
text = "Python Programming"

print(text.startswith("Python"))
```

**Output:**

```text
True
```

---

## `endswith()`

Checks whether a string ends with a specified value.

```python
text = "Python Programming"

print(text.endswith("Programming"))
```

**Output:**

```text
True
```

---

## Quick Reference

| Method | Purpose |
|---|---|
| `upper()` | Converts to uppercase |
| `lower()` | Converts to lowercase |
| `capitalize()` | Capitalizes the first character |
| `title()` | Capitalizes each word |
| `strip()` | Removes leading and trailing whitespace |
| `replace()` | Replaces part of a string |
| `split()` | Splits a string into a list |
| `join()` | Joins elements into a string |
| `find()` | Finds the position of a substring |
| `count()` | Counts occurrences |
| `startswith()` | Checks the starting text |
| `endswith()` | Checks the ending text |

---