# React Router 6

#### Documentation

 I've used **React Router** docs and **W3Schools** Router docs for source codes and examples. 

[React Router Docs](https://reactrouter.com/docs/en/v6/getting-started/overview)

[W3Schools Router Docs](https://www.w3schools.com/react/react_router.asp)


#### Create A React Application

```sh
npx create-react-app router
```

<br>

> **Note:** Create React App doesn't include page routing. 

#### Install react-router-dom

```sh
npm i react-router-dom
```

> Now that we have react app and react-router-dom installed in the project directory.

#### Components (Pages)

> To create an application with multiple page routes, let's first start with the file structure. Within the ``src`` folder, we'll create a folder named pages with several files: 
``src/pages/:`` 
``- Layout.js``
``- Home.js``
``- Blogs.js``
``- Contact.js``
``- NoPage.js``  
Each file will contain a very basic React component.


#### Usage

> Now we will use our Router in our ``index.js`` file to route to pages based on URL.

- index.js

```js
import ReactDOM from "react-dom/client";
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Layout from "./pages/Layout";
import Home from "./pages/Home";
import Blogs from "./pages/Blogs";
import Contact from "./pages/Contact";
import NoPage from "./pages/NoPage";


// Function component

export default function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Layout />}>
          <Route index element={<Home />} />
          <Route path="blogs" element={<Blogs />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NoPage />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
```

