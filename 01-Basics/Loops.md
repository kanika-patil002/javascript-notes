# Loops in JavaScript

## Introduction

A loop is a way to repeat a block of code multiple times without writing it over and over. Instead of manually writing `console.log()` five times, a loop can run the same instruction as many times as needed based on a condition.

JavaScript provides several types of loops: `for`, `while`, `do...while`, `for...of`, and `for...in`, each suited to different situations.

## Why is it important?

- Loops are essential for processing collections of data — iterating over arrays, objects, and lists is one of the most common tasks in programming.
- They reduce repetitive code and make programs shorter and easier to maintain.
- Real-world use cases include rendering lists of items on a webpage, processing API data, searching, and performing calculations across a dataset.

## Syntax

```javascript
// for loop
for (initialization; condition; increment) {
  // code to repeat
}

// while loop
while (condition) {
  // code to repeat
}

// do...while loop
do {
  // code to repeat
} while (condition);

// for...of (iterates over values - arrays, strings, etc.)
for (const value of iterable) {
  // code
}

// for...in (iterates over keys - objects)
for (const key in object) {
  // code
}
```

## Examples

### Example 1: for loop

```javascript
// Prints numbers 1 to 5
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

### Output
```
1
2
3
4
5
```

### Example 2: while and do...while loop

```javascript
// while loop: condition checked before running
let count = 1;
while (count <= 3) {
  console.log("While count:", count);
  count++;
}

// do...while loop: runs at least once, condition checked after
let num = 10;
do {
  console.log("Do-while num:", num);
  num++;
} while (num < 10);
```

### Output
```
While count: 1
While count: 2
While count: 3
Do-while num: 10
```

### Example 3: for...of and for...in

```javascript
// for...of iterates over array values
const fruits = ["apple", "banana", "mango"];
for (const fruit of fruits) {
  console.log(fruit);
}

// for...in iterates over object keys
const person = { name: "Aisha", age: 24, city: "Pune" };
for (const key in person) {
  console.log(key + ":", person[key]);
}
```

### Output
```
apple
banana
mango
name: Aisha
age: 24
city: Pune
```

## Explanation

**Example 1:**
- `let i = 1` initializes the loop counter.
- `i <= 5` is the condition checked before each iteration; the loop continues while it's `true`.
- `i++` increases `i` by 1 after each iteration, eventually making the condition `false` and stopping the loop.

**Example 2:**
- The `while` loop checks `count <= 3` before each run, so it prints `1`, `2`, and `3`.
- The `do...while` loop runs its block first, then checks the condition. Even though `num < 10` is `false` from the start (`num` is `10`), the block still executes once before the loop exits — this is the key difference from a regular `while` loop.

**Example 3:**
- `for...of` loops through the actual values of an iterable like an array, giving `"apple"`, `"banana"`, `"mango"` directly.
- `for...in` loops through the keys (property names) of an object. `person[key]` is used to access the value associated with each key.

## Key Points

| Loop Type | Best Used For | Checks Condition |
|---|---|---|
| `for` | Known number of iterations | Before each run |
| `while` | Unknown number of iterations, condition-based | Before each run |
| `do...while` | When code must run at least once | After each run |
| `for...of` | Iterating over values (arrays, strings, maps, sets) | N/A |
| `for...in` | Iterating over object keys | N/A |

- `for...of` should be used for arrays and other iterables; `for...in` is meant for object keys.
- Avoid using `for...in` on arrays, since it iterates over indices as strings and can include unexpected inherited properties.
- `break` exits a loop early; `continue` skips to the next iteration.

