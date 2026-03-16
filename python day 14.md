# subprocess
The **`subprocess` module** in Python lets you run **system commands or external programs** directly from a Python script. It is widely used in **DevOps, automation, and system administration** because it allows Python to interact with the operating system.

In simple terms:
**Python → executes Linux/Windows commands → returns the output.**

For someone preparing for **DevOps roles (as you are)**, `subprocess` is important because many automation scripts run commands like `docker`, `kubectl`, `git`, or `systemctl`.

---

## Basic Example

```python
import subprocess

result = subprocess.run(["ls", "-l"], capture_output=True, text=True)

print(result.stdout)
```

**Explanation**

* `subprocess.run()` → runs the command
* `["ls", "-l"]` → command + arguments
* `capture_output=True` → captures command output
* `text=True` → output returned as string

Output will show the **list of files in the directory**.

---

## Important Functions in `subprocess`

| Function                    | Purpose                            |
| --------------------------- | ---------------------------------- |
| `subprocess.run()`          | Recommended way to run commands    |
| `subprocess.call()`         | Runs command and returns exit code |
| `subprocess.check_output()` | Returns command output             |
| `subprocess.Popen()`        | Advanced control over processes    |

---

## Example 1 – Check Linux Disk Usage (DevOps)

```python
import subprocess

result = subprocess.run(["df", "-h"], capture_output=True, text=True)

print(result.stdout)
```

Shows **disk usage of servers**.

---

## Example 2 – Run Git Command

```python
import subprocess

result = subprocess.run(["git", "status"], capture_output=True, text=True)

print(result.stdout)
```

Used in **CI/CD automation scripts**.

---

## Example 3 – Restart a Service

```python
import subprocess

subprocess.run(["systemctl", "restart", "nginx"])
```

Used for **server automation**.

---

## Example 4 – Capture Error Output

```python
import subprocess

result = subprocess.run(["ls", "wrongfile"], capture_output=True, text=True)

print("Output:", result.stdout)
print("Error:", result.stderr)
```

Useful for **troubleshooting scripts**.

---

## Example 5 – Using `Popen`

```python
import subprocess

process = subprocess.Popen(["ping", "google.com"], stdout=subprocess.PIPE)

for line in process.stdout:
    print(line.decode().strip())
```

Used when you want **real-time output**.

---

## Real DevOps Use Cases

| Use Case              | Example Command           |
| --------------------- | ------------------------- |
| Docker automation     | `docker ps`               |
| Kubernetes deployment | `kubectl get pods`        |
| Git automation        | `git pull`                |
| Server monitoring     | `top`, `df -h`, `free -m` |
| Service management    | `systemctl restart nginx` |

Example:

```python
import subprocess

pods = subprocess.run(["kubectl", "get", "pods"], capture_output=True, text=True)
print(pods.stdout)
```

---

## Important Interview Points

**1️⃣ Why use subprocess instead of os.system()?**
`subprocess` is **more secure, flexible, and powerful**.

**2️⃣ What does `capture_output=True` do?**
Captures stdout and stderr.

**3️⃣ What does `check=True` do?**

```python
subprocess.run(["ls"], check=True)
```

Raises an **exception if the command fails**.

**4️⃣ What is `stdout=subprocess.PIPE`?**
It allows Python to **capture command output**.

---
# psutil
The **`psutil`** library (Process and System Utilities) is a Python library used to **monitor system resources and processes**. It’s very popular in **DevOps, system monitoring, and automation scripts** because it can read CPU, memory, disk, network, and running processes directly from Python.

Think of it as Python giving you information similar to Linux commands like **`top`**, **`htop`**, **`df -h`**, or **`free -m`**.

---

## Installing `psutil`

```bash
pip install psutil
```

or

```bash
pip3 install psutil
```

---

## Basic Example

```python
import psutil

print(psutil.cpu_percent())
```

Output example:

```
23.5
```

This shows the **CPU usage percentage**.

---

## Common System Monitoring Examples

### 1. CPU Usage

```python
import psutil

print("CPU Usage:", psutil.cpu_percent(interval=1), "%")
```

This checks CPU usage over **1 second**.

---

### 2. Memory Usage

```python
import psutil

memory = psutil.virtual_memory()

print("Total Memory:", memory.total)
print("Used Memory:", memory.used)
print("Memory Usage:", memory.percent, "%")
```

Similar to the Linux command:

```
free -m
```

---

### 3. Disk Usage

```python
import psutil

disk = psutil.disk_usage('/')

print("Total Disk:", disk.total)
print("Used Disk:", disk.used)
print("Disk Usage:", disk.percent, "%")
```

Equivalent to:

```
df -h
```

---

### 4. Network Statistics

```python
import psutil

net = psutil.net_io_counters()

print("Bytes Sent:", net.bytes_sent)
print("Bytes Received:", net.bytes_recv)
```

---

### 5. List Running Processes

```python
import psutil

for process in psutil.process_iter(['pid', 'name']):
    print(process.info)
```

This shows **PID and process names** running on the system.

---

## Real DevOps Example – Simple Monitoring Script

```python
import psutil

print("CPU:", psutil.cpu_percent(), "%")
print("Memory:", psutil.virtual_memory().percent, "%")
print("Disk:", psutil.disk_usage('/').percent, "%")
```

Output:

```
CPU: 22 %
Memory: 65 %
Disk: 40 %
```

This type of script is used in **server monitoring automation**.

---

## DevOps Use Cases

| Use Case                   | Example                       |
| -------------------------- | ----------------------------- |
| Server monitoring          | CPU, memory alerts            |
| Health check scripts       | Check resource usage          |
| Kubernetes node monitoring | Track system metrics          |
| Automation scripts         | Trigger actions when CPU high |
| Custom monitoring tools    | Alternative to Nagios/Zabbix  |

Example:

```python
import psutil

if psutil.cpu_percent() > 80:
    print("High CPU usage detected!")
```

---

## Short Interview Definition

**psutil** is a Python library used to **retrieve system information such as CPU usage, memory usage, disk usage, network statistics, and running processes**, commonly used in **DevOps monitoring and automation scripts**.

---

