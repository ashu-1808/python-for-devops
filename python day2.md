In Python, the **`input()` function** is used to take **user input from the keyboard**. Whatever the user types is returned as a **string**.

**Basic syntax**

```python
input("message")
```

**Example 1: Simple input**

```python
name = input("Enter your name: ")
print("Hello", name)
```

If the user types `Ashu`, the output will be:

```
Hello Ashu
```

**Example 2: Input for numbers**

Since `input()` returns a **string**, you must convert it to a number if needed.

```python
age = int(input("Enter your age: "))
print(age + 5)
```

**Example 3: Taking two numbers**

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print("Sum:", a + b)
```

**Common conversions**

* `int()` → converts to integer
* `float()` → converts to decimal number
* `str()` → converts to string

Example:

```python
num = float(input("Enter a decimal number: "))
print(num)
```

**Short definition (for notes / README):**
**`input()`** is a built-in Python function used to **read data entered by the user from the keyboard.**
