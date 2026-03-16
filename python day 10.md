In Python, the **CSV module** is used to read and write **CSV (Comma Separated Values) files**. CSV files are very common in data processing, automation scripts, and DevOps tasks where logs, reports, or configuration data are stored in tabular format.

The module you use is the built-in **csv**, so you don’t need to install anything.

---

## 1. Reading a CSV File

You can read data from a CSV file using `csv.reader`.

```python
import csv

with open('data.csv', 'r') as file:
    reader = csv.reader(file)
    
    for row in reader:
        print(row)
```

Example CSV (`data.csv`):

```
Name,Age,City
Ashu,25,Pune
Rahul,28,Mumbai
```

Output:

```
['Name', 'Age', 'City']
['Ashu', '25', 'Pune']
['Rahul', '28', 'Mumbai']
```

---

## 2. Writing to a CSV File

Use `csv.writer` to create or write data.

```python
import csv

data = [
    ['Name', 'Age', 'City'],
    ['Ashu', 25, 'Pune'],
    ['Rahul', 28, 'Mumbai']
]

with open('output.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerows(data)
```

This will create **output.csv** with the given table.

---

## 3. Reading CSV as Dictionary (Very Useful)

Use `csv.DictReader` to access data by column names.

```python
import csv

with open('data.csv', 'r') as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row['Name'], row['City'])
```

Output:

```
Ashu Pune
Rahul Mumbai
```

---

## 4. Writing CSV using Dictionary

```python
import csv

data = [
    {"Name": "Ashu", "Age": 25, "City": "Pune"},
    {"Name": "Rahul", "Age": 28, "City": "Mumbai"}
]

with open('people.csv', 'w', newline='') as file:
    fieldnames = ["Name", "Age", "City"]

    writer = csv.DictWriter(file, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerows(data)
```

---

## 5. Real DevOps Use Cases of CSV

Since you're learning **Python for DevOps**, CSV is often used for automation tasks:

| Use Case           | Example                            |
| ------------------ | ---------------------------------- |
| Server inventory   | List of servers, IPs, environments |
| User reports       | Export IAM users from AWS          |
| Log analysis       | Store parsed log results           |
| Monitoring reports | CPU / Memory usage reports         |
| CI/CD reports      | Build status export                |

Example: reading server list from CSV.

```python
import csv

with open("servers.csv") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(f"Connecting to {row['server']} with IP {row['ip']}")
```

---

## 6. Common CSV Functions

| Function           | Purpose                |
| ------------------ | ---------------------- |
| `csv.reader()`     | Read CSV rows          |
| `csv.writer()`     | Write rows             |
| `csv.DictReader()` | Read CSV as dictionary |
| `csv.DictWriter()` | Write dictionary data  |
| `writerow()`       | Write single row       |
| `writerows()`      | Write multiple rows    |

---
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


