# Scope #

* Scope is the area determined between "{}" brackets.
* There are three scope types global, block and function scope. 
* Event callback function also follow the same rules as event callback

### Definitions ###
```javascript
var apple =1;
{
    console.log(apple);  //output-1
    console.log(orange); //output-ReferenceError: orange is not defined 
} 
```
* In the above program the apple is declared globally it can access alos inside the block scope. When a variable is deined using var keyword.
* In the above code the orange variable is refered, which does not define it will give reference error like in the above code.
* When we define var globally automatially it becomes window object.

## Hoisting ##

* If the apple is defined using var keyword inside a block scope it would be placed on the top of the code it becomes global.
* Hoisting is limited to variable de keywfined using var keyword and function name defined using function keyword.
* Variables defined using let const are not hoisted.

```javascript

console.log(apple);
{
    var apple = 1; //undefined
}
```
* In the above code the variable name only hoisted the value of the variable is not hoisted. So it becomes undefined.


## Funciton name hoisting ##

* Hositing also apllies to function name but variable hoisitng takes precedence.

```javascript 
fun();
fun1();
function fun(){
    console.log("Hello");
}

var fun = function(){
    console.log("vanakam");
}

var fun1 = function(){
    console.log("vanakam");
}

fun();
```
* In the above the the function is called before the function definitio but by function name hoisting it will ptint "Hello".
* The fun1(); call will produce error because it is normal to assign a variable to anonymous funciton but it will no to be hoisted.


```javascript
function fun(){
    console.log("Hello1");
}
function fun(){
    console.log("Hello2");
}
fun();
```

* In above code the it will Hello2 the last funciton will take precedence.

```javascript

var fun = function(){
    console.log("Hello2");
}
function fun(){
    console.log("Hello1");
}

fun();//Hello2

```
* In the above code variable name will take precedence than the funcition definition.

## Variable Types ##

* var - It is is the original specification. Instead of that start using let and const.
* let - let can define variable but it has a block scope.
* const - const also same as let but const cant be reassigne value once it is defined.

* Funtion - In all funciton the variable types including var also have limited block scope

## In classes ##

* In class the let (or var or const) creates the local scope only.
* It cannot be accecsed outside the scope .
* In class the variables are defined inside the function or its methods.

```javascript
class car {
    constructor(){
        let property =1;
        this.apple =2;
    }
    method(){
        console.log(this.property);
        console.log(this.apple);
    }
}

let auto = new car();

console.log(auto);
```
