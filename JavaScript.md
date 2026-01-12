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

## 24. What is the event loop?

The Event Loop is a mechanism in JavaScript that handles asynchronous operations. It constantly monitors the Call Stack (where code runs) and the Callback Queue (where waiting tasks sit). If the Call Stack is empty, the Event Loop takes the first task from the Queue and pushes it onto the Stack to be executed.

### Explanation of Event Loop

Think of a Busy Restaurant with only One Chef (JavaScript Engine).

1. The Chef (Call Stack): Can only cook one dish at a time.
2. The Orders (Code): Most orders are quick (chopping onions = console.log). The Chef does these immediately.
3. The Special Orders (Asynchronous tasks): Some orders take a long time, like baking a cake (Downloading a file).
    - Instead of standing there staring at the oven for 30 minutes, the Chef puts the cake in the oven (Web API) and moves on to the next customer's order immediately.
4. The Bell (Callback Queue): When the cake is done, the oven "dings" and puts the cake on the counter.
5. The Waiter (Event Loop): The waiter's only job is to watch the Chef.
    - Rule: The Waiter cannot interrupt the Chef.
    - If the Chef is busy cooking, the cake waits on the counter.
    - The moment the Chef is free (Stack is empty), the Waiter hands them the cake to finish plating (executes the callback).

<details>
<summary>Terminologies:</details>

- Single-Threaded: JavaScript can literally only do one thing at a specific micro-second. It doesn't have multiple brains.
- Call Stack: The place where the code is actually running right now. It follows "Last In, First Out." If this is not empty, nothing else can happen.
- Web APIs: Tools provided by the Browser (not JavaScript itself) to handle heavy lifting like timers (setTimeout), HTTP requests (fetch), or DOM events. They run in the background.
- Callback Queue (Task Queue): A waiting line for functions (callbacks) that are ready to run but are waiting for the Call Stack to be free.
- Microtask Queue: A "VIP Line" for Promises. Tasks here get processed before the standard Callback Queue.

```JavaScript
console.log("1. Start");

// This goes to Web API -> Queue -> Waits for Stack to clear
setTimeout(() => {
    console.log("2. Timeout (0 seconds)");
}, 0);

// This goes to Microtask Queue (VIP) -> Runs before Timeout
Promise.resolve().then(() => {
    console.log("3. Promise");
});

console.log("4. End");

/* OUTPUT ORDER:
1. Start
4. End
3. Promise  (VIP Queue runs first)
2. Timeout (0 seconds) (Standard Queue runs last)
*/
```

### Use Cases of Event loop

- Non-blocking I/O: The server can handle thousands of requests (like a chat app) without freezing, because it doesn't wait for one message to send before receiving the next.
- Smooth UI: Allows the browser to re-render animations and respond to clicks even while waiting for data from a server.
- Delayed Execution: Scheduling tasks to run slightly later to prioritize critical UI updates first.

---

## 25. Explain fetch API

The Fetch API is a modern interface in JavaScript used to make HTTP requests to servers (like requesting data or sending a form). It is built into the browser and uses Promises to handle results, providing a more powerful and flexible feature set than the older XMLHttpRequest.

### Explaination of fetch API

Think of Fetch as a Messenger Dog.

1. The Command: You tell the dog, "Go to this address (URL) and get me the newspaper."
2. The Journey (Async): The dog runs off. You don't freeze; you keep drinking your coffee.
3. The Return (Promise Resolves): The dog comes back.
    - Important: The dog comes back with a "package" (The Response Object). You can't read the news yet because it's wrapped up.
4. Unwrapping (Response.json()): You have to perform a second step: unwrap the package to actually read the text inside.

<details>
<summary>Terminologies:</summary>

