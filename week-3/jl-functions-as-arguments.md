> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/function-exercises/master/functions-as-arguments.md) into this file and complete the exercises!   

# Functions as Arguments

In JavaScript you can pass functions as arguments.  Since functions are reference types, they will behave a lot like arrays and objects when passed as arguments.  And since they are still functions being called from inside an execution frame, they will still make a callstack like in exercises 3.

### Index:
* [completed example](#completed-example)
* exercises
    * [number 1](#number-1)
    * [number 2](#number-2)
    * [number 3](#number-3)
    * [number 4](#number-4)

---

## completed example

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28param_1,%20param_2%29%20%7B%0A%20%20var%20word_1%20%3D%20param_1%28't',%20'e',%20'a'%29%3B%0A%20%20var%20word_2%20%3D%20param_2%28'e',%20'a',%20't'%29%3B%0A%20%20return%20word_1%20%2B%20'%20'%20%2B%20word_2%3B%0A%7D%0A%0Afunction%20first%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_2%20%2B%20_3%20%2B%20_1%3B%0A%7D%0A%0Afunction%20second%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_3%20%2B%20_1%20%2B%20_2%3B%0A%7D%0A%0Aconst%20result%20%3D%20sentence%28first,%20second%29%3B%0A%0Aconsole.assert%28result%20%3D%3D%3D%20'eat%20tea',%20'result%20%3D%3D%3D%20'%20%2B%20result%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  function sentence(param_1, param_2) {
    var word_1 = param_1('t', 'e', 'a');
    var word_2 = param_2('e', 'a', 't');
    return word_1 + ' ' + word_2;
  }

  function first(_1, _2, _3) {
    return _2 + _3 + _1;
  }

  function second(_1, _2, _3) {
    return _3 + _1 + _2;
  }

  const result = sentence(first, second);

  console.assert(result === 'eat tea', 'result === ' + result);
}
```

[TOP](#functions-as-arguments)

---

## number 1

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28param_1%29%20%7B%0A%20%20var%20word_1%20%3D%20param_1%28/*%20fill%20this%20*/%29%3B%0A%20%20var%20word_2%20%3D%20param_1%28/*%20fill%20this%20*/%29%3B%0A%20%20var%20word_3%20%3D%20param_1%28/*%20fill%20this%20*/%29%3B%0A%20%20return%20word_1%20%2B%20word_2%20%2B%20word_3%3B%0A%7D%0A%0Afunction%20first%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_2%20%2B%20_3%20%2B%20_1%3B%0A%7D%0A%0Aconst%20result%20%3D%20sentence%28first%29%3B%0A%0Aconsole.assert%28result%20%3D%3D%3D%20'eat%20ate%20tea',%20'result%20%3D%3D%3D%20'%20%2B%20result%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  function sentence(param_1) {
    var word_1 = param_1(/* fill this */);
    var word_2 = param_1(/* fill this */);
    var word_3 = param_1(/* fill this */);
    return word_1 + word_2 + word_3;
  }

  function first(_1, _2, _3) {
    return _2 + _3 + _1;
  }

  const result = sentence(first);

  console.assert(result === 'eat ate tea', 'result === ' + result);
}
```

[TOP](#functions-as-arguments)

---

## number 2

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20word_1%20%3D%20param_1%28/*%20fill%20this%20*/%29%3B%0A%20%20var%20word_2%20%3D%20param_2%28/*%20fill%20this%20*/%29%3B%0A%20%20var%20word_3%20%3D%20param_3%28/*%20fill%20this%20*/%29%3B%0A%20%20return%20word_1%20%2B%20word_2%20%2B%20word_3%3B%0A%7D%0A%0Afunction%20first%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_2%20%2B%20_3%20%2B%20_1%20%2B%20'%20'%3B%0A%7D%0Afunction%20second%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_3%20%2B%20_1%20%2B%20_2%20%2B%20'%20'%3B%0A%7D%0Afunction%20third%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_1%20%2B%20_3%20%2B%20_2%3B%0A%7D%0A%0Aconst%20result%20%3D%20sentence%28first,%20second,%20third%29%3B%0A%0Aconsole.assert%28result%20%3D%3D%3D%20'eat%20ate%20tea',%20'result%20%3D%3D%3D%20'%20%2B%20result%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  function sentence(param_1, param_2, param_3) {
    var word_1 = param_1(/* fill this */);
    var word_2 = param_2(/* fill this */);
    var word_3 = param_3(/* fill this */);
    return word_1 + word_2 + word_3;
  }

  function first(_1, _2, _3) {
    return _2 + _3 + _1 + ' ';
  }
  function second(_1, _2, _3) {
    return _3 + _1 + _2 + ' ';
  }
  function third(_1, _2, _3) {
    return _1 + _3 + _2;
  }

  const result = sentence(first, second, third);

  console.assert(result === 'eat ate tea', 'result === ' + result);
}
```

[TOP](#functions-as-arguments)

---

## number 3

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20word_1%20%3D%20param_1%28't',%20'a',%20'e'%29%3B%0A%20%20var%20word_2%20%3D%20param_2%28'e',%20't',%20'a'%29%3B%0A%20%20var%20word_3%20%3D%20param_3%28'a',%20't',%20'e'%29%3B%0A%20%20return%20word_1%20%2B%20word_2%20%2B%20word_3%3B%0A%7D%0A%0Afunction%20first%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20/*%20fill%20this%20*/%3B%0A%7D%0Afunction%20second%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20/*%20fill%20this%20*/%3B%0A%7D%0Afunction%20third%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20/*%20fill%20this%20*/%3B%0A%7D%0A%0Aconst%20result%20%3D%20sentence%28first,%20second,%20third%29%3B%0A%0Aconsole.assert%28result%20%3D%3D%3D%20'eat%20ate%20tea',%20'result%20%3D%3D%3D%20'%20%2B%20result%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  function sentence(param_1, param_2, param_3) {
    var word_1 = param_1('t', 'a', 'e');
    var word_2 = param_2('e', 't', 'a');
    var word_3 = param_3('a', 't', 'e');
    return word_1 + word_2 + word_3;
  }

  function first(_1, _2, _3) {
    return /* fill this */;
  }
  function second(_1, _2, _3) {
    return /* fill this */;
  }
  function third(_1, _2, _3) {
    return /* fill this */;
  }

  const result = sentence(first, second, third);

  console.assert(result === 'eat ate tea', 'result === ' + result);
}
```

[TOP](#functions-as-arguments)

---

## number 4

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20word_1%20%3D%20param_1%28't',%20'a',%20'e'%29%3B%0A%20%20var%20word_2%20%3D%20param_2%28'e',%20't',%20'a'%29%3B%0A%20%20var%20word_3%20%3D%20param_3%28'a',%20't',%20'e'%29%3B%0A%20%20return%20word_1%20%2B%20word_2%20%2B%20word_3%3B%0A%7D%0A%0Afunction%20first%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_2%20%2B%20_3%20%2B%20_1%3B%0A%7D%0Afunction%20second%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_3%20%2B%20_2%20%2B%20_1%3B%0A%7D%0Afunction%20third%28_1,%20_2,%20_3%29%20%7B%0A%20%20return%20_3%20%2B%20_2%20%2B%20_1%3B%0A%7D%0A%0Aconst%20result%20%3D%20sentence%28/*%20fill%20this%20*/%29%3B%0A%0Aconsole.assert%28result%20%3D%3D%3D%20'eat%20ate%20tea',%20'result%20%3D%3D%3D%20'%20%2B%20result%29%3B&cumulative=false&curInstr=2&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  function sentence(param_1, param_2, param_3) {
    var word_1 = param_1('t', 'a', 'e');
    var word_2 = param_2('e', 't', 'a');
    var word_3 = param_3('a', 't', 'e');
    return word_1 + word_2 + word_3;
  }

  function first(_1, _2, _3) {
    return _2 + _3 + _1;
  }
  function second(_1, _2, _3) {
    return _3 + _2 + _1;
  }
  function third(_1, _2, _3) {
    return _3 + _2 + _1;
  }

  const result = sentence(/* fill this */);

  console.assert(result === 'eat ate tea', 'result === ' + result);
}
```

[TOP](#functions-as-arguments)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
