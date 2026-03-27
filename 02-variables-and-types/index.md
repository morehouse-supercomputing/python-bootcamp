---
layout: default
title: "02 -- Variables and Types"
---

# Variables and Types

Now that your environment is set up, let's write some real Python. In this lesson, you'll learn how Python stores data, the basic data types, and how to work with user input.

---

## Variables

A variable is a name that points to a value. You create one with `=`:

```python
name = "Ashley"
age = 30
gpa = 3.85
```

Rules for variable names:
- Must start with a letter or underscore
- Can contain letters, numbers, and underscores
- Case-sensitive (`Name` and `name` are different)
- No spaces -- use underscores: `first_name`, not `first name`

```python
# Good
student_name = "Marcus"
total_score = 95

# Bad (these will cause errors)
# 2nd_place = "Jordan"    -- can't start with a number
# my score = 88           -- no spaces allowed
```

---

## Data Types

Every value in Python has a type. The four basic types:

| Type | What It Stores | Example |
|------|---------------|---------|
| `int` | Whole numbers | `42`, `-7`, `0` |
| `float` | Decimal numbers | `3.14`, `-0.5`, `2.0` |
| `str` | Text (strings) | `"hello"`, `'Python'` |
| `bool` | True or False | `True`, `False` |

Check a value's type with `type()`:

```python
print(type(42))        # <class 'int'>
print(type(3.14))      # <class 'float'>
print(type("hello"))   # <class 'str'>
print(type(True))      # <class 'bool'>
```

---

## Arithmetic Operators

Python works like a calculator:

| Operator | Operation | Example | Result |
|----------|-----------|---------|--------|
| `+` | Addition | `5 + 3` | `8` |
| `-` | Subtraction | `10 - 4` | `6` |
| `*` | Multiplication | `3 * 7` | `21` |
| `/` | Division | `15 / 4` | `3.75` |
| `//` | Floor division | `15 // 4` | `3` |
| `%` | Modulo (remainder) | `15 % 4` | `3` |
| `**` | Exponent | `2 ** 3` | `8` |

```python
# Order of operations follows PEMDAS
result = 2 + 3 * 4      # 14, not 20
result = (2 + 3) * 4    # 20
```

Division always returns a float, even if the result is a whole number:

```python
print(10 / 2)    # 5.0 (float)
print(10 // 2)   # 5   (int)
```

---

## String Operations

Strings can be combined and repeated:

```python
first = "Morehouse"
last = "College"

# Concatenation (joining)
full = first + " " + last    # "Morehouse College"

# Repetition
cheer = "Go! " * 3           # "Go! Go! Go! "

# Length
print(len(full))              # 16
```

### f-strings (formatted strings)

The easiest way to mix variables into text:

```python
name = "Marcus"
score = 95

print(f"Nice work, {name}! You scored {score}%.")
# Output: Nice work, Marcus! You scored 95%.

# You can put expressions inside the braces
print(f"Double your score: {score * 2}")
# Output: Double your score: 190
```

---

## Type Casting

Sometimes you need to convert between types:

```python
# String to int
age_str = "21"
age = int(age_str)       # 21

# String to float
price_str = "9.99"
price = float(price_str) # 9.99

# Number to string
count = 42
count_str = str(count)   # "42"

# Float to int (truncates, does not round)
pi = 3.99
print(int(pi))           # 3
```

Why does this matter? Because `input()` always returns a string:

```python
# This won't work the way you expect
age = input("How old are you? ")
print(age + 5)   # ERROR: can't add string + int

# Fix it with int()
age = int(input("How old are you? "))
print(age + 5)   # Works!
```

---

## Input and Output

`print()` outputs to the screen. `input()` reads from the keyboard:

```python
# Basic output
print("Welcome to Python!")

# Getting user input
name = input("What's your name? ")
print(f"Hello, {name}!")

# Getting a number from the user
age = int(input("How old are you? "))
print(f"In 10 years you'll be {age + 10}.")
```

`input()` always pauses the program and waits for the user to type something and press Enter.

---

## Quick Reference

```python
# Variables
x = 10
name = "Python"

# Check type
type(x)          # int

# Casting
int("5")         # string to int
float("3.14")    # string to float
str(42)          # int to string

# f-strings
f"Hello, {name}"

# Input
answer = input("Enter something: ")
```

---

## Practice

Open the notebook for this lesson and complete the exercises:

```bash
cd python-bootcamp/02-variables-and-types
jupyter notebook notebook.ipynb
```

When you're done, submit your completed notebook to Canvas.

---

## What's Next

Next up: [Logic and Conditionals](../03-logic-and-conditionals/) -- making decisions in your code with `if`, `elif`, and `else`.

---

[Back to home](../)
