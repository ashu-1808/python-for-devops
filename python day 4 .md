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



