To use a CSS transition, you need two things: a **starting state** (the default style) and a **trigger state** (like `:hover`, `:focus`, or a class added via JavaScript). The `transition` property tells the browser _how_ to animate between these two states.

### The Shorthand Syntax

The most common way to write it is using the shorthand:

CSS

```
/* property | duration | timing-function | delay */
transition: all 0.3s ease-in-out 0s;
```

### Basic Example: A Hover Effect

Here is a button that smoothly changes background color and size when hovered.

CSS

```
.button {
  background-color: blue;
  width: 100px;
  
  /* 1. Define the transition on the element (NOT the hover state) */
  transition: background-color 0.5s ease, width 0.5s ease;
}

.button:hover {
  /* 2. Change the properties here */
  background-color: red;
  width: 150px;
}
```

### Breaking Down the 4 Parts

1. **`transition-property`**: What do you want to animate?
    
    - `background-color`, `transform`, `opacity`, `width`, etc.
        
    - **Tip:** Use `all` to animate every property that changes, but be careful as this can impact performance.
        
2. **`transition-duration`**: How long should it take?
    
    - Examples: `0.3s`, `500ms`.
        
    - If you omit this, the default is `0s` (instant change, no animation).
        
3. **`transition-timing-function`**: How does the speed change over time?
    
    - `linear`: Same speed from start to end.
        
    - `ease`: Starts slow, gets fast, ends slow (default).
        
    - `ease-in`: Starts slow.
        
    - `ease-out`: Ends slow.
        
4. **`transition-delay`** _(Optional)_: How long to wait before starting?
    
    - Example: `1s` (waits 1 second after you hover before moving).
        

### Performance Note

For the smoothest animations (60fps), try to stick to transitioning **`transform`** (scale, rotate, translate) and **`opacity`**. Transitioning properties that change layout (like `width`, `height`, or `margin`) forces the browser to recalculate the page structure, which can look jittery on slower devices.

### Next Step

Since you are interested in React, would you like to see how to trigger these transitions conditionally using **React state** (e.g., toggling a class when a button is clicked)?