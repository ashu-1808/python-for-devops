**Modules in Python**
---
* A **module** is a file that contains **Python code (functions, variables, classes)**.
* Modules help **organize code and reuse it in different programs**.
* You can **import a module** using the `import` keyword.


---
**1.Math Module in Python**

* The **math module** is a built-in Python module that provides **mathematical functions**.
* It helps perform operations like **square root, power, factorial, trigonometry, and constants like π**.
* To use it, you must **import the module**.

**Syntax**

```python
import math
```

**Common Functions**

| Function            | Description |
| ------------------- | ----------- |
| `math.sqrt(x)`      | Square root |
| `math.pow(x, y)`    | Power (x^y) |
| `math.factorial(x)` | Factorial   |
| `math.ceil(x)`      | Round up    |
| `math.floor(x)`     | Round down  |
| `math.pi`           | Value of π  |


```python
import math

result = math.sqrt(25)

print(f"The result is {result}")
```

Explanation:

* `math` → module
* `sqrt(25)` → function from the module
* `result` → variable storing the output

Output:

```
The result is 5.0
```

Here is an **example using the `math` module for power** and storing the result:

```python
import math

result = math.pow(2, 3)

print(f"The result is {result}")
```

**Explanation**

* `math` → module
* `pow(2, 3)` → calculates (2^3)
* `result` → stores the value

**Output**

```
The result is 8.0
```


**Simple definition:**
* A **module** is a **Python file that contains functions, variables, or classes that can be reused in other programs**.
* Use a module → store output in **`result` variable** → print or use it later.

---
**2.`datetime` Module in Python**

* The **`datetime` module** is used to **work with dates and times**.
* It allows you to **create, manipulate, and format date and time values**.
* It is a **built-in module** in Python.

**Import the module**

```python
import datetime
```

**Common Classes**

| Class       | Description                                   |
| ----------- | --------------------------------------------- |
| `date`      | Represents a date (year, month, day)          |
| `time`      | Represents time (hour, minute, second)        |
| `datetime`  | Combines date and time                        |
| `timedelta` | Represents difference between two dates/times |

**Example 1**

```python
import datetime

now = datetime.datetime.now()

print("Current date and time:", now)
```
Here are **two examples using the `datetime` module**.

**Example 2: Current date and time**

```python
import datetime

now = datetime.datetime.now()
print("Current date and time:", now)
```

**Example 3: Create a specific date**

```python
import datetime

d = datetime.date(2025, 3, 12)
print("Date:", d)
```
---
**3.OS Module in Python**

* The **`os` module** is used to **interact with the operating system**.
* It helps perform tasks like **working with files, directories, environment variables, and system commands**.

**Import module**

```python
import os
```

**Common Functions**

| Function       | Description                   |
| -------------- | ----------------------------- |
| `os.getcwd()`  | Get current working directory |
| `os.listdir()` | List files in a directory     |
| `os.mkdir()`   | Create a new directory        |
| `os.remove()`  | Delete a file                 |
| `os.rename()`  | Rename a file                 |

**Example 1**

```python
import os

print(os.getcwd())
```

**Example 2**

```python
import os

files = os.listdir()
print(files)
```

**Simple definition:**
The **OS module** allows Python programs to **interact with the operating system and manage files or directories**.
---

**4.`sys` Module in Python**

* The **`sys` module** provides access to **Python interpreter and system-specific parameters**.
* It helps interact with the **runtime environment and command-line arguments**.

**Import**

```python
import sys
```

**Common Uses**

| Function      | Description                    |
| ------------- | ------------------------------ |
| `sys.argv`    | Get command-line arguments     |
| `sys.exit()`  | Exit the program               |
| `sys.path`    | Show Python module search path |
| `sys.version` | Show Python version            |

**Example 1: Python version**

```python
import sys
print(sys.version)
```

**Example 2: Command-line arguments**

```python
import sys
print(sys.argv)
```

**Simple definition:**
The **`sys` module** allows Python programs to **interact with the interpreter and system environment**.
---
**5.Paramiko in Python**

* **Paramiko** is a Python library used to **connect to remote servers using SSH**.
* It allows you to **execute commands, transfer files, and automate server tasks**.
* Commonly used in **DevOps and automation**.

**Install Paramiko**

```bash
pip install paramiko
```

**Example: Connect to a server**

```python
import paramiko

ssh = paramiko.SSHClient()
ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())

ssh.connect(hostname="192.168.1.10", username="user", password="password")

stdin, stdout, stderr = ssh.exec_command("ls")

print(stdout.read().decode())

ssh.close()
```

**Simple definition:**
**Paramiko** is a Python library used to **connect to remote servers via SSH and run commands remotely**.
---
**6.`subprocess` Module in Python**

* The **`subprocess` module** is used to **run system commands from a Python program**.
* It allows Python to **execute shell commands, scripts, or external programs**.
* Commonly used in **DevOps automation**.

**Import**

```python
import subprocess
```

**Example 1: Run a command**

```python
import subprocess

subprocess.run(["ls"])
```

This runs the **`ls` command** to list files.

**Example 2: Capture command output**

```python
import subprocess

result = subprocess.run(["echo", "Hello DevOps"], capture_output=True, text=True)

print(result.stdout)
```

Output:

```
Hello DevOps
```

**Simple definition:**
The **`subprocess` module** allows Python to **execute system commands and interact with the operating system shell**.

