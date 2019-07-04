> start (and try to finish) the [conditional tasks](https://javascript.info/ifelse) from javascript.info and paste each of your solutions into this file.  
> things that might help: [javascript.inf - comparisons](https://javascript.info/comparison), [interactive coercion table](https://janke-learning.org/equalities-coercion/), [equalities table](https://dorey.github.io/JavaScript-Equality-Table/)

## if (a string with zero)

```js
if ("0") {
  alert( 'Hello' );
}
```
Any string except an empty one (and "0" is not empty) becomes true in the logical context.

## The name of JavaScript

```js
let value = prompt('What is the "official" name of JavaScript?', '');

    if (value == 'ECMAScript') {
      alert('Right!');
    } else {
      alert("You don't know? ECMAScript!");
    }
```

## Show the sign

```js
let value = prompt('Type a number', 0);

if (value > 0) {
  alert( 1 );
} else if (value < 0) {
  alert( -1 );
} else {
  alert( 0 );
}
```

## Rewrite 'if' into '?'
```js
if (a + b < 4) {
  result = 'Below';
} else {
  result = 'Over';
}
/-->
result = (a + b < 4) ? 'Below' : 'Over';

## Rewrite 'if..else' into '?'
```js
let message;

if (login == 'Employee') {
  message = 'Hello';
} else if (login == 'Director') {
  message = 'Greetings';
} else if (login == '') {
  message = 'No login';
} else {
  message = '';
}
/-->
let message = (login == 'Employee') ? 'Hello' :
  (login == 'Director') ? 'Greetings' :
  (login == '') ? 'No login' :
  '';
```
