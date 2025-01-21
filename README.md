# PHP basics
## Summary
1. [Introduction](#introduction-to-php)
2. [Why PHP?](#why-use-php)
3. [Syntax and basics](#php-syntax-and-basics)
4. [Variables and data types](#variables-and-data-types)
5. [Structure](#control-structures)
6. [Functions](#functions)

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
?>
```

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
#### Corresponding PHP script (<submit.php>):
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
  - Online sandbox like [Replit](https://replit.com/) for quick PHP testing.
