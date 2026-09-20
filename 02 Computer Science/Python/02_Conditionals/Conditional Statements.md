# Conditional Statements

**Conditional statements** are used to make decisions in a Python program based on whether a condition is `True` or `False`.

Python provides:

- `if`
- `if-else`
- `if-elif-else`
- Nested `if`

---

## `if` Statement

The `if` statement executes a block of code when the given condition is `True`.

```python
age = 20

if age >= 18:
    print("You are an adult")
```

**Output:**

```text
You are an adult
```

---

## `if-else` Statement

The `else` block executes when the `if` condition is `False`.

```python
age = 16

if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")
```

**Output:**

```text
You are a minor
```

---

## `if-elif-else` Statement

The `elif` statement is used to check multiple conditions.

```python
marks = 75

if marks >= 90:
    print("Grade A")
elif marks >= 75:
    print("Grade B")
elif marks >= 50:
    print("Grade C")
else:
    print("Fail")
```

**Output:**

```text
Grade B
```

---

## Nested `if`

An `if` statement inside another `if` statement is called a **nested if**.

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
```

**Output:**

```text
Entry allowed
```

---

## Conditional Expression

A **conditional expression** is a short way of writing an `if-else` statement in a single line.

### Syntax

```python
value_if_true if condition else value_if_false
```

### Example

```python
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```

**Output:**

```text
Adult
```

---

## Multiple Conditions

Multiple conditions can be combined using logical operators such as `and`, `or`, and `not`.

```python
age = 20
has_id = True

if age >= 18 and has_id:
    print("Entry allowed")
```

**Output:**

```text
Entry allowed
```

---

## Example Program

```python
marks = int(input("Enter your marks: "))

if marks >= 90:
    print("Grade A")
elif marks >= 75:
    print("Grade B")
elif marks >= 50:
    print("Grade C")
else:
    print("Fail")
```

**Input:**

```text
Enter your marks: 82
```

**Output:**

```text
Grade B
```

---

## Summary

| Statement | Purpose |
|---|---|
| `if` | Executes code when a condition is `True` |
| `else` | Executes code when the condition is `False` |
| `elif` | Checks another condition |
| Nested `if` | `if` statement inside another `if` |
| Conditional Expression | Short one-line `if-else` |