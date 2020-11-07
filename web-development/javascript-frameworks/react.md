# React

A JavaScript library for building user interfaces.

## Features

1. Declarative
2. Component Based

## Notes

The first version of these notes are based on [Fullstack Open course](https://fullstackopen.com/en/)

Components accept arbitrary inputs \(called “props”\) and return React elements describing what should appear on the screen.

React embraces that rendering logic is coupled with other UI logic: State changes, event handling and how the data is prepared for rendering.

React uses babel under the hood to convert JSX into regular JavaScript.

**You should never mutate the state directly.** The changes of the state has to be done by setting the state to a new object.

### JSX

Is a syntax extension to JavaScript. JSX produces React "Elements".

### Function Components

The simplest way to define a component is the following:

```javascript
const App = () => {
  return (
    <div>
      <p>Hello world</p>
    </div>
  )
}

function Example(props) {
  // Write component here
}
```

The content of a React component \(usually\) needs to contain one root element, if not, it will throw an error. We can wrap it on a `<div>` or use what React calls [fragments](https://reactjs.org/docs/fragments.html#short-syntax) which look like this: `<> </>`.

### Props

You can pass data into a component using props.

```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

<Welcome name="Bob" /> //Will return "Hello, Bob"
<Welcome name="Alice" /> //Will return "Hello, Alice"
```

There can be an arbitrary number of props and their values can be "hard coded" strings or results of JavaScript expressions. If the value of the prop is achieved using JavaScript it must be wrapped with curly braces.

#### Destructuring props

We can use destructuring to assign variable names to props since `props` is an object.

```javascript
const Component = (props) => {
  const [name, age] = props
  // The rest of the component...
}
```

Instead of calling `props.name` or `props.age`, we can call `name` or `age`.

```javascript
const AnotherComponent = ({ name, age }) => {
  // Component...
}
```

Another way is to assign the values of the properties directly to variables by destructuring the `props` object that is passed to the component function as a parameter.

### Component helper functions

Functions declared inside a component can access all props passed into the component.

```javascript
const AddMiddleName = (props) => {
  const albertMiddleName = () => {
    return `${props.firstName} Albert ${props.lastName}`
  }
  return (
    <div>
      <p>Your full name is {albertMiddleName()}</p>
    </div>
  )
}

<AddMiddleName firstName="Mike" lastName="Robinson"> // Renders Mike Albert Robinson
```

### Statefull Components

We can add state to our app using React's [state hook.](https://reactjs.org/docs/hooks-state.html)

```javascript
import React, { useState } from "react" // Import useState function
import ReactDOM from "react-dom"

const App = () => {
  const [counter, setCounter] = useState(0)
  setTimeout(() => setCounter(counter + 1), 1000)
  return <div>{counter}</div>
}

ReactDOM.render(<App />, document.getElementById("root"))
```

Example taken from [Fullstack Open.](https://fullstackopen.com/en/part1/component_state_event_handlers)
In this example, `counter` variable is assigned to the initial value of the state. `setCounter` is assigned to the function that will be used to modify the state.

### Event handling

Using JSX we pass a function as event handler instead of a string

```javascript
<button onClick={someFunction}>Cool button</button>
```

In React we must call `preventDefault` explicitly.

```javascript
function Hello() {
  function handleClick(e) {
    // Function that is going to be passed into the click event
    e.preventDefault()
    console.log("You clicked!")
  }
  return <button onClick={handleClick}>Click Me!</button>
}
```

Defining an event handler within JSX templates is not a good idea.

## Resources

[React Website](https://reactjs.org/)

[What is React?](https://www.youtube.com/watch?v=1wZoGFF_oi4&list=PLZlA0Gpn_vH_NT5zPVp18nGe_W9LqBDQK): Video from Web Dev Simplified explaining what is react and why you should learn it.
