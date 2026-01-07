📘 JavaScript Objects 

1️⃣ What is an Object?

An object is a collection of key–value pairs (properties).

const user = {
  name: "Stephen",
  age: 21,
  isStudent: true
};

Key points

Keys → strings or symbols

Values → any data type (even functions)

Objects are reference types



---

2️⃣ Creating Objects

🔹 Object Literal (Most Common)

const car = {
  brand: "Toyota",
  year: 2022
};


---

🔹 Using new Object()

const person = new Object();
person.name = "John";

❌ Avoid (verbose, unnecessary)


---

🔹 Constructor Function

function User(name, age) {
  this.name = name;
  this.age = age;
}

const u1 = new User("Stephen", 21);

⚠️ Before ES6 classes


---

🔹 Object.create()

const proto = { role: "admin" };
const user = Object.create(proto);
user.name = "Stephen";

Used for prototypes


---

3️⃣ Accessing Object Properties

🔹 Dot Notation

user.name;

🔹 Bracket Notation

user["age"];

Use bracket when

Property name has spaces

Dynamic keys


const key = "email";
user[key] = "test@mail.com";


---

4️⃣ Modifying Objects

Add

user.country = "Kenya";

Update

user.age = 22;

Delete

delete user.isStudent;


---

5️⃣ Methods (Functions in Objects)

const user = {
  name: "Stephen",
  greet() {
    return `Hello, ${this.name}`;
  }
};

⚠️ Avoid arrow functions as methods

greet: () => this.name // ❌ undefined


---

6️⃣ this Keyword (VERY IMPORTANT )

const user = {
  name: "Stephen",
  show() {
    console.log(this.name);
  }
};

this → object calling the method

Arrow functions ❌ do not bind this



---

7️⃣ Object Destructuring

const user = { name: "Stephen", age: 21 };

const { name, age } = user;

Rename

const { name: userName } = user;

Default values

const { country = "Kenya" } = user;


---

8️⃣ Spread Operator (...)

Clone Object (Shallow Copy)

const copy = { ...user };

Merge Objects

const a = { x: 1 };
const b = { y: 2 };
const merged = { ...a, ...b };


---

9️⃣ Object Reference vs Copy (INTERVIEW )

const obj1 = { a: 1 };
const obj2 = obj1;

obj2.a = 5;
console.log(obj1.a); // 5 ❌

Correct Copy

const obj2 = { ...obj1 };


---

🔟 Deep Copy (Important!)

❌ Wrong (Nested objects break)

const copy = { ...obj };

✅ JSON method

const deepCopy = JSON.parse(JSON.stringify(obj));

⚠️ Loses functions, undefined, Date


---

11️⃣ Object Methods (Must Know)

Object.keys(obj);    // array of keys
Object.values(obj); // array of values
Object.entries(obj); // key-value pairs

Looping

for (let key in obj) {
  console.log(key, obj[key]);
}


---

12️⃣ Checking Properties

"user" in obj;
obj.hasOwnProperty("name");


---

13️⃣ Object Comparison (TRICK ⚠️)

{} === {} // false ❌

Objects compare by reference, not value.

Workaround

JSON.stringify(obj1) === JSON.stringify(obj2);


---

14️⃣ Freezing & Sealing Objects

🔹 Object.freeze()

Object.freeze(user);

❌ Cannot add, delete, modify


🔹 Object.seal()

Object.seal(user);

✅ Modify

❌ Add / Delete



---

15️⃣ Real-World Use Cases

User profiles

API responses

Config files

Database records

React props & state



---

16️⃣ Common Mistakes ❌

❌ Using arrow functions as methods
❌ Mutating objects accidentally
❌ Shallow copying nested objects
❌ Comparing objects with ===


---

17️⃣ Interview Questions 

Q1: Is object primitive or reference?

✅ Reference type


---

Q2: Difference between dot and bracket notation?

✅ Bracket allows dynamic keys


---

Q3: How do you clone an object?

const copy = { ...obj };


---

Q4: What is shallow vs deep copy?

Shallow → copies reference

Deep → fully independent copy



---

Q5: Why this fails in arrow functions?

✅ Arrow functions inherit this from outer scope


---
---

  (Interview Gold)

> “Objects in JavaScript are reference types, so understanding copying, mutation, and this is critical for writing bug-free applications.”


