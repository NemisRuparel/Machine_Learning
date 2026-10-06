# None

`None` is a special value in Python that represents the **absence of a value** or **no value**.

The data type of `None` is `NoneType`.

```python
value = None

print(value)
print(type(value))
```

**Output:**

```text
None
<class 'NoneType'>
```

---

## Assigning `None`

A variable can be assigned `None` when it does not have a value yet.

```python
name = None

print(name)
```

**Output:**

```text
None
```

The variable can later be assigned another value.

```python
name = None

name = "Nemis"

print(name)
```

**Output:**

```text
Nemis
```

---

## Checking for `None`

The `is` operator is commonly used to check whether a value is `None`.

```python
value = None

if value is None:
    print("No value")
```

**Output:**

```text
No value
```

To check that a value is not `None`:

```python
value = "Python"

if value is not None:
    print("Value exists")
```

**Output:**

```text
Value exists
```

---

## `None` in Functions

A function that does not explicitly return a value returns `None`.

```python
def greet():
    print("Hello")

result = greet()

print(result)
```

**Output:**

```text
Hello
None
```

---

## `None` vs `0`

`None` and `0` are different values.

```python
a = None
b = 0

print(a == b)
```

**Output:**

```text
False
```

`0` represents the number zero, while `None` represents the absence of a value.

---

## `None` vs Empty String

`None` and an empty string `""` are also different.

```python
a = None
b = ""

print(a == b)
```

**Output:**

```text
False
```

An empty string is a string containing no characters, while `None` represents no value.

---

## Example

```python
username = None

if username is None:
    print("Username is not set")
else:
    print("Username:", username)
```

**Output:**

```text
Username is not set
```

---

## Key Points

- `None` represents the absence of a value.
- The type of `None` is `NoneType`.
- `None` is different from `0`, `False`, and `""`.
- Use `is None` to check for `None`.
- Use `is not None` to check that a value exists.
- Functions without a `return` statement return `None`.