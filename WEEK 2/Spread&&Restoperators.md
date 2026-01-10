📘 JavaScript Spread & Rest Operators

1️⃣ What are Spread & Rest Operators?

The spread (...) and rest (...) operators both use the same syntax (three dots), but they serve different purposes:

- Spread: Expands (spreads) elements of an array or properties of an object
- Rest: Collects remaining elements into an array or object

Introduced in ES6, they make working with arrays and objects more concise and readable.

Key Symbol: ...



---

2️⃣ Spread Operator (...)

Used to "spread" out elements or properties.

🔹 With Arrays

const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const combined = [...arr1, ...arr2]; // [1,2,3,4,5,6]

🔹 Copying Arrays

const original = [1, 2, 3];
const copy = [...original]; // [1,2,3] (shallow copy)

🔹 Adding Elements

const nums = [1, 2, 3];
const withMore = [0, ...nums, 4]; // [0,1,2,3,4]

🔹 Function Calls

function sum(a, b, c) {
  return a + b + c;
}
const nums = [1, 2, 3];
console.log(sum(...nums)); // 6

🔹 With Objects

const obj1 = { a: 1, b: 2 };
const obj2 = { c: 3, d: 4 };
const merged = { ...obj1, ...obj2 }; // {a:1,b:2,c:3,d:4}

🔹 Cloning Objects

const user = { name: "Stephen", age: 21 };
const clone = { ...user }; // shallow copy

🔹 Overriding Properties

const defaults = { theme: "light", lang: "en" };
const config = { ...defaults, theme: "dark" }; // {theme:"dark", lang:"en"}



---

3️⃣ Rest Operator (...)

Used to "collect" remaining elements into an array or object.

🔹 Function Parameters

function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}
console.log(sum(1, 2, 3, 4)); // 10

🔹 Destructuring Arrays

const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first);  // 1
console.log(second); // 2
console.log(rest);   // [3,4,5]

🔹 Destructuring Objects

const { name, age, ...others } = { name: "Stephen", age: 21, city: "Nairobi", country: "Kenya" };
console.log(name);   // "Stephen"
console.log(others); // {city: "Nairobi", country: "Kenya"}

🔹 Advanced: Rest in Arrow Functions

const multiply = (multiplier, ...nums) => nums.map(n => n * multiplier);
console.log(multiply(2, 1, 2, 3)); // [2,4,6]



---

4️⃣ Spread vs Rest: Key Differences

Feature	Spread	Rest

Purpose	Expands/Spreads	Collects/Gathers
Use Case	Arrays/Objects in calls	Parameters/Destructuring
Position	Anywhere in array/object	End of parameters/destructure
Syntax	...array	...rest



---

5️⃣ Common Use Cases

🔹 Array Manipulation

const arr = [1, 2, 3];
const doubled = [...arr].map(n => n * 2); // [2,4,6]

🔹 Function Composition

const add = (a, b) => a + b;
const numbers = [5, 10];
console.log(add(...numbers)); // 15

🔹 Object Merging (React/Configs)

const user = { name: "Stephen" };
const details = { age: 21, city: "Nairobi" };
const profile = { ...user, ...details }; // merged object

🔹 Removing Duplicates

const arr = [1, 2, 2, 3, 3, 4];
const unique = [...new Set(arr)]; // [1,2,3,4]

🔹 String to Array

const str = "hello";
const chars = [...str]; // ["h","e","l","l","o"]



---

6️⃣ Best Practices ✅

✔ Use spread for shallow copying arrays/objects
✔ Prefer rest in function parameters over arguments
✔ Combine with destructuring for clean code
✔ Remember: spread creates shallow copies
✔ Use rest at the end of destructuring

Avoid

❌ Deep nesting spreads (performance)
❌ Using spread on non-iterables
❌ Forgetting rest position (must be last)



---

7️⃣ Common Mistakes ❌

❌ Confusing spread and rest

function wrong(...args, last) {} // ❌ SyntaxError

✅ function correct(last, ...args) {}

❌ Shallow copy issues with nested objects

const obj = { nested: { value: 1 } };
const copy = { ...obj };
copy.nested.value = 2; // affects original

❌ Using spread on objects in function calls (only arrays)

func(...obj) // ❌ TypeError

✅ func(...Object.values(obj))



---

8️⃣ Performance Considerations

Spread creates new arrays/objects → memory usage

For large data, consider alternatives:

- Array.concat() instead of spread for arrays
- Object.assign() for objects (though spread is more readable)

But readability often > micro-optimizations



---

9️⃣ Real-World Examples

🔹 React Props

const Component = ({ className, ...props }) => (
  <div className={`default ${className}`} {...props} />
);

🔹 API Parameters

const fetchData = (url, ...params) => {
  const query = params.join('&');
  return fetch(`${url}?${query}`);
};

🔹 Redux Actions

const updateUser = (id, updates) => ({
  type: 'UPDATE_USER',
  payload: { id, ...updates }
});



---

🔟 Interview Questions & Answers 🎯

Q1: Difference between spread and rest?

Spread expands, rest collects. Same syntax, different context.

Q2: Does spread create deep copies?

No, shallow copies. Use libraries for deep cloning.

Q3: Can you use rest in object destructuring?

Yes, ES9 feature.

Q4: What happens with spread on strings?

Converts to array of characters.

Q5: Performance of spread vs traditional methods?

Spread is syntactic sugar, similar performance.

Q6: Can spread be used with Sets/Maps?

Yes, they are iterables.

Q7: Rest parameters vs arguments object?

Rest is real array, arguments is array-like. Prefer rest.



---

11️⃣ Summary

Spread & Rest make JavaScript more functional and readable.

Spread: Expand arrays/objects

Rest: Collect remaining items

Master them for modern JS development!

---

> "Spread and rest operators are powerful tools for handling collections, but remember they create shallow copies and should be used mindfully in performance-critical code."