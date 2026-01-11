# JavaScript

---

## 1. What is JavaScript? and its features?

> JavaScript is a high-level, interpreted, client-side scripting language used to create interactive effects within web browsers

<details>
</summary>Term:</summary>

- High-level: You write code in a language that looks like English (e.g., if, else, function), rather than machine code (1s and 0s) that the computer understands directly. You don't have to manage computer memory manually.
- Interpreted: The browser reads and executes the code line-by-line as it runs. You don't need to "compile" (convert) it into a separate file before running it, unlike languages like C++ or Java.
- Client-side: The code runs on the user's computer (in their browser), not on the website's server. This makes things happen instantly for the user.
- Scripting language: A language designed to automate tasks or control other software (like a browser), usually easier to learn than full programming languages like C++.

</details>

### Explanation

Think of a webpage like a house

- HTML is the structure (walls, doors, layout).
- CSS is the decoration (paint color, carpet style).
- JavaScript is the electricity and plumbing (what makes the lights turn on, the water run, and the garage door open).

Without JavaScript, a website is just a static poster. With JavaScript, the website can "think" and react—like checking if your password is strong enough, playing a video when you click a button, or updating a news feed without reloading the page.

### Key features (in simple words)

- Runs everywhere: All modern browsers and Node.js understand it; no install needed.
- Event-driven: Listens to clicks, key presses, scroll, network responses.
- Dynamic typing: Variables can hold any type; flexible but needs careful checks.
- First-class functions: Functions behave like values; you can pass them around.
- Asynchronous support: Promises, async/await, event loop handle slow tasks.
- Huge ecosystem: NPM packages, frameworks (React, Vue, Angular), tooling.

### Use Cases

- Interactive Forms: Checking if a user entered a valid email address before they hit "submit."
- Web Applications: Building complex apps like Gmail, Google Maps, or Trello that feel like desktop software.
- Dynamic Content: Loading new Instagram posts as you scroll down without refreshing the page.
- Game Development: Creating games that run directly in the browser (e.g., using engines like Phaser.js).
- Server-Side Development: Using Node.js (a way to run JS outside the browser) to build the backend of websites.

---

## 2. Differentiate between JavaScript and Java

JavaScript and Java share a name but are different tools.

- JavaScript is a lightweight, interpreted scripting language mainly for web pages and Node.js. Java is a compiled, class-based programming language for many platforms (web backends, Android, desktop).
- JS is dynamically typed. Java is statically typed.
- JS runs in browsers and Node.js without a compiler step. Java code is compiled to bytecode and runs on the JVM.
- JS shines in front-end interactivity and quick prototyping. Java shines in large, strongly typed systems like banking apps and Android apps.

<details>
<summary>Term:</summary>

- dynamically types: You don't need to specify the data type. The computer figures it out while the code runs. A variable can hold a number now and text later.
- statically typed: You must tell the computer exactly what kind of data a variable holds (e.g., number, text) when you create it. You cannot change it later.

</details>

---

## 3. What is ES6? and What is its long form?

ES6 stands for ECMAScript 2015. It is the sixth edition of the ECMAScript standard, adding modern language features.

- Adds: let/const, arrow functions, template literals, classes, default/rest/spread, destructuring, promises, modules.

---

## 4. What are various types of scopes in JavaScript?

- Global scope: Visible everywhere (avoid polluting it).
- Function scope: Variables declared with `var` inside a function live only in that function.
- Block scope: Variables declared with `let` or `const` inside `{}` (if/for/while) live only in that block.
- Module scope: In ES modules, everything is local to the file unless exported.

---

## 5. What is hoisting?

Hoisting is JavaScript's behavior of moving declarations to the top of their scope during compilation.

- `var` declarations hoist and initialize as `undefined`, so you can access them before the line (but value is undefined).
- `let` and `const` declarations hoist but stay uninitialized in the temporal dead zone until their line runs; accessing early throws an error.
- Function declarations hoist fully, so you can call them before their definition.

---

## 6. What is the difference between `var`, `let`, and `const`? why over others?

