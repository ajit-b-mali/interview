# AJAX

---

## 1. What is AJAX?

> AJAX stands for **A**synchronous **J**avaScript **A**nd **X**ML. It is not a programming language but a technique for accessing web servers from a web page.

### Explanation

Imagine you are reading a newspaper.

- Traditional Web: To read a new article, you have to buy a whole new newspaper (reload the page).
- AJAX: You just cut out the new article and paste it over the old one, without touching the rest of the paper.

AJAX allows web pages to update asynchronously by exchanging data with a web server behind the scenes. This means parts of a web page can be updated without reloading the whole page.

<details>
<summary>Terminologies:</summary>

- Asynchronous: Happening independently of the main program flow. The code sends a request and keeps running; it doesn't freeze waiting for the answer.
- XML: Extensible Markup Language. It was the original format for data transfer, but now **JSON** is standard. The name AJAX stuck, even though we rarely use XML anymore.

</details>

---

## 2. Why AJAX is used?

- **Better User Experience**: No flashing white screens between clicks.
- **Speed**: Only small bits of data are transferred, not the whole HTML page.
- **Interactivity**: Features like auto-complete search, infinite scrolling (Instagram/Twitter), and live chats rely on AJAX.

---

## 3. What does asynchronous mean?

Asynchronous means that the script can send a request to the server and continue executing other code without waiting for the reply.

- **Synchronous**: You call a pizza place and stay on the line until they tell you it's ready. You can't do anything else.
- **Asynchronous**: You order pizza online and go watch TV. The pizza arrives later (callback/promise) without stopping you from watching TV.

---

## 4. What happens in a normal page reload vs AJAX?

| Feature | Normal Page Reload (Synchronous) | AJAX (Asynchronous) |
| :--- | :--- | :--- |
| **Action** | Browser sends request for URL. | Browser sends JS request to server. |
| **Server** | Returns entire HTML page (Header + Body + Footer). | Returns only data (usually JSON). |
| **Client** | Browser clears screen and renders new HTML. | JS updates only a specific `<div>`. |
| **Feel** | Page blinks/refreshes. | Seamless/Smooth update. |

---

## 5. What data formats are used in AJAX?

- **JSON (JavaScript Object Notation)**: The standard. Lightweight, easy to parse.
- **XML**: Older, verbose, tag-based. Rarely used now.
- **HTML**: Snippets of pre-built HTML code.
- **Plain Text**: Simple strings.

---

## 6. What is fetch API? and what it returns?

The `fetch()` API is the modern, native way to make AJAX requests in JavaScript.

- It is built into the browser (no libraries needed).
- It returns a **Promise** that resolves to the Response to that request.

```js
fetch('https://api.example.com/data') // Returns a Promise
```

---

## 7. Why .then() is used with fetch?

Since `fetch` returns a Promise (because network requests take time), `.then()` is used to handle the result *when it arrives*.

```js
fetch(url)
  .then(response => {
     // Code here runs ONLY after headers arrive
  });
```

---

## 8. What is .json() method in fetch?

The response from `fetch` is a raw HTTP response stream (headers + body). The body isn't usable text yet.
`.json()` is a method that reads the stream and parses it as JSON. It returns a **Promise** because reading the stream is also asynchronous.

```js
fetch(url)
  .then(response => response.json()) // Read body and parse JSON
  .then(data => console.log(data));  // Use the actual data
```

---

## 9. How to handle errors in fetch API?

`fetch()` only rejects (errors out) on network failure (offline, DNS error). It does **not** reject on 404 (Not Found) or 500 (Server Error). You must check `response.ok`.

```js
fetch('https://api.example.com/user')
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error("Fetch error:", error));
```

---

## 10. difference between $.ajax and fetch API

- **$.ajax**: jQuery's method. Older. Handles browser compatibility (IE). automatically parses JSON. Rejects on 404/500 errors.
- **fetch**: Native browser API. Modern. Uses Promises. More low-level (doesn't auto-reject 404).

---

## 11. $.ajax() vs $.get() vs $.post()

- `$.ajax({ ... })`: The master function. Highly configurable (headers, timeout, async settings).
- `$.get(url, callback)`: Shorthand for simple GET requests.
- `$.post(url, data, callback)`: Shorthand for simple POST requests.

---

## 12. AJAX lifecycle

1.  **Event Occurs**: User clicks button or page loads.
2.  **Request Created**: JS creates `XMLHttpRequest` or calls `fetch`.
3.  **Request Sent**: Request travels to server.
4.  **Server Process**: Server runs DB query, logic.
5.  **Response Sent**: Server sends back JSON/XML.
6.  **Response Received**: Browser receives data.
7.  **Callback/Promise**: JS function runs to update UI with new data.

---

## 13. GET vs POST

| Feature | GET | POST |
| :--- | :--- | :--- |
| **Purpose** | Get data from server. | Send data to server (create/update). |
| **Visibility** | Data visible in URL (`?id=1`). | Data hidden in request body. |
| **Size Limit** | Limited (URL length). | No limit (can send files). |
| **Caching** | Can be cached. | Not cached. |

---

## 14. What is XMLHttpRequest?

The original, "old school" object used for AJAX before `fetch` came along.

- It is event-based (uses `onreadystatechange`).
- It is clunky and verbose compared to Promises.

```js
// The Old Way
const xhr = new XMLHttpRequest();
xhr.open("GET", "data.txt");
xhr.onload = function() {
  if (xhr.status === 200) {
    console.log(xhr.responseText);
  }
};
xhr.send();
```

---

## 15. Real use cases of AJAX

- **Google Search**: Suggestions appear as you type.
- **Maps**: Loading new tiles as you drag the map.
- **Shopping Cart**: Adding items without leaving the product page.
- **Form Validation**: Checking if "Username is taken" instantly.

---

## 16. Advantages of using AJAX

- **Reduced Server Traffic**: Transmits less data.
- **Responsiveness**: Site feels faster.
- **Asynchronous**: User can work while data loads.

---

## 17. Disadvantages of using AJAX

- **SEO**: Search engines (crawlers) sometimes struggle to read content loaded via JS (though this is improving).
- **History**: Doesn't automatically add to browser "Back" button history (needs extra code).
- **Complexity**: logic is split between client and server; harder to debug.

## AJAX Readiness Checklist

- Answer YES / NO honestly:
- Can I explain AJAX in 1 sentence?
- Can I explain async vs sync?
- Do I know XMLHttpRequest?
- Do I understand fetch()?
- Do I know Promise basics?
- Can I explain GET vs POST?
- Do I know what JSON is?
- Can I handle success & error?
- Can I explain AJAX flow?
- Can I give real example?

✔️ 8–10 YES → READY
✔️ 6–7 YES → Almost ready
❌ < 6 → Revise AJAX
