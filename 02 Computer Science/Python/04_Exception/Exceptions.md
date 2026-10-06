# Exceptions

An **exception** is an error that occurs while a Python program is running and interrupts the normal flow of the program.

When an exception occurs, Python creates an **exception object** containing information about the error.

---

## Example

```python
number = 10
result = number / 0
```

This produces:

```text
ZeroDivisionError: division by zero
```

The program stops because an exception occurred.

---

## Common Python Exceptions

| Exception | Meaning |
|---|---|
| `ZeroDivisionError` | Division or modulo by zero |
| `ValueError` | Invalid value |
| `TypeError` | Invalid operation between incompatible types |
| `NameError` | Name or variable is not defined |
| `IndexError` | Index is outside the valid range |
| `KeyError` | Dictionary key does not exist |
| `FileNotFoundError` | File does not exist |
| `AttributeError` | Object does not have the specified attribute |
| `ModuleNotFoundError` | Module cannot be found |

---

## Handling Exceptions

The `try` and `except` statements are used to handle exceptions.

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print(result)

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

If the user enters `0`, the exception is handled instead of stopping the program.

---

## `try`

The `try` block contains code that may cause an exception.

```python
try:
    result = 10 / 0
```

---

## `except`

The `except` block handles the exception.

```python
try:
    result = 10 / 0

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

**Output:**

```text
Cannot divide by zero.
```

---

## Handling Multiple Exceptions

Multiple `except` blocks can be used to handle different types of exceptions.

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except ValueError:
    print("Please enter a valid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

---

## `else`

The `else` block executes when no exception occurs.

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except ZeroDivisionError:
    print("Cannot divide by zero.")

else:
    print("Result:", result)
```

---

## `finally`

The `finally` block always executes, whether an exception occurs or not.

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except ZeroDivisionError:
    print("Cannot divide by zero.")

finally:
    print("Program finished.")
```

---

## Raising an Exception

The `raise` statement is used to manually generate an exception.

```python
age = -5

if age < 0:
    raise ValueError("Age cannot be negative")
```

**Output:**

```text
ValueError: Age cannot be negative
```

---

## Custom Exception

A custom exception can be created by defining a class that inherits from `Exception`.

```python
class AgeError(Exception):
    pass


age = 15

if age < 18:
    raise AgeError("Age must be 18 or above")
```

---

## Exception Handling Flow

```text
try
  ↓
Exception occurs?
  ↓
Yes → except
  ↓
else → runs only if no exception
  ↓
finally → always runs
```

---

## Key Points

- An exception occurs during program execution.
- `try` contains code that may cause an exception.
- `except` handles an exception.
- `else` runs when no exception occurs.
- `finally` always runs.
- `raise` is used to manually raise an exception.
- Different exceptions represent different types of errors.