# 🐍 Python Learning Notes — Beginner Level

> My Python learning journey: Beginner to Advanced Python Backend Developer  
> Goal: Master Python, Django, Django REST Framework and Production Backend Development.

---

## 📌 Learning Progress

### Completed Topics

- [x] Variables and Assignment
- [x] Python Data Types
- [x] Numeric Data Types
- [x] Boolean Data Type
- [x] Truthy and Falsy Values
- [x] Logical Operators
- [x] Strings
- [x] String Indexing and Slicing
- [x] String Methods
- [x] String Formatting
- [x] Unicode, Encoding and Decoding
- [x] Basic Coding Practice — 10 Questions

**Current Learning Stage:** Python Fundamentals

---

# 1. Variables in Python

## What is a Variable?

A variable is a name that refers to an object in Python.

Example:

```python
name = "Smit"
age = 21
height = 169.5

print(name)
print(age)
print(height)
```

Output:

```text
Smit
21
169.5
```

### Important Concepts

**1. Dynamic Typing**

Python does not require us to declare a variable's data type explicitly.

```python
value = 100
value = "Python"
value = 10.5

print(value)
```

Output:

```text
10.5
```

Python determines the object's type at runtime.

**2. Check Data Type**

```python
name = "Python"

print(type(name))
```

Output:

```text
<class 'str'>
```

**3. Object Identity**

```python
a = 10

print(id(a))
```

`id()` returns an object's identity. In CPython, it is commonly related to its memory address, but Python does not guarantee that.

**4. Variable Naming Rules**

Valid:

```python
name = "Smit"
user_age = 21
_marks = 90
```

Invalid:

```python
2name = "Smit"
user-name = "Smit"
```

### Important Points

- Python is dynamically typed.
- Variable names are case-sensitive.
- Use `snake_case` for variable names.
- Variables refer to objects; assignment can rebind a name to another object.

---

# 2. Python Data Types

A data type defines what kind of value an object represents.

## Main Data Types

| Category | Data Types | Example |
|---|---|---|
| Numeric | int, float, complex | 10, 10.5, 2+3j |
| Sequence | str, list, tuple, range | "Python", [1, 2] |
| Set | set, frozenset | {1, 2, 3} |
| Mapping | dict | {"name": "Smit"} |
| Boolean | bool | True, False |
| None | NoneType | None |

### Examples

```python
age = 21
price = 99.50
number = 2 + 3j

name = "Python"
numbers = [10, 20, 30]
coordinates = (10, 20)
unique_numbers = {1, 2, 3}

student = {
    "name": "Smit",
    "age": 21
}

is_active = True
result = None

print(type(age))
print(type(price))
print(type(number))
print(type(name))
print(type(numbers))
print(type(student))
```

## Difference Between `type()` and `isinstance()`

```python
number = 10

print(type(number))
print(isinstance(number, int))
```

- `type()` tells us the exact type of an object.
- `isinstance()` checks whether an object belongs to a specified type or its subclass.

---

# 3. Numeric Data Types

Python has three main numeric types.

## 3.1 Integer (`int`)

Integers are whole numbers without decimal points.

```python
a = 10
b = -20

print(a + b)
```

Python integers can grow beyond fixed 32-bit or 64-bit limits, subject to available memory.

## 3.2 Float (`float`)

Floats represent decimal numbers.

```python
price = 99.50

print(price)
print(type(price))
```

### Division Operators

```python
print(10 / 2)
print(10 // 3)
print(10 % 3)
```

Output:

```text
5.0
3
1
```

| Operator | Meaning |
|---|---|
| `/` | True division |
| `//` | Floor division |
| `%` | Remainder |
| `**` | Power |

**Important:** `/` returns a float, even when the result is mathematically a whole number.

### Floating-Point Precision

```python
print(0.1 + 0.2)
```

Output:

```text
0.30000000000000004
```

Why?

Many decimal fractions cannot be represented exactly in binary floating-point format.

For financial calculations, use `Decimal`:

