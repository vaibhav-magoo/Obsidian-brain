tags - [[React]] [[Hooks]]

---
 -  tells react to do some code when certain condition occurs
 - used in [[event listeners]] , [[DOM manipulation]] , [[Subscriptions]] , [[Fetching data from API]] , [[Clean up]] 
 -  allows you to perform side effects in your components.
 - `useEffect` accepts two arguments. The second argument is optional.
   `useEffect(<function>, <dependency>)`
 - if second argument is empty array it will only run once
 ---

### 1. The Definition

`useEffect` is a React Hook that lets you synchronize a component with an **external system** (the internet, a timer, or the manual DOM). It runs **after** the render is committed to the screen.

### 2. The Syntax

JavaScript

```jsx
useEffect(() => {
  // 1. The Code: What you want to do
  
  return () => {
    // 2. The Cleanup: (Optional) Undo what you did
  };
}, [ /* 3. The Dependencies: When to do it */ ]);
```

---

### 3. The "When" (Dependency Array)

This is the most important part to memorize for exams or interviews:

|**Dependency Array**|**Run Frequency**|
|---|---|
|**None** `useEffect(() => {})`|Runs after **every** single render.|
|**Empty** `useEffect(() => {}, [])`|Runs **only once** (on mount).|
|**Variables** `[data]`|Runs on mount + whenever **`data`** changes.|

---

### 4. Common Use Cases (The "Big Four")

1. **API Requests:** Fetching data from a server.
    
2. **Event Listeners:** Attaching `window.addEventListener`.
    
3. **Timers:** Setting up `setTimeout` or `setInterval`.
    
4. **Manual DOM:** Changing the `document.title` or using a 3rd-party library (like a map or a chart).
    

---

### 5. The Cleanup Function

If your effect does something that keeps running (like a timer or a subscription), you **must** stop it when the component disappears ("unmounts").

- **How:** Return a function inside your `useEffect`.
    
- **Why:** To prevent **memory leaks** (where the app gets slower because it's still doing old, useless work).
    

> **Analogy:** If `useEffect` is "turning on the faucet," the cleanup function is "turning it off" so the sink doesn't overflow.

---

### 💡 Top 3 Rules to Remember

1. **Don't overthink it:** If you can calculate something during render (like filtering a list), you don't need `useEffect`.
    
2. **Placement:** Hooks must always be at the **top level** of your component (not inside `if` statements or loops).
    
3. **Stability:** If you use a variable or function inside `useEffect`, it usually needs to be included in the dependency array