

# 🐍 Python 

Python is a high-level, interpreted programming language used to write software, automate tasks, analyze data, build web applications, and manage cloud infrastructure.

It was created by Guido van Rossum and first released in 1991.

What makes Python popular is that the syntax is very simple and close to normal English, so it’s easier to learn compared to many other languages.


---

## 📌 Objectives

* Learn Python fundamentals
* Practice problem-solving using Python
* Write automation scripts
* Prepare Python skills for **DevOps and cloud environments**

---
**Python features **

**1. Easy to Learn** – Python syntax is simple and readable.
Example:

```python
print("Hello World")
```

**2. Interpreted Language** – Code runs line by line without compilation.
Example:

```python
x = 5
print(x)
```

**3. Dynamically Typed** – No need to declare variable type.
Example:

```python
x = 10
x = "Python"
print(x)
```

**4. Object-Oriented** – Supports classes and objects.
Example:

```python
class Car:
    name = "BMW"

c = Car()
print(c.name)
```

**5. Large Standard Library** – Many built-in modules available.
Example:

```python
import math
print(math.sqrt(16))
```

**6. Cross-Platform** – Runs on Windows, Linux, and macOS.
Example:

```python
import platform
print(platform.system())
```

**7. Good for Automation** – Used to automate system tasks.
Example:

```python
import os
os.system("ls")
```

---
IDE:
An IDE (Integrated Development Environment) in Python is a software tool that helps you write, run, test, and debug Python code in one place.
Common Python IDEs:

PyCharm – very powerful for professional development

Visual Studio Code (VS Code) – lightweight and popular

Jupyter Notebook – used for data science

Spyder – used for scientific computing

IDLE – default IDE that comes with Python

For someone learning Python or using it with DevOps tools (automation, scripts, cloud), many developers prefer VS Code or PyCharm because they integrate well with Git, Docker, and terminals.
---

## 🧠 Topics Covered

### 1️⃣ Python Basics

* Variables and Data Types
* Input and Output
* Operators
* Comments

Example:

```python
name = "Ashutosh"
age = 25

print("Name:", name)
print("Age:", age)
```

---

### 2️⃣ Control Statements

* if / else
* elif
* nested conditions

Example:

```python
num = 10

if num > 0:
    print("Positive Number")
else:
    print("Negative Number")
```

---

### 3️⃣ Loops

* for loop
* while loop
* break and continue

Example:

```python
for i in range(1,6):
    print(i)
```

---

### 4️⃣ Functions

* Creating functions
* Parameters
* Return values

Example:

```python
def add(a, b):
    return a + b

print(add(5, 3))
```

---

### 5️⃣ Data Structures

* Lists
* Tuples
* Sets
* Dictionaries

Example:

```python
fruits = ["apple", "banana", "mango"]

for fruit in fruits:
    print(fruit)
```

---

### 6️⃣ File Handling

Example:

```python
file = open("test.txt", "w")
file.write("Hello Python")
file.close()
```

---

### 7️⃣ Python Modules

Example:

```python
import math

print(math.sqrt(16))
```

---

### 8️⃣ Automation Scripts

Examples in this repository may include:

* File automation
* Log parsing
* System monitoring scripts
* DevOps automation scripts

Example:

```python
import os

files = os.listdir()
print(files)
```

---

## 📂 Repository Structure

```
python-learning/
│
├── basics/
│   ├── variables.py
│   ├── operators.py
│
├── control-statements/
│   ├── if_else.py
│
├── loops/
│   ├── for_loop.py
│   ├── while_loop.py
│
├── functions/
│   ├── functions.py
│
├── data-structures/
│   ├── list.py
│   ├── dictionary.py
│
├── file-handling/
│   ├── read_file.py
│
└── automation/
    ├── system_info.py
```

---

## ⚙️ Requirements

* Python 3.x installed

Check version:

```bash
python3 --version
```

---

## ▶️ How to Run

Clone the repository:

```bash
git clone https://github.com/your-username/python-learning.git
```

Go to project directory:

```bash
cd python-learning
```

Run a Python file:

```bash
python3 filename.py
```

---

## 📚 Learning Resources

* Python Official Documentation
* Automate the Boring Stuff with Python
* Python for DevOps

---

## 🎯 Future Goals

* Build CLI tools
* Write DevOps automation scripts
* Integrate Python with **AWS, Docker, and Kubernetes**

---

⭐ If you find this repository useful, consider giving it a **star**!

---


