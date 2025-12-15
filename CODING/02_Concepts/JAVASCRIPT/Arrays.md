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
### **Transformation & Creation (Returns New Array)**

These create a _new_ array or string, leaving the original untouched.

|**Method**|**Description**|**Example**|
|---|---|---|
|`concat()`|Merges two or more arrays into a new one.|`arr1.concat(arr2)`|
|`slice()`|Selects a part of an array and returns a new array.|`arr.slice(1, 3)`|
|`join()`|Joins all elements into a string, separated by a specified character.|`arr.join(", ")`|
|`toString()`|Converts array to a string (comma separated).|`arr.toString()`|
|`flat()`|Flattens nested arrays (sub-arrays) into a single array.|`[[1,2], [3]].flat()` → `[1,2,3]`|
|`flatMap()`|Maps each element using a function, then flattens the result.|`arr.flatMap(x => [x, x*2])`|
|`toSorted()`|Like `sort()`, but returns a new array instead of mutating.|`arr.toSorted()`|
|`toReversed()`|Like `reverse()`, but returns a new array.|`arr.toReversed()`|
|`toSpliced()`|Like `splice()`, but returns a new array.|`arr.toSpliced(1, 1)`|
|`with()`|Returns a new array with one element replaced at a given index.|`arr.with(2, "NewVal")`|

### **Iteration (High Order Functions)**

These methods loop through the array and execute a function for every element.

| **Method**      | **Description**                                                             | **Example**                           |
| --------------- | --------------------------------------------------------------------------- | ------------------------------------- |
| `forEach()`     | Calls a function for each element (does not return anything).               | `arr.forEach(x => console.log(x))`    |
| `map()`         | Creates a new array with the result of calling a function on every element. | `arr.map(x => x * 2)`                 |
| `filter()`      | Creates a new array with every element that passes a test function.         | `arr.filter(x => x > 18)`             |
| `reduce()`      | Reduces the array to a single value (accumulator) (left-to-right).          | `arr.reduce((total, x) => total + x)` |
| `reduceRight()` | Like `reduce()`, but works right-to-left.                                   | `arr.reduceRight(...)`                |
| `every()`       | Checks if **every** element passes a test. Returns Boolean.                 | `arr.every(x => x > 0)`               |
| `some()`        | Checks if **at least one** element passes a test. Returns Boolean.          | `arr.some(x => x > 10)`               |
| `entries()`     | Returns an Iterator object with key/value pairs.                            | `for (let [i, val] of arr.entries())` |
| `keys()`        | Returns an Iterator object containing the keys (indexes).                   | `for (let key of arr.keys())`         |
| `values()`      | Returns an Iterator object containing the values.                           | `for (let val of arr.values())`       |

### **Static Methods**

These are called on the `Array` class itself, not on an instance (a specific variable).

|**Method**|**Description**|**Example**|
|---|---|---|
|`Array.isArray()`|Returns `true` if the object is an array.|`Array.isArray(myVar)`|
|`Array.from()`|Creates an array from an array-like object (like a String or Set).|`Array.from("123")` → `['1','2','3']`|
|`Array.of()`|Creates a new array with a variable number of arguments.|`Array.of(1, 2, 3)`|