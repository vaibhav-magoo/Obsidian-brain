

To get data, you need to follow these three steps:

1. **State:** Create a place to hold the data once it arrives.
    
2. **Effect:** Run the code that asks for the data.
    
3. **Render:** Show the data in your HTML.

****
```jsx
import { useState, useEffect } from 'react';

function MyComponent() {
  // 1. Create state to hold the data (starts as an empty array)
  const [data, setData] = useState([]);

  // 2. useEffect runs once when the component "mounts" (appears on screen)
  useEffect(() => {
    fetch('https://jsonplaceholder.typicode.com/posts') // The request
      .then((response) => response.json())             // Convert response to JSON
      .then((json) => setData(json));                 // Save it to state
  }, []); // The empty [] means "only run this once"

  // 3. Render the data
  return (
    <div>
      <h1>Blog Posts</h1>
      <ul>
        {data.map(post => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}
```
## fetch:
```jsx
useEffect(() => { // This is the 'waiter' requesting data from the kitchen (backend)
 fetch('https://api.yourbackend.com/users') 
	 .then(response => response.json()) 
	 .then(data => setUsers(data)); 
}, []);
```

