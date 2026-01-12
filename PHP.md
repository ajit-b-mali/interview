# PHP

---

## 1. What is PHP? and its features?

> PHP (Hypertext Preprocessor) is a widely-used open source general-purpose scripting language that is especially suited for web development and can be embedded into HTML.

### Explanation

Think of PHP as the chef in a restaurant kitchen (Server).
- HTML is the menu (what the user sees).
- PHP processes the order. It checks the fridge (Database), cooks the meal (Logic), and puts it on a plate (dynamically created HTML) to send out to the customer (Browser).

### Features
- **Server-Side**: Runs on the server, not the user's browser.
- **Embedded**: Can be mixed directly inside HTML.
- **Database Support**: Excellent integration with MySQL/MariaDB.
- **Loosely Typed**: Variables don't need strict type definitions.

---

## 2. Why PHP is used?

- **Dynamic Content**: Can change page content (like "Welcome, [Name]") based on user data.
- **Database Interaction**: Easily store and retrieve data (Login systems, blogs).
- **Free & Open Source**: No cost to use.
- **Cross-Platform**: Runs on Windows, Linux, Mac.

---

## 3. Is PHP a server-side or client-side language?

It is **Server-Side**.
- The code executes on the web server (like Apache or Nginx).
- The output sent to the user is plain HTML. The user never sees the PHP source code (like database passwords), keeping it secure.

---

## 4. Differentiate between PHP and other programming languages

- **vs HTML**: HTML is static (structure). PHP is dynamic (logic).
- **vs JavaScript**: JS runs in the browser (client). PHP runs on the server.
- **vs Java/C++**: PHP is interpreted (runs line by line) and web-focused. Java/C++ are compiled and general-purpose.

---

## 5. How PHP code is executed?

1.  Client requests a `.php` file.
2.  Server (e.g., Apache) sees the `.php` extension.
3.  Server passes the file to the PHP Engine.
4.  PHP Engine executes script, runs DB queries, and generates HTML.
5.  Server sends the resulting HTML back to the Client.

---

## 6. What is XAMPP / WAMP?

These are software stacks that make it easy to set up a local server environment.
- **XAMPP**: **X** (Cross-platform), **A**pache (Server), **M**ySQL (Database), **P**HP, **P**erl.
- **WAMP**: **W**indows, **A**pache, **M**ySQL, **P**HP.

They turn your own computer into a local server so you can test PHP code.

---

## 7. What is .php file?

A text file that can contain:
- Text
- HTML
- CSS
- JavaScript
- PHP Code (inside `<?php ... ?>` tags)

---

## 8. echo vs print in PHP?

Both output data to the screen.
- **echo**: No return value. Can verify older versions allowed comma separation (`echo "a", "b"`). Slightly faster.
- **print**: Returns 1 (can be used in expressions). Slower.

Use **echo** by default.

---

## 9. What are variables in PHP?

Containers for storing data.
- Must start with a `$` sign.
- Case-sensitive (`$Age` and `$age` are different).
- Valid: `$name`, `$_valid`. Invalid: `$1name`.

```php
$txt = "Hello";
$x = 5;
```

---

## 10. What are PHP Data Types?

- **String**: "Hello"
- **Integer**: 123
- **Float**: 10.5
- **Boolean**: true/false
- **Array**: Multiple values
- **Object**: Instance of class
- **NULL**: No value
- **Resource**: Reference to external resource (DB connection).

---

## 11. empty vs isset in PHP?

- **isset($var)**: Returns TRUE if variable exists and is NOT NULL.
- **empty($var)**: Returns TRUE if variable does not exist OR is "empty" (0, "", null, false, array()).

```php
$a = 0;
isset($a); // True (it exists)
empty($a); // True (0 is considered empty)
```

---

## 12. == vs === in PHP?

- `==` (Equal): Checks value only. `5 == "5"` is TRUE.
- `===` (Identical): Checks value AND data type. `5 === "5"` is FALSE.

---

## 13. Control structures in PHP

Same logic as C/Java/JS.
- **if / else / elseif**
- **switch**
- **while / do...while**
- **for**
- **foreach**: Specifically for arrays.

