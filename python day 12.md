When interviewers ask about **try–except in Python**, they usually want to see if you understand **how to handle failures in automation scripts**—things like missing files, API failures, or command errors. Here are **five common interview-style questions**, with short explanations and examples.

---

**1. What is exception handling in Python? Why is it important in DevOps scripts?**

Exception handling is a way to **manage runtime errors without stopping the program**. Python uses `try`, `except`, `else`, and `finally` blocks to catch and handle errors.

Example:

```python
try:
    num = int(input("Enter number: "))
    print(10 / num)
except ZeroDivisionError:
    print("Cannot divide by zero")
```

Why it matters in DevOps: automation scripts must continue running even if **one task fails**.

---

**2. What is the difference between `except` and `except Exception as e`?**

`except` catches **any error**, but it doesn't give details.
`except Exception as e` catches the error and stores the message in variable `e`.

Example:

```python
try:
    x = int("abc")
except Exception as e:
    print("Error:", e)
```

Output will show the **actual error message**, which helps debugging CI/CD pipelines.

---

**3. What is the difference between `else` and `finally` in a try–except block?**

* `else` runs **only if no exception occurs**
* `finally` runs **always**, whether an error happens or not

Example:

```python
try:
    x = 10 / 2
except ZeroDivisionError:
    print("Error")
else:
    print("Success")
finally:
    print("Execution finished")
```

`finally` is often used to **close files or connections**.

---

**4. How do you handle multiple exceptions in Python?**

You can define **multiple except blocks**.

Example:

```python
try:
    num = int(input("Enter number: "))
    result = 10 / num
except ValueError:
    print("Invalid number")
except ZeroDivisionError:
    print("Division by zero")
```

This helps handle different types of errors differently.

---

**5. Give a real DevOps example where try–except is useful.**

A script reading server data from a CSV file may fail if the file doesn't exist. Using the Python **csv**, you can handle that safely:

```python
import csv

try:
    with open("servers.csv") as file:
        reader = csv.reader(file)
        for row in reader:
            print(row)
except FileNotFoundError:
    print("Server inventory file not found")
```

This prevents automation scripts from crashing when configuration files are missing.

---

A tip from real interviews: after explaining try–except, many interviewers follow up with **“What are the most common Python exceptions?”** (like `ValueError`, `TypeError`, `IndexError`, etc.). Being ready with those examples makes your answer stronger.


---
Here are ** practical DevOps-style error-handling examples using `try–except`** in Python. These show how automation scripts avoid crashing when something fails.

---

### 1. Handle Missing Configuration File

```python
try:
    file = open("config.txt")
    print(file.read())
except FileNotFoundError:
    print("Configuration file not found")
```

Use case: DevOps scripts often read config files before running.

---

### 2. Reading CSV Safely

Using the Python **csv**.

```python
import csv

try:
    with open("servers.csv") as file:
        reader = csv.reader(file)
        for row in reader:
            print(row)
except FileNotFoundError:
    print("Server list file missing")
```

Use case: reading **server inventory files**.

---

### 3. Handling API Request Failure

```python
import requests

try:
    response = requests.get("https://api.github.com")
    print(response.status_code)
except requests.exceptions.RequestException:
    print("API request failed")
```

Use case: calling APIs from CI/CD pipelines.

---

### 4. Handling Division or Calculation Errors

```python
try:
    cpu = 100
    servers = 0
    avg = cpu / servers
    print(avg)
except ZeroDivisionError:
    print("Server count cannot be zero")
```

Use case: monitoring calculations.

---

### 5. SSH Connection Failure

Using the Python SSH library **paramiko**.

```python
import paramiko

try:
    ssh = paramiko.SSHClient()
    ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())
    ssh.connect("192.168.1.10", username="ubuntu", password="pass")
except Exception:
    print("SSH connection failed")
```

Use case: remote server automation.

---

### 6. Running Linux Commands Safely

```python
import subprocess

try:
    subprocess.run(["docker","ps"], check=True)
except subprocess.CalledProcessError:
    print("Docker command failed")
```

Use case: executing infrastructure commands.

---

### 7. Reading Environment Variables

```python
import os

try:
    db_password = os.environ["DB_PASSWORD"]
    print(db_password)
except KeyError:
    print("Environment variable not set")
```

Use case: CI/CD secrets management.

---

### 8. JSON Parsing Error

```python
import json

try:
    data = json.loads('{"name": "server1"}')
    print(data["name"])
except json.JSONDecodeError:
    print("Invalid JSON format")
```

Use case: API responses in automation.

---

### 9. Kubernetes Command Failure

Example when interacting with **Kubernetes**.

```python
import subprocess

try:
    subprocess.run(["kubectl","get","pods"], check=True)
except subprocess.CalledProcessError:
    print("Failed to fetch Kubernetes pods")
```

Use case: cluster automation scripts.

---

### 10. File Permission Error

```python
try:
    with open("/root/secret.txt") as file:
        print(file.read())
except PermissionError:
    print("Permission denied")
```

Use case: restricted system files.

---

A common **DevOps best practice** is combining multiple exception types:

```python
try:
    # risky operation
    pass
except FileNotFoundError:
    print("File missing")
except PermissionError:
    print("Permission issue")
except Exception as e:
    print("Unexpected error:", e)
```

This keeps automation scripts **stable in production pipelines**.

---
