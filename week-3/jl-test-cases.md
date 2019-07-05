> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/test-cases/master/README.md) into this file and complete the exercises!   
> [data types](https://javascript.info/types), [type conversions](https://javascript.info/type-conversions), [operators](https://javascript.info/operators), [comparisons](https://javascript.info/comparison)

# Test Cases

Learn about test cases, a great way to understand code.  And learn a bit out JS operators while you're at it.

### Index:
* [describing behavior](#describing-behavior)
* [run\_tests function](#run-tests-function)
* [examples to study](#examples-to-study)
    * [failing test cases](#failing-test-cases)
    * [plus](#plus)
    * [loose equality](#loose-equality)
* [exercises](#exercises)
    * [strict equality](#strict-equality)
    * [typeof](#typeof)
    * [boolean](#boolean)
    * [number](#number)
    * [or](#or)
    * [and](#and)
    * [not](#not)
    * [ternary](#ternary)
    * [less than](#less-than)
    * [greater than](#greater-than)
    * [subtraction](#subtraction)
* [resources](#resources)

---

## Describing Behavior

Code's behavior is what has changed in your program _after_ the code has executed, implementation is the lines of text that make up the code.  This exercise will introduce how to understand behavior using __test cases__.

Practically speaking you can think of test cases as just inputs and outputs.   What values went into the function, and what values come out of the function?  The test case will contain the input-output pairs that your function _should_ implement, a test case fails if the function returns something else.  

Test cases may be relatively easy to read and use, but writing good ones can be tricky.  You have to think about all possible strange combinations and fringe cases. So don't worry about writing the perfect test cases yet, just do your best and compare with a friend to help each other understand how you thought of your test cases.

For this exercise you will write test cases in this format:
```js
test_cases = [
    {name:'meaningful name', args:['the inputs', 'for this snippet'], expected: 'what it should output'},
    {name:'another test case', args:['different', 'inputs'], expected: 'the expected output'},
  ];
```

> DISCLAIMER: 
> * In this exercise you are learning to write test cases for existing code.  The code is always right. If your test fails, change it.   
> * In the real world it will usually be the oposite. The tests should descibe the code.  If the tests fail, change the code.

[TOP](#test-cases)

---

## run\_tests Function

To check if your function passes all of it's test cases, we'll be using this function.  It takes two arguments (the function to test, and the test cases), and console.log's a message for every test case that fails.

Study it for a minute then paste it in the console, the exercises below won't work otherwise.  If you don't understand entirely how this function works that's okay.  The main objective for this exercise is to write & use test cases, understand JS operators.  

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

[TOP](#test-cases)

---

## Examples to Study

### Failing Test Cases

notice: in all of these exercises it is your test cases that need to change if they fail.  JS operators are always right, you must change your expectations until they match the actual behavior.
```js
{
  const test_cases = [
      {name: '3', args: [3], expected: 3},
      {name: 'null', args: [null], expected: 'object'},
      {name: 'true', args: [true], expected: '1'},
      {name: 'false', args: [false], expected: '0'},
    ];
  function to_string(a) {
    return String(a);
  }
  run_tests(to_string, test_cases);
}
```


### Plus

```js
{
  const test_cases = [
      {name: 'string, number', args: ['e', 1], expected: 'e1'},
      {name: 'string, null', args: ['e', null], expected: 'enull'},
      {name: 'string, undefined', args: ['e', undefined], expected: 'eundefined'},
      {name: 'string, boolean', args: ['e', false], expected: 'efalse'},
      {name: 'number, number', args: [1, -1], expected: 0},
      {name: 'true, number', args: [true, 1], expected: 2},
      {name: 'false, number', args: [false, 1], expected: 1},
      {name: 'null, number', args: [null, 1], expected: 1},
      {name: 'undefined, number', args: [undefined, 1], expected: NaN},
    ];
  function plus(a, b) {
    return a + b;
  }
  run_tests(plus, test_cases);
}
```

### Loose Equality

```js
{
  const test_cases = [
      {name: 'null, undefined', args: [null, undefined], expected: true},
      {name: 'null, null', args: [null, null], expected: true},
      {name: 'undefined, undefined', args: [undefined, undefined], expected: true},
      {name: 'null, ""', args: [null, ""], expected: false},
      {name: 'null, 0', args: [null, 0], expected: false},
      {name: 'null, false', args: [null, false], expected: false},
      {name: 'undefined, ""', args: [undefined, ""], expected: false},
      {name: 'undefined, 0', args: [undefined, 0], expected: false},
      {name: 'undefined, false', args: [undefined, false], expected: false},
      {name: 'true, false', args: [true, false], expected: false},
      {name: 'true, true', args: [true, true], expected: true},
      {name: 'false, false', args: [false, false], expected: true},
      {name: '3, "3"', args: [3, "3"], expected: true},
      {name: 'true, 1', args: [true, 1], expected: true},
      {name: 'false, 0', args: [false, 0], expected: true},
      {name: 'true, " "', args: [true, " "], expected: false},
      {name: 'false, "', args: [false, ""], expected: true},
      {name: '0, ""', args: [0, ""], expected: true}
    ];
  function loose_equality(a, b) {
    return a == b;
  }
  run_tests(loose_equality, test_cases);
}
```

[TOP](#test-cases)

---

## Exercises

These exercises are a bit backwards, usually as a developer you will write complete test cases then make sure your code passes them.  To complete these exercises you will be writing test cases that pass functions we give you.  If a test case fails it's the the test case that is wrong, go back to that case and fix it.

Writing test cases just happens to be the other best way to understand how code works.  The first best way is to [rewrite it yourself](https://blog.codinghorror.com/when-understanding-means-rewriting/) like in the Implicit Coercion exercises.

(test cases for these exercises should be limited to primitive types - Number, Boolean, String, Null, Undefined)


### strict equality

```js
{
  const test_cases = [
      {name: '3, 3', args: [3, 3], expected: true},
      {name: '3, "3"', args: [3, "3"], expected: false},
      /* write 8 more passing test cases */
    ];
  function strict_equality(a, b) {
    return a === b;
  }
  run_tests(strict_equality, test_cases);
}
```

[TOP](#test-cases)

### typeof

```js
{
  const test_cases = [
      {name: 'null', args: [null], expected: 'object'},
      {name: 'undefined', args: [undefined], expected: 'undefined'},
      /* write 6 more passing test cases */
    ];
  function _typeof(a) {
    return typeof a;
  }
  run_tests(_typeof, test_cases);
}
```

[TOP](#test-cases)

### Boolean

```js
{
  const test_cases = [
      {name: 'null', args: [null], expected: false},
      {name: 'undefined', args: [undefined], expected: false},
      /* write 10 more passing test cases */
    ];
  function to_boolean(a) {
    return Boolean(a);
  }
  run_tests(to_boolean, test_cases);
}
```

[TOP](#test-cases)

### Number

```js
{
  const test_cases = [
      {name: 'null', args: [null], expected: 0},
      {name: 'undefined', args: [undefined], expected: NaN},
      /* write 10 more passing test cases */
    ];
  function to_number(a) {
    return Number(a);
  }
  run_tests(to_number, test_cases);
}
```

[TOP](#test-cases)

### or

[replication](https://github.com/janke-learning/truthiness#or-operator)  
```js
{
  const test_cases = [
      {name: '1, 1', args: [1, 1], expected: 1},
      {name: '0, 1', args: [0, 1], expected: 1},
      {name: '1, 0', args: [1, 0], expected: 1},
      {name: '0, 0', args: [0, 0], expected: 0},
      /* write 10 more passing test cases */
    ];
  function or(a, b) {
    return a || b;
  }
  run_tests(or, test_cases);
}
```

[TOP](#test-cases)

### and

[replication](https://github.com/janke-learning/truthiness#and-operator)  
```js
{
  const test_cases = [
      {name: '1, 1', args: [1, 1], expected: 1},
      {name: '0, 1', args: [0, 1], expected: 0},
      {name: '1, 0', args: [1, 0], expected: 0},
      {name: '0, 0', args: [0, 0], expected: 0},
      /* write 10 more passing test cases */
    ];
  function and(a, b) {
    return a && b;
  }
  run_tests(and, test_cases);
}
```

[TOP](#test-cases)

### not

[replication](https://github.com/janke-learning/truthiness#not-operator)  
```js
{
  const test_cases = [
      {name: '1', args: [1], expected: false},
      {name: '0', args: [0], expected: true},
      /* write 10 more passing test cases */
    ];
  function not(a) {
    return !a;
  }
  run_tests(not, test_cases);
}
```

[TOP](#test-cases)

### ternary

[replication](https://github.com/janke-learning/truthiness#not-operator)  
```js
{
  const test_cases = [
      {name: '1, "x", "y"', args: [1, 'x', 'y'], expected: 'x'},
      {name: '0, "x", "y"', args: [0, 'x', 'y'], expected: 'y'},
      /* write 10 more passing test cases */
    ];
  function ternary(a, b, c) {
    return a ? b : c ;
  }
  run_tests(ternary, test_cases);
}
```

[TOP](#test-cases)


### greater than

rules for implicit coercion:
* If both operands are numbers, perform a numeric comparison.
* If both operands are strings, compare the [character codes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt) for each. sort of like alphabetical order.
* If one operand is a number, convert the other operand to a number and perform a numeric comparison.
* careful of NaN and values that convert to NaN. 
```js
{
  const test_cases = [
      {name: 'true, 0', args: [true, 0], expected: true},
      {name: 'true, 1', args: [true, 1], expected: false},
      {name: 'false, 0', args: [false, 0], expected: false},
      {name: 'false, 1', args: [false, 1], expected: false},
      /* write 4 more passing test cases with only strings */
      /* write 6 more passing test cases without NaN values */
      /* write 4 more passing test cases with NaN values */
    ];
  function greater_than(a, b) {
    return a > b;
  }
  run_tests(greater_than, test_cases);
}
```

[TOP](#test-cases)


### less than

rules for implicit coercion:
* If both operands are numbers, perform a numeric comparison.
* If both operands are strings, compare the [character codes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt) for each. sort of like alphabetical order.
* If one operand is a number, convert the other operand to a number and perform a numeric comparison.
* careful of NaN and values that cast to NaN. 
```js
{
  const test_cases = [
      {name: 'true, 0', args: [true, 0], expected: false},
      {name: 'true, 1', args: [true, 1], expected: false},
      {name: 'false, 0', args: [false, 0], expected: false},
      {name: 'false, 1', args: [false, 1], expected: true},
      /* write 4 more passing test cases with only strings */
      /* write 6 more passing test cases without NaN values*/
      /* write 4 more passing test cases with NaN values*/
    ];
  function less_than(a, b) {
    return a < b;
  }
  run_tests(less_than, test_cases);
}
```

[TOP](#test-cases)

    

### subtraction

implicit coercion with all mathematical operators (except for +) is pretty simple:
* convert everything to a number, then do math on them
* be aware of NaN values!
```js
{
  const test_cases = [
      {name: 'true, 0', args: [true, 0], expected: 1},
      {name: 'true, 1', args: [true, 1], expected: 0},
      {name: 'false, 0', args: [false, 0], expected: 0},
      {name: 'false, 1', args: [false, 1], expected: -1},
      /* write 5 more passing test cases without NaN values*/
      /* write 5 more passing test cases with NaN values*/
    ];
  function subtraction(a, b) {
    return a - b;
  }
  run_tests(subtraction, test_cases);
}
```

[TOP](#test-cases)



---

## Resources

* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)
* [javascript.info](https://javascript.info/operators)



[TOP](#test-cases)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
