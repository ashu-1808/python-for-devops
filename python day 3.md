**Control structures in Python** are used to control the **flow of program execution**—that is, which code runs, when it runs, and how many times it runs.

There are three main types.

### 1. Conditional Statements (Decision Making)

These execute code **based on a condition**.

**Example**

```python
age = 20

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Types:

1. if – Executes a block of code when a condition is true.
2. elif – Checks another condition if the previous condition is false.
3. else – Executes a block of code when all conditions are false.

Example:

```python
marks = 75

if marks >= 90:
    print("Grade A")
elif marks >= 60:
    print("Grade B")
else:
    print("Grade C")
```

### 2. Looping Statements (Repetition)

Loops execute code **multiple times**.

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
