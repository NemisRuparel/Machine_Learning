# Bugs

A **bug** is a mistake or defect in a Python program that causes it to produce incorrect results or behave unexpectedly.

## Types of Bugs

### 1. Syntax Bug

A syntax bug occurs when the Python code does not follow the correct syntax.

```python
print("Hello"
```

The closing `)` is missing.

Correct:

```python
print("Hello")
```

---

### 2. Logical Bug

A logical bug occurs when the program runs successfully but produces the wrong result.

```python
a = 10
b = 20

average = a + b / 2

print(average)
```

The intended calculation is:

```text
(10 + 20) / 2 = 15
```

But Python evaluates the expression as:

```text
10 + (20 / 2) = 20
```

Correct:

```python
average = (a + b) / 2
```

---

### 3. Runtime Bug

A runtime bug occurs while the program is executing and causes the program to stop unexpectedly.

Example:

```python
numbers = [10, 20, 30]

print(numbers[5])
```

The program tries to access an index that does not exist.

---

### 4. Semantic Bug

A semantic bug occurs when the code is syntactically valid but its meaning or implementation does not match what the programmer intended.

Example:

```python
age = 20

if age > 20:
    print("Adult")
```

If the intention is that someone aged **20 or above** should be considered an adult, the condition is incorrect.

Correct:

```python
if age >= 20:
    print("Adult")
```

---

## Common Python Bugs

### Incorrect Variable Name

```python
name = "Nemis"

print(nmae)
```

The variable was created as `name` but `nmae` was used later.

Correct:

```python
name = "Nemis"

print(name)
```

---

### Incorrect Operator

```python
marks = 75

if marks = 75:
    print("Good")
```

The assignment operator `=` is used instead of the comparison operator `==`.

Correct:

```python
if marks == 75:
    print("Good")
```

---

### Incorrect Loop Range

```python
for i in range(1, 5):
    print(i)
```

Output:

```text
1
2
3
4
```

If `5` is also intended, the range must be changed:

```python
for i in range(1, 6):
    print(i)
```

---

### Incorrect Calculation

```python
length = 10
width = 5

area = length + width
```

The formula for the area of a rectangle is:

```python
area = length * width
```

---

### Incorrect Indentation

```python
if age >= 18:
print("Adult")
```

Correct:

```python
if age >= 18:
    print("Adult")
```

---

## Debugging

**Debugging** is the process of finding, analyzing, and fixing bugs in a program.

A basic debugging process is:

1. Identify the unexpected behavior.
    
2. Find the part of the code causing the problem.
    
3. Determine why the code is behaving incorrectly.
    
4. Fix the code.
    
5. Test the program again.
    

### Example

Buggy code:

```python
a = 10
b = 20

result = a - b

print(result)
```

If the intention is to calculate the sum, the bug is in the operator.

Correct:

```python
result = a + b

print(result)
```

---

## Debugging Using `print()`

`print()` can be used to inspect values while finding a bug.

```python
a = 10
b = 20

print("a =", a)
print("b =", b)

result = a + b

print("result =", result)
```

This helps determine whether the variables contain the expected values.

---

## Bug vs Debugging

| Term             | Meaning                                                              |
| ---------------- | -------------------------------------------------------------------- |
| **Bug**          | A mistake or defect in a program                                     |
| **Debugging**    | The process of finding and fixing a bug                              |
| **Syntax Bug**   | Incorrect Python syntax                                              |
| **Logical Bug**  | Program runs but produces an incorrect result                        |
| **Runtime Bug**  | Problem occurs while the program is running                          |
| **Semantic Bug** | Code works syntactically but does not represent the intended meaning |
