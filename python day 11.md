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

Good—let’s step up a level. These are **more realistic DevOps-style scripts** where CSV becomes a small control plane: you keep infrastructure data in a spreadsheet-friendly file and your Python automation consumes it.

---

### 1. AWS EC2 Inventory → CSV Report

Using **boto3** to export EC2 instances.

```python
import boto3
import csv

ec2 = boto3.client('ec2', region_name='ap-south-1')

response = ec2.describe_instances()

with open("ec2_inventory.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["InstanceID", "InstanceType", "State"])

    for reservation in response["Reservations"]:
        for instance in reservation["Instances"]:
            writer.writerow([
                instance["InstanceId"],
                instance["InstanceType"],
                instance["State"]["Name"]
            ])
```

Typical use:
DevOps teams export **EC2 inventory reports** for auditing or capacity planning.

---

### 2. Kubernetes Node Report → CSV

Using **Kubernetes** via `kubectl`.

```python
import csv
import subprocess

nodes = subprocess.check_output(
    ["kubectl", "get", "nodes", "-o", "wide"]
).decode().splitlines()

with open("k8s_nodes.csv", "w", newline="") as f:
    writer = csv.writer(f)

    for line in nodes:
        writer.writerow(line.split())
```

Use case:
Export **cluster node information** for monitoring or audits.

---

### 3. Jenkins Build Result → CSV Report

Using **Jenkins** API.

```python
import requests
import csv

url = "http://jenkins-server/job/myjob/api/json"
data = requests.get(url).json()

with open("jenkins_builds.csv", "w", newline="") as f:
    writer = csv.writer(f)
    writer.writerow(["Build Number", "Result"])

    for build in data["builds"]:
        writer.writerow([build["number"], build.get("result")])
```

Use case:
CI/CD pipeline reporting.

---

### 4. Log Analyzer → Error Report

Parse application logs and export errors.

```python
import csv

logfile = "app.log"

with open(logfile) as f:
    lines = f.readlines()

with open("error_report.csv", "w", newline="") as out:
    writer = csv.writer(out)
    writer.writerow(["Error"])

    for line in lines:
        if "ERROR" in line:
            writer.writerow([line.strip()])
```

Use case:
Quick **production log analysis**.

---

### 5. Server Patch Automation (Using CSV)

CSV file:

```
server,ip
web01,192.168.1.10
web02,192.168.1.11
```

Python automation using **paramiko**:

```python
import csv
import paramiko

with open("servers.csv") as file:
    reader = csv.DictReader(file)

    for row in reader:
        ssh = paramiko.SSHClient()
        ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())

        ssh.connect(row["ip"], username="ubuntu", password="password")

        ssh.exec_command("sudo apt update && sudo apt upgrade -y")

        print("Patched:", row["server"])
        ssh.close()
```

Use case:
Automate **patching multiple servers**.

---

### 6. Docker Container Report

Export container list from **Docker**.

```python
import subprocess
import csv

containers = subprocess.check_output(
    ["docker", "ps", "--format", "{{.Names}},{{.Status}}"]
).decode().splitlines()

with open("docker_report.csv", "w", newline="") as f:
    writer = csv.writer(f)
    writer.writerow(["Container", "Status"])

    for c in containers:
        writer.writerow(c.split(","))
```

Use case:
Daily **container health report**.

---

### 7. Disk Usage Monitoring Report

```python
import subprocess
import csv

result = subprocess.check_output(["df", "-h"]).decode().splitlines()

with open("disk_usage.csv", "w", newline="") as f:
    writer = csv.writer(f)

    for line in result:
        writer.writerow(line.split())
```

Use case:
Export **Linux disk usage reports**.

---

### 8. Bulk DNS Record Generator

Generate DNS records for **Amazon Route 53**.

```python
import csv

with open("dns_records.csv", "w", newline="") as f:
    writer = csv.writer(f)
    writer.writerow(["Domain", "IP"])

    writer.writerow(["app.company.com", "192.168.1.10"])
    writer.writerow(["db.company.com", "192.168.1.20"])
```

Use case:
Prepare DNS bulk upload.

---

### 9. Kubernetes Pod Status Report

```python
import subprocess
import csv

pods = subprocess.check_output(
    ["kubectl", "get", "pods"]
).decode().splitlines()

with open("pods_report.csv", "w", newline="") as f:
    writer = csv.writer(f)

    for p in pods:
        writer.writerow(p.split())
```

Use case:
Track **pod health in Kubernetes clusters**.

---

### 10. Failed Login Detection Report

```python
import csv

logfile = "/var/log/auth.log"

with open(logfile) as f:
    logs = f.readlines()

with open("failed_logins.csv", "w", newline="") as out:
    writer = csv.writer(out)
    writer.writerow(["Failed Login"])

    for line in logs:
        if "Failed password" in line:
            writer.writerow([line.strip()])
```

Use case:
Security monitoring for Linux servers.

---



