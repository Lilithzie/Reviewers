<a id="top"></a>

# JavaScript Complete Guide & Reviewer

## Table of Contents

### Fundamentals
- [Variables & Data Types](#variables--data-types)
- [Operators](#operators)
- [Control Structures](#control-structures)
- [Functions](#functions)
- [Parameters](#parameters)
- [Truthy & Falsy](#truthy--falsy)
- [Type Coercion & Type Checking](#type-coercion--type-checking)
- [Hoisting](#hoisting)
- [Scope & Closures](#scope--closures)

### Intermediate Concepts
- [Objects & Arrays](#objects--arrays)
- [String Manipulation](#string-manipulation)
- [Methods](#methods)
- [Callback Functions](#callback-functions)
- [IIFE - Immediately Invoked Function Expression](#iife---immediately-invoked-function-expression)
- [Event Loop & Call Stack](#event-loop--call-stack)
- [Regular Expressions](#regular-expressions)
- [Error Handling](#error-handling)
- [Asynchronous JavaScript](#asynchronous-javascript)

### Advanced Concepts
- [Classes & Prototypes](#classes--prototypes)
- [Higher-Order Functions](#higher-order-functions)
- [Destructuring](#destructuring)
- [Template Literals](#template-literals)
- [Promises & Async/Await](#promises--asyncawait)

### DOM & Browser APIs
- [DOM Manipulation](#dom-manipulation)
- [Event Handling](#event-handling)
- [Local Storage & Session Storage](#local-storage--session-storage)
- [Fetch API](#fetch-api)

### Security & Best Practices
- [Password Hashing & Salting](#password-hashing--salting)
- [XSS Prevention](#xss-prevention)
- [CSRF Prevention](#csrf-prevention)
- [CORS & Security Headers](#cors--security-headers)
- [Input Validation & Sanitization](#input-validation--sanitization)
- [SQL Injection Prevention](#sql-injection-prevention)
- [Secure Data Storage](#secure-data-storage)
- [Authentication & JWT](#authentication--jwt)

### Tools & CLI
- [Node.js & npm](#nodejs--npm)
- [Common CLI Commands](#common-cli-commands)

### Quiz
- [All Quiz Questions & Answers](#all-quiz-questions--answers)

---

## Fundamentals [↑ Back to Top](#top)

### Variables & Data Types

#### Explanation
Variables are containers for storing data values. JavaScript has different data types including primitives (string, number, boolean, null, undefined, symbol, bigint) and objects (arrays, objects, functions).

#### Data Types
1. **String**: Text data enclosed in quotes
2. **Number**: Integer or floating-point numbers
3. **Boolean**: True or false
4. **Null**: Intentional absence of value
5. **Undefined**: Variable declared but not assigned
6. **Symbol**: Unique identifier
7. **BigInt**: Whole numbers larger than 2^53 - 1
8. **Object**: Collection of key-value pairs

#### Declaration Methods
```javascript
// var (function-scoped, can be redeclared)
var name = "John";
var name = "Jane"; // Valid

// let (block-scoped, cannot be redeclared)
let age = 25;
let age = 30; // Error: Identifier 'age' has already been declared

// const (block-scoped, cannot be redeclared or reassigned)
const city = "New York";
city = "Los Angeles"; // Error: Assignment to constant variable
```

#### Where It's Used
- Storing user input from forms
- Storing calculated results
- Managing application state
- Processing data from APIs

#### Purpose
To store and manage data throughout your application's execution.

#### Examples
```javascript
// String
const greeting = "Hello, World!";

// Number
const score = 95.5;

// Boolean
const isActive = true;

// Array (Object)
const fruits = ["apple", "banana", "orange"];

// Object (Object)
const person = {
  name: "Alice",
  age: 28,
  city: "Boston"
};

// Checking types
console.log(typeof greeting); // "string"
console.log(typeof score); // "number"
console.log(typeof isActive); // "boolean"
console.log(typeof fruits); // "object"
console.log(Array.isArray(fruits)); // true
```

#### Quiz Questions & Answers

**Q1: What's the difference between `let`, `const`, and `var`?**
A: `var` is function-scoped and can be redeclared; `let` is block-scoped and cannot be redeclared; `const` is block-scoped, cannot be redeclared, and cannot be reassigned (though object properties can be modified).

**Q2: What will be printed?**
```javascript
console.log(typeof undefined);
console.log(typeof null);
```
A: "undefined" and "object" (null is a historical quirk in JavaScript)

**Q3: Can you reassign a value to a const variable?**
A: No, you cannot reassign, but if it's an object, you can modify its properties.

---

### Operators

#### Explanation
Operators are symbols or keywords that perform operations on variables and values. They include arithmetic, comparison, logical, assignment, and more.

#### Types of Operators

**1. Arithmetic Operators**
```javascript
console.log(10 + 5);   // 15 (addition)
console.log(10 - 5);   // 5 (subtraction)
console.log(10 * 5);   // 50 (multiplication)
console.log(10 / 5);   // 2 (division)
console.log(10 % 3);   // 1 (modulo/remainder)
console.log(2 ** 3);   // 8 (exponentiation)
```

**2. Comparison Operators**
```javascript
console.log(5 == "5");    // true (value equality, type coercion)
console.log(5 === "5");   // false (strict equality, no coercion)
console.log(5 != "5");    // false (value inequality)
console.log(5 !== "5");   // true (strict inequality)
console.log(5 > 3);       // true
console.log(5 < 3);       // false
console.log(5 >= 5);      // true
console.log(5 <= 5);      // true
```

**3. Logical Operators**
```javascript
console.log(true && false);   // false (AND)
console.log(true || false);   // true (OR)
console.log(!true);           // false (NOT)
```

**4. Assignment Operators**
```javascript
let x = 10;
x += 5;    // x = 15 (addition assignment)
x -= 3;    // x = 12 (subtraction assignment)
x *= 2;    // x = 24 (multiplication assignment)
x /= 4;    // x = 6 (division assignment)
x %= 5;    // x = 1 (modulo assignment)
```

**5. Ternary Operator**
```javascript
const age = 20;
const status = age >= 18 ? "Adult" : "Minor";
console.log(status); // "Adult"
```

**6. Spread Operator**
```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2); // [1, 2, 3, 4, 5]

const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 };
console.log(obj2); // { a: 1, b: 2, c: 3 }
```

#### Purpose
To perform calculations, comparisons, logical operations, and value assignments.

#### Examples
```javascript
// Calculate discount price
const originalPrice = 100;
const discountRate = 0.2;
const finalPrice = originalPrice - (originalPrice * discountRate);
console.log(finalPrice); // 80

// Check user eligibility
const userAge = 25;
const hasLicense = true;
const canDrive = userAge >= 18 && hasLicense;
console.log(canDrive); // true
```

#### Quiz Questions & Answers

**Q1: What is the difference between `==` and `===`?**
A: `==` compares values with type coercion (5 == "5" is true), while `===` requires strict equality including type (5 === "5" is false).

**Q2: What will be the result?**
```javascript
let a = 5;
console.log(a++);
console.log(a);
```
A: First console.log prints 5, second prints 6 (post-increment returns old value).

**Q3: What does the spread operator do?**
A: It unpacks elements of an array or properties of an object into a new array or object.

---

### Control Structures

#### Explanation
Control structures allow you to execute different code based on certain conditions and to repeat code blocks multiple times.

#### Types of Control Structures

**1. if/else Statements**
```javascript
const score = 85;

if (score >= 90) {
  console.log("Grade A");
} else if (score >= 80) {
  console.log("Grade B");
} else if (score >= 70) {
  console.log("Grade C");
} else {
  console.log("Grade F");
}
// Output: Grade B
```

**2. switch Statements**
```javascript
const day = 3;

switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  case 3:
    console.log("Wednesday");
    break;
  default:
    console.log("Unknown day");
}
// Output: Wednesday
```

**3. for Loop**
```javascript
// Traditional for loop
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}

// for...in loop (iterates over keys)
const person = { name: "John", age: 30 };
for (let key in person) {
  console.log(key); // "name", "age"
}

// for...of loop (iterates over values)
const colors = ["red", "green", "blue"];
for (let color of colors) {
  console.log(color); // "red", "green", "blue"
}
```

**4. while Loop**
```javascript
let count = 0;
while (count < 3) {
  console.log(count); // 0, 1, 2
  count++;
}
```

**5. do...while Loop**
```javascript
let i = 0;
do {
  console.log(i); // 0, 1, 2
  i++;
} while (i < 3);
// Executes at least once even if condition is false
```

#### Purpose
To control the flow of your program based on conditions and to repeat operations.

#### Examples
```javascript
// Check login validation
const username = "admin";
const password = "password123";

if (username === "admin" && password === "password123") {
  console.log("Login successful");
} else {
  console.log("Invalid credentials");
}

// Display menu
const userRole = "admin";
switch (userRole) {
  case "admin":
    console.log("Show admin dashboard");
    break;
  case "user":
    console.log("Show user dashboard");
    break;
  default:
    console.log("Access denied");
}

// Calculate sum of numbers
let sum = 0;
for (let i = 1; i <= 10; i++) {
  sum += i;
}
console.log(sum); // 55
```

#### Quiz Questions & Answers

**Q1: What's the difference between for...in and for...of?**
A: for...in iterates over object keys/indices; for...of iterates over iterable values.

**Q2: What will be printed?**
```javascript
let x = 5;
if (x = 10) {
  console.log("x is", x);
}
```
A: "x is 10" (assignment in condition returns the assigned value)

**Q3: Why use break in switch statements?**
A: To prevent fall-through (executing subsequent cases).

---

### Functions

#### Explanation
Functions are reusable blocks of code that perform specific tasks. They help organize code, reduce repetition, and improve maintainability.

#### Defining Functions

**1. Function Declaration**
```javascript
function greet(name) {
  return "Hello, " + name + "!";
}

console.log(greet("Alice")); // "Hello, Alice!"
```

**2. Function Expression**
```javascript
const add = function(a, b) {
  return a + b;
};

console.log(add(5, 3)); // 8
```

**3. Arrow Function**
```javascript
const multiply = (a, b) => {
  return a * b;
};

// Concise arrow function
const square = (x) => x * x;
const square2 = x => x * x; // Parentheses optional for single parameter

console.log(multiply(4, 5)); // 20
console.log(square(5)); // 25
```

**4. Function with Default Parameters**
```javascript
function welcome(name = "Guest", age = 18) {
  console.log(`Welcome ${name}, age ${age}`);
}

welcome(); // "Welcome Guest, age 18"
welcome("John", 25); // "Welcome John, age 25"
```

**5. Function with Rest Parameters**
```javascript
function sum(...numbers) {
  let total = 0;
  for (let num of numbers) {
    total += num;
  }
  return total;
}

console.log(sum(1, 2, 3, 4, 5)); // 15
```

#### Purpose
To encapsulate logic, promote code reuse, improve readability, and maintain modularity.

#### Examples
```javascript
// Validate email
function isValidEmail(email) {
  return email.includes("@") && email.includes(".");
}

console.log(isValidEmail("user@example.com")); // true
console.log(isValidEmail("invalid.email")); // false

// Calculate age
const calculateAge = (birthYear) => new Date().getFullYear() - birthYear;
console.log(calculateAge(1995)); // 31 (in 2026)

// Process array of items
function doubleNumbers(numbers) {
  return numbers.map(num => num * 2);
}

console.log(doubleNumbers([1, 2, 3])); // [2, 4, 6]
```

#### Quiz Questions & Answers

**Q1: What's the difference between function declaration and function expression?**
A: Function declarations are hoisted (can be called before definition); function expressions are not hoisted and must be defined before use.

**Q2: What will this return?**
```javascript
const test = (a, b) => a + b;
console.log(test(3, 4));
```
A: 7 (arrow functions with single expression don't need curly braces or return keyword)

**Q3: What are rest parameters used for?**
A: To accept an indefinite number of arguments as an array (...args).

---

### Parameters

#### Explanation
Parameters are variables that define what information a function expects to receive. JavaScript supports several parameter types: positional parameters, default parameters, rest parameters, and destructured parameters.

#### Positional Parameters
```javascript
// Basic parameters
function greet(firstName, lastName) {
  return `Hello, ${firstName} ${lastName}`;
}

console.log(greet("John", "Doe")); // "Hello, John Doe"
console.log(greet("Jane")); // "Hello, Jane undefined"

// Parameters are passed by position
const result = greet("Alice", "Smith");
console.log(result); // "Hello, Alice Smith"
```

#### Default Parameters
```javascript
// Set default values
function createUser(name, role = "user", active = true) {
  return { name, role, active };
}

console.log(createUser("Alice")); 
// { name: "Alice", role: "user", active: true }

console.log(createUser("Bob", "admin")); 
// { name: "Bob", role: "admin", active: true }

console.log(createUser("Charlie", "moderator", false)); 
// { name: "Charlie", role: "moderator", active: false }

// Defaults can be expressions
function calculateDiscount(price, discountPercent = price * 0.1) {
  return price - discountPercent;
}

console.log(calculateDiscount(100)); // 90
console.log(calculateDiscount(100, 20)); // 80
```

#### Rest Parameters
```javascript
// Collect remaining arguments into an array
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3)); // 6
console.log(sum(1, 2, 3, 4, 5)); // 15
console.log(sum()); // 0

// Mix regular and rest parameters
function greetUsers(greeting, ...names) {
  return names.map(name => `${greeting}, ${name}`);
}

console.log(greetUsers("Hello", "Alice", "Bob", "Charlie"));
// ["Hello, Alice", "Hello, Bob", "Hello, Charlie"]

// Rest parameter must be last
function combine(first, second, ...rest) {
  console.log(first);  // 1
  console.log(second); // 2
  console.log(rest);   // [3, 4, 5]
}

combine(1, 2, 3, 4, 5);
```

#### Destructured Parameters
```javascript
// Destructure object parameter
function displayUser({ name, email, age = 25 }) {
  console.log(`${name} (${email}) - Age: ${age}`);
}

displayUser({ name: "John", email: "john@example.com" });
// "John (john@example.com) - Age: 25"

displayUser({ name: "Jane", email: "jane@example.com", age: 30 });
// "Jane (jane@example.com) - Age: 30"

// Destructure array parameter
function printCoordinates([x, y, z = 0]) {
  console.log(`X: ${x}, Y: ${y}, Z: ${z}`);
}

printCoordinates([10, 20]); // "X: 10, Y: 20, Z: 0"
printCoordinates([10, 20, 30]); // "X: 10, Y: 20, Z: 30"

// Rename destructured parameters
function processData({ firstName: first, lastName: last }) {
  return `${first} ${last}`;
}

console.log(processData({ firstName: "John", lastName: "Doe" })); 
// "John Doe"
```

#### Named Parameters Pattern
```javascript
// Using object as single parameter for clarity
function configureDatabase({
  host = "localhost",
  port = 5432,
  database = "myapp",
  username = "admin",
  password = "secret",
  ssl = false
}) {
  console.log(`Connecting to ${username}@${host}:${port}/${database}`);
  console.log(`SSL: ${ssl}`);
}

configureDatabase({
  host: "db.example.com",
  database: "production",
  username: "produser",
  password: "securepass",
  ssl: true
});
```

#### Arguments Object
```javascript
// Access all arguments (not recommended, use rest parameters instead)
function printAll() {
  console.log(arguments); // Arguments object
  console.log(arguments[0]); // First argument
  console.log(arguments.length); // Number of arguments
  
  // Convert to array
  const args = Array.from(arguments);
  console.log(args);
}

printAll(1, 2, 3); // [1, 2, 3]

// Note: Arrow functions don't have their own 'arguments' object
const arrowFunc = () => {
  console.log(arguments); // ReferenceError
};
```

#### Purpose
To define what data functions need, provide flexibility with default values, handle variable numbers of arguments, and make code more readable with destructuring.

#### Where It's Used
- Function definitions and calls
- API endpoints and callback functions
- Configuration objects
- Data processing functions
- Library functions and utilities

#### Examples
```javascript
// E-commerce order function
function createOrder(
  customerId,
  items = [],
  discountCode = null,
  ...metadata
) {
  return {
    customerId,
    items,
    discountCode,
    metadata,
    total: items.reduce((sum, item) => sum + item.price, 0)
  };
}

createOrder(123, [{ price: 50 }, { price: 30 }], "SAVE10");

// API call with configuration
async function fetchData({
  url,
  method = "GET",
  headers = {},
  body = null,
  timeout = 5000
}) {
  const response = await fetch(url, { method, headers, body });
  return response.json();
}

// Flexible logging function
function log(level = "info", ...messages) {
  const timestamp = new Date().toISOString();
  console.log(`[${timestamp}] [${level.toUpperCase()}]`, ...messages);
}

log("error", "Something went wrong", "Check logs");
```

#### Quiz Questions & Answers

**Q1: What's the difference between default parameters and rest parameters?**
A: Default parameters provide fallback values for individual parameters; rest parameters collect remaining arguments into an array.

**Q2: How do you make a function accept any number of arguments?**
A: Use rest parameters: `function myFunc(...args) { }`

**Q3: Can rest parameters be in the middle of the parameter list?**
A: No, rest parameters must be the last parameter in the list.

**Q4: What's an advantage of using destructured parameters?**
A: Makes the function signature clearer about what object properties are needed and allows default values.

**Q5: What's the difference between `arguments` object and rest parameters?**
A: `arguments` is array-like but not a true array; rest parameters are actual arrays and work with arrow functions.

---

### Truthy & Falsy

#### Explanation
In JavaScript, values are evaluated as either truthy or falsy when used in boolean contexts. Truthy values are those that evaluate to `true` in a boolean context, while falsy values evaluate to `false`.

#### Falsy Values
```javascript
// There are only 6 falsy values in JavaScript:
console.log(Boolean(false));      // false - the boolean false
console.log(Boolean(0));          // false - number zero
console.log(Boolean(-0));         // false - negative zero
console.log(Boolean(""));         // false - empty string
console.log(Boolean(null));       // false - null
console.log(Boolean(undefined));  // false - undefined
console.log(Boolean(NaN));        // false - Not a Number

// Everything else is truthy
console.log(Boolean(true));       // true
console.log(Boolean(1));          // true
console.log(Boolean(-1));         // true
console.log(Boolean("hello"));    // true
console.log(Boolean(" "));        // true (space is truthy!)
console.log(Boolean([]));         // true (empty array is truthy!)
console.log(Boolean({}));         // true (empty object is truthy!)
```

#### Using Truthy/Falsy in Conditionals
```javascript
// Explicit checking
if (value === false) {
  // Only true if value is exactly false
}

// Implicit truthy/falsy checking
if (value) {
  // Executes if value is truthy
}

if (!value) {
  // Executes if value is falsy
}

// Practical examples
const username = "";
if (username) {
  console.log("Username provided");
} else {
  console.log("Username is empty"); // This runs
}

const count = 0;
if (count) {
  console.log("There are items");
} else {
  console.log("No items"); // This runs
}

const user = null;
if (user) {
  console.log("User logged in");
} else {
  console.log("No user"); // This runs
}
```

#### Using with Logical Operators
```javascript
// && (AND) - returns first falsy or last truthy
const name = "Alice";
const age = 25;
const result = name && age; // "Alice" && 25 = 25
console.log(result); // 25

const empty = "";
const message = empty && "Continue"; // "" && "Continue" = ""
console.log(message); // ""

// || (OR) - returns first truthy or last falsy
const firstName = "";
const nickname = "Alex";
const displayName = firstName || nickname;
console.log(displayName); // "Alex"

const defaultValue = undefined || null || "default";
console.log(defaultValue); // "default"

// Nullish coalescing operator (??) - returns right if left is null/undefined
const value = null ?? "default";
console.log(value); // "default"

const zero = 0 ?? "default";
console.log(zero); // 0 (not treated as nullish)
```

#### Checking for Existence
```javascript
const obj = { name: "John", age: 0 };

// Bad - treats 0 as missing
if (obj.age) {
  console.log("Has age");
} else {
  console.log("No age"); // This runs even though age exists!
}

// Good - explicit check
if (obj.age !== undefined && obj.age !== null) {
  console.log("Has age"); // This runs
}

// Good - using nullish coalescing
const age = obj.age ?? 18;
console.log(age); // 0 (not replaced)

// Good - checking property existence
if ("age" in obj) {
  console.log("Age property exists"); // This runs
}

// Good - using hasOwnProperty
if (obj.hasOwnProperty("age")) {
  console.log("Age property exists"); // This runs
}
```

#### Purpose
To understand how JavaScript evaluates values in boolean contexts, write safer conditional logic, and avoid unexpected type coercion.

#### Examples
```javascript
// Form validation
const validateForm = (username, email) => {
  if (!username) return "Username is required";
  if (!email) return "Email is required";
  return "Form is valid";
};

console.log(validateForm("", "user@example.com")); // "Username is required"

// Providing default values
const getConfig = (config) => {
  const maxRetries = config?.maxRetries || 3;
  const timeout = config?.timeout ?? 5000;
  return { maxRetries, timeout };
};

// Function parameter checks
function processData(data) {
  if (!data) {
    console.log("No data provided");
    return;
  }
  // Process data...
}
```

#### Quiz Questions & Answers

**Q1: What are all the falsy values in JavaScript?**
A: false, 0, -0, "", null, undefined, and NaN.

**Q2: Is an empty array truthy or falsy?**
A: Truthy! `[] == true` but `[] === true` is false. Empty arrays are considered truthy.

**Q3: What's the difference between `||` and `??`?**
A: `||` returns first truthy value; `??` returns right side only if left is null or undefined (not other falsy values).

**Q4: What does `!value` do?**
A: Converts value to boolean and negates it. `!undefined` becomes `true`.

**Q5: How do you safely check if a property exists with a value of 0?**
A: Use `"property" in obj` or `obj.hasOwnProperty("property")` instead of checking truthiness.

---

### Type Coercion & Type Checking

#### Explanation
Type coercion is JavaScript's automatic or implicit conversion of values from one type to another. Type checking is explicitly determining or comparing data types.

#### Implicit Type Coercion

**1. String Coercion**
```javascript
// Adding to string coerces to string
console.log("Value: " + 42);        // "Value: 42"
console.log("Value: " + true);      // "Value: true"
console.log("Value: " + null);      // "Value: null"
console.log("Value: " + undefined); // "Value: undefined"
console.log("Value: " + [1, 2]);    // "Value: 1,2"

// Template literals don't coerce in the same way
const num = 42;
console.log(`Value: ${num}`);       // "Value: 42"
```

**2. Number Coercion**
```javascript
// Math operations coerce to numbers
console.log("5" - 2);              // 3 (5 - 2)
console.log("5" * 2);              // 10 (5 * 2)
console.log("5" / 2);              // 2.5 (5 / 2)
console.log("hello" - 5);          // NaN

// Unary plus converts to number
console.log(+"42");                // 42
console.log(+"hello");             // NaN
console.log(+true);                // 1
console.log(+false);               // 0
console.log(+null);                // 0
console.log(+undefined);           // NaN
```

**3. Boolean Coercion**
```javascript
// Double negation converts to boolean
console.log(!!"hello");            // true
console.log(!!0);                  // false

// In conditional contexts
if ("hello") console.log("truthy"); // Outputs: truthy
if (0) console.log("truthy");       // No output
```

**4. Loose Equality (==) - Type Coercion**
```javascript
// == coerces types
console.log("5" == 5);             // true (string coerced to number)
console.log(true == 1);            // true (boolean coerced to number)
console.log(false == 0);           // true
console.log(null == undefined);    // true (special rule)
console.log("0" == false);         // true (both coerced to 0)

// Unexpected coercions
console.log(" " == 0);             // true (space coerced to 0)
console.log([] == "");             // true (array to string)
console.log([] == 0);              // true
console.log([] == false);          // true
```

#### Explicit Type Checking

**1. typeof Operator**
```javascript
// Check type of value
console.log(typeof 42);            // "number"
console.log(typeof "hello");       // "string"
console.log(typeof true);          // "boolean"
console.log(typeof undefined);     // "undefined"
console.log(typeof Symbol("id"));  // "symbol"
console.log(typeof BigInt(42));    // "bigint"

// Objects return "object"
console.log(typeof {});            // "object"
console.log(typeof []);            // "object"
console.log(typeof null);          // "object" (historical quirk!)
console.log(typeof function() {}); // "function"
```

**2. instanceof Operator**
```javascript
// Check if object is instance of class/constructor
const arr = [1, 2, 3];
console.log(arr instanceof Array);           // true
console.log(arr instanceof Object);          // true

const date = new Date();
console.log(date instanceof Date);           // true
console.log(date instanceof Object);         // true

const num = 42;
console.log(num instanceof Number);          // false (not an object)
console.log(num instanceof Object);          // false

const numObj = new Number(42);
console.log(numObj instanceof Number);       // true
console.log(numObj instanceof Object);       // true
```

**3. Array.isArray()**
```javascript
// Specific check for arrays
console.log(Array.isArray([]));             // true
console.log(Array.isArray([1, 2]));         // true
console.log(Array.isArray("not array"));    // false
console.log(Array.isArray({ length: 0 })); // false
```

**4. Strict Equality (===) - No Coercion**
```javascript
// === does NOT coerce types
console.log("5" === 5);             // false
console.log(true === 1);            // false
console.log(false === 0);           // false
console.log(null === undefined);    // false
console.log(0 === -0);              // true (edge case)
console.log(NaN === NaN);           // false (NaN is never equal to anything)

// Safe comparison with NaN
console.log(Number.isNaN(NaN));     // true
console.log(Object.is(NaN, NaN));   // true
```

#### Purpose
To understand JavaScript's type system, avoid unexpected coercions, and write safer type-aware code.

#### Examples
```javascript
// Safe type checking function
function processValue(value) {
  if (typeof value === "string") {
    return value.toUpperCase();
  }
  if (typeof value === "number") {
    return value * 2;
  }
  if (Array.isArray(value)) {
    return value.length;
  }
  return value;
}

console.log(processValue("hello"));     // "HELLO"
console.log(processValue(5));           // 10
console.log(processValue([1, 2, 3]));   // 3

// Validate input types
function validateUser(user) {
  if (typeof user !== "object" || user === null) {
    throw new Error("User must be an object");
  }
  if (typeof user.name !== "string") {
    throw new Error("Name must be a string");
  }
  if (typeof user.age !== "number") {
    throw new Error("Age must be a number");
  }
}

validateUser({ name: "John", age: 30 }); // Valid
```

#### Quiz Questions & Answers

**Q1: What's the difference between `==` and `===`?**
A: `==` performs type coercion before comparison; `===` requires both value and type to match without coercion.

**Q2: Why does `typeof null` return "object"?**
A: It's a historical quirk/bug in JavaScript that has been kept for backward compatibility.

**Q3: Can you use typeof to check if a variable is an array?**
A: No, `typeof []` returns "object". Use `Array.isArray()` instead.

**Q4: What happens when you add a number and a string?**
A: JavaScript coerces the number to a string and performs string concatenation.

**Q5: Is `NaN` equal to `NaN`?**
A: No, `NaN === NaN` is false. Use `Number.isNaN()` or `Object.is()` to check for NaN.

---

### Hoisting

#### Explanation
Hoisting is JavaScript's behavior of moving declarations to the top of their scope before code execution. Function declarations and variable declarations are hoisted, but in different ways.

#### Function Hoisting
```javascript
// Function declarations are fully hoisted
console.log(greet("Alice"));  // "Hello, Alice" - Works!

function greet(name) {
  return `Hello, ${name}`;
}

// Equivalent to:
// function greet(name) {
//   return `Hello, ${name}`;
// }
// console.log(greet("Alice"));
```

#### Variable Hoisting with var
```javascript
// var declarations are hoisted but initialized as undefined
console.log(x); // undefined (not ReferenceError)
var x = 5;
console.log(x); // 5

// Equivalent to:
// var x;
// console.log(x); // undefined
// x = 5;
// console.log(x); // 5
```

#### Variable Hoisting with let & const
```javascript
// let and const are hoisted but NOT initialized (Temporal Dead Zone)
console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 10;

// Same with const
console.log(z); // ReferenceError: Cannot access 'z' before initialization
const z = 20;

// The variables exist but are not accessible until the declaration is reached
```

#### Function Expression Hoisting
```javascript
// Function expressions are NOT fully hoisted
console.log(add(5, 3)); // TypeError: add is not a function

const add = function(a, b) {
  return a + b;
};

// Variable 'add' is hoisted but assigned as undefined
// The assignment happens where it's written in the code
```

#### Arrow Function Hoisting
```javascript
// Arrow functions are NOT hoisted
console.log(multiply(4, 5)); // TypeError: multiply is not a function

const multiply = (a, b) => a * b;

// Same as function expressions - variable is hoisted, not the function
```

#### Hoisting with Function Scope
```javascript
function example() {
  console.log(name); // undefined (hoisted within function scope)
  
  if (true) {
    var name = "John";
  }
  
  console.log(name); // "John" (var is function-scoped)
}

example();

// var declarations are hoisted to the top of the function, not block
```

#### Hoisting with Block Scope
```javascript
// let and const are block-scoped
{
  console.log(value); // ReferenceError
  let value = 5;
}

// Temporal Dead Zone prevents access to block-scoped variables
for (let i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2
}
console.log(i); // ReferenceError: i is not defined
```

#### Purpose
To understand how JavaScript processes declarations, avoid ReferenceError and unexpected undefined values, and write more predictable code.

#### Examples
```javascript
// Problematic hoisting - var behavior
function processData() {
  if (condition) {
    var x = 5;
  }
  console.log(x); // undefined, not ReferenceError!
}

// Better - use let/const
function processDataBetter() {
  if (condition) {
    let x = 5;
    console.log(x); // Inside block
  }
  // console.log(x); // Would cause ReferenceError
}

// Calling function before declaration (works with function declaration)
console.log(factorial(5)); // 120

function factorial(n) {
  return n <= 1 ? 1 : n * factorial(n - 1);
}

// Be careful with dependencies
console.log(dependentVar); // undefined

dependentVar = "value";

var dependentVar;
```

#### Quiz Questions & Answers

**Q1: What gets hoisted to the top of a function?**
A: With `var`: declaration and initialization to undefined. With `let/const`: declaration but not initialization (Temporal Dead Zone).

**Q2: Can you call a function before it's declared?**
A: Yes, if it's a function declaration. No, if it's a function expression or arrow function.

**Q3: What is the Temporal Dead Zone?**
A: The period between entering a scope and reaching the declaration of a `let` or `const` variable where the variable cannot be accessed.

**Q4: Is var hoisted to global scope?**
A: var is hoisted to its function scope or global scope, not block scope.

**Q5: Why should you avoid using var?**
A: var has confusing hoisting behavior and function scope. `let` and `const` are more predictable with block scope.

---

### Scope & Closures

#### Explanation
Scope determines where variables can be accessed. JavaScript has function scope and block scope. Closures are functions that have access to variables from their outer scope.

#### Types of Scope

**1. Global Scope**
```javascript
const globalVar = "I'm global";

function checkGlobal() {
  console.log(globalVar); // Can access
}

checkGlobal(); // "I'm global"
```

**2. Function Scope**
```javascript
function outer() {
  const functionVar = "I'm in function scope";
  
  console.log(functionVar); // Can access
}

console.log(functionVar); // Error: functionVar is not defined
```

**3. Block Scope**
```javascript
if (true) {
  let blockVar = "I'm block-scoped";
  const blockConst = "Also block-scoped";
  console.log(blockVar); // "I'm block-scoped"
}

console.log(blockVar); // Error: blockVar is not defined
```

**4. Closures**
```javascript
function outer() {
  const message = "Hello from outer";
  
  function inner() {
    console.log(message); // Inner function "closes over" outer variable
  }
  
  return inner;
}

const innerFunc = outer();
innerFunc(); // "Hello from outer"
```

**5. Advanced Closure Example**
```javascript
function createCounter() {
  let count = 0; // Private variable
  
  return {
    increment: function() {
      count++;
      return count;
    },
    decrement: function() {
      count--;
      return count;
    },
    getCount: function() {
      return count;
    }
  };
}

const counter = createCounter();
console.log(counter.increment()); // 1
console.log(counter.increment()); // 2
console.log(counter.decrement()); // 1
console.log(counter.getCount()); // 1
```

#### Where It's Used
- Creating private variables
- Module patterns
- Callback functions
- Event handlers
- Data persistence

#### Purpose
To control variable access, create private variables, and maintain state.

#### Examples
```javascript
// Bank account with private balance
function bankAccount(initialBalance) {
  let balance = initialBalance;
  
  return {
    deposit: (amount) => {
      balance += amount;
      return balance;
    },
    withdraw: (amount) => {
      if (amount <= balance) {
        balance -= amount;
        return balance;
      }
      return "Insufficient funds";
    },
    getBalance: () => balance
  };
}

const myAccount = bankAccount(1000);
console.log(myAccount.deposit(500)); // 1500
console.log(myAccount.withdraw(200)); // 1300
```

#### Quiz Questions & Answers

**Q1: What is a closure?**
A: A closure is a function that has access to variables from its outer scope, even after the outer function has returned.

**Q2: What will be logged?**
```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 100);
}
```
A: 3, 3, 3 (var is function-scoped, so i is shared; use let instead to get 0, 1, 2)

**Q3: How can you create private variables in JavaScript?**
A: Using closures - define variables in an outer function and return inner functions that access them.

---

## Intermediate Concepts [↑ Back to Top](#top)

### Objects & Arrays

#### Explanation
Objects are collections of key-value pairs. Arrays are ordered collections of values. Both are essential for organizing and manipulating data in JavaScript.

#### Objects

**1. Creating Objects**
```javascript
// Object literal
const user = {
  name: "John",
  age: 30,
  email: "john@example.com",
  isActive: true
};

// Using constructor
const person = new Object();
person.name = "Jane";
person.age = 28;
```

**2. Accessing Properties**
```javascript
const car = {
  brand: "Toyota",
  model: "Camry",
  year: 2023
};

// Dot notation
console.log(car.brand); // "Toyota"

// Bracket notation
console.log(car["model"]); // "Camry"

// Using variable as key
const key = "year";
console.log(car[key]); // 2023
```

**3. Modifying Objects**
```javascript
const product = {
  name: "Laptop",
  price: 1000
};

// Add property
product.quantity = 5;

// Update property
product.price = 950;

// Delete property
delete product.quantity;

console.log(product); // { name: "Laptop", price: 950 }
```

**4. Object Methods**
```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
};

console.log(person.fullName()); // "John Doe"

// Object methods
console.log(Object.keys(person)); // ["firstName", "lastName", "fullName"]
console.log(Object.values(person)); // ["John", "Doe", ƒ]
console.log(Object.entries(person)); // [["firstName", "John"], ...]
```

#### Arrays

**1. Creating Arrays**
```javascript
// Array literal
const fruits = ["apple", "banana", "orange"];

// Array constructor
const numbers = new Array(1, 2, 3, 4, 5);

// Array with specific length
const emptyArray = new Array(3); // [empty × 3]
```

**2. Array Methods**
```javascript
const numbers = [1, 2, 3, 4, 5];

// Adding elements
numbers.push(6); // [1, 2, 3, 4, 5, 6]
numbers.unshift(0); // [0, 1, 2, 3, 4, 5, 6]

// Removing elements
numbers.pop(); // [0, 1, 2, 3, 4, 5]
numbers.shift(); // [1, 2, 3, 4, 5]

// Checking existence
console.log(numbers.includes(3)); // true
console.log(numbers.indexOf(2)); // 1
```

**3. Array Iteration Methods**
```javascript
const arr = [1, 2, 3, 4, 5];

// map - transform each element
const doubled = arr.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

// filter - select elements
const evens = arr.filter(num => num % 2 === 0);
console.log(evens); // [2, 4]

// reduce - combine into single value
const sum = arr.reduce((acc, num) => acc + num, 0);
console.log(sum); // 15

// forEach - execute for each element
arr.forEach((num, index) => {
  console.log(index, num);
});

// find - get first matching element
const firstEven = arr.find(num => num % 2 === 0);
console.log(firstEven); // 2

// some - check if any element matches
const hasEven = arr.some(num => num % 2 === 0);
console.log(hasEven); // true

// every - check if all elements match
const allPositive = arr.every(num => num > 0);
console.log(allPositive); // true
```

**4. Array Manipulation**
```javascript
const arr = [1, 2, 3, 4, 5];

// slice - extract portion (doesn't modify original)
console.log(arr.slice(1, 4)); // [2, 3, 4]

// splice - modify array
arr.splice(2, 1, "three");
console.log(arr); // [1, 2, "three", 4, 5]

// join - convert to string
console.log(arr.join("-")); // "1-2-three-4-5"

// reverse - reverse array
arr.reverse();
console.log(arr); // [5, 4, "three", 2, 1]

// sort - sort array
const numbers = [3, 1, 4, 1, 5, 9];
numbers.sort((a, b) => a - b);
console.log(numbers); // [1, 1, 3, 4, 5, 9]
```

#### Purpose
To organize and store related data, making it easier to manage and manipulate complex information.

#### Examples
```javascript
// User management system
const users = [
  { id: 1, name: "Alice", email: "alice@example.com", active: true },
  { id: 2, name: "Bob", email: "bob@example.com", active: false },
  { id: 3, name: "Charlie", email: "charlie@example.com", active: true }
];

// Get all active users
const activeUsers = users.filter(user => user.active);

// Get user names
const names = users.map(user => user.name);

// Find user by id
const user = users.find(u => u.id === 2);
```

#### Quiz Questions & Answers

**Q1: What's the difference between slice and splice?**
A: slice returns a new array without modifying the original; splice modifies the array and returns removed elements.

**Q2: What does reduce do?**
A: It iterates through array elements and accumulates a single value by applying a function to an accumulator.

**Q3: How do you access nested object properties?**
A: Using dot notation (obj.level1.level2) or bracket notation (obj["level1"]["level2"]).

---

### String Manipulation

#### Explanation
Strings are sequences of characters. JavaScript provides many methods to create, analyze, and transform strings.

#### String Creation
```javascript
// String literal
const str1 = "Hello";

// Single quotes
const str2 = 'World';

// Template literal (backticks)
const name = "John";
const greeting = `Hello, ${name}!`;
console.log(greeting); // "Hello, John!"

// Multi-line string
const multiline = `This is
a multi-line
string`;
```

#### String Properties & Methods

**1. Basic Properties & Methods**
```javascript
const text = "JavaScript";

// Length
console.log(text.length); // 10

// Access character by index
console.log(text[0]); // "J"
console.log(text.charAt(4)); // "S"

// Get character code
console.log(text.charCodeAt(0)); // 74

// Check substring
console.log(text.includes("Script")); // true
console.log(text.startsWith("Java")); // true
console.log(text.endsWith("Script")); // true
```

**2. Case Conversion**
```javascript
const text = "Hello World";

console.log(text.toUpperCase()); // "HELLO WORLD"
console.log(text.toLowerCase()); // "hello world"
```

**3. Finding & Extracting**
```javascript
const sentence = "The quick brown fox";

// Find index
console.log(sentence.indexOf("quick")); // 4
console.log(sentence.lastIndexOf("o")); // 17

// Search (returns index or -1)
console.log(sentence.search("brown")); // 10

// Extract substring
console.log(sentence.substring(4, 9)); // "quick"
console.log(sentence.substr(4, 5)); // "quick"
console.log(sentence.slice(4, 9)); // "quick"
```

**4. Replacing Content**
```javascript
const text = "I like apples and apples";

// Replace first occurrence
console.log(text.replace("apples", "oranges")); 
// "I like oranges and apples"

// Replace all occurrences (with regex)
console.log(text.replace(/apples/g, "oranges"));
// "I like oranges and oranges"
```

**5. Splitting & Joining**
```javascript
const csv = "apple,banana,orange";

// Split into array
const fruits = csv.split(",");
console.log(fruits); // ["apple", "banana", "orange"]

// Join array into string
const joined = fruits.join(" - ");
console.log(joined); // "apple - banana - orange"
```

**6. Trimming & Padding**
```javascript
const text = "  Hello  ";

console.log(text.trim()); // "Hello"
console.log(text.trimStart()); // "Hello  "
console.log(text.trimEnd()); // "  Hello"

// Padding
console.log("5".padStart(3, "0")); // "005"
console.log("5".padEnd(3, "0")); // "500"
```

**7. Repeating**
```javascript
console.log("Ha".repeat(3)); // "HaHaHa"
```

#### Purpose
To manipulate text data, validate input, format output, and process strings.

#### Examples
```javascript
// Email validation
function validateEmail(email) {
  return email.includes("@") && email.includes(".");
}

// Format currency
function formatCurrency(amount) {
  return "$" + amount.toFixed(2);
}
console.log(formatCurrency(19.5)); // "$19.50"

// Extract username from email
const email = "john.doe@example.com";
const username = email.split("@")[0];
console.log(username); // "john.doe"

// Create slug from title
function createSlug(title) {
  return title.toLowerCase().replace(/\s+/g, "-");
}
console.log(createSlug("Hello World Title")); // "hello-world-title"
```

#### Quiz Questions & Answers

**Q1: What's the difference between substring and slice?**
A: substring doesn't accept negative indices; slice does and counts from the end with negative numbers.

**Q2: How do you replace all occurrences of a string?**
A: Use replace with a global regex pattern: str.replace(/pattern/g, "replacement")

**Q3: What do template literals allow?**
A: String interpolation using ${expression} and multi-line strings.

---

### Methods

#### Explanation
Methods are functions that belong to objects. They are actions that objects can perform. JavaScript has built-in methods for different data types (strings, arrays, objects) and you can create custom methods.

#### Object Methods

**1. Creating Methods**
```javascript
// Method in object literal
const person = {
  name: "John",
  age: 30,
  greet: function() {
    return `Hello, I'm ${this.name}`;
  }
};

console.log(person.greet()); // "Hello, I'm John"

// Shorthand syntax (ES6)
const car = {
  brand: "Toyota",
  start() {
    return `${this.brand} is starting...`;
  }
};

console.log(car.start()); // "Toyota is starting..."
```

**2. The `this` Keyword**
```javascript
const calculator = {
  value: 0,
  add(n) {
    this.value += n;
    return this;
  },
  subtract(n) {
    this.value -= n;
    return this;
  },
  getResult() {
    return this.value;
  }
};

calculator.add(5).subtract(2).add(3);
console.log(calculator.getResult()); // 6
```

**3. Built-in Object Methods**
```javascript
const person = {
  name: "Alice",
  age: 25,
  email: "alice@example.com"
};

// Object.keys() - get all keys
console.log(Object.keys(person)); 
// ["name", "age", "email"]

// Object.values() - get all values
console.log(Object.values(person)); 
// ["Alice", 25, "alice@example.com"]

// Object.entries() - get key-value pairs
console.log(Object.entries(person)); 
// [["name", "Alice"], ["age", 25], ["email", "alice@example.com"]]

// Object.assign() - copy/merge objects
const defaults = { theme: "light", notifications: true };
const userSettings = { theme: "dark" };
const merged = Object.assign({}, defaults, userSettings);
console.log(merged); 
// { theme: "dark", notifications: true }

// Object.freeze() - make object immutable
const config = { apiUrl: "https://api.example.com" };
Object.freeze(config);
config.apiUrl = "https://new.example.com"; // No effect
console.log(config.apiUrl); // "https://api.example.com"

// Object.hasOwnProperty() - check if property exists
console.log(person.hasOwnProperty("name")); // true
console.log(person.hasOwnProperty("age")); // true
console.log(person.hasOwnProperty("greet")); // false
```

#### Array Methods

**1. Transformation Methods**
```javascript
const numbers = [1, 2, 3, 4, 5];

// map() - transform each element
const doubled = numbers.map(n => n * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

// filter() - keep matching elements
const evens = numbers.filter(n => n % 2 === 0);
console.log(evens); // [2, 4]

// reduce() - combine into single value
const sum = numbers.reduce((acc, n) => acc + n, 0);
console.log(sum); // 15

// flatMap() - map then flatten
const words = ["hello world", "javascript"];
const chars = words.flatMap(word => word.split(""));
console.log(chars); // ["h", "e", "l", "l", "o", ...]
```

**2. Search Methods**
```javascript
const users = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" },
  { id: 3, name: "Charlie" }
];

// find() - get first match
const user = users.find(u => u.id === 2);
console.log(user); // { id: 2, name: "Bob" }

// findIndex() - get index of first match
const index = users.findIndex(u => u.id === 2);
console.log(index); // 1

// includes() - check if element exists
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.includes(3)); // true

// indexOf() - get index of element
console.log(numbers.indexOf(3)); // 2

// some() - check if any match
console.log(numbers.some(n => n > 4)); // true

// every() - check if all match
console.log(numbers.every(n => n > 0)); // true
```

**3. Modification Methods**
```javascript
const arr = [1, 2, 3];

// push() - add to end
arr.push(4); // [1, 2, 3, 4]

// pop() - remove from end
const last = arr.pop(); // 4, arr is [1, 2, 3]

// unshift() - add to beginning
arr.unshift(0); // [0, 1, 2, 3]

// shift() - remove from beginning
const first = arr.shift(); // 0, arr is [1, 2, 3]

// splice() - insert/remove at position
arr.splice(1, 1, "two"); // arr is [1, "two", 3]

// reverse() - reverse array
arr.reverse(); // [3, "two", 1]

// sort() - sort array
const numbers = [3, 1, 4, 1, 5];
numbers.sort((a, b) => a - b); // [1, 1, 3, 4, 5]
```

#### String Methods

**1. Case & Whitespace**
```javascript
const text = "  Hello World  ";

// Case conversion
console.log(text.toUpperCase()); // "  HELLO WORLD  "
console.log(text.toLowerCase()); // "  hello world  "

// Trim whitespace
console.log(text.trim()); // "Hello World"
console.log(text.trimStart()); // "Hello World  "
console.log(text.trimEnd()); // "  Hello World"
```

**2. Search Methods**
```javascript
const str = "JavaScript is great";

// Search for substring
console.log(str.includes("Script")); // true
console.log(str.startsWith("Java")); // true
console.log(str.endsWith("great")); // true

// Find position
console.log(str.indexOf("is")); // 11
console.log(str.lastIndexOf("a")); // 17
console.log(str.search("great")); // 15
```

**3. Extract & Replace**
```javascript
const str = "Hello World";

// Extract part of string
console.log(str.substring(0, 5)); // "Hello"
console.log(str.slice(6)); // "World"
console.log(str.substr(0, 5)); // "Hello"

// Replace content
console.log(str.replace("World", "JavaScript")); 
// "Hello JavaScript"

// Character at position
console.log(str.charAt(0)); // "H"
console.log(str.charCodeAt(0)); // 72 (ASCII code)
```

**4. Split & Combine**
```javascript
const csv = "apple,banana,orange";

// Split into array
const fruits = csv.split(",");
console.log(fruits); // ["apple", "banana", "orange"]

// Combine array into string
console.log(fruits.join(" - ")); // "apple - banana - orange"

// Repeat string
console.log("Ha".repeat(3)); // "HaHaHa"

// Padding
console.log("5".padStart(3, "0")); // "005"
console.log("5".padEnd(3, "0")); // "500"
```

#### Purpose
To perform operations on objects, arrays, and strings; encapsulate functionality; and make code more modular and reusable.

#### Where It's Used
- Object manipulation and data transformation
- Array processing and filtering
- String parsing and formatting
- DOM manipulation
- Event handling
- Data validation and processing

#### Examples
```javascript
// User management with methods
const userManager = {
  users: [
    { id: 1, name: "Alice", active: true },
    { id: 2, name: "Bob", active: false }
  ],
  
  addUser(name) {
    const user = { id: this.users.length + 1, name, active: true };
    this.users.push(user);
    return user;
  },
  
  deactivateUser(id) {
    const user = this.users.find(u => u.id === id);
    if (user) user.active = false;
    return user;
  },
  
  getActiveUsers() {
    return this.users.filter(u => u.active);
  },
  
  getUserNames() {
    return this.users.map(u => u.name);
  }
};

userManager.addUser("Charlie");
console.log(userManager.getActiveUsers()); 
// [{ id: 1, name: "Alice", active: true }, { id: 3, name: "Charlie", active: true }]

// Data processing chain
const sales = [100, 250, 75, 150, 300];
const bonus = sales
  .filter(amount => amount > 100)
  .map(amount => amount * 0.1)
  .reduce((total, bonus) => total + bonus, 0);
console.log(bonus); // 85
```

#### Quiz Questions & Answers

**Q1: What's the difference between a method and a function?**
A: A method is a function that belongs to an object and can access the object via `this`; a function is standalone code.

**Q2: What does the `this` keyword refer to in a method?**
A: It refers to the object that the method belongs to.

**Q3: What's the difference between map() and forEach()?**
A: map() returns a new array with transformed elements; forEach() executes code for each element but returns undefined.

**Q4: How do you chain array methods?**
A: Methods that return arrays can be chained: `arr.filter(...).map(...).reduce(...)`

**Q5: Can you use arrow functions as object methods?**
A: Not recommended because arrow functions don't have their own `this` - they inherit from the outer scope.

---

### Callback Functions

#### Explanation
A callback is a function passed as an argument to another function, which is then invoked inside that function. Callbacks are fundamental to JavaScript's asynchronous programming model.

#### Synchronous Callbacks
```javascript
// Simple callback
function greet(name, callback) {
  const message = `Hello, ${name}`;
  callback(message);
}

greet("Alice", (msg) => {
  console.log(msg); // "Hello, Alice"
});

// Array method callbacks
const numbers = [1, 2, 3, 4, 5];
numbers.forEach((num, index) => {
  console.log(`Index ${index}: ${num}`);
});

// Map with callback
const doubled = numbers.map((num) => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]
```

#### Asynchronous Callbacks
```javascript
// Callback for async operation
function fetchUserData(userId, callback) {
  setTimeout(() => {
    const user = { id: userId, name: "John" };
    callback(user);
  }, 1000);
}

fetchUserData(1, (user) => {
  console.log("User data:", user);
});

// Event listener callback
button.addEventListener("click", (event) => {
  console.log("Button clicked");
});

// File operation callback (Node.js)
// fs.readFile("file.txt", (err, data) => {
//   if (err) console.log("Error:", err);
//   else console.log("Data:", data);
// });
```

#### Callback Hell (Pyramid of Doom)
```javascript
// Multiple nested callbacks - hard to read
getUser(userId, (user) => {
  getOrders(user.id, (orders) => {
    getOrderDetails(orders[0].id, (details) => {
      processPayment(details, (result) => {
        sendConfirmation(result, (confirmation) => {
          console.log("Done:", confirmation);
        });
      });
    });
  });
});

// Modern solution: use Promises or async/await
// (See Promises & Async/Await section)
```

#### Purpose
To execute code after an operation has been completed, handle async operations, and allow functions to accept custom behavior.

#### Examples
```javascript
// Custom array filter with callback
function customFilter(array, callback) {
  const result = [];
  for (let item of array) {
    if (callback(item)) {
      result.push(item);
    }
  }
  return result;
}

const numbers = [1, 2, 3, 4, 5];
const evens = customFilter(numbers, (n) => n % 2 === 0);
console.log(evens); // [2, 4]

// Promise-based callback
function delay(ms, callback) {
  setTimeout(callback, ms);
}

delay(2000, () => {
  console.log("2 seconds passed");
});

// Error-first callback (Node.js convention)
function readData(filename, callback) {
  try {
    const data = "file content";
    callback(null, data); // null error, data result
  } catch (error) {
    callback(error); // error first
  }
}

readData("file.txt", (err, data) => {
  if (err) {
    console.log("Error:", err);
  } else {
    console.log("Data:", data);
  }
});
```

#### Quiz Questions & Answers

**Q1: What is a callback function?**
A: A function passed as an argument to another function, which is executed after an operation has been completed.

**Q2: What's the difference between synchronous and asynchronous callbacks?**
A: Synchronous callbacks execute immediately; asynchronous callbacks execute after some operation completes (API call, timer, etc.).

**Q3: What is callback hell?**
A: Deeply nested callbacks that make code hard to read and maintain. Use Promises or async/await to avoid it.

**Q4: What's the error-first callback convention?**
A: In Node.js, the first parameter is usually an error object (null if no error), followed by the result.

**Q5: Can you return from a callback to the calling function?**
A: No, callbacks create their own execution context. Use Promises or async/await if you need to return values.

---

### IIFE - Immediately Invoked Function Expression

#### Explanation
An IIFE (Immediately Invoked Function Expression) is a function that is defined and executed immediately. It's commonly used to create a new scope and avoid polluting the global namespace.

#### Basic IIFE Syntax
```javascript
// Function expression wrapped in parentheses, then invoked with ()
(function() {
  console.log("This runs immediately");
})();

// With parameters
(function(name) {
  console.log(`Hello, ${name}`);
})("Alice");

// Arrow function IIFE
(() => {
  console.log("Arrow function IIFE");
})();

// With return value
const result = (function() {
  return "Result";
})();
console.log(result); // "Result"
```

#### Creating Private Scope
```javascript
// Without IIFE - pollutes global scope
var counter = 0;
var increment = () => { counter++; };
var getCounter = () => counter;

// With IIFE - creates private scope
const counterModule = (() => {
  let counter = 0; // Private variable
  
  return {
    increment: () => { counter++; },
    decrement: () => { counter--; },
    getCounter: () => counter
  };
})();

counterModule.increment();
counterModule.increment();
console.log(counterModule.getCounter()); // 2
// Can't access counter directly - it's private!
```

#### Module Pattern
```javascript
const calculator = (() => {
  // Private variables and functions
  let total = 0;
  
  const updateTotal = (value) => {
    total = value;
  };
  
  // Public methods
  return {
    add: (num) => {
      total += num;
      return total;
    },
    subtract: (num) => {
      total -= num;
      return total;
    },
    multiply: (num) => {
      total *= num;
      return total;
    },
    getTotal: () => total,
    reset: () => {
      total = 0;
      return total;
    }
  };
})();

console.log(calculator.add(10));      // 10
console.log(calculator.multiply(2));  // 20
console.log(calculator.subtract(5));  // 15
console.log(calculator.getTotal());   // 15
```

#### Avoiding Variable Conflicts
```javascript
// Without IIFE - variables can conflict
var name = "Global";
function someLibrary() {
  var name = "Library"; // Overwrites global
}

// With IIFE - prevents conflicts
(function() {
  var name = "Private";
  console.log(name); // "Private"
})();
console.log(window.name); // "Global" - unchanged
```

#### Purpose
To create private scopes, avoid global namespace pollution, create modules, and execute initialization code immediately.

#### Examples
```javascript
// Self-executing function with parameters
(function(document, window) {
  // Safe private scope
  const setup = () => {
    console.log("Setting up...");
  };
  setup();
})(document, window);

// Creating a plugin
const myPlugin = (() => {
  let initialized = false;
  
  return {
    init: () => {
      if (!initialized) {
        console.log("Plugin initialized");
        initialized = true;
      }
    },
    getData: () => ({ initialized })
  };
})();

myPlugin.init(); // "Plugin initialized"
myPlugin.init(); // No output (already initialized)

// Namespace management
const App = (() => {
  const state = { count: 0 };
  
  return {
    increment: () => { state.count++; },
    getCount: () => state.count
  };
})();
```

#### Quiz Questions & Answers

**Q1: What does IIFE stand for?**
A: Immediately Invoked Function Expression.

**Q2: How do you create an IIFE?**
A: Wrap a function expression in parentheses and add `()` at the end: `(function() { })();`

**Q3: Why use IIFE instead of regular function declarations?**
A: IIFE executes immediately, creates a private scope, and doesn't pollute the global namespace.

**Q4: Can IIFE access outer scope variables?**
A: Yes, IIFE has access to outer scope but creates its own scope that's not accessible from outside.

**Q5: Is IIFE still useful with modern module systems?**
A: Less common now with ES6 modules, but still used for legacy code and creating plugins.

---

### Event Loop & Call Stack

#### Explanation
The Event Loop is the mechanism that JavaScript uses to handle asynchronous operations. The Call Stack keeps track of function calls, and the Event Loop manages callbacks when the stack is empty.

#### Call Stack
```javascript
// Function calls are added to call stack
function first() {
  console.log("First");
  second();
}

function second() {
  console.log("Second");
  third();
}

function third() {
  console.log("Third");
}

first();
// Execution order:
// 1. first() added to stack
// 2. "First" logged
// 3. second() added to stack
// 4. "Second" logged
// 5. third() added to stack
// 6. "Third" logged
// 7. Stack empties

// Output: First, Second, Third
```

#### Synchronous vs Asynchronous
```javascript
// Synchronous - blocks until complete
console.log("Start");
function slowTask() {
  // Imagine long operation here
  for (let i = 0; i < 1000000000; i++) {}
  console.log("Task complete");
}
slowTask();
console.log("End");
// Output: Start, Task complete, End

// Asynchronous - doesn't block
console.log("Start");
setTimeout(() => {
  console.log("Async task");
}, 0); // Even with 0ms delay
console.log("End");
// Output: Start, End, Async task
```

#### Event Loop Phases
```javascript
// 1. Synchronous code executes first (Call Stack)
console.log("1. Sync");

// 2. Microtasks (Promises, MutationObserver)
Promise.resolve().then(() => {
  console.log("2. Microtask (Promise)");
});

// 3. setTimeout/setInterval (Macrotask/Task Queue)
setTimeout(() => {
  console.log("3. Macrotask (setTimeout)");
}, 0);

console.log("4. Sync");

// Output:
// 1. Sync
// 4. Sync
// 2. Microtask (Promise)
// 3. Macrotask (setTimeout)
```

#### Event Loop Visualization
```javascript
// Understanding the queue order:

console.log("Start"); // Call Stack

setTimeout(() => {
  console.log("setTimeout 1");
}, 0); // Macrotask Queue

Promise.resolve().then(() => {
  console.log("Promise 1");
}); // Microtask Queue

setTimeout(() => {
  console.log("setTimeout 2");
}, 0); // Macrotask Queue

Promise.resolve().then(() => {
  console.log("Promise 2");
}); // Microtask Queue

console.log("End"); // Call Stack

// Execution order:
// Start (Call Stack)
// End (Call Stack)
// Promise 1 (Microtask - executes before next macrotask)
// Promise 2 (Microtask)
// setTimeout 1 (Macrotask)
// setTimeout 2 (Macrotask)
```

#### Blocking the Event Loop
```javascript
// BAD - blocks the entire application
function blockingLoop() {
  for (let i = 0; i < 10000000000; i++) {
    // Long running operation
  }
  console.log("Done");
}

// During this time, no other code can execute
blockingLoop();

// GOOD - allows other tasks to run
function nonBlockingTask() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("Task done");
      resolve();
    }, 1000);
  });
}

nonBlockingTask().then(() => {
  console.log("Can run other code now");
});
```

#### Purpose
To understand how JavaScript handles concurrent operations, manage asynchronous code effectively, and prevent performance issues.

#### Examples
```javascript
// Understanding execution order
function demonstrateEventLoop() {
  console.log("Step 1");
  
  setTimeout(() => {
    console.log("Step 2 (setTimeout)");
  }, 0);
  
  Promise.resolve()
    .then(() => {
      console.log("Step 3 (Promise)");
    })
    .then(() => {
      console.log("Step 4 (Promise)");
    });
  
  console.log("Step 5");
}

demonstrateEventLoop();
// Output:
// Step 1
// Step 5
// Step 3 (Promise)
// Step 4 (Promise)
// Step 2 (setTimeout)

// Practical: Ensure UI updates
function updateUI() {
  // Synchronous UI updates
  document.body.style.background = "red";
  
  // Defer heavy computation
  setTimeout(() => {
    // Heavy computation that won't block UI
    const result = complexCalculation();
    console.log(result);
  }, 0);
}
```

#### Quiz Questions & Answers

**Q1: What's the difference between the Call Stack and Event Loop?**
A: Call Stack tracks function calls being executed; Event Loop manages callbacks when the stack is empty.

**Q2: Why does `setTimeout(..., 0)` not execute immediately?**
A: It's added to the macrotask queue and only executes when the call stack is empty.

**Q3: What's the difference between microtasks and macrotasks?**
A: Microtasks (Promises, MutationObserver) execute before the next macrotask (setTimeout, setInterval).

**Q4: How do you prevent blocking the Event Loop?**
A: Use asynchronous operations (Promises, async/await, callbacks) instead of blocking synchronous code.

**Q5: Can you have multiple setTimeout callbacks in the queue?**
A: Yes, they go into the macrotask queue and execute one at a time when the stack is empty.

---

### Regular Expressions

#### Explanation
Regular expressions (regex) are patterns used to match character combinations in strings. They're powerful for validation, searching, and replacing text.

#### Creating Regular Expressions
```javascript
// Literal notation
const regex1 = /pattern/flags;

// Constructor
const regex2 = new RegExp("pattern", "flags");

// Simple pattern
const pattern = /hello/;
console.log(pattern.test("hello world")); // true
```

#### Flags
```javascript
// g - global (find all matches)
const text = "cat cat cat";
console.log(text.match(/cat/g)); // ["cat", "cat", "cat"]

// i - case insensitive
console.log(/HELLO/i.test("hello")); // true

// m - multiline (^ and $ match line boundaries)
const multiline = "line1\nline2";
console.log(/^line2/m.test(multiline)); // true

// s - dotall (. matches newlines)
console.log(/a.b/s.test("a\nb")); // true
```

#### Character Classes
```javascript
// [abc] - any of a, b, or c
console.log(/[aeiou]/.test("hello")); // true

// [^abc] - not a, b, or c
console.log(/[^0-9]/.test("abc123")); // true

// [0-9] - any digit
console.log(/[0-9]/.test("hello123")); // true

// \d - digit (same as [0-9])
// \D - non-digit
// \w - word character [a-zA-Z0-9_]
// \W - non-word character
// \s - whitespace
// \S - non-whitespace
```

#### Quantifiers
```javascript
// * - 0 or more
console.log(/ab*c/.test("ac")); // true
console.log(/ab*c/.test("abc")); // true
console.log(/ab*c/.test("abbc")); // true

// + - 1 or more
console.log(/ab+c/.test("ac")); // false
console.log(/ab+c/.test("abc")); // true

// ? - 0 or 1
console.log(/ab?c/.test("ac")); // true
console.log(/ab?c/.test("abc")); // true
console.log(/ab?c/.test("abbc")); // false

// {n} - exactly n
console.log(/a{3}/.test("aaa")); // true

// {n,} - n or more
// {n,m} - between n and m
```

#### Anchors
```javascript
// ^ - start of string
console.log(/^hello/.test("hello world")); // true
console.log(/^hello/.test("say hello")); // false

// $ - end of string
console.log(/world$/.test("hello world")); // true
console.log(/world$/.test("world hello")); // false

// \b - word boundary
console.log(/\bcat\b/.test("the cat sat")); // true
console.log(/\bcat\b/.test("concatenate")); // false
```

#### Common Patterns
```javascript
// Email validation
const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
console.log(emailPattern.test("user@example.com")); // true

// Phone number (US)
const phonePattern = /^\d{3}-\d{3}-\d{4}$/;
console.log(phonePattern.test("123-456-7890")); // true

// URL validation
const urlPattern = /^https?:\/\/.+/;
console.log(urlPattern.test("https://example.com")); // true

// Alphanumeric only
const alphanumericPattern = /^[a-zA-Z0-9]+$/;
console.log(alphanumericPattern.test("abc123")); // true
console.log(alphanumericPattern.test("abc_123")); // false
```

#### Methods
```javascript
const pattern = /(\w+)@(\w+)/;
const email = "john@example.com";

// test - check if pattern matches
console.log(pattern.test(email)); // true

// exec - get match details
const match = pattern.exec(email);
console.log(match[0]); // "john@example"
console.log(match[1]); // "john"
console.log(match[2]); // "example"

// String methods
console.log(email.match(/\w+/g)); // ["john", "example", "com"]
console.log(email.replace(/@/, " [at] ")); // "john [at] example.com"
console.log(email.search(/@/)); // 4
console.log(email.split("@")); // ["john", "example.com"]
```

#### Purpose
To validate input format, search and extract patterns, and replace text efficiently.

#### Examples
```javascript
// Password strength validator
function isStrongPassword(password) {
  const pattern = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/;
  return pattern.test(password);
}
console.log(isStrongPassword("Weak")); // false
console.log(isStrongPassword("Strong@123")); // true

// Extract numbers from string
function extractNumbers(str) {
  return str.match(/\d+/g);
}
console.log(extractNumbers("Phone: 123-456-7890")); // ["123", "456", "7890"]

// Format phone number
function formatPhone(phone) {
  const cleaned = phone.replace(/\D/g, "");
  return cleaned.replace(/(\d{3})(\d{3})(\d{4})/, "($1) $2-$3");
}
console.log(formatPhone("1234567890")); // "(123) 456-7890"
```

#### Quiz Questions & Answers

**Q1: What's the difference between match and exec?**
A: match returns all matches as an array (with g flag) or first match with groups; exec returns detailed match object including groups and index.

**Q2: Write a regex to validate a ZIP code (5 digits)?**
A: `/^\d{5}$/`

**Q3: What does the ? in lookahead/lookbehind do?**
A: `(?=...)` is positive lookahead; `(?!...)` is negative lookahead; they assert a position without consuming characters.

---

### Error Handling

#### Explanation
Error handling allows you to gracefully manage errors that occur during program execution, preventing crashes and providing meaningful feedback.

#### Types of Errors
```javascript
// Syntax Error (caught during parsing)
// const x = ; // SyntaxError

// Reference Error (variable not defined)
// console.log(undefinedVar); // ReferenceError

// Type Error (wrong type operation)
// const num = 5;
// num.toUpperCase(); // TypeError

// Range Error (invalid array length)
// new Array(-1); // RangeError
```

#### Try-Catch-Finally
```javascript
function divide(a, b) {
  try {
    if (b === 0) {
      throw new Error("Division by zero not allowed");
    }
    return a / b;
  } catch (error) {
    console.log("Error caught:", error.message);
    return null;
  } finally {
    console.log("Execution completed");
  }
}

console.log(divide(10, 2)); // 5, "Execution completed"
console.log(divide(10, 0)); // "Error caught: Division by zero not allowed", null, "Execution completed"
```

#### Custom Errors
```javascript
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
}

function validateAge(age) {
  if (age < 0 || age > 150) {
    throw new ValidationError("Age must be between 0 and 150");
  }
  return age;
}

try {
  validateAge(200);
} catch (error) {
  if (error instanceof ValidationError) {
    console.log("Validation failed:", error.message);
  }
}
```

#### Error Objects
```javascript
const error = new Error("Something went wrong");
console.log(error.name); // "Error"
console.log(error.message); // "Something went wrong"
console.log(error.stack); // Stack trace
```

#### Throwing Errors
```javascript
function authenticate(username, password) {
  if (!username) {
    throw new Error("Username is required");
  }
  if (!password) {
    throw new Error("Password is required");
  }
  return true;
}

try {
  authenticate("", "password");
} catch (error) {
  console.log(error.message); // "Username is required"
}
```

#### Purpose
To handle unexpected situations gracefully, provide debugging information, and ensure program stability.

#### Examples
```javascript
// Safe JSON parsing
function parseJSON(jsonString) {
  try {
    return JSON.parse(jsonString);
  } catch (error) {
    console.log("Invalid JSON:", error.message);
    return null;
  }
}

// File operation with error handling
function readFile(filename) {
  try {
    // Simulated file reading
    if (!filename) {
      throw new Error("Filename required");
    }
    return `Contents of ${filename}`;
  } catch (error) {
    console.log("Read failed:", error.message);
    return null;
  } finally {
    console.log("Cleanup done");
  }
}
```

#### Quiz Questions & Answers

**Q1: What's the difference between throw and catch?**
A: throw is used to generate an error; catch is used to handle/receive the thrown error.

**Q2: Does finally always execute?**
A: Yes, finally executes whether an error occurs or not (except if return/break in try/catch).

**Q3: How do you create custom error types?**
A: Extend the Error class and override the constructor and name property.

---

### Asynchronous JavaScript

#### Explanation
Asynchronous programming allows operations to run without blocking the main thread. JavaScript uses callbacks, promises, and async/await for asynchronous operations.

#### Callbacks
```javascript
// Simple callback
function greet(name, callback) {
  console.log("Greeting", name);
  callback();
}

greet("Alice", () => {
  console.log("Callback executed");
});

// Callback with async simulation
function fetchData(id, callback) {
  setTimeout(() => {
    callback({ id: id, name: "User" });
  }, 1000);
}

fetchData(1, (data) => {
  console.log("Data:", data);
});
```

#### Callback Hell (Pyramid of Doom)
```javascript
// Nested callbacks - hard to read
function getUser(id, callback) {
  setTimeout(() => callback({ id: id }), 100);
}

function getOrders(userId, callback) {
  setTimeout(() => callback([{ order: 1 }]), 100);
}

getUser(1, (user) => {
  getOrders(user.id, (orders) => {
    console.log("User orders:", orders); // Very nested and hard to read
  });
});
```

#### Promises

**1. Creating Promises**
```javascript
const promise = new Promise((resolve, reject) => {
  // Async operation
  const success = true;
  
  if (success) {
    resolve("Operation successful");
  } else {
    reject("Operation failed");
  }
});

promise
  .then(result => console.log(result))
  .catch(error => console.log(error));
```

**2. Promise Chains**
```javascript
function fetchUser(id) {
  return new Promise((resolve) => {
    setTimeout(() => resolve({ id: id, name: "John" }), 500);
  });
}

function fetchOrders(userId) {
  return new Promise((resolve) => {
    setTimeout(() => resolve([{ order: 1 }, { order: 2 }]), 500);
  });
}

fetchUser(1)
  .then(user => {
    console.log("User:", user);
    return fetchOrders(user.id);
  })
  .then(orders => console.log("Orders:", orders))
  .catch(error => console.log("Error:", error));
```

**3. Promise Methods**
```javascript
// Promise.all - waits for all promises
Promise.all([promise1, promise2, promise3])
  .then(results => console.log("All done:", results));

// Promise.race - returns first completed
Promise.race([promise1, promise2])
  .then(result => console.log("First done:", result));

// Promise.allSettled - waits for all, returns status
Promise.allSettled([promise1, promise2])
  .then(results => console.log(results));
```

#### Async/Await

**1. Basic Async/Await**
```javascript
async function fetchData() {
  try {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
    return data;
  } catch (error) {
    console.log("Error:", error);
  }
}

fetchData();
```

**2. Multiple Awaits**
```javascript
async function getOrdersSummary(userId) {
  try {
    const user = await fetchUser(userId); // Wait for user
    const orders = await fetchOrders(user.id); // Wait for orders
    const summary = await summarizeOrders(orders); // Wait for summary
    
    return summary;
  } catch (error) {
    console.log("Error:", error);
  }
}
```

**3. Parallel Execution**
```javascript
// Sequential (slower)
async function sequentialFetch() {
  const user = await fetchUser(1);
  const orders = await fetchOrders(1);
  return { user, orders };
}

// Parallel (faster)
async function parallelFetch() {
  const [user, orders] = await Promise.all([
    fetchUser(1),
    fetchOrders(1)
  ]);
  return { user, orders };
}
```

#### Purpose
To handle long-running operations (API calls, file operations) without blocking the user interface.

#### Examples
```javascript
// Fetch user data from API
async function loadUserProfile(userId) {
  try {
    const response = await fetch(`/api/users/${userId}`);
    if (!response.ok) {
      throw new Error("Failed to load user");
    }
    const user = await response.json();
    console.log("User loaded:", user);
    return user;
  } catch (error) {
    console.log("Error loading user:", error.message);
  }
}

// Retry logic
async function fetchWithRetry(url, maxRetries = 3) {
  for (let i = 0; i < maxRetries; i++) {
    try {
      const response = await fetch(url);
      return await response.json();
    } catch (error) {
      if (i === maxRetries - 1) throw error;
      await new Promise(r => setTimeout(r, 1000)); // Wait before retry
    }
  }
}
```

#### Quiz Questions & Answers

**Q1: What's the difference between callbacks and promises?**
A: Callbacks can lead to "callback hell"; promises provide chaining and cleaner error handling.

**Q2: When should you use Promise.all vs Promise.race?**
A: Use all when you need all results; use race when you need the first completed result.

**Q3: What does async/await do?**
A: It's syntactic sugar for promises, allowing you to write asynchronous code like synchronous code using try/catch.

---

## Advanced Concepts [↑ Back to Top](#top)

### Classes & Prototypes

#### Explanation
Classes are blueprints for creating objects. Prototypes are the mechanism behind JavaScript's inheritance model.

#### ES6 Classes
```javascript
class Animal {
  constructor(name, species) {
    this.name = name;
    this.species = species;
  }
  
  speak() {
    console.log(`${this.name} makes a sound`);
  }
  
  static info() {
    console.log("This is the Animal class");
  }
}

const dog = new Animal("Rex", "Dog");
dog.speak(); // "Rex makes a sound"
Animal.info(); // "This is the Animal class"
```

#### Inheritance
```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }
  
  speak() {
    console.log(`${this.name} makes a sound`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // Call parent constructor
    this.breed = breed;
  }
  
  speak() {
    console.log(`${this.name} barks`);
  }
  
  getInfo() {
    console.log(`${this.name} is a ${this.breed}`);
  }
}

const myDog = new Dog("Buddy", "Golden Retriever");
myDog.speak(); // "Buddy barks"
myDog.getInfo(); // "Buddy is a Golden Retriever"
```

#### Getters & Setters
```javascript
class Rectangle {
  constructor(width, height) {
    this._width = width;
    this._height = height;
  }
  
  get width() {
    return this._width;
  }
  
  set width(value) {
    if (value <= 0) {
      console.log("Width must be positive");
      return;
    }
    this._width = value;
  }
  
  get area() {
    return this._width * this._height;
  }
}

const rect = new Rectangle(10, 5);
console.log(rect.area); // 50
rect.width = 20;
console.log(rect.area); // 100
```

#### Prototypes
```javascript
// Constructor function
function Car(brand, model) {
  this.brand = brand;
  this.model = model;
}

// Add method to prototype
Car.prototype.displayInfo = function() {
  return `${this.brand} ${this.model}`;
};

const myCar = new Car("Toyota", "Camry");
console.log(myCar.displayInfo()); // "Toyota Camry"

// Check prototype
console.log(myCar.hasOwnProperty("brand")); // true
console.log(myCar.hasOwnProperty("displayInfo")); // false
console.log("displayInfo" in myCar); // true
```

#### Purpose
To create reusable object templates, establish inheritance hierarchies, and organize code structure.

#### Examples
```javascript
// Banking system with classes
class BankAccount {
  constructor(accountHolder, initialBalance = 0) {
    this.accountHolder = accountHolder;
    this._balance = initialBalance;
  }
  
  deposit(amount) {
    if (amount > 0) {
      this._balance += amount;
      console.log(`Deposited $${amount}`);
    }
  }
  
  withdraw(amount) {
    if (amount <= this._balance) {
      this._balance -= amount;
      console.log(`Withdrew $${amount}`);
    }
  }
  
  getBalance() {
    return this._balance;
  }
}

class SavingsAccount extends BankAccount {
  constructor(accountHolder, initialBalance, interestRate) {
    super(accountHolder, initialBalance);
    this.interestRate = interestRate;
  }
  
  applyInterest() {
    const interest = this._balance * (this.interestRate / 100);
    this._balance += interest;
    console.log(`Interest applied: $${interest}`);
  }
}

const savings = new SavingsAccount("John", 1000, 2.5);
savings.deposit(500);
savings.applyInterest();
console.log(savings.getBalance()); // 1537.5
```

#### Quiz Questions & Answers

**Q1: What's the difference between a class and a constructor function?**
A: Classes are syntactic sugar for constructor functions (ES6); classes have cleaner syntax and stricter mode behavior.

**Q2: What does super() do?**
A: Calls the parent class constructor and allows you to access parent methods.

**Q3: What's the difference between own properties and prototype properties?**
A: Own properties are directly on the object; prototype properties are inherited through the prototype chain.

---

### Higher-Order Functions

#### Explanation
Higher-order functions are functions that take functions as arguments or return functions. They enable functional programming patterns.

#### Functions as Arguments
```javascript
// Callback
function processArray(arr, callback) {
  const result = [];
  for (let item of arr) {
    result.push(callback(item));
  }
  return result;
}

const numbers = [1, 2, 3, 4];
const doubled = processArray(numbers, (n) => n * 2);
console.log(doubled); // [2, 4, 6, 8]
```

#### Functions Returning Functions
```javascript
function createMultiplier(factor) {
  return function(number) {
    return number * factor;
  };
}

const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(5)); // 10
console.log(triple(5)); // 15
```

#### Currying
```javascript
// Regular function
function add(a, b, c) {
  return a + b + c;
}

// Curried version
function curriedAdd(a) {
  return function(b) {
    return function(c) {
      return a + b + c;
    };
  };
}

console.log(curriedAdd(1)(2)(3)); // 6

// Or more concise with arrow functions
const curriedAdd2 = (a) => (b) => (c) => a + b + c;
console.log(curriedAdd2(1)(2)(3)); // 6
```

#### Composition
```javascript
const compose = (...fns) => (x) => 
  fns.reduceRight((acc, fn) => fn(acc), x);

const addTwo = (x) => x + 2;
const multiplyByThree = (x) => x * 3;
const square = (x) => x * x;

const operation = compose(square, multiplyByThree, addTwo);
console.log(operation(5)); // ((5 + 2) * 3)^2 = 441
```

#### Purpose
To create more flexible and reusable code, implement design patterns, and enable functional programming.

#### Examples
```javascript
// Data transformation pipeline
const pipe = (...fns) => (x) => 
  fns.reduce((acc, fn) => fn(acc), x);

const trim = (str) => str.trim();
const lowercase = (str) => str.toLowerCase();
const removeSpaces = (str) => str.replace(/\s/g, "");

const normalize = pipe(trim, lowercase, removeSpaces);
console.log(normalize("  HELLO WORLD  ")); // "helloworld"

// Memoization (caching)
function memoize(fn) {
  const cache = {};
  
  return function(...args) {
    const key = JSON.stringify(args);
    if (key in cache) {
      console.log("Returning cached result");
      return cache[key];
    }
    
    const result = fn(...args);
    cache[key] = result;
    return result;
  };
}

const fibonacci = memoize(function(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
});

console.log(fibonacci(5)); // 5
console.log(fibonacci(5)); // "Returning cached result", 5
```

#### Quiz Questions & Answers

**Q1: What is a higher-order function?**
A: A function that takes functions as arguments or returns a function.

**Q2: What is currying?**
A: Converting a function that takes multiple arguments into a sequence of functions that each take one argument.

**Q3: What's the purpose of function composition?**
A: To combine simple functions into more complex operations while keeping code readable and reusable.

---

### Destructuring

#### Explanation
Destructuring is a convenient way to extract values from arrays or properties from objects into distinct variables.

#### Array Destructuring
```javascript
// Basic
const [first, second] = [1, 2, 3];
console.log(first, second); // 1, 2

// Skip elements
const [a, , c] = [1, 2, 3];
console.log(a, c); // 1, 3

// Rest operator
const [head, ...tail] = [1, 2, 3, 4, 5];
console.log(head); // 1
console.log(tail); // [2, 3, 4, 5]

// Default values
const [x, y = 10] = [5];
console.log(x, y); // 5, 10

// Nested
const [num, [nested]] = [1, [2]];
console.log(num, nested); // 1, 2
```

#### Object Destructuring
```javascript
// Basic
const { name, age } = { name: "John", age: 30 };
console.log(name, age); // John, 30

// Rename
const { name: personName, age: personAge } = { name: "Jane", age: 25 };
console.log(personName); // Jane

// Default values
const { city = "Unknown" } = { name: "Bob" };
console.log(city); // "Unknown"

// Nested
const person = {
  id: 1,
  profile: {
    name: "Alice",
    email: "alice@example.com"
  }
};

const { profile: { name, email } } = person;
console.log(name, email); // Alice, alice@example.com

// Rest
const { name: n, ...rest } = { name: "Charlie", age: 35, city: "NYC" };
console.log(n); // Charlie
console.log(rest); // { age: 35, city: "NYC" }
```

#### Function Parameters
```javascript
// Array parameters
function sum([a, b]) {
  return a + b;
}
console.log(sum([5, 10])); // 15

// Object parameters
function displayUser({ name, email }) {
  console.log(`${name}: ${email}`);
}
displayUser({ name: "John", email: "john@example.com" }); 
// John: john@example.com

// With defaults
function greet({ greeting = "Hello", name }) {
  console.log(`${greeting}, ${name}`);
}
greet({ name: "Alice" }); // Hello, Alice
greet({ greeting: "Hi", name: "Bob" }); // Hi, Bob
```

#### Purpose
To write cleaner, more concise code when working with complex data structures.

#### Examples
```javascript
// Extract API response data
const apiResponse = {
  status: 200,
  data: {
    id: 1,
    user: {
      name: "John",
      email: "john@example.com"
    }
  }
};

const { data: { user: { name, email } } } = apiResponse;
console.log(name, email);

// Swap variables
let a = 1, b = 2;
[a, b] = [b, a];
console.log(a, b); // 2, 1

// Extract specific properties from array of objects
const users = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" }
];

const names = users.map(({ name }) => name);
console.log(names); // ["Alice", "Bob"]
```

#### Quiz Questions & Answers

**Q1: How do you set a default value in destructuring?**
A: Use the `=` operator: `const { name = "Unknown" } = obj`

**Q2: What does the rest operator do in destructuring?**
A: Captures remaining elements/properties: `const [first, ...rest] = arr`

**Q3: Can you destructure nested structures?**
A: Yes, using nested patterns: `const { user: { name } } = obj`

---

### Template Literals

#### Explanation
Template literals are string literals allowing embedded expressions and multi-line strings, using backticks instead of quotes.

#### Basic Usage
```javascript
// Traditional string concatenation
const name = "John";
const greeting = "Hello, " + name + "!";

// Template literal
const greeting2 = `Hello, ${name}!`;
console.log(greeting2); // Hello, John!

// Expression evaluation
const x = 10;
const y = 20;
console.log(`Sum: ${x + y}`); // Sum: 30
```

#### Multi-line Strings
```javascript
// Traditional
const message = "Line 1\nLine 2\nLine 3";

// Template literal
const message2 = `Line 1
Line 2
Line 3`;

console.log(message2);
```

#### Tagged Templates
```javascript
function highlight(strings, ...values) {
  return strings
    .map((str, i) => str + (values[i] ? `**${values[i]}**` : ""))
    .join("");
}

const user = "Alice";
const action = "logged in";
console.log(highlight`User ${user} has ${action}!`);
// User **Alice** has **logged in**!
```

#### HTML/SQL Formatting
```javascript
// HTML
const title = "My Page";
const html = `
  <html>
    <head>
      <title>${title}</title>
    </head>
    <body>
      <h1>${title}</h1>
    </body>
  </html>
`;

// SQL Query (careful with injection!)
const userId = 123;
const query = `SELECT * FROM users WHERE id = ${userId}`;
```

#### Purpose
To make string manipulation more readable and reduce concatenation complexity.

#### Examples
```javascript
// Format object data
const user = { name: "John", age: 30, city: "NYC" };
const profile = `
  Name: ${user.name}
  Age: ${user.age}
  City: ${user.city}
`;
console.log(profile);

// Build URLs with parameters
const baseUrl = "https://api.example.com";
const endpoint = "users";
const id = 123;
const url = `${baseUrl}/${endpoint}/${id}`;

// Conditional display
const items = 5;
const message = `You have ${items} item${items !== 1 ? "s" : ""} in your cart`;
console.log(message);
```

#### Quiz Questions & Answers

**Q1: What's the difference between template literals and regular strings?**
A: Template literals support embedded expressions `${}` and multi-line strings; regular strings need concatenation.

**Q2: What are tagged templates?**
A: Functions that process template literals, receiving strings and expressions separately for custom formatting.

**Q3: Can you execute code inside template literals?**
A: Yes, any JavaScript expression can go inside `${}`: `${functionCall()}`, `${obj.property}`, etc.

---

### Promises & Async/Await

*(Covered in detail under [Asynchronous JavaScript](#asynchronous-javascript), but here's additional advanced patterns)*

#### Promise Patterns

**1. Creating Resolved/Rejected Promises**
```javascript
// Immediately resolved
Promise.resolve("success")
  .then(result => console.log(result)); // "success"

// Immediately rejected
Promise.reject("error")
  .catch(error => console.log(error)); // "error"
```

**2. Timeout Wrapper**
```javascript
function withTimeout(promise, ms) {
  return Promise.race([
    promise,
    new Promise((_, reject) => 
      setTimeout(() => reject(new Error("Timeout")), ms)
    )
  ]);
}

const slowPromise = new Promise(resolve => 
  setTimeout(() => resolve("Done"), 5000)
);

withTimeout(slowPromise, 1000)
  .catch(error => console.log(error.message)); // "Timeout"
```

**3. Retry Pattern**
```javascript
function retry(fn, maxAttempts = 3, delay = 1000) {
  return new Promise((resolve, reject) => {
    const attempt = (attemptNum) => {
      fn()
        .then(resolve)
        .catch(error => {
          if (attemptNum < maxAttempts) {
            setTimeout(() => attempt(attemptNum + 1), delay);
          } else {
            reject(error);
          }
        });
    };
    attempt(1);
  });
}
```

#### Advanced Async/Await

**1. Error Handling Patterns**
```javascript
// Try-catch with multiple awaits
async function loadData() {
  try {
    const user = await fetchUser();
    const posts = await fetchPosts(user.id);
    const comments = await fetchComments(posts[0].id);
    return { user, posts, comments };
  } catch (error) {
    console.error("Failed to load data:", error);
    return null;
  }
}

// Promise.allSettled for partial failures
async function loadAll() {
  const [userResult, postsResult, commentsResult] = 
    await Promise.allSettled([
      fetchUser(),
      fetchPosts(),
      fetchComments()
    ]);
  
  return {
    user: userResult.status === "fulfilled" ? userResult.value : null,
    posts: postsResult.status === "fulfilled" ? postsResult.value : [],
    comments: commentsResult.status === "fulfilled" ? commentsResult.value : []
  };
}
```

**2. Async Generators**
```javascript
async function* fetchPages(url, pageCount) {
  for (let i = 1; i <= pageCount; i++) {
    const response = await fetch(`${url}?page=${i}`);
    yield await response.json();
  }
}

// Usage
(async () => {
  for await (const page of fetchPages("/api/users", 5)) {
    console.log("Page:", page);
  }
})();
```

#### Quiz Questions & Answers

**Q1: What's the difference between Promise.all and Promise.allSettled?**
A: all rejects if any promise rejects; allSettled waits for all and returns status for each.

**Q2: How do you handle errors in async/await?**
A: Use try/catch blocks or .catch() on the promise chain.

**Q3: Can you use await outside an async function?**
A: Only in top-level modules (modern JS) or within async functions.

---

## DOM & Browser APIs [↑ Back to Top](#top)

### DOM Manipulation

#### Explanation
The Document Object Model (DOM) represents the HTML structure as a tree. You can manipulate it using JavaScript to change page content dynamically.

#### Selecting Elements
```javascript
// By ID
const element = document.getElementById("myId");

// By class
const elements = document.getElementsByClassName("myClass");
const elements2 = document.querySelectorAll(".myClass");

// By tag
const paragraphs = document.getElementsByTagName("p");

// Query selectors
const div = document.querySelector("div.container");
const all = document.querySelectorAll("div.container");

// Relationship
const parent = element.parentElement;
const children = element.children;
const firstChild = element.firstElementChild;
const siblings = element.nextElementSibling;
```

#### Creating Elements
```javascript
// Create element
const div = document.createElement("div");
div.textContent = "Hello";
div.className = "container";
div.id = "main";

// Add to page
document.body.appendChild(div);

// Insert at specific position
const parent = document.querySelector(".parent");
const newElement = document.createElement("p");
parent.insertBefore(newElement, parent.firstChild);

// Multiple ways to add HTML
div.innerHTML = "<p>Hello</p>";
div.textContent = "Hello"; // Safer for user input
div.innerText = "Hello"; // Returns visible text
```

#### Modifying Elements
```javascript
const element = document.getElementById("myElement");

// Text content
element.textContent = "New text";

// HTML
element.innerHTML = "<strong>Bold text</strong>";

// Attributes
element.setAttribute("data-id", "123");
element.getAttribute("data-id"); // "123"
element.removeAttribute("data-id");
element.hasAttribute("data-id"); // false

// Classes
element.classList.add("active");
element.classList.remove("inactive");
element.classList.toggle("highlight");
element.classList.contains("active"); // true

// Styles
element.style.color = "red";
element.style.backgroundColor = "blue";
element.style.display = "none";

// Data attributes
element.dataset.userId = "456";
console.log(element.dataset.userId); // "456"
```

#### Removing Elements
```javascript
const element = document.getElementById("myElement");

// Remove from page
element.remove();

// Alternative
element.parentElement.removeChild(element);
```

#### Purpose
To dynamically update page content, respond to user interactions, and create interactive experiences.

#### Examples
```javascript
// Create a todo list item
function addTodoItem(text) {
  const li = document.createElement("li");
  li.textContent = text;
  li.className = "todo-item";
  
  const deleteBtn = document.createElement("button");
  deleteBtn.textContent = "Delete";
  deleteBtn.onclick = () => li.remove();
  
  li.appendChild(deleteBtn);
  document.getElementById("todoList").appendChild(li);
}

// Toggle visibility
function toggleElement(id) {
  const element = document.getElementById(id);
  if (element.style.display === "none") {
    element.style.display = "block";
  } else {
    element.style.display = "none";
  }
}

// Update user profile
function updateProfile(userData) {
  document.getElementById("username").textContent = userData.name;
  document.getElementById("email").textContent = userData.email;
  document.getElementById("avatar").src = userData.avatarUrl;
}
```

#### Quiz Questions & Answers

**Q1: What's the difference between textContent and innerHTML?**
A: textContent sets plain text; innerHTML sets HTML content (can be unsafe with user input).

**Q2: How do you safely add user input to the page?**
A: Use textContent instead of innerHTML to prevent XSS attacks.

**Q3: What does classList do?**
A: Provides methods to add, remove, toggle, and check classes without replacing existing ones.

---

### Event Handling

#### Explanation
Events are user interactions (clicks, typing, scrolling) or browser events. You can respond to them with event listeners.

#### Adding Event Listeners
```javascript
const button = document.getElementById("myButton");

// Method 1: addEventListener (recommended)
button.addEventListener("click", () => {
  console.log("Button clicked");
});

// Method 2: Inline event handler
button.onclick = () => {
  console.log("Button clicked");
};

// Method 3: HTML attribute
// <button onclick="handleClick()">Click</button>
```

#### Event Types
```javascript
// Mouse events
element.addEventListener("click", (event) => {});
element.addEventListener("dblclick", (event) => {});
element.addEventListener("mouseover", (event) => {});
element.addEventListener("mouseout", (event) => {});
element.addEventListener("mousedown", (event) => {});
element.addEventListener("mouseup", (event) => {});

// Keyboard events
element.addEventListener("keydown", (event) => {
  console.log("Key:", event.key); // The character pressed
});
element.addEventListener("keyup", (event) => {});
element.addEventListener("keypress", (event) => {});

// Form events
form.addEventListener("submit", (event) => {
  event.preventDefault(); // Prevent form submission
});
input.addEventListener("input", (event) => {
  console.log("User typing:", event.target.value);
});
input.addEventListener("change", (event) => {
  console.log("Input changed:", event.target.value);
});

// Document events
document.addEventListener("DOMContentLoaded", () => {
  console.log("Page loaded");
});
window.addEventListener("scroll", () => {
  console.log("User scrolled");
});
window.addEventListener("resize", () => {
  console.log("Window resized");
});
```

#### Event Object
```javascript
document.addEventListener("click", (event) => {
  console.log("Type:", event.type); // "click"
  console.log("Target:", event.target); // Element that triggered event
  console.log("X coordinate:", event.clientX);
  console.log("Y coordinate:", event.clientY);
  console.log("Key code:", event.keyCode); // For keyboard events
  console.log("Shift pressed:", event.shiftKey);
  console.log("Ctrl pressed:", event.ctrlKey);
  console.log("Alt pressed:", event.altKey);
});
```

#### Event Delegation
```javascript
// Instead of adding listener to each item
const list = document.getElementById("list");
list.addEventListener("click", (event) => {
  if (event.target.tagName === "LI") {
    console.log("Clicked item:", event.target.textContent);
  }
});
```

#### Removing Event Listeners
```javascript
const button = document.getElementById("myButton");

// Define handler function
function handleClick() {
  console.log("Clicked");
}

// Add listener
button.addEventListener("click", handleClick);

// Remove listener (must reference same function)
button.removeEventListener("click", handleClick);
```

#### Purpose
To create interactive user interfaces that respond to user actions.

#### Examples
```javascript
// Form validation on submit
const form = document.getElementById("loginForm");
form.addEventListener("submit", (event) => {
  event.preventDefault();
  
  const email = form.email.value;
  const password = form.password.value;
  
  if (email && password) {
    console.log("Form valid, submitting...");
  } else {
    console.log("Please fill all fields");
  }
});

// Real-time search input
const searchInput = document.getElementById("search");
searchInput.addEventListener("input", (event) => {
  const query = event.target.value;
  console.log("Searching for:", query);
  // Perform search...
});

// Dynamic button click
const deleteButtons = document.querySelectorAll(".delete-btn");
deleteButtons.forEach(btn => {
  btn.addEventListener("click", (event) => {
    const id = event.target.dataset.id;
    console.log("Deleting item:", id);
    // Delete item...
  });
});
```

#### Quiz Questions & Answers

**Q1: What's the difference between event.target and event.currentTarget?**
A: target is the element that triggered the event; currentTarget is the element with the listener.

**Q2: What does event.preventDefault() do?**
A: Stops the browser's default action (e.g., form submission, link navigation).

**Q3: What is event delegation?**
A: Adding a single event listener to a parent element instead of individual listeners to each child.

---

### Local Storage & Session Storage

#### Explanation
Web Storage allows you to store data on the client side persistently (LocalStorage) or temporarily (SessionStorage).

#### LocalStorage

**1. Setting Data**
```javascript
// Store string
localStorage.setItem("username", "john_doe");

// Store object (convert to JSON)
const user = { id: 1, name: "John", email: "john@example.com" };
localStorage.setItem("user", JSON.stringify(user));
```

**2. Retrieving Data**
```javascript
// Get string
const username = localStorage.getItem("username");
console.log(username); // "john_doe"

// Get object (parse JSON)
const userJson = localStorage.getItem("user");
const user = JSON.parse(userJson);
console.log(user.name); // "John"

// Get with default value
const theme = localStorage.getItem("theme") || "light";
```

**3. Removing Data**
```javascript
// Remove specific item
localStorage.removeItem("username");

// Remove all
localStorage.clear();

// Check if key exists
if (localStorage.getItem("username")) {
  console.log("Username found");
}
```

**4. Iterating**
```javascript
// Get all keys
for (let i = 0; i < localStorage.length; i++) {
  const key = localStorage.key(i);
  const value = localStorage.getItem(key);
  console.log(key, value);
}

// Using entries (in modern browsers)
Object.entries(localStorage).forEach(([key, value]) => {
  console.log(key, value);
});
```

#### SessionStorage
```javascript
// Same methods as localStorage
sessionStorage.setItem("tempData", "value");
const data = sessionStorage.getItem("tempData");
sessionStorage.removeItem("tempData");
sessionStorage.clear();

// Difference: Data is cleared when tab/browser closes
```

#### Storage Events
```javascript
window.addEventListener("storage", (event) => {
  console.log("Key:", event.key);
  console.log("Old value:", event.oldValue);
  console.log("New value:", event.newValue);
  console.log("Storage type:", event.storageArea === localStorage);
});
```

#### Purpose
To persist user preferences, cache data, maintain session state.

#### Examples
```javascript
// Save user theme preference
function setTheme(theme) {
  document.body.className = theme;
  localStorage.setItem("theme", theme);
}

function loadTheme() {
  const saved = localStorage.getItem("theme") || "light";
  document.body.className = saved;
}

// Save form data
const form = document.getElementById("myForm");
form.addEventListener("input", (e) => {
  localStorage.setItem(e.target.name, e.target.value);
});

// Load saved form data
function restoreForm() {
  const fields = form.querySelectorAll("input");
  fields.forEach(field => {
    const saved = localStorage.getItem(field.name);
    if (saved) field.value = saved;
  });
}

loadTheme();
restoreForm();

// Save shopping cart
function addToCart(item) {
  const cart = JSON.parse(localStorage.getItem("cart") || "[]");
  cart.push(item);
  localStorage.setItem("cart", JSON.stringify(cart));
}

function getCart() {
  return JSON.parse(localStorage.getItem("cart") || "[]");
}
```

#### Quiz Questions & Answers

**Q1: What's the difference between localStorage and sessionStorage?**
A: localStorage persists until manually cleared; sessionStorage is cleared when the browser tab closes.

**Q2: Can you store objects directly in localStorage?**
A: No, you must convert to JSON using JSON.stringify() and parse using JSON.parse().

**Q3: How do you clear all localStorage data?**
A: Use localStorage.clear() to remove all items.

---

### Fetch API

#### Explanation
The Fetch API is used to make HTTP requests to servers and retrieve data asynchronously.

#### Basic GET Request
```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
```

#### Fetch with Async/Await
```javascript
async function fetchPost() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}

fetchPost();
```

#### POST Request
```javascript
const newPost = {
  title: "New Post",
  body: "This is a new post",
  userId: 1
};

fetch("https://jsonplaceholder.typicode.com/posts", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify(newPost)
})
  .then(response => response.json())
  .then(data => console.log("Created:", data))
  .catch(error => console.error("Error:", error));
```

#### PUT Request (Update)
```javascript
const updatedPost = {
  id: 1,
  title: "Updated Title",
  body: "Updated body",
  userId: 1
};

fetch("https://jsonplaceholder.typicode.com/posts/1", {
  method: "PUT",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify(updatedPost)
})
  .then(response => response.json())
  .then(data => console.log("Updated:", data));
```

#### DELETE Request
```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1", {
  method: "DELETE"
})
  .then(response => response.json())
  .then(data => console.log("Deleted:", data));
```

#### Response Handling
```javascript
fetch("https://api.example.com/data")
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
```

#### Response Formats
```javascript
// JSON
response.json()

// Plain text
response.text()

// Blob (binary data)
response.blob()

// ArrayBuffer
response.arrayBuffer()

// FormData
response.formData()
```

#### Headers & Options
```javascript
fetch("https://api.example.com/data", {
  method: "GET",
  headers: {
    "Authorization": "Bearer token123",
    "Content-Type": "application/json"
  },
  credentials: "include", // Include cookies
  mode: "cors", // Enable CORS
  cache: "no-cache"
})
  .then(response => response.json());
```

#### Purpose
To retrieve data from servers, submit form data, update resources, and build dynamic web applications.

#### Examples
```javascript
// Load and display user profile
async function loadUserProfile(userId) {
  try {
    const response = await fetch(`/api/users/${userId}`);
    if (!response.ok) throw new Error("Failed to load user");
    
    const user = await response.json();
    document.getElementById("username").textContent = user.name;
    document.getElementById("email").textContent = user.email;
  } catch (error) {
    console.error("Error:", error);
    document.getElementById("error").textContent = "Failed to load profile";
  }
}

// Submit form data
const form = document.getElementById("contactForm");
form.addEventListener("submit", async (e) => {
  e.preventDefault();
  
  const formData = new FormData(form);
  const data = Object.fromEntries(formData);
  
  try {
    const response = await fetch("/api/contact", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(data)
    });
    
    if (response.ok) {
      console.log("Message sent successfully");
    }
  } catch (error) {
    console.error("Error:", error);
  }
});

// Fetch with retry
async function fetchWithRetry(url, options = {}, retries = 3) {
  for (let i = 0; i < retries; i++) {
    try {
      const response = await fetch(url, options);
      if (response.ok) return response.json();
    } catch (error) {
      if (i === retries - 1) throw error;
      await new Promise(r => setTimeout(r, 1000));
    }
  }
}
```

#### Quiz Questions & Answers

**Q1: How do you check if a fetch request was successful?**
A: Check `response.ok` or `response.status` (200-299 is successful).

**Q2: What methods are available for different HTTP operations?**
A: GET (retrieve), POST (create), PUT (update), DELETE (remove), PATCH (partial update).

**Q3: How do you send JSON data with fetch?**
A: Set `body: JSON.stringify(data)` and header `"Content-Type": "application/json"`.

---

## Security & Best Practices [↑ Back to Top](#top)

### Password Hashing & Salting

#### Explanation
Hashing is a one-way process that converts passwords into fixed-length strings. Salting adds random data to the hash to prevent rainbow table attacks. Never store plain text passwords.

#### Understanding Hashing & Salting
```javascript
// NEVER do this - storing plain text
// users.password = "myPassword123"; // INSECURE!

// Hashing with bcrypt (Node.js backend)
const bcrypt = require('bcrypt');

// Creating a hash with salt
async function hashPassword(password) {
  const saltRounds = 10; // Cost factor (higher = slower, more secure)
  const hash = await bcrypt.hash(password, saltRounds);
  return hash;
}

// Example hash output
// Password: "myPassword123"
// Hash: "$2b$10$N9qo8uLOickgx2ZMRZoMyeIjZAgcg7b3XeKeUxWdeS86E36P4/uGm"
// Each time you hash, you get a different result (due to random salt)

// Verifying a password
async function verifyPassword(password, hash) {
  const isValid = await bcrypt.compare(password, hash);
  return isValid; // true or false
}

// Example usage
async function registerUser(username, password) {
  const hashedPassword = await hashPassword(password);
  // Store username and hashedPassword in database
  return {
    username,
    password: hashedPassword // SAFE - hashed
  };
}

async function loginUser(username, providedPassword) {
  // Get user from database
  const user = await getFromDatabase(username);
  
  // Compare provided password with stored hash
  const isValid = await verifyPassword(providedPassword, user.password);
  
  if (isValid) {
    console.log("Login successful");
    return true;
  } else {
    console.log("Invalid password");
    return false;
  }
}
```

#### Crypto Module (Node.js) - Encryption
```javascript
const crypto = require('crypto');

// Generate random salt
function generateSalt() {
  return crypto.randomBytes(16).toString('hex');
}

// Hash password with salt (PBKDF2)
function hashPasswordPBKDF2(password, salt) {
  return crypto.pbkdf2Sync(password, salt, 100000, 64, 'sha512').toString('hex');
}

// Example
const salt = generateSalt();
const hash = hashPasswordPBKDF2("myPassword", salt);
console.log(`Salt: ${salt}`);
console.log(`Hash: ${hash}`);

// To verify, hash the provided password with the stored salt
const providedPassword = "myPassword";
const storedHash = hash; // From database
const rehash = hashPasswordPBKDF2(providedPassword, salt);
console.log(rehash === storedHash); // true if password matches
```

#### Purpose
To securely store user passwords, prevent unauthorized access, and protect user data.

#### Examples
```javascript
// Complete user authentication system
async function createUser(email, password) {
  // Validate input
  if (!email || !password || password.length < 8) {
    throw new Error("Invalid email or password");
  }
  
  // Check if user already exists
  const existingUser = await User.findOne({ email });
  if (existingUser) {
    throw new Error("User already exists");
  }
  
  // Hash password
  const hashedPassword = await bcrypt.hash(password, 10);
  
  // Save user
  const user = new User({
    email,
    password: hashedPassword
  });
  await user.save();
  
  return { id: user._id, email: user.email };
}

async function authenticateUser(email, password) {
  const user = await User.findOne({ email });
  
  if (!user) {
    throw new Error("User not found");
  }
  
  const isPasswordValid = await bcrypt.compare(password, user.password);
  
  if (!isPasswordValid) {
    throw new Error("Invalid password");
  }
  
  // Generate JWT token (see JWT section)
  const token = generateJWT(user._id);
  
  return { token, user: { id: user._id, email: user.email } };
}
```

#### Quiz Questions & Answers

**Q1: Why shouldn't you store plain text passwords?**
A: If the database is breached, attackers have direct access to all passwords.

**Q2: What's the purpose of salting?**
A: Adds random data to prevent rainbow table attacks where hackers use precomputed hashes.

**Q3: Why is bcrypt better than simple hashing?**
A: bcrypt includes salting automatically and has a configurable cost factor to slow down brute force attacks.

**Q4: How do you verify a password without storing the original?**
A: Hash the provided password and compare it with the stored hash.

**Q5: Should salt values be stored in the database?**
A: For bcrypt, the salt is embedded in the hash. For PBKDF2, yes, store salt (it's not secret).

---

### XSS Prevention

#### Explanation
Cross-Site Scripting (XSS) is an attack where malicious scripts are injected into web pages. There are three types: Stored, Reflected, and DOM-based.

#### Understanding XSS Attacks
```javascript
// VULNERABLE - Don't do this!
function displayUserInput(userInput) {
  // If userInput = "<script>alert('Hacked!')</script>"
  document.getElementById("output").innerHTML = userInput;
  // The script will execute!
}

// Attack vector
displayUserInput("<img src=x onerror='stealCookies()'>");
// This will execute stealCookies() function!
```

#### Prevention Method 1: Use textContent Instead of innerHTML
```javascript
// SAFE - Use textContent for plain text
function displayUserInput(userInput) {
  document.getElementById("output").textContent = userInput;
  // Scripts won't execute, HTML tags displayed as text
}

displayUserInput("<script>alert('test')</script>");
// Output: <script>alert('test')</script> (as plain text, not executed)
```

#### Prevention Method 2: Sanitize HTML
```javascript
// Use a library like DOMPurify
// npm install dompurify

import DOMPurify from 'dompurify';

function displayUserContent(userHTML) {
  const clean = DOMPurify.sanitize(userHTML);
  document.getElementById("output").innerHTML = clean;
}

// Unsafe input
const userInput = '<p>Hello</p><script>alert("xss")</script>';
const safe = DOMPurify.sanitize(userInput);
console.log(safe); // '<p>Hello</p>' (script removed)

// Allow certain tags
const allowedHTML = DOMPurify.sanitize(userInput, {
  ALLOWED_TAGS: ['p', 'a', 'strong', 'em'],
  ALLOWED_ATTR: ['href']
});
```

#### Prevention Method 3: Template Literals (Safer)
```javascript
// Safer approach - avoid dynamic HTML
function displayMessage(name) {
  // Use template literals instead of HTML
  const message = `Hello ${name}!`;
  document.getElementById("output").textContent = message;
}

// Event handler with direct assignment
button.onclick = function() {
  const message = `You clicked at ${new Date()}`;
  console.log(message);
};
```

#### Prevention Method 4: Content Security Policy (CSP)
```html
<!-- Add to HTML head -->
<meta http-equiv="Content-Security-Policy" 
      content="default-src 'self'; 
               script-src 'self' https://trusted-cdn.com;
               style-src 'self' 'unsafe-inline';
               img-src 'self' data: https:;
               frame-ancestors 'none';">
```

#### Prevention Method 5: Encode Special Characters
```javascript
function escapeHTML(text) {
  const div = document.createElement('div');
  div.textContent = text;
  return div.innerHTML;
}

// Or use a library
function encodeHTML(str) {
  return str
    .replace(/&/g, '&amp;')
    .replace(/</g, '&lt;')
    .replace(/>/g, '&gt;')
    .replace(/"/g, '&quot;')
    .replace(/'/g, '&#39;');
}

const userInput = '<script>alert("xss")</script>';
console.log(escapeHTML(userInput));
// Output: &lt;script&gt;alert(&quot;xss&quot;)&lt;/script&gt;
```

#### Purpose
To prevent malicious scripts from executing on your site and protect user data.

#### Examples
```javascript
// Safe comment display
function addComment(userComment) {
  const commentDiv = document.createElement('div');
  commentDiv.className = 'comment';
  
  // Use textContent instead of innerHTML
  const textNode = document.createTextNode(userComment);
  commentDiv.appendChild(textNode);
  
  document.getElementById('comments').appendChild(commentDiv);
}

// Safe form submission
form.addEventListener('submit', (e) => {
  e.preventDefault();
  
  const userInput = form.input.value;
  
  // Sanitize before sending to server
  const sanitized = DOMPurify.sanitize(userInput);
  
  // Send sanitized data
  fetch('/api/comment', {
    method: 'POST',
    body: JSON.stringify({ comment: sanitized })
  });
});
```

#### Quiz Questions & Answers

**Q1: What's the difference between innerHTML and textContent?**
A: innerHTML parses HTML and can execute scripts; textContent treats everything as plain text (safer).

**Q2: How does DOMPurify help prevent XSS?**
A: It removes dangerous HTML tags and attributes while preserving safe formatting.

**Q3: What is Content Security Policy (CSP)?**
A: A security header that restricts where scripts can be loaded from and what they can do.

**Q4: Should you trust user input?**
A: Never. Always sanitize and validate user input on both client and server.

**Q5: Can XSS attacks happen through form submissions?**
A: Yes, if user input is displayed without sanitization.

---

### CSRF Prevention

#### Explanation
Cross-Site Request Forgery (CSRF) is an attack where a malicious site tricks users into performing unwanted actions on another site they're logged into.

#### Understanding CSRF
```javascript
// User is logged into bank.com
// User visits evil.com
// evil.com has this hidden form:
// <form action="bank.com/transfer" method="POST">
//   <input name="amount" value="1000">
//   <input name="to" value="attacker">
// </form>
// <script>document.forms[0].submit();</script>
// Without CSRF protection, the transfer happens!
```

#### Prevention Method 1: CSRF Tokens
```javascript
// Server generates unique token
// Send token with form
// Verify token on server

// Frontend - Get CSRF token from server
async function loadForm() {
  const response = await fetch('/api/csrf-token');
  const { token } = await response.json();
  
  // Add token to form
  document.getElementById('csrfToken').value = token;
}

// Frontend - Submit form with token
const form = document.getElementById('myForm');
form.addEventListener('submit', async (e) => {
  e.preventDefault();
  
  const token = document.getElementById('csrfToken').value;
  const formData = new FormData(form);
  
  const response = await fetch('/api/action', {
    method: 'POST',
    headers: {
      'X-CSRF-Token': token,
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(Object.fromEntries(formData))
  });
});

// Backend (Node.js) - Verify token
app.post('/api/action', (req, res) => {
  const token = req.headers['x-csrf-token'];
  
  if (!validateCSRFToken(token, req.session)) {
    return res.status(403).json({ error: 'CSRF token invalid' });
  }
  
  // Process the request
  res.json({ success: true });
});
```

#### Prevention Method 2: SameSite Cookie Attribute
```javascript
// Set this on the server side when setting cookies
// res.cookie('sessionId', sessionId, {
//   sameSite: 'Strict', // or 'Lax'
//   httpOnly: true,
//   secure: true
// });

// SameSite values:
// 'Strict' - Cookie not sent in cross-site requests
// 'Lax' - Cookie sent for top-level navigation
// 'None' - Cookie sent in all requests (requires Secure)
```

#### Prevention Method 3: Double-Submit Cookies
```javascript
// Server sets two cookies with same value
// Client must send the value in a request header
// If they don't match, request is rejected

// Frontend
const csrfToken = getCookie('csrf-token'); // From cookie
fetch('/api/data', {
  method: 'POST',
  headers: {
    'X-CSRF-Token': csrfToken // In header
  }
});

// Backend - both must match
app.post('/api/data', (req, res) => {
  const cookieToken = req.cookies['csrf-token'];
  const headerToken = req.headers['x-csrf-token'];
  
  if (cookieToken !== headerToken) {
    return res.status(403).json({ error: 'CSRF protection failed' });
  }
  
  // Process request
});
```

#### Purpose
To prevent unauthorized actions from being performed on behalf of authenticated users.

#### Examples
```javascript
// Safe form submission with CSRF protection
async function submitTransferForm(fromAccount, toAccount, amount) {
  // Get CSRF token
  const tokenResponse = await fetch('/api/csrf-token');
  const { token } = await tokenResponse.json();
  
  // Submit with token
  const response = await fetch('/api/transfer', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-CSRF-Token': token
    },
    body: JSON.stringify({
      from: fromAccount,
      to: toAccount,
      amount: amount
    })
  });
  
  if (response.ok) {
    console.log('Transfer successful');
  }
}
```

#### Quiz Questions & Answers

**Q1: How does CSRF attack work?**
A: Attacker tricks an authenticated user into visiting a malicious site that performs unwanted actions.

**Q2: What's a CSRF token?**
A: A unique, unpredictable token generated by the server and verified on state-changing requests.

**Q3: Why is SameSite cookie important?**
A: It prevents cookies from being sent in cross-site requests, blocking CSRF attacks.

**Q4: Should CSRF tokens be stored in cookies?**
A: The token can be generated and stored server-side; client receives it and must send it back.

**Q5: Does CSRF protection only apply to POST requests?**
A: No, any state-changing request (POST, PUT, DELETE) should be protected.

---

### CORS & Security Headers

#### Explanation
CORS (Cross-Origin Resource Sharing) controls which sites can access your APIs. Security headers protect against various attacks.

#### Understanding CORS
```javascript
// Frontend on www.example.com
fetch('https://api.example.com/data')
  .then(r => r.json())
  .catch(e => console.log(e));
// If api.example.com doesn't allow cross-origin requests,
// browser blocks it with CORS error

// Backend response needs CORS headers:
// Access-Control-Allow-Origin: https://www.example.com
// Access-Control-Allow-Methods: GET, POST, OPTIONS
// Access-Control-Allow-Headers: Content-Type
```

#### Setting CORS on Server (Node.js)
```javascript
const express = require('express');
const cors = require('cors');
const app = express();

// Allow specific origin
app.use(cors({
  origin: 'https://www.example.com',
  credentials: true, // Allow cookies
  methods: ['GET', 'POST', 'PUT', 'DELETE'],
  allowedHeaders: ['Content-Type', 'Authorization']
}));

// Or allow all origins (less secure)
app.use(cors());

// Manual CORS headers
app.use((req, res, next) => {
  res.header('Access-Control-Allow-Origin', 'https://www.example.com');
  res.header('Access-Control-Allow-Methods', 'GET, POST, OPTIONS');
  res.header('Access-Control-Allow-Headers', 'Content-Type, Authorization');
  next();
});
```

#### Important Security Headers
```javascript
// Set these headers on server responses

// 1. X-Content-Type-Options: Prevent MIME type sniffing
app.use((req, res, next) => {
  res.header('X-Content-Type-Options', 'nosniff');
  
  // 2. X-Frame-Options: Prevent clickjacking
  res.header('X-Frame-Options', 'DENY');
  
  // 3. X-XSS-Protection: Enable browser XSS filter
  res.header('X-XSS-Protection', '1; mode=block');
  
  // 4. Strict-Transport-Security: Force HTTPS
  res.header('Strict-Transport-Security', 'max-age=31536000; includeSubDomains');
  
  // 5. Content-Security-Policy: Control resource loading
  res.header('Content-Security-Policy', "default-src 'self'; script-src 'self' https://trusted.com");
  
  // 6. Referrer-Policy: Control referrer information
  res.header('Referrer-Policy', 'strict-origin-when-cross-origin');
  
  next();
});
```

#### Helmet.js (Automatic Security Headers)
```javascript
const helmet = require('helmet');
const express = require('express');
const app = express();

// Apply multiple security headers at once
app.use(helmet());

// Configure specific headers
app.use(helmet.contentSecurityPolicy({
  directives: {
    defaultSrc: ["'self'"],
    scriptSrc: ["'self'", "trusted-cdn.com"],
    styleSrc: ["'self'", "'unsafe-inline'"]
  }
}));
```

#### Purpose
To allow safe cross-origin requests while preventing unauthorized access and attacks.

#### Examples
```javascript
// Frontend - Making safe cross-origin requests
async function fetchUserData() {
  const response = await fetch('https://api.example.com/user', {
    method: 'GET',
    headers: {
      'Authorization': `Bearer ${token}`,
      'Content-Type': 'application/json'
    },
    credentials: 'include' // Include cookies if needed
  });
  
  if (!response.ok) {
    throw new Error(`HTTP error! status: ${response.status}`);
  }
  
  return response.json();
}

// Backend - Secure CORS setup
const corsOptions = {
  origin: process.env.ALLOWED_ORIGINS?.split(',') || ['http://localhost:3000'],
  credentials: true,
  optionsSuccessStatus: 200
};

app.use(cors(corsOptions));
```

#### Quiz Questions & Answers

**Q1: What does CORS prevent?**
A: It prevents websites from making unauthorized requests to APIs on other domains.

**Q2: What's the difference between simple and preflight CORS requests?**
A: Simple requests are sent directly; preflight requests first ask permission via OPTIONS method.

**Q3: Should you allow CORS for all origins?**
A: No, specify allowed origins in production for security.

**Q4: What's the purpose of Strict-Transport-Security header?**
A: Forces browsers to always use HTTPS, preventing man-in-the-middle attacks.

**Q5: Does CORS prevent backend access to other APIs?**
A: No, CORS is a browser security feature. Backend can access any API.

---

### Input Validation & Sanitization

#### Explanation
Validation checks that input meets requirements. Sanitization removes/escapes dangerous characters to prevent injection attacks.

#### Client-Side Validation
```javascript
// Check format and type
function validateEmail(email) {
  const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return regex.test(email);
}

function validatePassword(password) {
  // At least 8 characters, 1 uppercase, 1 lowercase, 1 number
  const regex = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$/;
  return regex.test(password);
}

function validatePhoneNumber(phone) {
  const regex = /^\d{10}$/; // 10 digits
  return regex.test(phone.replace(/\D/g, ''));
}

// Form validation
function validateForm(email, password, phone) {
  const errors = [];
  
  if (!validateEmail(email)) {
    errors.push('Invalid email format');
  }
  
  if (!validatePassword(password)) {
    errors.push('Password must be 8+ chars with uppercase, lowercase, and numbers');
  }
  
  if (!validatePhoneNumber(phone)) {
    errors.push('Phone must be 10 digits');
  }
  
  return { valid: errors.length === 0, errors };
}

// Usage
const validation = validateForm('user@example.com', 'MyPass123', '5551234567');
console.log(validation);
// { valid: true, errors: [] }
```

#### Server-Side Validation (REQUIRED)
```javascript
// NEVER trust client-side validation alone!
app.post('/api/register', (req, res) => {
  const { email, password, name } = req.body;
  
  // Validate on server
  if (!email || !email.includes('@')) {
    return res.status(400).json({ error: 'Invalid email' });
  }
  
  if (!password || password.length < 8) {
    return res.status(400).json({ error: 'Password too short' });
  }
  
  if (!name || name.trim().length === 0) {
    return res.status(400).json({ error: 'Name required' });
  }
  
  // Process valid input
  createUser(email, password, name);
});
```

#### Sanitization Examples
```javascript
// Remove dangerous HTML tags
function sanitizeText(text) {
  return text
    .replace(/&/g, '&amp;')
    .replace(/</g, '&lt;')
    .replace(/>/g, '&gt;')
    .replace(/"/g, '&quot;')
    .replace(/'/g, '&#39;');
}

// Trim whitespace
function sanitizeInput(input) {
  return input.trim();
}

// Remove special characters
function sanitizeFilename(filename) {
  return filename.replace(/[^a-zA-Z0-9._-]/g, '');
}

// Validate and sanitize URL
function validateURL(urlString) {
  try {
    const url = new URL(urlString);
    // Only allow http and https
    if (!['http:', 'https:'].includes(url.protocol)) {
      return false;
    }
    return true;
  } catch {
    return false;
  }
}
```

#### Purpose
To ensure data meets requirements and prevent injection attacks.

#### Examples
```javascript
// Complete form validation and submission
async function submitRegistrationForm(formData) {
  // 1. Client-side validation
  const validation = validateForm(
    formData.email,
    formData.password,
    formData.phone
  );
  
  if (!validation.valid) {
    showErrors(validation.errors);
    return;
  }
  
  // 2. Sanitize input
  const sanitized = {
    email: formData.email.toLowerCase().trim(),
    password: formData.password,
    name: formData.name.trim(),
    phone: formData.phone.replace(/\D/g, '')
  };
  
  // 3. Send to server
  try {
    const response = await fetch('/api/register', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(sanitized)
    });
    
    if (!response.ok) {
      const { error } = await response.json();
      showError(error);
    } else {
      console.log('Registration successful');
    }
  } catch (error) {
    showError('Network error');
  }
}
```

#### Quiz Questions & Answers

**Q1: Is client-side validation enough?**
A: No, server-side validation is required. Client validation can be bypassed.

**Q2: What's the difference between validation and sanitization?**
A: Validation checks if data is correct; sanitization cleans it up.

**Q3: Should you validate on both client and server?**
A: Yes, client validation improves UX, server validation ensures security.

**Q4: How do you safely accept user file uploads?**
A: Validate file type, size, scan for viruses, and save with restricted names.

**Q5: What characters are dangerous in input?**
A: `<`, `>`, `"`, `'`, `&`, `/`, `;`, `--`, etc. (depends on context).

---

### SQL Injection Prevention

#### Explanation
SQL Injection is an attack where malicious SQL code is inserted into queries. Always use parameterized queries.

#### Understanding SQL Injection
```javascript
// VULNERABLE - Never do this!
const userId = req.body.id; // User input
const query = `SELECT * FROM users WHERE id = ${userId}`;
// If userId = "1; DROP TABLE users; --"
// Query becomes: SELECT * FROM users WHERE id = 1; DROP TABLE users; --
// This deletes the entire users table!

// SAFE - Use parameterized queries
const query = 'SELECT * FROM users WHERE id = ?';
db.query(query, [userId]); // UserId is treated as data, not code
```

#### Safe Query Examples
```javascript
const mysql = require('mysql2/promise');

// Using placeholders
async function getUserById(userId) {
  const query = 'SELECT * FROM users WHERE id = ?';
  const [rows] = await pool.query(query, [userId]);
  return rows[0];
}

// Multiple parameters
async function updateUser(id, email, name) {
  const query = 'UPDATE users SET email = ?, name = ? WHERE id = ?';
  await pool.query(query, [email, name, id]);
}

// Using named placeholders
async function findUserByEmail(email) {
  const query = 'SELECT * FROM users WHERE email = :email';
  const results = await pool.query(query, { email });
  return results[0];
}

// Escaping (less reliable than parameterized)
const mysql = require('mysql');
const escapeId = mysql.escapeId('users');
const escapedValue = mysql.escape('O\'Reilly'); // Handles quotes
```

#### Using ORM (Safest)
```javascript
// Using Sequelize ORM
const User = require('./models/User');

// Safe queries - ORM handles parameterization
async function findUser(id) {
  return await User.findByPk(id);
}

async function findByEmail(email) {
  return await User.findOne({ where: { email } });
}

// Using Mongoose for MongoDB
const User = require('./models/User');

async function getUser(userId) {
  return await User.findById(userId);
}

async function updateUser(id, data) {
  return await User.findByIdAndUpdate(id, data, { new: true });
}
```

#### Purpose
To prevent attackers from executing arbitrary SQL commands.

#### Examples
```javascript
// Complete user authentication safely
async function authenticateUser(email, password) {
  // Use parameterized query
  const query = 'SELECT id, password_hash FROM users WHERE email = ?';
  const [rows] = await pool.query(query, [email]);
  
  if (rows.length === 0) {
    throw new Error('User not found');
  }
  
  const user = rows[0];
  const isValid = await bcrypt.compare(password, user.password_hash);
  
  if (!isValid) {
    throw new Error('Invalid password');
  }
  
  return user;
}

// Safe search with LIKE
async function searchUsers(searchTerm) {
  const query = 'SELECT id, name, email FROM users WHERE name LIKE ?';
  const [rows] = await pool.query(query, [`%${searchTerm}%`]);
  return rows;
}
```

#### Quiz Questions & Answers

**Q1: What is SQL Injection?**
A: An attack where malicious SQL code is injected into queries through user input.

**Q2: How do you prevent SQL Injection?**
A: Use parameterized queries/prepared statements that separate code from data.

**Q3: Is escaping enough to prevent SQL Injection?**
A: Parameterized queries are more reliable than escaping.

**Q4: What's an ORM?**
A: Object-Relational Mapping library that handles database queries safely (Sequelize, Mongoose).

**Q5: Should you build SQL queries with string concatenation?**
A: Never, always use parameters or an ORM.

---

### Secure Data Storage

#### Explanation
How and where you store sensitive data determines security. Never store secrets in code or browsers.

#### Secure Backend Storage
```javascript
// Store sensitive data in environment variables
// Create .env file (never commit to git)
DB_PASSWORD=secure_password_here
API_SECRET=secret_key_here
JWT_SECRET=jwt_secret_key_here

// Load with dotenv
require('dotenv').config();

const dbPassword = process.env.DB_PASSWORD;
const apiSecret = process.env.API_SECRET;
const jwtSecret = process.env.JWT_SECRET;

// Never log secrets
console.log(apiSecret); // BAD
console.log('Connected to database'); // GOOD
```

#### Secure Frontend Storage
```javascript
// NEVER store sensitive data in localStorage
localStorage.setItem('token', sensitiveToken); // BAD
localStorage.setItem('password', password); // VERY BAD

// BETTER - Use httpOnly cookies (server-side controlled)
// Server sends cookie automatically with each request
// JavaScript can't access it

// If you must store in frontend:
// 1. Use sessionStorage (cleared when tab closes)
sessionStorage.setItem('tempToken', token);

// 2. Store in memory (cleared on page refresh)
let token = null;
function setToken(t) { token = t; }
function getToken() { return token; }

// 3. Use encrypted storage
const crypto = require('crypto');

function encrypt(text, key) {
  const cipher = crypto.createCipher('aes192', key);
  let encrypted = cipher.update(text, 'utf8', 'hex');
  encrypted += cipher.final('hex');
  return encrypted;
}

function decrypt(encrypted, key) {
  const decipher = crypto.createDecipher('aes192', key);
  let decrypted = decipher.update(encrypted, 'hex', 'utf8');
  decrypted += decipher.final('utf8');
  return decrypted;
}
```

#### Encryption at Rest
```javascript
const crypto = require('crypto');

// Encrypt sensitive data in database
function encryptData(plaintext, encryptionKey) {
  const iv = crypto.randomBytes(16);
  const cipher = crypto.createCipheriv('aes-256-cbc', encryptionKey, iv);
  
  let encrypted = cipher.update(plaintext, 'utf8', 'hex');
  encrypted += cipher.final('hex');
  
  // Store both IV and encrypted data (IV doesn't need to be secret)
  return iv.toString('hex') + ':' + encrypted;
}

function decryptData(encryptedData, encryptionKey) {
  const [iv, encrypted] = encryptedData.split(':');
  const decipher = crypto.createDecipheriv(
    'aes-256-cbc',
    encryptionKey,
    Buffer.from(iv, 'hex')
  );
  
  let decrypted = decipher.update(encrypted, 'hex', 'utf8');
  decrypted += decipher.final('utf8');
  return decrypted;
}

// Usage
const key = crypto.scryptSync('password', 'salt', 32); // Key generation
const encrypted = encryptData('sensitive-info', key);
const decrypted = decryptData(encrypted, key);
```

#### Purpose
To protect secrets and sensitive data from unauthorized access.

#### Examples
```javascript
// Secure user data flow
async function registerUser(email, password, ssn) {
  // 1. Hash password with salt
  const hashedPassword = await bcrypt.hash(password, 10);
  
  // 2. Encrypt SSN
  const encryptionKey = Buffer.from(process.env.ENCRYPTION_KEY, 'hex');
  const encryptedSSN = encryptData(ssn, encryptionKey);
  
  // 3. Store in database
  const user = await User.create({
    email,
    password: hashedPassword,
    ssn: encryptedSSN
  });
  
  // 4. Return safe token (never return password/ssn)
  const token = generateJWT(user.id);
  return { token, user: { id: user.id, email: user.email } };
}

// Retrieve and decrypt sensitive data
async function getUserSSN(userId) {
  const user = await User.findByPk(userId);
  const encryptionKey = Buffer.from(process.env.ENCRYPTION_KEY, 'hex');
  const ssn = decryptData(user.ssn, encryptionKey);
  return ssn;
}
```

#### Quiz Questions & Answers

**Q1: Where should you store API secrets?**
A: In environment variables (.env file) on the server, never in code.

**Q2: Should you store authentication tokens in localStorage?**
A: Not ideal; httpOnly cookies are safer. If you must, use sessionStorage.

**Q3: What's the difference between hashing and encryption?**
A: Hashing is one-way (for passwords); encryption is reversible (for data that needs retrieval).

**Q4: Should the encryption key be stored in the database?**
A: No, store it separately in environment variables or a key management service.

**Q5: What's the .gitignore file for?**
A: To prevent committing .env files and other sensitive files to version control.

---

### Authentication & JWT

#### Explanation
Authentication verifies who a user is. JWT (JSON Web Tokens) is a secure way to transmit authentication information.

#### JWT Basics
```javascript
const jwt = require('jsonwebtoken');

// Create JWT token
function generateToken(userId, expiresIn = '1h') {
  const payload = {
    userId,
    iat: Math.floor(Date.now() / 1000), // Issued at
    exp: Math.floor(Date.now() / 1000) + 3600 // Expires in 1 hour
  };
  
  const secret = process.env.JWT_SECRET;
  return jwt.sign(payload, secret);
}

// Verify JWT token
function verifyToken(token) {
  try {
    const secret = process.env.JWT_SECRET;
    const decoded = jwt.verify(token, secret);
    return decoded;
  } catch (error) {
    return null; // Invalid or expired
  }
}

// Middleware to protect routes
function authMiddleware(req, res, next) {
  const token = req.headers.authorization?.split(' ')[1]; // "Bearer token"
  
  if (!token) {
    return res.status(401).json({ error: 'No token provided' });
  }
  
  const decoded = verifyToken(token);
  if (!decoded) {
    return res.status(401).json({ error: 'Invalid token' });
  }
  
  req.userId = decoded.userId;
  next();
}

// Protected route
app.get('/api/profile', authMiddleware, (req, res) => {
  res.json({ userId: req.userId });
});
```

#### Login Flow
```javascript
// Login endpoint
app.post('/api/login', async (req, res) => {
  const { email, password } = req.body;
  
  try {
    // Find user
    const user = await User.findOne({ email });
    if (!user) {
      return res.status(401).json({ error: 'Invalid credentials' });
    }
    
    // Verify password
    const isValid = await bcrypt.compare(password, user.password);
    if (!isValid) {
      return res.status(401).json({ error: 'Invalid credentials' });
    }
    
    // Generate token
    const token = generateToken(user.id);
    
    // Return token (in real app, set as httpOnly cookie)
    res.json({ token, user: { id: user.id, email: user.email } });
  } catch (error) {
    res.status(500).json({ error: 'Server error' });
  }
});

// Frontend login
async function login(email, password) {
  const response = await fetch('/api/login', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ email, password })
  });
  
  if (!response.ok) {
    throw new Error('Login failed');
  }
  
  const { token } = await response.json();
  
  // Store token (preferably in httpOnly cookie via server)
  sessionStorage.setItem('token', token);
  
  // Redirect to dashboard
  window.location.href = '/dashboard';
}
```

#### Refresh Tokens
```javascript
// Generate both access and refresh tokens
function generateTokens(userId) {
  const accessToken = jwt.sign(
    { userId, type: 'access' },
    process.env.JWT_SECRET,
    { expiresIn: '15m' } // Short-lived
  );
  
  const refreshToken = jwt.sign(
    { userId, type: 'refresh' },
    process.env.REFRESH_TOKEN_SECRET,
    { expiresIn: '7d' } // Long-lived
  );
  
  return { accessToken, refreshToken };
}

// Refresh token endpoint
app.post('/api/refresh', (req, res) => {
  const { refreshToken } = req.body;
  
  try {
    const decoded = jwt.verify(refreshToken, process.env.REFRESH_TOKEN_SECRET);
    const newAccessToken = jwt.sign(
      { userId: decoded.userId },
      process.env.JWT_SECRET,
      { expiresIn: '15m' }
    );
    
    res.json({ accessToken: newAccessToken });
  } catch (error) {
    res.status(401).json({ error: 'Invalid refresh token' });
  }
});
```

#### Purpose
To verify user identity and authorize access to protected resources securely.

#### Examples
```javascript
// Complete authentication system
async function setupAuth(app) {
  // Login
  app.post('/api/auth/login', async (req, res) => {
    const { email, password } = req.body;
    
    const user = await User.findOne({ email });
    if (!user || !await bcrypt.compare(password, user.password)) {
      return res.status(401).json({ error: 'Invalid credentials' });
    }
    
    const { accessToken, refreshToken } = generateTokens(user.id);
    
    // Set refresh token as httpOnly cookie
    res.cookie('refreshToken', refreshToken, {
      httpOnly: true,
      secure: true,
      sameSite: 'strict'
    });
    
    res.json({ accessToken, user: { id: user.id, email: user.email } });
  });
  
  // Protected route
  app.get('/api/profile', authMiddleware, async (req, res) => {
    const user = await User.findByPk(req.userId);
    res.json(user);
  });
  
  // Logout
  app.post('/api/auth/logout', (req, res) => {
    res.clearCookie('refreshToken');
    res.json({ message: 'Logged out' });
  });
}

// Frontend usage
async function getProtectedData(accessToken) {
  const response = await fetch('/api/profile', {
    headers: {
      'Authorization': `Bearer ${accessToken}`
    }
  });
  
  if (response.status === 401) {
    // Token expired, refresh it
    const newToken = await refreshAccessToken();
    return getProtectedData(newToken);
  }
  
  return response.json();
}
```

#### Quiz Questions & Answers

**Q1: What is JWT?**
A: JSON Web Token - a secure way to transmit authentication information between client and server.

**Q2: Can JWT tokens be decoded by anyone?**
A: Yes, they're Base64 encoded, not encrypted. The signature is what prevents tampering.

**Q3: Should you store JWT in localStorage?**
A: For SPAs it's acceptable, but httpOnly cookies are more secure (can't be accessed by JS).

**Q4: What's the difference between access and refresh tokens?**
A: Access tokens are short-lived for API requests; refresh tokens are long-lived to get new access tokens.

**Q5: Should JWT tokens contain sensitive data?**
A: No, they're not encrypted. Only put non-sensitive identifying information in them.

---

## Tools & CLI [↑ Back to Top](#top)

### Node.js & npm

#### Explanation
Node.js is a JavaScript runtime environment that runs JavaScript outside browsers. npm (Node Package Manager) manages JavaScript packages and dependencies.

#### Installation & Setup
```bash
# Check Node.js version
node --version  # or node -v

# Check npm version
npm --version  # or npm -v

# Update npm
npm install -g npm@latest

# Initialize new project
npm init
npm init -y  # Skip questions

# Install specific version
npm install package-name@1.2.3

# Install from package.json
npm install
```

#### Common npm Commands
```bash
# Install dependencies
npm install                           # Install all
npm install package-name              # Install specific package
npm install --save package-name       # Install and save to dependencies
npm install --save-dev package-name   # Install as dev dependency

# Update packages
npm update                             # Update all
npm update package-name                # Update specific package

# Remove packages
npm uninstall package-name             # Remove from project
npm uninstall -g package-name          # Remove globally

# List packages
npm list                               # List all installed
npm list -g                            # List globally installed

# Search for packages
npm search package-name                # Search npm registry

# Run scripts (defined in package.json)
npm start                              # Run start script
npm test                               # Run test script
npm run custom-script                  # Run custom script
```

#### package.json
```json
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "My awesome project",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "test": "jest",
    "dev": "nodemon index.js",
    "build": "webpack"
  },
  "dependencies": {
    "express": "^4.18.0",
    "mongoose": "^5.9.0"
  },
  "devDependencies": {
    "jest": "^29.0.0",
    "nodemon": "^2.0.0"
  },
  "keywords": ["node", "javascript"],
  "author": "Your Name",
  "license": "MIT"
}
```

#### Version Semantics (Semantic Versioning)
```
Version format: MAJOR.MINOR.PATCH (e.g., 1.2.3)

^ (caret): Compatible with version
  ^1.2.3 allows >=1.2.3 <2.0.0

~ (tilde): Approximately equivalent
  ~1.2.3 allows >=1.2.3 <1.3.0

* or x: Any version
  * allows any version

> >= < <= =: Comparison operators
```

#### Purpose
To manage project dependencies, run development servers, and automate tasks.

#### Examples
```bash
# Create new React project
npm create react-app my-app
cd my-app
npm start

# Install testing framework
npm install --save-dev jest
npm test

# Install and use package globally
npm install -g http-server
http-server  # Start simple server
```

#### Quiz Questions & Answers

**Q1: What's the difference between dependencies and devDependencies?**
A: dependencies are needed to run the app; devDependencies are only for development/testing.

**Q2: What does ^ vs ~ mean in package.json?**
A: ^ allows minor/patch updates; ~ allows only patch updates.

**Q3: How do you install specific versions?**
A: Use `npm install package@version` or specify in package.json.

---

### Common JavaScript CLI Commands

#### Node.js Commands
```bash
# Run JavaScript file
node filename.js                    # Execute a JavaScript file
node -e "console.log('Hello')"      # Run inline JavaScript code
node -v                             # Check Node.js version

# Interactive Node.js REPL (Read-Eval-Print Loop)
node                                # Start interactive JavaScript shell
# Type .exit or Ctrl+C to quit
```

#### npm Commands
```bash
# Initialize and install
npm init                            # Create package.json interactively
npm init -y                         # Create package.json with defaults
npm install                         # Install all dependencies

# Install packages
npm install package-name            # Install latest version
npm install package-name@version    # Install specific version
npm install package-name@latest     # Install latest version explicitly
npm install --save package-name     # Install and add to dependencies
npm install --save-dev package-name # Install as development dependency
npm install -g package-name         # Install globally

# Update packages
npm update                          # Update all packages
npm update package-name             # Update specific package
npm outdated                        # List outdated packages

# Remove packages
npm uninstall package-name          # Remove package locally
npm uninstall -g package-name       # Remove global package
npm prune                           # Remove unused packages

# List packages
npm list                            # List all installed packages
npm list -g                         # List globally installed packages
npm list package-name               # Check if package is installed
npm search package-name             # Search npm registry

# Run scripts (defined in package.json)
npm start                           # Run start script
npm test                            # Run test script
npm run dev                         # Run dev script
npm run build                       # Run build script
npm run [custom-script]             # Run custom script

# Clean and audit
npm clean cache                     # Clear npm cache
npm audit                           # Check for security vulnerabilities
npm audit fix                       # Automatically fix vulnerabilities

# Version management
npm version patch                   # Increment patch version (1.0.0 → 1.0.1)
npm version minor                   # Increment minor version (1.0.0 → 1.1.0)
npm version major                   # Increment major version (1.0.0 → 2.0.0)
```

#### yarn Commands (Alternative Package Manager)
```bash
# Initialize and install
yarn init                           # Create package.json
yarn install                        # Install dependencies from yarn.lock

# Install packages
yarn add package-name               # Install package
yarn add package-name@version       # Install specific version
yarn add --dev package-name         # Install as dev dependency
yarn add -g package-name            # Install globally

# Remove packages
yarn remove package-name            # Remove package

# List packages
yarn list                           # List installed packages
yarn info package-name              # Get package information

# Run scripts
yarn start                          # Run start script
yarn test                           # Run test script
yarn [script-name]                  # Run custom script

# Other commands
yarn upgrade                        # Upgrade packages
yarn cache clean                    # Clear cache
yarn audit                          # Check security vulnerabilities
```

#### npx Commands (Execute npm Packages)
```bash
# Run packages without installing
npx package-name                    # Run package directly
npx package-name@version            # Run specific version
npx -p package-name script-name     # Run script from package

# Create new projects
npx create-react-app my-app         # Create React application
npx vite                            # Create Vite project
npx webpack                         # Run Webpack bundler
```

#### Purpose
To manage JavaScript projects, install dependencies, run development servers, execute scripts, and manage package versions.

#### Examples
```bash
# Create and setup a new JavaScript project
npm init -y
npm install express
npm install --save-dev nodemon
npm start

# Run JavaScript file directly
node app.js

# Install and use a package globally
npm install -g http-server
http-server

# Run linting/formatting tools
npm run lint
npm run format

# Build and test
npm run build
npm test

# Check for security issues
npm audit
npm audit fix

# Work with specific package versions
npm install lodash@4.17.21
npm install react@latest
npm install --save-dev typescript@5.0.0
```

#### Quiz Questions & Answers

**Q1: What's the difference between `npm install` and `npm install -g`?**
A: `npm install` installs packages locally in the project; `-g` installs globally for system-wide access.

**Q2: What does `npm run build` do?**
A: It runs the build script defined in package.json, typically used to compile/bundle code for production.

**Q3: How do you install a package as a dev dependency?**
A: Use `npm install --save-dev package-name` (appears in devDependencies, not used in production).

**Q4: What's the difference between npm and yarn?**
A: Both are package managers for JavaScript; yarn is faster and uses lock files by default; npm is the official Node.js package manager.

**Q5: What does npx do?**
A: Executes npm packages without installing them globally, useful for running tools once or testing packages.

---

## Index & Quick Reference [↑ Back to Top](#top)

### By Difficulty Level

**Beginner Topics:**
- Variables & Data Types
- Operators
- Control Structures
- Functions
- String Manipulation

**Intermediate Topics:**
- Objects & Arrays
- Scope & Closures
- DOM Manipulation
- Event Handling
- Asynchronous JavaScript

**Advanced Topics:**
- Classes & Prototypes
- Higher-Order Functions
- Promises & Async/Await
- Regular Expressions
- Destructuring

### By Category

**Core Language:**
- Variables & Data Types
- Operators
- Control Structures
- Functions
- Scope & Closures

**Object-Oriented:**
- Objects & Arrays
- Classes & Prototypes
- Higher-Order Functions

**Functional Programming:**
- Functions
- Higher-Order Functions
- Destructuring

**String & Pattern Matching:**
- String Manipulation
- Regular Expressions
- Template Literals

**Asynchronous Programming:**
- Callbacks
- Promises
- Async/Await
- Fetch API

**DOM & Browser:**
- DOM Manipulation
- Event Handling
- Local Storage & Session Storage
- Fetch API

---

<!-- Practical Implementation: Back to Top Arrow

### Overview
A "Back to Top" button is a common UX feature that helps users quickly navigate to the top of long pages. It appears as the user scrolls down and smoothly scrolls back to the top when clicked.

### HTML Structure
```html
<!-- Add this button element to your page, typically before closing </body> -- >
<button id="backToTopBtn" class="back-to-top" title="Go to top">
  ↑ Back to Top
</button>
```

### CSS Styling
```css
/* Back to Top Button Styling */
.back-to-top {
  position: fixed;
  bottom: 30px;
  right: 30px;
  background-color: #007bff;
  color: white;
  padding: 12px 18px;
  border: none;
  border-radius: 50px;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
  z-index: 999;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

/* Show button when it has the 'show' class */
.back-to-top.show {
  opacity: 1;
  visibility: visible;
}

/* Hover effect */
.back-to-top:hover {
  background-color: #0056b3;
  transform: translateY(-3px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
}

/* Active state */
.back-to-top:active {
  transform: translateY(-1px);
}
```

### JavaScript Implementation

**Method 1: Simple Implementation**
```javascript
const backToTopBtn = document.getElementById("backToTopBtn");

// Show/hide button based on scroll position
window.addEventListener("scroll", () => {
  if (window.pageYOffset > 300) {
    backToTopBtn.classList.add("show");
  } else {
    backToTopBtn.classList.remove("show");
  }
});

// Smooth scroll to top when button is clicked
backToTopBtn.addEventListener("click", () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth"
  });
});
```

**Method 2: Using requestAnimationFrame for Better Performance**
```javascript
const backToTopBtn = document.getElementById("backToTopBtn");

window.addEventListener("scroll", () => {
  if (window.pageYOffset > 300) {
    backToTopBtn.classList.add("show");
  } else {
    backToTopBtn.classList.remove("show");
  }
});

function scrollToTop() {
  const scrollHeight = window.scrollY;
  const scrollStep = scrollHeight / 30; // Divide scroll into 30 steps
  
  let scrollAmount = 0;
  const scrollInterval = setInterval(() => {
    if (scrollAmount < scrollHeight) {
      window.scrollBy(0, -scrollStep);
      scrollAmount += scrollStep;
    } else {
      clearInterval(scrollInterval);
      window.scrollTo(0, 0); // Ensure we're at the exact top
    }
  }, 10);
}

backToTopBtn.addEventListener("click", scrollToTop);
```

**Method 3: Advanced with Throttling**
```javascript
const backToTopBtn = document.getElementById("backToTopBtn");

// Throttle function to limit scroll event firing
function throttle(func, limit) {
  let inThrottle;
  return function() {
    if (!inThrottle) {
      func.apply(this);
      inThrottle = true;
      setTimeout(() => inThrottle = false, limit);
    }
  };
}

// Show/hide button with throttling
const handleScroll = throttle(() => {
  if (window.pageYOffset > 300) {
    backToTopBtn.classList.add("show");
  } else {
    backToTopBtn.classList.remove("show");
  }
}, 100);

window.addEventListener("scroll", handleScroll);

// Scroll to top with smooth animation
backToTopBtn.addEventListener("click", () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth"
  });
});
```

### How It Works

1. **HTML Button**: A fixed-position button is added to the page
2. **CSS Styling**: 
   - Positioned fixed (stays visible while scrolling)
   - Hidden by default with `opacity: 0` and `visibility: hidden`
   - Shows when `.show` class is added
   - Smooth transitions and hover effects
3. **JavaScript Logic**:
   - Listens to scroll events
   - Shows button when page is scrolled down more than 300px
   - Hides button when near the top
   - Scrolls smoothly to top when clicked

### Where It's Used
- Long-form articles and documentation
- E-commerce product pages
- Blog posts with extensive content
- FAQ pages
- Tutorial pages
- Any page with significant scrollable content

### Purpose
To improve user experience by:
- Reducing scroll fatigue on long pages
- Providing quick navigation to page top
- Improving accessibility
- Enhancing visual feedback

### Quiz Questions & Answers

**Q1: Why use `position: fixed` for the back-to-top button?**
A: Fixed positioning keeps the button visible at a constant position on the screen, even while scrolling.

**Q2: What does the `show` class do?**
A: It changes the opacity from 0 to 1 and visibility from hidden to visible, making the button appear.

**Q3: How do you create a smooth scroll to the top?**
A: Use `window.scrollTo({ top: 0, behavior: "smooth" })` - the `behavior: "smooth"` property enables the smooth animation.

**Q4: Why is throttling useful in the scroll event?**
A: It limits how often the scroll event handler runs, improving performance by reducing unnecessary function calls.

**Q5: What's the advantage of using requestAnimationFrame over setInterval?**
A: requestAnimationFrame syncs with the browser's repaint cycle, resulting in smoother animations and better performance.

### Complete Example
Save this as `index.html` to see the back-to-top button in action:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Back to Top Example</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      color: #333;
    }
    
    main {
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
    }
    
    h1, h2 {
      color: #007bff;
    }
    
    section {
      margin-bottom: 50px;
      padding-bottom: 30px;
      border-bottom: 1px solid #ddd;
    }
    
    .back-to-top {
      position: fixed;
      bottom: 30px;
      right: 30px;
      background-color: #007bff;
      color: white;
      padding: 12px 18px;
      border: none;
      border-radius: 50px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      opacity: 0;
      visibility: hidden;
      transition: opacity 0.3s ease, visibility 0.3s ease;
      z-index: 999;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }
    
    .back-to-top.show {
      opacity: 1;
      visibility: visible;
    }
    
    .back-to-top:hover {
      background-color: #0056b3;
      transform: translateY(-3px);
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    }
  </style>
</head>
<body>
  <main>
    <h1>Long Page with Back to Top Button</h1>
    
    <section>
      <h2>Section 1</h2>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris.</p>
      <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
    </section>
    
    <section>
      <h2>Section 2</h2>
      <p>Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
    </section>
    
    <section>
      <h2>Section 3</h2>
      <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
    </section>
    
    <section>
      <h2>Section 4</h2>
      <p>Scroll down and you'll see the back-to-top button appear in the bottom-right corner.</p>
      <p>Click it to smoothly scroll back to the top of the page.</p>
    </section>
  </main>
  
  <!-- Back to Top Button -- >
  <button id="backToTopBtn" class="back-to-top" title="Go to top">
    ↑ Back to Top
  </button>
  
  <script>
    const backToTopBtn = document.getElementById("backToTopBtn");
    
    window.addEventListener("scroll", () => {
      if (window.pageYOffset > 300) {
        backToTopBtn.classList.add("show");
      } else {
        backToTopBtn.classList.remove("show");
      }
    });
    
    backToTopBtn.addEventListener("click", () => {
      window.scrollTo({
        top: 0,
        behavior: "smooth"
      });
    });
  </script>
</body>
</html>
```

-->

---

## All Quiz Questions & Answers [↑ Back to Top](#top)

### Fundamentals

#### Variables & Data Types
**Q1: What's the difference between `var`, `let`, and `const`?**
A: `var` is function-scoped and hoisted; `let` and `const` are block-scoped. `const` can't be reassigned but is still mutable for objects/arrays.

**Q2: How do you check the type of a variable?**
A: Use `typeof` operator: `typeof variable`. For arrays and objects, use `Array.isArray()` or `instanceof`.

**Q3: Are JavaScript strings mutable?**
A: No, strings are immutable. Methods like `toUpperCase()` return new strings rather than modifying the original.

**Q4: What's the difference between `null` and `undefined`?**
A: `undefined` means a variable hasn't been assigned; `null` is an intentional absence of value.

**Q5: Why should you use `const` by default?**
A: `const` prevents accidental reassignment and makes code intent clearer. Use `let` only when you need to reassign.

#### Operators
**Q1: What's the difference between `==` and `===`?**
A: `==` does type coercion; `===` requires same type and value. Always use `===`.

**Q2: What does the `??` (nullish coalescing) operator do?**
A: Returns the right operand only if the left is `null` or `undefined`, not other falsy values.

**Q3: How does the ternary operator work?**
A: `condition ? valueIfTrue : valueIfFalse` - it's shorthand for simple if/else statements.

**Q4: What's the purpose of the spread operator `...`?**
A: It expands iterables (arrays/objects). In arrays: `[...arr]` copies; in objects: `{...obj}` spreads properties.

**Q5: What does the logical AND operator `&&` return?**
A: It returns the first falsy value or the last value if all are truthy. Useful for short-circuit evaluation.

#### Control Structures
**Q1: What's the difference between `for`, `while`, and `do...while`?**
A: `for` is best for known iterations; `while` repeats while condition is true; `do...while` executes at least once.

**Q2: When should you use `switch` instead of `if/else`?**
A: When checking one value against multiple cases - it's cleaner and potentially faster than multiple `if` statements.

**Q3: What happens if you forget a `break` statement in a switch?**
A: Execution "falls through" to the next case, executing code even if the case doesn't match.

**Q4: Can you nest control structures?**
A: Yes, you can nest loops, conditionals, and other control structures, but deeply nested code becomes hard to read.

**Q5: What's the purpose of the `label` statement in JavaScript?**
A: It identifies loops or blocks for use with `break` or `continue`, allowing you to break out of nested loops.

#### Functions
**Q1: What's the difference between function declarations and expressions?**
A: Declarations are hoisted and can be called before definition; expressions are not hoisted and must be defined before use.

**Q2: Are arrow functions the same as regular functions?**
A: No, arrow functions don't have their own `this` binding and don't have an `arguments` object.

**Q3: What's a pure function?**
A: A function that always produces the same output for the same input and has no side effects.

**Q4: Can a function modify variables outside its scope?**
A: Yes, it can access and modify outer scope variables (closures), but it's generally considered bad practice.

**Q5: What's the return value if a function doesn't have a return statement?**
A: `undefined` - every JavaScript function returns something, even if not explicitly stated.

#### Parameters
**Q1: How do default parameters work?**
A: `function(param = defaultValue)` - if the parameter isn't provided, the default value is used.

**Q2: What are rest parameters?**
A: `...args` captures remaining arguments into an array. Useful when you don't know how many arguments will be passed.

**Q3: How does destructuring work with function parameters?**
A: `function({ name, age }) { }` extracts object properties directly into parameters, cleaner than `param.name`.

**Q4: What's the difference between positional and named parameters?**
A: Positional parameters depend on order; named parameters (objects) are order-independent and self-documenting.

**Q5: Can you mix rest parameters with regular parameters?**
A: Yes, but rest parameters must be last: `function(a, b, ...rest)` is valid; `function(...rest, a)` is not.

#### Truthy & Falsy
**Q1: What are the six falsy values in JavaScript?**
A: `false`, `0`, `""` (empty string), `null`, `undefined`, and `NaN`.

**Q2: Is an empty array truthy or falsy?**
A: Truthy! `[]` is truthy even though `[].length === 0`. This is a common gotcha.

**Q3: How do you convert a value to boolean?**
A: Use the `Boolean()` function or the `!!` double negation operator.

**Q4: What's the nullish coalescing operator used for?**
A: `??` returns the right side only if left is `null` or `undefined`, preserving other falsy values like `0` or `""`.

**Q5: Why is `if (arr.length)` safer than `if (arr)`?**
A: Because `[]` is truthy even when empty, but `[].length` is `0` which is falsy.

#### Type Coercion & Type Checking
**Q1: What's the difference between implicit and explicit type coercion?**
A: Implicit happens automatically (e.g., `"5" + 3` becomes `"53"`); explicit uses functions like `Number()` or `String()`.

**Q2: What does `typeof` return for an array?**
A: `"object"` - arrays are objects in JavaScript. Use `Array.isArray()` to check specifically for arrays.

**Q3: How do you safely check for `NaN`?**
A: Use `Number.isNaN()` or `Object.is(value, NaN)`. Avoid `value === NaN` or `typeof NaN` which don't work correctly.

**Q4: Why does `"5" > 3` return true in JavaScript?**
A: In comparisons (not equality), strings are coerced to numbers, so `"5"` becomes `5`.

**Q5: What's the safest way to check a variable's type?**
A: Use `Object.prototype.toString.call(value)` for accurate type detection, or use TypeScript for type safety.

#### Hoisting
**Q1: What gets hoisted in JavaScript?**
A: Function declarations and variable declarations (as `undefined`). Function expressions and `let`/`const` aren't fully hoisted.

**Q2: What's the Temporal Dead Zone (TDZ)?**
A: The period between the start of a block and where a `let`/`const` variable is declared, where accessing it throws ReferenceError.

**Q3: Are arrow functions hoisted?**
A: No, arrow functions are expressions and follow the same hoisting rules as function expressions.

**Q4: What happens if you reference a variable before declaring it with `var`?**
A: It returns `undefined` due to hoisting, not an error. This is why `let`/`const` are preferred.

**Q5: How does hoisting affect the `this` keyword?**
A: Hoisting doesn't directly affect `this`, but function hoisting can affect where `this` is bound.

#### Scope & Closures
**Q1: What's the difference between local scope and global scope?**
A: Global scope is accessible everywhere; local scope is limited to a function or block.

**Q2: What's a closure?**
A: A function that has access to variables from its outer scope even after the outer function has finished executing.

**Q3: Can you have a closure in a closure?**
A: Yes, nested functions create nested closures with access to all parent scopes.

**Q4: What's the memory implication of closures?**
A: Closures keep references to outer variables in memory, which can cause memory leaks if not managed carefully.

**Q5: How do you use closures for data privacy?**
A: Return an object with methods that access private variables in the closure, like the module pattern.

### Intermediate Concepts

#### Objects & Arrays
**Q1: How do you check if an object has a property?**
A: Use `obj.hasOwnProperty('prop')`, `'prop' in obj`, or `obj.prop !== undefined`.

**Q2: What's the difference between a shallow and deep copy?**
A: Shallow copy (`{...obj}`) copies top level only; deep copy recursively copies nested objects.

**Q3: Can you modify array methods like `map` to behave differently?**
A: No, built-in methods can't be changed, but you can create wrapper functions.

**Q4: How do you merge multiple objects?**
A: Use spread operator `{...obj1, ...obj2}` or `Object.assign(target, source)`.

**Q5: What's the fastest way to check array length?**
A: Using the `length` property directly: `arr.length` - it's always available without computation.

#### String Manipulation
**Q1: How do you check if a string contains a substring?**
A: Use `str.includes('substring')`, `str.indexOf()`, or regex `str.match()`.

**Q2: What's the difference between `slice` and `substring` on strings?**
A: `slice` accepts negative indices; `substring` doesn't and swaps parameters if start > end.

**Q3: Can you modify a string in place?**
A: No, strings are immutable. All methods return new strings.

**Q4: How do you split a string into an array?**
A: Use `string.split('delimiter')` or regex `string.split(/regex/)`.

**Q5: What does `trim()` do and are there variations?**
A: `trim()` removes whitespace from both ends; `trimStart()` and `trimEnd()` remove from specific sides.

#### Methods
**Q1: What's the difference between `map` and `forEach`?**
A: `map` returns a new array; `forEach` has no return value and is only for side effects.

**Q2: How does `filter` work and what does it return?**
A: `filter` returns a new array with elements that pass the test function.

**Q3: What does `reduce` do?**
A: `reduce` iterates through array elements, accumulating a single value returned at the end.

**Q4: Can you chain array methods?**
A: Yes, as long as they return arrays. Example: `arr.filter(x => x > 5).map(x => x * 2)`.

**Q5: What's the difference between `find` and `filter`?**
A: `find` returns the first matching element; `filter` returns all matching elements as an array.

#### Callback Functions
**Q1: What's a callback function?**
A: A function passed as an argument to another function, to be executed later (synchronously or asynchronously).

**Q2: What's "callback hell" and how do you avoid it?**
A: Deeply nested callbacks are hard to read. Use promises, async/await, or named functions instead.

**Q3: Can callbacks be asynchronous?**
A: Yes, callbacks can be used for async operations, but they lead to callback hell. Promises are better.

**Q4: How do you handle errors in callbacks?**
A: Pass an error as the first parameter (Node.js convention) or use try/catch.

**Q5: Are callbacks always asynchronous?**
A: No, callbacks can be synchronous (like `array.map(callback)`) or asynchronous (like `setTimeout(callback)`).

#### IIFE - Immediately Invoked Function Expression
**Q1: Why use IIFE instead of regular functions?**
A: IIFE creates a new scope immediately, preventing variable pollution and keeping globals clean.

**Q2: Can you pass parameters to an IIFE?**
A: Yes, parameters go after the function: `(function(param) { })(argument)`.

**Q3: What's the module pattern?**
A: An IIFE that returns an object with public methods and private variables for encapsulation.

**Q4: Do arrow functions work with IIFE?**
A: Yes, `((arg) => { })(value)` works, but arrow functions don't have their own `this`.

**Q5: Can IIFE return values?**
A: Yes, and you can assign the returned value: `const result = (function() { return 42; })();`.

#### Event Loop & Call Stack
**Q1: What's the difference between macrotasks and microtasks?**
A: Macrotasks include setTimeout, I/O; microtasks include Promises, async/await. Microtasks run before next macrotask.

**Q2: Why does `console.log` in a Promise appear before setTimeout?**
A: Promises (microtasks) run before setTimeout (macrotask) even if setTimeout is scheduled first.

**Q3: What happens if the call stack is full?**
A: A "Maximum call stack size exceeded" error occurs (infinite recursion or very deep calls).

**Q4: Can you have multiple event loops?**
A: Each browser tab/web worker has its own event loop. Node.js has one main event loop with phases.

**Q5: What's the purpose of `process.nextTick()` in Node.js?**
A: It queues a callback to run after the current operation but before the next event loop iteration.

#### Regular Expressions
**Q1: What does the `/g` flag do in regex?**
A: Global flag finds all matches instead of just the first one.

**Q2: How do you test if a string matches a pattern?**
A: Use `regex.test(string)` or `string.match(regex)`.

**Q3: What's the difference between `search` and `indexOf` on strings?**
A: `search` accepts regex; `indexOf` searches for literal strings.

**Q4: How do you replace all occurrences of a pattern?**
A: Use `string.replaceAll()` or regex with `/g` flag in `replace()`.

**Q5: What are capturing groups in regex?**
A: Parentheses `()` capture parts of the match for later reference or extraction.

#### Error Handling
**Q1: What's the difference between try/catch and if/else for errors?**
A: try/catch handles runtime errors; if/else checks conditions. Use try/catch for exceptions.

**Q2: Can you have multiple catch blocks?**
A: JavaScript doesn't support multiple catch blocks directly, but you can check error type inside one.

**Q3: Does finally execute if catch returns early?**
A: Yes, finally always executes regardless of return statements in try/catch.

**Q4: How do you create custom errors?**
A: Extend the Error class: `class CustomError extends Error { }` or throw custom objects.

**Q5: What's the difference between throw and return in error handling?**
A: `throw` creates an exception (stops execution); `return` returns a value (normal flow).

#### Asynchronous JavaScript
**Q1: What's the disadvantage of callbacks for async operations?**
A: Callback hell - deeply nested callbacks become unreadable and hard to maintain.

**Q2: How are Promises better than callbacks?**
A: Promises chain with `.then()`, making async code more readable and easier to error-handle.

**Q3: What happens if you don't handle a Promise rejection?**
A: An unhandled promise rejection error occurs (Node.js crashes in some versions).

**Q4: Can you mix Promises and async/await?**
A: Yes, async functions return Promises, and you can await Promises inside async functions.

**Q5: What's the purpose of Promise.all()?**
A: It waits for all promises to resolve and returns an array of results; fails if any promise rejects.

### Advanced Concepts

#### Classes & Prototypes
**Q1: What's the difference between classical and prototypal inheritance?**
A: Classical (ES6 classes) is more familiar; prototypal is more flexible, allowing dynamic property assignment.

**Q2: Do ES6 classes use prototypes underneath?**
A: Yes, ES6 classes are syntactic sugar over prototype-based inheritance.

**Q3: How do you create a private method in a class?**
A: Use the `#` prefix: `#privateMethod() { }` (supported in modern JavaScript).

**Q4: Can you use super in arrow functions?**
A: No, arrow functions don't have their own `this`, so `super` doesn't work correctly.

**Q5: What's the difference between static and instance methods?**
A: Static methods are called on the class itself; instance methods are called on objects.

#### Higher-Order Functions
**Q1: What's a higher-order function?**
A: A function that takes another function as argument or returns a function.

**Q2: How is currying different from partial application?**
A: Currying transforms a function to take one argument at a time; partial application fixes some arguments.

**Q3: What's function composition?**
A: Combining multiple functions so the output of one becomes the input of the next.

**Q4: Why use memoization in higher-order functions?**
A: Memoization caches results to avoid redundant calculations, improving performance.

**Q5: Can you compose async functions?**
A: Yes, but you need to handle promises properly with `.then()` or async/await.

#### Destructuring
**Q1: Can you rename variables when destructuring?**
A: Yes, use the colon syntax: `const { oldName: newName } = obj`.

**Q2: What happens if a destructured variable doesn't exist?**
A: It's `undefined` unless you provide a default value: `const { prop = 'default' } = obj`.

**Q3: How do you destructure nested objects?**
A: `const { outer: { inner } } = obj` accesses nested properties.

**Q4: Can you destructure in function parameters?**
A: Yes, perfect for extracting specific properties without accessing the full object.

**Q5: What's the difference between rest and spread in destructuring?**
A: Rest `...rest` collects remaining properties; spread `...obj` distributes properties.

#### Template Literals
**Q1: What's the advantage of template literals over concatenation?**
A: Template literals are more readable, support multiline strings, and have expression interpolation.

**Q2: Can you execute expressions inside `${}`?**
A: Yes, any JavaScript expression works: `${2 + 2}`, `${array.length}`, `${func()}`.

**Q3: What's a tagged template literal?**
A: A function that processes template literal parts and expressions customly.

**Q4: Are template literals faster than string concatenation?**
A: Not significantly, but they're more readable which is the main advantage.

**Q5: How do you escape backticks in template literals?**
A: Use backslash: `` \` `` or just use regular quotes inside without escaping.

#### Promises & Async/Await
**Q1: What are the three states of a Promise?**
A: Pending (initial), Fulfilled (resolved successfully), Rejected (error occurred).

**Q2: Can you catch errors from all promises with one .catch()?**
A: Yes, if they're chained: `promise.then().then().catch()` catches all errors.

**Q3: What does `Promise.race()` do?**
A: Returns the result of whichever promise settles first (resolves or rejects).

**Q4: Can you await non-Promise values?**
A: Yes, `await 42` immediately returns 42. This makes mixing sync and async code easier.

**Q5: Is async/await just syntactic sugar for Promises?**
A: Essentially yes, but it reads like synchronous code and has better error handling with try/catch.

### DOM & Browser APIs

#### DOM Manipulation
**Q1: What's the difference between `querySelector` and `getElementById`?**
A: `querySelector` uses CSS selectors (more flexible); `getElementById` only finds by ID (faster).

**Q2: When should you use `textContent` vs `innerHTML`?**
A: `textContent` for plain text (safer); `innerHTML` for HTML (careful with user input).

**Q3: How do you add multiple classes to an element efficiently?**
A: Use `classList.add('class1', 'class2', 'class3')` instead of adding one at a time.

**Q4: What's the difference between `appendChild` and `insertBefore`?**
A: `appendChild` adds to the end; `insertBefore` inserts at a specific position.

**Q5: Can you modify the DOM in a loop safely?**
A: Yes, but be careful iterating while adding/removing elements. Create a copy or use NodeList properly.

#### Event Handling
**Q1: What's the difference between event capturing and bubbling?**
A: Capturing goes from top to bottom; bubbling goes from bottom to top through the DOM tree.

**Q2: When should you use event delegation?**
A: When handling many similar elements (like list items), attach one listener to parent instead of each child.

**Q3: What does `event.stopPropagation()` do?**
A: Prevents the event from bubbling up to parent elements.

**Q4: What's the difference between `addEventListener` and inline event handlers?**
A: `addEventListener` is cleaner, allows multiple listeners, and separates JS from HTML.

**Q5: How do you remove an event listener?**
A: `element.removeEventListener('event', functionReference)` - you need the same function reference.

#### Local Storage & Session Storage
**Q1: What's the size limit for localStorage?**
A: Typically 5-10MB per domain, depending on browser.

**Q2: When is sessionStorage cleared?**
A: When the tab/window is closed (not just the session).

**Q3: Can you store objects directly in storage?**
A: No, use `JSON.stringify()` to store and `JSON.parse()` to retrieve.

**Q4: Is localStorage secure for sensitive data?**
A: No, it's accessible from JavaScript and vulnerable to XSS attacks.

**Q5: Can you access localStorage from different origins?**
A: No, each origin (protocol, domain, port) has separate storage.

#### Fetch API
**Q1: How do you send headers with a fetch request?**
A: `fetch(url, { headers: { 'Content-Type': 'application/json' } })`.

**Q2: What methods are available for different HTTP operations?**
A: GET (retrieve), POST (create), PUT (update), DELETE (remove), PATCH (partial update).

**Q3: How do you send JSON data with fetch?**
A: Set `body: JSON.stringify(data)` and header `"Content-Type": "application/json"`.

**Q4: Can fetch make requests to different domains?**
A: Only if the server allows CORS. Otherwise, the browser blocks the request.

**Q5: How do you handle fetch errors?**
A: Fetch rejects on network error, not HTTP error status. Check `response.ok` or `response.status`.

### Security & Best Practices

#### Password Hashing & Salting
**Q1: Why shouldn't you store plain text passwords?**
A: If the database is breached, attackers have direct access to all passwords.

**Q2: What's the purpose of salting?**
A: Adds random data to prevent rainbow table attacks where hackers use precomputed hashes.

**Q3: Why is bcrypt better than simple hashing?**
A: bcrypt includes salting automatically and has a configurable cost factor to slow down brute force attacks.

**Q4: How do you verify a password without storing the original?**
A: Hash the provided password and compare it with the stored hash.

**Q5: Should salt values be stored in the database?**
A: For bcrypt, the salt is embedded in the hash. For PBKDF2, yes, store salt (it's not secret).

#### XSS Prevention
**Q1: What's the difference between innerHTML and textContent?**
A: innerHTML parses HTML and can execute scripts; textContent treats everything as plain text (safer).

**Q2: How does DOMPurify help prevent XSS?**
A: It removes dangerous HTML tags and attributes while preserving safe formatting.

**Q3: What is Content Security Policy (CSP)?**
A: A security header that restricts where scripts can be loaded from and what they can do.

**Q4: Should you trust user input?**
A: Never. Always sanitize and validate user input on both client and server.

**Q5: Can XSS attacks happen through form submissions?**
A: Yes, if user input is displayed without sanitization.

#### CSRF Prevention
**Q1: How does CSRF attack work?**
A: Attacker tricks an authenticated user into visiting a malicious site that performs unwanted actions.

**Q2: What's a CSRF token?**
A: A unique, unpredictable token generated by the server and verified on state-changing requests.

**Q3: Why is SameSite cookie important?**
A: It prevents cookies from being sent in cross-site requests, blocking CSRF attacks.

**Q4: Should CSRF tokens be stored in cookies?**
A: The token can be generated and stored server-side; client receives it and must send it back.

**Q5: Does CSRF protection only apply to POST requests?**
A: No, any state-changing request (POST, PUT, DELETE) should be protected.

#### CORS & Security Headers
**Q1: What does CORS prevent?**
A: It prevents websites from making unauthorized requests to APIs on other domains.

**Q2: What's the difference between simple and preflight CORS requests?**
A: Simple requests are sent directly; preflight requests first ask permission via OPTIONS method.

**Q3: Should you allow CORS for all origins?**
A: No, specify allowed origins in production for security.

**Q4: What's the purpose of Strict-Transport-Security header?**
A: Forces browsers to always use HTTPS, preventing man-in-the-middle attacks.

**Q5: Does CORS prevent backend access to other APIs?**
A: No, CORS is a browser security feature. Backend can access any API.

#### Input Validation & Sanitization
**Q1: Is client-side validation enough?**
A: No, server-side validation is required. Client validation can be bypassed.

**Q2: What's the difference between validation and sanitization?**
A: Validation checks if data is correct; sanitization cleans it up.

**Q3: Should you validate on both client and server?**
A: Yes, client validation improves UX, server validation ensures security.

**Q4: How do you safely accept user file uploads?**
A: Validate file type, size, scan for viruses, and save with restricted names.

**Q5: What characters are dangerous in input?**
A: `<`, `>`, `"`, `'`, `&`, `/`, `;`, `--`, etc. (depends on context).

#### SQL Injection Prevention
**Q1: What is SQL Injection?**
A: An attack where malicious SQL code is injected into queries through user input.

**Q2: How do you prevent SQL Injection?**
A: Use parameterized queries/prepared statements that separate code from data.

**Q3: Is escaping enough to prevent SQL Injection?**
A: Parameterized queries are more reliable than escaping.

**Q4: What's an ORM?**
A: Object-Relational Mapping library that handles database queries safely (Sequelize, Mongoose).

**Q5: Should you build SQL queries with string concatenation?**
A: Never, always use parameters or an ORM.

#### Secure Data Storage
**Q1: Where should you store API secrets?**
A: In environment variables (.env file) on the server, never in code.

**Q2: Should you store authentication tokens in localStorage?**
A: Not ideal; httpOnly cookies are safer. If you must, use sessionStorage.

**Q3: What's the difference between hashing and encryption?**
A: Hashing is one-way (for passwords); encryption is reversible (for data that needs retrieval).

**Q4: Should the encryption key be stored in the database?**
A: No, store it separately in environment variables or a key management service.

**Q5: What's the .gitignore file for?**
A: To prevent committing .env files and other sensitive files to version control.

#### Authentication & JWT
**Q1: What is JWT?**
A: JSON Web Token - a secure way to transmit authentication information between client and server.

**Q2: Can JWT tokens be decoded by anyone?**
A: Yes, they're Base64 encoded, not encrypted. The signature is what prevents tampering.

**Q3: Should you store JWT in localStorage?**
A: For SPAs it's acceptable, but httpOnly cookies are more secure (can't be accessed by JS).

**Q4: What's the difference between access and refresh tokens?**
A: Access tokens are short-lived for API requests; refresh tokens are long-lived to get new access tokens.

**Q5: Should JWT tokens contain sensitive data?**
A: No, they're not encrypted. Only put non-sensitive identifying information in them.

---

## Conclusion [↑ Back to Top](#top)

This guide covers essential JavaScript concepts from fundamentals to advanced topics. Regular practice with the provided examples and quiz questions will strengthen your understanding. Keep building projects and experimenting with code to master JavaScript development!

