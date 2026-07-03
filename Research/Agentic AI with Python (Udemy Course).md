---
title: Agentic AI with Python (Udemy Course)
tags: [course, python, agentic-ai]
status: in-progress
started: 2026-07-02
tools: [VS Code, Python, LLMs]
---

# Agentic AI with Python

**Tools Used:** VS Code · Python · LLMs

## Progress Tracker
Tick off each module as you finish it — this doubles as your course map.

- [x] Introduction
- [x] The Coding World of Python
	- [x] What is Programming?
	- [x] Real World Python Code Intro (Class/Object/Properties/Methods)
	- [x] Why Use Python
	- [x] Writing First Python on Windows (Virtual Environments)
	- [x] Organizing Your Python Codes
	- [x] PEP 8
- [ ] Data Types in Python
- [ ] *(add next module here as you go)*

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
- **Virtual Environments** — isolated spaces to manage project-specific dependencies without conflicts.

> [!question]- Notes to self on venvs (expand and fill in as you learn)
> - How to create one: `python -m venv venv`
> - How to activate it (Windows): `venv\Scripts\activate`
> - Why it matters: *(fill in once covered)*

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

### PEP 8 — Style Guide Essentials
- [ ] Use 4 spaces, never tabs
- [ ] Use descriptive names (`chai`, not `c1`)
- [ ] Use formatters to auto-enforce style

---

## 2. Data Types in Python
*(Section not yet covered in the source — template below is ready for when you get here.)*

> [!question] Key Questions to Answer
> - What are the built-in data types in Python?
> - How do you check a variable's type?
> - What's the difference between mutable and immutable types?

```python
# Scratch space for code examples as you learn
```

**Notes:**
-

---

## List of Terms 

| Term | Definition |
|---|---|
| Class | Blueprint for creating objects |
| Object | Instance of a class |
| Module | A single `.py` file |
| Package | A folder of modules containing `__init__.py` |
| Virtual Environment | Isolated Python dependency environment |

## 🔗 Related Notes
- [[(VISTA) IT Project 2 Work Log]]
