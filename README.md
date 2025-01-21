# PHP basics
## Summary
1. [Introduction](#introduction_to_PHP)
2. [Why PHP?](#why_use_PHP?)

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
Example:
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
