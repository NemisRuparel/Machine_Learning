A **loop** is used to execute a block of code repeatedly.

Python provides two main types of loops:

- `for` loop
- `while` loop

---

## `for` Loop

A `for` loop is used to iterate over a sequence or range of values.

```python
for i in range(1, 6):
    print(i)
```

**Output:**

```text
1
2
3
4
5
```

---

## For-Each Style Loop

Python does not have a separate `foreach` keyword.

The `for` loop can be used to iterate through each item of a sequence.

```python
languages = ["Python", "Java", "C++"]

for language in languages:
    print(language)
```

**Output:**

```text
Python
Java
C++
```

---

## `while` Loop

A `while` loop executes a block of code as long as the condition is `True`.

```python
i = 1

while i <= 5:
    print(i)
    i += 1
```

**Output:**

```text
1
2
3
4
5
```

---

## Do-While Loop

Python does **not** have a built-in `do-while` loop.

Do-while behavior can be implemented using `while True` and `break`.

A do-while loop executes the code at least once before checking the condition.

```python
while True:
    number = int(input("Enter a positive number: "))

    if number > 0:
        break
```

---

# Loop Control Statements

Loop control statements are used to change the normal execution of a loop.

Python provides:

- `break`
- `continue`
- `pass`

---

## `break`

The `break` statement immediately terminates the loop.

```python
for i in range(1, 6):
    if i == 3:
        break

    print(i)
```

**Output:**

```text
1
2
```

---

## `continue`

The `continue` statement skips the current iteration and moves to the next iteration.

```python
for i in range(1, 6):
    if i == 3:
        continue

    print(i)
```

**Output:**

```text
1
2
4
5
```

---

## `pass`

The `pass` statement does nothing.

It is used as a placeholder when a statement is required but no code needs to be executed yet.

```python
for i in range(5):
    pass
```

---

## Nested Loops

A loop inside another loop is called a **nested loop**.

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i, j)
```

**Output:**

```text
1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3
```

---

## Loop with `else`

Python allows an `else` block with `for` and `while` loops.

The `else` block executes when the loop finishes normally.

```python
for i in range(1, 4):
    print(i)
else:
    print("Loop completed")
```

**Output:**

```text
1
2
3
Loop completed
```

If the loop is terminated using `break`, the `else` block does not execute.

```python
for i in range(1, 5):
    if i == 3:
        break

    print(i)
else:
    print("Loop completed")
```

**Output:**

```text
1
2
```

---

## Summary

| Loop / Statement | Purpose |
|---|---|
| `for` | Iterates over a sequence or range |
| `while` | Repeats while a condition is `True` |
| `break` | Terminates the loop |
| `continue` | Skips the current iteration |
| `pass` | Does nothing; acts as a placeholder |
| `for`-each style | Iterates through each item of a sequence |
| `do-while` behavior | Executes at least once using `while True` and `break` |
| Nested loop | Loop inside another loop |
| `else` | Executes when a loop finishes normally |

---