# Type Conversion in JavaScript

## Introduction

Type conversion is the process of converting a value from one data type to another — for example, turning a string `"25"` into a number `25`, or a number `0` into a boolean `false`. JavaScript is a loosely typed language, which means variables are not locked to a single data type and can be converted automatically or manually as needed.

There are two kinds of type conversion in JavaScript:
- **Implicit conversion (type coercion)** — JavaScript automatically converts a value's type behind the scenes.
- **Explicit conversion (type casting)** — The developer manually converts a value using built-in functions.

## Why is it important?

- JavaScript automatically coerces types in many situations (like comparisons and string concatenation), and not understanding this leads to confusing bugs.
- Form inputs, URL parameters, and API responses are often received as strings and need to be converted to numbers or booleans before use.
- Type conversion mistakes are one of the most common sources of bugs for beginners, especially with the `==` operator.
- It is a favorite topic in interviews because it tests deep understanding of how JavaScript works internally.

## Syntax

```javascript
// Explicit conversion to Number
Number(value);
parseInt(value);
parseFloat(value);

// Explicit conversion to String
String(value);
value.toString();

// Explicit conversion to Boolean
Boolean(value);
```

## Examples

### Example 1: Implicit type conversion (coercion)

```javascript
// String + Number results in string concatenation
console.log("5" + 3);      // string coercion
console.log("5" - 3);      // numeric coercion
console.log("5" * "2");    // numeric coercion
console.log(true + 1);     // boolean to number
console.log("" + null);    // null to string
```

### Output
```
53
2
10
2
null
```

### Example 2: Explicit conversion to Number

```javascript
console.log(Number("42"));       // string to number
console.log(Number("42px"));     // invalid number
console.log(Number(""));         // empty string
console.log(Number(true));       // boolean to number
console.log(parseInt("42px"));   // parses leading digits only
console.log(parseFloat("3.14abc")); // parses leading float
```

### Output
```
42
NaN
0
1
42
3.14
```

### Example 3: Explicit conversion to String and Boolean

```javascript
// Converting to String
console.log(String(100));        // number to string
console.log(String(null));       // null to string
console.log((250).toString());   // using toString method

// Converting to Boolean
console.log(Boolean(0));         // falsy
console.log(Boolean(""));        // falsy
console.log(Boolean("hello"));   // truthy
console.log(Boolean(null));      // falsy
console.log(Boolean(undefined)); // falsy
console.log(Boolean([]));        // truthy (empty array is truthy!)
```

### Output
```
100
null
250
false
false
true
false
false
true
```

## Explanation

**Example 1:**
- `"5" + 3` — when `+` sees a string, it converts the number to a string and joins them, producing `"53"`.
- `"5" - 3`, `"5" * "2"` — the `-` and `*` operators only work with numbers, so JavaScript converts the strings to numbers automatically.
- `true + 1` — `true` is converted to `1`, so the result is `2`.
- `"" + null` — `null` is converted to the string `"null"` and joined with the empty string.

**Example 2:**
- `Number("42")` converts a clean numeric string into a number.
- `Number("42px")` fails because the entire string isn't a valid number, so it returns `NaN` (Not a Number).
- `Number("")` returns `0`, a common source of bugs when checking for empty input.
- `parseInt("42px")` reads characters from the left until it hits a non-numeric character, returning `42`.
- `parseFloat("3.14abc")` works similarly for decimal numbers.

**Example 3:**
- `String()` and `.toString()` both convert values into their string representation.
- `Boolean()` converts any value into `true` or `false` based on JavaScript's truthy/falsy rules. Values like `0`, `""`, `null`, `undefined`, `NaN`, and `false` are falsy; everything else (including empty arrays and objects) is truthy.

## Key Points

| Value | Converted to Number | Converted to Boolean |
|---|---|---|
| `""` (empty string) | `0` | `false` |
| `"0"` | `0` | `true` |
| `null` | `0` | `false` |
| `undefined` | `NaN` | `false` |
| `NaN` | `NaN` | `false` |
| `[]` | `0` | `true` |
| `{}` | `NaN` | `true` |

- `+` performs string concatenation if either operand is a string; otherwise it performs numeric addition.
- `-`, `*`, `/` always attempt numeric conversion, even on strings.
- `parseInt` and `parseFloat` extract numbers from the beginning of a string and ignore trailing invalid characters.
- `Number()` is stricter — it returns `NaN` if the entire string is not a valid number.
- Falsy values in JavaScript: `false`, `0`, `""`, `null`, `undefined`, `NaN`. Everything else is truthy.