- Endpoint: The specific URL you are sending the Fetch messenger to (e.g., <https://api.google.com/users>).
- Method (GET, POST, etc.): The type of action you want to do.
  - GET: "Go get this data." (Default)
  - POST: "Go give this data to the server" (like submitting a login form).
- Headers: Extra information stamped on the envelope. Examples: "This is JSON data" or "Here is my security pass (token)."
- Body: The actual content inside the envelope (only used when sending data, like in a POST request).
- Stream: The way Fetch receives data. It doesn't download the whole file at once; it opens a "flow" of data. This is why you need to call .json() or .text() to read it completely.

</details>

```js
// GET
fetch('https://api.example.com/data') // 1. Go to URL
  .then(response => {
     // 2. Check if the server answered "OK"
     if (!response.ok) {
       throw new Error('Network response was not ok');
     }
     // 3. Unwrap the package (convert stream to JSON)
     return response.json(); 
  })
  .then(data => {
     // 4. Use the data
     console.log(data); 
  })
  .catch(error => {
     console.error('There was a problem:', error);
  });


// POST
fetch('https://api.example.com/login', {
  method: 'POST', // We are sending data
  headers: {
    'Content-Type': 'application/json' // Tell server we are sending JSON
  },
  body: JSON.stringify({ username: 'John', password: '123' }) // The data
})
.then(response => response.json())
.then(data => console.log('Login Success:', data));
```

---

## 26. What is JSON? and how to used?

JSON (JavaScript Object Notation) is a lightweight, text-based data format used to store and transport data. It is language-independent, meaning while it looks like JavaScript objects, it can be read and written by almost any programming language (Python, Java, C++, etc.).

### Explaination of JSON

Think of JSON as the "English Language" of the Internet.

- If a French person (Python) wants to talk to a German person (Java), they might struggle.
- But if they both agree to write their message in English (JSON), they can understand each other perfectly.

In the tech world:

- Your browser (Frontend) speaks JavaScript.
- The database (Backend) might speak Python or PHP.
- To send user data from the browser to the server, we wrap it in a JSON "envelope." The server opens it, reads it, and understands it.

<details>
<summary>Terminologies:</summary>

- Serialization (Stringify): Converting a "live" object (which lives in computer memory) into a simple text string so it can be sent over a wire (the internet).
- Deserialization (Parsing): Converting that text string back into a live, usable object in code.
- Key-Value Pair: The structure of data. Key is the label, Value is the content.
  - Example: "name": "Alice" (Label is Name, Content is Alice).

</details>

1. The Syntax (Rules):
    - Keys must be in double quotes " ".
    - No trailing commas allowed.
    - Functions are not allowed inside JSON.

```JSON
{
  "name": "John Doe",
  "age": 25,
  "isStudent": true,
  "skills": ["JavaScript", "React"]
}
```

```JavaScript
// A. Sending Data (Object -> String)
const userObject = { name: "John", age: 30 };
const jsonString = JSON.stringify(userObject);
console.log(jsonString); 
// Output: '{"name":"John","age":30}' -> This is now just text!

// B. Receiving Data (String -> Object)
const serverResponse = '{"name":"John","age":30}';
const parsedObject = JSON.parse(serverResponse);
console.log(parsedObject.name); 
// Output: John -> This is now a usable variable!
```

### Use Case of JSON

- API Communication: The most common use. REST APIs usually send responses in JSON format.
- Configuration Files: Storing settings for an app (e.g., package.json in Node.js or settings.json in VS Code).
- Local Storage: Saving simple user data (like "Dark Mode: On") in the user's browser storage.

### JSON vs XML

| Feature | JSON | XML (The Old Standard) |
| :--- | :--- | :--- |
| **Readability** | **Advantage:** Very clean and easy for humans to read. | **Disadvantage:** Verbose (lots of `<tags>` everywhere). |
| **Size** | **Advantage:** Lightweight. Uses less bandwidth because it doesn't need closing tags. | **Disadvantage:** Heavy. The same data takes up more space. |
| **Parsing Speed** | **Advantage:** Extremely fast for browsers to parse (since it is native to JS). | **Disadvantage:** Slower and requires a complex parser. |
| **Data Types** | **Disadvantage:** Limited types. Cannot store Functions, Dates, or undefined. | **Advantage:** Can store more complex schema definitions. |

---

## 27. fetch() vs axios?

- Fetch: The native, built-in JavaScript API for making HTTP requests. It uses Promises and comes pre-installed in all modern browsers.

- Axios: A popular third-party JavaScript library (package) for making HTTP requests. It is built on top of the generic XMLHttpRequest interface but wraps it in Promises and adds powerful features.

### Explanation of Difference

Think of making an HTTP request like Cooking a Meal.

- Fetch (The Manual Kit): You get the raw ingredients.
  - You have to chop the vegetables yourself (Convert to JSON manually).
  - You have to check if the food is rotten yourself (Manual error handling).
  - It’s free and already in your kitchen (Built-in).

- Axios (The Meal Kit Delivery): You pay for a service (Need to install a library).
  - The ingredients come pre-chopped (Automatic JSON conversion).
  - If the food is bad, they don't even deliver it; they call you immediately to apologize (Automatic error handling).
  - It comes with extra sauces and tools (Interceptors, timeout settings).

<details>
<summary>Terminologies:</summary>

- Boilerplate Code: Code that you have to write over and over again with no major changes. Fetch requires more boilerplate (like response.json()).
- Interceptors: A feature in Axios that lets you "intercept" a request or response before it reaches your code. Like a security guard checking every package leaving or entering the building (useful for adding Authentication Tokens automatically).
- Backward Compatibility: The ability to work on old browsers. Fetch doesn't work on very old Internet Explorer without a "polyfill," while Axios handles this internally.
- Response Timeout: Setting a limit (e.g., 5 seconds). If the server doesn't answer by then, cancel the request. Axios does this easily; Fetch makes it harder (requires AbortController).
- XSRF: Cross-Site Request Forgery protection. Axios has built-in support for this security feature, while Fetch requires manual handling.

</details>

```JavaScript
// fetch
fetch('https://api.example.com/user')
  .then(response => {
    // MANUAL STEP 1: Check for 404/500 errors
    if (!response.ok) {
      throw new Error('Server Error');
    }
    // MANUAL STEP 2: Convert to JSON
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.log('Error:', error));

// axios
// Automatic JSON conversion & Error handling
axios.get('https://api.example.com/user')
  .then(response => {
    // Data is already inside response.data
    console.log(response.data); 
  })
  .catch(error => {
    // Automatically runs this if status is 404/500
    console.log('Error:', error); 
  });
```

### Use Cases of fetch and axios

- Use Fetch when:
  - You are building a small project or a simple website.
  - You don't want to increase your app's file size by downloading extra libraries.
  - You only have a few simple API calls.

- Use Axios when:
  - You are building a large, complex application (Enterprise level).
  - You need Interceptors (e.g., to attach a login token to every single request automatically).
  - You need to support older browsers.
  - You want built-in protection against security threats like XSRF.

### fetch vs axios

| Feature | Fetch (Native) | Axios (Library) |
| :--- | :--- | :--- |
| **Setup** | **Advantage:** No installation. Just write code. | **Disadvantage:** Must run `npm install axios` and import it. Adds roughly 11KB to your project size. |
| **Data Transformation** | **Disadvantage:** Two steps: 1. Get response, 2. `.json()`. | **Advantage:** One step: Data is automatically converted to JSON. |
| **Error Handling** | **Disadvantage:** Does not throw errors for HTTP 404/500. You must manually check `response.ok`. | **Advantage:** Automatically throws an error for any bad status code (400-500). |
| **Progress Tracking** | **Disadvantage:** Hard to track upload progress (like a % bar). | **Advantage:** Built-in "Upload Progress" feature. Great for file uploads. |
| **Request Cancellation** | **Disadvantage:** Verbose. Requires creating an `AbortController`. | **Advantage:** Simple. Uses a "CancelToken". |

---

## 28. What is localStorage vs sessionStorage vs cookies?

- **Local Storage**: A web storage API that allows JavaScript sites to store key-value pairs in a web browser with no expiration date. Data persists even after the browser is closed and reopened.
- **Session Storage**: A web storage API that stores data for one session only. The data is deleted when the browser tab is closed.
- **Cookies**: Small pieces of data (text files) sent from a website and stored on the user's computer while the user is browsing. Unlike storage APIs, cookies are sent to the server with every HTTP request.

### Explanation of storages

Imagine you are visiting a hotel (The Website).

- Local Storage (The Safe): You put your passport in the room safe. You leave the hotel, come back next year, and it is still there. It stays until you deliberately remove it.
- Session Storage (The Whiteboard): You write a note on the room's whiteboard. It stays there while you are in the room. But the moment you check out (close the tab), the cleaning crew wipes it completely clean.
- Cookies ( The ID Badge): The hotel gives you a sticky badge to wear on your shirt. Every time you go to the restaurant or the pool (make a request to the server), the staff looks at your badge to know who you are.

<details>
<summary>Terminologies:</summary>

- Persistence: How long the data stays alive. (Local = Forever, Session = Until tab close, Cookie = Until expiration date set by code).
- HttpOnly: A security flag for Cookies. If a cookie is "HttpOnly," JavaScript cannot read it. This prevents hackers from stealing your login info using malicious scripts (XSS attacks). Storage APIs do not have this feature.
- Capacity (Quota): How much data you can store. Storage APIs are big (Standard rooms), Cookies are tiny (A small pocket).
- Server-Side Access: Whether the server (backend) can see the data. The server automatically sees Cookies. It cannot see Local/Session storage unless you manually send that data to it.

</details>

```js
// LocalStorage and Session Storage Same syntax
// A. SAVE Data
localStorage.setItem('username', 'JohnDoe');
sessionStorage.setItem('isLoggedIn', 'true');

// B. GET Data
const user = localStorage.getItem('username'); // Returns "JohnDoe"

// C. REMOVE Data
localStorage.removeItem('username'); // Delete specific item
sessionStorage.clear(); // Delete everything

// Cookies
// Setting a cookie (Name=Value; Expiration)
document.cookie = "username=JohnDoe; expires=Fri, 31 Dec 9999 23:59:59 GMT; path=/";

// Reading cookies (Returns one long string you have to split manually)
console.log(document.cookie); 
// Output: "username=JohnDoe; theme=dark"
```

### Use Cases of storages

- Local Storage:
  - Storing "Dark Mode" preferences (so the site remembers next time you visit).
  - Saving a draft of a long form/blog post so you don't lose it if the internet dies.
  - Storing a "Shopping Cart" for non-logged-in users.

- Session Storage:
  - Sensitive data for a specific transaction (e.g., banking portal details that should vanish if the user closes the tab).
  - Single-page application state (filtering a list just for this visit).

- Cookies:
  - Authentication Tokens: Identifying if a user is logged in (The s server reads this to allow access).
  - Tracking: Google Analytics or Facebook Ads tracking user behavior across pages.

### difference between storages

Feature,Local Storage,Session Storage,Cookies
Capacity,Advantage: Large (~5MB - 10MB).,Advantage: Large (~5MB).,Disadvantage: Tiny (Only 4KB).
Expiration,Advantage: Never expires (unless manually deleted).,Neutral: Expires when Tab/Window closes.,Neutral: Manually set expiration date.
Server Access,Disadvantage: Data stays on Client. Server can't see it easily.,Disadvantage: Data stays on Client.,Advantage: Sent to server with every request automatically.
Security,Disadvantage: Vulnerable to XSS attacks (Scripts can read it).,Disadvantage: Vulnerable to XSS.,Advantage: Safer if HttpOnly flag is used (Scripts cannot read it).
Ease of Use,"Advantage: Very easy API (setItem, getItem).",Advantage: Very easy API.,Disadvantage: Hard to parse strings manually.

---

## 29. What is DOM?

The DOM (Document Object Model) is a programming interface for web documents. It represents the page so that programs (like JavaScript) can change the document structure, style, and content. The DOM represents the document as nodes and objects.

### Explaination of DOM

Think of the DOM as the Family Tree of your website.

- The Window: The Great-Grandparent (The browser tab).
- The Document: The Grandparent (The web page itself).
- HTML: The Parent.
- Head & Body: The Children.
- Divs, H1s, Paragraphs: The Grandchildren.

When you write HTML code, the browser reads it and builds this tree in its memory. JavaScript uses this tree to find elements (like finding a cousin in a family tree) and change them (like changing the cousin's shirt color).

<details>
<summary>Terminologies:</summary>

- Node: Every single item in the DOM tree is a "Node." An HTML tag is an Element Node, text inside a tag is a Text Node, and comments are Comment Nodes.
- Root Element: The top-most element that holds everything else (usually the `<html>` tag).
- Traversing: Moving up and down the tree (e.g., asking "Who is the parent of this button?").

</details>

### What is getElementById() vs querySelector()?

- getElementById()
  - What it does: Selects a single element based strictly on its unique id attribute.
  - Syntax: `document.getElementById("myId")` (Note: No # symbol).
  - Return: Returns the Element object or null if not found.

- querySelector()
  - What it does: Selects the first element that matches a specific CSS Selector.
  - Syntax: `document.querySelector("#myId")` or .myClass or div > p.
  - Return: Returns the first matching Element or null.

| Feature | getElementById() | querySelector() |
| :--- | :--- | :--- |
| **Scope** | Selects only by ID attribute. | Selects by any CSS selector (ID, class, tag). |
| **Syntax** | `document.getElementById("myId")` (No `#`). | `document.querySelector("#myId")` (Needs `#`). |
| **Performance** | Faster (optimized hash map lookup). | Slower (must parse the selector string). |
| **Return** | Reference to the Element or `null`. | Reference to the first matching Element or `null`. |


```html
<div id="container">
    <p class="text">Hello</p>
    <p class="text">World</p>
</div>
```

```js
// 1. Using getElementById (Old Faithful)
// fast and specific
const container = document.getElementById("container"); 

// 2. Using querySelector (The Swiss Army Knife)
// selects by ID (needs #)
const sameContainer = document.querySelector("#container"); 
// selects by Class (needs .) - ONLY returns the FIRST 'p' ("Hello")
const firstParagraph = document.querySelector(".text"); 

// 3. querySelectorAll (To get ALL matches)
const allParagraphs = document.querySelectorAll(".text");
```

#### Use Cases of selectors

- Use getElementById:
  - When you have a specific ID and you want the fastest possible performance (though the speed difference is negligible in modern browsers).
  - When you want to be 100% sure you are getting a unique element.

- Use querySelector:
  - When you need to find an element by class, attribute (e.g., input[type="text"]), or complex relationship (e.g., "The span inside the div").
  - When you want to write consistent code (using CSS syntax everywhere).

#### Difference between selectors

| Feature | getElementById | querySelector |
| :--- | :--- | :--- |
| **Speed** | **Advantage:** Extremely fast (optimized by browsers). | **Disadvantage:** Slightly slower (because it has to parse the CSS selector string). |
| **Flexibility** | **Disadvantage:** Can ONLY find by ID. | **Advantage:** Can find by ID, Class, Tag, Attribute, or hierarchy (`div .class`). |
| **Return Value** | Returns a single element. | Returns a single element (the first match). |
| **Live vs Static** | Returns a live reference. | Returns a static reference. |

---

## 30. What is event and how to handle events in JavaScript?

- **Event**: An "Event" is a signal that something has happened in the browser. It could be a user action (click, keypress) or a browser action (page load, error).
- **Event Propagation**: The process of an event traveling through the DOM tree (the hierarchy of HTML elements) to reach its target and then traveling back.
- **Event Bubbling**: The phase where the event starts at the target element (the most specific one) and "bubbles up" to the ancestors (parents, grandparents). This is the default behavior.
- **Event Capturing (Trickling)**: The phase where the event goes down from the top of the window to the specific target element.

### Explaination of event The "Office Hierarchy" Analogy

Imagine a CEO (Window), a Manager (Parent Div), and a Worker (Button).

- Event Handling: The Worker yells "I need help!" (The Click).
- Event Capturing (Top-Down): The message travels down from the CEO -> Manager -> Worker. The CEO notices "Someone below me is yelling" before the Worker even knows the message arrived.
- Event Bubbling (Bottom-Up): After the Worker handles it, the noise travels up. The Worker yells -> The Manager hears it -> The CEO hears it.

In JavaScript, by default, we only listen to the "Bubbling" (the noise going up). If you click a button inside a Div, the Div also thinks it was clicked because the click "bubbles" up to it.3. Meaning of Hard Terminologies

<details>
<summary>Terminologies:</summary>

- Listener (Handler): A function that sits and waits for a specific event to happen. When the event fires, the function runs.
- stopPropagation(): A command to "Kill the bubble." It stops the event from traveling further up or down the chain. Use this if you want the Button to be clicked, but don't want the Parent Div to know about it.
- target vs currentTarget:
  - target: The actual element you clicked (The Button).
  - currentTarget: The element that owns the listener (The Parent Div that caught the bubble).
- preventDefault(): Stops the browser's default behavior. (e.g., Stops a form from submitting and refreshing the page, or stops a link from opening a URL).

</details>

```html
<div id="parent" style="padding: 20px; background: grey;">
  Parent
  <button id="child">Child Button</button>
</div>
```

```js
const parent = document.getElementById("parent");
const child = document.getElementById("child");

// 1. Handling an Event (The Listener)
child.addEventListener("click", function(event) {
    console.log("Child Clicked!");
    
    // Optional: Uncomment to STOP bubbling
    // event.stopPropagation(); 
});

// 2. Demonstrating Bubbling
// If you click the BUTTON, this Parent listener runs too!
parent.addEventListener("click", function() {
    console.log("Parent Clicked (via Bubble)!");
});

// 3. Demonstrating Capturing (Rarely used)
// Pass 'true' as the 3rd argument to catch it on the way DOWN
parent.addEventListener("click", function() {
    console.log("Parent Captured (Run First)!");
}, true);
```

### Use case of event

- Event Delegation (Best Bubbling Use Case): Instead of adding 100 listeners to 100 list items, you add one listener to the parent `<ul>`. Because of bubbling, clicks on any `<li>` will bubble up to the `<ul>`. You catch it there.
- Analytics: Tracking clicks on the entire `<body>` to see where users interact most.
- Modals/Popups: Detecting a click on the "background" (parent) to close the modal, while keeping clicks inside the "modal content" (child) active (using stopPropagation).

## 31. What is the difference between `map`, `filter`, and `reduce`?

- **map()**: Creates a new array by applying a function to every element in the original array. It transforms data.
- **filter()**: Creates a new array containing only the elements that pass a specific test (return true). It selects data.
- **reduce()**: Reduces an array of values down to a single value (like a number, string, or object) by executing a reducer function on each element. It aggregates data.

### Explanation of array methods

Think of a Chef processing a basket of raw potatoes.

- **map()** is Chopping: The chef takes every potato, peels and chops it.
  - Input: 5 Whole Potatoes.
  - Output: 5 Chopped Potatoes. (Same number of items, but changed).

- **filter()** is Inspecting: The chef checks each potato. If it's rotten, throw it away. If it's good, keep it.
  - Input: 5 Potatoes.
  - Output: 3 Good Potatoes. (Fewer items, but the items themselves are unchanged).

- **reduce()** is Cooking (Mashing): The chef puts all the potatoes into a pot and mashes them together into one big bowl of mashed potatoes.
  - Input: 5 Potatoes.
  - Output: 1 Bowl of Mash. (Many things turned into one thing).

<details>
<summary>Terminologies:</summary>

- Higher-Order Function: A function that takes another function as an input. map, filter, and reduce are all higher-order functions because you pass a callback function into them.
- Immutability: Not changing the original data. All three of these methods return a new array (or value). The original array remains untouched (safe).
- Accumulator (for reduce): The "storage variable" that gets passed along from one step to the next. It collects the result. (Like a snowball rolling down a hill, gathering more snow).

</details>

```js
const numbers = [10, 20, 30, 40];

// 1. MAP: Double every number
// "Take x, return x * 2"
const doubled = numbers.map(num => num * 2);
console.log(doubled); // Output: [20, 40, 60, 80] (Array of same length)

// 2. FILTER: Keep only numbers > 25
// "Take x, keep it if x > 25"
const bigNumbers = numbers.filter(num => num > 25);
console.log(bigNumbers); // Output: [30, 40] (Array of smaller length)

// 3. REDUCE: Add them all up
// "Start with 0 (acc). Add current number (curr) to it."
const total = numbers.reduce((acc, curr) => {
    return acc + curr;
}, 0); // <- 0 is the initial value
console.log(total); // Output: 100 (Single value)
```

### Use Cases of array methods

- map Use Cases:
  - Converting a list of User Objects ({name, age}) into a simple list of names (['John', 'Jane']) to display in a dropdown.
  - Converting temperatures from Celsius to Fahrenheit for a weather app.

- filter Use Cases:
  - Removing a deleted item from a list (e.g., "Keep all tasks where ID is NOT 5").
  - Showing only "Active" users in an admin dashboard.

- reduce Use Cases:
  - Calculating the Total Price of items in a shopping cart.
  - Flattening a nested array (turning [[1,2], [3,4]] into [1,2,3,4]).
  - Counting how many times a specific word appears in a paragraph.

---

## 32. What is destructuring?

Short syntax to pull values from arrays/objects into variables.

```js
const user = { name: 'Sam', age: 30 };
const { name, age } = user; // name = 'Sam', age = 30

const nums = [10, 20, 30];
const [first, , third] = nums; // first = 10, third = 30
```

---

## 33. What is `this` keyword? and its different contexts?

The this keyword in JavaScript refers to the object that is currently executing the function. Its value is dynamic—it is determined at the moment the function is called (runtime), not when the function is written.

### Explanatin of `this`

Think of this like the word "My" or "Me" in English.

- If I (Gemini) say, "My name is Gemini," the word "My" refers to Gemini.
- If You (The User) say, "My name is User," the word "My" refers to You.

The word is exactly the same ("My"), but who it points to changes depending on who is speaking. In JavaScript:

- If a function belongs to an object (e.g., user.speak()), this refers to the user.
- If a function stands alone, this gets confused and usually refers to the "Global World" (Window).

<details>
<summary>Terminologies:</summary>

- Execution Context:: The environment where the code is running. Is it running inside a function? Or just out in the open? this changes based on this environment.
- Implicit Binding: The standard way JS figures out this. It looks at what is to the left of the dot (e.g., in obj.func(), obj is the this).
- Explicit Binding: Forcing a function to use a specific object as this using tools like .call(), .apply(), or .bind().
- Lexical Scoping (Arrow Functions): Arrow functions (=>) are special. They don't have their own this. They "steal" the this from their parent.

</details>

```js
// 1. Global Context (Alone)
console.log(this); // Refers to Window (Browser)

// 2. Object Method (Implicit)
const person = {
    name: "John",
    greet: function() {
        // 'this' refers to 'person' because person called the function
        console.log("Hi, I am " + this.name); 
    }
};
person.greet(); // Output: Hi, I am John

// 3. Arrow Function (Lexical - The Trap!)
const arrowPerson = {
    name: "Jane",
    greet: () => {
        // Arrow functions DON'T own 'this'. They look up to the Window.
        console.log("Hi, I am " + this.name); 
    }
};
arrowPerson.greet(); // Output: Hi, I am undefined (or Window name)

// 4. Constructor (New Keyword)
function Car(model) {
    this.model = model; // 'this' refers to the NEW object being created
}
const myCar = new Car("Tesla");
```

### Rules to determine value of `this`

| Context | Rule (How it is called) | Value of `this` |
| :--- | :--- | :--- |
| **Default Binding** | `myFunction()` (Standalone) | Global Window object (or `undefined` in Strict Mode). |
| **Implicit Binding** | `user.myFunction()` (Dot Notation) | The object before the dot (`user`). |
| **Explicit Binding** | `myFunction.call(user)` | The object you manually passed (`user`). |
| **New Binding** | `new myFunction()` | A brand new empty object created by the constructor. |
| **Arrow Functions** | `() => {}` | The `this` of the surrounding code (Parent scope). |

---

## 34. What are comments?

- Single-line: `// text`
- Multi-line: `/* text */`

Use comments to explain why, not to restate obvious code.

---


## 35. Can we use JavaScript for backend development? How?

Yes, absolutely. JavaScript can be used for backend development primarily through a technology called Node.js.

Node.js is an open-source, cross-platform JavaScript runtime environment that executes JavaScript code outside of a web browser. It allows developers to use JavaScript to write command-line tools and for server-side scripting—running scripts server-side to produce dynamic web page content before the page is sent to the user's web browser.

### Explanation of node.js

For a long time, JavaScript was like a House Cat. It lived strictly inside the house (The Web Browser) and couldn't survive outside.

- Frontend (Browser): JavaScript changed colors, made buttons work, and showed animations.
- Backend (Server): You had to use other languages like Java, PHP, or Python to talk to the database.

Node.js is the "space suit" that lets the House Cat go outside. It took the engine that runs JavaScript inside Google Chrome (called V8), pulled it out, and added features to let it talk to files, databases, and the internet directly. Now, you can use the same language to paint the walls (Frontend) and build the foundation (Backend).

<details>
<summary>Terminologies:</summary>

- Runtime Environment: It is not a programming language itself and it is not a framework. It is the "gym" or "playground" where the JavaScript code runs. It provides the tools (APIs) JS needs to work on a computer server.
- V8 Engine: The high-performance engine built by Google (used in Chrome). Node.js uses this to translate human-readable JavaScript into fast machine code.
- NPM (Node Package Manager): A giant app store for code. It contains millions of free packages (libraries) that you can download to do almost anything (e.g., npm install express to build a web server easily).
- Module: A single file or collection of code that you can import into your main file. It helps organize backend code into small blocks.

</details>

```js
// 1. Import the built-in 'http' module
const http = require('http');

// 2. Create the server
const server = http.createServer((req, res) => {
    // 3. Send a response when someone visits
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Hello! I am a JavaScript Backend Server.');
});

// 4. Listen on port 3000
server.listen(3000, () => {
    console.log('Server running at http://localhost:3000/');
});
```

### Use Cases of node.js

- Real-Time Applications: Chat apps (WhatsApp clones), Live collaboration tools (Google Docs), or Online gaming servers. Node.js is incredibly fast at passing messages back and forth.
- API Servers (REST & GraphQL): Building the backend for Single Page Applications (React/Vue apps) that need to fetch data.
- Streaming Services: Netflix uses Node.js for parts of its streaming interface because it handles data streams efficiently without buffering issues.
- Microservices: Breaking a huge app into tiny, fast independent servers.

### Advantages & Disadvantages of node.js

| Feature | JavaScript Backend (Node.js) | Other Backends (Java/Python) |
| :--- | :--- | :--- |
| **Development Speed** | **Advantage:** You use One Language for both Frontend and Backend ("Full Stack"). Teams move faster because they share code and knowledge. | **Disadvantage:** Frontend devs must learn a completely new language (Context Switching). |
| **Performance** | **Advantage:** High throughput for I/O tasks (database/network requests) due to the Event Loop. Great for high traffic. | **Advantage:** Better for heavy CPU calculation (Machine Learning, Video Processing). Node.js can struggle with heavy math. |
| **Ecosystem** | **Advantage:** NPM is the largest software registry in the world. There is a package for everything. | **Advantage:** Java and Python have older, more "enterprise-mature" libraries for strict banking/security needs. |
| **Concurrency** | **Advantage:** Handles thousands of concurrent connections easily with a single thread. | **Disadvantage:** Creates a new "thread" for every user, which eats up memory (RAM) quickly. |

---

## 36. What are different types of loops?

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
