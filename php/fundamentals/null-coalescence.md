# Null coalescence

PHP uses the null-coalescing operator: ??

This is used to check if a value is set (and not null).

If a value is null or not set, the operator will return the value to the right.

## Use cases

### Arrays

```php
$data = ['name' => 'Matt'];
echo $data['name'] ?? 'No name set.'; // Matt
echo $data['age'] ?? 'No age set.'; // No age set
```

### Optional variables

```php
echo $username ?? 'Guest';
```

### Prioritised fallbacks

```php
echo $a ?? $b ?? $c ?? 'Fallback';
```
