> start (and try to finish) the [loop tasks](https://javascript.info/while-for) from javascript.info and paste each of your solutions into this file.  
> Don't be afraid of peeking at the solutions!  Just be sure you study them well

## Last loop value
```js
let i = 3;

while (i) {
  alert( i-- );
}
```
last value: 1

## Which values does the while loop show?
```js
let i = 0;
while (++i < 5) alert( i ); // last value 4
let i = 0;
while (i++ < 5) alert( i ); // last value 5
```

##  Output even numbers in the loop
```js
for (let i = 2; i <= 10; i++) {
  if (i % 2 == 0) {
    alert( i );
  }
}
```

## Replace "for" with "while"
Rewrite the code changing the for loop to while without altering its behavior (the output should stay same).
```js
 for (let i = 0; i < 3; i++) {
  alert( `number ${i}!` );
}
//
let i = 0;
while (i < 3) {
  alert( `number ${i}!` );
  i++;
}
```

## Repeat until the input is correct
```js
let num;

do {
  num = prompt("Enter a number greater than 100?", 0);
} while (num <= 100 && num);
```

## Output prime numbers
Write the code which outputs prime numbers in the interval from 2 to n.
For n = 10 the result will be 2,3,5,7.
```js
let n = 10;

nextPrime:
for (let i = 2; i <= n; i++) { // for each i...

  for (let j = 2; j < i; j++) { // look for a divisor..
    if (i % j == 0) continue nextPrime; // not a prime, go next i
  }

  alert( i ); // a prime
}
```

