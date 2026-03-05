# 🔤 Palindrome Checker — Python Challenge

## 📌 Overview

A Python function that determines whether a given string is a palindrome, ignoring spaces, capitalization, and punctuation.

---

## 📝 Problem Statement

Given a string, return a Boolean value indicating whether it is a palindrome. A palindrome is a string that reads the same forward and backward.

**Rules:**
- Ignore letter casing
- Ignore spaces
- Ignore punctuation

**Example palindromes:**
| Input | Is Palindrome? |
|-------|---------------|
| `"Radar"` | ✅ True |
| `"Race car!"` | ✅ True |
| `"Madam, I'm Adam."` | ✅ True |
| `"Hello World"` | ❌ False |

---

## ⚙️ Parameters & Result

| Name | Type | Description |
|------|------|-------------|
| `teststr` | `String` | The string to evaluate |
| **Returns** | `Boolean` | `True` if palindrome, `False` if not |

**Constraints:**
- `teststr` is always at least one character long

---

## 💡 Approach

The solution follows three simple steps:

1. **Clean** the string — remove all non-alphanumeric characters and convert to lowercase
2. **Reverse** the cleaned string
3. **Compare** the cleaned string to its reverse and return the result

---

## 🧑‍💻 Code

```python
test_words = ["Hello World", "Radar", "Mama?", "Madam, I'm Adam.", "Race car!"]

def is_palindrome(teststr):
    # Step 1: Clean the string - keep only letters/digits and lowercase them
    cleaned = "".join(c.lower() for c in teststr if c.isalnum())
    
    # Step 2: Reverse the cleaned string
    reversed_str = cleaned[::-1]

    # Step 3: Compare and return the result
    return cleaned == reversed_str

# Testing it out
for word in test_words:
    print(f'"{word}" -> {is_palindrome(word)}')
```

---

## 📊 Output

```
"Hello World" -> False
"Radar" -> True
"Mama?" -> False
"Madam, I'm Adam." -> True
"Race car!" -> True
```

---

## 🔍 Code Breakdown

### Step 1 — Cleaning the string
```python
cleaned = "".join(c.lower() for c in teststr if c.isalnum())
```
This single line does three things:
- `for c in teststr` — loops through every character
- `if c.isalnum()` — filters out spaces and punctuation, keeping only letters and digits
- `c.lower()` — converts each character to lowercase
- `"".join(...)` — stitches everything back into a single string

**Example:** `"Race car!"` → `"racecar"`

### Step 2 — Reversing the string
```python
reversed_str = cleaned[::-1]
```
The `[::-1]` slice reads the string from end to start, effectively reversing it.

**Example:** `"racecar"` → `"racecar"`

### Step 3 — Comparing and returning
```python
return cleaned == reversed_str
```
The `==` operator directly returns `True` or `False`, no `if` statement needed.

---

## 🎬 Full Trace Example

Tracing `"Madam, I'm Adam."` through the function:

```
Input:      "Madam, I'm Adam."
Cleaned:    "madamimadam"
Reversed:   "madamimadam"
Result:     True ✅
```

---

## 🛠️ Built With

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)

---

*Solution to Coding Challenge for Chapter 2 of the 'Learning Python (2021)' module of Anaconda for Data Science.*
