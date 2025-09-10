# Idea-PHP-Generics

```php
class One{
.   function __constructor(){
.       echo __CLASSES__[0];// One
.       echo __CLASSES__[1];// Two
.   }
}

class Two{
.   function getObj():One|Two{
.       return new One|Two();
.   }
}

trait traitOne {
.   function funTrait(){
.      echo count(__CLASSES__);
.   }
}
```

```php
$obj1 = new One&Two();
echo getclass($obj1->getObj());
// One
// Two
// One&Two


$obj2 = new One&traitOne();
$obj2->funTrait()
// One
// Two
// 2

$obj3 = new One&int();
// One
// int

```

```php

$obj1 = new One|Two();
echo getclass($obj1->getObj());
// One
// Two
// Exception: not support call 'getObj) function

$obj2 = new One|traitOne();
$obj2->funTrait()
// One
// Two
// Exception: not support call 'funTrait' function

$obj3 = new One|int();
// One
// int

```
