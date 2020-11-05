# JavaScript

The programming language of the web.

## Notes

### Variables

```javascript
let x = 1 // Declares variable x with value of 1
const y = 4 // Declares a constant y with value 4

console.log(x) // 1 is printed to the console
x = 1234
console.log(x) // 1234 is printed to the console
y = "Hello" // causes an error
```

The value of `const` can't be changed through reassignment, and it can't be redeclared. `let` works like a normal variable declaration.

### Arrays

```javascript
const pets = ['dog', 'cat']
pets.push('goldfish')
console.log(pets) // ['dog', 'cat', 'goldfish'] will be printed to the console

pets.forEach(value => {
  console.log(value) // dog, cat, goldfish are printed, each on their own line
})
```

Note from the example that adding an element to an array or object, this is not re-assigning or re-declaring the constant, it's just adding to the array that the constant points to.

You can iterate on an array with `forEach`, this receives a function defined using arrow syntax as a parameter. forEach calls the function on each item of the array always passing the individual item as parameter.

We can asign individual items of an array to a variable using [destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

```javascript
const pets = ['dog', 'cat', 'hedghog', 'goldfish']

const [bestBoi, coolPet, ...otherPets] = pets
console.log(bestBoi) // dog
console.log(coolPet) // cat
console.log(otherPets) // ['hedghog', 'goldfish']
```

### Objects

```javascript
const person = {
  id: 123,
  name: 'Rick',
  gender: 'Male',
}
// object.properties or object[properties]
person.id // 123
person[name] // Rick
person.gender // Male
```

The values of the properties can be of any type. You can reference the properties of the object using "dot" notation or by using brackets. We can add a property on the fly using either dot notation or brackets.

```javascript
person.email = 'rick@example.com'
person[petName] = 'Al'
```

### Functions

**Arrow functions**

```javascript
let product = (a, b) => {
  return a * b
}
```

There are two ways you can define a function prior to ES6 **Giving a name on function declaration**

```javascript
function welcomeMessage(name) {
  return `Welcome home ${name}` 
}
const message = welcomeMessage('John') // Welcome home John
```

**Define the function using a function expression**

```javascript
const powerOfTwo = funtion(a) {
  return a ** 2
}
const result = powerOfTwo(8) // 64
```

### "this"

**this** is defined based on how the method is called. When calling a method through a reference the value of `this` becomes [global object](https://developer.mozilla.org/en-US/docs/Glossary/Global_object)

## Resources

* [MDN JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
* [You Don't Know JS](https://github.com/getify/You-Dont-Know-JS)

## JavasScript Frameworks

* [React](../javascript-frameworks/react.md): is a JavaScript library for building user interfaces.

