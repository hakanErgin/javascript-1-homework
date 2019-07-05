> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/function-exercises/master/callstack.md) into this file and complete the exercises!   

# Sentences

defining and calling functions from _within_ functions! no. way.

yups.  You can!  that's how the __callstack__ is made, you stack up function calls.

It sounds complicated at first, but after some practice you'll find it's not so bad.  calling a function from inside another function (inside a new _lexical scope_) is no different than calling one from the global scope.  

### Index
* completed examples
    * [tailor](#tailor)
    * [space capes](#space-capes)
* warm-ups
    * [tour 1](#tour-1)
    * [tour 2](#tour-2)
* exercises
    * [eat ate tea 1](#1)
    * [eat ate tea 2](#2)
    * [space capes 1](#3)
    * [space capes 2](#4)
    * [cruel ulcer 1](#5)
    * [cruel ulcer 2](#6)
    * [cruel ulcer 3](#7)

---

## Completed Examples

### Tailor

[on pytut](http://www.pythontutor.com/javascript.html#code=function%20a_word%28_1,%20_2,%20_3,%20_4,%20_5,%20_6%29%20%7B%20%0A%20%20%0A%20%20function%20tailor%28_a,%20_b,%20_c,%20_d,%20_e,%20_f%29%20%7B%0A%20%20%20%20return%20_a%20%2B%20_c%20%2B%20_b%20%2B%20_d%20%2B%20_f%20%2B%20_e%3B%0A%20%20%7D%0A%20%20var%20word%20%3D%20tailor%28_2,%20_6,%20_1,%20_5,%20_4,%20_3%29%3B%0A%0A%20%20var%20result%20%3D%20word%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20a_word%28%22a%22,%20%22t%22,%20%22o%22,%20%22r%22,%20%22l%22,%20%22i%22%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'tailor',%20%22example%201%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{ // completed example 1
  function a_word(_1, _2, _3, _4, _5, _6) { 
    
    function tailor(_a, _b, _c, _d, _e, _f) {
      return _a + _c + _b + _d + _f + _e;
    }
    var word = tailor(_2, _6, _1, _5, _4, _3);

    var result = word;
    return result;
  }
  const return_val = a_word("a", "t", "o", "r", "l", "i");
  console.assert(return_val === 'tailor', "example 1: return_val === " + return_val);
};
```

### Space Capes

[on pytut](http://www.pythontutor.com/javascript.html#code=function%20sentence%28_1,%20_2,%20_3,%20_4,%20_5%29%20%7B%20%0A%20%20%0A%20%20function%20space%28_a,%20_b,%20_c,%20_d,%20_e%29%20%7B%0A%20%20%20%20return%20_a%20%2B%20_b%20%2B%20_c%20%2B%20_d%20%2B%20_e%3B%0A%20%20%7D%0A%20%20var%20word_1%20%3D%20space%28_5,%20_4,%20_2,%20_3,%20_1%29%3B%0A%0A%20%20function%20capes%28_a,%20_b,%20_c,%20_d,%20_e%29%20%7B%0A%20%20%20%20return%20_a%20%2B%20_b%20%2B%20_c%20%2B%20_d%20%2B%20_e%3B%0A%20%20%7D%0A%20%20var%20word_2%20%3D%20capes%28_3,%20_2,%20_4,%20_1,%20_5%29%3B%0A%0A%20%20var%20result%20%3D%20word_1%20%2B%20%22%20%22%20%2B%20word_2%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20sentence%28%22e%22,%20%22a%22,%20%22c%22,%20%22p%22,%20%22s%22%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'space%20capes',%20%22example%202%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)  
```js
{ // completed example 2
  function sentence(_1, _2, _3, _4, _5) { 
    
    function space(_a, _b, _c, _d, _e) {
      return _a + _b + _c + _d + _e;
    }
    var word_1 = space(_5, _4, _2, _3, _1);

    function capes(_a, _b, _c, _d, _e) {
      return _a + _b + _c + _d + _e;
    }
    var word_2 = capes(_3, _2, _4, _1, _5);

    var result = word_1 + " " + word_2;
    return result;
  }
  const return_val = sentence("e", "a", "c", "p", "s");
  console.assert(return_val === 'space capes', "example 2: return_val === " + return_val);
};
```

[TOP](#sentences)

---

## Warm Ups

### Tour 1

[on pytut](http://www.pythontutor.com/javascript.html#code=function%20a_word%28_1,%20_2,%20_3,%20_4%29%20%7B%20%0A%20%20%0A%20%20function%20tour%28_a,%20_b,%20_c,%20_d%29%20%7B%0A%20%20%20%20return%20_b%20%2B%20_a%20%2B%20_c%20%2B%20_d%3B%0A%20%20%7D%0A%20%20var%20word%20%3D%20tour%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20var%20result%20%3D%20word%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20a_word%28%22o%22,%20%22t%22,%20%22u%22,%20%22r%22%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'tour',%20%22wu-1%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)  
```js
{ // warmup 1
  function a_word(_1, _2, _3, _4) { 
    
    function tour(_a, _b, _c, _d) {
      return _b + _a + _c + _d;
    }
    var word = tour(/* fill this in */);

    var result = word;
    return result;
  }
  const return_val = a_word("o", "t", "u", "r");
  console.assert(return_val === 'tour', "wu-1: return_val === " + return_val);
};
```

### Tour 2

[on pytut](http://www.pythontutor.com/live.html#code=function%20a_word%28_1,%20_2,%20_3,%20_4%29%20%7B%20%0A%20%20%0A%20%20function%20tour%28_a,%20_b,%20_c,%20_d%29%20%7B%0A%20%20%20%20return%20_c%20%2B%20_a%20%2B%20_d%20%2B%20_b%3B%0A%20%20%7D%0A%20%20var%20word%20%3D%20tour%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20var%20result%20%3D%20word%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20a_word%28%22u%22,%20/*%20fill%20this%20in%20*/%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'tour',%20%22wu-2%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{ // warmup 2
  function a_word(_1, _2, _3, _4) { 
    
    function tour(_a, _b, _c, _d) {
      return _c + _a + _d + _b;
    }
    var word = tour(/* fill this in */);

    var result = word;
    return result;
  }
  const return_val = a_word("u", /* fill this in */);
  console.assert(return_val === 'tour', "wu-2: return_val === " + return_val);
};
```

[TOP](#sentences)

---

## Exercises

### 1

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28_1,%20_2,%20_3%29%20%7B%20%0A%20%20%0A%20%20function%20eat%28_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_1%20%3D%20eat%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20function%20ate%28_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_2%20%3D%20ate%28_1,%20_2,%20_3%29%3B%0A%0A%20%20function%20tea%28_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_x%20%2B%20_y%20%2B%20_3%3B%0A%20%20%7D%0A%20%20var%20word_3%20%3D%20tea%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20var%20result%20%3D%20word_1%20%2B%20%22%20%22%20%2B%20word_2%20%2B%20%22%20%22%20%2B%20word_3%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20sentence%28%22a%22,%20%22e%22,%20%22t%22%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'eat%20ate%20tea',%20%221%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=14&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{ // 1 -> eat ate tea.  
  function sentence(_1, _2, _3) { 
    
    function eat(_x, _y, _z) {
      return _x + _y + _z;
    }
    var word_1 = eat(/* fill this in */);

    function ate(_x, _y, _z) {
      return _x + _y + _z;
    }
    var word_2 = ate(_1, _2, _3);

    function tea(_x, _y, _z) {
      return _x + _y + _3;
    }
    var word_3 = tea(/* fill this in */);

    var result = word_1 + " " + word_2 + " " + word_3;
    return result;
  }
  const return_val = sentence("a", "e", "t");
  console.assert(return_val === 'eat ate tea', "1: return_val === " + return_val);
};
```

### 2 

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28_1,%20_2,%20_3%29%20%7B%20%0A%20%20%0A%20%20function%20eat%28_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_z%20%2B%20_y%20%2B%20_x%3B%0A%20%20%7D%0A%20%20var%20word_1%20%3D%20eat%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20function%20ate%28_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_y%20%2B%20_x%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_2%20%3D%20ate%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20function%20tea%28_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_x%20%2B%20_z%20%2B%20_y%3B%0A%20%20%7D%0A%20%20var%20word_3%20%3D%20tea%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20var%20result%20%3D%20word_1%20%2B%20%22%20%22%20%2B%20word_2%20%2B%20%22%20%22%20%2B%20word_3%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20sentence%28%22a%22,%20%22e%22,%20%22t%22%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'eat%20ate%20tea',%20%222%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=14&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{ // 2 -> eat ate tea.  2 
  function sentence(_1, _2, _3) { 
    
    function eat(_x, _y, _z) {
      return _z + _y + _x;
    }
    var word_1 = eat(/* fill this in */);

    function ate(_x, _y, _z) {
      return _y + _x + _z;
    }
    var word_2 = ate(/* fill this in */);

    function tea(_x, _y, _z) {
      return _x + _z + _y;
    }
    var word_3 = tea(/* fill this in */);

    var result = word_1 + " " + word_2 + " " + word_3;
    return result;
  }
  const return_val = sentence("a", "e", "t");
  console.assert(return_val === 'eat ate tea', "2: return_val === " + return_val);
};
```

### 3

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28_1,%20_2,%20_3,%20_4,%20_5%29%20%7B%20%0A%0A%20%20function%20space%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_v%20%2B%20_w%20%2B%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_1%20%3D%20space%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20function%20capes%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_v%20%2B%20_w%20%2B%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_2%20%3D%20capes%28_4,%20_3,%20_2,%20_5,%20_1%29%3B%0A%0A%20%20var%20result%20%3D%20word_1%20%2B%20%22%20%22%20%2B%20word_2%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20sentence%28/*%20fill%20this%20in%20*/%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'space%20capes',%20%223%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=11&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{ // 3 -> space capes
  function sentence(_1, _2, _3, _4, _5) { 

    function space(_v, _w, _x, _y, _z) {
      return _v + _w + _x + _y + _z;
    }
    var word_1 = space(/* fill this in */);

    function capes(_v, _w, _x, _y, _z) {
      return _v + _w + _x + _y + _z;
    }
    var word_2 = capes(_4, _3, _2, _5, _1);

    var result = word_1 + " " + word_2;
    return result;
  }
  const return_val = sentence(/* fill this in */);
  console.assert(return_val === 'space capes', "3: return_val === " + return_val);
};
```

### 4

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28_1,%20_2,%20_3,%20_4,%20_5%29%20%7B%20%0A%0A%20%20function%20space%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_v%20%2B%20_w%20%2B%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_1%20%3D%20space%28_3,%20_4,%20_1,%20_5,%20_2%29%3B%0A%0A%20%20function%20capes%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_v%20%2B%20_w%20%2B%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_2%20%3D%20capes%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20var%20result%20%3D%20word_1%20%2B%20%22%20%22%20%2B%20word_2%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20sentence%28/*%20fill%20this%20in%20*/%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'space%20capes',%20%224%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=11&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{ // 4 -> space capes
  function sentence(_1, _2, _3, _4, _5) { 

    function space(_v, _w, _x, _y, _z) {
      return _v + _w + _x + _y + _z;
    }
    var word_1 = space(_3, _4, _1, _5, _2);

    function capes(_v, _w, _x, _y, _z) {
      return _v + _w + _x + _y + _z;
    }
    var word_2 = capes(/* fill this in */);

    var result = word_1 + " " + word_2;
    return result;
  }
  const return_val = sentence(/* fill this in */);
  console.assert(return_val === 'space capes', "4: return_val === " + return_val);
};
```

### 5

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28_1,%20_2,%20_3,%20_4,%20_5%29%20%7B%20%0A%0A%20%20function%20cruel%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_v%20%2B%20_w%20%2B%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_1%20%3D%20cruel%28_3,%20_1,%20_4,%20_5,%20_2%29%3B%0A%0A%20%20function%20ulcer%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_v%20%2B%20_w%20%2B%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_2%20%3D%20ulcer%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20var%20result%20%3D%20word_1%20%2B%20%22%20%22%20%2B%20word_2%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20sentence%28/*%20fill%20this%20in%20*/%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'cruel%20ulcer',%20%225%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=11&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{ // 5 -> cruel ulcer
  function sentence(_1, _2, _3, _4, _5) { 

    function cruel(_v, _w, _x, _y, _z) {
      return _v + _w + _x + _y + _z;
    }
    var word_1 = cruel(_3, _1, _4, _5, _2);

    function ulcer(_v, _w, _x, _y, _z) {
      return _v + _w + _x + _y + _z;
    }
    var word_2 = ulcer(/* fill this in */);

    var result = word_1 + " " + word_2;
    return result;
  }
  const return_val = sentence(/* fill this in */);
  console.assert(return_val === 'cruel ulcer', "5: return_val === " + return_val);
};
```

### 6

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28_1,%20_2,%20_3,%20_4,%20_5%29%20%7B%20%0A%0A%20%20function%20cruel%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_v%20%2B%20_w%20%2B%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_1%20%3D%20cruel%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20function%20ulcer%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_v%20%2B%20_w%20%2B%20_x%20%2B%20_y%20%2B%20_z%3B%0A%20%20%7D%0A%20%20var%20word_2%20%3D%20ulcer%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20var%20result%20%3D%20word_1%20%2B%20%22%20%22%20%2B%20word_2%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20sentence%28%22e%22,%20%22l%22,%20%22u%22,%20%22c%22,%20%22r%22%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'cruel%20ulcer',%20%226%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=11&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{ // 6 -> cruel ulcer
  function sentence(_1, _2, _3, _4, _5) { 

    function cruel(_v, _w, _x, _y, _z) {
      return _v + _w + _x + _y + _z;
    }
    var word_1 = cruel(/* fill this in */);

    function ulcer(_v, _w, _x, _y, _z) {
      return _v + _w + _x + _y + _z;
    }
    var word_2 = ulcer(/* fill this in */);

    var result = word_1 + " " + word_2;
    return result;
  }
  const return_val = sentence("e", "l", "u", "c", "r");
  console.assert(return_val === 'cruel ulcer', "6: return_val === " + return_val);
};
```

### 7

[on pytut](http://www.pythontutor.com/live.html#code=function%20sentence%28_1,%20_2,%20_3,%20_4,%20_5%29%20%7B%20%0A%0A%20%20function%20cruel%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_x%20%2B%20_z%20%2B%20_w%20%2B%20_v%20%2B%20_y%3B%0A%20%20%7D%0A%20%20var%20word_1%20%3D%20cruel%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20function%20ulcer%28_v,%20_w,%20_x,%20_y,%20_z%29%20%7B%0A%20%20%20%20return%20_z%20%2B%20_w%20%2B%20_y%20%2B%20_x%20%2B%20_v%3B%0A%20%20%7D%0A%20%20var%20word_2%20%3D%20ulcer%28/*%20fill%20this%20in%20*/%29%3B%0A%0A%20%20var%20result%20%3D%20word_1%20%2B%20%22%20%22%20%2B%20word_2%3B%0A%20%20return%20result%3B%0A%7D%0Aconst%20return_val%20%3D%20sentence%28%22e%22,%20%22l%22,%20%22u%22,%20%22c%22,%20%22r%22%29%3B%0Aconsole.assert%28return_val%20%3D%3D%3D%20'cruel%20ulcer',%20%227%3A%20return_val%20%3D%3D%3D%20%22%20%2B%20return_val%29%3B&cumulative=false&curInstr=11&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{ // 7 -> cruel ulcer
  function sentence(_1, _2, _3, _4, _5) { 

    function cruel(_v, _w, _x, _y, _z) {
      return _x + _z + _w + _v + _y;
    }
    var word_1 = cruel(/* fill this in */);

    function ulcer(_v, _w, _x, _y, _z) {
      return _z + _w + _y + _x + _v;
    }
    var word_2 = ulcer(/* fill this in */);

    var result = word_1 + " " + word_2;
    return result;
  }
  const return_val = sentence("e", "l", "u", "c", "r");
  console.assert(return_val === 'cruel ulcer', "7: return_val === " + return_val);
};
```







[TOP](#sentences)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
