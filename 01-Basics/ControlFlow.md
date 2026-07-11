# Conditionals in JavaScript

## Introduction

Conditionals allow a program to make decisions and execute different blocks of code based on whether a condition is `true` or `false`. Instead of running every line of code in order, your program can choose different paths depending on the situation — just like how you decide "if it's raining, take an umbrella, else don't."

JavaScript provides `if`, `else if`, `else`, and the ternary operator (`? :`) to handle conditional logic.

## Why is it important?

- Almost every real application needs decision-making — validating login credentials, checking form input, showing/hiding UI elements, and controlling game logic all rely on conditionals.
- Conditionals are the foundation of control flow, which determines how a program behaves in different scenarios.
- Understanding conditionals deeply (including truthy/falsy values) prevents subtle logic bugs.

## Syntax

```javascript
// if statement
if (condition) {
  // code runs if condition is true
}

// if...else
if (condition) {
  // runs if true
} else {
  // runs if false
}

// if...else if...else
if (condition1) {
  // runs if condition1 is true
} else if (condition2) {
  // runs if condition2 is true
} else {
  // runs if none are true
}

// Ternary operator
condition ? expressionIfTrue : expressionIfFalse;
```

## Examples

### Example 1: Basic if...else

```javascript
let age = 20;

if (age >= 18) {
  console.log("You are eligible to vote.");
} else {
  console.log("You are not eligible to vote.");
}
```

### Output
```
You are eligible to vote.
```

### Example 2: if...else if...else ladder

```javascript
let marks = 75;

if (marks >= 90) {
  console.log("Grade: A");
} else if (marks >= 75) {
  console.log("Grade: B");
} else if (marks >= 50) {
  console.log("Grade: C");
} else {
  console.log("Grade: F");
}
```

### Output
```
Grade: B
```

### Example 3: Ternary operator

```javascript
let temperature = 15;

// Ternary is a shorthand for simple if...else
let weatherMessage = temperature > 20 ? "It's warm outside" : "It's cold outside";
console.log(weatherMessage);

// Nested ternary (use sparingly)
let score = 85;
let result = score >= 90 ? "A" : score >= 75 ? "B" : "C";
console.log(result);
```

### Output
```
It's cold outside
B
```

## Explanation

**Example 1:**
- The condition `age >= 18` is checked. Since `age` is `20`, the condition is `true`, so the code inside the `if` block runs and the `else` block is skipped.

**Example 2:**
- JavaScript checks each condition from top to bottom.
- `marks >= 90` is `false` (75 is not ≥ 90), so it moves to the next check.
- `marks >= 75` is `true`, so `"Grade: B"` is printed and the remaining conditions are skipped.

**Example 3:**
- `temperature > 20 ? "It's warm outside" : "It's cold outside"` is shorthand for an `if...else`. Since `15 > 20` is `false`, the value after the colon (`:`) is used.
- The nested ternary checks `score >= 90` first, then `score >= 75`. Since `85 >= 75` is `true`, `"B"` is returned.

## Key Points

| Statement | Use Case |
|---|---|
| `if` | Run code only when a single condition is true |
| `if...else` | Choose between two paths |
| `if...else if...else` | Choose among multiple paths |
| Ternary (`? :`) | Short, single-expression conditional, good for simple assignments |

- Conditions are evaluated based on truthy/falsy values, not just strict `true`/`false`.
- Only one block runs in an `if...else if...else` chain — as soon as a condition is `true`, the rest are skipped.
- Ternary operators are best for simple, short conditions. Deeply nested ternaries hurt readability.

