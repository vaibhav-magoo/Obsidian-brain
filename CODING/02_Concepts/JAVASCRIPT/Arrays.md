tags - [[javascript]] [[coding]]


- With JavaScript, the full array can be accessed by referring to the array name:
- Arrays are a special type of objects. The `typeof` operator in JavaScript returns "object" for arrays.
- Arrays use **numbers** to access its "elements" Objects use **names** to access its "members"
- You can have objects in an Array. You can have functions in an Array. You can have arrays in an Array

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


## looping through Arrays
**A. The `for` loop (Classic)** Good for when you need the index number.

JavaScript

```js
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```

**B. The `forEach` loop (Modern & Clean)** Better for simply reading through items.

JavaScript

```js
fruits.forEach(function(fruit) {
    console.log(fruit);
});
```



### **Properties**

| **Property**  | **Description**                                               | **Example**                      |
| ------------- | ------------------------------------------------------------- | -------------------------------- |
| `length`      | Returns the number of elements in the array.                  | `arr.length`                     |
| `constructor` | Returns the function that created the Array object.           | `arr.constructor`                |
| `prototype`   | Allows you to add properties and methods to the Array object. | `Array.prototype.myMethod = ...` |

### **Basic Modification (Mutates Original Array)**

These methods change the array they are called on.

|**Method**|**Description**|**Example**|
|---|---|---|
|`push()`|Adds one or more elements to the **end**. Returns new length.|`arr.push(4)`|
|`pop()`|Removes the **last** element. Returns that element.|`arr.pop()`|
|`unshift()`|Adds one or more elements to the **beginning**. Returns new length.|`arr.unshift(0)`|
|`shift()`|Removes the **first** element. Returns that element.|`arr.shift()`|
|`splice()`|Adds/Removes elements at a specific index.|`arr.splice(2, 0, "New")`|
|`reverse()`|Reverses the order of the elements.|`arr.reverse()`|
|`sort()`|Sorts the elements (alphabetically by default).|`arr.sort()`|
|`fill()`|Fills elements with a static value.|`arr.fill(0)`|
|`copyWithin()`|Copies array elements within the array to a specified position.|`arr.copyWithin(2, 0)`|

### **Access & Search (Does Not Mutate)**

These methods return specific items or information about the array.

|**Method**|**Description**|**Example**|
|---|---|---|
|`indexOf()`|Returns the first index of a specified value. Returns -1 if not found.|`arr.indexOf("A")`|
|`lastIndexOf()`|Returns the last index of a specified value.|`arr.lastIndexOf("A")`|
|`includes()`|Returns `true` if array contains a value, `false` otherwise.|`arr.includes(5)`|
|`find()`|Returns the **value** of the first element that passes a test function.|`arr.find(x => x > 10)`|
|`findIndex()`|Returns the **index** of the first element that passes a test function.|`arr.findIndex(x => x > 10)`|
|`findLast()`|Like `find()`, but starts from the end.|`arr.findLast(x => x > 10)`|
|`findLastIndex()`|Like `findIndex()`, but starts from the end.|`arr.findLastIndex(x => x > 10)`|
|`at()`|Returns the element at a specific index (allows negative integers for end-counting).|`arr.at(-1)` (Last item)|