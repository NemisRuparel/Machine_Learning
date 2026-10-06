# Dictionary

A **dictionary** is a collection used to store data in **key-value pairs**.

Dictionaries are:

- Ordered
- Changeable (mutable)
- Do not allow duplicate keys
- Can contain different data types

A dictionary is created using curly brackets `{}`.

```python
student = {
    "name": "Nemis",
    "age": 20,
    "marks": 85.5
}

print(student)
```

**Output:**

```text
{'name': 'Nemis', 'age': 20, 'marks': 85.5}
```

---

## Accessing Dictionary Values

Values can be accessed using their keys.

```python
student = {
    "name": "Nemis",
    "age": 20
}

print(student["name"])
print(student["age"])
```

**Output:**

```text
Nemis
20
```

The `get()` method can also be used to access a value.

```python
print(student.get("name"))
```

**Output:**

```text
Nemis
```

---

## Adding Items

A new key-value pair can be added to a dictionary.

```python
student = {
    "name": "Nemis",
    "age": 20
}

student["city"] = "Ahmedabad"

print(student)
```

**Output:**

```text
{'name': 'Nemis', 'age': 20, 'city': 'Ahmedabad'}
```

---

## Changing Values

The value of an existing key can be changed.

```python
student = {
    "name": "Nemis",
    "age": 20
}

student["age"] = 21

print(student)
```

**Output:**

```text
{'name': 'Nemis', 'age': 21}
```

---

## Removing Items

### `pop()`

Removes an item using its key.

```python
student = {
    "name": "Nemis",
    "age": 20,
    "city": "Ahmedabad"
}

student.pop("city")

print(student)
```

**Output:**

```text
{'name': 'Nemis', 'age': 20}
```

### `del`

The `del` keyword can also remove an item.

```python
del student["age"]

print(student)
```

### `clear()`

Removes all items from the dictionary.

```python
student.clear()

print(student)
```

**Output:**

```text
{}
```

---

## Checking Keys

The `in` operator can be used to check whether a key exists.

```python
student = {
    "name": "Nemis",
    "age": 20
}

print("name" in student)
print("marks" in student)
```

**Output:**

```text
True
False
```

---

## Dictionary Methods

### `keys()`

Returns all keys.

```python
student = {
    "name": "Nemis",
    "age": 20
}

print(student.keys())
```

---

### `values()`

Returns all values.

```python
print(student.values())
```

---

### `items()`

Returns all key-value pairs.

```python
print(student.items())
```

---

### `update()`

Adds new items or updates existing values.

```python
student = {
    "name": "Nemis",
    "age": 20
}

student.update({"age": 21, "city": "Ahmedabad"})

print(student)
```

**Output:**

```text
{'name': 'Nemis', 'age': 21, 'city': 'Ahmedabad'}
```

---

## Iterating Through a Dictionary

A `for` loop can be used to iterate through a dictionary.

### Keys

```python
student = {
    "name": "Nemis",
    "age": 20
}

for key in student:
    print(key)
```

**Output:**

```text
name
age
```

### Keys and Values

```python
for key, value in student.items():
    print(key, ":", value)
```

**Output:**

```text
name : Nemis
age : 20
```

---

## Nested Dictionary

A dictionary can contain another dictionary.

```python
students = {
    "student1": {
        "name": "Nemis",
        "age": 20
    },
    "student2": {
        "name": "Rahul",
        "age": 21
    }
}

print(students["student1"]["name"])
```

**Output:**

```text
Nemis
```

---

## Dictionary Comprehension

Dictionary comprehension provides a short way to create a dictionary.

```python
numbers = [1, 2, 3, 4, 5]

squares = {number: number ** 2 for number in numbers}

print(squares)
```

**Output:**

```text
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

## Common Dictionary Methods

| Method | Purpose |
|---|---|
| `get()` | Returns the value of a key |
| `keys()` | Returns all keys |
| `values()` | Returns all values |
| `items()` | Returns all key-value pairs |
| `update()` | Adds or updates items |
| `pop()` | Removes an item using its key |
| `clear()` | Removes all items |
| `copy()` | Creates a copy of the dictionary |

---