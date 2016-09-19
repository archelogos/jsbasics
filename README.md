# JS Basics

## Types
```
var n = 1;
var b = true;
var s = "string";
var a = [];
var o = {};

// Init
var n = n || 0;
var b = b || false;
var s = s || "";
var a = a || [];
var o = o || {};

// Undefined
var x;
x // undefined
typeof x // "undefined"
var n = 1; typeof n; // "number"
var b = true; typeof b; // "boolean"
var s = "string"; typeof s; // "string"
var a = []; typeof a; // "object"
var o = {}; typeof o; // "object"

// Let and const
let x = 123;
const X = 123;
```

## Console
```
console.log("Log");
console.error("Error");
console.warn("Warn");
```

## Number
```
// Math
Math.round(); Math.floor(); Math.random();
var arr = [1,2,3];
Math.max.apply(null, arr); // -> 3
Math.min.apply(null, arr); // -> 1

var sn = "123";
var n = parseInt(sn);
```

## String
```
var s = "hello";
s.length // -> 5
s.charAt(0) // -> "h"
s.charCodeAt(0) // -> 104

var ns = 123;
var s = ns.toString();

function palindrome(str){
    if(typeof str !== "string"){
        return false;
    }
    let i;
    for(i=0; i < Math.floor(str.length/2); i++){
        if(str[i] !== str[str.length-1+i]){
            return false;
        }
    }    
    return true;
}

// ReplaceAll
String.prototype.replaceAll = function(t, g){
    return this.split(t).join(g);
}
```

## Array and loops
```
// Unshift & Shift (At the beginning)
var arr = [];
arr.unshift(1); // -> [1]
arr.shift(); -> 1; []

// Push & Pop (At the end)
var arr = [];
arr.push(1); // -> [1]
arr.pop(); -> 1; []

// Queue (FIFO)
var arr = [];
arr.push(1);
arr.shift();

// Stack (LIFO)
var arr = [];
arr.unshift(1);
arr.shift();

var arr = [1,2,3];
// ForEach
arr.forEach(function(elem,index){
    console.log(elem+index);
});
// For
var i;
for(i=0; i<arr.length; i++){
    // foo
}
// Reduce
arr.reduce(function(a,b){
    return a+b;
}); // -> 6

// Map
arr.map(function(elem){
    return elem+1;
}); // -> [2,3,4]

// Sort (IN PLACE)
var sArr = ["b","a","d","c"];
sArr.sort();

var nArr = [2,1,4,3];
nArr.sort(function(a,b){
    return a-b;
});

// IndexOf
var arr = [1,2,3];
arr.indexOf(2); // -> 1
arr.indexOf("hey"); // -1
```

## Boolean
```
var x = 1;
var y = 1;
(x == y) // true, it checks value
(x != y) // false, it checks value
(x === y) // true, it checks value and type
(x !== y) /false, it checks value and type
if(cond){
 // ...
}
else if{
 // ...
}
else{
}
```

## Declare
```
var x;
function x(){
}
```

## Define
```
x = 5;
var x = function(){
}
```

## Hoisting
```
x = 5;
console.log(x); // It works! declaration goes to the top.
var x;

execute();
function execute(){
    console.log("executing"); // It works! declaration goes to the top.
}
```

## Objects
```
var obj = {};
obj.x = "prop x";
obj.xFn = function(){};
obj[x]; // -> "prop x"
```

## Function
```
// Constructor Style
function fn (){
}

// Variable Style
var fn = function(){
}

// Anonymus
var element = document.getElementById("id");
element.addEventListener("click", function(){}, false);
```

## IIFE
```
(function(){

})();
```

## Closure
```
function myFunction(){
    var a = "hello";
    var sayHello = function(){
        return a;
    };
    return sayHello();
}
```

## BinarySearch
```
```

## Event Bubbling
```
var elements = document.querySelectorAll(".class");
elements.forEach(function(elem){
    elem.addEventListener("click", function(){}, false);
});
```

## Classes and Objects
```
function Entity(){
}
var e1 = new Entity();

function Product(price, category){
    this.price = price || 0;
    this.category = category || "not set";
}
var book1 = new Product(14.95, "Books");
book1 instanceof Product; // true
book1 instanceof Object; // true
```

## Private, privileged and proto functions
```
function Entity(){
    this.id = 123;
    var name = "test name";

    // Private
    var setName = function(newName){
        if(typeof newName === "string"){
            name = newName;
        }
    }

    // Privileged
    this.setName = function(newName){
        if(typeof newName === "string"){
                name = newName;
            }
    }
}
// Prototyping
Entity.prototype.getId = function(){
    return this.id;
}
```

## Inheritance
```
function Person(age, gender){
    this.age = age || 0;
    this.gender = gender || "not set";
}
function Man(age){
    Person.call(this, age, "male");
}
Man.prototype = Object.create(Person.prototype);
Man.prototype.constructor = Man;
```

## Call or Apply
```
Entity.call(this, arg1, arg2, arg3);
Entity.apply(this, [arg1, arg2, arg3]);
```

## Prototyping
```
Array.prototype.quickSort = function(){
    var self = this; // this -> Array
};
String.prototype.replaceAll = function(){
    var self = this; // this -> String
};
Object.prototype.newFn = function(){
    var self = this; // this -> Object
};
// Entity prototyping
function Entity(){
}
Entity.prototype.getSomething = function(){}
```

## Singleton Pattern
```
var Model = (function(){

    function M(){
    }

    var instance;
    return {
        getInstance: function(){
            if(!instance){
                instance = new M();
            }
            return instance;
        }
    };

})();
var MODEL1 = Model.getInstance();
var MODEL2 = Model.getInstance();
(MODEL1 === MODEL2) // true
```

## XMLHTTPRequest
```
var req = new XMLHTTPRequest();
req.open("GET", "http://api.example.com/entity");
req.onload = function(){
    if(req.responseStatus === 200){
        //success
        console.log(req.response);
    }
    else{
        // ?
    }
};
req.open();
```

## Promises
```
var p = new Promise(function(resolve, reject){
    // async stuff
    var data = {};
    resolve(data);
    // reject(data);
}).then(function(data){
    // do something
    return data;
}).then(function(data){
    // do something
    return data;
}).catch(function(data){
    // error
});
```

## Graphs
```
```

## Trees
```
```

## Service Workers
```
```
