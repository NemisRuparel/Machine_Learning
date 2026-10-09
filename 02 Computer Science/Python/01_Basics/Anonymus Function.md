# Anonymous Functions (`lambda`)

## 1. What is an Anonymous Function?

An **anonymous function** is a function defined without a conventional function name.

In Python, anonymous functions are created using the `lambda` keyword.

Lambda functions are generally used for short operations that can be expressed as a single expression.

### Syntax

```
lambda arguments: expression
```

- `lambda`: Defines an anonymous function.
    
- `arguments`: Inputs received by the function.
    
- `expression`: An expression whose result is returned automatically.
    

Unlike a function defined with `def`, a lambda function does not use an explicit `return` statement.

---

## 2. Basic Example

```
square = lambda x: x * x

print(square(5))
```

**Output:**

```
25
```

Here, `x` is the argument, and `x * x` is the expression. The result is returned automatically.

---

## 3. Lambda Function with Multiple Arguments

A lambda function can accept multiple arguments.

```
add = lambda a, b: a + b

print(add(10, 20))
```

**Output:**

```
30
```

Another example:

```
multiply = lambda a, b: a * b

print(multiply(4, 5))
```

**Output:**

```
20
```

---

## 4. Lambda Function with Conditional Expressions

A lambda function can contain a conditional expression.

```
check_even = lambda number: "Even" if number % 2 == 0 else "Odd"

print(check_even(8))
print(check_even(7))
```

**Output:**

```
Even
Odd
```

The expression checks whether the number is divisible by 2.

---

## 5. Using Lambda with `map()`

The `map()` function applies a function to every item in an iterable.

```
numbers = [1, 2, 3, 4, 5]

squares = list(map(lambda x: x ** 2, numbers))

print(squares)
```

**Output:**

```
[1, 4, 9, 16, 25]
```

The lambda function calculates the square of each number.

---

## 6. Using Lambda with `filter()`

The `filter()` function selects items for which a condition evaluates to `True`.

```
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = list(filter(lambda x: x % 2 == 0, numbers))

print(even_numbers)
```

**Output:**

```
[2, 4, 6]
```

Only even numbers are included in the resulting list.

---

## 7. Using Lambda with `sorted()`

Lambda functions are useful for specifying custom sorting keys.

```
students = [
    ("Amit", 85),
    ("Neha", 92),
    ("Raj", 78)
]

students.sort(key=lambda student: student[1])

print(students)
```

**Output:**

```
[('Raj', 78), ('Amit', 85), ('Neha', 92)]
```

The `key` function returns the second element of each tuple, so the students are sorted by marks in ascending order.

To sort in descending order:

```
students.sort(key=lambda student: student[1], reverse=True)

print(students)
```

**Output:**

```
[('Neha', 92), ('Amit', 85), ('Raj', 78)]
```

---

## 8. Lambda vs. Regular Function

|Lambda Function|Regular Function|
|---|---|
|Uses the `lambda` keyword.|Uses the `def` keyword.|
|Contains a single expression.|Can contain multiple statements.|
|Returns the expression's result automatically.|Typically uses `return` to return a value.|
|Useful for short operations.|Better for complex or reusable logic.|

### Regular Function

```
def square(x):
    return x * x

print(square(5))
```

**Output:**

```
25
```

### Equivalent Lambda Function

```
square = lambda x: x * x

print(square(5))
```

**Output:**

```
25
```

Both functions produce the same result.

---

## 9. Important Limitations

- A lambda function's body must be a single expression, not a sequence of statements.
    
- Lambda functions can accept zero or more arguments.
    
- They are useful for short operations, but complex logic is usually clearer with `def`.
    
- Lambda functions are not automatically faster than regular functions.
    
- Although often called anonymous functions, lambda functions can be assigned to variables. For complex named functions, prefer `def`.
    

---

## 10. Key Points

- `lambda` creates an anonymous function.
    
- Syntax: `lambda arguments: expression`.
    
- The result of the expression is returned automatically.
    
- Lambda functions support multiple arguments.
    
- They are commonly used with `map()`, `filter()`, and `sorted()`.
    
- Use `def` when the function needs complex logic or a descriptive name.