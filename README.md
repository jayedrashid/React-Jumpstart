# `ReactJS: Jump-start`

<p align="center">
 <img width="400px" src="https://miro.medium.com/max/1400/0*EitUXT-pqbaQSCTt.gif" align="center" alt="GitHub Readme Stats" />
 <h2 align="center">My React Journey Begins</h2>
</p>


Starting React JS

---

## Quick Links

<!-- - [Summary](#summary) -->
- [Environment Setup](#environment-setup)
- [React Folder Structure](#react-folder-structure)
- [App & Index file Basics](#app-component-basics)
- [Dynamic Values](#dynamic-values)
- [Multiple Components](#multiple-components)
- [Adding Styles](#adding-styles)
- [Click Events](#click-events)
- [Using State](#using-state)
- [Outputting Lists](#outputting-lists)
- [Props](#props)
- [Reusing Components](#reusing-components)
- [Functions As Props](#functions-as-props)
- [Using State useEffect Hook](#using-state-useEffect-hook)
- [useEffect Dependencies](#useEffect-dependencies)
- [Using JSON Server](#using-json-server)
- [Fetching Data with useEffect](#fetching-data-with-useEffect)
- [JSX](#jsx)



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

## State `useState`
Using State (useState hook)

React components has a built-in state object. The state object is where you store property values that belongs to the component. When the state object changes, the component re-renders.

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
    setCount(count + 1);
    setCount(count + 1);  // now batch works
  }
  const subtract = () => {
    setCount(count - 1);
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

Basic Hooks
- useState = handle reactive data
- useEffect = change over component life-cycle 
- useContext
Additional Hooks
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




---

## Reusing Components
Reusing Components in React

---

## Functions As Props
Using Functions as Props in React

---

## Using State `useEffect` Hook
Using useEffect Hook (the basics)

---

## useEffect Dependencies
Using useEffect 

---

## Using JSON Server
Using JSON Server 

---

## Fetching Data with `useEffect`
Fetching Data with useEffect 




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








