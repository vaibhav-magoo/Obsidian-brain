tags -- [[React]]

- lets us create multiple pages using 1 html file
- required to install react-router
- in main.jsx , import browserrouter and wrap the app component with
``` jsx
createRoot(document.getElementById('root')).render(
  <StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </StrictMode>,
)
``` 
- 