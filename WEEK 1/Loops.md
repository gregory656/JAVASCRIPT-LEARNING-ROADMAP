📘 JavaScript Loops 

1️⃣ What are Loops?

Loops are used to execute a block of code repeatedly until a condition is met.

Use loops when:

Iterating over arrays

Processing objects

Repeating tasks

Handling data from APIs



---

2️⃣ Types of Loops in JavaScript

1. for


2. while


3. do...while


4. for...of


5. for...in


6. Loop control (break, continue)


7. Array iteration methods (modern alternative)




---

3️⃣ for Loop (Most Common)

for (let i = 0; i < 5; i++) {
  console.log(i);
}

Structure

for (initialization; condition; increment) {}

Use cases

When you know the number of iterations

Index-based loops



---

4️⃣ while Loop

let i = 0;

while (i < 5) {
  console.log(i);
  i++;
}

Use cases

When number of iterations is unknown

Condition-controlled loops


⚠️ Risk

Infinite loop if condition never becomes false



---

5️⃣ do...while Loop

let i = 0;

do {
  console.log(i);
  i++;
} while (i < 5);

✔ Executes at least once, even if condition is false


---

6️⃣ for...of Loop (Modern & Clean)

Used for iterable values

const skills = ["JS", "React", "Node"];

for (const skill of skills) {
  console.log(skill);
}

Works with

Arrays

Strings

Maps

Sets


❌ Does NOT work with plain objects


---

7️⃣ for...in Loop (Objects)

Iterates over keys (properties)

const user = {
  name: "Stephen",
  age: 21
};

for (const key in user) {
  console.log(key, user[key]);
}

⚠️ Avoid using for...in with arrays


---

8️⃣ Loop Control Keywords

🔹 break

Stops the loop completely

for (let i = 0; i < 10; i++) {
  if (i === 5) break;
}


---

🔹 continue

Skips current iteration

for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i);
}


---

9️⃣ Nested Loops

for (let i = 1; i <= 3; i++) {
  for (let j = 1; j <= 3; j++) {
    console.log(i, j);
  }
}

⚠️ Performance cost → O(n²)


---

🔟 Looping Over Objects & Arrays (Comparison)

Loop	Best For	Avoid When

for	Index needed	Code readability
while	Unknown count	Simple iteration
for...of	Arrays	Objects
for...in	Objects	Arrays
map	Transform arrays	Side effects
forEach	Side effects	Breaking loops



---

11️⃣ Modern Array Iteration (Preferred)

🔹 forEach

arr.forEach(item => console.log(item));

❌ Cannot use break


---

🔹 map

const doubled = arr.map(n => n * 2);

✔ Returns new array


---

🔹 filter

const evens = arr.filter(n => n % 2 === 0);


---

🔹 reduce

const sum = arr.reduce((a, b) => a + b, 0);


---

12️⃣ Common Mistakes ❌

❌ Infinite loops
❌ Using for...in on arrays
❌ Forgetting let / const in loops
❌ Mutating arrays while looping
❌ Using map without returning


---

13️⃣ Interview Traps ⚠️

Q1: Difference between for...of and for...in?

for...of → values

for...in → keys



---

Q2: Can you break a forEach loop?

❌ No


---

Q3: Which loop is fastest?

✅ Traditional for (usually), but readability > micro-optimization


---

Q4: When use while vs for?

for → known iterations

while → unknown iterations



---

14️⃣ Real-World Examples

Looping API data

users.forEach(user => {
  console.log(user.name);
});

Validate inputs

for (const value of inputs) {
  if (!value) return false;
}


---

15️⃣ Best Practices 

✔ Prefer for...of for arrays
✔ Prefer array methods (map, filter)
✔ Avoid deep nesting
✔ Always check loop exit condition
✔ Keep loops small & readable


---

---
 (Interview Gold)

> “Modern JavaScript favors for...of and array methods for readability, but knowing classic loops is essential for performance-critical logic.”




---
