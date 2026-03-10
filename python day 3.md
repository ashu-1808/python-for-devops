**Control structures in Python** are used to control the **flow of program execution**—that is, which code runs, when it runs, and how many times it runs.

There are three main types.

### 1. Conditional Statements (Decision Making)

A **conditional statement** is a programming structure used to **execute different blocks of code based on whether a condition is true or false**.


**Example**

```python
age = 20

if age >= 18:
    print("Adult")
else:
    print("Minor")
```
To ask the user to **enter their age**, use the `input()` function and convert it to an integer:

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

The program will display **“Enter your age:”**, wait for the user to type a number, and then print **Adult** or **Minor** based on the entered age.


Types:

1. if – Executes a block of code when a condition is true.
2. elif – Checks another condition if the previous condition is false.
3. else – Executes a block of code when all conditions are false.

Example:

```python
marks = int(input("Enter your marks: "))

if marks >= 90:
    print("Grade A+")
elif marks >= 80:
    print("Grade A")
elif marks >= 70:
    print("Grade B")
elif marks >= 60:
    print("Grade C")
elif marks >= 50:
    print("Grade D")
elif marks >= 40:
    print("Grade E")
else:
    print("Fail")
```

### 2. Looping Statements (Repetition)

A **loop** is a control structure used to **repeat a block of code multiple times until a condition is met or for a specific number of iterations**.


**For Loop**

```python
for i in range(5):
    print(i)
```

**While Loop**

```python
i = 1

while i <= 3:
    print(i)
    i += 1
```

### 3. Control Statements (Loop Control)

These control loop behavior.

**break**

```python
for i in range(5):
    if i == 3:
        break
    print(i)
```

**continue**

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

**pass**

```python
for i in range(3):
    pass
```

### Short version (for notes / README)

Control structures in Python:

* **Conditional:** `if`, `elif`, `else`
* **Loops:** `for`, `while`
* **Control keywords:** `break`, `continue`, `pass`

**Definition:**
Control structures determine the **order and conditions under which code executes in a program.**