- `var`: Function-scoped, hoisted with undefined, can be redeclared. Avoid in new code because scope can leak.
- `let`: Block-scoped, not usable before declaration (temporal dead zone), can be reassigned, cannot be redeclared in the same scope.
- `const`: Block-scoped, must be initialized once, cannot be reassigned (but object contents can change).

Use `const` by default, switch to `let` if you need to reassign, avoid `var` to prevent accidental scope issues.

Example:

```js
// const: value never reassigned
const apiUrl = 'https://example.com/data';

// let: value changes
let count = 0;
count += 1;

// var: function-scoped (legacy)
function oldWay() {
  if (true) {
    var x = 10; // x leaks to the whole function
  }
  console.log(x); // 10
}
```

---

## 7. What are data types in JavaScript?

- Primitive: string, number, boolean, null, undefined, symbol, bigint.
- Non-primitive: objects (arrays, functions, dates, regex, plain objects, etc.).

Check with `typeof` and `Array.isArray()` for arrays.

---

## 8. What is the use of typeof operator?

`typeof` returns a string describing the type of a value at runtime.

```js
typeof 'hi'; // 'string'
typeof 10; // 'number'
typeof true; // 'boolean'
typeof undefined; // 'undefined'
typeof null; // 'object' (quirk)
typeof []; // 'object' (use Array.isArray to detect arrays)
typeof (() => {}); // 'function'
```

---

## 9. What is type coercion?

Automatic conversion from one type to another during operations.

- Example: `'5' * 2` becomes `10` (string coerced to number). `'5' + 2` becomes `'52'` (number coerced to string).
- Prefer explicit conversion(type casting): `Number(str)`, `String(num)`, `Boolean(val)`.

- **Implicit Coercion**: Happens automatically during operations.
- **Explicit Coercion**: Done manually by the developer using functions.

---

## 10. What is the difference between `==` and `===`?

- `==` (loose equality): Compares after type coercion. Can give surprising matches, e.g., `0 == false` is true.
- `===` (strict equality): Compares value and type. Safer default. `0 === false` is false.

Use `===` and `!==` almost always.

---

## 11. What is the difference between `null` and `undefined`?

- `undefined`: A variable was declared but not assigned, or a missing property/parameter.
- `null`: An intentional empty value set by the developer to mean "no value".

---

## 12. What are types of functions?

- Function declaration: `function add(a, b) { return a + b; }`
- Function expression: `const add = function (a, b) { return a + b; };`
- Arrow function: `const add = (a, b) => a + b;`
- Anonymous function: A function without a name, often used inline. (e.g., `setTimeout(function() { ... }, 1000);`)
- Higher-order function: A function that takes/returns other functions (e.g., `map`).
- Constructor function: Used with `new` to create objects (pre-class style). (e.g., `function Person(name) { this.name = name; }`)

---

## 13. What is a function expression vs function declaration?

- Declaration: `function greet() {}` is hoisted, so you can call it before its line.
- Expression: `const greet = function () {};` is assigned to a variable; not callable before its line because the variable must be initialized first.

---

## 14. What are arrow functions?

Shorter syntax for functions, introduced in ES6.

- No own `this`, `arguments`, `super`, or `new.target`; they capture `this` from the surrounding scope.
- Great for callbacks; avoid as methods when you need dynamic `this`.

Example:

```js
const nums = [1, 2, 3];
const doubled = nums.map(n => n * 2);
```

---

## 15. What is an IIFE (Immediately Invoked Function Expression)?

A function that runs as soon as it is defined. Helps create a private scope.

```js
(function () {
  const secret = 42;
  console.log('Runs immediately');
})();
```

---

## 16. What is callback function?

A Callback Function is a function that is passed as an argument (parameter) to another function, and is executed (called back) after the first function has finished its task.

### Explanation of Callback Function

Imagine you are calling a pizza place to order delivery.

- Standard Function: You order the pizza.
- The Problem: You don't want to stay on the line holding the phone for 30 minutes while they bake it.
- The Callback: You give them your phone number and say, "Call me back when the pizza is at my door."
- The Execution: You hang up and go watch TV (do other tasks). When the pizza arrives, they call your number (execute the callback), and you go eat.