```python
from decimal import Decimal

a = Decimal("0.1")
b = Decimal("0.2")

print(a + b)
```

Output:

```text
0.3
```

## 3.3 Complex (`complex`)

Complex numbers have real and imaginary parts.

```python
number = 2 + 3j

print(number.real)
print(number.imag)
```

Output:

```text
2.0
3.0
```

---

# 4. Boolean Data Type

Boolean has only two values:

```python
True
False
```

Example:

```python
age = 21

print(age >= 18)
```

Output:

```text
True
```

## Comparison Operators

| Operator | Meaning |
|---|---|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal |
| `<=` | Less than or equal |

Example:

```python
a = 10
b = 20

print(a == b)
print(a < b)
print(a != b)
```

## Logical Operators

### AND

Both conditions must be true.

```python
age = 21
has_id = True

print(age >= 18 and has_id)
```

### OR

At least one condition must be true.

```python
print(True or False)
```

### NOT

Reverses the Boolean result.

```python
print(not True)
```

## Truthy and Falsy Values

Falsy values include:

```python
False
0
0.0
""
[]
{}
()
set()
None
```

Examples:

```python
print(bool(0))
print(bool(""))
print(bool([]))
print(bool("Python"))
```

Output:

```text
False
False
False
True
```

## Short-Circuit Evaluation

Python may stop evaluating a logical expression once its result is known.

```python
username = "admin"
password = "12345"

if username and password:
    print("Login details provided")
```

- `and` stops when it finds a falsy value.
- `or` stops when it finds a truthy value.

**Important Interview Fact:** `bool` is a subclass of `int`.

```python
print(True + True)
print(False + True)
```

Output:

```text
2
1
```

---

# 5. Strings in Python

A string is a sequence of characters.

```python
name = "Python"
message = 'Hello World'
```

Multiline strings:

```python
text = """This is
a multiline
string."""
```

## String Immutability

Strings are immutable, which means their existing contents cannot be changed in place.

Incorrect:

```python
text = "Python"
text[0] = "J"
```

This produces a `TypeError`.

Correct:

```python
text = "Python"
text = "J" + text[1:]

print(text)
```

Output:

```text
Jython
```

Methods such as `replace()` return a new string.

```python
text = "Python"

new_text = text.replace("P", "J")

print(new_text)
print(text)
```

Output:

```text
Jython
Python
```

## String Indexing

```python
text = "Python"
```

| Character | P | y | t | h | o | n |
|---|---|---|---|---|---|---|
| Positive index | 0 | 1 | 2 | 3 | 4 | 5 |
| Negative index | -6 | -5 | -4 | -3 | -2 | -1 |

```python
print(text[0])
print(text[-1])
```

Output:

```text
P
n
```

## String Slicing

Syntax:

```python
string[start:stop:step]
```

The `stop` index is excluded.

```python
text = "Python"

print(text[0:3])
print(text[2:5])
print(text[:4])
print(text[2:])
print(text[::-1])
```

Output:

```text
Pyt
tho
Pyth
thon
nohtyP
```

`[::-1]` reverses a string.

## Important String Methods

```python
text = "  hello python  "

print(text.upper())
print(text.lower())
print(text.title())
print(text.capitalize())
print(text.strip())
print(text.lstrip())
print(text.rstrip())
```

### Search Methods

```python
text = "Hello Python"

print(text.find("Python"))
print(text.index("Hello"))
print(text.startswith("Hello"))
print(text.endswith("Python"))
```

Important difference:

- `find()` returns `-1` if the substring is missing.
- `index()` raises `ValueError` if the substring is missing.

### Replace and Split

```python
text = "I love Java"

print(text.replace("Java", "Python"))

sentence = "Python is easy"

words = sentence.split()

print(words)
```

Output:

```text
I love Python
['Python', 'is', 'easy']
```

`split()` returns a list.

### Join

```python
words = ["Python", "is", "powerful"]

result = " ".join(words)

print(result)
```

Output:

```text
Python is powerful
```

### Character Checking Methods

