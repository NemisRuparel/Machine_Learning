# Random Module

The `random` module is a built-in Python module used to generate **pseudo-random numbers** and make random selections.

The module must be imported before using its functions.

```python
import random
```

---

## `random()`

The `random()` function returns a random floating-point number between `0` and `1`.

```python
import random

number = random.random()

print(number)
```

**Example Output:**

```text
0.735421
```

The value is always:

```text
0 <= number < 1
```

---

## `randint()`

The `randint()` function returns a random integer between the given values.

Both the starting and ending values are included.

```python
import random

number = random.randint(1, 10)

print(number)
```

**Example Output:**

```text
7
```

The result can be any integer from `1` to `10`.

---

## `randrange()`

The `randrange()` function returns a randomly selected value from a range.

```python
import random

number = random.randrange(1, 10)

print(number)
```

The result can be from `1` to `9`.

The ending value `10` is not included.

---

## `choice()`

The `choice()` function randomly selects one item from a sequence.

```python
import random

fruits = ["Apple", "Banana", "Mango", "Orange"]

fruit = random.choice(fruits)

print(fruit)
```

**Example Output:**

```text
Mango
```

---

## `choices()`

The `choices()` function selects multiple items from a sequence.

```python
import random

fruits = ["Apple", "Banana", "Mango", "Orange"]

selected = random.choices(fruits, k=2)

print(selected)
```

**Example Output:**

```text
['Mango', 'Apple']
```

Items can be selected more than once.

---

## `sample()`

The `sample()` function selects multiple **unique** items from a sequence.

```python
import random

numbers = [1, 2, 3, 4, 5]

selected = random.sample(numbers, 3)

print(selected)
```

**Example Output:**

```text
[4, 1, 5]
```

The same item cannot be selected more than once.

---

## `shuffle()`

The `shuffle()` function randomly changes the order of items in a list.

```python
import random

numbers = [1, 2, 3, 4, 5]

random.shuffle(numbers)

print(numbers)
```

**Example Output:**

```text
[3, 5, 1, 4, 2]
```

`shuffle()` changes the original list.

---

## `uniform()`

The `uniform()` function returns a random floating-point number between two values.

```python
import random

number = random.uniform(1, 10)

print(number)
```

**Example Output:**

```text
6.42891
```

---

## `seed()`

The `seed()` function initializes the random number generator.

Using the same seed produces the same sequence of pseudo-random values.

```python
import random

random.seed(10)

print(random.randint(1, 100))
print(random.randint(1, 100))
```

This is useful when you need **reproducible results**, such as during testing.

---

## Example Program

```python
import random

number = random.randint(1, 10)

print("Random number:", number)

fruits = ["Apple", "Banana", "Mango", "Orange"]

print("Random fruit:", random.choice(fruits))
```

**Example Output:**

```text
Random number: 7
Random fruit: Mango
```

---

## Common Random Functions

| Function | Purpose |
|---|---|
| `random()` | Random float from `0` to less than `1` |
| `randint()` | Random integer including both endpoints |
| `randrange()` | Random value from a range |
| `choice()` | Selects one random item |
| `choices()` | Selects multiple random items |
| `sample()` | Selects multiple unique items |
| `shuffle()` | Randomly changes list order |
| `uniform()` | Random float between two values |
| `seed()` | Initializes the random number generator |

---