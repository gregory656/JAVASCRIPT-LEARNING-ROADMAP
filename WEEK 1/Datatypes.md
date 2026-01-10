
📘 JavaScript Data Types 

1️⃣ What are Data Types?

Data types define the kind of value a variable can hold and what operations can be performed on it.

JavaScript is a dynamically typed language → variable types are determined at runtime.

let x = 10;      // Number
x = "Hello";    // String (allowed)


---

2️⃣ Categories of Data Types

🔹 Primitive (Immutable)

Stored by value

1. String


2. Number


3. Boolean


4. Undefined


5. Null


6. Symbol (ES6)


7. BigInt



🔹 Non-Primitive (Reference)

Stored by reference

1. Object


2. Array


3. Function


4. Date, Map, Set, etc.




---

3️⃣ Primitive Data Types (Deep Dive)

🧵 String

Represents text

let name = "Stephen";
let greeting = `Hello ${name}`; // Template literal

Tricks

Use backticks (`) for interpolation

Strings are immutable


let str = "Hi";
str[0] = "h"; // ❌ No effect

Avoid

let s = new String("Hello"); // ❌ creates object


---

🔢 Number

Represents integers & decimals

let age = 21;
let price = 99.99;

Special values

Infinity
-Infinity
NaN

Tricks

Number("10") // 10
+"10"        // 10

Avoid floating point comparison

0.1 + 0.2 === 0.3 // false ❌


---

✅ Boolean

True or false

let isLoggedIn = true;

Falsy values

false, 0, "", null, undefined, NaN


---

❓ Undefined

Declared but not assigned

let x;
console.log(x); // undefined

Avoid

Manually assigning undefined



---

⛔ Null

Intentional empty value

let user = null;

⚠️ JavaScript bug

typeof null // "object"


---

🧿 Symbol (Advanced)

Unique identifiers

const id = Symbol("id");

Used in libraries & frameworks


---

🔢 BigInt

For very large integers

let big = 12345678901234567890n;


---

4️⃣ Non-Primitive Data Types

📦 Object

Key–value pairs

const user = {
  name: "Stephen",
  age: 21
};


---

📚 Array

Ordered list

const skills = ["JS", "React", "Node"];

Array is an object

typeof skills // "object"


---

🔧 Function

Callable object

function greet() {
  return "Hello";
}


---

5️⃣ typeof Operator

typeof "Hello"   // string
typeof 10        // number
typeof true      // boolean
typeof undefined // undefined
typeof null      // object ❌
typeof {}        // object
typeof []        // object
typeof function(){} // function


---

6️⃣ Value vs Reference (IMPORTANT )

Primitive

let a = 10;
let b = a;
b = 20;
console.log(a); // 10

Reference

let obj1 = { x: 1 };
let obj2 = obj1;
obj2.x = 5;
console.log(obj1.x); // 5


---

7️⃣ Type Coercion (Implicit Conversion)

"5" + 2   // "52"
"5" - 2   // 3
true + 1  // 2

Avoid

==   // loose equality ❌

Use

===  // strict equality ✅


---

8️⃣ Best Practices ✅

✔ Use const by default
✔ Use === instead of ==
✔ Check arrays properly

Array.isArray(arr)

✔ Explicit conversions

Number(value)
String(value)
Boolean(value)


---

9️⃣ Common Mistakes ❌

❌ Confusing null and undefined
❌ Modifying objects accidentally
❌ Using typeof for arrays
❌ Floating-point math assumptions


---

🔟 Interview Questions & Answers 🎯

Q1: Is JavaScript statically or dynamically typed?

✅ Dynamically typed


---

Q2: Difference between null and undefined?

null	undefined

Intentional empty	Not assigned
Developer sets	JS sets



---

Q3: Why typeof null === "object"?

✅ Historical JavaScript bug


---

Q4: Difference between primitive and reference types?

✅ Primitive → stored by value
✅ Reference → stored by reference


---

Q5: What is NaN?

✅ Not a Number – result of invalid math

Number("abc") // NaN


---

Q6: How do you clone an object?

const copy = { ...obj };


---

11️⃣ Where Data Types Are Used (Real-World)

React → props & state types

Node.js → API validation

Databases → data consistency

Cybersecurity → input validation



When interviewing:

> “JavaScript has 7 primitive data types and reference types. Understanding coercion and memory behavior is key to avoiding bugs.”

