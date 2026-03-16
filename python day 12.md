**Exception handling** in Python means **managing runtime errors so the program doesn’t crash**. Instead of stopping the program, you catch the error and handle it gracefully.

Python mainly uses **`try` and `except` blocks** for this.

Basic idea:

```python
try:
    # risky code
except:
    # code that runs if an error occurs
```

Example:

```python
try:
    num = int(input("Enter number: "))
    print(10 / num)
except:
    print("An error occurred")
```

If the user enters `0` or a non-number, the program will **not crash**.

---

## Common Types of Exceptions

| Exception           | Meaning                 | Example              |
| ------------------- | ----------------------- | -------------------- |
| `ZeroDivisionError` | Division by zero        | `10/0`               |
| `ValueError`        | Wrong data type         | `int("abc")`         |
| `FileNotFoundError` | File not found          | opening missing file |
| `IndexError`        | List index out of range | `list[5]`            |
| `KeyError`          | Dictionary key missing  | `dict["name"]`       |

Example with specific exceptions:

```python
try:
    num = int(input("Enter number: "))
    result = 10 / num
    print(result)

except ZeroDivisionError:
    print("Cannot divide by zero")

except ValueError:
    print("Invalid number")
```

---

## `else` Block

Runs **only if no error occurs**.

```python
try:
    x = 10
    y = 2
    print(x / y)

except ZeroDivisionError:
    print("Division error")

else:
    print("Program executed successfully")
```

---

## `finally` Block

Runs **always**, whether error happens or not.

```python
try:
    f = open("data.txt")
    print(f.read())

except FileNotFoundError:
    print("File not found")

finally:
    print("Program finished")
```

Often used for **closing files, network connections, or cleanup**.

---

## Simple Flow

```
try → run risky code
if error → except runs
if no error → else runs
finally → always runs
```

---

## Small DevOps-style example (reading CSV safely)

Using the Python **csv**:

```python
import csv

try:
    with open("users.csv","r") as file:
        reader = csv.reader(file)
        for row in reader:
            print(row)

except FileNotFoundError:
    print("CSV file not found")
```

This prevents automation scripts from failing if the file is missing.

---

If you're learning Python for DevOps, I can also show you **10 real DevOps error-handling examples using try–except** (SSH connections, APIs, Docker commands, file operations).
