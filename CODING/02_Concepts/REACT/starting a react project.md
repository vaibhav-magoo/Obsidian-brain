[[React]]
Here is the modern, standard way to start a React project using **Vite** (faster and better than the old `create-react-app`).

### 1. Prerequisites

Ensure you have **Node.js** installed.

- Check by running: `node -v` in your terminal.
    
- If not installed, download the "LTS" version from the official Node.js website.
    

### 2. Create the Project

Open your terminal (Command Prompt, PowerShell, or VS Code terminal) and run:

Bash

```
npm create vite@latest
```

### 3. Follow the Prompts

The terminal will ask you a few questions. Use your arrow keys to select:

1. **Project name:** (e.g., `my-react-app`)
    
2. **Select a framework:** `React`
    
3. **Select a variant:** `JavaScript` (or `JavaScript + SWC` for speed). _Choose TypeScript only if you already know it._
    

### 4. Install Dependencies

Vite creates the folder but doesn't install the heavy libraries yet. You need to go into the folder and install them.

Bash

```
cd my-react-app
npm install
```

### 5. Start the Development Server

This turns on the local server so you can see your app in the browser.

Bash

```
npm run dev
```

- **Result:** You will see a link like `http://localhost:5173/`. Ctrl+Click it to open your app.
    

---

### 6. Clean Up (Optional but Recommended)

Vite comes with a default "counter" example. To start fresh:

1. Open the project in VS Code (`code .`).
    
2. Go to `src/App.css` and delete everything.
    
3. Go to `src/App.jsx` and replace the code with this empty boilerplate:
    

JavaScript

```
import './App.css'

function App() {
  return (
    <div>
      <h1>Hello World</h1>
    </div>
  )
}

export default App
```

Since you are revising for your notes, would you like a quick explanation of the **Folder Structure** (what `main.jsx` vs `App.jsx` actually do)?