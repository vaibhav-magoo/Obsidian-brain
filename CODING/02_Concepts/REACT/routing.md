tags -- [[React]]

- lets us create multiple pages using 1 html file
- required to install react-router
- in main.jsx , import browserrouter and wrap the app component with
``` js
createRoot(document.getElementById('root')).render(
  <StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </StrictMode>,
)
``` 
- now in app.jsx import routes and then add a `<Routes></Routes>` to the return function
- this will tell us all the pages in the website
```js
function App(){
  return(
    <>
      <Routes>
        <Route path="/" element={<HomePage />}></Route>
        <Route path="cart" element={<Cart />}></Route>
      </Routes>
    </>
  );}
```
- you can add new pages using the route element with props , path and element .
  path gives the URL and element give the component to run on that page 

- instead of path="/" we can just write index and it will work