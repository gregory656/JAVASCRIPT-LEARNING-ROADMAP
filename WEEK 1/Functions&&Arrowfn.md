📘 JavaScript Functions & Arrow Functions 

1️⃣ What are Functions?

Functions are reusable blocks of code that perform a task or return a value.

function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet("Stephen")); // Hello, Stephen!

Key Points:

Functions can have parameters and return values

Can be called/invoked anywhere after declaration (depends on type)



---

2️⃣ Function Types

🔹 1. Function Declaration

function add(a, b) {
  return a + b;
}

console.log(add(2, 3)); // 5

Tricks

Hoisted → can be called before declaration

Can have default parameters


function multiply(a, b = 1) {
  return a * b;
}

Avoid

Using global variables inside functions unnecessarily



---

🔹 2. Function Expression

const subtract = function(a, b) {
  return a - b;
};

console.log(subtract(5, 2)); // 3

Tricks

Not hoisted → must be declared before use

Can be anonymous or named



---

🔹 3. Arrow Functions (ES6)

const divide = (a, b) => a / b;
console.log(divide(10, 2)); // 5

Tricks

Single-expression → implicit return

Can omit parentheses for single parameter


const square = x => x * x;

Avoid

Using this inside arrow functions (arrow functions don’t have their own this)

Not suitable for constructors



---

🔹 4. IIFE (Immediately Invoked Function Expression)

(function() {
  console.log("Runs immediately!");
})();

Use Case: Module pattern, isolating scope


---

3️⃣ Function Arguments

🔹 Rest Parameters

function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}
console.log(sum(1, 2, 3, 4)); // 10

🔹 Default Parameters

function greet(name = "Guest") {
  return `Hello ${name}`;
}

🔹 Arguments Object

function showArgs() {
  console.log(arguments);
}
showArgs(1, 2, 3); // [1,2,3] (not a real array)


---

4️⃣ Arrow Functions vs Regular Functions

Feature	Regular Function	Arrow Function

this	Dynamic	Lexical (inherits from scope)
arguments	Exists	Does not exist
Constructor	✅ Can use new	❌ Cannot use new
Hoisting	✅ Function declaration hoisted	❌ Only expressions are not hoisted



---

5️⃣ Closures (Important!)

A closure is a function remembering the scope in which it was created.

function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  }
}

const counter = outer();
console.log(counter()); // 1
console.log(counter()); // 2

Use Cases:

Private variables

Memoization

Callbacks & Event Handlers



---

6️⃣ Common Mistakes / What to Avoid

Forgetting return in multi-line arrow functions


const sum = (a, b) => { a + b }; // undefined ❌

Confusing this in arrow vs regular functions

Excessive nesting → hard to read

Overusing global variables



---

7️⃣ Best Practices 

Prefer const for function expressions and arrow functions

Use arrow functions for callbacks and array methods

Use function declarations for hoisting and API functions

Keep functions small and single-purpose



---

8️⃣ Real-World Examples

🔹 Array Methods

const nums = [1,2,3];
const doubled = nums.map(n => n * 2);
console.log(doubled); // [2,4,6]

🔹 Event Listener

button.addEventListener("click", () => {
  console.log("Clicked!");
});

🔹 API Fetch

fetch(url)
  .then(res => res.json())
  .then(data => console.log(data));


---

9️⃣ Interview Questions 

1. Q: Difference between function declaration and expression?
A: Declaration → hoisted; Expression → not hoisted


2. Q: Arrow functions don’t have this?
A: ✅ They inherit this from the surrounding scope


3. Q: What is a closure?
A: Function remembering its lexical scope


4. Q: Can arrow functions be constructors?
A: ❌ No


5. Q: Difference between arguments and rest parameters?
A: arguments → array-like, all functions; ...rest → real array, modern JS




---

:

> “Arrow functions are great for callbacks and functional programming, but never use them for methods needing this or as constructors.”