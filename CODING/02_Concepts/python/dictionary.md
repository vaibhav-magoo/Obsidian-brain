tags - [[coding]] [[python]]

a **Dictionary** is a built-in data type used to store data in **key-value pairs**.
In a Python dictionary, every key is unique, and it acts as a map to a specific piece of information.

## 1. Basic Syntax

Dictionaries are written with **curly braces** `{}`. Each pair is separated by a colon `:`, and pairs are separated by commas.

Python

```
# Creating a dictionary
student = {
    "name": "Alex",
    "age": 19,
    "major": "Computer Science",
    "is_enrolled": True
}
```

---

## 2. Key Characteristics

- **Ordered:** As of Python 3.7+, dictionaries maintain the order in which items were inserted.3
    
- **Mutable:** You can change, add, or remove items after the dictionary has been created.4
    
- **Unique Keys:** You cannot have two identical keys.5 If you try to add a key that already exists, it will overwrite the old value.
    
- **Fast Lookups:** Dictionaries use a process called "hashing," which allows the computer to find the value for a key almost instantly, regardless of how large the dictionary is.6
    

---

## 3. Common Operations

### Accessing Data

You can access a value by putting its key inside square brackets `[]`.

Python

```
print(student["name"])  # Output: Alex
```

### Adding or Updating

If the key exists, the value is updated. If it doesn't, a new pair is created.

Python

```
student["age"] = 20           # Updating existing key
student["university"] = "MIT"  # Adding new key-value pair
```

### Removing Data

Python

```
del student["is_enrolled"]    # Removes the key "is_enrolled"
# OR
age = student.pop("age")      # Removes "age" and returns its value
```

---

## 4. Dictionary Methods

Python provides several built-in methods to help you work with dictionaries:

|**Method**|**Description**|
|---|---|
|`.keys()`|Returns a list of all the keys in the dictionary.|
|`.values()`|Returns a list of all the values.|
|`.items()`|Returns a list of tuples (key, value pairs).|
|`.get(key)`|Returns the value of a key (safer than `[]` because it doesn't crash if the key is missing).|

---

## Why use Dictionaries instead of Lists?

A **List** is great for an ordered collection of items (like a grocery list). However, a **Dictionary** is better when you need to label your data.

- **List:** `['Alex', 19, 'CS']` — _Which one is the age? You have to remember the index._
    
- **Dictionary:** `{'name': 'Alex', 'age': 19}` — _The label 'age' makes the data self-explanatory._