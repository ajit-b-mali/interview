# jQuery

---

## 1. What is jQuery?

> jQuery is a fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, animation, and Ajax much simpler with an easy-to-use API that works across a multitude of browsers.

### Explanation

Think of JavaScript as a raw toolset (hammer, saw, drill). You can build anything, but it takes many manual steps.
jQuery is like a power tool or a prefabricated kit. It wraps complex, multi-line JavaScript tasks into single, short commands.

Instead of writing 10 lines of code to check browser compatibility and find an element, you write 1 line of jQuery.

---

## 2. What are the features of jQuery?

- **DOM Manipulation**: Easy to select and change HTML elements.
- **Event Handling**: Simple `.click()`, `.hover()`.
- **AJAX Support**: Simple `$.ajax()`, `$.get()`.
- **Animations**: Built-in effects like slide, fade.
- **Cross-Browser**: Handling the differences between Chrome, Firefox, Safari, and old IE automatically.

---

## 3. Why is jQuery used?

It simplifies client-side scripting.
- **Write Less, Do More**: That's their motto.
- Handling cross-browser inconsistencies (especially historically relevant).
- Huge ecosystem of plugins.

---

## 4. Differentiate between JavaScript and jQuery

| Feature | JavaScript | jQuery |
| :--- | :--- | :--- |
| **Nature** | Programming Language. | Library (written in JavaScript). |
| **Syntax** | Verbose (`document.getElementById`). | Concise (`$('#id')`). |
| **Performance** | Faster (native to valid browser). | Slightly slower (overhead of library). |
| **Use** | Core logic. | DOM/UI Shortcuts. |

---

## 5. How to include jQuery in a webpage?

1.  **CDN (Content Delivery Network)**: Link to a hosted file.
    ```html
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    ```
2.  **Download**: Save the `.js` file locally and link it.

---

## 6. What is `$` in jQuery?

The `$` sign is an alias (short name) for the `jQuery` function.
Writing `$("#box")` is the same as writing `jQuery("#box")`. It is the entry point to access all jQuery features.

---

## 7. What is $(document).ready()?

It is a function that waits for the HTML structure (DOM) to be fully loaded before running the code inside it.

```js
$(document).ready(function() {
  // Code runs only after HTML is ready
  $("button").click(function(){ ... });
});

// Shorter version:
$(function() {
   // Code here
});
```
**Why?** If you try to select an element (like a button) before the browser has rendered it, your script will fail. This prevents that.

---

## 8. What are jQuery selectors?

Selectors allow you to "pick" HTML elements to apply actions to them. They mimic CSS selectors.

- `$("p")` - Selects all `<p>` tags.
- `$(".class")` - Selects by class.
- `$("#id")` - Selects by ID.
- `$("div > p")` - Direct child.
- `$("tr:odd")` - Odd table rows.

---

## 9. How do you select an element by id? by class?

- **ID**: `$("#myId")` – The `#` symbol denotes ID.
- **Class**: `$(".myClass")` – The `.` symbol denotes Class.

---

## 10. How to handle click events in jQuery?

Use the `.click()` method or `.on('click', ...)`

```js
$("#btnSubmit").click(function() {
  alert("Button Clicked!");
});
```

---

## 11. Differentiate between `.html()` and `.text()`

- `.text()`: Gets or sets only the **text content**. Ignores HTML tags.
    - `$("div").text("<b>Bold</b>")` → Outputs literally `<b>Bold</b>`.
- `.html()`: Gets or sets the **HTML content**. Renders HTML tags.
    - `$("div").html("<b>Bold</b>")` → Outputs **Bold**.

---

## 12. How to hide and show elements using jQuery?

```js
// Hide
$("#box").hide(); // Sets display: none

// Show
$("#box").show(); // Restores display property

// Toggle (Switch between hide/show)
$("#box").toggle();
```

---

## 13. What are jQuery effects?

Built-in animations to make UI interactions smooth.

- `hide() / show() / toggle()`
- `fadeIn() / fadeOut() / fadeToggle()`
- `slideUp() / slideDown() / slideToggle()`
- `animate()` (Custom CSS animations)

---

## 14. Differentiate between `.hide()` and `.fadeOut()`

- `.hide()`: Instantly removes the element (Effectively `display: none`). ZERO time.
- `.fadeOut()`: Gradually changes opacity from 1 to 0 over time, then sets `display: none`. Smooth visual effect.

---

## 15. What is `.slideUp()` and `.slideDown()`?

- `.slideUp()`: Hides an element by sliding it up (decreasing height to 0).
- `.slideDown()`: Shows an element by sliding it down (increasing height).

---

## 16. What is chaining in jQuery?

Chaining allows you to run multiple jQuery commands on the same element in a single line of code.

```js
// Without chaining
$("#p1").css("color", "red");
$("#p1").slideUp(2000);
$("#p1").slideDown(2000);

// With Chaining
$("#p1").css("color", "red").slideUp(2000).slideDown(2000);
```

---

## 17. How to traverse DOM elements using jQuery?

Traversal methods help you move around the DOM tree from a selected element.

- `.parent()`: Direct parent.
- `.children()`: Direct children.
- `.find("span")`: Search deeply inside.
- `.siblings()`: Elements on the same level.
- `.next()`: Next sibling.
- `.prev()`: Previous sibling.

---

## 18. Difference between `.click()` and `.on()` methods?

- `.click(fn)`: Simple shorthand. Only works for elements present **when the code runs**.
- `.on('click', fn)`: The preferred modern way.
    - Can handle **Event Delegation**: works for elements added dynamically (e.g., via AJAX) later in the future.

```js
// Works for future elements added to #container
$("#container").on("click", ".dynamic-btn", function() { ... });
```

---

## 19. How to prevent default action of an event in jQuery?

Use `event.preventDefault()`.

```js
$("a").click(function(event) {
  event.preventDefault(); // Stops link from navigating to URL
  alert("Link disabled");
});
```

---

## 20. How do you change CSS using jQuery?

Using the `.css()` method.

```js
// Get property
let color = $("#box").css("background-color");

// Set property
$("#box").css("background-color", "blue");

// Set multiple properties
$("#box").css({
  "background-color": "blue",
  "font-size": "20px"
});
```

---

## 21. How do you add and remove classes in jQuery?

- `.addClass("className")`: Adds a class.
- `.removeClass("className")`: Removes a class.
- `.toggleClass("className")`: Adds if missing, removes if present.

---

## 22. How to handle form submissions using jQuery?

Use the `.submit()` event.

```js
$("#myForm").submit(function(event) {
    if (/* validation fails */) {
         event.preventDefault(); // Stop form from sending to server
         alert("Error!");
    }
});
```

## Task

1. Button click → hide/show div
2. Change text on button click
3. Form validation (empty check)
4. Add/remove class dynamically
5. Load data using AJAX (basic)

## Checklist for readyness

- Step 1: Explain
  - What is jQuery and why is it used?
  - Difference between JavaScript and jQuery
  - What is $?
  - What is $(document).ready()?

- Step 2: Write basic code
  - Select by ID/Class
  - Handle click event
  - Hide/Show an element
