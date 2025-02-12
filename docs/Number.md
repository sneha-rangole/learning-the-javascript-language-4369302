## Notes on JavaScript `Number` Object

### 1. Introduction

- The `Number` type represents floating-point numbers (e.g., `37`, `-9.25`).
- JavaScript does not have a separate integer type; all numbers are stored as floating-point values.
- The `Number` constructor has properties and methods to work with numbers.
- Other data types can be converted into numbers using the `Number()` function.

### 2. Number Representation

Numbers can be written in different ways:

```js
255 === 255.0; // true (same value)
255 === 0xff; // true (hexadecimal format)
255 === 0b11111111; // true (binary format)
255 === 0.255e3; // true (scientific notation)
```

### 3. Converting Other Types to Numbers

- Strings and other data types can be converted using `Number(value)`.
- If conversion fails, it returns `NaN` (Not a Number).

```js
Number("123"); // 123
Number("hello"); // NaN
Number(undefined); // NaN
```

### 4. Number Encoding (IEEE 754 Standard)

Numbers in JavaScript use a 64-bit floating-point format:

- 1 bit for the sign (positive or negative).
- 11 bits for the exponent.
- 52 bits for the mantissa (fractional part).

This allows numbers to be precise up to 15-17 decimal places.

### 5. Limits of Numbers

- `Number.MAX_VALUE`: Largest possible number.
- `Number.MIN_VALUE`: Smallest positive number close to zero.
- `Number.MAX_SAFE_INTEGER`: Largest integer that can be safely used (`2^53 - 1`).
- `Number.MIN_SAFE_INTEGER`: Smallest integer that can be safely used (`-(2^53 - 1)`).
- `Number.POSITIVE_INFINITY` and `Number.NEGATIVE_INFINITY`: Special values for numbers that exceed limits.

```js
console.log(Number.MAX_SAFE_INTEGER); // 9007199254740991
console.log(Number.MIN_SAFE_INTEGER); // -9007199254740991
```

### 6. Number Coercion (Type Conversion)

JavaScript converts values into numbers in different ways:

- `true` → `1`, `false` → `0`
- `null` → `0`
- `undefined` → `NaN`
- Strings → Converted if they contain a valid number, otherwise `NaN`.

```js
Number("123"); // 123
Number(""); // 0
Number(null); // 0
Number("0x11"); // 17 (hexadecimal)
Number("100a"); // NaN (invalid format)
```

### 7. Integer Conversion

Some functions expect integers, so JavaScript removes decimal parts:

- `Math.floor(4.7)` → `4`
- `parseInt("12.34")` → `12`
- `parseFloat("12.34")` → `12.34`

### 8. Static Properties of `Number`

| Property                   | Description                             |
| -------------------------- | --------------------------------------- |
| `Number.EPSILON`           | Smallest difference between two numbers |
| `Number.MAX_SAFE_INTEGER`  | Largest safe integer (`2^53 - 1`)       |
| `Number.MIN_SAFE_INTEGER`  | Smallest safe integer (`-(2^53 - 1)`)   |
| `Number.MAX_VALUE`         | Largest possible number                 |
| `Number.MIN_VALUE`         | Smallest positive number close to zero  |
| `Number.NaN`               | Represents "Not a Number"               |
| `Number.POSITIVE_INFINITY` | Represents infinity                     |
| `Number.NEGATIVE_INFINITY` | Represents negative infinity            |

### 9. Static Methods of `Number`

| Method                    | Purpose                                      |
| ------------------------- | -------------------------------------------- |
| `Number.isFinite(x)`      | Checks if `x` is a finite number             |
| `Number.isInteger(x)`     | Checks if `x` is an integer                  |
| `Number.isNaN(x)`         | Checks if `x` is `NaN`                       |
| `Number.isSafeInteger(x)` | Checks if `x` is within safe integer range   |
| `Number.parseFloat(x)`    | Converts a string to a floating-point number |
| `Number.parseInt(x)`      | Converts a string to an integer              |

### 10. Instance Methods of `Number`

| Method            | Description                                            |
| ----------------- | ------------------------------------------------------ |
| `toExponential()` | Converts number to exponential notation                |
| `toFixed(n)`      | Formats number with `n` decimal places                 |
| `toPrecision(n)`  | Formats number with `n` significant digits             |
| `toString(base)`  | Converts number to a string (supports different bases) |

```js
let num = 123.456;
console.log(num.toFixed(2)); // "123.46"
console.log(num.toExponential(2)); // "1.23e+2"
console.log(num.toString(16)); // "7b" (hexadecimal)
```

### 11. Examples

#### a) Assigning values to Number variables

```js
const maxNum = Number.MAX_VALUE;
const minNum = Number.MIN_VALUE;
const infNum = Number.POSITIVE_INFINITY;
const negInfNum = Number.NEGATIVE_INFINITY;
const nanVal = Number.NaN;
```

#### b) Converting a Date to a Number

```js
const d = new Date("2000-01-01");
console.log(Number(d)); // Timestamp representation
```

#### c) Using `Number()` with different values

```js
console.log(Number("123")); // 123
console.log(Number(null)); // 0
console.log(Number("12.34")); // 12.34
console.log(Number("0b11")); // 3 (binary)
console.log(Number("foo")); // NaN
```

---

## HOTS (Higher Order Thinking Skills) Interview Questions

### Understanding Concepts

1. Why does JavaScript store all numbers as floating-point values instead of having a separate integer type?
2. Explain why `Number("123") === 123` returns `true`, but `Number("123a")` returns `NaN`.

### Application-Based

3. If you need to store a number larger than `Number.MAX_SAFE_INTEGER`, what alternative can you use?
4. Write a function that takes a number and returns its binary representation as a string.
5. How can you safely check if a number is a valid integer before using it in a loop?

### Analysis & Evaluation

6. Why does `Number(null)` return `0`, but `Number(undefined)` returns `NaN`? What does this tell us about JavaScript's type conversion?
7. If `parseInt("0123")` is executed, will it return `123` or `83`? Explain why.
8. Given an array of mixed data types, how would you filter out only the valid numbers?

### Creative Thinking

9. How would you design a function that converts any given number to words? (e.g., `123` → `"one hundred twenty-three"`)
10. How can JavaScript's `Number` object be improved to handle precision errors better?
