---
title: "Javascript tutorial"
author: "László Simon <laszlo.simon@t-systems.com>"
created: "Tue Aug 23 2016 08:24:05 GMT+0200 (Central Europe Daylight Time)"
original:
    title: "Javascript tutorial"
    url: "http://localhost:3000/index.html"
show_footer: true
---

Summary
1. About javascript
2. Types
    + Strings, booleans, numbers
    + Arrays (ES6)
    + Object (ES6)
3. Classes and functions
    + Functions
        + Arrow functions
    + Advanced classes
4. Promises
5. ???

# About Javascript

  JavaScript (/ˈdʒɑːvəˌskrɪpt/) is a high-level, dynamic, untyped, and interpreted programming language. It has been standardized in the ECMAScript language specification.
Although there are strong outward similarities between JavaScript and Java, including language name, syntax, and respective standard libraries, the two are distinct languages and differ greatly in their design. JavaScript was influenced by programming languages such as Self and Scheme.
"JavaScript" is a trademark of Oracle Corporation.

  JavaScript (/ˈdʒɑːvəˌskrɪpt/) is a high-level, dynamic, untyped, and interpreted programming language. It has been standardized in the ECMAScript language specification.
Although there are strong outward similarities between JavaScript and Java, including language name, syntax, and respective standard libraries, the two are distinct languages and differ greatly in their design. JavaScript was influenced by programming languages such as Self and Scheme.

  "JavaScript" is a trademark of Oracle Corporation.

## Types

JavaScript supports much of the structured programming syntax from C (e.g., if statements, while loops, switch statements, do while loops, etc.). One partial exception is scoping: JavaScript originally had only function scoping with ```var```. Lately ```let``` have been introduced.

### let vs. var

Let is for block scoping. What does that mean?New text block

```javascript; runnable
let me = 'go';
var i = 'able';

return { let: me, var: i };
```

What about functions?

```javascript; runnable
(function you() {
    let shall = !'pass';
})();

return shall;
```

```javascript; runnable
(function whitGreatPower() {
    var gte = 'responsibility';
})();

return gte;
```

There must be a way...

```javascript; runnable
return nish;
for( var nish = 5; nish > 0; nish-- ) { }
```

```javascript; runnable
for( var nish = 5; nish > 0; nish-- ) { }
return nish;
```

```javascript; runnable
for( var nish = 5; nish > 0; nish-- ) {
    return nish;
}
```

```javascript; runnable
return tuce;
for( let tuce = 5; tuce > 0; tuce-- ) { }
```

```javascript; runnable
for( let tuce = 5; tuce > 0; tuce-- ) { }
return tuce;
```

```javascript; runnable
for( let tuce = 5; tuce > 0; tuce-- ) {
    return tuce;
}
```

What it is good for?

Have you ever met with the following situation?

```javascript; runnable
while (graphElement.firstChild) { graphElement.removeChild(graphElement.firstChild); }

this.buttons = [];
for(var i = 0; i < 5; i++){
    let button = document.createElement('button');
    let text = document.createTextNode("Button #" + i);
    button.appendChild(text);
    graphElement.appendChild(button);
    this.buttons.push(button);
}
```

```javascript; runnable
for(var i = 0; i < this.buttons.length; i++) {
  this.buttons[i].onclick = function() { alert(i) }
}
```

```javascript; runnable
for(let i = 0; i < this.buttons.length; i++) {
  this.buttons[i].onclick = function() { alert(i) }
}
```

## Strings

Strings can be declared many ways.

```javascript; runnable
var byteArray = [117, 115, 101, 114, 102, 114, 105, 101, 110, 100, 108, 121];
var strArr = this.strArr = [
    "I'm", 'not',
    `${"antisocial"};`,
    new String('just' + ' ' + 'not'),
    String.fromCharCode(...byteArray)
];

return strArr.join(' ');
```

You may ask: But why? What is the difference?

```javascript; runnable
var result = {};

this.strArr.forEach( (i) => {
    result[i] = typeof i;
})
return result
```

### Numbers

What types of numbers we have in JS?

```javascript; runnable
return parseInt(1.2);
```

```javascript; runnable
return parseInt(1.99);
```

```javascript; runnable
return parseFloat(5.25);
```

```javascript; runnable
return { 
    "parseInt" : typeof parseInt(1.2),
    "parseFloat" : typeof parseFloat(5.25)
}
```

Based on parseFloat and parseInt you may say, there is at least two.
Wrooong, it just one ```Number```

#### String to number conversion

```javascript; runnable
return "3" + 5;
```

```javascript; runnable
return 5 + "3";
```

```javascript; runnable
return +"3" + 5;
```

```javascript; runnable
return 5 * "2";
```

```javascript; runnable
return "2" * 5;
```

### Booleans

Very often, in programming, you will need a data type that can only have one of two values. For this, JS has a ```Boolean``` data type. It can be either ```true``` or ```false```.

