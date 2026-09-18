# Input and Output

## Output

The `print()` function is used to display output on the screen.

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