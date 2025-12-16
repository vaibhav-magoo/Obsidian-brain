**Lifting State Up** is the standard way to solve the "Sibling Problem" in React.

It describes the process of moving a state variable from a **child component** "up" to a **parent component** so that other children can use it.

### 1. The Problem (The Sibling Barrier)

In React, data flows down.

- **Parent → Child:** ✅ Easy (Props)
    
- **Child → Parent:** ✅ Easy (Functions/Callbacks)
    
- **Child → Sibling:** ❌ **Impossible** directly.
    

Imagine two components, `<InputBox />` and `<MessageList />`. If `<InputBox />` holds the state (the text you are typing), `<MessageList />` cannot see it. They are like two separate rooms with no door between them.

### 2. The Solution (Lift It Up)

To let them share data, you remove the state from the child and move it to their **closest common parent**.

The Parent becomes the "Source of Truth." It holds the water tank, and pipes water down to both children.

- **Sibling A** receives the data via props.
    
- **Sibling B** receives the data via props.
    

---

### 3. Visual Example

**Before Lifting (Broken):**

Plaintext

```
      [ Parent ]
      /        \
  [Child A]   [Child B] 
  (Has State) (Needs State)
      |           |
      |---❌----->| (Cannot pass data sideways!)
```

**After Lifting (Fixed):**

Plaintext

```
      [ Parent ] <--- STATE LIVES HERE NOW 🏠
      /        \
  (Props ↓)    (Props ↓)
    /            \
[Child A]      [Child B]
```

---

### 4. Code Example

Let's look at the Chat App we just built. This is a perfect example of Lifting State Up.

#### The "Wrong" Way (State inside Child)

If we wrote it like this, the `MessageList` would never know what was typed.

JavaScript

```
// 🔴 BAD: State is trapped inside InputBox
function InputBox() {
  const [text, setText] = useState(""); // State is here
  return <input value={text} ... />
}

function MessageList() {
  // 😭 I can't see 'text'! It's inside InputBox!
  return <div>???</div>
}
```

#### The "Right" Way (State Lifted to App)

We move `useState` to `App`, so both children can use it.

JavaScript

```
// 🟢 GOOD: State is in the Parent
function App() {
  const [text, setText] = useState(""); // 🏠 State lives here

  return (
    <>
      {/* Pass setter down so InputBox can CHANGE it */}
      <InputBox onTextChange={setText} /> 
      
      {/* Pass value down so MessageList can READ it */}
      <MessageList message={text} />      
    </>
  );
}
```

### Summary Checklist

You know you need to "Lift State Up" when:

1. Two children need to share the same data.
    
2. One child needs to change data, and another child needs to display it.