#### Comparisons

 Operator | Description 
--- | ---
! | not
== | equal to (by value)
=== | equal to (by type and value)
!= | not equal to (by value)
!== | not equal to (by type and value)
> | greater
>= | greater or equal
> | lower 
>= | lower or equal
\|\| | orElse
\&\& | andAlso

Under some conditions other datatypes could be converted to boolean, but it's not always clear.
These are called falsy values:

```javascript; runnable
return {
  false: Boolean(false),
  0: Boolean(0),
  "": Boolean(""),
  undefined: Boolean(undefined),
  null: Boolean(null),
  NaN: Boolean(NaN)
}
```

```javascript; runnable
return [
    false == 0,
    false == "",
    0 == ""
]
```

```javascript; runnable
return [
    Boolean(''),
    Boolean(0),
    Boolean(new String('')),
    Boolean(new Number(0))
]
```

Wait... What about this:

```javascript; runnable
return new String('') === ''
```

```javascript; runnable
return typeof new String('');
```

```javascript; runnable
return typeof '';
```

```javascript; runnable
return [
    null == false,
    null == null,
    null == undefined,
    undefined == undefined,
    undefined == null
]
```

```javascript; runnable
return [
    NaN == null,
    NaN == NaN
]
```

```javascript; runnable
return [
    Boolean([]),
    Boolean(['']),
    Boolean({})
]
```

Lets move on to
### Arrays and Objects

You can declare arrays like:

```javascript; runnable
var arr = ['a','b',3, undefined];
var arr2 = new Array(5);

return {arr: arr, arr2: arr2}
```

What is the type of an array?

```javascript; runnable
return typeof new Array();
```

```javascript; runnable
return typeof [];
```

Since array is and ```object``` it has a ```prototype```.
What is a prototype you may ask?!

Every JavaScript object has a prototype. The prototype is also an object. (```{}```)
All JS object inherit their properties and methods from their prototype.

```javascript; runnable
var Person = this.Person = function (first, last, age, eyecolor) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eyecolor;
}
return Object.keys(Person);
```

```javascript; runnable
var person = new this.Person('Cookie', 'Monster', 47, 'black')
return Object.keys(person);
```

But back to Arrays. Array's prototype has a lot of method. 
Let's see the commonly used ones (at least I use them often):

```javascript; auto
this.fruits = ['Apple', 'Banana', 'Pineapple', 
               'Coconut', 'Orange', 'Lemon'];
```

#### forEach

As it name states, it's a loop. Is it sync or async?

Let's start with a single for loop, but spin it up with async calls.

What will be the result?

```javascript; runnable
var result = '\n';

for(let i=0; i < this.fruits.length; i++){
    let item = this.fruits[i];
    let index = i;
    setTimeout(function(){
        result += (`${index}: ${item}\n`);
    })
}

result += 'Is this thing async or sync?\n';

return result;
```

You may say, it's because return occures before all setTimeouts finishes.

```javascript; runnable
var wait = function (ms){ // NEVER DO THIS!!!
   var start = new Date().getTime();
   var end = start;
   while(end < start + ms) {
     end = new Date().getTime();
  }
}

var result = '\n';

for(let i=0; i < this.fruits.length; i++){
    let item = this.fruits[i];
    let index = i;
    setTimeout(function(){
        result += (`${index}: ${item}\n`);
    })
}

result += 'Is this thing async or sync?\n';

wait(this.fruits.length*20);
return result;
```

Do you remember? String is one of JS's types. Types not called by a reference. They are always values.

Since setTimeout's function runs on another scope, the result variable inside is not the same as the result variable outside.

```javascript; runnable
function StringBuilder(base){
    this.text = base || '\n';
    this.append = function(str){ this.text += `${str}\n` };
}
var result = new StringBuilder();

for(let i=0; i < this.fruits.length; i++){
    let item = this.fruits[i];
    let index = i;
    setTimeout(function(){
        result.append(`${index}: ${item}`);
    })
}

result.append('Is this thing async or sync?');

return result;
```

What we did? We created a class and initialized a copy of it. It is an object now, which is accessed by reference. Therefore we always manipulate the same string(```this.text```).

Returning to the original topic: You can see the string was built on an async way, since ```'Is this thing...'``` appeared at the begining of the result, because it was executed earlier than the setTimeout function.

```javascript; runnable
var result = '\n';

this.fruits.forEach(function(item, index, array){
    result += `${index}: ${item}\n`
})

result += 'Is this thing async or sync?';

return result;
```

#### pop

Removes the last element and returns with it.

```javascript; auto
return {
    pop: this.fruits.pop(),
    arr: this.fruits
}
```

#### push

Adds a new element to the array and returns the new length

```javascript; auto
return {
    push: this.fruits.push('Lemon'),
    arr: this.fruits
}
```
