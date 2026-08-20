# Functions

A **function** is a block of reusable code that performs a specific task.

**Example:**

```python
print("Hello World")
```

Here, `print()` is a **built-in function** used to display content on the screen.

---

## Calling a Function

Using a function in a program is called **calling the function**.

```python
print("Hello World")
```

Here, `print()` is being called.

---

## Arguments

An **argument** is a value passed to a function when the function is called.

**Example:**

```python
print("Hello World")
```

Here, `"Hello World"` is an **argument** passed to the `print()` function.

Another example:

```python
print("Hello", "Nemis", 20)
```

Here, `"Hello"`, `"Nemis"`, and `20` are arguments.

---

## Parameters

A **parameter** is a variable defined inside the function definition that receives an argument.

```python
def greet(name):
    print("Hello", name)
```

Here, `name` is a **parameter**.

When the function is called:

```python
greet("Nemis")
```

`"Nemis"` is the **argument** passed to the `name` parameter.

### Parameter vs Argument

```text
Parameter → Variable defined in the function
Argument  → Actual value passed to the function
```

---

## Defining a Function

A function is defined using the `def` keyword.

```python
def greet():
    print("Hello World")
```

Here:

- `def` → keyword used to define a function
     
- `greet` → function name
    
- `()` → parameters are written inside these brackets
    
- `:` → indicates the beginning of the function block
    
- Indented code → function body
    

---

## Calling a User-Defined Function

```python
def greet():
    print("Hello World")

greet()
```

Output:

```text
Hello World
```

`greet()` calls the function and executes its code.

---

## Function with Parameters

```python
def greet(name):
    print("Hello", name)

greet("Nemis")
```

Output:

```text
Hello Nemis
```

Here:

```text
name   → parameter
"Nemis" → argument
```

---

## Function with Return Value

A function can return a value using the `return` statement.

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

Output:

```text
30
```

Here:

```text
a, b      → parameters
10, 20    → arguments
a + b     → returned value
result    → stores the returned value
```

---

## Types of Functions

### Built-in Functions

Functions already provided by Python.

Examples:

```python
print()
len()
type()
input()
int()
str()
sum()
max()
min()
```

### User-Defined Functions

Functions created by the programmer using `def`.

```python
def square(number):
    return number * number
```

---

## Function Syntax

```python
def function_name(parameters):
    # function body
    return value
```

Example:

```python
def multiply(a, b):
    return a * b
```

---

## Why Use Functions?

Functions help to:

- Reuse code
    
- Avoid writing the same code repeatedly
    
- Organize programs
    
- Make code easier to understand
    
- Make debugging easier
    
- Break a large program into smaller tasks