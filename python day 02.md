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

---

In Python, **string functions (string methods)** are built-in functions used to manipulate or work with text (strings).

### 1. `upper()` – Convert to uppercase

```python
text = "hello"
print(text.upper())
```

Output:

```
HELLO
```

### 2. `lower()` – Convert to lowercase

```python
text = "HELLO"
print(text.lower())
```

### 3. `title()` – Capitalize first letter of each word

```python
text = "hello world"
print(text.title())
```

### 4. `strip()` – Remove spaces from beginning and end

```python
text = "  python  "
print(text.strip())
```

### 5. `replace()` – Replace a word or character

```python
text = "I like Java"
print(text.replace("Java", "Python"))
```

### 6. `split()` – Split string into list

```python
text = "apple,banana,mango"
print(text.split(","))
```

### 7. `find()` – Find position of a substring

```python
text = "Hello Python"
print(text.find("Python"))
```

### 8. `count()` – Count occurrences

```python
text = "banana"
print(text.count("a"))
```

### Short version (good for notes)

Common Python string functions:

* `upper()`
* `lower()`
* `title()`
* `strip()`
* `replace()`
* `split()`
* `find()`
* `count()`

**Definition:**
String functions are built-in methods used to **modify, search, or format text in Python.**

If you want, I can also show **20 most important Python string methods commonly asked in interviews**.

---
