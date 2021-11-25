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
