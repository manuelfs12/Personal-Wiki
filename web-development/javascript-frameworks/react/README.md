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
the simplest way to define a component is the following:
```javascript
const App = () => {
  return (
    <div>
      <p>Hello world</p>
    </div>
  )
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

## Resources
[React Website](https://reactjs.org/)
[What is React?](https://www.youtube.com/watch?v=1wZoGFF_oi4&list=PLZlA0Gpn_vH_NT5zPVp18nGe_W9LqBDQK): Video from  Web Dev Simplified explaning what is react and why you should learn it.