```python
print("Python".isalpha())
print("12345".isdigit())
print("Python123".isalnum())
print("   ".isspace())
```

### Important Methods Summary

| Method | Purpose |
|---|---|
| `lower()` | Converts to lowercase |
| `upper()` | Converts to uppercase |
| `title()` | Converts words to title case |
| `strip()` | Removes whitespace from both ends |
| `replace()` | Replaces a substring |
| `split()` | Splits string into a list |
| `join()` | Joins iterable strings |
| `find()` | Finds substring, returns -1 if missing |
| `index()` | Finds substring, raises error if missing |
| `startswith()` | Checks starting characters |
| `endswith()` | Checks ending characters |
| `isalpha()` | Checks alphabetic characters |
| `isdigit()` | Checks digit characters |
| `isalnum()` | Checks letters or digits |

---

# 6. String Formatting

String formatting allows us to insert values into strings.

## 6.1 Concatenation

```python
name = "Smit"
age = 21

print("My name is " + name)
```

## 6.2 format()

```python
name = "Smit"
age = 21

print("My name is {} and my age is {}".format(name, age))
```

## 6.3 f-Strings

The recommended readable approach:

```python
name = "Smit"
age = 21

print(f"My name is {name} and my age is {age}")
```

### Decimal Formatting

```python
price = 45.6789

print(f"{price:.2f}")
```

Output:

```text
45.68
```

`.2f` means display two digits after the decimal point.

---

# 7. Unicode, Encoding and Decoding

Unicode is a standard that represents characters from different writing systems.

Python strings are Unicode text.

## ord()

Returns the Unicode code point of a character.

```python
character = "A"

print(ord(character))
```

Output:

```text
65
```

## chr()

Converts a Unicode code point into a character.

```python
number = 65

print(chr(number))
```

Output:

```text
A
```

## Encoding

Converts a string into bytes using a character encoding.

```python
text = "Hello"

encoded = text.encode("utf-8")

print(encoded)
print(type(encoded))
```

## Decoding

Converts bytes back into a string.

```python
decoded = encoded.decode("utf-8")

print(decoded)
```

### Difference Between str and bytes

| str | bytes |
|---|---|
| Represents text | Represents binary data |
| Unicode text | Sequence of byte values |
| `"Hello"` | `b"Hello"` |

---

# 8. Important Coding Questions with Answers

These questions are part of my initial Python practice tracker.

## PY-01: Swap Two Variables

**Question:** Swap the values of two variables without using a third variable.

```python
a = 10
b = 20

a = a + b
b = a - b
a = a - b

print("a:", a)
print("b:", b)
```

Output:

```text
a: 20
b: 10
```

Python's simpler approach:

```python
a = 10
b = 20

a, b = b, a

print(a, b)
```

## PY-02: Calculate Total and Average

**Question:** Calculate total and average marks.

```python
math_marks = 80
science_marks = 75
english_marks = 85

total = math_marks + science_marks + english_marks
average = total / 3

print(f"Total: {total}")
print(f"Average: {average}")
```

Output:

```text
Total: 240
Average: 80.0
```

## PY-03: Check Even or Odd

**Question:** Check whether a number is even or odd.

```python
number = 24

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Even
```

Logic:

- Remainder 0 means even.
- Otherwise, odd.

## PY-04: Login Condition

**Question:** Check username and password.

```python
username = "admin"
password = "12345"

if username == "admin" and password == "12345":
    print("Login successful")
else:
    print("Login failed")
```

Output:

```text
Login successful
```

## PY-05: Count Numbers

**Question:** Count numbers from 1 to 10 using a loop.

```python
count = 0

for number in range(1, 11):
    count += 1

print(count)
```

Output:

```text
10
```

## PY-06: Count Vowels and Consonants

**Question:** Count vowels and consonants in a word.

```python
text = "developer"

vowels = 0
consonants = 0

for char in text:
    if char in "aeiou":
        vowels += 1
    elif char.isalpha():
        consonants += 1

print("Vowels:", vowels)
print("Consonants:", consonants)
```

Output:

