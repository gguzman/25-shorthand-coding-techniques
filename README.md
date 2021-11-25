# 25+ JavaScript Shorthand Coding Techniques
To help you understand what is going on, I have included the longhand versions to give some coding perspective.

## 1. The Ternary Operator

This is a great code saver when you want to write an `if..else` statement in just one line.

Longhand:
```js
const x = 20;
let answer;

if (x > 10) {
    answer = "greater than 10";
} else {
    answer =  "less than 10";
}
```

Shorthand:

```js
const answer = x > 10 ? "greater than 10" : "less than 10";
```

You can also nest your if statement like this:
```js
const answer = x > 10 ? "greater than 10" : x < 5 ? "less than 5" : "between 5 and 10";
```

## 2. Short-circuit Evaluation Shorthand

When assigning a variable value to another variable, you may want to ensure that the source variable is not null, undefined, or empty. You can either write a long `if` statement with multiple conditionals, or use a short-circuit evaluation.

Longhand:
```js
if (variable1 !== null || variable1 !== undefined || variable1 !== '') {
     let variable2 = variable1;
}
```

Shorthand:

```js
const variable2 = variable1  || 'new';
```

Don’t believe me? Test it yourself (paste the following code in [es6console](https://es6console.com/)):
```js
let variable1;
let variable2 = variable1  || 'bar';
console.log(variable2 === 'bar'); // prints true

variable1 = 'foo';
variable2 = variable1  || 'bar';
console.log(variable2); // prints foo
```

Do note that if you set `variable1` to `false` or `0`, the value `bar` will be assigned.

## 3. Declaring Variables Shorthand

It’s good practice to declare your variable assignments at the beginning of your functions. This shorthand method can save you lots of time and space when declaring multiple variables at the same time.

Longhand:
```js
let x;
let y;
let z = 3;
```

Shorthand:

```js
let x, y, z=3;
```

## 4. If Presence Shorthand

This might be trivial, but worth a mention. When doing “`if` checks”, assignment operators can sometimes be omitted.

Longhand:

```js
if (likeJavaScript === true)
```

Shorthand:

```js
if (likeJavaScript)
```

>Note: these two examples are not exactly equal, as the shorthand check will pass as long as `likeJavaScript` is a [truthy value](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).

Here is another example. If `a` is NOT equal to true, then do something.

Longhand:

```js
let a;
if ( a !== true ) {
// do something...
}
```

Shorthand:

```js
let a;
if ( !a ) {
// do something...
}
```

## 5. JavaScript For Loop Shorthand

This little tip is really useful if you want plain JavaScript and don’t want to rely on external libraries such as jQuery or lodash.

Longhand:

```js
const fruits = ['mango', 'peach', 'banana'];
for (let i = 0; i < fruits.length; i++)
```

Shorthand:

```js
for (let fruit of fruits)
```

If you just wanted to access the index, do:

```js
for (let index in fruits)
```

This also works if you want to access keys in a literal object:

```js
const obj = {continent: 'Africa', country: 'Kenya', city: 'Nairobi'}
for (let key in obj)
  console.log(key) // output: continent, country, city
```

Shorthand for Array.forEach:
```js
function logArrayElements(element, index, array) {
  console.log("a[" + index + "] = " + element);
}
[2, 5, 9].forEach(logArrayElements);
// a[0] = 2
// a[1] = 5
// a[2] = 9
```

## 6. Short-circuit Evaluation
Instead of writing six lines of code to assign a default value if the intended parameter is null or undefined, we can simply use a short-circuit logical operator and accomplish the same thing with just one line of code.

Longhand:

```js
let dbHost;
if (process.env.DB_HOST) {
  dbHost = process.env.DB_HOST;
} else {
  dbHost = 'localhost';
}
```

Shorthand:

```js
const dbHost = process.env.DB_HOST || 'localhost';
```
## 7. Decimal Base Exponents
You may have seen this one around. It’s essentially a fancy way to write numbers without the trailing zeros. For example, 1e7 essentially means 1 followed by 7 zeros. It represents a decimal base (which JavaScript interprets as a float type) equal to 10,000,000.

Longhand:

```js
for (let i = 0; i < 10000; i++) {}
```

Shorthand:

```js
for (let i = 0; i < 1e7; i++) {}

// All the below will evaluate to true
1e0 === 1;
1e1 === 10;
1e2 === 100;
1e3 === 1000;
1e4 === 10000;
1e5 === 100000;
```

## 8. Object Property Shorthand
Defining object literals in JavaScript makes life much easier. ES6 provides an even easier way of assigning properties to objects. If the variable name is the same as the object key, you can take advantage of the shorthand notation.

Longhand:

```js
const x = 1920, y = 1080;
const obj = { x:x, y:y };
```

Shorthand:

```js
const obj = { x, y };
```

## 9. Arrow Functions Shorthand
Classical functions are easy to read and write in their plain form, but they do tend to become a bit verbose and confusing once you start nesting them in other function calls.

Longhand:

```js
function sayHello(name) {
  console.log('Hello', name);
}

setTimeout(function() {
  console.log('Loaded')
}, 2000);

list.forEach(function(item) {
  console.log(item);
});
```

Shorthand:

```js
sayHello = name => console.log('Hello', name);

setTimeout(() => console.log('Loaded'), 2000);

list.forEach(item => console.log(item));
```

It’s important to note that the value of `this` inside an arrow function is determined differently than for longhand functions, so the two examples are not strictly equivalent. See [this article on arrow function syntax](https://www.sitepoint.com/es6-arrow-functions-new-fat-concise-syntax-javascript/) for more details.


## 10. Implicit Return Shorthand
Return is a keyword we use often to return the final result of a function. An arrow function with a single statement will implicitly return the result its evaluation (the function must omit the braces (`{}`) in order to omit the return keyword).

To return a multi-line statement (such as an object literal), it’s necessary to use `()` instead of `{}` to wrap your function body. This ensures the code is evaluated as a single statement.

Longhand:

```js
function calcCircumference(diameter) {
  return Math.PI * diameter
}
```

Shorthand:

```js
calcCircumference = diameter => (
  Math.PI * diameter;
)
```

## 11. Default Parameter Values
You can use the `if` statement to define default values for function parameters. In ES6, you can define the default values in the function declaration itself.

Longhand:

```js
function volume(l, w, h) {
  if (w === undefined)
    w = 3;
  if (h === undefined)
    h = 4;
  return l * w * h;
}
```

Shorthand:

```js
volume = (l, w = 3, h = 4 ) => (l * w * h);

volume(2) //output: 24
```

## 12. Template Literals
Aren’t you tired of using `' + '` to concatenate multiple variables into a string? Isn’t there a much easier way of doing this? If you are able to use ES6, then you are in luck. All you need to do is use is the backtick, and `${}` to enclose your variables.

Longhand:

```js
const welcome = 'You have logged in as ' + first + ' ' + last + '.'

const db = 'http://' + host + ':' + port + '/' + database;
```

Shorthand:

```js
const welcome = `You have logged in as ${first} ${last}`;

const db = `http://${host}:${port}/${database}`;
```

## 13. Destructuring Assignment Shorthand
If you are working with any popular web framework, there are high chances you will be using arrays or data in the form of object literals to pass information between components and APIs. Once the data object reaches a component, you’ll need to unpack it.

Longhand:

```js
const observable = require('mobx/observable');
const action = require('mobx/action');
const runInAction = require('mobx/runInAction');

const store = this.props.store;
const form = this.props.form;
const loading = this.props.loading;
const errors = this.props.errors;
const entity = this.props.entity;
```

Shorthand:

```js
import { observable, action, runInAction } from 'mobx';

const { store, form, loading, errors, entity } = this.props;
```

You can even assign your own variable names:

```js
const { store, form, loading, errors, entity:contact } = this.props;
```
