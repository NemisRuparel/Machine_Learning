# Command-Line Arguments

**Command-line arguments** are values passed to a Python program when it is executed from a terminal.

They allow users to provide input without using the `input()` function inside the program.

Python provides the `sys` module to access command-line arguments.

---

## Using `sys.argv`

`sys.argv` is a list containing the command-line arguments passed to a Python script.

- `sys.argv[0]` → Name or path of the Python script.
- `sys.argv[1]` → First argument.
- `sys.argv[2]` → Second argument.
- And so on.

### Example

```python
import sys

print(sys.argv)
```

Run the program from the terminal:

```bash
python main.py Nemis 20
```

**Output:**

```text
['main.py', 'Nemis', '20']
```

The exact script path shown in `sys.argv[0]` can vary depending on how the program is executed.

---

## Accessing Individual Arguments

```python
import sys

name = sys.argv[1]
age = sys.argv[2]

print("Name:", name)
print("Age:", age)
```

Run:

```bash
python main.py Nemis 20
```

**Output:**

```text
Name: Nemis
Age: 20
```

---

## Command-Line Arguments Are Strings

All command-line arguments received through `sys.argv` are strings.

Convert them to the required data type when necessary.

```python
import sys

a = int(sys.argv[1])
b = int(sys.argv[2])

print("Sum:", a + b)
```

Run:

```bash
python main.py 10 20
```

**Output:**

```text
Sum: 30
```

---

## Checking the Number of Arguments

`len(sys.argv)` returns the number of elements in the argument list, including the script name.

```python
import sys

print("Number of arguments:", len(sys.argv))
```

Run:

```bash
python main.py Hello World
```

**Output:**

```text
Number of arguments: 3
```

There are three elements: the script name, `Hello`, and `World`.

---

## Using `argparse`

The `argparse` module provides a more structured way to handle command-line arguments. It supports named options, type conversion, help messages, and validation.

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument("name")
parser.add_argument("--age", type=int, default=18)

args = parser.parse_args()

print("Name:", args.name)
print("Age:", args.age)
```

Run:

```bash
python main.py Nemis --age 20
```

**Output:**

```text
Name: Nemis
Age: 20
```

To display the available options:

```bash
python main.py --help
```

---

## `input()` vs Command-Line Arguments

| `input()` | Command-Line Arguments |
|---|---|
| Takes input while the program is running | Receives input when the program starts |
| User types values when prompted | User supplies values in the terminal command |
| Returns a string | `sys.argv` values are strings |
| Uses the built-in `input()` function | Commonly uses `sys.argv` or `argparse` |

---

## Key Points

- Command-line arguments pass values to a program through the terminal.
- `sys.argv` stores the script name and supplied arguments.
- Arguments accessed through `sys.argv` are strings.
- `len(sys.argv)` counts the script name as well.
- `argparse` is useful for programs with named options and input validation.