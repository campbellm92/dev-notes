# Methods

A method is a function attached to a class.

Methods access attributes and other methods of an object instance with the 'this' keyword.

```php
class Bicycle {
    public $colour;

    public function getColour() {
        echo $this->colour;
    }
}
```

Executing a method on an object:

```php
$bike = new Bicycle();
$bike->colour = 'Red';
$bike->getColour();
```