In programming, instead of blocking the code while waiting for a file to load or a database to respond, we give the computer a function and say, "Run this when you are done loading."

<details>
<summary>Terminologies:</summary>

- Higher-Order Function: The "Main Function" that accepts your callback as a parameter. It is the boss function that decides when to run your callback.
- Asynchronous: Things happening independently of the main program flow. A task that starts now but finishes later (like downloading a file) without freezing the screen. Callbacks are the primary way to handle this.
- Synchronous Callback: A callback that runs immediately, blocking the code until it finishes (e.g., standard array loops).

</details>

```js
console.log("1. Start ordering pizza");

setTimeout(function() {
    // This runs after 2 seconds (2000ms), simulating a delay
    console.log("3. Pizza is here! (Callback Executed)");
}, 2000);

console.log("2. Watch TV while waiting");
```

### Use Cases of Callback Functions

- Event Listeners: Running code only when a user clicks a button (button.addEventListener('click', callback)).
- Timers: Running code after a specific delay (setTimeout).
- API Requests: Fetching user data from a server and running a function only after the data arrives (so you don't display a blank screen).
- File I/O (Node.js): Reading a large file from the hard drive and processing it only when reading is complete.

---

## 17. What is callback hell?

Callback Hell is a phenomenon in JavaScript where multiple callbacks are nested inside each other to ensure tasks happen in a specific order. It creates a code structure that grows horizontally (shaped like a pyramid or arrow) making the code difficult to read, maintain, and debug. It is formally known as the "Pyramid of Doom."

### Eplanation of Callback Hell

Imagine you want to cook a fancy dinner, but you have very strict rules:

- You cannot cut vegetables until you buy them.
- You cannot turn on the stove until the vegetables are cut.
- You cannot serve the food until the stove is off.

In "Callback Hell," you don't just write a list of instructions. You write it like this:

- "Go to the store. IF you successfully buy food, THEN go home and cut it. IF you successfully cut it, THEN turn on the stove. IF the stove is on, THEN cook..."

You end up with a giant, deep hole of instructions inside instructions. If something goes wrong in the middle (e.g., you forgot your wallet at the store), it is very hard to find exactly where the error happened in that mess.

<details>
<summary>Terminologies:</summary>

- Pyramid of Doom: A slang term for the visual shape of the code. Because each callback is indented (moved to the right), the code looks like a sideways pyramid >.
- Inversion of Control: This is a deeper problem with callbacks. You are handing over control of your code to a third-party function (like an API). You trust them to call your callback at the right time. In callback hell, this trust is multiplied, increasing the risk of bugs.
- Sequential Execution: Tasks that must happen one after another (Step A, then Step B, then Step C). This is the main cause of callback hell because you have to nest B inside A, and C inside B.

</details>

```js
// AVOID THIS PATTERN
getUser(userId, function(user) {
    getPosts(user.id, function(posts) {
        getComments(posts[0].id, function(comments) {
            updateUI(comments, function() {
                console.log("Finally done!");
            });
        });
    });
});
```

Fix with promises or async/await.

---

## 18. What are promises?

A Promise is a JavaScript object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. It acts as a placeholder for a value that is not yet known when the promise is created.

### Explanation of Promises

Think of a Promise literally like a receipt at a burger restaurant.

- Ordering (Pending): You pay for a burger. The cashier gives you a receipt (The Promise). The burger isn't ready yet, so the receipt is just a placeholder.
- Waiting: You hold onto the receipt. You can't eat the receipt, but it guarantees you get a burger eventually.
- Completion:
  - Success (Resolved): The chef calls your number. You exchange the receipt for the burger. (The promise is fulfilled).
  - Failure (Rejected): The chef comes out and says, "Sorry, we ran out of buns." You get a refund or an apology. (The promise is rejected).

In code, instead of blocking the computer while it downloads a file, the computer gives you a "Promise" object and says, "Keep working. I'll update this object when the download finishes."

<details>
<summary>Terminologies:</summary>

- Pending: The initial state. The operation (like downloading a file) has started but hasn't finished yet.
- Fulfilled (Resolved): The operation completed successfully, and the Promise now holds the resulting data (e.g., the downloaded file).
- Rejected: The operation failed (e.g., no internet connection), and the Promise now holds an Error reason.
- .then(): A method you attach to a Promise. It means "Run this code ONLY if the promise succeeds."
- .catch(): A method used for error handling. It means "Run this code if the promise fails."
- Executor Function: The function inside new Promise((resolve, reject) => { ... }) that contains the actual code to run (the network request, timer, etc.).

</details>

```js
// 1. Creating a Promise
const myPromise = new Promise((resolve, reject) => {
    let connectionSpeed = "Fast";
    
    if (connectionSpeed === "Fast") {
        // Successful scenario
        resolve("Success! Data downloaded."); 
    } else {
        // Failure scenario
        reject("Error! Connection too slow."); 
    }
});

// 2. Consuming the Promise (Using the receipt)
myPromise
    .then((message) => {
        // This runs ONLY if resolve() was called
        console.log("In .then(): " + message); 
    })
    .catch((error) => {
        // This runs ONLY if reject() was called
        console.log("In .catch(): " + error);
    });
```

### Use cases of Promises

- Fetching Data: Getting user info from an API (e.g., using fetch('<https://api.github.com/...>')).
- Waiting: Replacing setTimeout with a cleaner delay function.
- Device Access: requesting access to a user's webcam or microphone (the browser returns a Promise pending the user's "Allow" click).
- Multiple Tasks: Using Promise.all() to download 5 images at once and waiting until all of them are done before showing the gallery.

