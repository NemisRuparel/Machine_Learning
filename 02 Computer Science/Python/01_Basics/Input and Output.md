# Print function

The `print()` function is used to display output on the screen.

```python
print(object(s), sep=' ', end='\n', file=sys.stdout, flush=False)
```

- **`object(s)`**: Any object (strings, numbers, lists, etc.), and as many as you like. Python converts them into strings before displaying them.

- **`sep`** _(Optional)_: Specifies how to separate multiple objects. The default is a single space (`' '`).

- **`end`** _(Optional)_: Specifies what to print at the very end of the line. The default is a newline character (`'\n'`), which moves the cursor to the next line.

- **`file`** _(Optional)_: An object with a write method where the output is sent. The default is `sys.stdout` (your screen).

- **`flush=False` (Default):** The output is buffered (stored in memory temporarily) and usually only gets displayed when a newline character (`\n`) is encountered, when the program ends, or when the buffer fills up.

- **`flush=True`:** The output is pushed to the console or stream **instantly**, bypassing any memory buffering
## Example 

**Input:** 

```python
print("Hello World")
```

**Output:**

```text
Hello World
```

---

## Printing Multiple Values

Multiple values can be passed to `print()`.

```python
name = "Nemis"
age = 20

print(name, age)
```

**Output:**

```text
Nemis 20
```

---

## Input

The `input()` function is used to take input from the user.

```python
name = input("Enter your name: ")

print(name)
```

**Input:**

```text
Enter your name: Nemis
```

**Output:**

```text
Nemis
```

---

## Input as String

The `input()` function always returns the entered value as a **string**.

```python
age = input("Enter your age: ")

print(type(age))
```

**Input:**

```text
Enter your age: 20
```

**Output:**

```text
<class 'str'>
```

---

## Taking Integer Input

Use `int()` to convert the input into an integer.

```python
age = int(input("Enter your age: "))

print(age)
```

**Input:**

```text
Enter your age: 20
```

**Output:**

```text
20
```

---

## Taking Float Input

Use `float()` to convert the input into a floating-point number.

```python
price = float(input("Enter price: "))

print(price)
```

**Input:**

```text
Enter price: 99.50
```

**Output:**

```text
99.5
```

---

## Taking Multiple Inputs

Multiple values can be taken using `split()`.

```python
a, b = input("Enter two numbers: ").split()

print(a)
print(b)
```

**Input:**

```text
Enter two numbers: 10 20
```

**Output:**

```text
10
20
```

---

## Integer Multiple Inputs

```python
a, b = map(int, input("Enter two numbers: ").split())

print(a + b)
```

**Input:**

```text
Enter two numbers: 10 20
```

**Output:**

```text
30
```

---
