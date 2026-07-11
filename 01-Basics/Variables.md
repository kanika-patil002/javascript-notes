# Variables in JavaScript

## Introduction

A variable is a named container used to store data in a program. Think of it like a labeled box — you put a value inside it, give the box a name, and later you can look inside the box (read the value) or replace what's inside (update the value).

In JavaScript, you can create variables using three keywords: `var`, `let`, and `const`. Each behaves differently in terms of scope, whether it can be reassigned, and how it handles redeclaration. Understanding these differences is one of the most fundamental skills every JavaScript developer needs.

## Why is it important?

- Variables are the building blocks of every JavaScript program — without them, you couldn't store user input, track application state, or perform calculations.
- Choosing the right variable type (`let` vs `const`) makes your code safer and easier to understand.
- Interviewers frequently test `var` vs `let` vs `const` because it reveals whether a candidate understands scope, hoisting, and modern JavaScript best practices.
- Frameworks like React, Vue, and Node.js rely heavily on `const` and `let` for predictable, bug-free state management.

## Syntax

```javascript
var variableName = value;   // function-scoped, old way
let variableName = value;   // block-scoped, can be reassigned
const variableName = value; // block-scoped, cannot be reassigned
```

## Examples

### Example 1: Declaring and using variables

```javascript
// Declaring variables using let and const
let city = "Mumbai";       // can be changed later
const country = "India";   // cannot be changed later

console.log(city);
console.log(country);

// Reassigning a let variable
city = "Delhi";
console.log(city);
```

### Output
```
Mumbai
India
Delhi
```

### Example 2: var vs let scope difference

```javascript
function testVar() {
  if (true) {
    var x = 10; // function-scoped
  }
  console.log(x); // accessible outside the if block
}

function testLet() {
  if (true) {
    let y = 20; // block-scoped
  }
  console.log(y); // throws an error, not accessible here
}

testVar();
testLet();
```

### Output
```
10
Uncaught ReferenceError: y is not defined
```

### Example 3: const with objects and arrays

```javascript
// const prevents reassignment, but object/array contents can still change
const person = { name: "Riya", age: 22 };
person.age = 23; // allowed, we are modifying a property, not reassigning
console.log(person);

const numbers = [1, 2, 3];
numbers.push(4); // allowed
console.log(numbers);

// person = {}; // this would throw an error
```

### Output
```
{ name: 'Riya', age: 23 }
[ 1, 2, 3, 4 ]
```

## Explanation

**Example 1:**
- `let city = "Mumbai";` creates a variable that can later be reassigned.
- `const country = "India";` creates a variable whose value cannot be reassigned.
- `city = "Delhi";` successfully changes the value because `city` was declared with `let`.

**Example 2:**
- Inside `testVar()`, `var x` is declared inside an `if` block, but because `var` is function-scoped, `x` is accessible anywhere inside the function, even outside the block.
- Inside `testLet()`, `let y` is block-scoped, so it only exists inside the `if {}` block. Trying to access `y` outside that block throws a `ReferenceError`.

**Example 3:**
- `const person` cannot be reassigned to a new object, but you can still change its properties (`person.age = 23`) because you are modifying the object's contents, not the reference itself.
- Similarly, `numbers.push(4)` modifies the array's contents without reassigning the `numbers` variable, so it is allowed with `const`.

## Key Points

| Feature | var | let | const |
|---|---|---|---|
| Scope | Function-scoped | Block-scoped | Block-scoped |
| Redeclaration | Allowed | Not allowed | Not allowed |
| Reassignment | Allowed | Allowed | Not allowed |
| Hoisting | Hoisted, initialized as `undefined` | Hoisted, but in "temporal dead zone" | Hoisted, but in "temporal dead zone" |
| Must initialize at declaration | No | No | Yes |

- `var` is the oldest way to declare variables and is generally avoided in modern code.
- `let` is used when the value needs to change later.
- `const` is used when the value should not be reassigned — this is the recommended default choice.
- Both `let` and `const` were introduced in ES6 (2015) to fix scoping issues caused by `var`.




