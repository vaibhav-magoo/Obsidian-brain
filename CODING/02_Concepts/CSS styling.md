---
type: concept
tags:
created: 2025-12-12
source:
---
Tags: [[React]] , [[Webdev]]

There are many ways to style React with CSS, this tutorial will take a closer look at three common ways:

- Inline styling
- CSS stylesheets
- CSS Modules


# Inline Styling
 -  you just write the CSS inside the line.
  - Since the inline CSS is written in a JavaScript object, properties with hyphen separators, like `background-color`, must be written with camel case syntax:

 example--
```javascript
<h1 style={{backgroundColor: "lightblue"}}></h1>
```

 can also make a javascript object and later add it to the line.

example: 
```jsx
const Header = () => {
  const myStyle = {
    color: "white",
    backgroundColor: "DodgerBlue",
    padding: "10px",
    fontFamily: "Sans-Serif"
  };
  return (
    <>
      <h1 style={myStyle}>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
}
```


# stylesheet
	you can write it in a seperate css file

- you will have to import the style sheet into the component
	`import './MyStylesheet.css'`

# modules
- 



---
