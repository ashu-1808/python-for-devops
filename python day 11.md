Since you’re learning **Python for DevOps**, CSV files are often used to automate repetitive infrastructure tasks—server lists, user reports, monitoring exports, etc. Below are **10 practical DevOps automation examples using the Python CSV module**. These are the kinds of scripts people actually write in real environments.

---

## 1. Read Server Inventory from CSV

DevOps teams often store server details in a CSV file.

**servers.csv**

```
server,ip,env
web01,192.168.1.10,prod
web02,192.168.1.11,prod
db01,192.168.1.20,dev
```

**Python Script**

```python
import csv

with open('servers.csv') as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(f"Server: {row['server']} | IP: {row['ip']} | Env: {row['env']}")
```

Use case: server inventory management.

---

## 2. SSH to Servers from CSV

Using **paramiko**.

```python
import csv
import paramiko

with open("servers.csv") as file:
    reader = csv.DictReader(file)

    for row in reader:
        ssh = paramiko.SSHClient()
        ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())

        ssh.connect(row["ip"], username="ubuntu", password="password")

        stdin, stdout, stderr = ssh.exec_command("uptime")
        print(row["server"], stdout.read().decode())

        ssh.close()
```

Use case: run commands on multiple servers.

---

## 3. Generate Disk Usage Report

Collect disk usage from servers and save results.

```python
import csv

servers = ["web01", "web02", "db01"]

with open("disk_report.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["Server", "Disk Usage"])

    for s in servers:
        usage = "70%"   # simulated value
        writer.writerow([s, usage])
```

Use case: monitoring reports.

---

## 4. Parse Log Data into CSV

Convert logs into structured CSV.

```python
import csv

logs = [
    "ERROR database connection failed",
    "INFO server started",
    "WARNING high CPU usage"
]

with open("log_report.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["Level", "Message"])

    for log in logs:
        level, message = log.split(" ", 1)
        writer.writerow([level, message])
```

Use case: log analysis.

---

## 5. Export AWS Instance Data

Example export of instances to CSV.

```python
import csv

instances = [
    {"id": "i-12345", "type": "t2.micro", "region": "ap-south-1"},
    {"id": "i-67890", "type": "t2.medium", "region": "us-east-1"}
]

with open("aws_instances.csv", "w", newline="") as file:
    fieldnames = ["id", "type", "region"]

    writer = csv.DictWriter(file, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerows(instances)
```

Use case: infrastructure reporting.

---

## 6. Bulk User Creation from CSV

CSV file:

```
username,email
user1,user1@test.com
user2,user2@test.com
```

Python script:

```python
import csv

with open("users.csv") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(f"Creating user {row['username']} with email {row['email']}")
```

Use case: user provisioning automation.

---

## 7. Monitor CPU Usage and Save Report

```python
import csv
import random

servers = ["web01", "web02", "db01"]

with open("cpu_report.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["Server", "CPU Usage"])

    for s in servers:
        cpu = random.randint(10, 90)
        writer.writerow([s, f"{cpu}%"])
```

Use case: monitoring dashboards.

---

## 8. Convert CSV to JSON

Useful when moving configs to APIs.

```python
import csv
import json

data = []

with open("servers.csv") as file:
    reader = csv.DictReader(file)

    for row in reader:
        data.append(row)

with open("servers.json", "w") as file:
    json.dump(data, file, indent=4)
```

Use case: config management tools.

---

## 9. Find Failed Servers from CSV

```python
import csv

with open("status.csv") as file:
    reader = csv.DictReader(file)

    for row in reader:
        if row["status"] == "down":
            print("Alert! Server down:", row["server"])
```

Use case: alert automation.

---

## 10. CI/CD Build Report Generator

```python
import csv

builds = [
    ["Build_101", "Success"],
    ["Build_102", "Failed"],
    ["Build_103", "Success"]
]

with open("build_report.csv", "w", newline="") as file:
    writer = csv.writer(file)

    writer.writerow(["Build", "Status"])
    writer.writerows(builds)
```

Use case: CI/CD pipeline reporting.

---

If you want, I can also show you **5 advanced DevOps CSV scripts used in real companies**, such as:

* AWS EC2 inventory automation
* Kubernetes node report generator
* Jenkins build report parser
* Log analyzer for production servers
* Auto patching script for multiple servers.
