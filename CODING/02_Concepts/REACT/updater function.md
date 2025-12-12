Here are your revision notes on **Updater Functions** in React `useState`.

### 1. What is an Updater Function?

Instead of passing a **value** to your state setter, you pass a **callback function**.

- **Standard:** `setCount(5)`
    
- **Updater:** `setCount(prevCount => prevCount + 1)`
    

### 2. The Problem: "Stale State" & Batching

React processes state updates in **batches** for performance. If you try to update the same state multiple times in one event based on its _current_ value, React might use an "old" version of the variable.

**The "Buggy" Example:**

JavaScript

```
const increment3Times = () => {
  // ❌ WRONG: 'count' is 0 for all three lines!
  setCount(count + 1); // React thinks: 0 + 1 = 1
  setCount(count + 1); // React thinks: 0 + 1 = 1
  setCount(count + 1); // React thinks: 0 + 1 = 1
};
// Result: Count increases by 1, not 3.
```

### 3. The Solution: Updater Functions

When you pass a function, React adds it to a **Queue**. It runs them in order, passing the result of the previous one into the next one.

**The Correct Example:**

JavaScript

```
const increment3Times = () => {
  // ✅ RIGHT: React takes the PREVIOUS calculation
  setCount(prev => prev + 1); // 0 -> 1
  setCount(prev => prev + 1); // 1 -> 2
  setCount(prev => prev + 1); // 2 -> 3
};
// Result: Count increases by 3.
```

### 4. Syntax Variations

You will see different naming conventions for the argument (the previous state). All are valid.

- **Prefix naming:** `setCount(prevCount => prevCount + 1)` (Most readable)
    
- **Generic naming:** `setCount(prev => prev + 1)`
    
- **Single letter:** `setCount(c => c + 1)` (Common in short code)
    

### 5. Advanced: Updating Objects safely

When using updater functions with Objects, be careful with the **syntax for returning an object**. You must wrap the object in parentheses `()`, otherwise JavaScript thinks the curly braces `{}` are the function block.

JavaScript

```
const [user, setUser] = useState({ name: "John", age: 20 });

const birthday = () => {
  // ❌ Syntax Error: JS thinks {} is the function body
  setUser(prev => { age: prev.age + 1 }); 

  // ✅ Correct: Wrap object in parentheses to return it
  setUser(prev => ({ ...prev, age: prev.age + 1 }));
};
```

### Summary Rule of Thumb

- If your new state **does not depend** on the old state (e.g., resetting a form): Pass the value directly. `setCount(0)`
    
- If your new state **depends on** the old state (e.g., counters, toggles, appending to lists): **Always use the Updater Function.** `setCount(prev => prev + 1)`
    

Would you like a practice question on converting a "buggy" array update into a correct "updater function" version?