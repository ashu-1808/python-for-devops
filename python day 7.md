**Modules in Python**
---
* A **module** is a file that contains **Python code (functions, variables, classes)**.
* Modules help **organize code and reuse it in different programs**.
* You can **import a module** using the `import` keyword.


---
**Math Module in Python**

* The **math module** is a built-in Python module that provides **mathematical functions**.
* It helps perform operations like **square root, power, factorial, trigonometry, and constants like π**.
* To use it, you must **import the module**.

**Syntax**

```python
import math
```

**Common Functions**

| Function            | Description |
| ------------------- | ----------- |
| `math.sqrt(x)`      | Square root |
| `math.pow(x, y)`    | Power (x^y) |
| `math.factorial(x)` | Factorial   |
| `math.ceil(x)`      | Round up    |
| `math.floor(x)`     | Round down  |
| `math.pi`           | Value of π  |


```python
import math

result = math.sqrt(25)

print(f"The result is {result}")
```

Explanation:

* `math` → module
* `sqrt(25)` → function from the module
* `result` → variable storing the output

Output:

```
The result is 5.0
```

Here is an **example using the `math` module for power** and storing the result:

```python
import math

result = math.pow(2, 3)

print(f"The result is {result}")
```

**Explanation**

* `math` → module
* `pow(2, 3)` → calculates (2^3)
* `result` → stores the value

**Output**

```
The result is 8.0
```


**Simple definition:**
* A **module** is a **Python file that contains functions, variables, or classes that can be reused in other programs**.
* Use a module → store output in **`result` variable** → print or use it later.

---
**`datetime` Module in Python**

* The **`datetime` module** is used to **work with dates and times**.
* It allows you to **create, manipulate, and format date and time values**.
* It is a **built-in module** in Python.

**Import the module**

```python
import datetime
```

**Common Classes**

| Class       | Description                                   |
| ----------- | --------------------------------------------- |
| `date`      | Represents a date (year, month, day)          |
| `time`      | Represents time (hour, minute, second)        |
| `datetime`  | Combines date and time                        |
| `timedelta` | Represents difference between two dates/times |

**Example 1**

```python
import datetime

now = datetime.datetime.now()

print("Current date and time:", now)
```
Here are **two examples using the `datetime` module**.

**Example 2: Current date and time**

```python
import datetime

now = datetime.datetime.now()
print("Current date and time:", now)
```

**Example 3: Create a specific date**

```python
import datetime

d = datetime.date(2025, 3, 12)
print("Date:", d)
```
