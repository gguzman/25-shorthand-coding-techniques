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
