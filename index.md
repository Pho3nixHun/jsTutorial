---
title: "Javascript tutorial"
author: "László Simon <laszlo.simon@t-systems.com>"
created: "Mon Aug 22 2016 13:45:38 GMT+0100 (BST)"
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

JavaScript supports much of the structured programming syntax from C (e.g., if statements, while loops, switch statements, do while loops, etc.). One partial exception is scoping: JavaScript originally had only function scoping with var. Lately let have been introduced.


### let vs. var

Let is for block scoping. What does that mean?

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

Strings can be declared two ways

