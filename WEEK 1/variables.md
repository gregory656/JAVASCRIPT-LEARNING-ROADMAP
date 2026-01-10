📘 JavaScript Variables

1️⃣ What is a Variable?

A variable is a container used to store data values in a program so they can be reused and manipulated later.

Think of a variable like a labeled box that holds information.

let name = "Stephen";
let age = 20;

Here:

name stores a string

age stores a number





2️⃣ Why Variables Are Important

Variables help to:

Store user input

Hold data from APIs

Make code reusable

Avoid repeating values

Improve readability & maintainability


❌ Bad practice:

console.log("Stephen is 20 years old");

✅ Good practice:

let name = "Stephen";
let age = 20;

console.log(name + " is " + age + " years old");




3️⃣ Declaring Variables in JavaScript

JavaScript has three ways to declare variables:

Keyword	  Scope	  Reassignable	Hoisted	 Use Case

var	     Function	 Yes	    Yes	     Old code only
let	     Block	     Yes	    No	     Preferred
const	 Block	     No	        No	     Best for constants




4️⃣ var (Old & Not Recommended)

var city = "Nairobi";
city = "Mombasa"; // allowed

Problems with var

No block scope

Causes bugs in large apps

Can be redeclared


var x = 10;
var x = 20; // No error 

Avoid in modern JavaScript.



5️⃣ let (Recommended)

let score = 50;
score = 80; // allowed

Block Scope Example

if (true) {
  let message = "Hello";
}

// console.log(message);  Error

Use let when the value will change.




6️⃣ const (Best Practice)

const PI = 3.14;
// PI = 3.15 ❌ Error

Use const when the value should not change.

Important Note ⚠

Objects and arrays declared with const can still be modified.

const user = {
  name: "Stephen",
  age: 20
};

user.age = 21; // ✅ allowed

You cannot reassign the variable, but you can modify its contents.




7️⃣ Variable Naming Rules

 Valid Names

let firstName;
let total_marks;
let $price;
let isLoggedIn;

 Invalid Names

let 1name;     // cannot start with number
let my-name;  // hyphen not allowed
let let;      // reserved keyword

Best Practices

Use camelCase

Use meaningful names


let totalPrice; // ✅
let x;          // ❌ (not descriptive)




8️⃣ Variable Initialization vs Declaration

let count;        // declaration
count = 10;       // initialization

OR

let count = 10;   // both


---

9️⃣ Hoisting Explained (Simple)

var is hoisted

console.log(a); // undefined
var a = 5;

let and const are NOT hoisted

console.log(b); // ❌ Error
let b = 10;

 Always declare variables before using them.


---

🔟 Real-World Examples

Example 1: Login Status

let isLoggedIn = true;

if (isLoggedIn) {
  console.log("Welcome back!");
}

Example 2: Shopping Cart

const itemPrice = 500;
let quantity = 2;

let total = itemPrice * quantity;
console.log("Total:", total);


---

1️⃣1️⃣ Common Mistakes to Avoid 

Using var instead of let or const

Using unclear variable names

Reassigning const

Declaring variables globally unnecessarily



---

1️⃣2️⃣ When to Use What?

 Use const by default
 Use let if value changes
 Avoid var


---

1️⃣3️⃣ Interview Questions (Basic)

1. Difference between var, let, and const?


2. Can you change a const object?


3. What is block scope?


4. What is hoisting?


5. Why is var discouraged?






1️⃣4️⃣ Summary

Variables store data

JavaScript has var, let, const

Prefer const and let

Use clear naming

Understand scope & hoisting


VARIABLES 1 DONE!!