### Advantages of Promises over Callbacks

| Feature | Promises | Callbacks |
| ------- | -------- | --------- |
| Structure | Advantage: Chaining. You can attach `.then()` after `.then()` in a straight vertical line. No “Pyramid of Doom.” | Disadvantage: Deep nesting (Callback Hell) makes code hard to read. |
| Error Handling | Advantage: Centralized error handling. One `.catch()` at the end can catch errors from any step in the chain. | Disadvantage: You must manually write `if (err)` inside every single callback. |
| State | Advantage: A Promise is an object you can pass around. It saves its state (success/fail), so you can handle it even after the event happened. | Disadvantage: A callback is just a function call. Once it runs, the result is gone unless you saved it manually. |
| Cancellation | Disadvantage: Once a standard JS Promise starts, you generally cannot cancel it (though newer `AbortController` helps). | Advantage: Some callback implementations (like `clearTimeout`) are easy to cancel. |

---

## 19. What is a promise chain?

Promise Chaining is a technique in JavaScript used to perform multiple asynchronous tasks sequentially (one after another). It works because the .then() method of a Promise returns a new Promise automatically. This allows you to attach a subsequent .then() to the result of the previous one.

### Explanation of Promise Chaining

Think of a bucket brigade (a line of people passing buckets of water to put out a fire).

- Person A dips the bucket in the river (Task 1).
- Person A passes the full bucket to Person B.
- Person B takes that specific bucket and runs to the house (Task 2).
- Person B passes the empty bucket to Person C...

In Promise Chaining:

- Function 1 runs.
- It finishes and passes its "result" (the water) to the next .then().
- Function 2 starts only after it receives that result.
- If anyone drops the bucket (Error), the whole chain stops, and the "Manager" (the .catch() block at the end) handles the mess.

```js
function login(username) {
    return new Promise((resolve) => {
        setTimeout(() => resolve(`User_ID_123`), 1000);
    });
}

function getUserData(userId) {
    return new Promise((resolve) => {
        setTimeout(() => resolve(`${userId}: John Doe`), 1000);
    });
}

// THE CHAIN
login("johnny")
    .then((userId) => {
        console.log("1. Logged in. ID is: " + userId);
        return getUserData(userId); 
    })
    .then((data) => {
        console.log("2. Data received: " + data);
        return "Displaying Welcome Message";
    })
    .then((message) => {
        console.log("3. UI Update: " + message);
    })
    .catch((error) => {
        console.log("Something failed along the way: " + error);
    });
```

