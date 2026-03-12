**Functions in Python**
---
* A **function** is a reusable block of code that performs a specific task.
* Functions help make programs **modular, organized, and reusable**.
* **`def`** is a Python keyword used to **define (create) a function**.
* A function can **take parameters (inputs)** and **return values**.
* Helps **reduce code repetition**.

**Basic syntax**
```python
def function_name(parameters):
    # code block
    return value
```


```python
def greet():
    print("Hello...! Welcome to the Python Session")
```
---
**Calling a function** means **executing the function by writing its name followed by parentheses `()`**.

**Syntax**

```python
function_name()
```

**Example**

```python
def greet():
    print("Hello...! Welcome to the Python Session")

greet()
```
---
Argument passing means sending values (arguments) to a function when calling it.
example1

```python
def add(a, b):
    print(f"The sum of {a} and {b} is {a + b}")

add(5, 3)
add(10, 20)
```

Output:

```
The sum of 5 and 3 is 8
The sum of 10 and 20 is 30
```
example2

```python
def add(a, b):
    print(f"The sum of {a} and {b} is {a + b}")

add(5, 3)
add(10, 20)
```

Output:

```
The sum of 5 and 3 is 8
The sum of 10 and 20 is 30
```
---
**Return value** is the **value that a function sends back to the place where it was called** using the `return` keyword.

Example using your function style:

```python
def add(a, b):
    return a + b

result = add(5, 3)
print(f"The sum of 5 and 3 is {result}")
```

Explanation:

* `return a + b` → sends the result back
* `result` → stores the returned value
* Then we print it.

**Simple definition:**
A **return value** is the **result a function gives back using `return`.**


Here is a simple **square example using a return value**:

```python
def square(num):
    return num * num

result = square(5)
print(f"The square of 5 is {result}")
```

**Explanation**

* `num` → parameter
* `return num * num` → returns the square
* `result` → stores the returned value

Output:

```
The square of 5 is 25
```
---
A **global variable** is a variable **defined outside a function and can be accessed anywhere in the program**.

Example:

```python
name = "Ashu"   # global variable

def greet():
    print(name)

greet()
```

Explanation:

* `name` is defined **outside the function**
* It can be used **inside the function**

**Simple definition:**
A **global variable** is a variable **declared outside a function and accessible throughout the program.**
---
**Argument passing** means **sending values (arguments) to a function when calling it**.

Example:

```python
def greet(name):
    print(f"Hello {name}")

greet("Ashu")
greet("Yogesh")
```

Explanation:

* `name` → parameter (in function definition)
* `"Ashu"` and `"Yogesh"` → arguments (values passed to the function)

**Simple definition:**
**Argument passing** is the process of **providing values to a function when it is called.**

