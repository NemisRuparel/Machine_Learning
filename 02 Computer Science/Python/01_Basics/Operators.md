# Python Operators

## 1. What are Operators?

Operators are special symbols or keywords used to perform operations on variables and values.

Python supports several types of operators:

- Arithmetic operators
    
- Comparison operators
    
- Assignment operators
    
- Logical operators
    
- Bitwise operators
    
- Membership operators
    
- Identity operators
    

---

## 2. Arithmetic Operators

Arithmetic operators perform mathematical calculations.

|Operator|Name|Example|Result|
|---|---|---|---|
|`+`|Addition|`10 + 5`|`15`|
|`-`|Subtraction|`10 - 5`|`5`|
|`*`|Multiplication|`10 * 5`|`50`|
|`/`|Division|`10 / 4`|`2.5`|
|`//`|Floor division|`10 // 4`|`2`|
|`%`|Modulus|`10 % 4`|`2`|
|`**`|Exponentiation|`2 ** 3`|`8`|

### Example

```
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** b)
```

**Output:**

```
13
7
30
3.3333333333333335
3
1
1000
```

**Note:** Floor division rounds the quotient down toward negative infinity. For example, `-7 // 2` produces `-4`.

---

## 3. Comparison Operators

Comparison operators compare two values and return a Boolean value: `True` or `False`.

|Operator|Meaning|Example|
|---|---|---|
|`==`|Equal to|`5 == 5` → `True`|
|`!=`|Not equal to|`5 != 3` → `True`|
|`>`|Greater than|`5 > 3` → `True`|
|`<`|Less than|`3 < 5` → `True`|
|`>=`|Greater than or equal to|`5 >= 5` → `True`|
|`<=`|Less than or equal to|`3 <= 5` → `True`|

### Example

```
a = 10
b = 5

print(a == b)
print(a != b)
print(a > b)
print(a < b)
print(a >= b)
print(a <= b)
```

**Output:**

```
False
True
True
False
True
False
```

---

## 4. Assignment Operators

Assignment operators assign values to variables or update existing values.

|Operator|Example|Equivalent operation|
|---|---|---|
|`=`|`x = 10`|Assign `10` to `x`|
|`+=`|`x += 5`|`x = x + 5`|
|`-=`|`x -= 5`|`x = x - 5`|
|`*=`|`x *= 5`|`x = x * 5`|
|`/=`|`x /= 5`|`x = x / 5`|
|`//=`|`x //= 5`|`x = x // 5`|
|`%=`|`x %= 5`|`x = x % 5`|
|`**=`|`x **= 2`|`x = x ** 2`|
|`&=`|`x &= 3`|Bitwise AND assignment|
|`\|=`|`x \|= 3`|Bitwise OR assignment|
|`^=`|`x ^= 3`|Bitwise XOR assignment|
|`>>=`|`x >>= 1`|Right-shift assignment|
|`<<=`|`x <<= 1`|Left-shift assignment|

### Example

```
x = 10

x += 5
print(x)

x *= 2
print(x)

x -= 4
print(x)
```

**Output:**

```
15
30
26
```

Python also supports `:=`, called the **assignment expression operator** or _walrus operator_. It assigns a value within an expression.

```
if (length := len("Python")) > 5:
    print(length)
```

**Output:**

```
6
```

---

## 5. Logical Operators

Logical operators combine or reverse Boolean conditions.

|Operator|Meaning|Example|
|---|---|---|
|`and`|True when both conditions are true|`True and False` → `False`|
|`or`|True when at least one condition is true|`True or False` → `True`|
|`not`|Reverses truth value|`not True` → `False`|

### Example

```
age = 20
has_id = True

print(age >= 18 and has_id)
print(age < 18 or has_id)
print(not has_id)
```

**Output:**

```
True
True
False
```

**Note:** `and` and `or` use short-circuit evaluation and can return one of their operands rather than a Boolean value.

---

## 6. Bitwise Operators

Bitwise operators perform operations on the binary representations of integers.

|Operator|Name|Description|
|---|---|---|
|`&`|AND|Sets a bit if both corresponding bits are `1`|
|`\|`|OR|Sets a bit if either corresponding bit is `1`|
|`^`|XOR|Sets a bit if corresponding bits differ|
|`~`|NOT|Inverts integer bits|
|`<<`|Left shift|Shifts bits to the left|
|`>>`|Right shift|Shifts bits to the right|

### Example

```
a = 5  # Binary: 0101
b = 3  # Binary: 0011

print(a & b)
print(a | b)
print(a ^ b)
print(~a)
print(a << 1)
print(a >> 1)
```

**Output:**

```
1
7
6
-6
10
2
```

For Python integers, `~x` is equivalent to `-x - 1`.

---

## 7. Membership Operators

Membership operators check whether a value exists in a sequence or collection.

|Operator|Meaning|
|---|---|
|`in`|Checks whether a value is present|
|`not in`|Checks whether a value is absent|

### Example

```
languages = ["Python", "Java", "C++"]

print("Python" in languages)
print("Ruby" in languages)
print("Ruby" not in languages)
```

**Output:**

```
True
False
True
```

Membership behavior depends on the type of object. For dictionaries, `in` checks keys by default.

---

## 8. Identity Operators

Identity operators check whether two references point to the same object.

|Operator|Meaning|
|---|---|
|`is`|Both references point to the same object|
|`is not`|References point to different objects|

### Example

```
a = [1, 2, 3]
b = a
c = [1, 2, 3]

print(a is b)
print(a is c)
print(a == c)
print(a is not c)
```

**Output:**

```
True
False
True
True
```

- `is` checks object identity.
    
- `==` checks value equality.
    

Use `is None` to check whether a value is `None`.

```
result = None

if result is None:
    print("No result")
```

**Output:**

```
No result
```

---

## 9. Operator Precedence

Operator precedence determines the order in which operations are evaluated.

|Priority|Operators|Description|
|---|---|---|
|High|`()`|Parentheses for grouping|
||`**`|Exponentiation|
||`+x`, `-x`, `~x`|Unary operations|
||`*`, `/`, `//`, `%`|Multiplication and division|
||`+`, `-`|Addition and subtraction|
||`<<`, `>>`|Bit shifts|
||`&`, `^`, `\|`|Bitwise operations|
||Comparisons, `in`, `is`|Comparisons, membership, identity|
||`not`|Logical NOT|
||`and`|Logical AND|
||`or`|Logical OR|
|Low|`:=`|Assignment expression|

This is a simplified overview; Python has additional precedence details, including between bitwise operators and comparisons. Parentheses make complex expressions easier to read.

### Example

```
result = 2 + 3 * 4
print(result)

result = (2 + 3) * 4
print(result)
```

**Output:**

```
14
20
```

Multiplication takes precedence over addition unless parentheses change the evaluation order.

---

## 10. Chained Comparisons

Python allows multiple comparisons to be combined.

```
age = 25

print(18 <= age <= 60)
```

**Output:**

```
True
```

This is equivalent in meaning to checking `18 <= age and age <= 60`, except that the middle expression is evaluated only once.

---

## 11. Key Points

- Arithmetic operators perform mathematical calculations.
    
- Comparison operators return Boolean results.
    
- Assignment operators assign or update values.
    
- Logical operators combine conditions.
    
- Bitwise operators manipulate integer bits.
    
- Membership operators check whether values belong to collections.
    
- Identity operators compare object identity, not value equality.
    
- Operator precedence determines evaluation order.
    
- Use parentheses to make complicated expressions clearer.
    
- Use `==` for value equality and `is` for identity checks.