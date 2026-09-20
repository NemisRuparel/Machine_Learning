# Match

The `match` statement is used to compare a value against multiple patterns.

It is similar to a `switch` statement found in some other programming languages.

The `match` statement was introduced in **Python 3.10**.

---

## Basic Syntax

```python
match value:
    case pattern1:
        # code
    case pattern2:
        # code
    case _:
        # default code
```

- `match` → starts the pattern matching
- `case` → defines a pattern to match
- `_` → matches anything and acts as a default case

---

## Example

```python
day = 2

match day:
    case 1:
        print("Monday")
    case 2:
        print("Tuesday")
    case 3:
        print("Wednesday")
    case _:
        print("Invalid day")
```

**Output:**

```text
Tuesday
```

---

## Default Case

The `_` pattern is used when none of the previous cases match.

```python
number = 10

match number:
    case 1:
        print("One")
    case 2:
        print("Two")
    case _:
        print("Other number")
```

**Output:**

```text
Other number
```

---

## Multiple Values in One Case

Multiple values can be matched using `|`.

```python
day = "Saturday"

match day:
    case "Saturday" | "Sunday":
        print("Weekend")
    case "Monday" | "Tuesday" | "Wednesday" | "Thursday" | "Friday":
        print("Weekday")
    case _:
        print("Invalid day")
```

**Output:**

```text
Weekend
```

---

## Match with Input

```python
choice = int(input("Enter a number: "))

match choice:
    case 1:
        print("Add")
    case 2:
        print("Subtract")
    case 3:
        print("Multiply")
    case 4:
        print("Divide")
    case _:
        print("Invalid choice")
```

---

## `if-elif` vs `match`

Use `if-elif` when you need to evaluate **conditions or ranges**.

```python
marks = 85

if marks >= 90:
    print("A")
elif marks >= 75:
    print("B")
else:
    print("C")
```

Use `match` when you want to compare a value against **specific patterns or values**.

```python
choice = 2

match choice:
    case 1:
        print("Add")
    case 2:
        print("Subtract")
    case _:
        print("Invalid choice")
```