```text
Vowels: 4
Consonants: 5
```

## PY-07: Remove Spaces and Convert to Lowercase

**Question:** Remove spaces from the beginning and end, then convert to lowercase.

```python
text = "   HELLO PYTHON   "

result = text.strip().lower()

print(result)
```

Output:

```text
hello python
```

## PY-08: Check Palindrome

**Question:** Check whether a string reads the same forward and backward.

```python
text = "madam"

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not a palindrome")
```

Output:

```text
Palindrome
```

## PY-09: Format a Decimal Number

**Question:** Display a number with two digits after the decimal point.

```python
price = 45.6789

print(f"Price: {price:.2f}")
```

Output:

```text
Price: 45.68
```

## PY-10: Unicode Conversion

**Question:** Convert a character into its Unicode code point and back.

```python
character = "A"

number = ord(character)
result = chr(number)

print(number)
print(result)
```

Output:

```text
65
A
```

---

# 9. Important Interview Questions and Answers

### Q1. What is Python?

Python is a high-level, general-purpose programming language known for its readable syntax and large ecosystem.

### Q2. Is Python compiled or interpreted?

Python implementations commonly compile source code into bytecode, which is then executed by a runtime such as the CPython virtual machine.

### Q3. What is dynamic typing?

Dynamic typing means variable names do not need explicit type declarations. The objects they refer to have types determined at runtime.

### Q4. What is the difference between `==` and `=`?

- `=` assigns a value.
- `==` compares two values.

### Q5. What is the difference between `/` and `//`?

- `/` performs true division.
- `//` performs floor division.

### Q6. Why is `0.1 + 0.2` not exactly `0.3`?

Because binary floating-point cannot represent many decimal fractions exactly.

### Q7. Are strings mutable?

No. Strings are immutable in Python.

### Q8. What is string slicing?

Slicing extracts part of a sequence using `[start:stop:step]`.

### Q9. Difference between `find()` and `index()`?

`find()` returns `-1` when a substring is missing. `index()` raises `ValueError`.

### Q10. Difference between `split()` and `join()`?

- `split()` converts a string into a list.
- `join()` combines strings from an iterable into one string.

### Q11. What is short-circuit evaluation?

Python stops evaluating a logical expression once its result is already determined.

### Q12. Difference between `str` and `bytes`?

`str` represents Unicode text, whereas `bytes` represents a sequence of bytes.

### Q13. What is Unicode?

Unicode is a standard for representing characters across different languages and writing systems.

### Q14. What is an f-string?

An f-string is a convenient way to insert expressions and values into a string using `{}`.

### Q15. What does `None` mean?

`None` represents the absence of a value. It is different from `0`, `False` and an empty string.

---

# 10. Quick Revision Cheat Sheet

```python
# Variables
name = "Smit"

# Data type
print(type(name))

# Identity
print(id(name))

# Numeric operators
print(10 / 2)
print(10 // 3)
print(10 % 3)
print(2 ** 3)

# Boolean
print(10 > 5)
print(True and False)
print(True or False)
print(not True)

# String indexing
text = "Python"
print(text[0])
print(text[-1])

# String slicing
print(text[0:3])
print(text[::-1])

# String methods
print(text.upper())
print(text.lower())
print(text.replace("P", "J"))

# Formatting
age = 21
print(f"My age is {age}")

# Unicode
print(ord("A"))
print(chr(65))

# Encoding and decoding
encoded = "Hello".encode("utf-8")
decoded = encoded.decode("utf-8")
```

---

# 11. My Next Learning Goals

- [ ] Conditional statements in depth
- [ ] Loops in depth
- [ ] Nested loops and patterns
- [ ] Lists
- [ ] Tuples
- [ ] Sets
- [ ] Dictionaries
- [ ] Functions
- [ ] Exception handling
- [ ] File handling
- [ ] Object-Oriented Programming
- [ ] Advanced Python
- [ ] SQL and PostgreSQL
- [ ] Django
- [ ] Django REST Framework
- [ ] Production deployment

---
