# React
A JavaScript library for building user interfaces.

## Features
1. Declarative
2. Component Based

## Notes
Components accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.

React embraces that rendering logic is coupled with other UI logic: State changes, event handling and how the data is prepared for rendering.

React uses bable under the hood to convert JSX into regular JavaScript.
#### JSX
Is a syntax extension to JavaScript. JSX produces React "Elements".

#### Function Components
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
The content of a React component (usually) needs to contain one root element, if not, it will throw an error.
We can wrap it on a `<div>` or use what Ract calls [fragments](https://reactjs.org/docs/fragments.html#short-syntax) which look like this: `<> </>`.

#### Props
You can pass data into a component using props.

```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

<Welcome name="Bob" /> //Will return "Hello, Bob" 
<Welcome name="Alice" /> //Will return "Hello, Alice" 
```
There can be an arbitrary number of props and their values can be "hard coded" strings or results of JavaScript expressions. If the value of the prop is achieved using JavaScript it must be wrapped with curly braces.

##### Destructuring props
We can use destructuring to assign variable names to props since *props* is an object.
```javascript
const Component = (props) => {
  const [name, age] = props // Instead of calling props.name or props.age, we can call name or age.
  // The rest of the component...
}

const AnotherComponent = ({name, age}) => {
  // Here instead of asigning the entire props object, we assign the values of the properties directly to variables by destructuring the props object that is passed to the component function as a parameter
}
``` 

#### Component helper functions
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

#### Statefull Components
We can add state to our app using React's [state hook.](https://reactjs.org/docs/hooks-state.html)
```javascript
import React, { useState } from 'react' // Import useState function
import ReactDOM from 'react-dom'

const App = () => {
  const [ counter, setCounter ] = useState(0) 
  setTimeout(    () => setCounter(counter + 1),    1000  )
  return (
    <div>{counter}</div>
  )
}

ReactDOM.render(
  <App />, 
  document.getElementById('root')
)
```
Example taken from [Fullstack Open.](https://fullstackopen.com/en/part1/component_state_event_handlers)
in this example, `counter` variable is assigned to the intial value of the state. `setCounter` is assigned to the fuction that will be used to modify the state.

## Resources
[React Website](https://reactjs.org/)
[What is React?](https://www.youtube.com/watch?v=1wZoGFF_oi4&list=PLZlA0Gpn_vH_NT5zPVp18nGe_W9LqBDQK): Video from  Web Dev Simplified explaning what is react and why you should learn it.