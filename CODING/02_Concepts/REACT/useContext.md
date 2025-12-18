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


This is the standard way to avoid **Prop Drilling**, which is when you pass data through 5 layers of components just to reach the one at the bottom.

---

### Step 1: Create the "Broadcast Station" (`CartContext.jsx`)

In this file, you define the "Box" (Context) and the "Sender" (Provider). The Provider "wraps" your components to give them access to the data.

JavaScript

```jsx
import { createContext, useState, useContext } from 'react';

// 1. Initialize the Context box
const CartContext = createContext();

// 2. Create the Provider component
export const CartProvider = ({ children }) => {
  const [cart, setCart] = useState([]);

  const addToCart = (product) => {
    setCart((prev) => [...prev, product]);
  };

  // We "provide" the cart and the function to anyone inside
  return (
    <CartContext.Provider value={{ cart, addToCart }}>
      {children}
    </CartContext.Provider>
  );
};

// 3. Create a custom hook for easy access
export const useCart = () => useContext(CartContext);
```

---

### Step 2: Wrap Your Entire App (`main.jsx`)

To make the broadcast available everywhere, you must wrap your top-level component. This is usually done in `main.jsx` or `index.jsx`.

JavaScript

```
import { CartProvider } from './CartContext';
import App from './App';

ReactDOM.createRoot(document.getElementById('root')).render(
  <CartProvider> 
    <App />
  </CartProvider>
);
```

---

### Step 3: Listen to the Broadcast (The Example)

Now, any component—no matter how deep—can grab the `cart` data or the `addToCart` function without receiving them as props.

#### Component A: The Navbar (Shows Count)

JavaScript

```
import { useCart } from './CartContext';

function Navbar() {
  const { cart } = useCart(); // Directly grab 'cart' from the "air"
  return <nav>Items in Cart: {cart.length}</nav>;
}
```

#### Component B: The Product Card (Adds Items)

Your "Add to Cart" button can now trigger the global function directly.

JavaScript

```
import { useCart } from './CartContext';

function ProductCard({ item }) {
  const { addToCart } = useCart(); // Grab only the function you need
  return (
    <button onClick={() => addToCart(item)}>
      Add to Bag
    </button>
  );
}
```

---

### Why this fixes your specific issues:

1. **Prop Drilling:** You no longer need to pass `cart` through your `listings-container`.
    
2. **Logic Separation:** Your `App.jsx` stays clean because the shopping cart logic lives in `CartContext.jsx`.
    
3. **No More `useEffect` Loops:** You don't need a `useEffect` to sync the cart count in your Navbar; the Navbar simply reads `cart.length` from the Context, and React updates it automatically when the array changes.
    

---

### One final check on your setup:

- **The declaration error:** Ensure you have deleted the duplicate `products` array in your `App.jsx` to clear that ESLint error.
    
- **Fast Refresh:** If you still see the warning about "only exporting components," move the `useCart` hook to its own file called `useCart.js`.
    

**Would you like me to show you how to add a "Remove from Cart" function to this Context so you can use it on your new Cart Page?**