---
title: Agentic AI with Python (Udemy Course)
tags: [course, python, agentic-ai]
status: in-progress
started: 2026-07-02
tools: [VS Code, Python, LLMs]
---
# Agentic AI with Python

**Tools Used:** VS Code · Python · LLMs

##  Progress Tracker
Tick off each module as you finish it — this doubles as your course map.

- [x] Introduction
- [x] The Coding World of Python
	- [x] What is Programming?
	- [x] Real World Python Code Intro (Class/Object/Properties/Methods)
	- [x] Why Use Python
	- [x] Writing First Python on Windows (Virtual Environments)
	- [x] Organizing Your Python Codes
	- [x] PEP 8
- [x] Data Types in Python
	- [x] Objects and Mutability
	- [x] Immutable Objects (Numbers, Strings, Tuples)
	- [x] Mutable Objects (Lists, Sets, Dictionaries)
	- [x] Advanced Data Types (datetime, collections)
- [x] *Conditionals*
	- [ ] ~~Project-Based~~

---

## 1. The Coding World of Python

### What is Programming?
> [!abstract] Definition
> Giving instructions to a computer. Computers can't "think," so every step must be spelled out explicitly.

> [!example] Analogy — Making Chai Tea
> **1. Gather Data (Collection)**
> - Water
> - Milk
> - Tea leaves
> - Sugar
> - Utensils
>
> **2. Check Conditions**
> - Enough water?
> - Clean cups?
>
> **3. Steps**
> 1. Check if kettle has water
> 2. Plug in kettle, boil water
> 3. Get clean cups
> 4. Add tea leaves and sugar to cup
> 5. Pour boiled water into cup
> 6. Stir and serve

### Real World Python Code Intro
Mapping the chai analogy onto OOP concepts — a running glossary you can extend as new terms appear.

| Term | Meaning | Chai Example |
|---|---|---|
| **Class** | Blueprint containing functions (no parentheses) — opened with `def __init__` | The "recipe" for a chai cup |
| **Object** | A specific instance made from a class | Cup, kettle, chai |
| **Properties** | Data/attributes an object holds | Cup color, kettle size, chai sweetness |
| **Methods / Functions** | Actions an object can perform | Stir, pour, drink |

> [!tip]- Quick code sketch (click to expand)
> ```python
> class ChaiCup:
>     def __init__(self, color, sweetness):
>         self.color = color
>         self.sweetness = sweetness
> 	    # Its primary job is to set up the initial state of the object by
> 	    # assigning values to its specific attributes
>
>     def stir(self):
>         print("Stirring the chai...")
> ```


### Why Use Python?
- [x] Easy to learn
- [x] Portable across operating systems
- [x] Readable — very predictable syntax
- [x] Meant to be productive
- [x] Huge Standard Library — millions have already written reusable code
- [x] Multi-use (web, data, automation, AI, etc.)
- [x] Chai-level happiness 🍵

### Writing Your First Python Program (Windows)
- **Virtual Environments** — isolated spaces to manage project-specific dependencies without conflicts
### Organizing Your Python Code
Example project structure:

```
Chai_Shop/                # Top-level directory
├── run.py                # Entry point / starts the application (Module)
├── chai.py                # Core functional code (Module)
├── Processing/
└── utils/                 # Package
    └── __init__.py
```

> [!note] Reminder
> Use backticks for anything with underscores (like `__init__.py`) so Obsidian doesn't turn `__x__` into **bold** text.

### PEP 8 — Style Guide Essentials
- [ ] Use 4 spaces, never tabs
- [ ] Use descriptive names (`chai`, not `c1`)
- [ ] Use formatters to auto-enforce style

---

## 2. Data Types in Python

### Objects and Mutability
> [!abstract] Core Idea
> Everything in Python is an **object**. Every object has:
> - A unique **Identity** (its I.D.)
> - A unique **Type**
> - A **Value**

> [!warning] Important Distinction
> - **Mutable** = changeable in terms of its referencing
> - **Immutable** = cannot be changed
>
> Use **Identity** (not value) to determine mutability — value is a **wrong indicator**. What appears to change is often the *reference*, not the underlying value.

```python
# Check identity vs value
x = [1, 2, 3]
print(id(x))   # Identity — use this to reason about mutability
print(x)       # Value — don't rely on this alone
```

---

### Immutable Objects

#### a. Numbers
| Type         | Description      |
| ------------ | ---------------- |
| Integer      | Whole numbers    |
| Boolean      | `True` / `False` |
| Real (Float) | Decimal values   |
| Complex      | e.g. `2 + 3j`    |

> [!tip]- Integer operations (click to expand)
> ```python
> a + b      # Addition
> a - b      # Subtraction
> a / b      # Division — full value with decimals
> a // b     # Floor division — whole number only
> a ** b     # Exponential (power)
> ```

**Boolean** → supports logical operations: `AND`, `OR`, `NOT`
**Complex Numbers** → handled via the `fractions` / complex number library

#### b. Strings — *Immutable*
```python
s = "Aromatic and Okay"
#    0123456789...      <- indexing
```
- **Indexing** — access a single character by position
- **Slicing** — access a range of characters
- **Encoding / Decoding** — converting strings to/from byte representations

#### c. Tuples & Membership Testing — *Unchangeable*
> [!note] Bracket Cheat Sheet
> | Symbol | Name | Used For |
> |---|---|---|
> | `()` | Parenthesis | **Tuples** (immutable) |
> | `[]` | Brackets | Lists (mutable) |
> | `{}` | Braces | Sets / Dictionaries (mutable) |

```python
my_tuple = ("ginger", "lemon")
"ginger" in my_tuple   # Membership testing -> True
```

---

### Mutable Objects

#### Lists (Python's Array)
```python
my_list = ["ginger", "lemon"]
my_list.append("honey")     # list.method()
"honey" in my_list           # Membership testing applies to lists too
```
- Supports **operator overloading** (e.g. `+` to concatenate, `*` to repeat)

#### Sets
- A **Set** guarantees **unique** elements.
- **Frozenset** = the immutable version of a set.

```python
a = {"ginger", "lemon"}
b = {"lemon", "mint"}
a | b   # Union — combination of all elements
a & b   # Intersection — common elements only
```

#### Dictionary
```python
tea_menu = {"ginger": 30, "lemon": 25}
"ginger" in tea_menu   # Membership testing
```

---

### Advanced Data Types — Third-Party Modules
> [!info] Modules to Explore
> - `datetime`, `time`, `calendar` — working with dates/times
> - `timedelta` — represents a duration
> - `arrow`, `dateutil` — third-party date/time utilities
> - `collections` — specialized container datatypes

```python
from datetime import datetime, timedelta
now = datetime.now()
later = now + timedelta(days=1)
```


---
## 3. Conditionals in Python

> [!abstract] Conditions
> Decision Making 
> Yes, No Routes
> 


## Glossary (running list — add new terms as they appear)
| Term | Definition |
|---|---|
| Class | Blueprint for creating objects |
| Object | Instance of a class |
| Module | A single `.py` file |
| Package | A folder of modules containing `__init__.py` |
| Virtual Environment | Isolated Python dependency environment |
| Identity | An object's unique ID — the reliable way to check mutability |
| Mutable | Can be changed (e.g. list, set, dict) |
| Immutable | Cannot be changed (e.g. int, str, tuple) |
| Tuple | Immutable ordered collection using `()` |
| Frozenset | Immutable version of a set |
| Membership Testing | Checking if a value exists in a collection, using `in` |

##  Related Notesx`
- [[Persnal Work Log]]
