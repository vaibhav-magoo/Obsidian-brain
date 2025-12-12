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
- Create the CSS module with the `.module.css` extension, example: `my-style.module.css`.
-  import the stylesheet:
	`import styles from './my-style.module.css';`


# Difference between stylesheet and module

| **Feature**          | **Standard CSS Stylesheets**                                                                                        | **CSS Modules**                                                                                                          |
| -------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Scope**            | **Global**. Styles defined in one file can affect elements in completely different components if class names match. | **Local**. Styles are scoped to the specific component where they are imported.                                          |
| **File Extension**   | `.css` (e.g., `Button.css`)                                                                                         | `.module.css` (e.g., `Button.module.css`)                                                                                |
| **Import Syntax**    | `import './Button.css'`                                                                                             | `import styles from './Button.module.css'`                                                                               |
| **JSX Usage**        | String literal: `className="btn"`                                                                                   | Object property: `className={styles.btn}`                                                                                |
| **Class Naming**     | You see exactly what you type (e.g., `class="btn"`).                                                                | **Hashed/Obfuscated**. React generates unique names like `Button_btn__2f9a` to prevent conflicts.                        |
| **Conflict Risk**    | **High**. If two components use `.container`, they will clash.                                                      | **Zero**. Since class names are unique, you can reuse common names (like `.container` or `.title`) in every file safely. |
| **Hyphenated Names** | Standard usage: `.side-bar` is fine.                                                                                | **Tricky**. You cannot use dot notation for hyphens. You must use bracket notation: `styles['side-bar']`.                |
| **Best Use Case**    | Global styles, resets, font setups, and legacy projects.                                                            | Component-specific styling (Buttons, Headers, Cards) in modern React apps.                                               |

---
