
tags - [[react]] [[onClick]] 

how to pass arguments 
```jsx
// ❌ WRONG: This runs immediately when the page loads!
<button onClick={deleteUser(user.id)}>Delete</button>
```
 

### 1. The Essentials (Core Identity)

 These are general properties found on almost every event typez


|**Property**|**Type**|**Description**|
|---|---|---|
|**`e.target`**|DOM Element|The element that was **actually clicked** (could be a generic `<span>` inside your button).|
|**`e.currentTarget`**|DOM Element|The element the **event handler is attached to** (your `<button>`).|
|**`e.type`**|String|The name of the event (e.g., `"click"`, `"mousedown"`).|
|**`e.timeStamp`**|Number|The time (in milliseconds) at which the event was created.|
|**`e.isTrusted`**|Boolean|`true` if invoked by a user action; `false` if invoked by script/code.|
|**`e.nativeEvent`**|DOM Event|The original underlying browser event (if you need to access raw browser-specific data).|

---

### 2. Event Control (Methods)

These are functions you call to control how the event behaves.

|**Method**|**Description**|
|---|---|
|**`e.preventDefault()`**|Stops the browser's default action (e.g., prevents a link from navigating or a form from submitting).|
|**`e.stopPropagation()`**|Stops the event from bubbling up to parent elements.|
|**`e.isDefaultPrevented()`**|Returns `true` if `preventDefault()` was already called.|
|**e.isPropagationStopped()**|Returns `true` if `stopPropagation()` was already called.|

---

### 3. Mouse & Position Data (Specific to `onClick`)

These properties tell you _where_ the user clicked.

|**Property**|**Description**|
|---|---|
|**`e.clientX` / `e.clientY`**|Coordinates relative to the **browser window** (viewport). Useful for tooltips.|
|**`e.pageX` / `e.pageY`**|Coordinates relative to the **whole document** (includes scroll amount).|
|**`e.screenX` / `e.screenY`**|Coordinates relative to the **user's physical monitor screen**.|
|**`e.button`**|Which mouse button was pressed (`0` = Left, `1` = Middle, `2` = Right).|
|**`e.buttons`**|Used if multiple buttons are held down simultaneously (Bitmask).|

---

### 4. Modifier Keys (Key + Click)

These booleans tell you if a key was being held down _while_ the click happened.

|**Property**|**Description**|
|---|---|
|**`e.altKey`**|`true` if the **Alt** (Option) key was pressed.|
|**`e.ctrlKey`**|`true` if the **Ctrl** key was pressed.|
|**`e.shiftKey`**|`true` if the **Shift** key was pressed.|
|**`e.metaKey`**|`true` if the **Windows** or **Command** (Mac) key was pressed.|