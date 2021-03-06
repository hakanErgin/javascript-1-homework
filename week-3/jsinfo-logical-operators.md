> start (and try to finish) the [loop tasks](https://javascript.info/logical-operators) from javascript.info and paste each of your solutions into this file.  
> things that might help: [truthiness](https://github.com/janke-learning/truthiness/blob/master/README.md)

## What's the result of OR?
What is the code below going to output?
```js
alert( null || 2 || undefined );
//2 (first true value)
```

## What's the result of OR'ed alerts?
```js
//The answer: first 1, then 2.
alert( alert(1) || 2 || alert(3) );
```
The call to alert does not return a value. Or, in other words, it returns undefined.

The first OR || evaluates it’s left operand alert(1). That shows the first message with 1.
The alert returns undefined, so OR goes on to the second operand searching for a truthy value.
The second operand 2 is truthy, so the execution is halted, 2 is returned and then shown by the outer alert.
There will be no 3, because the evaluation does not reach alert(3).

## What is the result of AND?
```js
alert( 1 && null && 2 );
```
The answer: null, because it’s the first falsy value from the list.

## What is the result of AND'ed alerts?

The answer: 1, and then undefined.
```js
 alert( alert(1) && alert(2) );
 ```
The call to alert returns undefined (it just shows a message, so there’s no meaningful return).//

Because of that, && evaluates the left operand (outputs 1), and immediately stops, because undefined is a falsy value. And && looks for a falsy value and returns it, so it’s done.


## The result of OR AND OR

The answer: 3.
```js
 alert( null || 2 && 3 || 4 );
 ```
The precedence of AND && is higher than ||, so it executes first.

The result of 2 && 3 = 3, so the expression becomes:
```js
null || 3 || 4
```
Now the result is the first truthy value: 3.

## Check the range between
```js
if (age >= 14 && age <= 90)
```

## Check the range outside
Write an if condition to check that age is NOT between 14 and 90 inclusively.
Create two variants: the first one using NOT !, the second one – without it.
```js
if (!(age >= 14 && age <= 90))

if (age < 14 || age > 90)
```

## A question about "if"
The answer: the first and the third will execute.
```js
 // Runs.
// The result of -1 || 0 = -1, truthy
if (-1 || 0) alert( 'first' );

// Doesn't run
// -1 && 0 = 0, falsy
if (-1 && 0) alert( 'second' );

// Executes
// Operator && has a higher precedence than ||
// so -1 && 1 executes first, giving us the chain:
// null || -1 && 1  ->  null || 1  ->  1
if (null || -1 && 1) alert( 'third' );
```

## Check the login
```js
let userName = prompt("Who's there?", '');

if (userName == 'Admin') {

  let pass = prompt('Password?', '');

  if (pass == 'TheMaster') {
    alert( 'Welcome!' );
  } else if (pass == '' || pass == null) {
    alert( 'Canceled.' );
  } else {
    alert( 'Wrong password' );
  }

} else if (userName == '' || userName == null) {
  alert( 'Canceled' );
} else {
  alert( "I don't know you" );
}
```
