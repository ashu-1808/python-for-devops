# Python Library
A Python library is a collection of prewritten code (modules and functions) that developers use to perform common tasks without writing the code from scratch.

## 1.Matplotlib
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

## 2.NumPy
**NumPy** (short for **Numerical Python**) is a Python library used for **fast numerical and mathematical operations**, especially with arrays and matrices. It’s a foundation for many data science and scientific computing tools.

A simple way to think about it: NumPy gives Python a powerful **array object** and a large set of **vectorized math functions** that run much faster than regular Python loops.

A short interview-style definition:
“NumPy is a Python library used for numerical computing, providing support for arrays, matrices, and mathematical functions.”

Here’s a small example.

```python
import numpy as np

arr = np.array([10, 20, 30, 40])
print(arr)
```

This creates a NumPy **array**.

You can also perform operations on the whole array at once:

```python
import numpy as np

arr = np.array([1, 2, 3, 4])
print(arr * 2)
```

Output:

```
[2 4 6 8]
```

NumPy automatically multiplies every element by 2.

Another common example:

```python
import numpy as np

arr = np.array([5, 10, 15])
print(np.mean(arr))
```

Output:

```
10.0
```

Some commonly used NumPy functions:

* `np.array()` → create an array
* `np.mean()` → average
* `np.sum()` → sum of elements
* `np.max()` → maximum value
* `np.min()` → minimum value
* `np.zeros()` → array of zeros
* `np.ones()` → array of ones

Example:

```python
import numpy as np

arr = np.zeros(5)
print(arr)
```

Output:

```
[0. 0. 0. 0. 0.]
```

One useful thing to remember:
Many libraries like **Pandas, SciPy, TensorFlow, and Matplotlib** internally use NumPy arrays.


# File handling in Python

**** means **creating, opening, reading, writing, and closing files** using Python code. It allows programs to store data permanently instead of keeping it only in memory.

A short interview definition:
**“File handling in Python is the process of reading, writing, and managing files using built-in functions like `open()`.”**

The basic syntax looks like this:

```python
file = open("filename.txt", "mode")
```

The **mode** tells Python what you want to do with the file.

| Mode | Meaning     | Description                                                                            |
| ---- | ----------- | -------------------------------------------------------------------------------------- |
| `r`  | Read        | Opens a file for reading. Error if file does not exist.                                |
| `w`  | Write       | Opens file for writing. Overwrites existing content. Creates file if it doesn't exist. |
| `a`  | Append      | Adds new data at the end of the file. Creates file if it doesn't exist.                |
| `x`  | Create      | Creates a new file. Gives error if file already exists.                                |
| `b`  | Binary mode | Used for binary files like images, videos, PDFs.                                       |
| `t`  | Text mode   | Used for text files (default mode).                                                    |
|


Common Mode Combinations
| Mode | Meaning                                   |
| ---- | ----------------------------------------- |
| `r+` | Read and write file                       |
| `w+` | Write and read (overwrites existing data) |
| `a+` | Append and read                           |
| `rb` | Read binary file                          |
| `wb` | Write binary file                         |
| `ab` | Append binary file                        |


Example: **Reading a file**

```python
file = open("data.txt", "r")
content = file.read()
print(content)
file.close()
```

Example: **Writing to a file**

```python
file = open("data.txt", "w")
file.write("Hello Python")
file.close()
```

Example: **Appending data**

```python
file = open("data.txt", "a")
file.write("\nWelcome to file handling")
file.close()
```

A better and safer way is using **`with open()`**, which automatically closes the file:

```python
with open("data.txt", "r") as file:
    print(file.read())
```

Common file methods you should know:

| Method        | Purpose          |
| ------------- | ---------------- |
| `read()`      | Read entire file |
| `readline()`  | Read one line    |
| `readlines()` | Read all lines   |
| `write()`     | Write text       |
| `close()`     | Close the file   |

In **DevOps / automation**, file handling is often used for:

* Reading **configuration files**
* Processing **log files**
* Updating **deployment scripts**
* Handling **JSON/YAML configs**

Example (reading a log file):

```python
with open("server.log", "r") as file:
    for line in file:
        print(line)
```



