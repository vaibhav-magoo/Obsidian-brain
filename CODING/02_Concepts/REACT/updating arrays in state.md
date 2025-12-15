tags - [[React]] [[state]] 
related - [[unordered list]]

- create an array in use state
- then to display it ,we can use an unordered list element
- inside a input element give it an id , and then use getElementById to access the string input
- inside a handler function , store this in a const and then use updater function to add to array
- remember to use the span function otherwise the array will get deleted and a new one will be created

---
## to remove an element:
 - inside the list element add an onclick event handler with a callback to a handler function
 - the handler will take the index as a parameter, and using array filters display the part without 
   the deleted part
 
---

## to edit array of objects
 - it will be similar to the previous one , just handle each variable seperately and then add them all to an object