> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/function-exercises/master/functions.md) into this file and complete the exercises!   
> references: [javascript.info functions](https://javascript.info/function-basics), [function examples to study](https://github.com/janke-learning/function-exercises/blob/master/examples-to-study.md)

# Functions

some exercises to help you understand functions:
* Defining vs. Calling functions
    * Defining: when you write the funciton -> function name() {}.  This creates the function in memory
    * Calling: using the function to compute new values -> name().  This creates a new frame and returns a new value
* Arguments
* Lexical Scope
* Return Values

### Index
* [completed example](#completed-example)
* exercises
    * [number 1](#1)
    * [number 2](#2)
    * [number 3](#3)
    * [number 4](#4)
    * [number 5](#5)
    * [number 6](#6)
    * [number 7](#7)
    * [number 8](#8)
* [resources](#resources)

---

## Completed Example

[on pytut](http://www.pythontutor.com/javascript.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_2%20%2B%20param_3%20%2B%20param_1%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22x%22,%20arg_2%20%3D%20%22z%22,%20arg_3%20%3D%20%22y%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22zyx%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)  
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_2%20%2B%20param_3%20%2B%20param_1%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22x%22,%20arg_2%20%3D%20%22z%22,%20arg_3%20%3D%20%22y%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22zyx%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)
```js
{  // completed example
  function f(param_1, param_2, param_3) {
    var result = param_2 + param_3 + param_1;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "x", arg_2 = "z", arg_3 = "y";
  let return_val = f(arg_1, arg_2, arg_3);

  console.assert(return_val === "zyx", "example: return_val === " + return_val);
}
```

[TOP](#functions)

---

## Exercises

### 1

[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22,%20arg_2%20%3D%20%22%22,%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22zyx%22,%20%221%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=6&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22,%20arg_2%20%3D%20%22%22,%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22zyx%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)
```js
{   // 1
  function f(param_1, param_2, param_3) {
    var result = param_3 + param_1 + param_2;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "", arg_2 = "", arg_3 = "";
  let return_val = f(arg_1, arg_2, arg_3);

  console.assert(return_val === "zyx", "1: return_val === " + return_val);
}
```

### 2

[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22,%20arg_2%20%3D%20%22%22,%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22yxz%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=6&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)    
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1%2C%20param_2%2C%20param_3%29%20%7B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A%2F%2F%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22%2C%20arg_2%20%3D%20%22%22%2C%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1%2C%20arg_2%2C%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22yxz%22%2C%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)
```js
{  // 2
  function f(param_1, param_2, param_3) {
    var result = param_3 + param_1 + param_2;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "", arg_2 = "", arg_3 = "";
  let return_val = f(arg_1, arg_2, arg_3);

  console.assert(return_val === "yxz", "2: return_val === " + return_val);
}
```

### 3

[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20_%20%3D%20param_2%3B%0A%20%20param_2%20%3D%20param_1%3B%0A%20%20param_1%20%3D%20_%3B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22,%20arg_2%20%3D%20%22%22,%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22yxz%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=9&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)   
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1%2C%20param_2%2C%20param_3%29%20%7B%0A%20%20var%20_%20%3D%20param_2%3B%0A%20%20param_2%20%3D%20param_1%3B%0A%20%20param_1%20%3D%20_%3B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A%2F%2F%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22%2C%20arg_2%20%3D%20%22%22%2C%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1%2C%20arg_2%2C%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22yxz%22%2C%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)
```js
{  // 3
  function f(param_1, param_2, param_3) {
    var _ = param_2;
    param_2 = param_1;
    param_1 = _;
    var result = param_3 + param_1 + param_2;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "", arg_2 = "", arg_3 = "";
  let return_val = f(arg_1, arg_2, arg_3);

  console.assert(return_val === "yxz", "3: return_val === " + return_val);
}
```

### 4

[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20%20var%20_%20%3D%20param_2%3B%0A%20%20param_2%20%3D%20param_3%3B%0A%20%20param_3%20%3D%20_%3B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A//%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22,%20arg_2%20%3D%20%22%22,%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22xyz%22,%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=9&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1%2C%20param_2%2C%20param_3%29%20%7B%0A%20%20var%20_%20%3D%20param_2%3B%0A%20%20param_2%20%3D%20param_3%3B%0A%20%20param_3%20%3D%20_%3B%0A%20%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20%20return%20result%3B%0A%7D%3B%0A%0A%2F%2F%20set%20values%20in%20the%20args%20to%20pass%20the%20assert%0Alet%20arg_1%20%3D%20%22%22%2C%20arg_2%20%3D%20%22%22%2C%20arg_3%20%3D%20%22%22%3B%0Alet%20return_val%20%3D%20f%28arg_1%2C%20arg_2%2C%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22xyz%22%2C%20%22return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)
```js
{  // 4
  function f(param_1, param_2, param_3) {
    var _ = param_2;
    param_2 = param_3;
    param_3 = _;
    var result = param_3 + param_1 + param_2;
    return result;
  };

  // set values in the args to pass the assert
  let arg_1 = "", arg_2 = "", arg_3 = "";
  let return_val = f(arg_1, arg_2, arg_3);

  console.assert(return_val === "xyz", "4: return_val === " + return_val);
}
```

### 5

[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20return%20result%3B%0A%7D%3B%0A%0Alet%20x%20%3D%20%22x%22,%20y%20%3D%20%22y%22,%20z%20%3D%20%22z%22%3B%0Alet%20return_val%20%3D%20f%28/*%20pass%20x,%20y%20%26%20z%20in%20the%20right%20order%20*/%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22xyz%22,%20%225%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=6&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)   
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1%2C%20param_2%2C%20param_3%29%20%7B%0A%20var%20result%20%3D%20param_3%20%2B%20param_1%20%2B%20param_2%3B%0A%20return%20result%3B%0A%7D%3B%0A%0Alet%20x%20%3D%20%22x%22%2C%20y%20%3D%20%22y%22%2C%20z%20%3D%20%22z%22%3B%0Alet%20return_val%20%3D%20f%28%2F*%20pass%20x%2C%20y%20%26%20z%20in%20the%20right%20order%20*%2F%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22xyz%22%2C%20%225%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)  
```js
{  // 5
   function f(param_1, param_2, param_3) {
    var result = param_3 + param_1 + param_2;
    return result;
   };

   let x = "x", y = "y", z = "z";
   let return_val = f(/* pass x, y & z in the right order */);

   console.assert(return_val === "xyz", "5: return_val === " + return_val);
}
```

### 6

[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20var%20result%20%3D%20param_2%20%2B%20param_1%20%2B%20param_3%3B%0A%20return%20result%3B%0A%7D%3B%0A%0Alet%20x%20%3D%20%22x%22,%20y%20%3D%20%22y%22,%20z%20%3D%20%22z%22%3B%0Alet%20return_val%20%3D%20f%28/*%20pass%20x,%20y%20%26%20z%20in%20the%20right%20order%20*/%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22xzy%22,%20%226%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=6&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1%2C%20param_2%2C%20param_3%29%20%7B%0A%20var%20result%20%3D%20param_2%20%2B%20param_1%20%2B%20param_3%3B%0A%20return%20result%3B%0A%7D%3B%0A%0Alet%20x%20%3D%20%22x%22%2C%20y%20%3D%20%22y%22%2C%20z%20%3D%20%22z%22%3B%0Alet%20return_val%20%3D%20f%28%2F*%20pass%20x%2C%20y%20%26%20z%20in%20the%20right%20order%20*%2F%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22xzy%22%2C%20%226%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B) 
```js
{  // 6
   function f(param_1, param_2, param_3) {
    var result = param_2 + param_1 + param_3;
    return result;
   };

   let x = "x", y = "y", z = "z";
   let return_val = f(/* pass x, y & z in the right order */);

   console.assert(return_val === "xzy", "6: return_val === " + return_val);
}
```

### 7

[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20var%20result%20%3D%20/*%20arrange%20the%20params%20to%20pass%20the%20assert%20*/%3B%0A%20return%20result%3B%0A%7D%3B%0A%0Alet%20arg_1%20%3D%20%22z%22,%20arg_2%20%3D%20%22y%22,%20arg_3%20%3D%20%22x%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22xzy%22,%20%227%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1%2C%20param_2%2C%20param_3%29%20%7B%0A%20var%20result%20%3D%20%2F*%20arrange%20the%20params%20to%20pass%20the%20assert%20*%2F%3B%0A%20return%20result%3B%0A%7D%3B%0A%0Alet%20arg_1%20%3D%20%22z%22%2C%20arg_2%20%3D%20%22y%22%2C%20arg_3%20%3D%20%22x%22%3B%0Alet%20return_val%20%3D%20f%28arg_1%2C%20arg_2%2C%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22xzy%22%2C%20%227%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)  
```js
{  // 7
   function f(param_1, param_2, param_3) {
    var result = /* arrange the params to pass the assert */;
    return result;
   };

   let arg_1 = "z", arg_2 = "y", arg_3 = "x";
   let return_val = f(arg_1, arg_2, arg_3);

   console.assert(return_val === "xzy", "7: return_val === " + return_val);
}
```

### 8

[on pytut](http://www.pythontutor.com/live.html#code=function%20f%28param_1,%20param_2,%20param_3%29%20%7B%0A%20var%20result%20%3D%20/*%20arrange%20the%20params%20to%20pass%20the%20assert%20*/%3B%0A%20return%20result%3B%0A%7D%3B%0A%0Alet%20arg_1%20%3D%20%22z%22,%20arg_2%20%3D%20%22y%22,%20arg_3%20%3D%20%22x%22%3B%0Alet%20return_val%20%3D%20f%28arg_1,%20arg_2,%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22yxz%22,%20%228%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
[parsonized](http://janke-learning.github.io/parsonizer/?snippet=function%20f%28param_1%2C%20param_2%2C%20param_3%29%20%7B%0A%20var%20result%20%3D%20%2F*%20arrange%20the%20params%20to%20pass%20the%20assert%20*%2F%3B%0A%20return%20result%3B%0A%7D%3B%0A%0Alet%20arg_1%20%3D%20%22z%22%2C%20arg_2%20%3D%20%22y%22%2C%20arg_3%20%3D%20%22x%22%3B%0Alet%20return_val%20%3D%20f%28arg_1%2C%20arg_2%2C%20arg_3%29%3B%0A%0Aconsole.assert%28return_val%20%3D%3D%3D%20%22yxz%22%2C%20%228%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B)  
```js
{  // 8
   function f(param_1, param_2, param_3) {
    var result = /* arrange the params to pass the assert */;
    return result;
   };

   let arg_1 = "z", arg_2 = "y", arg_3 = "x";
   let return_val = f(arg_1, arg_2, arg_3);

   console.assert(return_val === "yxz", "8: return_val === " + return_val);
}
```

---

## Resources

* [pythontutor video](https://www.youtube.com/watch?v=bJUmxDsaduY&list=PLzV58Zm8FuBJFfQN5il3ujx6FDAY8Ds3u&index=6)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
