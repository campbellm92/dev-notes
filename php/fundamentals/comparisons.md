# Comparison operators

## ==

Checks if two values are equal

```php
$one = 1;
$two = 2;

$one == $two; // false
```

As in JavaScipt, PHP performs type juggling if a string has the same number value as an int:

```php
$a = 5;
$b = "5";

$a == $b; // true
```

However, unlike in JavaScript, a numeric string + an int will give an int:

```php
$a = 5;
$b = "5";

$a + $b; // 10
```

## !=

Checks if two values are NOT equal

```php
$one = 1;
$two = 2;

$one != $two; // true
```

## ===

Checks if two values are equal and of the same type. In this way, PHP has type coercion like in JavaScript

```php
$five_int = 5;
$five_str = '5';

$five_int === $five_str; // false
```
