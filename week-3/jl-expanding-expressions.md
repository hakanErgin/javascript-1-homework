> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/expanding/master/exercises-operators-only.md) into this file and complete the exercises!   

# Operator-Only Exercises

Some single-line expressions to expand with only operators.  

Be sure to practice _incremental refactoring_ by running your tests every time you expand an operator, like you see in [these worked examples](./worked-expressions.md).

You'll be presented with a single line expression.  your task is to write enough test cases to begin understanding it, refactor it into steps according to operator precedence, then study your test cases in more detail.  

The main objective for these exercises is that you become comfortable stepping through and working with complex JS expressions, not that your learn everything about how all operators work.  Understanding implicit coercion is very important but will be covered in depth later on.  


### Index
* [learning objectives](#learning-objectives)
* Testing Tools
    * [test case format](#test-case-format)
    * [run\_tests function](#run-tests-function)
* completed examples
    * [one](#one)
    * [two](#two)
    * [three](#three)
    * [four](#four)
    * [five](#five)
* exercises
    * [types & casting (3)](#types-and-casting)
    * [logical operators (3)](#logical-operators)
    * [arithmetic operators (3)](#arithmetic-operators)
    * [all primitive operators (3)](#all-primitive-operators)
* [resources](#resources)

---

## learning objectives


* which operators exist in JS
* reading this [operator precedence table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
* breaking down long expressions (super helpful for debugging, reading & writing code)
* statements vs. expressions

[TOP](#operator-only-exercises)

---

## Testing Tools

### Test Case Format

```js
const test_cases = [
    {name:'meaningful name', args:['the inputs', 'for this snippet'], expected: 'what it should output'},
    {name:'another test case', args:['different', 'inputs'], expected: 'the expected output'},
    ...
  ];
```

### Run Tests Function

__paste this into your console before moving on__
```js
function run_tests(_target, _cases) {
  console.groupCollapsed('<- click this arrow to see the function')
  console.log(_target.toString());
  console.groupEnd();

  for (let t_case of _cases) {
    
    // create variables for readability
    const expected = t_case.expected;
    const args = t_case.args;
    
    // run function with test case
    const actual = _target(...args);

    // compare
    let pass;
    if (typeof expected === 'object' && expected !== null) {
      const _actual = JSON.stringify(actual);
      const _expected = JSON.stringify(expected);
      pass = _actual === _expected;
    } else if ( expected !== expected ) {
      pass = actual !== actual;
    } else {
      pass = actual === expected;
    };

    // communicate result to developer 
    if (pass) {
      console.groupCollapsed(`%cPASS: ${t_case.name}`, 'color:green');
    } else {
      console.groupCollapsed(`%c: ${t_case.name}`, 'color:red');
      console.log("%cactual: ",  'color:orange', typeof actual +", "+ actual);
    };

    for (let i = 0; i < args.length; i++) {
      console.log(`arg ${i+1}: ${typeof args[i]},`, args[i]);
    }
    console.log("%cexpected: ", 'color:blue', typeof expected +", "+ expected);
    console.groupEnd();
  };
}
```

[TOP](#operator-only-exercises)

---

## Completed Examples

### One

uncomment the refactors one at a time to see that they all pass the same tests.

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=Number%28Boolean%28String%28a%29%29%29%0AString%28_%29%0ABoolean%28_%29%0ANumber%28_%29)  
```js
test_cases = [
  {name: 'false', args: [false], expected: 1},
  {name: 'NaN', args: [NaN], expected: 1},
  {name: '""', args: [""], expected: 0},
  {name: 'null', args: [null], expected: 1},
  {name: 'undefined', args: [undefined], expected: 1},
  {name: '0', args: [0], expected: 1},
];
/* // original challenge
function expression(a) {
  return  Number(Boolean(String(a)));
}   */
/* // first refactor
function expression(a) {
  const op_1 = String(a);
  return  Number(Boolean(op_1));
}   */
/* // second refactor
function expression(a) {
  const op_1 = String(a);
  const op_2 = Boolean(op_1);
  return  Number(op_2);
}   */

// fully expanded
function expression(a) {
  const op_1 = String(a);
  const op_2 = Boolean(op_1);
  const op_3 = Number(op_2);
  return  op_3;
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)

---

### Two

uncomment the refactors one at a time to see that they all pass the same tests.

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=%28a%20%2B%20b%29%20%3D%3D%20%28a%20%3C%20c%29%0A_%20%2B%20_%0A_%20%3C%20_%0A_%20%3D%3D%20_%0A%0A%0A%0A)  
```js
test_cases = [
  {name: 'false, true, false', args: [false, true, false], expected: false},
  {name: '0, 1, 0', args: [0, 1, 0], expected: false},
  {name: '"", " ", ""', args: ["", " ", ""], expected: true},
  {name: '2, -1, 3', args: [2, -1, 3], expected: true},
  {name: 'null, undefined, NaN', args: [null, undefined, NaN], expected: false},
];
/* // original challenge
function expression(a, b, c) {
  return (a + b) == (a < c);
}   */
/* // first refactor
function expression(a, b, c) {
  const op_1 = a + b;
  return op_1 == (a < c);
}   */
/* // second refactor
function expression(a, b, c) {
  const op_1 = a + b;
  const op_2 = a < c;
  return op_1 == op_2;
}   */

// fully expanded
function expression(a, b, c) {
  const op_1 = a + b;
  const op_2 = a < c;
  const op_3 = op_1 == op_2;
  return op_3;
}   
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)

---

### Three

uncomment the refactors one at a time to see that they all pass the same tests.

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=b%20%26%26%20typeof%20a%20%3D%3D%3D%20'string'%0Atypeof%20_%0A_%20%3D%3D%3D%20'string'%0A_%20%26%26%20_)  
```js
test_cases = [
  {name: 'false, true', args: [false, true], expected: false},
  {name: 'false, "true"', args: [false, "true"], expected: false},
  {name: 'true, 0', args: [true, 0], expected: 0},
  {name: 'true, ƒalse', args: [true, false], expected: false},
  {name: 'true, "ƒalse"', args: [true, "false"], expected: false},
  {name: '"", ""', args: ["", ""], expected: ""},
  {name: '"", " "', args: ["", " "], expected: true},
];
/* // original challenge
function expression(a, b) {
  return b && typeof a === 'string';
}  */
/* // first refactor
function expression(a, b) {
  const op_1 = typeof a;
  return b && op_1 === 'string';
}  */
/* // second refactor
function expression(a, b) {
  const op_1 = typeof a;
  const op_2 = op_1 === 'string';
  return b && op_2;
}  */

// expanded expression
function expression(a, b) {
  const op_1 = typeof a;
  const op_2 = op_1 === 'string';
  const op_3 = b && op_2;
  return op_3;
}  
run_tests(expression, test_cases);
```

> short-circuiting with ```||``` and ```&&```, an advanced gotcha: [worked expansion](./worked-short-circuiting.md), [codeburst: using || cleverly](https://codeburst.io/javascript-what-is-short-circuit-evaluation-ff22b2f5608c)  
> The examples on this page do not replicate short-circuiting, and you don't have to either in the assignments

[TOP](#operator-only-exercises)

---


### Four

uncomment the refactors one at a time to see that they all pass the same tests.

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=%28b%20%26%26%20typeof%20a%29%20%3D%3D%3D%20'string'%0Atypeof%20_%0A_%20%26%26%20_%0A_%20%3D%3D%3D%20'string')  

```js
test_cases = [
  {name: '"", NaN', args: ["", NaN], expected: false},
  {name: 'NaN, ""', args: [NaN, ""], expected: false},
  {name: '" ", NaN', args: ["", NaN], expected: false},
  {name: 'NaN, " "', args: [NaN, " "], expected: false},
  {name: '"string", NaN', args: ["string", NaN], expected: false},
  {name: 'NaN, "string"', args: [NaN, "string"], expected: false},
  {name: '"string", true', args: ["", NaN], expected: false},
];
/* // original challenge
function expression(a, b) {
  return (b && typeof a) === 'string';
}   */
/* // first refactor
function expression(a, b) {
  const op_1 = typeof a;
  return (b && op_1) === 'string';
}   */
/* // second refactor
function expression(a, b) {
  const op_1 = typeof a;
  const op_2 = b && op_1;
  return op_2 === 'string';
}   */

// final expansion
function expression(a, b) {
  const op_1 = typeof a;
  const op_2 = b && op_1;
  const op_3 = op_2 === 'string'
  return op_3;
}   
run_tests(expression, test_cases);
```

> __challenge question:__ can this function ever return true?  
> Either explain why it's impossible, or write a test case that will return true.

[TOP](#operator-only-exercises)

---

### Five

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=%28%20a%20%3E%20Number%28b%29%20%29%20%7C%7C%20String%28c%29%0ANumber%28_%29%0A_%20%3E%20_%0AString%28_%29%0A_%20%7C%7C%20_)  

```js
test_cases = [
  {name: '0, 1, null', args:[0, 1, null], expected: "null"},
  {name: '1, 0, null', args:[1, 0, null], expected: true},
  {name: '1, "e", null', args:[1, 'e', null], expected: "null"},
  {name: '"e", "e", null', args:['e', 'e', null], expected: "null"},
  {name: '3, "2", null', args:[3, '2', null], expected: true},
  {name: '"2", "2", undefined', args:['2', '2', undefined], expected: 'undefined'},
];
/* // original challenge
function expression(a, b, c) {
  return ( a > Number(b) ) || String(c);
}   */
/* // first refactor
function expression(a, b, c) {
  const op_1 = Number(b);
  return ( a > op_1 ) || String(c);
}   */
/* // second refactor
function expression(a, b, c) {
  const op_1 = Number(b);
  const op_2 = a > op_1;
  return op_2 || String(c);
}   */
/* // third refactor
function expression(a, b, c) {
  const op_1 = Number(b);
  const op_2 = a > op_1;
  const op_3 = String(c);
  return op_2 || op_3;
}   */

// final expansion
function expression(a, b, c) {
  const op_1 = Number(b);
  const op_2 = a > op_1;
  const op_3 = String(c);
  const op_4 = op_2 || op_3;
  return op_4;
}
run_tests(expression, test_cases);
```

> short-circuiting with ```||``` and ```&&```, an advanced gotcha: [worked expansion](./worked-short-circuiting.md), [codeburst: using || cleverly](https://codeburst.io/javascript-what-is-short-circuit-evaluation-ff22b2f5608c)  
> The examples on this page do not replicate short-circuiting, and you don't have to either in the assignments


[TOP](#operator-only-exercises)

---

## Types and Casting

### types & casting 1

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=typeof%20a%20%3D%3D%3D%20typeof%20b%0Atypeof%20a%0Atypeof%20b%0A_%20%3D%3D%3D%20_)  
```js
test_cases = [
  {name: 'null, null', args: [null, null], expected: null},
];
function expression(a, b) {
  return typeof a === typeof b;
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)

### types & casting 2

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=Boolean%28a%29%20!%3D%3D%20Boolean%28b%29%0ABoolean%28a%29%0ABoolean%28b%29%0A_%20!%3D%3D%20_)  
```js
test_cases = [
  {name: 'null, null', args: [null, null], expected: null},
];
function expression(a, b) {
  return Boolean(a) !== Boolean(b);
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)

### types & casting 3

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=Boolean%28b%29%20%3D%3D%3D%20Boolean%28Number%28a%29%29%0ABoolean%28b%29%0ANumber%28a%29%0ABoolean%28_%29%0A_%20%3D%3D%3D%20_)   
```js
test_cases = [
  {name: 'null, null', args: [null, null], expected: null},
];
function expression(a, b) {
  return Boolean(b) === Boolean(Number(a));
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)

---


## Logical Operators


### logical operators 1

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=!%28a%20%26%26%20!b%29%0A!_%0A_%20%26%26%20_%0A!%28_%29%0A%0A)  
```js
test_cases = [
  {name: 'null, null', args: [null, null], expected: null},
];
function expression(a, b) {
  return !(a && !b);
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)


### logical operators 2

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=!!a%20%7C%7C%20!!b%0A!a%0A!_%0A!b%0A!_%0A_%20%7C%7C%20_)  
```js
test_cases = [
  {name: 'null, null', args: [null, null], expected: null},
];
function expression(a, b) {
  return !!a || !!b;
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)


### logical operators 3

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=!!a%20%7C%7C%20!!b%0A!a%0A!_%0A!b%0A!_%0A_%20%7C%7C%20_)  
```js
test_cases = [
  {name: 'null, null, null', args: [null, null, null], expected: null},
];
function expression(a, b, c) {
  return a || b && c || a;
}
run_tests(expression, test_cases);
```


[TOP](#operator-only-exercises)

---

## Arithmetic Operators

### arithmetic operators 1

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=-%28a%20%2B%20b%29%20*%20c%0A_%20%2B%20_%0A-%28_%29%0A_%20*%20_)  
```js
test_cases = [
  {name: 'null, null, null', args: [null, null, null], expected: null},
];
function expression(a, b, c) {
  return -(a + b) * c;
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)


### arithmetic operators 2

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=a%20**%20b%20%2F%20%2Bc%0A%2B_%0A_%20**%20_%0A_%20%2F%20_)  
```js
test_cases = [
  {name: 'null, null, null', args: [null, null, null], expected: null},
];
function expression(a, b, c) {
  return a ** b / +c;
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)



### arithmetic operators 3

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=b%20%25%20c%20-%20a%20**%20c%20%2F%20b%0A_%20**%20_%0A_%20%2F%20_%0A_%20%25%20_%0A_%20-%20_)  
```js
test_cases = [
  {name: 'null, null, null', args: [null, null, null], expected: null},
];
function expression(a, b, c) {
  return b % c - a ** c / b;
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)

---

## All Primitive Operators


### all primitive operators 1

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=a%20%25%20b%20%7C%7C%20!!a%0A_%20%25%20_%0A!a%0A!_%0A_%20%7C%7C%20_)  
```js
test_cases = [
  {name: 'null, null', args: [null, null], expected: null},
];
function expression(a, b) {
  return a % b || !!a;
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)



### all primitive operators 2

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=typeof%20a%20%3D%3D%3D%20'number'%20%2B%20a%0Atypeof%20_%0A_%20%3D%3D%3D%20_%0A_%20%2B%20_)  
```js
test_cases = [
  {name: 'null, null', args: [null, null], expected: null},
];
function expression(a, b) {
  return typeof a === 'number' + a;
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)

### all primitive operators 3

[parsonized operators](https://janke-learning.github.io/parsonizer/?snippet=!!%2Ba%20%3D%3D%3D%20Boolean%28a%29%0A%2B_%0A!_%0A!_%0ABoolean%28_%29%0A_%20%3D%3D%3D%20_)  
```js
test_cases = [
  {name: 'null', args: [null], expected: null},
];
function expression(a) {
  return !!+a === Boolean(a);
}
run_tests(expression, test_cases);
```

[TOP](#operator-only-exercises)

---

## Resources

* [test cases](https://github.com/janke-learning/test-cases)
* [worked examples to study](./worked-expressions.md)
* [operator precedence: mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
* [operator precedence: janke](https://github.com/janke-learning/operator-precedence)
* [operator precedence: scripting master](http://www.scriptingmaster.com/javascript/operator-precedence.asp)
* [operator precedence: dummies](https://www.dummies.com/web-design-development/javascript-operator-precedence/)
* [ast visualizer](https://astexplorer.net/) 
    * explore how JS parses your code and represents operator precedence
    * select to hide everything just above the collapsible tree, makes it readable
    * this tool will be very helpful figuring out order of operations when expanding expressions
        * the deepest operators are executed first, then their parents, ...
    * using this for anything but just expressions will likely be more confusing than helpful
    * this tool doesn't check for syntax errors and doesn't run code, so keep it simple and just copy in the expression. no need for variable declarations


[TOP](#operator-only-exercises)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
