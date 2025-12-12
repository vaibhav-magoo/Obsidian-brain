tags - [[React]] [[Hooks]]


---
 ROUGH NOTES
- hooks allow components to use react features
- makes a variable and a setter function 
- setter function will update its value in the [[Virtual DOM]] 
- hooks are used in function based component not [[class component]]
- you need to import React
- you can [[destructure]] it and only improt useState
- the useState function will return an array with two values, we [[destructure]] it and store it as a variable and setvariable
- we use setvariable function to update the values of our variable
- we can pass an initial state to useState()
-  

---

> [!NOTE]
> State generally refers to data or properties that need to be tracking in an application

## Importing

```jsx
import { useState } from "react";
```

## sample initialising 

```jsx
import { useState } from "react";

function FavoriteColor() {
  const [color, setColor] = useState("red");
}
```

## including an object

```jsx
const [car, setCar] = useState({
    brand: "Ford",
    model: "Mustang",
    year: "1964",
    color: "red"
  });
```
can be accessed by ```car.color```
If we only called `setCar({color: "blue"})`, this would remove the brand, model, and year from our state
[[JavaScript spread operator]]

```jsx
const updateColor = () => {
  setCar(previousState => {
    return { ...previousState, color: "blue" }
  });
}
```