---

## 20. What is async/await?

Async/Await is a modern JavaScript feature (introduced in ES2017) that acts as "syntactic sugar" on top of Promises. It allows you to write asynchronous code that looks and behaves like synchronous (standard) code, making it much easier to read and maintain.

### Explanation of Async/Await

Remember the "Promise" explanation where you got a receipt for your burger?

- With Promises (.then): You get the receipt, and you have to write specific instructions on the back of the receipt saying, "When this turns into a burger, eat it."
- With Async/Await: You simply pause time.
  - You say: await getBurger().
  - The code literally stops at that line (inside that function only).
  - It waits until the burger is ready.
  - Once it's ready, the code moves to the next line, and you have the burger in your hand. No receipts, no callback functions, just a straight list of instructions.

It turns "Do A, then do B, then do C" into "Do A. (Wait). Do B. (Wait). Do C."

<details>
<summary>Terminologies:</summary>

- Syntactic Sugar: A feature that doesn't add new functionality to the language but makes existing functionality (Promises) "sweeter" (easier/cleaner) to use.
- async keyword: Putting this before a function tells JavaScript: "This function will handle asynchronous tasks and will always return a Promise automatically." You must mark a function as async to use await inside it.
- await keyword: This acts like a "Pause Button." It tells JavaScript: "Don't move to the next line until this Promise is finished." It extracts the value from the Promise (unwraps the burger from the receipt).
- Blocking vs. Non-blocking: Even though await looks like it freezes the program, it only pauses that specific function. The rest of the website (buttons, animations) keeps working fine.

</details>

```js
// OLD WAY
function getData() {
    fetch('https://api.example.com/user')
        .then(response => response.json())
        .then(data => console.log(data))
        .catch(error => console.log(error));
}

// NEW WAY
// 1. Mark function as async
async function getData() {
    try {
        // 2. "Pause" here until fetch is done
        const response = await fetch('https://api.example.com/user'); 
        
        // 3. "Pause" again until conversion is done
        const data = await response.json();
        
        console.log(data); // We have the data directly!
    } catch (error) {
        // Standard try/catch for errors (much cleaner)
        console.log("Something went wrong:", error);
    }
}
```

---

## 21. What is the difference between synchronous and asynchronous code?

- Synchronous: Tasks run one after another; a slow task blocks the rest.
- Asynchronous: Tasks start and let others continue; results handled later via callbacks, promises, or async/await.

---

## 22. What is the difference between `setTimeout` and `setInterval`?

- `setTimeout(fn, ms)`: Runs `fn` once after a delay.
- `setInterval(fn, ms)`: Runs `fn` repeatedly every `ms` until cleared.

Clear with `clearTimeout(id)` or `clearInterval(id)`.

---

## 23. What are closures? explain with real life example

A Closure is a feature in JavaScript where an inner function has access to the outer function's variables (its lexical scope), even after the outer function has finished executing.

In technical terms: "A closure is the combination of a function bundled together with references to its surrounding state (the lexical environment)."

### Explanation of Closures

The "Backpack" Analogy:

Imagine a function is like a student at school.

- The School (Outer Function): The school provides resources like books, pens, and a calculator (Variables).
- The Student (Inner Function): The student is inside the school and uses these resources.
- The Magic: When the school day ends, the school closes (The outer function finishes executing). usually, everything in the school would be locked away or thrown out.
- The Closure: However, this student carries a Backpack. Before leaving, they put the books and calculator into their backpack. Even though the school is closed, the student can still access those tools wherever they go next.

Real-Life Example: A Digital Counter Think of a person standing at a door counting people entering a club.

Even if the manager (Outer function) goes home, the person at the door (Inner function) remembers the current count in their head (Closure). They don't reset to zero just because the manager left.

<details>
<summary>Terminologies:</summary>

