> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/implicit-coercion/master/replicate-loose-equality.md) into this file and complete the exercises!   

# Replicate Loose Equality


["What I cannot create, I do not understand."](https://blog.codinghorror.com/when-understanding-means-rewriting/)  

Gain a deeper understanding of implicit coercion and the tricky ```==``` operator by developing your own replication for primitive values onlu using a [TDD methodology](https://github.com/janke-learning/tdd).  


### Index
* [describing behavior](#describing-behavior)
* [run\_tests function](#run--tests-function)
* [test driven development](#test-driven-development)
* [study ```==```](#study-it)
* [replicate ```==```](#replicate-it)

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

[TOP](#replicate-loose-equality)

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

[TOP](#replicate-loose-equality)

---

## Test Driven Development

Very briefly this is a development philosophy that says to write all the tests your code should pass, then write the code to pass the tests.  

In the following exercise you will be practicing TDD by starting with the ```test_cases```, and then writing the ```==``` replication to pass the tests.

For more info and TDD exercises [check this out](https://github.com/janke-learning/tdd).

[TOP](#replicate-loose-equality)

---

### Study It

Study [this comparison table](https://dorey.github.io/JavaScript-Equality-Table/).     
Play around with this [interactive table](https://janke-learning.org/equalities-coercion/).    
Then test yourself with [this quiz](https://eqeq.js.org).  


[TOP](#replicate-loose-equality)

---

### Replicate It

It's your turn.  In this exercise you'll write your own replication of the == operator for primitive values 'number', 'string', 'boolean', 'null' and 'undefined'.  We've provided you with a whole bunch of test cases and a commented starter function.  It's up to you to do the rest!  (hint: try focusing on one comment at a time, pass it then, move on to pass the next. also, the test cases are organized to match up with the three sections of the function)

__Passing Test Cases:__ you will use these tests to develop your replication of ```==```.  Copy-paste them into the console and hit enter.  to make sure they are loaded type ```test_cases``` into the console. Feel free to add more passing test cases before moving on the replication!
```js
test_cases = [
  { name: 'null, undefined', args: [null, undefined], expected: true},
  { name: 'undefined, null', args: [undefined, null], expected: true},
  { name: 'null, null', args: [null, null], expected: true},
  { name: 'undefined, undefined', args: [undefined, undefined], expected: true},
  { name: 'null, "anything else"', args: [null, "anything else"], expected: false},
  { name: 'undefined, "anything else"', args: [undefined, "anything else"], expected: false},
  { name: 'true, false', args: [true, false], expected: false},
  { name: 'false, false', args: [false, false], expected: true},
  { name: '3, 3', args: [3, 3], expected: true},
  { name: '3.0, 3', args: [3.0, 3], expected: true},
  { name: '+0, -0', args: [+0, -0], expected: true},
  { name: '"\t", "\t"', args: ["\t", '\t'], expected: true},
  { name: '-3, +3', args: [-3, +3], expected: false},
  { name: '3, "3"', args: [3, "3"], expected: true},
  { name: '"3", 3', args: ["3", 3], expected: true},
  { name: '"3", "3"', args: ["3", "3"], expected: true},
  { name: 'true, 1', args: [true, 1], expected: true},
  { name: 'false, 0', args: [false, 0], expected: true},
  { name: 'false, ""', args: [false, ""], expected: true},
  { name: '0, ""', args: [0, ""], expected: true},
  { name: '"e", true', args: ["e", true], expected: false},
  { name: 'undefined, ""', args: [undefined, ""], expected: false}
];
```

__Native Operation:__ Before moving on, copy-paste this code into the console and hit enter. Study the test results to build a first understanding of how ```==``` works. (if there are any red test cases, something went wrong!)
```js
{
  function loose_equality(a, b) {
    return a == b;
  }
  run_tests(loose_equality, test_cases);
}
```

__Your Replication:__ Your turn!  Paste the code below into the console and begin developing your own replication of the ```==``` operator. Write little bits of code at once and run the code frequently.  Try perhaps implementing one comment at a time or to pass one test case at a time.   
Once you've passed all the tests, paste your code back into this markdown for studying later!
```js
{
  function loose_replication(a, b) { 
    // if both a and b are null or undefined, return true
    // if only one is null or undefined, return false
  
    // if both arguments are the same type (num, string, or bool)
    //  compare them with === and return the result
  
    // if both are not the same type
    //  make sure both are type 'number'
    //  compare them with ===, and return the result
  }
  run_tests(loose_replication, test_cases);
}
```

[TOP](#replicate-loose-equality)

---

> [a complete replication of ```==```](https://gist.github.com/qntm/d899c00aa1ac2c663ac6db23bcffcaba), not just for primitives

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
