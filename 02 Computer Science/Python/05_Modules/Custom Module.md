# Creating Own Libraries

A **library** is a collection of reusable code that can be used in different programs.

In Python, we can create our own reusable code using **modules and packages**.

- **Module:** A Python file (`.py`) containing functions, variables, or classes.
- **Package:** A directory containing related Python modules, commonly organized using an `__init__.py` file.

---

## Creating a Module

Create a Python file named `math_operations.py`.

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b
```

This file contains three reusable functions.

---

## Importing a Module

Create another file named `main.py` in the same directory.

```python
import math_operations

print(math_operations.add(10, 5))
print(math_operations.subtract(10, 5))
print(math_operations.multiply(10, 5))
```

**Output:**

```text
15
5
50
```

The `import` statement allows us to use functions defined in another Python module.

---

## Importing Specific Functions

We can import only the functions we need.

```python
from math_operations import add, multiply

print(add(10, 5))
print(multiply(10, 5))
```

**Output:**

```text
15
50
```

---

## Using an Alias

The `as` keyword gives a module or imported function a shorter name.

```python
import math_operations as mo

print(mo.add(10, 5))
```

**Output:**

```text
15
```

---

## Creating a Package

A package organizes multiple related modules inside a directory.

Example structure:

```text
my_library/
    __init__.py
    arithmetic.py
    greetings.py

main.py
```

### `arithmetic.py`

```python
def add(a, b):
    return a + b


def multiply(a, b):
    return a * b
```

### `greetings.py`

```python
def greet(name):
    return f"Hello, {name}!"
```

### `__init__.py`

This file can be empty. It marks the directory as a regular Python package and can also expose selected functions.

```python
from .arithmetic import add, multiply
from .greetings import greet
```

### `main.py`

```python
from my_library import add, multiply, greet

print(add(10, 5))
print(multiply(10, 5))
print(greet("Nemis"))
```

**Output:**

```text
15
50
Hello, Nemis!
```

---

## Importing a Module from a Package

We can import a module directly from a package.

```python
from my_library import arithmetic

print(arithmetic.add(10, 5))
```

**Output:**

```text
15
```

---

## Creating a Reusable Library

A well-organized library should:

- Contain reusable functions or classes.
- Use meaningful module and function names.
- Separate related functionality into modules.
- Include documentation where useful.
- Avoid executing unrelated code when imported.

---

## Module vs Package

| Module | Package |
|---|---|
| A single Python file | A directory organizing modules |
| Has a `.py` extension | Usually contains multiple modules |
| Example: `math_operations.py` | Example: `my_library/` |
| Imported using `import module_name` | Imported using package and module names |

---

## Important Points

- A Python file can act as a module.
- Use `import` to reuse code from another module.
- Use `from ... import ...` to import specific functions.
- Use `as` to create an alias.
- Packages help organize larger libraries.
- Your own modules can be reused across multiple Python programs.