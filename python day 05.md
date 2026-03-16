A **data structure** is a way of **organizing and storing data so it can be accessed and used efficiently**.

Common Python data structures:

**List**

* Ordered collection of elements
* Allows duplicate values
* Mutable (can be changed)
* Defined using **`[]`**

**Tuple**

* Ordered collection of elements
* Allows duplicates
* Immutable (cannot be changed after creation)
* Defined using **`()`**

**Set**

* Unordered collection of unique elements
* Does **not allow duplicates**
* Mutable
* Defined using **`{}`**

**Dictionary**

* Unordered (item in dictonery does not have order)
* Collection of **key–value pairs**
* Keys must be unique
* Mutable
* Defined using **`{key: value}`**



Your list is mostly correct. I’ll **clean it slightly and fix a few small things** so it’s clearer for notes.

---

# Data Structure Functions in Python

## 1. List Functions (`list`)

| Method             | Description                          |
| ------------------ | ------------------------------------ |
| `append(x)`        | Add an item to the end               |
| `extend(iterable)` | Add elements from another iterable   |
| `insert(i, x)`     | Insert item at index `i`             |
| `remove(x)`        | Remove first occurrence of value `x` |
| `pop([i])`         | Remove and return item at index `i`  |
| `clear()`          | Remove all items                     |
| `index(x)`         | Return index of value `x`            |
| `count(x)`         | Count occurrences of `x`             |
| `sort()`           | Sort the list                        |
| `reverse()`        | Reverse the list                     |
| `copy()`           | Return a shallow copy                |

---
Here are **simple examples for each List function**.

```python
# Create a list
nums = [3, 1, 4, 1, 5]

# append(x) – Add item to end
nums.append(9)

# extend(iterable) – Add multiple items
nums.extend([2, 6])

# insert(i, x) – Insert at index
nums.insert(2, 10)

# remove(x) – Remove first occurrence
nums.remove(1)

# pop([i]) – Remove item at index
nums.pop(3)

# index(x) – Find index of value
print(nums.index(4))

# count(x) – Count occurrences
print(nums.count(1))

# sort() – Sort the list
nums.sort()

# reverse() – Reverse the list
nums.reverse()

# copy() – Copy the list
new_nums = nums.copy()

# clear() – Remove all elements
nums.clear()
```

Example output after some operations might look like:

```
[9, 6, 5, 4, 3, 2, 1]
```

---
# 2. Dictionary Functions (`dict`)

| Method                      | Description                  |
| --------------------------- | ---------------------------- |
| `get(key[,default])`        | Return value of key          |
| `keys()`                    | Return all keys              |
| `values()`                  | Return all values            |
| `items()`                   | Return key-value pairs       |
| `update(dict2)`             | Update dictionary            |
| `pop(key[,default])`        | Remove key and return value  |
| `popitem()`                 | Remove last inserted item    |
| `setdefault(key[,default])` | Get value and set if missing |
| `clear()`                   | Remove all items             |
| `copy()`                    | Return shallow copy          |
| `fromkeys(iterable,value)`  | Create dictionary from keys  |
---
Here’s a **dictionary example using 6 countries**, then applying some common dictionary functions:

```python
countries = {
    "India": "New Delhi",
    "USA": "Washington DC",
    "Japan": "Tokyo",
    "France": "Paris",
    "Germany": "Berlin",
    "Canada": "Ottawa"
}
```

**get()**

```python
print(countries.get("India"))
```

**keys()**

```python
print(countries.keys())
```

**values()**

```python
print(countries.values())
```

**items()**

```python
print(countries.items())
```

**update()**

```python
countries.update({"Australia": "Canberra"})
print(countries)
```

**pop()**

```python
countries.pop("Canada")
print(countries)
```

**copy()**

```python
new_dict = countries.copy()
print(new_dict)
```

**fromkeys()**

```python
keys = ["Brazil", "Italy", "Spain"]
new_dict = dict.fromkeys(keys, "Capital")
print(new_dict)
```

If you'd like, I can also show **very short single-line examples for each function**—good for quick revision or interview prep.


---

# 3. Set Functions (`set`)

| Method                       | Description                         |
| ---------------------------- | ----------------------------------- |
| `add(x)`                     | Add element                         |
| `update(iterable)`           | Add multiple elements               |
| `remove(x)`                  | Remove element (error if not found) |
| `discard(x)`                 | Remove element (no error)           |
| `pop()`                      | Remove random element               |
| `clear()`                    | Remove all elements                 |
| `copy()`                     | Return shallow copy                 |
| `union(set2)`                | Combine sets                        |
| `intersection(set2)`         | Common elements                     |
| `difference(set2)`           | Elements only in first set          |
| `symmetric_difference(set2)` | Elements in either but not both     |
| `issubset(set2)`             | Check subset                        |
| `issuperset(set2)`           | Check superset                      |
| `isdisjoint(set2)`           | Check no common elements            |
---
Here’s a **simple set example**:

Here are **simple Python examples for each `set` method** using small sets.

```python
# Create sets
set1 = {"apple", "banana", "mango"}
set2 = {"banana", "grape", "orange"}
```

**add(x)**

```python
set1.add("kiwi")
print(set1)
```

**update(iterable)**

```python
set1.update(["papaya", "cherry"])
print(set1)
```

**remove(x)**

```python
set1.remove("banana")
print(set1)
```

**discard(x)**

```python
set1.discard("grape")
print(set1)
```

**pop()**

```python
set1.pop()
print(set1)
```

**copy()**

```python
new_set = set1.copy()
print(new_set)
```

**union(set2)**

```python
print(set1.union(set2))
```

**intersection(set2)**

```python
print(set1.intersection(set2))
```

**difference(set2)**

```python
print(set1.difference(set2))
```

**symmetric_difference(set2)**

```python
print(set1.symmetric_difference(set2))
```

**issubset(set2)**

```python
print(set1.issubset(set2))
```

**issuperset(set2)**

```python
print(set1.issuperset(set2))
```

**isdisjoint(set2)**

```python
print(set1.isdisjoint(set2))
```

**clear()**

```python
set1.clear()
print(set1)
```

If you'd like, I can also make a **very short “one-line cheat sheet” for all Python data-structure methods (List, Tuple, Set, Dictionary)** that’s useful for quick revision.


**Key points**
* Sets **do not allow duplicate values**.
* Sets are **unordered collections**.
* Defined using **`{}`**.


---

# 4. Tuple Functions (`tuple`)

| Function   | Description              |
| ---------- | ------------------------ |
| `count(x)` | Count occurrences of `x` |
| `index(x)` | Return index of `x`      |
| `len(x)`   | Number of elements       |
| `max(x)`   | Largest value            |
| `min(x)`   | Smallest value           |
| `sum(x)`   | Sum of numeric values    |

---
Here is a **different tuple example** using names:

Here are **simple examples using a tuple** for each function:

```python
numbers = (5, 10, 15, 10, 20)
```

**count(x)**

```python
print(numbers.count(10))
```

**index(x)**

```python
print(numbers.index(15))
```

**len(x)**

```python
print(len(numbers))
```

**max(x)**

```python
print(max(numbers))
```

**min(x)**

```python
print(min(numbers))
```

**sum(x)**

```python
print(sum(numbers))
```

Example output:

```
2
2
5
20
5
60
```

---
**Quick Comparison**

| Structure  | Ordered | Mutable | Duplicates |
| ---------- | ------- | ------- | ---------- |
| List       | Yes     | Yes     | Yes        |
| Tuple      | Yes     | No      | Yes        |
| Set        | No      | Yes     | No         |
| Dictionary | Yes     | Yes     | Keys No    |
