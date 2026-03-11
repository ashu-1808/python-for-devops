Here are **simple DevOps-style `for` loop examples**.

**1. Check multiple servers**

```python
servers = ["server1", "server2", "server3"]

for server in servers:
    print(f"Checking {server}")
```

**2. Deploy application to multiple environments**

```python
environments = ["dev", "test", "prod"]

for env in environments:
    print(f"Deploying to {env}")
```

**3. Restart multiple services**

```python
services = ["nginx", "docker", "jenkins"]

for service in services:
    print(f"Restarting {service}")
```

**4. Check status of containers**

```python
containers = ["web", "db", "cache"]

for container in containers:
    print(f"Checking {container} container")
```

These are **common DevOps automation patterns** where a `for` loop runs tasks on **multiple servers, services, or environments**.



Here are a few **simple DevOps-style examples where a `while` loop could be used**.

**1. Check if a server is running**

```python
import time

status = False

while not status:
    print("Checking server...")
    # simulate server check
    status = True
    time.sleep(2)

print("Server is running")
```

**2. Retry deployment until success**

```python
deployment = False

while not deployment:
    print("Trying deployment...")
    # simulate success
    deployment = True

print("Deployment successful")
```

**3. Monitor CPU usage continuously**

```python
cpu = 30

while cpu < 80:
    print("CPU usage normal")
    cpu += 10
```

**4. Wait until a file appears**

```python
file_found = False

while not file_found:
    print("Waiting for file...")
    file_found = True
```

```python
password = ""

while password != "admin123":
    password = input("Enter password: ")

print("Access granted")
```

**How it works:**
The loop keeps asking for the password until the correct password (`admin123`) is entered.