- Lexical Scope: "Lexical" means "where you write it." If you write a variable inside a function, that variable physically belongs there. The inner function can "see" it because it is physically written inside the same block of code.
- Encapsulation: Hiding information. Closures allow you to hide variables so that no one from the "outside" can mess with them directly. They can only use the specific tools (inner functions) you gave them.
- Scope Chain: The order in which the computer looks for a variable. (1. Look inside local function -> Look in the parent function -> 3. Look in the global window).

</details>

```js
function createCounter() {
    let count = 0; // This variable is "closed over" (protected)

    // This inner function is the Closure
    return function increment() {
        count++; 
        console.log("Current count: " + count);
    };
}

const myCounter = createCounter(); // createCounter finishes running here!

// Even though createCounter is done, 'myCounter' REMEMBERS the 'count' variable.
myCounter(); // Output: Current count: 1
myCounter(); // Output: Current count: 2
myCounter(); // Output: Current count: 3
```

---

## What is the event loop?

The event loop is the mechanism that lets JavaScript handle asynchronous tasks in a single thread.

- Call stack runs synchronous code.
- Web APIs/Node APIs handle timers, fetch, etc.
- Task queues (macro/micro) hold callbacks.
- The event loop moves ready callbacks from queues to the stack when it is empty.

---

## Explain fetch API

`fetch()` makes HTTP requests and returns a promise.

```js
fetch('https://api.example.com/items')
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

With async/await:

```js
async function load() {
  const res = await fetch('/data.json');
  if (!res.ok) throw new Error('Request failed');
  const data = await res.json();
  console.log(data);
}
```

---

## What is JSON? and how to used?

JSON (JavaScript Object Notation) is a lightweight text format for data exchange.

- Looks like JS objects but is just a string.
- Use `JSON.stringify(obj)` to convert an object to JSON string.
- Use `JSON.parse(str)` to convert a JSON string to an object.

---

## fetch() vs axios?

- Built-in vs library: `fetch` is native; Axios is an external library.
- Defaults: `fetch` only rejects on network errors; need to check `res.ok`. Axios rejects on non-2xx automatically.
- Data handling: `fetch` requires `res.json()`; Axios already parses JSON.
- Older browser support: Axios works with more legacy browsers; `fetch` may need a polyfill.
- Extras: Axios has interceptors, request cancellation, progress events; `fetch` is simpler.

---

## What is localStorage vs sessionStorage vs cookies?

- localStorage: Key-value strings, ~5-10MB, persists until cleared, same-origin.
- sessionStorage: Same as localStorage but cleared when tab closes.
- Cookies: Small (~4KB), sent to server on each request, can set expiry and flags (HttpOnly, Secure, SameSite).

Use local/sessionStorage for client-only data; use cookies for server communication and auth tokens (with security flags).

---

## What is DOM?

Document Object Model: A tree representation of the HTML page. JavaScript can read and change it to update the UI.

---

## What is getElementById() vs querySelector()?

- `getElementById('id')`: Returns the single element with that id; fast, id-only.
- `querySelector('css')`: Returns the first element matching a CSS selector; flexible (classes, attributes, nesting).

---

## What is event and how to handle events in JavaScript?

An event is an action the browser reports (click, input, load, keydown).

Handle with listeners:

```js
const btn = document.getElementById('save');
btn.addEventListener('click', event => {
  event.preventDefault();
  console.log('Clicked');
});
```

---

## What is event bubbling? event capturing? event propagation?

- Capturing: Event moves from window -> document -> parent -> target.
- Bubbling: Event moves from target -> parents -> document -> window.
- Propagation: The overall travel path (capturing then bubbling). You can stop it with `event.stopPropagation()`.

Use event delegation by listening on a parent and handling child events during bubbling.

---

## What is the difference between `map`, `filter`, and `reduce`?

- `map`: Transforms each item, returns new array of same length.
- `filter`: Keeps items that pass a condition, returns new array possibly shorter.
- `reduce`: Combines items into a single value (number, object, array, etc.).

Example:

```js
const nums = [1, 2, 3, 4];
const doubled = nums.map(n => n * 2); // [2, 4, 6, 8]
const evens = nums.filter(n => n % 2 === 0); // [2, 4]
const sum = nums.reduce((acc, n) => acc + n, 0); // 10
```

---

## What is destructuring?

Short syntax to pull values from arrays/objects into variables.

```js
const user = { name: 'Sam', age: 30 };
const { name, age } = user; // name = 'Sam', age = 30

