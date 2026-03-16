* The `subprocess` module is perfect for that because most DevOps tooling—Docker, Kubernetes, Git, AWS CLI—already exposes powerful commands. Python simply orchestrates them.

Below are ten small, realistic scripts that mirror tasks engineers actually automate in CI/CD pipelines or server scripts.

---

### 1. Check Running Docker Containers

```python
import subprocess

result = subprocess.run(["docker", "ps"], capture_output=True, text=True)

print("Running Containers:\n")
print(result.stdout)
```

Use case: verify containers are running during deployment checks.

---

### 2. Automatically Pull Latest Git Code

```python
import subprocess

subprocess.run(["git", "pull", "origin", "main"])
```

Use case: update code on a server before restarting an application.

---

### 3. Get Kubernetes Pods

```python
import subprocess

result = subprocess.run(["kubectl", "get", "pods"], capture_output=True, text=True)

print(result.stdout)
```

Use case: check pod status during monitoring or troubleshooting.

---

### 4. Restart a Kubernetes Deployment

```python
import subprocess

subprocess.run([
    "kubectl",
    "rollout",
    "restart",
    "deployment",
    "nginx-deployment"
])
```

Use case: force restart of pods after configuration changes.

---

### 5. Build and Push Docker Image

```python
import subprocess

subprocess.run(["docker", "build", "-t", "myapp:v1", "."])
subprocess.run(["docker", "push", "myapp:v1"])
```

Use case: automated container builds in CI/CD.

---

### 6. Check AWS EC2 Instances

```python
import subprocess

result = subprocess.run(
    ["aws", "ec2", "describe-instances"],
    capture_output=True,
    text=True
)

print(result.stdout)
```

Use case: retrieve EC2 instance information from automation scripts.

---

### 7. Create an S3 Bucket

```python
import subprocess

subprocess.run([
    "aws",
    "s3",
    "mb",
    "s3://my-devops-bucket"
])
```

Use case: infrastructure setup automation.

---

### 8. Check Disk Usage on Server

```python
import subprocess

result = subprocess.run(["df", "-h"], capture_output=True, text=True)

print(result.stdout)
```

Use case: server health monitoring scripts.

---

### 9. Check Git Branch and Status

```python
import subprocess

result = subprocess.run(["git", "status"], capture_output=True, text=True)

print(result.stdout)
```

Use case: CI pipeline verification before building.

---

### 10. Deploy Kubernetes YAML File

```python
import subprocess

subprocess.run([
    "kubectl",
    "apply",
    "-f",
    "deployment.yaml"
])
```

Use case: automated Kubernetes deployments.

---

### A Practical DevOps Pattern

Most real scripts follow this pattern:

```python
import subprocess

result = subprocess.run(
    ["command", "argument"],
    capture_output=True,
    text=True
)

if result.returncode == 0:
    print("Command executed successfully")
else:
    print("Error:", result.stderr)
```

This lets your automation:

* run a command
* capture output
* detect errors

Exactly how CI/CD systems operate.

---
When you run production servers on Ubuntu, simple Python monitoring scripts can be surprisingly useful. Many teams still write small utilities like these for cron jobs, health checks, or lightweight monitoring. The `psutil` library makes it easy because it exposes the same metrics you’d normally inspect with `top`, `free`, `df`, or `ps`.

Below are ten practical examples you could actually run on an Ubuntu server.

---

### 1. CPU Usage Alert

Warn if CPU usage goes above a threshold.

```python
import psutil

cpu = psutil.cpu_percent(interval=1)

if cpu > 80:
    print("⚠ High CPU Usage:", cpu, "%")
else:
    print("CPU Normal:", cpu, "%")
```

Typical use: alert script in a cron job.

---

### 2. Memory Usage Monitor

```python
import psutil

memory = psutil.virtual_memory()

print("Total Memory:", memory.total)
print("Used Memory:", memory.used)
print("Memory Usage:", memory.percent, "%")
```

Equivalent to checking `free -m`.

---

### 3. Disk Usage Alert

```python
import psutil

disk = psutil.disk_usage('/')

if disk.percent > 85:
    print("⚠ Disk almost full:", disk.percent, "%")
else:
    print("Disk usage normal:", disk.percent, "%")
```

Useful for preventing disk outages on servers.

---

### 4. List Running Processes

```python
import psutil

for process in psutil.process_iter(['pid', 'name']):
    print(process.info)
```

Similar to `ps aux`.

---

### 5. Check If a Service Is Running

Example: verify **nginx** process.

```python
import psutil

for process in psutil.process_iter(['name']):
    if process.info['name'] == 'nginx':
        print("Nginx is running")
```

Often used in health-check scripts.

---

### 6. Network Traffic Monitor

```python
import psutil

net = psutil.net_io_counters()

print("Bytes Sent:", net.bytes_sent)
print("Bytes Received:", net.bytes_recv)
```

Useful for monitoring traffic spikes.

---

### 7. Monitor Top CPU Processes

```python
import psutil

for process in psutil.process_iter(['pid','name','cpu_percent']):
    print(process.info)
```

Helps detect which process is consuming CPU.

---

### 8. Continuous CPU Monitoring (like `top`)

```python
import psutil
import time

while True:
    print("CPU Usage:", psutil.cpu_percent(interval=1), "%")
    time.sleep(5)
```

Runs continuously like a lightweight monitoring tool.

---

### 9. System Uptime Script

```python
import psutil
import datetime

boot = datetime.datetime.fromtimestamp(psutil.boot_time())
print("System Boot Time:", boot)
```

Useful for server health dashboards.

---

### 10. Full Server Health Check Script

A small script combining multiple metrics.

```python
import psutil

print("CPU Usage:", psutil.cpu_percent(interval=1), "%")
print("Memory Usage:", psutil.virtual_memory().percent, "%")
print("Disk Usage:", psutil.disk_usage('/').percent, "%")
print("Number of Processes:", len(psutil.pids()))
```

This is the kind of script teams sometimes run via **cron every few minutes**.

---

One practical improvement (common in DevOps) is to combine this with alerts. For example: if CPU or disk crosses a threshold, send a Slack message, email, or log to a monitoring system.

If you'd like, I can also show you a **very realistic DevOps mini-project: a Python monitoring tool that checks CPU, RAM, disk, and automatically restarts a service when it crashes**. It’s a great practice exercise.


