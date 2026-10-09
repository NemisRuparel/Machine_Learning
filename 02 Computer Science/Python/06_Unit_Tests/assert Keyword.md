#  `assert` Keyword

## 1. What is `assert`?

The `assert` keyword is used to test whether a condition is `True`.

- If the condition is `True`, the program continues normally.
    
- If the condition is `False`, Python raises an `AssertionError`.
    

### Syntax

```
assert condition
```

You can also provide a custom error message:

```
assert condition, "Error message"
```

---

## 2. Basic Example

```
age = 20

assert age >= 18

print("You are eligible.")
```

**Output:**

```
You are eligible.
```

The condition `age >= 18` is `True`, so the program continues.

---

## 3. AssertionError

When the condition is `False`, Python raises an `AssertionError`.

```
age = 15

assert age >= 18

print("You are eligible.")
```

**Output:**

```
Traceback (most recent call last):
  ...
AssertionError
```

The `print()` statement does not execute because the assertion fails.

---

## 4. Using a Custom Error Message

You can specify a message to explain why an assertion failed.

```
marks = 25

assert marks >= 35, "Student has failed the exam."

print("Student has passed the exam.")
```

**Output:**

```
Traceback (most recent call last):
  ...
AssertionError: Student has failed the exam.
```

The custom message helps identify the failed condition.

---

## 5. Using `assert` with Variables

Assertions can validate assumptions about variable values.

```
temperature = 25

assert temperature >= 0, "Temperature cannot be negative."

print("Temperature:", temperature)
```

**Output:**

```
Temperature: 25
```

---

## 6. Using `assert` in Functions

Assertions can check assumptions about function arguments or results during development.

```
def calculate_square(number):
    assert isinstance(number, (int, float)), "Number must be numeric."
    return number ** 2

print(calculate_square(5))
```

**Output:**

```
25
```

If the function receives a string, the assertion fails:

```
print(calculate_square("hello"))
```

**Output:**

```
AssertionError: Number must be numeric.
```

---

## 7. Important Limitation

Assertions are primarily intended for debugging and checking internal assumptions during development.

Python can disable assertions when running with optimization, such as:

```
python -O assert-keyword.py
```

Therefore, **do not use** `assert` **for essential input validation, authentication, security checks, or handling untrusted user input.** Use regular `if` statements and raise appropriate exceptions for those cases.

### Example: Essential Validation

```
age = -5

if age < 0:
    raise ValueError("Age cannot be negative.")

print("Age:", age)
```

**Output:**

```
ValueError: Age cannot be negative.
```

Unlike assertions, this validation is not removed by Python's optimization mode.

---

## 8. `assert` vs. `if`

| `assert`                                             | `if`                                               |
| ---------------------------------------------------- | -------------------------------------------------- |
| Checks assumptions during development.               | Implements conditional logic and validation.       |
| Raises `AssertionError` when the condition is false. | Can execute custom code when a condition is false. |
| Can be disabled with optimization.                   | Is not disabled by optimization.                   |
| Not suitable for essential validation.               | Suitable for essential validation.                 |

---

## 9. Key Points

- `assert` checks whether a condition is `True`.
    
- A failed assertion raises `AssertionError`.
    
- A custom message can be added after a comma.
    
- Assertions are useful for debugging and testing assumptions.
    
- Assertions may be disabled when Python runs in optimization mode.
    
- Never rely on assertions for essential validation or security checks.