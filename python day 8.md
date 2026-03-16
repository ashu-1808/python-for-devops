# Python Library
A Python library is a collection of prewritten code (modules and functions) that developers use to perform common tasks without writing the code from scratch.
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

If you want, I can also show you **10 most used Matplotlib commands beginners should know** (very useful for Python interviews and practice).
