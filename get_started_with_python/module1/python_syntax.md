# Explore Python Syntax

## Overview
Python is a popular and flexible programming language widely used in fields like **software development**, **machine learning**, and **data analysis**. Familiarity with Python's **syntax** and **semantics** is essential for data professionals. This reading introduces Python's structure, guiding principles, and resources for further learning.

---

## Key Python Concepts

### **1. Syntax and Semantics**
- **Syntax**: The structure and arrangement of words and punctuation in Python.
- **Semantics**: The meaning conveyed by the syntax. 
- Learning syntax and semantics requires **exposure**, **practice**, and reading others’ code.

---

### **2. Basics of Python**

#### **Variables**
- Represent data stored as types like strings, tuples, dictionaries, and lists.  
  - Example: `student_name`

#### **Keywords**
- Reserved words used for specific purposes.  
  - Examples: `in`, `not`, `or`, `for`, `while`, `return`

#### **Operators**
- Symbols used for operations on objects and values.  
  - Examples:  
    - `+`: Addition  
    - `-`: Subtraction  
    - `/`: Division  
    - `%`: Modulo  
    - `==`: Equality  

#### **Expressions**
- Combine numbers, variables, and operators to compute results.  
  - Example: `[1, 2, 3] + [2, 4, 6]`

#### **Functions**
- Groups of related statements to perform a task.  
  - Example:
    ```python
    def to_celsius(x):
        '''Convert Fahrenheit to Celsius'''
        return (x - 32) * 5 / 9
    ```

#### **Conditional Statements**
- Direct program execution based on conditions.  
  - Example:
    ```python
    number = -4

    if number > 0:
        print('Number is positive.')
    elif number == 0:
        print('Number is zero.')
    else:
        print('Number is negative.')
    ```

---

### **3. Naming Rules and Conventions**
- No spaces in names.
- Names can mix upper and lower case but **cannot start with a number**.
- Use **snake_case** for variables and function names.  
  - Example: `student_name` instead of `sn`
- Descriptive names improve code readability.

---

### **4. The Zen of Python**
Python’s guiding principles emphasize clarity and simplicity:
- **Beautiful** is better than ugly.
- **Explicit** is better than implicit.
- **Simple** is better than complex.
- **Readability counts.**
- **Errors should never pass silently.**

---

### **5. PEP 8 Style Guide**
- **PEP 8** (Python Enhancement Proposals):  
  A trusted resource offering detailed guidelines for Python style and conventions.  
  Bookmark this guide for reference when writing Python code.