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

If you want, I can also give you a **Python Data Structures Cheat Sheet (very useful for interviews & GitHub README)**.
