<h1 align="center"><b>TUTORIAL: TIC-TAC-TOE</b></h1>

<!-- <br>
<hr>
<h3><a href=>Notes</a></h3>
<hr> -->


<!--==================================================-->
<br>

<p align="center">This repository showcases my work on building a tic-tac-toe game to learn the basics of React. It follows the instructions in an <a href="https://react.dev/learn/tutorial-tic-tac-toe">article</a> that guides you through setting up a development environment and creating the game board using React components.</p>



<!--==================================================-->
<br>
<p align="center">※※※※※※※※※※※※</p>
<br>

<details><summary align="center">React Basics</summary>

### 1. **Getting Started**

To start using React, you need to set up your development environment. You can use `create-react-app` to quickly set up a new React project.

```bash
npx create-react-app my-app
cd my-app
npm start
```

This will create a new React application and start a development server. Open `http://localhost:3000` to view your app.

### 2. **React Components**

React is all about components. A component is a reusable piece of UI. There are two types of components: functional and class components.

#### Functional Components

A functional component is a simple JavaScript function that returns JSX.

```jsx
import React from 'react';

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

export default Welcome;
```

#### Class Components

A class component is a more powerful, but more verbose, way to define a component.

```jsx
import React, { Component } from 'react';

class Welcome extends Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

export default Welcome;
```

### 3. **JSX**

JSX stands for JavaScript XML. It allows you to write HTML-like code inside your JavaScript, which makes it easier to create React components.

```jsx
const element = <h1>Hello, world!</h1>;
```

### 4. **Props**

Props (short for properties) are read-only inputs that are passed to components. They allow you to pass data from a parent component to a child component.

```jsx
function App() {
  return <Welcome name="Sara" />;
}

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

### 5. **State**

State is a way to store and manage data in a component. Unlike props, state is local to the component and can be changed.

#### Using State in Functional Components (with Hooks)

React introduced hooks to manage state in functional components. The `useState` hook is used to add state to a functional component.

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

export default Counter;
```

#### Using State in Class Components

Class components use `this.state` to hold the component's state and `this.setState` to update it.

```jsx
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    );
  }
}

export default Counter;
```

### 6. **Lifecycle Methods**

Lifecycle methods are special methods in class components that get called at different points in the component's life.

- `componentDidMount`: Called after the component is added to the DOM.
- `componentDidUpdate`: Called after the component's updates are flushed to the DOM.
- `componentWillUnmount`: Called right before the component is removed from the DOM.

### 7. **Handling Events**

Handling events in React is similar to handling events in regular HTML, but with some differences.

```jsx
function Button() {
  function handleClick() {
    alert('Button was clicked!');
  }

  return <button onClick={handleClick}>Click me</button>;
}
```

### 8. **Conditional Rendering**

You can use JavaScript conditions to control what gets rendered.

```jsx
function Greeting(props) {
  const isLoggedIn = props.isLoggedIn;
  if (isLoggedIn) {
    return <h1>Welcome back!</h1>;
  }
  return <h1>Please sign up.</h1>;
}
```

### 9. **Lists and Keys**

You can build lists of elements using the `map()` function.

```jsx
function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li key={number.toString()}>{number}</li>
  );
  return <ul>{listItems}</ul>;
}

const numbers = [1, 2, 3, 4, 5];
```

### 10. **Forms**

Forms in React are handled using controlled components, where form data is handled by the component's state.

```jsx
class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = { value: '' };

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({ value: event.target.value });
  }

  handleSubmit(event) {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <button type="submit">Submit</button>
      </form>
    );
  }
}
```

### 11. **Using External Data (Fetch API)**

You can use the `fetch` API or other methods to load data from external sources.

```jsx
import React, { useState, useEffect } from 'react';

function DataFetchingComponent() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []);

  return (
    <ul>
      {data.map(item => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}

export default DataFetchingComponent;
```

### Summary

These basics should help you get started with React. Here are some key points to remember:

- React components can be functional or class-based.
- JSX allows you to write HTML-like code in JavaScript.
- Props are read-only inputs passed to components.
- State is local to the component and can change over time.
- Use hooks like `useState` and `useEffect` in functional components.
- Lifecycle methods are available in class components.
- Handle events, conditionally render content, and manage forms using state.
- Fetch external data using APIs and display it in your components.

With these fundamentals, you'll be able to start building dynamic and responsive user interfaces using React.

</details>
