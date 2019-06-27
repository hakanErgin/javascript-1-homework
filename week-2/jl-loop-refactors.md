> paste [this markdown of exercises](https://raw.githubusercontent.com/colevandersWands/loop-refactors/master/README.md) into this file and complete the exercises!   

# Loop Refactors

At it's simplist _refactoring_ is rewriting code while keeping it's original behavior.  In the exercises and examples below you can test your refactors by pasting & running the original code in the console, then pasting & running your refactor in console.  If both snippets log the exact same messages you have successfully completed the exercise!

Learning to refactor loops is one of the best ways to learn how they work without struggling to solve code challenges.  As you practice shifting between ```while``` and ```for``` loops you'll begin to recognize the general principles of iteration:
1. initial value
1. advancing operation
1. end condition

Learning to identify these steps and rewrite loops in different ways will help you with debugging, problem solving & understanding other people's code.

### INDEX
* [learning objectives](#learning-objectives)
* completed examples
    * [for](#for)
    * [while](#while)
    * [do-while](#do-while)
* exercises
    * [for to while (4)](#for-to-while)
    * [while to for (4)](#while-to-for)
* [for or while?](#for-or-while)
* [resources](#resources)


---

## Learning Objectives

* mastering JS loop syntax
* identifying the 3 key components of an iteration
* shifting easily between loop types
* separating the __structure__ of written code from the __behavior__ of program data

[TOP](#loop-refactors)

---

## Completed Examples

### For


__[From w3schools](https://www.w3schools.com/js/js_loop_for.asp)__:
> The for loop has the following syntax:
```
for (statement 1; statement 2; statement 3) {
    code block to be executed
}
```
> Statement 1 is executed (one time) before the execution of the code block.  
> Statement 2 defines the condition for executing the code block.  
> Statement 3 is executed (every time) after the code block has been executed.  

* [study ```for``` on pytut](http://www.pythontutor.com/live.html#code=//%20for%20loop%0Afor%20%28%20let%20stepper%20%3D%200%3B%20stepper%20%3C%204%3B%20stepper%2B%2B%20%29%20%7B%0A%20%20//%20body%0A%7D%0A%0A%0A&cumulative=false&curInstr=9&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
* [```for``` loop parsonized](https://janke-learning.github.io/parsonizer/?snippet=%2F%2F%20for%20loop%0Afor%20%28%20let%20stepper%20%3D%200%3B%20stepper%20%3C%204%3B%20stepper%2B%2B%20%29%20%7B%0A%20%20%2F%2F%20body%0A%7D%0A%0A%0A)
* [block scope in for loops](http://www.pythontutor.com/live.html#code=for%20%28var%20x%20%3D%200%3B%20x%20%3C%202%3B%20x%2B%2B%29%20%7B%0A%20%20console.log%28%22x%3A%20%22,%20x%29%3B%0A%7D%0A%0Afor%20%28let%20y%20%3D%200%3B%20y%20%3C%202%3B%20y%2B%2B%29%20%7B%0A%20%20console.log%28%22y%3A%20%22,%20y%29%3B%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false) - JS does an unexpected thing by creating 2 blocks while stepping through the loop. for now just know that this happens, you can understand why later when you learn about closure.

_original for loop_
```js
{
  let result = '';
  console.log("initial result: ", result);

  for ( let stepper = 0; stepper < 3; stepper++ ) {
    result += stepper;
    console.log(result);
  }

  console.log("final result: ", result);
}
```

_refactored to while_
```js
{
  let result = '';
  console.log("initial result: ", result);

  let stepper = 0;
  while ( stepper < 3 ) {
    result += stepper;
    console.log(result);
    stepper++;
  }

  console.log("final result: ", result);
}
```

_refactored to do-while_
```js
/*
  it is not possible to refactor for loops into do-while loops
    for loops might never execute their body
    do-while loops will always execute their body at least once
*/
```


[TOP](#loop-refactors)

---

### While 

* [```while``` on pytut](http://www.pythontutor.com/live.html#code=//%20while%20loop%0Alet%20stepper%20%3D%200%3B%0Awhile%20%28%20%20stepper%20%3C%204%20%29%20%7B%0A%20%20//%20body%0A%20%20stepper%2B%2B%3B%3B%0A%7D%0A%0A%0A&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
* [```while``` parsonized](https://janke-learning.github.io/parsonizer/?snippet=%2F%2F%20while%20loop%0Alet%20stepper%20%3D%200%3B%0Awhile%20%28stepper%20%3C%204%29%20%7B%0A%20%20%2F%2F%20body%0A%20%20stepper%2B%2B%3B%0A%7D%0A%0A%0A)

_original while loop_
```js
{
  let result = '';
  console.log("initial result: ", result);

  let stepper = 0;
  while ( stepper < 3 ) {
    result += stepper;
    console.log(result);
    stepper++;
  }

  console.log("final result: ", result);
}
```

_refactored to for loop_
```js
{
  let result = '';
  console.log("initial result: ", result);

  for ( let stepper = 0; stepper < 3; stepper++ ) {
    result += stepper;
    console.log(result);
  }

  console.log("final result: ", result);
}
```

_refactored to do-while_
```js
/*
  it is not possible to refactor while loops into do-while loops
    while loops might never execute their body
    do-while loops will always execute their body at least once
*/
```


[TOP](#loop-refactors)

---

### Do-While

* [```do-while``` on pytut](http://www.pythontutor.com/live.html#code=//%20do-while%20loop%0Alet%20stepper%20%3D%200%3B%0Ado%20%7B%0A%20%20//%20body%0A%20%20stepper%2B%2B%3B%0A%7D%20while%20%28stepper%20%3C%204%29%3B%0A%0A%0A&cumulative=false&curInstr=9&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
* [```do-while``` parsonized](https://janke-learning.github.io/parsonizer/?snippet=%2F%2F%20do-while%20loop%0Alet%20stepper%20%3D%200%3B%0Ado%20%7B%0A%20%20%2F%2F%20body%0A%20%20stepper%2B%2B%3B%0A%7D%20while%20%28stepper%20%3C%204%29%3B%0A%0A%0A)

_original do-while_
```js
{
  let result = '';
  console.log("initial result: ", result);

  let stepper = 0;
  do {
    result += stepper;
    console.log(result);
    stepper++;
  } while (stepper < 3);

  console.log("final result: ", result);
}
```

_refactored to while_
```js
{
  let result = '';
  console.log("initial result: ", result);

  let stepper = 0;

  // do
  result += stepper;
  console.log(result);
  stepper++;
  
  while (stepper < 3) {
    result += stepper;
    console.log(result);
    stepper++;
  } 

  console.log("final result: ", result);
}
```

_refactored to for_
```js
{
  let result = '';
  console.log("initial result: ", result);

  let stepper = 0;

  // do
  result += stepper;
  console.log(result);

  for ( stepper = 1; stepper < 3; stepper++ ) {
    result += stepper;
    console.log(result);
  }

  console.log("final result: ", result);
}
```


[TOP](#loop-refactors)

---


## Exercises


### For to While

### for -> while 1

[practice on pytut](http://www.pythontutor.com/live.html#code=%7B%0A%20%20let%20result%20%3D%200%3B%0A%20%20for%20%28let%20i%20%3D%201%3B%20i%20%3C%2010%3B%20i%20%2B%3D%20result%29%20%7B%0A%20%20%20%20result%20%2B%3D%20i%3B%0A%20%20%20%20console.log%28i%29%3B%0A%20%20%7D%0A%7D%0A//%20refactor%20to%20while%20loop%0A%0Awhile%20%28%29%20%7B%0A%20%20%0A%7D&cumulative=false&curInstr=15&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  

_original for loop_
```js
{
  let result = 0;
  for (let i = 1; i < 10; i += result) {
    result += i;
    console.log(i);
  }
}
```

_refactor to while_
```js
{
  while () {

  }
}
```

[parsonized solution](https://janke-learning.github.io/parsonizer/?snippet=let%20result%20%3D%200%3B%0Alet%20i%20%3D%201%3B%0Awhile%20%28%20i%20%3C%2010%20%29%20%7B%0A%20%20result%20%2B%3D%20i%3B%0A%20%20console.log%28i%29%3B%0A%20%20i%20%2B%3D%20result%3B%0A%7D)

---

### for -> while 2

[practice on pytut](http://www.pythontutor.com/live.html#code=for%20%28let%20i%20%3D%20-3%3B%20i%20%3D%3D%3D%2010%20%7C%7C%20i%20%3C%2020%3B%20i%20*%3D%20-1.5%29%20%7B%0A%20%20console.log%28i%29%3B%0A%7D%0A%0A//%20refactor%20to%20while%20loop%0A%0Awhile%20%28%29%20%7B%0A%20%20%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  

_original for loop_
```js
{
  for (let i = -3; i === 10 || i < 20; i *= -1.5) {
    console.log(i);
  }
}
```

_refactor to while_
```js
{
  while () {

  }
}
```

[parsonized solution](https://janke-learning.github.io/parsonizer/?snippet=let%20i%20%3D%20-3%3B%0Awhile%20%28i%20%3D%3D%3D%2010%20%7C%7C%20i%20%3C%2020%29%20%7B%0A%20%20console.log%28i%29%3B%0A%20%20i%20*%3D%20-1.5%3B%0A%7D)

---

### for -> while 3

[practice on pytut](http://www.pythontutor.com/live.html#code=%7B%0A%20%20for%20%28let%20i%20%3D%200,%20j%20%3D%2010%3B%20i%20!%3D%3D%20j%3B%20i%2B%2B,%20j--%29%20%7B%0A%20%20%20%20console.log%28%22i%3A%20%22,%20i%29%3B%0A%20%20%20%20console.log%28%22j%3A%20%22,%20j%29%3B%0A%20%20%20%20console.log%28%22i%20%2B%20j%3A%20%22,%20i%20%2B%20j%29%3B%0A%20%20%7D%0A%7D%0A%0A//%20refactor%20to%20while%20loop%0A%0Awhile%20%28%29%20%7B%0A%20%20%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  

_original for loop_
```js
{
  for (let i = 0, j = 10; i !== j; i++, j--) {
    console.log("i: ", i);
    console.log("j: ", j);
    console.log("i + j: ", i + j);
  }
}
```

_refactor to while_
```js
{
  while () {

  }
}
```

[parsonized solution](https://janke-learning.github.io/parsonizer/?snippet=let%20i%20%3D%200%2C%20j%20%3D%2010%3B%0Awhile%20%28%20i%20!%3D%3D%20j%20%29%20%7B%0A%20%20console.log%28%22i%3A%20%22%2C%20i%29%3B%0A%20%20console.log%28%22j%3A%20%22%2C%20j%29%3B%0A%20%20console.log%28%22i%20%2B%20j%3A%20%22%2C%20i%20%2B%20j%29%3B%0A%20%20i%2B%2B%2C%20j--%3B%0A%7D)

---


### for -> while 4

> The logic in this loop is difficult to understand; The goal of these refactors is to recognize the __form__ of your code without worrying about the content.  You can easily complete this exercise without understanding what's happening!  This is the power of learning reliable refactoring patterns

[practice on pytut](http://www.pythontutor.com/live.html#code=%7B%0A%20%20const%20mixitup%20%3D%20false%3B%0A%20%20let%20val%3B%0A%20%20for%20%28let%20i%20%3D%20''%3B%20!!i%20!%3D%3D%20true%20%3B%20i%20%3D%20%2Bval%29%20%7B%0A%20%20%20%20val%20%3D%20!i%20%7C%7C%20mixitup%20*%20i%3B%0A%20%20%20%20console.log%28!!val%29%3B%0A%20%20%7D%0A%7D%0A%0A//%20refactor%20to%20while%20loop%0A%0Awhile%20%28%29%20%7B%0A%20%20%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  

_original for loop_
```js
{
  const mixitup = false;
  let val;
  for (let i = ''; !!i !== true ; i = +val) {
    val = !i || mixitup * i;
    console.log(!!val);
  }
}
```

_refactor to while_
```js
{
  while () {

  }
}
```

[parsonized solution](https://janke-learning.github.io/parsonizer/?snippet=const%20mixitup%20%3D%20false%3B%0Alet%20val%3B%0Alet%20i%20%3D%20''%3B%0Awhile%20%28%20!!i%20!%3D%3D%20true%20%29%20%7B%0A%20%20val%20%3D%20!i%20%7C%7C%20mixitup%20*%20i%3B%0A%20%20console.log%28!!val%29%3B%0A%20%20i%20%3D%20%2Bval%3B%0A%7D)



[TOP](#loop-refactors)

---

### While to For

### while -> for 1

[practice on pytut](http://www.pythontutor.com/live.html#code=let%20x%20%3D%209%3B%0Awhile%20%28x%20%3E%202%29%20%7B%0A%20%20console.log%28x%20*%203%29%3B%0A%20%20x--%3B%0A%7D%0A%0A//%20refactor%20to%20for%20loop%0A%0Afor%20%28%20%3B%20%3B%20%29%20%7B%0A%20%20%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
[parsonized while loop](https://janke-learning.github.io/parsonizer/?snippet=let%20x%20%3D%209%3B%0Awhile%20%28x%20%3E%202%29%20%7B%0A%20%20console.log%28x%20*%203%29%3B%0A%20%20x--%3B%0A%7D)

_original while loop_
```js
{
  let x = 9;
  while (x > 2) {
    console.log(x * 3);
    x--;
  }
}
```

_refactor to for_
```js
{
  for ( ; ; ) {

  }
}
```

---

### while -> for 2

> the [```++``` operator](https://github.com/janke-learning/expanding/blob/master/worked-in-place-operators.md) does two things in one step, it increments it's variable and returns a value.  When used in a while loop condition it does the work of the second & third parts of a for loop statement. 

[practice on pytut](http://www.pythontutor.com/live.html#code=let%20x%20%3D%209%3B%0Awhile%20%28x%2B%2B%20%3C%2020%29%20%7B%0A%20%20console.log%28x%29%3B%0A%7D%0A%0A//%20refactor%20to%20for%20loop%0A%0Afor%20%28%20%3B%20%3B%20/*%20nothing%20goes%20here%20*/%20%29%20%7B%0A%20%20%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  


_original while loop_
```js
{
  let x = 9;
  while (x++ < 20) {
    console.log(x);
  }
}
```

_refactor to for_
```js
{
  for ( ; ; /* nothing goes here */ ) {

  }
}
```


---

### while -> for 3

> for this refactor, write your for loop without using [```++``` operator](https://github.com/janke-learning/expanding/blob/master/worked-in-place-operators.md) in the condition check. we've started the refactor so you can get the idea

[practice on pytut](http://www.pythontutor.com/live.html#code=/*%20%0Afor%20this%20refactor,%20write%20your%20for%20loop%20without%20using%20%0A%20%20%60%60%60%2B%2B%60%60%60%20in%20the%20condition%20check.%20%0A%20%20we've%20started%20the%20refactor%20so%20you%20can%20get%20the%20idea%0A*/%0A%0Alet%20x%20%3D%209%3B%0Awhile%20%28x%2B%2B%20%3C%2020%29%20%7B%0A%20%20console.log%28x%29%3B%0A%7D%0A%0A//%20refactor%20to%20for%20loop%0A%0Afor%20%28%20%3B%20x%20%3C%20%3B%20x%20%2B%3D%201%20%29%20%7B%0A%20%20%0A%7D&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  


_original while loop_
```js
{
  let x = 9;
  while (x++ < 20) {
    console.log(x);
  }
}
```

_refactor to for_
```js
{
  for ( ; x <  ; x += 1 ) {

  }
}
```

---

### while -> for 4

> for this refactor, write your for loop without using [```++``` operator](https://github.com/janke-learning/expanding/blob/master/worked-in-place-operators.md) in the condition check. we're not starting this one for you

[practice on pytut](http://www.pythontutor.com/live.html#code=/*%20%0Afor%20this%20refactor,%20write%20your%20for%20loop%20without%20using%20%0A%20%20%60%60%60%2B%2B%60%60%60%20in%20the%20condition%20check.%20%0A%20%20we're%20not%20starting%20this%20one%20for%20you%0A*/%0A%0Alet%20x%20%3D%209%3B%0Awhile%20%28%2B%2Bx%20%3C%2020%29%20%7B%0A%20%20console.log%28x%29%3B%0A%7D%0A%0A//%20refactor%20to%20for%20loop%0A%0Afor%20%28%20%3B%20%3B%20%29%20%7B%0A%20%20%0A%7D&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  


_original while loop_
```js
{
  let x = 9;
  while (++x < 20) {
    console.log(x);
  }
}
```

_refactor to for_
```js
{
  for ( ;  ;  ) {

  }
}
```

[TOP](#loop-refactors)

---

## For or While


__[From StackOverflow](https://stackoverflow.com/questions/8109509/in-which-situations-should-i-use-while-loops-instead-for-loops-in-javascript#)__
> (This will soon get closed as too subjective, or moved to another forum, but anyway...)  
> Obviously any for loop can easily be rewritten using "while". But given the syntax of:  

```
for ([initialization]; [condition]; [final-expression])
```
> that is used by the for loop it is obviously very well suited to situations where there is some simple initialisation and a simple end-of-iteration update or counter increment. Putting all of the loop control logic right there in the loop's opening statement makes it easy to see at a glance what makes the loop tick.  
> With a while loop the end-of-iteration processing generally has to happen at the bottom of the loop's body, so it's harder to see at a glance how the loop works, but also that is much more suited to the situation where you have to perform a number of calculations to decide whether to keep the loop going.  
> Of course you can shove multiple statements in a for loop initialisation or final-expression by separating them with commas, but if that is anything more complicated than i++, j++, k-- it quickly gets too messy for my taste and a while loop would be a better choice.  
>
> -- nnnnnn

__For__ loops in JavaScript could be considered [syntactic sugar](https://www.quora.com/What-is-syntactic-sugar-in-programming-languages), meaning you can replicate their exact behavior using simpler language features. 

---


## Resources


__study tools__
* [python tutor for JS](http://www.pythontutor.com/live.html#code=&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
* [parsonizer](https://janke-learning.org/parsonizer)

__control-flow visualization__
* (neither of these tools are perfect. if you find them confusing that's just fine, if they help you all the better!)
* [code2flow](https://code2flow.com/app)
* [flowviz](https://janke-learning.org/flowviz)

__while loops__
* [javascript.info](https://javascript.info/while-for#the-while-loop)
* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
* [Video](https://www.youtube.com/watch?v=PpbFyLTtpWI)
* [use while instead of for](https://teamtreehouse.com/community/why-use-while-loop-instead-of-for)

__for loops__
* [MDN on For Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
* [Video + Article](https://www.kirupa.com/html5/loops_in_javascript.htm)
* [StackOverflow](https://stackoverflow.com/questions/39969145/while-loops-vs-for-loops-in-javascript)
* [block scope in for loops](http://www.pythontutor.com/live.html#code=for%20%28var%20x%20%3D%200%3B%20x%20%3C%202%3B%20x%2B%2B%29%20%7B%0A%20%20console.log%28%22x%3A%20%22,%20x%29%3B%0A%7D%0A%0Afor%20%28let%20y%20%3D%200%3B%20y%20%3C%202%3B%20y%2B%2B%29%20%7B%0A%20%20console.log%28%22y%3A%20%22,%20y%29%3B%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false) - JS does an unexpected thing by creating 2 blocks while stepping through the loop. for now just know that this happens, you can understand why later when you learn about closure.

__do-while loops__
* [javascript.info](https://javascript.info/while-for#the-do-while-loop)
* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)
* [do vs. while: Tutorial GateWay](https://www.tutorialgateway.org/difference-between-javascript-while-and-do-while-loop/)
* [do vs. while: Digital Ocean](https://www.digitalocean.com/community/tutorials/using-while-and-do-while-loops-in-javascript)


__loops__
* [So many of them!](https://www.hackreactor.com/blog/javascript-loops-difference-between-types-while-for-in) 
* [interactive examples](http://www.dofactory.com/tutorial/javascript-loops)






[TOP](#loop-refactors)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
