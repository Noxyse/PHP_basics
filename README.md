# PHP basics
## Summary
1. [Introduction](#introduction-to-php)
2. [Why PHP?](#why-use-php)
3. [Syntax and basics](#php-syntax-and-basics)
4. [Variables and data types](#variables-and-data-types)
5. [Structure](#control-structures)
6. [Functions](#functions)
7. [Database interaction](#database-interaction)
8. [Real-world application](#real-world-application)
9. [Advantages and disadvantages](#advantages-and-disadvantages)
10. [Resources](#resources)

## Introduction to PHP

### What is PHP?
PHP stands for 'PHP: Hypertext Preprocessor'. It's a server-side scripting language used primarily for web development created in 1994 by Rasmus Lerdorf. As many other languages, it's open-source and widely supported.
#### Key features:
- Embeds easily within HTML.
- Cross-platform: works on Windows, macOS and Linux servers.
- Works with major databases like MySQL, PostgreSQL, and SQLite.

## Why use PHP?
- **Simplicity**: rather easy to learn.
- **Versatility**: can be used for everything from small scripts to large enterprise apps.
- **Community support**: strong open-source community.
- **Real-world examples**:
  - WordPress, Joomla and Drupal are built on PHP.
  - Facebook and Wikipedia use PHP in their tech stack.
 
## PHP syntax and basics
### Hello, World!
```
<?php
echo "Hello, World!";
?>
```

### Inside HTML code
```
<!DOCTYPE html>
<html>
<body>
    <h1><?php echo "Welcome to PHP!"; ?></h1>
</body>
</html>
```

## Variables and data types
Data types: string, integer, float, boolean, array.

Variables are declared using **$** sign.
### Example:
```
<?php
$name = "John";
$age = 25;
echo "My name is $name and I am $age years old.";
?>
```

## Control structures


### If-else example:
```
<?php
$hour = 10;
if ($hour < 12) {
    echo "Good morning!";
} else {
    echo "Good afternoon!";
}
?>
```

### Loop example:
```
<?php
for ($i = 1; $i <= 5; $i++) {
    echo "Number: $i<br>";
}
?>
```

## Functions
### Defining a function:
```
<?php
function greet($name) {
    return "Hello, $name!";
}
echo greet("Alice");
?>
```

- The key word `function` is used to define a function in PHP.
- `greet` is the name of the function.
- `$name` is the **parameter** of the function. It acts as the placeholder that takes a value when the function is called.
- The function uses the `return` keyword to send a result back.

## Database interaction
### Basic MySQL query in PHP:
```
<?php
$conn = new mysqli("localhost", "username", "password", "database");
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
$result = $conn->query("SELECT * FROM users");
while ($row = $result->fetch_assoc()) {
    echo $row['name'] . "<br>";
}
$conn->close();
?>
```

#### 1. Connecting to the Database:
`$conn = new mysqli("localhost", "username", "password", "database");`
- Tries to establish a connection to the MySQL database server. If successful, `$conn` will hold the connection object.

#### 2. Checking for connection errors:
```
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
```
- The `connect_error` property of the `$conn` object checks if there was an error during the connection attempt.
- If there's an error (invalid creds or server unreachable), the script displays the error message using `die()` and stops further script execution.

#### 3. Executing a query:
`$result = $conn->query("SELECT * FROM users");` 
- The `$conn->query()` method sends a SQL query to the database.
- `"SELECT" * FROM users"` is a SQL command to select all columns (*) and all rows from the `users` table.
- The result of this query is stored in `$result`.
- If the query fails (table `users` doesn't exist), `$result` will be `fasle`.

#### 4. Fetching and displaying results:
```
while ($row = $result->fetch_assoc()) {
    echo $row['name'] . "<br>";
}
```
- `$result->fetch_assoc()` fetches one row of data from the result set as an **associative array**.
  - Keys of the array correspond to the column names in the `users` table.
- The `while` loop continues to fetch rows until there are no more left.
  - `$row['name']` accesses the value in the `name` column of the current row.
  - `echo $row['name'] . "<br>";` prints the `name` value, followed by a line break.

##### Output example:

Assuming the `users` table contains this data:
| id     | name | email        |
|----------|-----|-------------|
| 1    | neo01777  | neo01777@becode.org    |
| 2      | Reigen-cs  | reigen-cs@becode.org  |

The output will be:
```
neo01777
Reigen-cs
```

#### 5. Closing the connection
`$conn->close();`
- This releases resources associated with the connection.

## Real-world application
### Contact form in PHP
#### HTML code:
```
<form method="post" action="submit.php">
    Name: <input type="text" name="name"><br>
    Email: <input type="email" name="email"><br>
    <input type="submit">
</form>
```
#### Corresponding PHP script (`submit.php`):
```
<?php
$name = $_POST['name'];
$email = $_POST['email'];
echo "Thank you, $name. We will contact you at $email.";
?>
```

## Advantages and disadvantages
### Advantages:
- easy to learn and deploy.
- works seamlessly with HTML and CSS.
- supports a variety of databases.

### Disadvantages:
- can be less secure if not coded properly.
- slower than newer frameworks like Node.js for certain tasks.

## Resources
- [PHP documentation](https://www.php.net/manual/en/)
- Tutorials: [W3Schools](https://www.w3schools.com/php/), [PHP The Right Way](https://phptherightway.com/)
- Tools:
  - [XAMPP](https://www.apachefriends.org/fr/index.html): local server for PHP and MySQL.
