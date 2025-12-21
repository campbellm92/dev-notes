# Inheritance

Classes can 'extend' other classes, meaning they inherit a parent class's properties and methods.

To make a child class, use the 'extends' keyword.

```php
class Vehicle{
    public function drive() {
        echo "Driving...";
    }
}

class Truck extends Vehicle {

}
```

Use it with the function from Vehicle:

```php
$truck = new Truck();
$truck->drive();
```

Child classes can override methods in the parent:

```php
class Tractor extends Vehicle {
    public function drive() {
        echo "Driving slowly...";
    }
}
```

A class can use a parent's property or method with the $this variable

```php
class Motorcycle extends Vehicle {
    public function pushPedal() {
        $this->drive();
    }
}

$hog = new Motorcycle();
$hog->pushPedal(); // "Driving..."
```

When overriding a parent's property or method, calls made via $this will always resolve to the child’s implementation, not the parent’s.

If you want to reuse or extend the parent’s behavior instead of completely replacing it, you must explicitly call the parent method using parent::.

```php
class Racecar extends Vehicle{
    public function drive() {
        parent::drive();
        echo "Driving even faster..."; // outputs both echos
    }
}
```
