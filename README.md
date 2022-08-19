# `ReactJS: Jump-start`

`A JavaScript Library For Building User Interfaces`

<p align="center">
 <img width="400px" src="https://miro.medium.com/max/1400/0*EitUXT-pqbaQSCTt.gif" align="center" alt="GitHub Readme Stats" />
 <h2 align="center">My React Journey Begins</h2>
</p>

Starting React JS from sources:

<p align="center">
 <img width="100px" src="https://cdn.fs.teachablecdn.com/6Rl23AySyxnjtTrQ2VVw" align="center" alt="The Net Ninja logo" />
 <h2 align="center">The Net Ninja & Others</h2>
</p>

---

## Quick Links

<!-- - [Summary](#summary) -->

- [Environment Setup](#environment-setup)
- [React Folder Structure](#react-folder-structure)
- [JSX](#jsx)
- [App Component](#app-component)
- [Dynamic Values](#dynamic-values)
- [Multiple Components](#multiple-components)
- [Adding Styles](#adding-styles)
- [Click Events](#click-events)
- [State (useState) Hook](#state-usestate-hook)
- [10 Hooks](#10-hooks)
- [Outputting Lists](#outputting-lists)
- [Props](#props)
- [Reusing Components](#reusing-components)
- [Functions As Props](#functions-as-props)
- [State useEffect Hook](#state-useeffect-hook)
- [useEffect Dependencies](#useeffect-dependencies)
- [JSON Server](#json-server)
- [Fetch Data with useEffect](#fetch-data-with-useeffect)
- [Conditional Loading Message](#conditional-loading-message)
- [Handling Fetch Errors](#handling-fetch-errors)
- [Custom Hook](#custom-hook)
- [React Router](#react-router)
- [Exact Match Routes](#exact-match-routes)
- [Router Links](#router-links)
- [useEffect Cleanup](#useeffect-cleanup)


---

## Environment Setup

- Install VS Code
- Install `Simple React Snippets` (ext.)
- Setup VS Code `Emmet`
- Install Node

```sh
brew install node
```

- Install React

```sh
npx create-react-app .
```

- Install NPM (localhost:3000 start) (To Close Server = Ctrl + C)

```sh
yarn start
// or
npm start
```

- Install SASS (sass will start working after restarting vscode)

```sh
yarn add sass
// or
npm i sass
```

- Delete Unnecessary Files from `root` directory

---

## React Folder Structure

[Structuring React Projects](https://blog.bitsrc.io/structuring-a-react-project-a-definitive-guide-ac9a754df5eb)

[React Folder Structure](https://gist.github.com/vasanthk/2bde67682511659c4d6a)

[How To Organize React Projects](https://github.com/WebDevSimplified/react-folder-structure)

`Beginner` Folder Structure

```
root
├── node_modules
├── public
├── src
│   ├── __tests__
│   │   ├── components
│   │   └── hooks
│   ├── components
│   │   ├── Button.js
│   │   ├── Checkbox.js
│   │   ├── Dropdown.js
│   │   ├── FormInput.js
│   │   ├── FormSelect.js
│   │   ├── Home.js
│   │   ├── Modal.js
│   │   ├── Navbar.js
│   │   ├── NewTodoModal.js
│   │   ├── RadioButton.js
│   │   ├── TodoForm.js
│   │   ├── TodoItem.js
│   │   └── TodoList.js
│   └── hooks
│       ├── useFetch.js
│       └── useLocalStorage.js
├── .gitignore
├── package-lock.json
├── package.json
└── readme.md
```

`Intermidiate` Folder Structure

```
root
├── node_modules
├── public
├── src
│   ├── assets
│   │   ├── global.css
│   │   ├── profile.jpg
│   │   └── logo.svg
│   ├── components (General)
│   │   ├── __tests__
│   │   │   └── form.js
│   │   ├── form
│   │   │   ├── __tests__
│   │   │   │   └── Checkbox.js
│   │   │   ├── Checkbox.js
│   │   │   ├── FormInput.js
│   │   │   ├── FormSelect.js
│   │   │   └── RadioButton.js
│   │   ├── ui
│   │   │   ├── __tests__
│   │   │   │   └── Button.js
│   │   │   ├── Button.js
│   │   │   ├── ButtonGroup.js
│   │   │   ├── Dropdown.js
│   │   │   └── Modal.js
│   │   └── Navbar.js
│   ├── context
│   │   ├── __tests__
│   │   │   └── AuthContext.js
│   │   └── AuthContext.js
│   ├── data
│   │   ├── configValues.json
│   │   ├── constants.js
│   │   └── DefaultTodos.json
│   ├── hooks
│   │   ├── __tests__
│   │   │   └── Fetch.js
│   │   ├── useFetch.js
│   │   └── useLocalStorage.js
│   ├── pages (Each Individuals)
│   │   ├── Home
│   │   │   ├── __tests__
│   │   │   │   └── NewTodoModal.js
│   │   │   ├── index.js
│   │   │   ├── NewTodoModal.js
│   │   │   ├── TodoContext.js
│   │   │   ├── TodoForm.js
│   │   │   ├── TodoItem.js
│   │   │   └── TodoList.js
│   │   ├── Login
│   │   │   ├── __tests__
│   │   │   │   └── Form.js
│   │   │   ├── index.js
│   │   │   ├── LoginForm.js
│   │   │   └── useLogin.js
│   │   ├── Settings
│   │   │   ├── __tests__
│   │   │   │   └── Form.js
│   │   │   ├── index.js
│   │   │   ├── SettingsContext.js
│   │   │   ├── SettingsForm.js
│   │   │   └── useSettings.js
│   │   ├── Signup
│   │   │   ├── __tests__
│   │   │   │   └── Form.js
│   │   │   ├── index.js
│   │   │   ├── SignupForm.js
│   │   │   └── useSignup.js
│   └── utils
│       ├── __tests__
│       │   └── formatCurrency.js
│       ├── formatCurrency.js
│       └── formatDate.js
├── .gitignore
├── package-lock.json
├── package.json
└── readme.md
```

---

#### `node_modules` Folder

It holds all of our project dependencies

- Application dependencies
- Development dependencies

#### `public` Folder

All of our files public to the browser including index.html where all of our react code injected inside the id of `root`.

```sh
<div id="root"></div>
```

#### `src` Folder

All of our working files will be in this folder. Here, the index.js file will kick-start our application. This file will be responsible taking all of our react components and mounting them to the DOM. It holds the App component and render it to the DOM.

---

## JSX

JSX is a react extension to JavaScript that allows us to write HTML in JavaScript files, do not however think that JSX is just a smile templating language. The use of JSX allows us to keep our component logic and UI in a single file without bloating it. JSX allows us to interpret JavaScript expression and statements by wrapping it in curly braces, it actually compiles first and is faster than the actual JavaScript we write outside JSX.

In App.js file there is a function (can be an arrow function) called App which returns some html looking codes named JSX. Here babel compiles all these JSX template codes to html when we save the file and renders html to the DOM. In JSX html class turns into `className`.

```sh
function App() {
  return (
    <div className="App">
      <div className="content">
        <h1>App Component</h1>
      </div>
    </div>
  );
}
```

---

## App Component

Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. This page provides an introduction to the idea of components.

Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.

React Supports Class Based or Functional Components
With react there is more than one approach to compose your UI. If you like complexity, forgive my sarcasm then you can use class based components. A class component is Just a class that extends React.Component, it has a render method that is called to build and return our UI.

Some things should be simple and straightforward so I prefer using functional components. You just declare and export a function that returns our UI as we did in the earlier example. So whatever style you are comfortable with , react has got you.

Whenever we create a component function, we must export it.

In App.js file:

```sh
import './App.css';

function App() {
  return (
    <div className="App">
      <div className="content">
        <h1>App Component</h1>
      </div>
    </div>
  );
}

export default App;
```

After exporting from `App.js` we must import App component from `index.js` to render it react DOM to show on browser.

In index.js file:

```sh
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

---

## Dynamic Values

In JSX we can output `Dynamic Values` or `Variables` inside it.

```sh
import './App.css';

function App() {
  const title = 'Welcome to the new blog';
  const likes = 50;
  const person = { name: 'yoshi', age: 30 };

  return (
    <div className="App">
      <div className="content">
        <h1>{ title }</h1>
        <p>Liked { likes } times</p>
        <p>{ person }</p>
      </div>
    </div>
  );
}

export default App;
```

JSX is a react extension to JavaScript that allows us to write HTML in JavaScript files.

```sh
import './App.css';

function App() {
  const title = 'Welcome to the new blog';
  const likes = 50;
  // const person = { name: 'yoshi', age: 30 };
  const link = 'http://www.google.com';

  return (
    <div className="App">
      <div className="content">
        <h1>{ title }</h1>
        <p>Liked { likes } times</p>

        {/* <p>{ person }</p> */}

        <p>{ 10 }</p>
        <p>{ "hello, ninjas" }</p>
        <p>{ [1,2,3,4,5] }</p>
        <p>{ Math.random() * 10 }</p>

        <a href={link}>Google Site</a>
      </div>
    </div>
  );
}

export default App;
```

---

## Multiple Components

Create `Navbar` Component in Navbar.js file

```sh
const Navbar = () => {
  return (
    <nav className="navbar">
      <h1>The Dojo Blog</h1>
      <div className="links">
        <a href="/">Home</a>
        <a href="/create">New Blog</a>
      </div>
    </nav>
  );
}

export default Navbar;
```

Import `Navbar` Component in App.js file

```sh
import './App.css';
import Navbar from './Navbar';

function App() {
  return (
    <div className="App">
      <Navbar />          // self closing tag
      <div className="content">
        <h1>App Component</h1>
      </div>
    </div>
  );
}

export default App;
```

Create `Home` Component in Home.js file

```sh
const Home = () => {
  return (
    <div className="home">
      <h2>Homepage</h2>
    </div>
  );
}

export default Home;
```

Import `Home` Component in App.js file

```sh
import './App.css';
import Navbar from './Navbar';
import Home from './Home';

function App() {
  return (
    <div className="App">
      <Navbar />
      <div className="content">
        <Home />
      </div>
    </div>
  );
}

export default App;
```

---

## Adding Styles

[Style Your React App – 5 Ways to Write CSS](https://www.freecodecamp.org/news/how-to-style-react-apps-with-css/)

1. Inline Styles
2. Plain CSS
3. SASS / SCSS
4. CSS Modules
5. CSS-in-JS

### `Global Stylesheet`

Delete App.css and prepare index.css as our Global Stylesheet.

In index.css file

```sh
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300;400;500;600;700&display=swap');

/* base styles */
* {
  margin: 0;
  font-family: "Quicksand";
  color: #333;
}
.navbar {
  padding: 20px;
  display: flex;
  align-items: center;
  max-width: 600px;
  margin: 0 auto;
  border-bottom: 1px solid #f2f2f2;
}
.navbar h1 {
  color: #f1356d;
}
.navbar .links {
  margin-left: auto;
}
.navbar a {
  margin-left: 16px;
  text-decoration: none;
  padding: 6px;
}
.navbar a:hover {
  color: #f1356d;
}
.content {
  max-width: 600px;
  margin: 40px auto;
  padding: 20px;
}
```

### `Inline Style`

In `Navbar` component we can do Inline Style.

In Navbar.js file

```sh
const Navbar = () => {
  return (
    <nav className="navbar">
      <h1>The Dojo Blog</h1>
      <div className="links">
        <a href="/">Home</a>
        <a href="/create" style={{
          color: 'white',
          backgroundColor: '#f1356d',
          borderRadius: '8px'
        }}>New Blog</a>
      </div>
    </nav>
  );
}

export default Navbar;
```

---

## Click Events

There are many events like.. hover, click, form submission events etc. So, in Home component we will create a button and fire it by invoking a function (handleClick). Then we will create another button and function by passing arguments.

In Home.js file

```sh
const Home = () => {

  const handleClick = (e) => {
    console.log('hello ninjas', e);
  }

  const handleClickAgain = (name, e) => {
    console.log('hello ' + name, e.target);
  }

  return (
    <div className="home">
      <h2>Homepage</h2>
      <button onClick={handleClick}>Click me</button>
      <button onClick={(e) => handleClickAgain('mario', e)}>Click me again</button>
    </div>
  );
}

export default Home;
```

---

## State `useState` Hook

Using State (useState hook)

React components has a built-in state object. The state object is where you store property values that belongs to the component. When the state object changes, the component re-renders.

State is handled & updated inside of a component and change the value.

React Hooks
This is one of the holy grail of react. React hooks just makes your work so much easier, react hooks are designed to simplify difficult tasks like re-rendering the UI, managing state, picking an element from the DOM and lots more. There is a hook for most things you want and if there isn’t any react hook that meets your need then you can also build your own custom hook.

We used a very simple react hook here that allows us to update the state of a component and re render the UI anytime there is a state change. Now most people would say, there are other frameworks that makes state management a built in feature, say for instance Svelte or Angular which is reactive by default, but this way is more concise when compared to using vanilla JavaScript or even jQuery.

This ensures that there is less broiler plate code, we would have written more code if this was done without hooks or from a class based component. Hooks also eliminate the need for listening to multiple life cycle events on components, the hook manages all that behind the scene for you.

Hook in react is a special type of function that does a special type if job. You can tell a hook by it's name because it starts with 'use'. So useState hook gives us a way to make a reactive value and also provides us way to change the value.

We can use the hook as many times as we want in a component for different values. This value can be an array, object, boolean, string, number.

So, when you need a reactive value that might change in some point we will use `useState` hook todo that. We pass in an initial value 'mario' and we can output that value in a template { } and then we call the `set` function which is second value in the array [ name, setName ] to update it so that triggers a re-render and the new value is going to output to the browser.

You can't put hooks inside if conditions, functions, loops etc. So, the can't be nested. Hooks will always stay at the top level in your App component.

When useState comes in a variable, the array must be destructured inline and returned 2 values.

```sh
const [name, setName] = useState(0);

# name (1st Value or reactive Value) = currentState
# setName (2nd Value or setter) = setter function that updates currentState
# useState(0) = hook takes 1 optional argument which is current or default state
```

React update state in batches:

```sh
import { useState } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);

  const add = () => {
    setCount(count + 1);
    setCount(count + 1);  // batch not working
  }
  const subtract = () => {
    setCount(count - 1);
  }

  return (
    <div className="home">
      <h1>{count}</h1>

      <div className="calc">
        <button onClick={add}>+</button>
        <button onClick={subtract}>-</button>
      </div>

      <div className="reset">
        <button onClick={() => setCount(0)}>Reset</button>
      </div>
    </div>
  );
}

export default Home;
```

Using `set` function right way by correcting above snippet:

```sh
  const add = () => {
    setCount(prev => prev + 1);
    setCount(prev => prev + 1);  // now batch works
  }
  const subtract = () => {
    setCount(prev => prev - 1);
  }
```

In Home.js file

```sh
import { useState } from "react";

const Home = () => {
  // let name = 'mario';
  const [name, setName] = useState('mario');    // hook
  const [age, setAge] = useState(25);   // setAge is a function

  const handleClick = () => {
    // name = 'luigi';
    setName('luigi');
    setAge(30);
  }

  return (
    <div className="home">
      <h2>Homepage</h2>
      <p>{ name } is { age } years old</p>
      <button onClick={handleClick}>Click me</button>
    </div>
  );
}

export default Home;
```

---

## 10 Hooks

State = any data that changes application and so does ui.
React has 10 built-in Hooks:

- Basic Hooks
  - useState = handle reactive data
  - useEffect = change over component life-cycle
  - useContext
- Additional Hooks
  - useReducer
  - useCallback
  - useMemo
  - useRef
  - useImperativeHandle
  - useLayoutEffect
  - useDebugValue

---

## Outputting Lists

Outputting lists of data in React. We have list of data which we have store in useState and then we map through that data so that we take each item into that as we map through it and we output a template for each one and for each one it has a key property (unique id)

In Home.js file

```sh
import { useState } from "react";

const Home = () => {
  const [blogs, setBlogs] = useState([
    { title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1 },
    { title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2 },
    { title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3 }
  ])

  return (
    <div className="home">
      {blogs.map(blog => (
        <div className="blog-preview" key={blog.id} >
          <h2>{ blog.title }</h2>
          <p>Written by { blog.author }</p>
        </div>
      ))}
    </div>
  );
}

export default Home;
```

In index.css file add additional css snippet

```sh
/* blog previews / list */
.blog-preview {
  padding: 10px 16px;
  margin: 20px 0;
  border-bottom: 1px solid #fafafa;
}
.blog-preview:hover {
  box-shadow: 1px 3px 5px rgba(0,0,0,0.1);
}
.blog-preview h2 {
  font-size: 20px;
  color: #f1356d;
  margin-bottom: 8px;
}
```

---

## Props

Props are arguments passed into React components. Props are passed to components via HTML attributes. props stands for properties.

Props are like arguments to a function and handled outside of a component and display information. Props allows us to pass data from one `parent` component to another `child` component.

Import BlogList component from In Home.js file. Here `Home` is parent component and `<BlogList />` is child component.

```sh
import { useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState([
    { title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1 },
    { title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2 },
    { title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3 }
  ])

  return (
    <div className="home">
      <BlogList blogs={blogs} title="All Blogs" />    // blogs={blogs} is a prop
    </div>
  );
}

export default Home;
```

Create an external component named BlogList in BlogList.js file.

```sh
const BlogList = ({ blogs, title}) => {   // destruture props inside parenthesis
  // const blogs = props.blogs;
  // const title = props.title;
  // console.log(blogs);

  return (
    <div className="blog-list">
      <h2>{ title }</h2>
      {blogs.map(blog => (
        <div className="blog-preview" key={blog.id} >
          <h2>{ blog.title }</h2>
          <p>Written by { blog.author }</p>
        </div>
      ))}
    </div>
  );
}

export default BlogList;
```

---

## Reusing Components

Apply filter method in BlogList component in Home.js file. BlogList component can be reused with different data. Here we want only author: 'mario'. So,

```sh
import { useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState([
    { title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1 },
    { title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2 },
    { title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3 }
  ])

  return (
    <div className="home">
      <BlogList blogs={blogs} title="All Blogs" />
      <BlogList blogs={blogs.filter(blog => blog.author === 'mario')} title="Mario's Blogs" />
    </div>
  );
}

export default Home;
```

---

## Functions As Props

Using Functions as Props in React

First define handleDelete function inside Home component. Then use setBlogs function inside Home component to update the state.

In Home.js file.

```sh
import { useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState([
    { title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1 },
    { title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2 },
    { title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3 }
  ])

  const handleDelete = (id) => {
    const newBlogs = blogs.filter(blog => blog.id !== id);
    setBlogs(newBlogs);
  }

  return (
    <div className="home">
      <BlogList blogs={blogs} title="All Blogs" handleDelete={handleDelete} />    // handleDelete={handleDelete} is a prop function
    </div>
  );
}

export default Home;
```

In BlogList.js file. Passing handleDelete function as prop.

```sh
const BlogList = ({ blogs, title, handleDelete }) => {
  return (
    <div className="blog-list">
      <h2>{ title }</h2>
      {blogs.map(blog => (
        <div className="blog-preview" key={blog.id} >
          <h2>{ blog.title }</h2>
          <p>Written by { blog.author }</p>
          <button onClick={() => handleDelete(blog.id)}>delete blog</button>
        </div>
      ))}
    </div>
  );
}

export default BlogList;
```

---

## State `useEffect` Hook

The Effect Hook lets you perform side effects in function components. This useEffect Hook run code on every render. useEffect function fires on every render. When we change the data it rerender this to the DOM. Whenever the state changes useEffect function rerenders.

Whether or not you’re used to calling these operations “side effects” (or just “effects”), you’ve likely performed them in your components before.

Examples of `Side Effects` in React. Eg:

- Data fetching
- Authentication service communication
- Setting up a subscription
- manually changing the DOM

In Home.js file:

```sh
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState([
    { title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1 },
    { title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2 },
    { title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3 }
  ])

  const handleDelete = (id) => {
    const newBlogs = blogs.filter(blog => blog.id !== id);
    setBlogs(newBlogs);
  }

  useEffect(() => {
    console.log('use effect ran');
    console.log(blogs);
  })

  return (
    <div className="home">
      <BlogList blogs={blogs} title="All Blogs" handleDelete={handleDelete} />
    </div>
  );
}

export default Home;
```

---

## useEffect Dependencies

Using useEffect Dependencies to stop rerenders by Dependency array which is passed inside useEffect function as a second argument

You don't alway want to run a function after every single renders, maybe a only a certain renders. To do that we can use something called dependency array. This is basically an array that we can pass into an useEffect hook as an second argument. This hook only runs the function after the first initial render. Thereafter if the state changes it won't run the function again. It only runs it once.

```sh
useEffect(() => {

}, []);   //  dependency array
```

In Home.js file:

```sh
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState([
    { title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1 },
    { title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2 },
    { title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3 }
  ])

  const handleDelete = (id) => {
    const newBlogs = blogs.filter(blog => blog.id !== id);
    setBlogs(newBlogs);
  }

    useEffect(() => {
    console.log('use effect ran');
    console.log(blogs);
  }, [])

  return (
    <div className="home">
      <BlogList blogs={blogs} title="All Blogs" handleDelete={handleDelete} />
    </div>
  );
}

export default Home;
```

Another option is to run dependencies to this array. Any state values that should trigger the useEffect function to run when they change. So, lets create another piece of state:

In Home.js file:

```sh
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState([
    { title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1 },
    { title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2 },
    { title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3 }
  ])

  const [name, setName] = useState('mario');

  const handleDelete = (id) => {
    const newBlogs = blogs.filter(blog => blog.id !== id);
    setBlogs(newBlogs);
  }

  useEffect(() => {
    console.log('use effect ran');
    console.log(blogs);
  }, [name])    //  dependency array

  return (
    <div className="home">
      <BlogList blogs={blogs} title="All Blogs" handleDelete={handleDelete} />
      <button onClick={() => setName('luigi')}>change name</button>
    </div>
  );
}

export default Home;
```

---

## JSON Server

To use this useEffect hook we're going to be using it fetch some data. useEffect is a good place to fetch the data component because we know that it runs the function right here when the component first renders initially. Then we can use that data in our application instead of the data hard coded that we have in our state. Rather using a database using an api endpoint.
Here, we're going to use the JSON Server which is gonna allow us to build a fake rest api just using a JSON file to test this out.

In data/db.json file:

```sh
{
  "blogs": [
    {
      "title": "My First Blog",
      "body": "Why do we use it?\nIt is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).\n\n\nWhere does it come from?\nContrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of \"de Finibus Bonorum et Malorum\" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, \"Lorem ipsum dolor sit amet..\", comes from a line in section 1.10.32.\n\nThe standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from \"de Finibus Bonorum et Malorum\" by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.\n\nWhere can I get some?\nThere are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary, making this the first true generator on the Internet. It uses a dictionary of over 200 Latin words, combined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humour, or non-characteristic words etc.",
      "author": "mario",
      "id": 1
    },
    {
      "title": "Opening Party!",
      "body": "Why do we use it?\nIt is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).\n\n\nWhere does it come from?\nContrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of \"de Finibus Bonorum et Malorum\" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, \"Lorem ipsum dolor sit amet..\", comes from a line in section 1.10.32.\n\nThe standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from \"de Finibus Bonorum et Malorum\" by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.\n\nWhere can I get some?\nThere are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary, making this the first true generator on the Internet. It uses a dictionary of over 200 Latin words, combined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humour, or non-characteristic words etc.",
      "author": "yoshi",
      "id": 2
    }
  ]
}
```

Now we'll use the `JSON Server`package to watch this file and wrap it with some endpoints.

In terminal:

```sh
npx json-server --watch dta/db.json --port 8000

```

Routes management with Endpoints:

| Routes      | Endpoints | Details             |
| ----------- | --------- | ------------------- |
| /blogs      | GET       | Fetch all blogs     |
| /blogs/{id} | GET       | Fetch a single blog |
| /blogs      | POST      | Add a new blog      |
| /blogs/{id} | DELETE    | Delete a blog       |

---

## Fetch Data with `useEffect`

Fetching Data with useEffect

We're going to use some fetch request inside our component using this endpoints:
`http://localhost:8000/blogs`

In Home.js file:

```sh
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState(null)

  useEffect(() => {
    fetch('http://localhost:8000/blogs')  // make fetch request
      .then(res => {
        return res.json();
      })
      .then(data => {
        setBlogs(data);
      })
  }, [])  // dependency array helps not to loop render data and show it only when data changes

  return (
    <div className="home">
      {blogs && <BlogList blogs={blogs} />}
    </div>
  );
}

export default Home;
```

---

## Conditional Loading Message

Currently in our application we render the blog list once we have blog data and until then we don't render it. But it would be nice to create a loading massage whilst the data is being fetched so that user knows something is loading if it takes time to do. Here our fetch is very quick because we're just making a fetch to our own computer but most times the fetch will be to another server over the internet and slower in in which case the user will see that loading message while we fetch the data. So, to do this we're going to create an additional piece of state inside the home component and that is gonna be called isPending here.

In Home.js file:

```sh
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState(null);     // 1st state
  const [isPending, setIsPending] = useState(true);     // 2nd state

  useEffect(() => {
    setTimeout(() => {
      fetch('http://localhost:8000/blogs')
      .then(res => {
        return res.json();
      })
      .then(data => {
        setIsPending(false);
        setBlogs(data);
      })
    }, 1000);
  }, [])

  return (
    <div className="home">
      { isPending && <div>Loading...</div> }
      { blogs && <BlogList blogs={blogs} /> }
    </div>
  );
}

export default Home;
```

---

## Handling Fetch Errors

Handling Fetch Errors



---

## Custom Hook

Making a Custom Hook

---

## React Router

React Router


---

## Exact Match Routes

Exact Match Routes


---

## Router Links

Router Links


---

## useEffect Cleanup

useEffect Cleanup

---

## Contributors

<table>
  <tr>
    <td align="center"><a href="https://jayedrashid.com/"><img src="https://avatars.githubusercontent.com/u/68325519?s=400&u=c3380d6ce56295f87d4f877de9ca04b7adf28d55&v=4" width="100px;" style="border-radius:50%; border:2px solid white;" alt=""/><br /><sub><b>Jayed Rashid</b></sub></a><br />   
  </tr>
</table>

---

## Let's Connect

Feel free to Contact me on [Twitter](https://mobile.twitter.com/jayedrashid), send an email to jayed@jayedrashid.com

<img height="20" src="https://www.bollywoodmdb.com/images/uparrow.gif"> [back to top](#quick-links)<br>