```php
$colors = ["red", "green"];
foreach ($colors as $color) {
  echo $color;
}
```

---

## 14. What are arrays in PHP? types of arrays?

An array is a special variable that can hold more than one value.
- **Indexed Arrays**: Numeric index (0, 1, 2). `$cars = ["Volvo", "BMW"];`
- **Associative Arrays**: Named keys. `$age = ["Peter"=>"35", "Ben"=>"37"];`
- **Multidimensional Arrays**: Array inside array.

---

## 15. What are associative arrays in PHP?

Arrays where keys are named strings instead of numbers.
Access like `$array['key']`.

```php
$user = ["name" => "John", "role" => "Admin"];
echo $user['name']; // Prints John
```

---

## 16. What are superglobals in PHP?

Built-in variables available in all scopes.
- `$_GET`: Data from URL parameters.
- `$_POST`: Data from HTTP POST method (forms).
- `$_REQUEST`: Contains `$_GET`, `$_POST` and `$_COOKIE`.
- `$_SESSION`: Variables available across multiple pages.
- `$_COOKIE`: Data stored on the user's computer.
- `$_SERVER`: Headers, paths, script locations.

---

## 17. What are functions in PHP?

Function blocks of code.

```php
function greet($name) {
    return "Hello " . $name;
}
echo greet("World");
```

---

## 18. What is MySQL?

A popular, open-source relational database management system (RDBMS) often used with PHP. It stores data in tables.

---

## 19. What is mysqli / PDO?

Extensions to connect PHP to MySQL.
- **MySQLi**: Improved MySQL. Works ONLY with MySQL databases. Procedural & Object-Oriented.
- **PDO (PHP Data Objects)**: Works with 12 different database systems (MySQL, PostgreSQL, etc.). Only Object-Oriented. Preferred for flexibility.

---

## 20. Session vs Cookie in PHP?

| Feature | Session (`$_SESSION`) | Cookie (`$_COOKIE`) |
| :--- | :--- | :--- |
| **Location** | Stored on Server. | Stored on Client (Browser). |
| **Security** | More secure (User can't edit). | Less secure (User can see/edit). |
| **Expiry** | Ends when browser closes (default). | Can set long expiry date. |
| **Use** | Login status, Shopping cart. | "Remember me", Tracking preferences. |

---

## 21. What is error handling in PHP?

Techniques to manage script errors.
- `die("Message")`: Stop execution.
- `try...catch`: Modern exception handling.
- `error_reporting()`: Configure which errors to show.

---

## 22. GET vs POST methods in PHP?

Same as AJAX concept.
- **GET**: Data in URL. Visible. `$_GET['id']`. Use for retrieving data.
- **POST**: Data in body. Invisible. Secure for passwords. `$_POST['password']`. Use for submitting forms.

---

## 23. PHP thread life cycle?

PHP is generally "Process-based" (Apache prefork) or "Thread-safe" (PHP-FPM) depending on setup.
Simplest view: Request starts -> PHP engine initializes -> Scripts run -> Output sent -> Memory cleaned -> Request ends. Nothing stays in memory between requests (Shared Nothing Architecture).

---

## 24. difference between include and require in PHP?

Both import an external file (like header/footer).
- `require`: strict. If file missing → **Fatal Error** (Script stops).
- `include`: lenient. If file missing → **Warning** (Script continues).

Use `require` when the file is essential (like DB connection).

---

## 25. SQL Injection? prevention?

A hacking technique where an attacker puts SQL commands into input fields (e.g., login form) to manipulate the database.
- **Example**: Inputting `' OR '1'='1` in password to bypass login.
- **Prevention**: Use **Prepared Statements** (with PDO or MySQLi).
  - Keeps data and code separate.
  - Uses `?` or `:name` as placeholders.

```php
// Unsafe
$sql = "SELECT * FROM users WHERE name = '$name'";

// Safe (PDO)
$stmt = $pdo->prepare("SELECT * FROM users WHERE name = ?");
$stmt->execute([$name]);
```

## Advanced PHP Questions

- What are traits in PHP?
- What is autoloading in PHP?
