tags - [[javascript]] [[coding]]

## creating an array
 Using an array literal is the easiest way to create a JavaScript Array.
```js
 const _array_name_ = [_item1_, _item2_, ...];
       or
const cars = new Array("Saab", "Volvo", "BMW");
```


## Converting an Array to a String

The JavaScript method `toString()` converts an array to a string of (comma separated) array value
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];  
document.getElementById("demo").innerHTML = fruits.toString();
```