const nums = [10, 20, 30];
const [first, , third] = nums; // first = 10, third = 30
```

---

## What is `this` keyword? and its different contexts?

`this` refers to the current execution context.

- Global (non-strict): `this` is `window`/`globalThis`.
- In a method call: `this` is the object before the dot.
- In event handlers: `this` is the element (unless an arrow function is used).
- In functions (strict mode): `this` is `undefined` if not bound.
- In arrow functions: `this` is taken from the surrounding scope; it does not bind its own.
- With `call/apply/bind`: You can set `this` manually.

---

## What are comments?

- Single-line: `// text`
- Multi-line: `/* text */`

Use comments to explain why, not to restate obvious code.

---

## Can we use JavaScript for backend development? How?

Yes, with Node.js (runs JS outside the browser).

- Use frameworks like Express, NestJS, Koa.
- Handle HTTP requests, databases, authentication, real-time sockets.

---

## What are different types of loops?

- `for` (classic counter)
- `while`
- `do...while`
- `for...of` (iterate iterable values)
- `for...in` (iterate object keys; avoid on arrays)
- Array helpers like `forEach` (not a loop keyword but common)

- definition
- explaination - Explain concepts in your own words in simple language(not textbook definitions)
- terminologies(meaning, if needed for hard word)
- code - comments -> expand to code (if needed)
- examples(if needed)
- use cases(if needed)
- advantages and disadvantages over other alternatives(is needed)

## Just to know

- **Template literals** - Backtick strings that allow `${}` interpolation and multiline text.
- **modules** - Files that export/import values so code stays organized and scoped.
- **event delegation** - Attach one listener to a parent to handle events from many child elements.
- **call vs apply vs bind** - All set `this`; `call`/`apply` invoke immediately (`apply` takes args array), `bind` returns a new function with fixed `this`.
- **Node.js** - Runtime to run JavaScript outside the browser, built on Chrome's V8 engine.
- **higher-order functions** - Functions that take or return other functions (e.g., `map`, `filter`).
- **event bubbling and event capturing** - Two phases of event travel: down (capturing) then up (bubbling).
- **spread operator and rest parameter** - `...` to expand arrays/objects or gather function arguments.
- **array and its methods** - Common helpers: `push`, `pop`, `map`, `filter`, `reduce`, `find`, `some`, `every`, `includes`.
- **object and its methods** - `Object.keys`, `Object.values`, `Object.entries`, `Object.assign`, structured cloning via spread.

## Checklist for readyness

- Explain var, let, const with example
- Write a function (normal + arrow)
- Use map, filter, reduce
- Explain closure in simple words
- Handle a DOM event
- Explain Promise & async/await
- Solve 2–3 basic JS programs live

> Freshers are NOT rejected for lack of knowledge They are rejected for lack of clarity & confidence

- **i.e.** - You don’t need advanced JS. You need clear basics + practice.

## Extra Questions

- What are prototypes? - The mechanism objects use to share properties and methods; every object links to a prototype.
- What is a JavaScript engine? - The program (like V8, SpiderMonkey) that parses, optimizes, and runs JS code.
- What is a service worker? - A background script that can intercept network requests, cache assets, and enable offline behavior.
- What is memoization? - Caching function results so repeated calls with the same input return fast without recalculation.
- What are generators in JavaScript? - Functions written with `function*` that can pause and resume, yielding multiple values lazily.
- How to select elements in the DOM? - Use `getElementById`, `querySelector`, `querySelectorAll`, `getElementsByClassName`, etc.
- What is an event? - A browser-reported action (click, input, load, keydown) that code can listen to and handle.# JavaScript

---
