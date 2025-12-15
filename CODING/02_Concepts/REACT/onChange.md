tags- [[React]] [[event-handler]]

---
## Rough Notes:

- used with [[form elements]]
- similar to onClick
- using event.target.value we can get updates from it as soon as there is a change

---
### 1. What is it?

The onChange handler fires every time the value of an input changes.

In React, this means every single keystroke, checkbox toggle, or dropdown selection triggers this function immediately.

### 2. The "Controlled Component" Pattern

This is the standard way to handle inputs in React. You don't let the HTML hold the data; you force the HTML to display what is in your **State**.

**The Cycle:**

1. User types a letter.
    
2. `onChange` fires and updates the State.
    
3. React re-renders.
    
4. The Input box updates to match the new State.
    

### 3. Accessing the Data (`e.target`)

The event object `e` contains the new data, but the property you need depends on the input type.

|**Input Type**|**Property to Read**|**Example**|
|---|---|---|
|**Text / Email / Password**|`e.target.value`|`const text = e.target.value;`|
|**Dropdown (`<select>`)**|`e.target.value`|`const selection = e.target.value;`|
|**Checkbox / Radio**|**`e.target.checked`**|`const isChecked = e.target.checked;`|

---

### 4. Code Snippets (Cheat Sheet)

#### A. Text Input (String)

JavaScript

```jsx
const [name, setName] = useState("");

// Usage
<input 
  type="text" 
  value={name}                    // 1. Controlled by state
  onChange={(e) => setName(e.target.value)} // 2. Updates state
/>
```

#### B. Checkbox (Boolean)

**Critical:** You must use `checked` instead of `value`.

JavaScript

```
const [agreed, setAgreed] = useState(false);

// Usage
<input 
  type="checkbox" 
  checked={agreed}                // 1. Use 'checked', not 'value'
  onChange={(e) => setAgreed(e.target.checked)} // 2. Use .checked
/>
```

#### C. Dropdown / Select

**Critical:** Put the `onChange` on the `<select>` tag, not the options.

JavaScript

```
const [fruit, setFruit] = useState("apple");

// Usage
<select value={fruit} onChange={(e) => setFruit(e.target.value)}>
  <option value="apple">Apple</option>
  <option value="banana">Banana</option>
</select>
```