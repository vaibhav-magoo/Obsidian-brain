tags -- [[React]] [[hooks]]
Think of `useContext` as a **Teleporter** for data.

In normal React, if the "Grandparent" component has information that the "Grandchild" needs, you have to pass that info down through every single person in the middle. This is called **Prop Drilling**, and it gets very messy.

`useContext` lets the Grandchild "teleport" the data directly from the Grandparent, skipping everyone in the middle.

---

### The Three Pieces of the Puzzle

To use Context, you need three specific parts:

1. **The Radio Station (The Context Object):** You create the "channel" where the info will be broadcast.
    
2. **The Radio Tower (The Provider):** You wrap your components in this and give it a `value`. 1This is the source of the signal.
    
3. **The Radio Receiver (`useContext`):** Any component inside the tower can use this hook to "tune in" and grab the data.
    

---

### A Real-World Scenario: "The Theme Switcher"

Imagine your app has a **Dark Mode** and a **Light Mode**. Almost every button, text box, and background needs to know which mode is active.

- **Without Context:** You have to pass `theme="dark"` into the Page, then into the Sidebar, then into the Menu, then finally into the Button. The Sidebar and Menu don't even care about the theme; they are just acting as "mailmen."
    
- **With Context:** You put a `ThemeProvider` at the very top. Now, any Button anywhere in the app can just say `useContext(ThemeContext)` and instantly know if it should be black or white.
    

---

### When to use it vs. `useState`

|**Tool**|**Purpose**|
|---|---|
|**`useState`**|For "Local" info (e.g., "Is this one checkbox checked?")|
|**`useContext`**|For "Global" info (e.g., "Who is the logged-in user?" or "What language is the app in?")|

---

### Revision Notes for `useContext`

- **Avoid Prop Drilling:** Use it when data is needed by many components at different nesting levels.
    
- **Performance Note:** Whenever the value in the Provider changes, **every** component using `useContext` for that specific context will re-render.
    
- **Setup Steps:**
    
    1. `const MyContext = createContext()`
        
    2. `<MyContext.Provider value={data}> ... </MyContext.Provider>`
        
    3. `const data = useContext(MyContext)`