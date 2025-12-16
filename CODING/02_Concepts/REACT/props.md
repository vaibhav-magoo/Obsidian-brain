[[react]]

Here are detailed revision notes on **Props (Properties)** in React. You can save this as a reference guide.

---

# ⚛️ React Props: Revision Notes

## 1. What are Props?

- **Definition:** Short for "Properties." They are inputs that you pass into a React component.
    
- **Analogy:**
    
    - **HTML:** Like attributes (`<img src="..." />`). `src` is a prop.
        
    - **JavaScript:** Like function arguments (`function add(a, b)`). `a` and `b` are props.
        
- **Purpose:** To make components **dynamic** and **reusable**. Without props, a component would always render the exact same text/UI.
    

---

## 2. The Golden Rule of Props

> **Props are Read-Only (Immutable).**

- A child component **cannot change** its own props.
    
- Props are "owned" by the Parent.
    
- **Wrong:** `props.name = "Mike";` (This will throw an error).
    
- **Right:** If the Child wants to change data, it must ask the Parent to change the state via a callback function.
    

---

## 3. How to Pass Props (The Parent)

You pass props in the JSX of the parent component.

### Strings (Quotes)

If passing a hardcoded string, use double quotes.

JavaScript

```
<WelcomeMessage name="John" city="New York" />
```

### Anything Else (Curly Braces `{}`)

If passing numbers, booleans, variables, objects, or functions, you **must** use curly braces.

JavaScript

```
<Profile 
    age={25}                  // Number
    isOnline={true}           // Boolean
    hobbies={["coding", "gym"]} // Array
    user={userDataObject}     // Object
    onLogout={handleLogout}   // Function
/>
```

---

## 4. How to Receive Props (The Child)

There are two ways to write the child component logic.

### Method A: The `props` Object (The Old Way)

React collects all attributes into a single object called `props`.

JavaScript

```
function WelcomeMessage(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

### Method B: Destructuring (The Modern Standard)

This is cleaner. You unpack the properties directly in the function signature.

JavaScript

```
//         👇 Extract specific props immediately
function WelcomeMessage({ name, city }) {
  return <h1>Hello, {name} from {city}!</h1>;
}
```

---

## 5. Special Prop: `children`

React has a built-in prop called `children`. This allows you to pass content **between** the opening and closing tags of your component, rather than as an attribute.

**Parent:**

JavaScript

```
<Card>
    <h2>Title</h2>
    <p>This paragraph is the child.</p>
</Card>
```

**Child (Card):**

JavaScript

```
function Card({ children }) {
  return <div className="card-border">{children}</div>;
}
```

- **Use Case:** Layout components (Boxes, Modals, Cards) that wrap around other content.
    

---

## 6. Passing Functions ([[Lifting State Up]])

Props usually pass data **down** (Parent → Child). To communicate **up** (Child → Parent), we pass a function as a prop.

- **Concept:** The "Remote Control" signal.
    
- **Pattern:**
    
    1. Parent defines `const handleClick = () => ...`
        
    2. Parent passes it: `<Button onAction={handleClick} />`
        
    3. Child calls it: `<button onClick={onAction}>Click</button>`
        

---

## 7. Default Props

You can define what happens if a parent _forgets_ to pass a prop.

**Using default parameters (ES6):**

JavaScript

```
function Button({ text = "Click Me", color = "blue" }) {
  // If parent passes nothing, text is "Click Me" and color is "blue"
  return <button className={color}>{text}</button>;
}
```

---

## 8. Prop Drilling (The Problem)

This is a term used when you have to pass data through many layers of components that don't actually use the data, just to get it to a child at the bottom.

Flow:

App (Has Data) → Layout (Doesn't need it) → Header (Doesn't need it) → UserAvatar (Needs Data).

- **Note:** If you find yourself drilling props down 4-5 layers, you might need **Context API** or a state management library (like Redux or Zustand) later on.
    

---

## Summary Table

|**Concept**|**Syntax Example**|**Description**|
|---|---|---|
|**Pass String**|`title="Hello"`|Use quotes for static text.|
|**Pass Variable**|`count={count}`|Use `{}` for dynamic values.|
|**Receive Props**|`({ title })`|Destructure in the function argument.|
|**Read-Only**|`props.title = "X"` ❌|Never modify props directly.|
|**Children**|`{children}`|Renders content inside component tags.|
|**Functions**|`onClick={doStuff}`|Used to send signals back up to Parent.|

### Next Step

Would you like to try a small "Prop Challenge" where I give you a broken component structure, and you have to fix the props to make it work?