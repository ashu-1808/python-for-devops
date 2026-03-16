# 1.Matplotlib
**Matplotlib** can be useful in **DevOps** when you need to **visualize operational data**—things like CPU usage over time, memory consumption, response times, or deployment metrics. While it’s not a core automation library, it’s handy for turning raw monitoring data into clear charts for analysis or reports.

A simple interview-style way to say it:
**“Matplotlib is used in DevOps to visualize monitoring and performance data such as CPU usage, memory usage, and system metrics.”**

Here are a few realistic scenarios.

**1. Visualizing server performance**

Suppose you collect CPU usage from a monitoring script:

```python
import matplotlib.pyplot as plt

cpu_usage = [40, 55, 60, 50, 70]
time = [1, 2, 3, 4, 5]

plt.plot(time, cpu_usage, marker='o')
plt.title("Server CPU Usage")
plt.xlabel("Time")
plt.ylabel("CPU %")
plt.show()
```

This quickly shows whether CPU usage is **spiking or stable**.

**2. Deployment metrics**

DevOps teams sometimes track build or deployment durations.

```python
import matplotlib.pyplot as plt

builds = ['Build1', 'Build2', 'Build3']
time_taken = [5, 7, 4]

plt.bar(builds, time_taken)
plt.title("Build Time Analysis")
plt.xlabel("Build")
plt.ylabel("Minutes")
plt.show()
```

You can visually compare **which builds are slower**.

**3. Log or monitoring analysis**

If you export metrics from tools like:

* Prometheus
* Grafana
* CloudWatch
* ELK stack

Matplotlib can generate quick **trend charts** from that data.

**4. DevOps reports**

Sometimes engineers generate **automatic PDF or dashboard reports** showing:

* uptime trends
* latency graphs
* traffic patterns

Matplotlib can generate those charts directly from scripts.

---

In real DevOps workflows, Matplotlib is usually combined with libraries like:

* `numpy` → numerical data processing
* `pandas` → log/metrics data analysis
* `requests` → pulling monitoring APIs

---

# 2.NumPy


In **DevOps**, **NumPy** is not a core tool like `os`, `subprocess`, or `paramiko`, but it can still be useful when you need **fast numerical processing, metrics analysis, or data calculations** in automation scripts.

A simple way to say it in an interview:

**“ is used in DevOps mainly for numerical computations, data analysis, and processing monitoring metrics efficiently.”**

Here are a few practical DevOps-style uses.

**1. Server metrics analysis**

When analyzing CPU, memory, or latency data collected from monitoring tools.

Example:

```python
import numpy as np

cpu_usage = np.array([45, 55, 60, 70, 50])

print("Average CPU usage:", np.mean(cpu_usage))
print("Max CPU usage:", np.max(cpu_usage))
```

This helps analyze **system performance data** quickly.

---

**2. Log or monitoring data processing**

DevOps engineers often process large datasets from tools like:

* Prometheus
* Grafana
* CloudWatch
* ELK stack

NumPy can quickly calculate **average response time, percentiles, or trends**.

Example:

```python
import numpy as np

response_time = np.array([120, 150, 100, 130, 170])
print("Average response time:", np.mean(response_time))
```

---

**3. Capacity planning**

You can analyze usage data to predict infrastructure needs.

Example:

```python
import numpy as np

traffic = np.array([200, 250, 300, 280, 350])
print("Peak traffic:", np.max(traffic))
```

---

**4. Data preprocessing for monitoring dashboards**

Sometimes DevOps pipelines process data before sending it to dashboards or ML systems.

NumPy helps with **fast mathematical transformations**.

---

**Important point (real DevOps practice):**

More commonly used Python libraries in DevOps are:

* `os` → system operations
* `subprocess` → run Linux commands
* `paramiko` → SSH automation
* `boto3` → AWS automation
* `requests` → API calls
* `json` / `yaml` → configuration handling

NumPy is used **more in data science**, but in DevOps it helps with **metrics analysis and performance calculations**.

---



