> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/operator-precedence/master/README.md) into this file and complete the exercises!   

# Operator Precedence

you'll be presented with a single line expression.  your task is to break it into steps according to operator precedence.  The main objective for these exercises is that you become comfortable stepping through and working with complex JS expressions, not that your learn everything about how all operators work.  

Once you become familiar with these exercises you'll find that you're able to complete them just as easily no matter what values you set. 
After mastering them you'll find that you can complete them without even caring what values are going through the expressions!

This is because programming languages are _formal systems_, meaning their text is constructed based on a set of rules.  Once you learn how to manipulate code thinking not about _what it does_ but _how it's structured_ as a text, then you'll be ready to rock and roll.  

__learning objectives__
* which operators exist in JS
* reading this [operator precedence table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
* breaking down long expressions (super helpful for debugging, reading & writing code)
* stepping through expressions 
* building nasty debugging skillls
* statements vs. expressions



### Index
* [completed examples](#completed-examples)
    * [one](#1)
    * [two](#2)
    * [three](#3)
    * [four](#4)
    * [five](#5)
* exercises
    * [types & casting](#types-and-casting)
    * [logical operators](#logical-operators)
    * [arithmetic operators](#arithmetic-operators)
    * [all primitive operators](#all-primitive-operators)
* [resources](#resources)

---

## Completed Examples

### 1


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=Number%28Boolean%28String%28a%29%29%29%0AString%28_%29%0ABoolean%28_%29%0ANumber%28_%29)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20Number%28Boolean%28String%28a%29%29%29%3B%0A%0Aconst%20op_1%20%3D%20String%28a%29%3B%0Aconst%20step_1%20%3D%20Number%28Boolean%28op_1%29%29%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20Boolean%28op_1%29%3B%0Aconst%20step_2%20%3D%20Number%28op_2%29%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20Number%28op_2%29%3B%0Aconst%20step_3%20%3D%20op_3%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = ;

  const expected = Number(Boolean(String(a)));

  const op_1 = String(a);
  const step_1 = Number(Boolean(op_1));
  console.assert(step_1 === expected, "step_1");

  const op_2 = Boolean(op_1);
  const step_2 = Number(op_2);
  console.assert(step_2 === expected, "step_2");

  const op_3 = Number(op_2);
  const step_3 = op_3;
  console.assert(step_3 === expected, "step_3");
}
```

### 2

[parsonized](https://janke-learning.github.io/parsonizer/?snippet=%28a%20%2B%20b%29%20%3D%3D%20%28a%20%3C%20c%29%0A_%20%2B%20_%0A_%20%3C%20_%0A_%20%3D%3D%20_%0A%0A%0A%0A)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20,%20c%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20%28a%20%2B%20b%29%20%3D%3D%20%28a%20%3C%20c%29%3B%0A%0Aconst%20op_1%20%3D%20a%20%2B%20b%3B%0Aconst%20step_1%20%3D%20op_1%20%3D%3D%20%28a%20%3C%20c%29%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20a%20%3C%20c%3B%0Aconst%20step_2%20%3D%20op_1%20%3D%3D%20op_2%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20op_1%20%3D%3D%20op_2%3B%0Aconst%20step_3%20%3D%20op_3%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  

```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = , c = ;

  const expected = (a + b) == (a < c);

  const op_1 = a + b;
  const step_1 = op_1 == (a < c);
  console.assert(step_1 === expected, "step_1");

  const op_2 = a < c;
  const step_2 = op_1 == op_2;
  console.assert(step_2 === expected, "step_2");

  const op_3 = op_1 == op_2;
  const step_3 = op_3;
  console.assert(step_3 === expected, "step_3");
}
```

### 3


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=b%20%26%26%20typeof%20a%20%3D%3D%3D%20'string'%0Atypeof%20_%0A_%20%3D%3D%3D%20'string'%0A_%20%26%26%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20b%20%26%26%20typeof%20a%20%3D%3D%3D%20'string'%3B%0A%0Aconst%20op_1%20%3D%20typeof%20a%3B%0Aconst%20step_1%20%3D%20b%20%26%26%20op_1%20%3D%3D%3D%20'string'%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20op_1%20%3D%3D%3D%20'string'%3B%0Aconst%20step_2%20%3D%20b%20%26%26%20op_2%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20b%20%26%26%20op_2%3B%0Aconst%20step_3%20%3D%20op_3%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B&cumulative=false&curInstr=1&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = ;

  const expected = b && typeof a === 'string';

  const op_1 = typeof a;
  const step_1 = b && op_1 === 'string';
  console.assert(step_1 === expected, "step_1");

  const op_2 = op_1 === 'string';
  const step_2 = b && op_2;
  console.assert(step_2 === expected, "step_2");

  const op_3 = b && op_2;
  const step_3 = op_3;
  console.assert(step_3 === expected, "step_3");
}
```
[short-circuiting - an advanced gotcha](https://github.com/janke-learning/expanding/blob/master/worked-short-circuiting.md)

### 4


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=%28b%20%26%26%20typeof%20a%29%20%3D%3D%3D%20'string'%0Atypeof%20_%0A_%20%26%26%20_%0A_%20%3D%3D%3D%20'string')  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20%28b%20%26%26%20typeof%20a%29%20%3D%3D%3D%20'string'%3B%0A%0Aconst%20op_1%20%3D%20typeof%20a%3B%0Aconst%20step_1%20%3D%20op_1%20%3D%3D%3D%20'string'%20%26%26%20b%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20b%20%26%26%20op_1%3B%0Aconst%20step_2%20%3D%20op_2%20%3D%3D%3D%20'string'%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20op_2%20%3D%3D%3D%20'string'%3B%0Aconst%20step_3%20%3D%20op_3%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = ;

  const expected = (b && typeof a) === 'string';

  const op_1 = typeof a;
  const step_1 = (b && op_1) === 'string' ;
  console.assert(step_1 === expected, "step_1");

  const op_2 = b && op_1;
  const step_2 = op_2 === 'string';
  console.assert(step_2 === expected, "step_2");

  const op_3 = op_2 === 'string';
  const step_3 = op_3;
  console.assert(step_3 === expected, "step_3");
}
```


### 5


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=%28%20a%20%3E%20Number%28b%29%20%29%20%7C%7C%20String%28c%29%0ANumber%28_%29%0A_%20%3E%20_%0AString%28_%29%0A_%20%7C%7C%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20,%20c%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20%28%20a%20%3E%20Number%28b%29%20%29%20%7C%7C%20String%28c%29%3B%0A%0Aconst%20op_1%20%3D%20Number%28b%29%3B%0Aconst%20step_1%20%3D%20%28%20a%20%3E%20op_1%20%29%20%7C%7C%20String%28c%29%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20a%20%3E%20op_1%3B%0Aconst%20step_2%20%3D%20%28%20op_2%20%29%20%7C%7C%20String%28c%29%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20String%28c%29%3B%0Aconst%20step_3%20%3D%20op_2%20%7C%7C%20op_3%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B%0A%0Aconst%20op_4%20%3D%20op_2%20%7C%7C%20op_3%3B%0Aconst%20step_4%20%3D%20op_4%3B%0Aconsole.assert%28step_4%20%3D%3D%3D%20expected,%20%22step_4%22%29%3B&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = , c = ;

  const expected = ( a > Number(b) ) || String(c);

  const op_1 = Number(b);
  const step_1 = ( a > op_1 ) || String(c);
  console.assert(step_1 === expected, "step_1");

  const op_2 = a > op_1;
  const step_2 = ( op_2 ) || String(c);
  console.assert(step_2 === expected, "step_2");

  const op_3 = String(c);
  const step_3 = op_2 || op_3;
  console.assert(step_3 === expected, "step_3");

  const op_4 = op_2 || op_3;
  const step_4 = op_4;
  console.assert(step_4 === expected, "step_4");
}
```
[short-circuiting - an advanced gotcha](https://codeburst.io/javascript-what-is-short-circuit-evaluation-ff22b2f5608c)



[TOP](#operator-precedence)

---
---

# Exercises

---

## Types and Casting

### types & casting 1


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=typeof%20a%20%3D%3D%3D%20typeof%20b%0Atypeof%20a%0Atypeof%20b%0A_%20%3D%3D%3D%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20typeof%20a%20%3D%3D%3D%20typeof%20b%3B%0A%0Aconst%20op_1%20%3D%20%3B%0Aconst%20step_1%20%3D%20%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20%3B%0Aconst%20step_2%20%3D%20%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20%3B%0Aconst%20step_3%20%3D%20%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = ;

  const expected = typeof a === typeof b;

  let op_1;
  let step_1;
  console.assert(step_1 === expected, "step_1");

  let op_2;
  let step_2;
  console.assert(step_2 === expected, "step_2");

  let op_3;
  let step_3;
  console.assert(step_3 === expected, "step_3");
}
```

### types & casting 2


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=Boolean%28a%29%20!%3D%3D%20Boolean%28b%29%0ABoolean%28a%29%0ABoolean%28b%29%0A_%20!%3D%3D%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20Boolean%28a%29%20!%3D%3D%20Boolean%28b%29%3B%0A%0Aconst%20op_1%20%3D%20%3B%0Aconst%20step_1%20%3D%20%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20%3B%0Aconst%20step_2%20%3D%20%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20%3B%0Aconst%20step_3%20%3D%20%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B%20&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = ;

  const expected = Boolean(a) !== Boolean(b);

  let op_1;
  let step_1;
  console.assert(step_1 === expected, "step_1");

  let op_2;
  let step_2;
  console.assert(step_2 === expected, "step_2");

  let op_3;
  let step_3;
  console.assert(step_3 === expected, "step_3"); 
}
```

## types & casting 3


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=Boolean%28b%29%20%3D%3D%3D%20Boolean%28Number%28a%29%29%0ABoolean%28b%29%0ANumber%28a%29%0ABoolean%28_%29%0A_%20%3D%3D%3D%20_)   
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20Boolean%28b%29%20%3D%3D%3D%20Boolean%28Number%28a%29%29%3B%0A%0Aconst%20op_1%20%3D%20%3B%0Aconst%20step_1%20%3D%20%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20%3B%0Aconst%20step_2%20%3D%20%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20%3B%0Aconst%20step_3%20%3D%20%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B%0A%0Aconst%20op_4%20%3D%20%3B%0Aconst%20step_4%20%3D%20%3B%0Aconsole.assert%28step_4%20%3D%3D%3D%20expected,%20%22step_4%22%29%3B&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = ;

  const expected = Boolean(b) === Boolean(Number(a));

  let op_1;
  let step_1;
  console.assert(step_1 === expected, "step_1");

  let op_2;
  let step_2;
  console.assert(step_2 === expected, "step_2");

  let op_3;
  let step_3;
  console.assert(step_3 === expected, "step_3");

  let op_4;
  let step_4;
  console.assert(step_4 === expected, "step_4");
}
```

[TOP](#operator-precedence)

---

## Logical Operators

### logical operators 1


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=!%28a%20%26%26%20!b%29%0A!_%0A_%20%26%26%20_%0A!%28_%29%0A%0A)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20!%28a%20%26%26%20!b%29%3B%0A%0Aconst%20op_1%20%3D%20%3B%0Aconst%20step_1%20%3D%20%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20%3B%0Aconst%20step_2%20%3D%20%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20%3B%0Aconst%20step_3%20%3D%20%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B%20&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = ;

  const expected = !(a && !b);

  let op_1;
  let step_1;
  console.assert(step_1 === expected, "step_1");

  let op_2;
  let step_2;
  console.assert(step_2 === expected, "step_2");

  let op_3;
  let step_3;
  console.assert(step_3 === expected, "step_3"); 
}
```

### logical operators 2


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=!!a%20%7C%7C%20!!b%0A!a%0A!_%0A!b%0A!_%0A_%20%7C%7C%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20!!a%20%7C%7C%20!!b%3B%0A%0Aconst%20op_1%20%3D%20%3B%0Aconst%20step_1%20%3D%20%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20%3B%0Aconst%20step_2%20%3D%20%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20%3B%0Aconst%20step_3%20%3D%20%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B%20%0A%0Aconst%20op_4%20%3D%20%3B%0Aconst%20step_4%20%3D%20%3B%0Aconsole.assert%28step_4%20%3D%3D%3D%20expected,%20%22step_4%22%29%3B%0A%0Aconst%20op_5%20%3D%20%3B%0Aconst%20step_5%20%3D%20%3B%0Aconsole.assert%28step_5%20%3D%3D%3D%20expected,%20%22step_5%22%29%3B%20&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = ;

  const expected = !!a || !!b;

  let op_1;
  let step_1;
  console.assert(step_1 === expected, "step_1");

  let op_2;
  let step_2;
  console.assert(step_2 === expected, "step_2");

  let op_3;
  let step_3;
  console.assert(step_3 === expected, "step_3"); 

  let op_4;
  let step_4;
  console.assert(step_4 === expected, "step_4");

  let op_5;
  let step_5;
  console.assert(step_5 === expected, "step_5"); 
}
```

### logical operators 3


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=a%20%7C%7C%20b%20%26%26%20c%20%7C%7C%20a%0A_%20%26%26%20_%0Aa%20%7C%7C%20_%0A_%20%7C%7C%20a)   
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20,%20c%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20a%20%7C%7C%20b%20%26%26%20c%20%7C%7C%20a%3B%0A%0A//%20break%20down%20this%20expression&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = , b = , c = ;

  const expected = a || b && c || a;

  // break down this expression
}
```
[ast explorer](https://astexplorer.net/#/gist/bc0bac0e8559bf97071c9129a05a28f9/e5fcaa5df8317fb1a45ba1a7866733d96768c463)


[TOP](#operator-precedence)

---

## Arithmetic Operators

### arithmetic operators 1


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=-%28a%20%2B%20b%29%20*%20c%0A_%20%2B%20_%0A-%28_%29%0A_%20*%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%200,%201,%20-1,%20NaN,%20Infinity,%20.5,%20-0.0,%201e3,%201e-3,%20999e305,%20999e306%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20,%20c%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20-%28a%20%2B%20b%29%20*%20c%3B%0A%0Aconst%20op_1%20%3D%20%3B%0Aconst%20step_1%20%3D%20%3B%0Aconsole.assert%28step_1%20%3D%3D%3D%20expected,%20%22step_1%22%29%3B%0A%0Aconst%20op_2%20%3D%20%3B%0Aconst%20step_2%20%3D%20%3B%0Aconsole.assert%28step_2%20%3D%3D%3D%20expected,%20%22step_2%22%29%3B%0A%0Aconst%20op_3%20%3D%20%3B%0Aconst%20step_3%20%3D%20%3B%0Aconsole.assert%28step_3%20%3D%3D%3D%20expected,%20%22step_3%22%29%3B%20&cumulative=false&curInstr=10&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
/* values to try
  0, 1, -1, NaN, Infinity, .5, -0.0, 1e3, 1e-3, 999e305, 999e306
*/
const a = , b = , c = ;

const expected = -(a + b) * c;

let op_1;
let step_1;
console.assert(step_1 === expected, "step_1");

let op_2;
let step_2;
console.assert(step_2 === expected, "step_2");

let op_3;
let step_3;
console.assert(step_3 === expected, "step_3"); 
}
```
[scientific notation](http://www.java2s.com/Tutorials/Javascript/Javascript_Tutorial/Data_Type/How_to_write_Scientific_notation_literal_in_Javascript.htm)

### arithmetic operators 2


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=a%20**%20b%20%2F%20%2Bc%0A%2B_%0A_%20**%20_%0A_%20%2F%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%200,%201,%20-1,%20NaN,%20Infinity,%20.5,%20-0.0,%201e3,%201e-3,%20999e305,%20999e306%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20,%20c%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20a%20**%20b%20/%20%2Bc%3B%0A%0A//%20break%20down%20this%20expression%20&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    0, 1, -1, NaN, Infinity, .5, -0.0, 1e3, 1e-3, 999e305, 999e306
  */
  const a = , b = , c = ;

  const expected = a ** b / +c;

  // break down this expression 
}
```

### arithmetic operators 3


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=b%20%25%20c%20-%20a%20**%20c%20%2F%20b%0A_%20**%20_%0A_%20%2F%20_%0A_%20%25%20_%0A_%20-%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%200,%201,%20-1,%20NaN,%20Infinity,%20.5,%20-0.0,%201e3,%201e-3,%20999e305,%20999e306%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20,%20c%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20b%20%25%20c%20-%20a%20**%20c%20/%20b%3B%0A%0A//%20break%20down%20this%20expression&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    0, 1, -1, NaN, Infinity, .5, -0.0, 1e3, 1e-3, 999e305, 999e306
  */
  const a = , b = , c = ;

  const expected = b % c - a ** c / b;

  // break down this expression
}
```

[TOP](#operator-precedence)

---

## All Primitive Operators

### all primitive operators 1


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=a%20%25%20b%20%7C%7C%20!!a%0A_%20%25%20_%0A!a%0A!_%0A_%20%7C%7C%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%200,%201,%20-1,%20NaN,%20Infinity,%20.5,%20-0.0,%201e3,%201e-3,%20999e305,%20999e306%0A%20%200,%203%0A%20%201,%203%0A%20%202,%203%0A%20%203,%203%0A%20%204,%203%0A*/%0Aconst%20a%20%3D%20,%20b%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20a%20%25%20b%20%7C%7C%20!!a%3B%0A%0A//%20break%20down%20this%20expression&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    0, 1, -1, NaN, Infinity, .5, -0.0, 1e3, 1e-3, 999e305, 999e306
    0, 3
    1, 3
    2, 3
    3, 3
    4, 3
  */
  const a = , b = ;

  const expected = a % b || !!a;

  // break down this expression
}
```

### all primitive operators 2


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=typeof%20a%20%3D%3D%3D%20'number'%20%2B%20a%0Atypeof%20_%0A_%20%3D%3D%3D%20_%0A_%20%2B%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%200,%201,%20-1,%20NaN,%20Infinity,%20.5,%20-0.0,%201e3,%201e-3,%20999e305,%20999e306%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20typeof%20a%20%3D%3D%3D%20'number'%20%2B%20a%3B%0A%0A//%20break%20down%20this%20expression&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    0, 1, -1, NaN, Infinity, .5, -0.0, 1e3, 1e-3, 999e305, 999e306
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = ;

  const expected = typeof a === 'number' + a;

  // break down this expression
}
```

### all primitive operators 3


[parsonized](https://janke-learning.github.io/parsonizer/?snippet=!!%2Ba%20%3D%3D%3D%20Boolean%28a%29%0A%2B_%0A!_%0A!_%0ABoolean%28_%29%0A_%20%3D%3D%3D%20_)  
[on pytut](http://www.pythontutor.com/live.html#code=/*%20values%20to%20try%0A%20%20%22%22,%20%22%20%22,%20true,%20false,%20undefined,%20null,%200,%201,%20-1,%20NaN,%20Infinity%0A*/%0Aconst%20a%20%3D%20%3B%0A%0Aconst%20expected%20%3D%20!!%2Ba%20%3D%3D%3D%20Boolean%28a%29%3B%0A%0A//%20break%20down%20this%20expression&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  /* values to try
    "", " ", true, false, undefined, null, 0, 1, -1, NaN, Infinity
  */
  const a = ;

  const expected = !!+a === Boolean(a);

  // break down this expression
}
```


[TOP](#operator-precedence)

---

## Resources

* [operator precedence: mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
* [operator precedence: scripting master](http://www.scriptingmaster.com/javascript/operator-precedence.asp)
* [operator precedence: dummies](https://www.dummies.com/web-design-development/javascript-operator-precedence/)
* [ast visualizer](https://astexplorer.net/) 
    * explore how JS parses your code and represents operator precedence
    * select to hide everything just above the collapsible tree, makes it readable
    * this tool will be very helpful figuring out order of operations when expanding expressions
        * the deepest operators are executed first, then their parents, ...
    * using this for anything but just expressions will likely be more confusing than helpful
    * this tool doesn't check for syntax errors and doesn't run code, so keep it simple and just copy in the expression. no need for variable declarations


___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
