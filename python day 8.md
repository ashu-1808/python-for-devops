# Python Library
A Python library is a collection of prewritten code (modules and functions) that developers use to perform common tasks without writing the code from scratch.

# 1.Matplotlib
**Matplotlib** is a popular Python library used to create **graphs and visualizations** from data. It helps turn numbers into charts like line graphs, bar charts, pie charts, and histograms.

In simple terms:
**Matplotlib is a Python library used for data visualization (creating graphs and charts).**

Most plotting in Matplotlib is done using the module **`matplotlib.pyplot`**, usually imported like this:

```python
import matplotlib.pyplot as plt
```

Here are a few small examples so the idea becomes clear.

A **line chart** (very common):

```python
import matplotlib.pyplot as plt

x = [1,2,3,4]
y = [10,20,15,25]

plt.plot(x, y)
plt.title("Simple Line Chart")
plt.xlabel("X values")
plt.ylabel("Y values")
plt.show()
```

A **bar chart**:

```python
import matplotlib.pyplot as plt

subjects = ['Math','Science','English']
marks = [80,90,75]

plt.bar(subjects, marks)
plt.show()
```


```python
import matplotlib.pyplot as plt

subject = ['Math', 'Science', 'English', 'History']
marks = [85, 94, 67, 85]

# line graph
plt.plot(subject, marks)

plt.title("Student Marks")
plt.xlabel("Subjects")
plt.ylabel("Marks")

plt.show()
```

What each line does:

* `plt.plot(subject, marks)` → draws a **line chart**
* `plt.title()` → adds the graph title
* `plt.xlabel()` → label for X-axis
* `plt.ylabel()` → label for Y-axis
* `plt.show()` → displays the graph

You can also add markers to make the graph clearer:

```python
plt.plot(subject, marks, marker='o')
```





A **pie chart**:

```python
import matplotlib.pyplot as plt

data = [40,30,30]
labels = ['Python','Java','C++']

plt.pie(data, labels=labels)
plt.show()
```


Common charts you can create with Matplotlib include:

* Line chart
* Bar chart
* Pie chart
* Histogram
* Scatter plot

A short **interview definition** you can remember:

“Matplotlib is a Python library used for creating data visualizations such as line graphs, bar charts, and pie charts.”

# 2.NumPy
In **DevOps**, **NumPy** is not a core tool like `os`, `subprocess`, or `paramiko`, but it can still be useful when you need **fast numerical processing, metrics analysis, or data calculations** in automation scripts.

A simple way to say it in an interview:

**“NumPy is used in DevOps mainly for numerical computations, data analysis, and processing monitoring metrics efficiently.”**

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

If you want, I can also show you **Top 15 Python libraries every DevOps engineer should know** (very common interview question).


