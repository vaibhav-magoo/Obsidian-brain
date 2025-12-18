tags - [[react]]

In React, managing arrays is one of the most common tasks—from rendering a list of products to updating a shopping cart. Because React relies on **immutability** to detect changes, you cannot use "destructive" methods like `.push()` or `.splice()`.

Here are the detailed notes on the fundamental patterns for handling arrays in React.

---

## 1. The Core Principle: Immutability

When you update an array in state, React compares the **reference** of the old array to the new one. If you use `.push()`, the reference stays the same, and React won't re-render the UI.

- **Rule:** Always treat state as read-only.
    
- **Action:** Create a copy, modify the copy, and set the state to that copy.
    

---

## 2. Adding Items (Spread Operator)

The spread operator (`...`) is your best friend for adding items to the beginning or end of an array.

JavaScript

```
const [list, setList] = useState(['Item 1', 'Item 2']);

// Adding to the end
const addAtEnd = () => {
  setList([...list, 'New Item']);
};

// Adding to the beginning
const addAtStart = () => {
  setList(['New Item', ...list]);
};
```

---

## 3. Removing Items (`.filter`)

To remove an item, you use `.filter()`. It returns a **new array** containing only the elements that pass your "test."

JavaScript

```
const deleteItem = (id) => {
  // Keep everything that does NOT match the clicked ID
  setList(prevList => prevList.filter(item => item.id !== id));
};
```

---

## 4. Updating Items (`.map`)

To update a specific item (e.g., changing a price or toggling a "completed" status), use `.map()`. It allows you to transform specific elements while keeping the rest the same.

JavaScript

```
const updateItem = (id, newName) => {
  setList(prevList => 
    prevList.map(item => 
      item.id === id 
        ? { ...item, name: newName } // Update matching item
        : item                       // Keep others as they are
    )
  );
};
```

---

## 5. Calculations and Logic

You often need to derive information from your array (like a total price or a count). In React, **do this during render**, not in a separate state.

### Using `.reduce()` for Sums

JavaScript

```
// Calculate total price from an array of objects
const total = cart.reduce((sum, item) => sum + item.price, 0);
```

### Using `.some()` and `.find()`

- **`.some()`**: Returns `true/false`. Useful for checking if an item is already in the cart.
    
- **`.find()`**: Returns the actual item. Useful for getting details of a specific selection.
    

---

## 6. Rendering Lists with `key`

When using `.map()` to output JSX, you must provide a unique `key` prop to the top-level element. This helps React identify which items changed, were added, or were removed.

JavaScript

```
<ul>
  {cart.map((item) => (
    <li key={item.id}>
      {item.name} - ${item.price}
    </li>
  ))}
</ul>
```

> **Warning:** Never use the array index (`i`) as a key if the list can be reordered or filtered. Use unique IDs (like `item.id`).

---

## Summary Cheat Sheet

|**Task**|**Recommended Method**|**Returns**|
|---|---|---|
|**Add**|`[...prev, item]`|New Array|
|**Remove**|`.filter()`|New Array|
|**Update**|`.map()`|New Array|
|**Sum**|`.reduce()`|Single Value|
|**Search**|`.find()`|Single Element|
|**Exist?**|`.some()`|Boolean|

Would you like me to create a practical code example where we combine these methods to build a **"Search and Filter"** feature for your product listings?
tags
