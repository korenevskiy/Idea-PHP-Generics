# Idea-PHP-Generics

’’’
class One{
.   function __constructor(){
.       echo __CLASSES__[0];// One
.       echo __CLASSES__[1];// Two
.   }
}

class Two{}

trait traitOne {
.   function funOne(){
.      echo count(__CLASSES__);
.   }
}


$obj1 = new One&Two();
// One
// Two

$obj2 = new One&traitOne();
$obj2->funOne()
// One
// Two
// 2

$obj3 = new One&int();
// One
// int

’’’
