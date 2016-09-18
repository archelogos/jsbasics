# JS Foundations

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
