# `ReactJS: Notes`

`A JavaScript Library For Building User Interfaces`. React is a Declarative, Component-Based, JavaScript library for building User Interfaces.

<p align="center">
 <img width="400px" src="https://miro.medium.com/max/1400/0*EitUXT-pqbaQSCTt.gif" align="center" alt="GitHub Readme Stats" />
 <h2 align="center">React Beginners Guide</h2>
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
- [State (useEffect) Hook](#state-useeffect-hook)
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

It holds all of our project dependencies and node packages.

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

It is a syntax extension to JavaScript. We recommend using it with React to describe what the UI should look like. JSX may remind you of a template language, but it comes with the full power of JavaScript. JSX produces React “elements”. 

JSX stands for JavaScript xml. It allows html like syntax inside a JavaScript file. Then when this component is rendered to the DOM that jsx is compiled into regular JavaScript by babel compiler. That JavaScript injects this html like structure into the DOM. this is the reason we need babel in our html file. Because the browser doesn’t understand jsx and it needed to be compiled to work. 

In JSX we cannot use class attributes because ‘class’ is a reserved keyboard in JavaScript. So instead we’re gonna use className attributes. 

In JSX we can have only one single root element (div tag). You can’t add another root element next to it. Because JSX expressions must have one parent element. All we can do is to nest as many elements as we want inside one single parent element. 

In JSX we can output dynamic values or expressions inside templates. So create a variable (eg: string) as const and output that somewhere in the template. To do this we need to put a curly brace {} as a dynamic value. Inside that we need to put a JavaScript expression or variable. 
We can also use JavaScript methods with those variables. Eg: {title.toUpperCase()}.

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

## Types of Components

The component concept is quite simple to understand. Basically, it is a visual software element with its own state, receives some properties, and implements its own rendering logic. But are all the components the same? Can we rank them or differentiate them into component types?

Types of Behavioral Components
Depending on the type of behavior that the component will perform, we can differentiate the components in Stateless, Stateful, Pure Components, or HOC. Therefore, you are going to know and understand each of these types of components:

- Stateful Component
This type of component is the most used. The main characteristics of this type of component are that they use encapsulation in classes, have a state that they define and update, and each change in both props and state calls the render method.

- Stateless components
This component is a simplified version of the most common component: Stateful. These components are defined as functions in vanilla js and do not have or work with the state. The only data that these types of components work with is with the received props, and it also does not allow working with overwriting the methods of their life cycle. The advantages of these components are that they are easy to write, easily testable, and improve performance.

- Pure Component
This type of component is similar to the stateful ones in terms of its definition. They are also implemented as classes, but in this case, they will extend from React.PureComponent. Like stateless components, this type of component does not define a state, purely just a visual component. These components are optimized for better rendering performance since they only change if they detect a change in their props, and these are different from the previous values.

- Higher-Order Components or HOC.
This type of component is a design pattern used in React applications. This otherwise named design pattern in this ecosystem faithfully reminds me of the Decorator pattern.
The higher-order components (HOC) take another parameter component, extending its functionality and returning a new component with extended functionality. If the properties of the HOC change, the HOC will render again and update the component wrapped in it.
This type of component is used to implement common functionalities such as pagination, intercept and modify the rendering, make calls to APIs, feed the wrapped component, and control the inputs of forms.
This type of component is used in libraries widely used in the React ecosystem, such as react-redux and react-redux-form. Basically, it is a good method to decouple functionality, extend the functionality of our components and reuse the code throughout our application.


Types of Structural Components
These components do not technically correspond to any API element, class, or function in React. They are just purely conceptual. This categorization aims to organize our application so that it is simpler and more intuitive to develop. This categorization is not a React standard but a community standard and allows us to define architecture in our applications.

- Visual Components
These types of components should only focus and focus their efforts on how the UI should be rendered. These types of components can be made up of other visual elements and often include styles and classes. All the data involved in its rendering must be received through props, so it must be independent of calls to external services. These components are usually of the Stateless type since they do not need a state and must manage their actions to parent components through their props.

- Container Components
These components must put aside the interface and take care of the functional part. They are simply containers for other components and are in charge of managing the interaction logic and the data logic, making the necessary calls to external services. Unlike the previous ones, they usually manage their own state, being an important node in the hierarchy of the component tree.



---

## App Component

Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.

Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.

Components are autonomous, reusable pieces of code. Components are the fundamental units of React applications. Although they work independently and output HTML, they do the same thing as JavaScript functions. Components allow us to avoid writing unnecessary code. Components come in two types:
- Functional components
- Class components

A Component is one of the core building blocks of React. In other words, we can say that every application you will develop in React will be made up of pieces called components. Components make the task of building UIs much easier. You can see a UI broken down into multiple individual pieces called components and work on them independently and merge them all in a parent component which will be your final UI. 
You can see in the below image we have broken down the UI of GeeksforGeeks’s homepage into individual components. 

Google’s custom search at the top can be seen as an individual component, the navigation bar can be seen as an individual component, the sidebar is an individual component, the list of articles or post is also an individual component and finally, we can merge all of these individual components to make a parent component which will be the final UI for the homepage.
Components in React basically return a piece of JSX code that tells what should be rendered on the screen. In React, we mainly have two types of components: 
 

1. Functional Components: Functional components are simply javascript functions. We can create a functional component in React by writing a javascript function. These functions may or may not receive data as parameters, we will discuss this later in the tutorial. Below example shows a valid functional component in React: 

```sh
const Democomponent=()=>
{
    return <h1>Welcome Message!</h1>;
}
```

2. Class Components: The class components are a little more complex than the functional components. The functional components are not aware of the other components in your program whereas the class components can work with each other. We can pass data from one class component to other class components. We can use JavaScript ES6 classes to create class-based components in React. Below example shows a valid class-based component in React: 

```sh
class Democomponent extends React.Component
{
    render(){
          return <h1>Welcome Message!</h1>;
    }
}
```

The components we created in the above two examples are equivalent, and we also have stated the basic difference between a functional component and class component. We will learn about more properties of class-based components in further tutorials. For now, keep in mind that we will use functional component only when we are sure that our component does not require interacting or work with any other component. That is, these components do not require data from other components however we can compose multiple functional components under a single functional component. We can also use class-based components for this purpose but it is not recommended as using class-based components without need will make your application in-efficient.


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

## Rendering Components

In our previous post on rendering elements in React we have seen how elements initialized with DOM tags are rendered using ReactDOM.render() method. React is also capable of rendering user-defined components. To render a component in React we can initialize an element with a user-defined component and pass this element as the first parameter to ReactDOM.render() or directly pass the component as the first argument to the ReactDOM.render() method. 
Below syntax shows how to initialize a component to an element: 

```sh
const elementName = <ComponentName />;
```

In the above syntax, the ComponentName is the name of the user-defined component. 
Note: The name of a component should always start with a capital letter. This is done to differentiate a component tag with html tags.
Below example renders a component named Welcome to the screen: 

Open your index.js file from your project directory, and make the given below changes:

src index.js:

```sh

import React from 'react'; 
import ReactDOM from 'react-dom'; 
  
// This is a functional component 
const Welcome=()=>
{ 
        return <h1>Hello World!</h1> 
} 
  
ReactDOM.render( 
    <Welcome />, 
    document.getElementById("root") 
); 
```

Output: Hello World!

Let us see step-wise what is happening in the above example: 
1. We call the ReactDOM.render() as the first parameter.
2. React then calls the component Welcome, which returns <h1>Hello World!</h1>; as the result.
3. Then the ReactDOM efficiently updates the DOM to match with the returned element and renders that element to the DOM element with id as “root”.

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
.blog-preview:hover {
  box-shadow: 1px 3px 5px rgba(0,0,0,0.1);
}
.blog-preview h2 {
  font-size: 20px;
  color: #f1356d;
  margin-bottom: 8px;
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

## React Hooks

React Hooks are simple JavaScript functions that we can use to isolate the reusable part from a functional component. Hooks can be stateful and can manage side-effects. React hook is one of the holy grail of react. React hooks just makes your work so much easier, react hooks are designed to simplify difficult tasks like re-rendering the UI, managing state, picking an element from the DOM and lots more. There is a hook for most things you want and if there isn’t any react hook that meets your need then you can also build your own custom hook.

This ensures that there is less broiler plate code, we would have written more code if this was done without hooks or from a class based component. Hooks also eliminate the need for listening to multiple life cycle events on components, the hook manages all that behind the scene for you.

Hook in react is a special type of function that does a special type of job. You can tell a hook by it's name because it starts with 'use'. So useState hook gives us a way to make a reactive value and also provides us way to change the value.

We can use the hook as many times as we want in a component for different values. This value can be an array, object, boolean, string, number.

You can't put hooks inside if conditions, functions, loops etc. So, the can't be nested. Hooks will always stay at the top level in your App component.



## State `useState` Hook

Using State (useState hook)

React components has a built-in state object. The state object is where you store property values that belongs to the component. When the state object changes, the component re-renders.

State is handled & updated inside of a component and change the value. 
State is any data that changes application and so does ui. 

So, when you need a reactive value that might change in some point we will use `useState` hook todo that. We pass in an initial value 'mario' and we can output that value in a template { } and then we call the `set` function which is second value in the array [ name, setName ] to update it so that triggers a re-render and the new value is going to output to the browser.

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

In ReactJS, the props are a type of object where the value of attributes of a tag is stored. The word “props” implies “properties”, and its working functionality is quite similar to HTML attributes. Basically, these props components are read-only components.

Props are like arguments to a function and handled outside of a component and display information. Props are arguments passed into React components. Props allows us to pass data from one `parent` component to another `child` component. Props are passed to components via HTML attributes.

Import BlogList component from In Home.js file. Here `Home` is a parent component and `<BlogList />` is a child component.

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

Using Functions as Props in React:

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

The Effect Hook lets you perform side effects in function components. This useEffect Hook run code on every render. useEffect function fires on every render. When we change the data, it rerenders this to the DOM. Whenever the state changes, the useEffect function rerenders.

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
    console.log('use effect run');
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

Using useEffect Dependencies to stop rerenders by Dependency array which is passed inside useEffect function as a second argument.

You don't always want to run a function after every single renders, maybe only a certain render. To do that we can use something called 'dependency array'. This is basically an array that we can pass into an useEffect hook as an second argument. This hook only runs the function after the first initial render. Thereafter if the state changes it won't run the function again. It only runs it once.

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

Currently in our application we render the blog list once we have blog data and until then we don't render it. But it would be nice to create a loading massage whilst the data is being fetched so that user knows something is loading if it takes time to do. Here our fetch is very quick because we're just making a fetch to our own computer but most times the fetch will be to another server over the internet and slower. In which case the user will see that loading message while we fetch the data. So, to do this we're going to create an additional piece of state inside the home component and that is gonna be called isPending here.

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

We want to handle any kind of error inside the Home component when we try to make the fetch. This error can be set back from server or some kind of connection error. In that case we wouldn't get the data back and let user know some kind of error. So, add a catch block after fetching data:

```sh
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
  const [blogs, setBlogs] = useState(null);
  const [isPending, setIsPending] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    setTimeout(() => {
      fetch('http://localhost:8000/blogs')
      .then(res => {
        if (!res.ok) { // error coming back from server
          throw Error('could not fetch the data for that resource');
        } 
        return res.json();
      })
      .then(data => {
        setIsPending(false);
        setBlogs(data);
        setError(null);
      })
      .catch(err => {
        // auto catches network / connection error
        setIsPending(false);
        setError(err.message);
      })
    }, 1000);
  }, [])

  return (
    <div className="home">
      { error && <div>{ error }</div> }
      { isPending && <div>Loading...</div> }
      { blogs && <BlogList blogs={blogs} /> }
    </div>
  );
}
 
export default Home;
```

---

## Custom Hook

Previously we've put together all those logic inside the useEffect hook to update 
all of these state properties to output the data or loading massage or an error if there is one.
But what if we want to do this same kind of thing in another component in the future where we fetch some data or create state for the data itself the error and is pending property etc. We then have to rewrite all of these code in that component again. Which is not easy to manage especially if you put these code in a few different places in your application.
So, it would be good if we could make use of all of this code again in different component so make it bit more reusable so we don't have to continuously write it out again and again.
So when we do something like this by externalizing the logic into its own file we're creating something called a `Custom Hook` in react. It's a bit like useState & useEffect have their own specific functionality as hooks. We'd be creating a Custom Hook with a specific ability to fetch data. 

In order to make this custom hook, we first make a new file named useFetch.js in the source folder:

```sh
import { useState, useEffect } from 'react';

const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [isPending, setIsPending] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    setTimeout(() => {
      fetch(url)
      .then(res => {
        if (!res.ok) { // error coming back from server
          throw Error('could not fetch the data for that resource');
        } 
        return res.json();
      })
      .then(data => {
        setIsPending(false);
        setData(data);
        setError(null);
      })
      .catch(err => {
        // auto catches network / connection error
        setIsPending(false);
        setError(err.message);
      })
    }, 1000);
  }, [url])

  return { data, isPending, error };
}
 
export default useFetch;
```

In Home.js file import the functions:

```sh
import { useEffect, useState } from "react";
import BlogList from "./BlogList";
import useFetch from "./useFetch";

const Home = () => {
  const { error, isPending, data: blogs } = useFetch('http://localhost:8000/blogs')

  return (
    <div className="home">
      { error && <div>{ error }</div> }
      { isPending && <div>Loading...</div> }
      { blogs && <BlogList blogs={blogs} /> }
    </div>
  );
}
 
export default Home;
```

---

## React Router

React Router is a standard library for routing in React. It enables the navigation among views of various components in a React Application, allows changing the browser URL, and keeps the UI in sync with the URL.

By far our application has one single page, we don't navigate around to other pages we just have this single home page and most websites you create are gonna have probably multi page. So we need a way to introduce multiple different pages or routes in our react application and the way we do this in react is with the react router.

So we assign a top level component for each route or page and that component is dynamically injected into the browser when we visit that route. Now, this whole process means that we're making less request to the server and the whole website therefore feels faster and slicker. We need to install `React Router` package for this because it's not the part of core react library.

In terminal:

```sh
npm install react-router-dom@6
```

In App.js file import the router:

```sh
import Navbar from './Navbar';
import Home from './Home';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

function App() {
  return (
    <Router>
      <div className="App">
        <Navbar />        // same on every page
        <div className="content">
          <Switch>        // content inside switch change on every page
            <Route path="/">        // root path
              <Home />
            </Route>
          </Switch>
        </div>
      </div>
    </Router>
  );
}

export default App;
```


---

## Exact Match Routes

Let's set another route and to do this we need another page component. This gonna be a web form to add new blog. We name it Create component.

In Create.js create a function Create:

```sh
const Create = () => {
  return (
    <div className="create">
      <h2>Add a New Blog</h2>
    </div>
  );
}

export default Create;
```

In App.js file import the router:

```sh
import Navbar from './Navbar';
import Home from './Home';
import Create from './Create';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

function App() {
  return (
    <Router>
      <div className="App">
        <Navbar />        // same on every page
        <div className="content">
          <Switch>        // content inside switch change on every page
            <Route exact path="/">        // root path
              <Home />
            </Route>
            <Route path="/create">        // another root path
              <Create />
            </Route>
          </Switch>
        </div>
      </div>
    </Router>
  );
}

export default App;
```

We want to match this if this is exactly the route So we add `exact` prop. So now it only match this if it's exactly the url we go to not just inside the url.


---

## Router Links

Go to the Navbar.js file import the link tag from react router dom package:

```sh
import { Link } from 'react-router-dom';

const Navbar = () => {
  return (
    <nav className="navbar">
      <h1>The Dojo Blog</h1>
      <div className="links">
        <Link to="/">Home</Link>        // a is replaced by 'Link' & href is repalced by 'to'
        <a to="/create">New Blog</a>
      </div>
    </nav>
  );
}

export default Navbar;
```

A link component doesn't have an href like an anchor tag instead it uses 'to' by this way react prevents reloading full html and only triggers the route link which is previously defined with "/create".

---

## useEffect Cleanup

Click 'New Blog' then click 'home' then click 'New Blog' again will show error in console. Because it still tries to update the Home component which is not in browser anymore. 

We will be using a combination of Cleanup function in a useEffect hook and something called 'Abort Controller' in JavaScript. 
Now we will place the Cleanup function inside useEffect hook and we will just return it. That returned value is a function. When the component that uses the useEffect or this use fetch hook on mounts it fires that returned Cleanup function. 
We will create Abort Controller inside useEffect. As because we want to stop the fetch that's going on in the background so that we don't try to update the state. For this we will use Abort Controller. We can associate it with a specific fetch request. Once we have associated it with a fetch we can use the Abort Controller to stop the fetch. 

Go to the usefetch.js:

```sh
import { useState, useEffect } from 'react';

const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [isPending, setIsPending] = useState(true);
  const [error, setError] = useState(null);
  
  useEffect(() => {
    const abortCont = new AbortController();         // Abort Controller
    
    setTimeout(() => {
      fetch(url, { signal:  abortCont.signal })
       .then(res => {
        if (!res.ok) { // error coming back from server
          throw Error('could not fetch the data for that resource');
        } 
        return res.json();
      })
      
      .then(data => {
        setIsPending(false);
        setData(data);
        setError(null);
      })
      .catch(err => {
        if (err.name === 'AbortError') {           // stop the fetch
          console.log('fetch aborted');
        } else {
        setIsPending(false);
        setError(err.message);
        }
      })
    }, 1000);
    
    return () => abortCont.abort();
  }, [url])

  return { data, isPending, error };
}
 
export default useFetch;
```




---

## Route Parameters

A route is where a certain part of it is changable but regardless of what that changable part is it still renders the same page or component. Example is a blog details page. eg: `/blogs/123` or `/blogs/456` or `/blogs/789` in these cases we would still render the same blog details components but instead we would show the blog with these ids. So this changable part of the route is knows as a route parameter. It's like a variable inside a route. In our react application we need to be able to use route parameters and access those route parameters from our components. So that in the component we can use these ids for example to fetch data for that particular blog. 

Create BlogDetails.js file:

```sh
import { useParams } from 'react-router-dom';

const BlogDetails = () => {
  const { id } = useParams();         // creating new hook to connect exact id of the blogs route

  return (
    <div className="blog-details">
       <h2>Blog Details - { id } </h2>
    </div>
  );
}

export default BlogDetails;
```

In App.js file import the router:

```sh
import Navbar from './Navbar';
import Home from './Home';
import Create from './Create';
import BlogDetails from './BlogDetails';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

function App() {
  return (
    <Router>
      <div className="App">
        <Navbar />        // same on every page
        <div className="content">
          <Switch>        // content inside switch change on every page
            <Route exact path="/">        // root path
              <Home />
            </Route>
            <Route path="/create">        // another root path
              <Create />
            </Route>
            <Route path="/blogs/:id">        // Route Parameters
              <BlogDetails />
            </Route>
          </Switch>
        </div>
      </div>
    </Router>
  );
}

export default App;
```


In BlogList.js file import router:

```sh
import { Link } from 'react-router-dom';

const BlogList = ({ blogs, title, handleDelete }) => {
  return (
    <div className="blog-list">
      <h2>{ title }</h2>
      {blogs.map(blog => (
        <div className="blog-preview" key={blog.id} >
          <Link to={`/blogs/${blog.id}`}>                 // made it dynamic with {}
             <h2>{ blog.title }</h2>
             <p>Written by { blog.author }</p>
          </Link>
        </div>
      ))}
    </div>
  );
}

export default BlogList;
```

---

## Reusing Custom Hooks

Now we can click one of these links to go through to the blog details page where we have access to that route parameter the id for that blog. S o we can use that inside this component now to make a fetch request for the details of that particular blog from the json db file. So, to do that we are gonna be reusing our custom hook `useFetch`. Now remenber this returns 3 values. The data we're trying to fetch which is the individual blog, the isPending property which is 'true' or 'false', then an error if there is one. 

All we have to do is to use this hook in the blog details and pass in the url.

In BlogDetails.js file:

```sh
import { useParams } from 'react-router-dom';
import useFetch from './useFetch';

const BlogDetails = () => {
  const { id } = useParams();
  const { data: blog, error, isPending } = useFetch('http://localhost:8000/blogs/' + id);

  return (
    <div className="blog-details">
       { isPending && <div>Loading...</div> }
       { error && <div>{ error }</div> }
       { blog && (
         <article>
           <h2>{ blog.title }</h2>
           <p>Written by { blog.author }</p>
           <div>{ blog.body }</div>
         <article>
       )}
    </div>
  );
}

export default BlogDetails;
```

---

## Controlled Inputs Forms

We will now create web forms for react. So that a user can type a new blog and add that later to send a post request. So it adds it to the json data. In order to do it we need to create few Controlled Inputs and different form fields.

Controlled Inputs in react is basically a way of setting up input fields in forms so that we can track their values. If it is a text input field where a user can type into it and we can store that value in a state and if that state changes it updates the value that we see in the input field. So we always keeping the input field and our state in sync with each other. 

In Create.js file make a form:

```sh
import { useState } from 'react';

const Create = () => {
  const [ title, setTitle ] = useState('');
  const [ body, setBody ] = useState('');
  const [ author, setAuthor ] = useState('mario');

  return (
    <div className="create">
      <h2>Add a New Blog</h2>
      <form>
        <label>Blog Title:</label>
        <input type="text" required value={ title } onChange={ (e) => setTitle(e.target.value) } ></>
        <label>Blog Body:</label>
        <textarea required value={ body } onChange={ (e) => setBody(e.target.value) } ></textarea>
        <label>Blog Author:</label>
        <select value={ author } onChange={ (e) => setAuthor(e.target.value) } >
          <option value="mario">Mario</option>
          <option value="yoshi">Yoshi</option>
        </select>
        <button>Add Blog</button>
        <p>{ title }</p>
        <p>{ body }</p>
        <p>{ author }</p>
      </form>
    </div>
  );
}

export default Create;
```


---

## Submit Events

When a button is pressed inside a form, it fires a submit event on the form itself so that we can listen that submit event and react to it.  

In Create.js file include a submit event:

```sh
import { useState } from 'react';

const Create = () => {
  const [ title, setTitle ] = useState('');
  const [ body, setBody ] = useState('');
  const [ author, setAuthor ] = useState('mario');
  
   const handleSubmit = (e) => {
     e.preventDefault();                           // stop page refresh
     const blog = { title, body, author };         // create blog object
   };

  return (
    <div className="create">
      <h2>Add a New Blog</h2>
      <form onSubmit={ handleSubmit }>             // handleSubmit function added
        <label>Blog Title:</label>
        <input type="text" required value={ title } onChange={ (e) => setTitle(e.target.value) } ></>
        <label>Blog Body:</label>
        <textarea required value={ body } onChange={ (e) => setBody(e.target.value) } ></textarea>
        <label>Blog Author:</label>
        <select value={ author } onChange={ (e) => setAuthor(e.target.value) } >
          <option value="mario">Mario</option>
          <option value="yoshi">Yoshi</option>
        </select>
        <button>Add Blog</button>
        <p>{ title }</p>
        <p>{ body }</p>
        <p>{ author }</p>
      </form>
    </div>
  );
}

export default Create;
```



---

## Making Post Request

We will make a request to the json server. This time we will not use useFetch hook to make a universal post.

We will make this post requet inside the handleSubmit function because we're gonna make this request once in whole application.

In Create.js file create a post request:

```sh
import { useState } from 'react';

const Create = () => {
  const [ title, setTitle ] = useState('');
  const [ body, setBody ] = useState('');
  const [ author, setAuthor ] = useState('mario');
  const [ isPending, setIsPending ] = useState(false);         // a state for loading message
                                         // we don't want loading run from start so false
  
   const handleSubmit = (e) => {
     e.preventDefault();
     const blog = { title, body, author };
     
     setIsPending(true);          // loading starts
     
     
     fetch('http://localhost:8000/blogs', {              // same endpoint from home component
       method: 'POST',
       headers: { "Content-Type:" "application/json" },      // we're sending json data
       body: JSON.stringify(blog)                        // from object to string
     }).then(() => {              // since it's asynchronous and returns a promise so 'then'
        console.log('new blog added')
        setIsPending(false);      // false when loading completed
      });
   }

  return (
    <div className="create">
      <h2>Add a New Blog</h2>
      <form onSubmit={ handleSubmit }>
        <label>Blog Title:</label>
        <input type="text" required value={ title } onChange={ (e) => setTitle(e.target.value) } ></>
        <label>Blog Body:</label>
        <textarea required value={ body } onChange={ (e) => setBody(e.target.value) } ></textarea>
        <label>Blog Author:</label>
        <select value={ author } onChange={ (e) => setAuthor(e.target.value) } >
          <option value="mario">Mario</option>
          <option value="yoshi">Yoshi</option>
        </select>
        { !isPending && <button>Add Blog</button> }                  // when false
        { isPending && <button disabled>Adding Blog...</button> }      // when true
      </form>
    </div>
  );
}

export default Create;
```


---

## Programmatic Redirects

Now we successfully added new blog by submitting the form. But once we added the blog it stays in the same page. We want it redirect to the home page after submitting the form. In order to do so we need another hook that is called `useHistory`. It helps to back and forward to history and also add a new page to the history in another words redirect them to a new route. 

In Create.js file create a new hook:

```sh
import { useState } from 'react';
import { useHistory } from 'react-router-dom';

const Create = () => {
  const [ title, setTitle ] = useState('');
  const [ body, setBody ] = useState('');
  const [ author, setAuthor ] = useState('mario');
  const [ isPending, setIsPending ] = useState(false);
  const history = useHistory();  
  
   const handleSubmit = (e) => {
     e.preventDefault();
     const blog = { title, body, author };
     
     setIsPending(true);          // loading starts
     
     
     fetch('http://localhost:8000/blogs', {              // same endpoint from home component
       method: 'POST',
       headers: { "Content-Type:" "application/json" },      // we're sending json data
       body: JSON.stringify(blog)                        // from object to string
     }).then(() => {              // since it's asynchronous and returns a promise so 'then'
        console.log('new blog added')
        setIsPending(false);      // false when loading completed
        // history.go(-1);      // go back (to go forward give it a positive integer +1)
        history.push('/');     // go to home page
     });
   }

  return (
    <div className="create">
      <h2>Add a New Blog</h2>
      <form onSubmit={ handleSubmit }>
        <label>Blog Title:</label>
        <input type="text" required value={ title } onChange={ (e) => setTitle(e.target.value) } ></>
        <label>Blog Body:</label>
        <textarea required value={ body } onChange={ (e) => setBody(e.target.value) } ></textarea>
        <label>Blog Author:</label>
        <select value={ author } onChange={ (e) => setAuthor(e.target.value) } >
          <option value="mario">Mario</option>
          <option value="yoshi">Yoshi</option>
        </select>
        { !isPending && <button>Add Blog</button> }                  // when false
        { isPending && <button disabled>Adding Blog...</button> }      // when true
      </form>
    </div>
  );
}

export default Create;
```




---

## Deleting Blogs

Now we want to delete a blog by clicking a button at the bottom of the blog detail component. 

In BlogDetails.js file create a delete button:

```sh
import { useParams } from 'react-router-dom';
import useFetch from './useFetch';

const BlogDetails = () => {
  const { id } = useParams();
  const { data: blog, error, isPending } = useFetch('http://localhost:8000/blogs/' + id);
  const history = useHistory(); 
  
  const handleClick = (e) => {
    fetch('http://localhost:8000/blogs' + blog.id , {        // endpoint home component
       method: 'DELETE'
     }).then(() => {              // since it's asynchronous and returns a promise so 'then'
        history.push('/');     // go to home page
     });
  }

  return (
    <div className="blog-details">
       { isPending && <div>Loading...</div> }
       { error && <div>{ error }</div> }
       { blog && (
         <article>
           <h2>{ blog.title }</h2>
           <p>Written by { blog.author }</p>
           <div>{ blog.body }</div>
           <button onClick={ handleClick }>Delete</button>    // del btn with click handler
         <article>
       )}
    </div>
  );
}

export default BlogDetails;
```


---

## 404 Pages

It is 404 component or not found component. We want to stop routing of any unexpected url.

Create NotFound.js file:

```sh
import { Link } from 'react-router-dom';

const NotFound = () => {
  return (
    <div className="not-found">
       <h2>Sorry!</h2>
       <p>That page cannot be found.</p>
       <Link to="/">Back to the homepage...</Link>
    </div>
  );
}

export default NotFound;
```


In App.js file set the home route:

```sh
import Navbar from './Navbar';
import Home from './Home';
import Create from './Create';
import BlogDetails from './BlogDetails';
import NotFound from './NotFound';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

function App() {
  return (
    <Router>
      <div className="App">
        <Navbar />        // same on every page
        <div className="content">
          <Switch>        // content inside switch change on every page
            <Route exact path="/">        // root path
              <Home />
            </Route>
            <Route path="/create">        // another root path
              <Create />
            </Route>
            <Route path="/blogs/:id">        // Route Parameters
              <BlogDetails />
            </Route>
            <Route path="*">        // Set Home Route
              <NotFound />
            </Route>
          </Switch>
        </div>
      </div>
    </Router>
  );
}

export default App;
```

Here we added `*` on the path means 'catch any other routes'.

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


