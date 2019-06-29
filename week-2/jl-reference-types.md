> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/reference-type-exercises/master/README.md) into this file and complete the exercises!   

# Reference Type Exercises

A series of examples and exercises to help you understand:
* reference vs. value (two ways variables can store values)
* arrays
* objects
* comparing arrays & objects
* nesting data structures

### Index
* [examples to study](#examples-to-study)
* [reference exercises](#reference-exercises)
* [array exercises](#array-exercises)
* [object exercises](#object-exercises)
* [arrays vs objects](#arrays-vs-objects)
* nesting
    * [arrays](#nesting-arrays)
    * [objects](#nesting-objects)
    * [both](#nesting-arrays-and-objects)

---

## Examples to Study

__Swapping with Arrays__  
[on pytut](http://www.pythontutor.com/javascript.html#code=let%20a%20%3D%20%5B%22b%22%5D%3B%0Alet%20b%20%3D%20%5B%22a%22%5D%3B%0Alet%20_%20%3D%20null%3B%0A%0A//%20swap%20the%20arrays%20to%20which%20each%20variable%20points%0A_%20%3D%20a%3B%0Aa%20%3D%20b%3B%0Ab%20%3D%20_%3B%0A%0A//%20------%0A%0A_%20%3D%20null%3B%0Alet%20x%20%3D%20%5B%22y%22%5D%3B%0Alet%20y%20%3D%20%5B%22x%22%5D%3B%0A%0A//%20swap%20the%20value%20each%20array%20contains%0A_%20%3D%20x%5B0%5D%3B%0Ax%5B0%5D%20%3D%20y%5B0%5D%3B%0Ay%5B0%5D%20%3D%20_%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  let a = ["b"];
  let b = ["a"];
  let _ = null;

  // swap the arrays to which each variable points
  _ = a;
  a = b;
  b = _;

  // ------

  _ = null;
  let x = ["y"];
  let y = ["x"];

  // swap the value each array contains
  _ = x[0];
  x[0] = y[0];
  y[0] = _;
}
```

__Comparing Reference Types__
[on pytut](http://www.pythontutor.com/live.html#code=let%20a%20%3D%20%5B%5D%3B%0Alet%20b%20%3D%20%5B%5D%3B%0Aconsole.assert%28a%20!%3D%3D%20b%29%3B%0Aconsole.assert%28a%20%3D%3D%3D%20b%29%3B%0A%0Ab%20%3D%20a%3B%0Aconsole.assert%28a%20%3D%3D%3D%20b%29%3B%0Aconsole.assert%28a%20!%3D%3D%20b%29%3B&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  let a = [];
  let b = [];
  console.assert(a !== b);
  console.assert(a === b);
  
  b = a;
  console.assert(a === b);
  console.assert(a !== b);
}
```


__Swapping with Objects__ (dot notation)  
[on pytut](http://www.pythontutor.com/live.html#code=let%20a%20%3D%20%7By_prop%3A%20%22y%22%7D%3B%0Alet%20b%20%3D%20%7Bx_prop%3A%20%22x%22%7D%3B%0Alet%20_%20%3D%20null%3B%0A%0A//%20swap%20the%20object%20in%20which%20each%20value%20is%20stored%0A_%20%3D%20a%3B%0Aa%20%3D%20b%3B%0Ab%20%3D%20_%3B%0A%0A//%20------%0A%0A_%20%3D%20null%3B%0Alet%20x%20%3D%20%7Ba_prop%3A%20%22b%22%7D%3B%0Alet%20y%20%3D%20%7Bb_prop%3A%20%22a%22%7D%3B%0A%0A//%20swap%20the%20value%20each%20object%20contains%0A_%20%3D%20x.a_prop%3B%0Ax.a_prop%20%3D%20y.b_prop%3B%0Ay.b_prop%20%3D%20_%3B&cumulative=false&curInstr=12&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  let a = {y_prop: "y"};
  let b = {x_prop: "x"};
  let _ = null;

  // swap the object in which each value is stored
  _ = a;
  a = b;
  b = _;

  // ------

  _ = null;
  let x = {a_prop: "b"};
  let y = {b_prop: "a"};

  // swap the value each object contains
  _ = x.a_prop;
  x.a_prop = y.b_prop;
  y.b_prop = _;
}
```

__Swapping with Objects__ (bracket notation)  
[(read this first)](https://github.com/janke-learning/dots-vs-brackets)  
[on pytut](http://www.pythontutor.com/live.html#code=let%20a%20%3D%20%7Bx_prop%3A%20%22y%22%7D%3B%0Alet%20b%20%3D%20%7By_prop%3A%20%22x%22%7D%3B%0Alet%20_%20%3D%20null%3B%0A%0A//%20swap%20the%20object%20in%20which%20each%20value%20is%20stored%0A//%20%20with%20dots%0A_%20%3D%20a.x_prop%3B%0Aa.x_prop%20%3D%20b.y_prop%3B%0Ab.y_prop%20%3D%20_%3B%0A%0A//%20------%0A%0A_%20%3D%20null%3B%0Alet%20x%20%3D%20%7Ba_prop%3A%20%22b%22%7D%3B%0Alet%20y%20%3D%20%7Bb_prop%3A%20%22a%22%7D%3B%0A%0A//%20swap%20the%20object%20in%20which%20each%20value%20is%20stored%0A//%20%20with%20brackets%0Aconst%20a_key%20%3D%20%22a_prop%22%3B%0Aconst%20b_key%20%3D%20%22b_prop%22%3B%0A_%20%3D%20x%5Ba_key%5D%3B%0Ax%5Ba_key%5D%20%3D%20y%5Bb_key%5D%3B%0Ay%5Bb_key%5D%20%3D%20_%3B&cumulative=false&curInstr=14&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  let a = {x_prop: "y"};
  let b = {y_prop: "x"};
  let _ = null;

  // swap the object in which each value is stored
  //  with dots
  _ = a.x_prop;
  a.x_prop = b.y_prop;
  b.y_prop = _;

  // ------

  _ = null;
  let x = {a_prop: "b"};
  let y = {b_prop: "a"};

  // swap the object in which each value is stored
  //  with brackets
  const a_key = "a_prop";
  const b_key = "b_prop";
  _ = x[a_key];
  x[a_key] = y[b_key];
  y[b_key] = _;
}
```

[TOP](#reference-type-exercises)

---

## Reference Exercises

__Swap the Object & the Array__  
[on pytut](http://www.pythontutor.com/javascript.html#code=let%20obj%20%3D%20%5B%5D%3B%0Alet%20arr%20%3D%20%7B%7D%3B%0Alet%20_%20%3D%20null%3B%0A%0A//%20swap%20the%20object%20and%20the%20array&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  let obj = [];
  let arr = {};
  let _ = null;

  // --- swap below here ---

}
```

__Complete this code__  
[(read this first)](https://github.com/janke-learning/reference-vs-value)  
[on pytut](http://www.pythontutor.com/javascript.html#code=%20%20let%20value_1%20%3D%205%3B%0A%20%20let%20reference_1%20%3D%20%5B%5D%3B%0A%0A%20%20let%20value_2%20%3D%20value_1%3B%0A%20%20console.assert%28value_2%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20value_1%29%3B%0A%0A%20%20let%20reference_2%20%3D%20reference_1%3B%0A%20%20console.assert%28reference_2%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20reference_1%29%3B%0A%0A%20%20%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20console.assert%28value_1%20!%3D%3D%20value_2%29%3B%20%20%0A%20%20%20%20%0A%20%20%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20console.assert%28reference_1%5B0%5D%20%3D%3D%3D%20reference_2%5B0%5D%29%3B%0A%0A%20%20//%20remove%20the%20array%20from%20memory%0A%20%20%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20%20%20%20%20%3B%20//%20write%20this%20line&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  let value_1 = 5;
  let reference_1 = [];

  let value_2 = value_1;
  console.assert(value_2 /* === or !== ? */ value_1);

  let reference_2 = reference_1;
  console.assert(reference_2 /* === or !== ? */ reference_1);

      ; // write this line
  console.assert(value_1 !== value_2);  

      ; // write this line
  console.assert(reference_1[0] === reference_2[0]);

  // remove the array from memory
      ; // write this line
      ; // write this line
}
```

[TOP](#reference-type-exercises)

---

## Array Exercises

__Complete the Assertions__  
[on pytut](http://www.pythontutor.com/javascript.html#code=let%20a_1%20%3D%20%5B%5D%3B%0Alet%20a_2%20%3D%20a_1%3B%0Aconsole.assert%28a_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20a_2%29%3B%0A%0Alet%20b_1%20%3D%20%5B%5D%3B%0Alet%20b_2%20%3D%20%5B%5D%3B%0Aconsole.assert%28b_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20b_2%29%3B%0A%0A//%20---%0A%0Alet%20a_1.push%283%29%3B%0Alet%20a_2.push%283%29%3B%0Aconsole.assert%28a_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20a_2%29%3B%0A%0Alet%20b_1.push%285%29%3B%0Alet%20b_2.push%285%29%3B%0Aconsole.assert%28b_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20b_2%29%3B%0A%0A&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  let a_1 = [];
  let a_2 = a_1;
  console.assert(a_1 /* === or !== ? */ a_2);

  let b_1 = [];
  let b_2 = [];
  console.assert(b_1 /* === or !== ? */ b_2);

  // ---

  let a_1.push(3);
  let a_2.push(3);
  console.assert(a_1 /* === or !== ? */ a_2);

  let b_1.push(5);
  let b_2.push(5);
  console.assert(b_1 /* === or !== ? */ b_2);
}
```

__Complete the Assertions__  
[on pytut](http://www.pythontutor.com/javascript.html#code=let%20a_1%20%3D%20%5B%5D%3B%0Alet%20a_2%20%3D%20a_1%3B%0Aconsole.assert%28a_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20a_2%29%3B%0A%0Alet%20b_1%20%3D%20%5B%5D%3B%0Alet%20b_2%20%3D%20%5B%5D%3B%0Aconsole.assert%28b_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20b_2%29%3B%0A%0A//%20---%0A%0Aconst%20key%20%3D%200%3B%0A%0Alet%20a_1%5Bkey%5D%20%3D%203%3B%0Alet%20a_2%5Bkey%5D%20%3D%203%3B%0Aconsole.assert%28a_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20a_2%29%3B%0A%0Alet%20b_1%5Bkey%5D%20%3D%205%3B%0Alet%20b_2%5Bkey%5D%20%3D%205%3B%0Aconsole.assert%28b_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20b_2%29%3B%0A&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  let a_1 = [];
  let a_2 = a_1;
  console.assert(a_1 /* === or !== ? */ a_2);

  let b_1 = [];
  let b_2 = [];
  console.assert(b_1 /* === or !== ? */ b_2);

  // ---

  const index = 0;

  let a_1[index] = 3;
  let a_2[index] = 3;
  console.assert(a_1 /* === or !== ? */ a_2);

  let b_1[index] = 5;
  let b_2[index] = 5;
  console.assert(b_1 /* === or !== ? */ b_2);
}
```

__Fill in the Blanks__  
[on pytut](http://www.pythontutor.com/live.html#code=%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20%20%20%3B%20//%20write%20this%20line%0Aconsole.assert%28arr_1%20!%3D%3D%20arr_2%29%3B%0Aconsole.assert%28arr_1%5B1%5D%20%3D%3D%3D%20arr_2%5B1%5D%29%3B%0Aconsole.assert%28arr_1%5B1%5D%20%3D%3D%3D%20'B'%29%0A%0Alet%20key%20%3D%200%3B%0Aconsole.assert%28arr_1%5Bkey%5D%20%3D%3D%3D%20arr_2%5Bkey%5D%29%3B%0Aconsole.assert%28arr_1%5Bkey%5D%20%3D%3D%3D%20'A'%29%3B%0A%0A%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20%20%20%3B%20//%20write%20this%20line%0Aconsole.assert%28arr_1%5Barr_2%5B2%5D%5D%20%3D%3D%3D%20arr_2%5Barr_1%5B2%5D%5D%29%3B%0Aconsole.assert%28arr_1%5Barr_2%5B2%5D%5D%20%3D%3D%3D%20'B'%29%3B%0A%0A%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20%20%20%3B%20//%20write%20this%20line%0Aconsole.assert%28arr_1%20%3D%3D%3D%20arr_2%29%3B%0Aconsole.assert%28arr_3%20!%3D%3D%20arr_1%29%3B%0Aconsole.assert%28arr_3%20!%3D%3D%20arr_2%29%3B%0Aconsole.assert%28arr_3%5Bkey%5D%20%3D%3D%3D%20arr_1%5B0%5D%29%3B%0A%0A%20%20%20%20%3B%20//%20write%20this%20line%0Aconsole.assert%28obj_3%5B1%5D%20%3D%3D%3D%20obj_2%5Bkey%5D%29%3B&cumulative=false&curInstr=1&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
      ; // write this line
      ; // write this line
  console.assert(arr_1 !== arr_2);
  console.assert(arr_1[1] === arr_2[1]);
  console.assert(arr_1[1] === 'B')

  let key = 0;
  console.assert(arr_1[key] === arr_2[key]);
  console.assert(arr_1[key] === 'A');

      ; // write this line
      ; // write this line
  console.assert(arr_1[arr_2[2]] === arr_2[arr_1[2]]);
  console.assert(arr_1[arr_2[2]] === 'B');

      ; // write this line
      ; // write this line
  console.assert(arr_1 === arr_2);
  console.assert(arr_3 !== arr_1);
  console.assert(arr_3 !== arr_2);
  console.assert(arr_3[key] === arr_1[0]);

      ; // write this line
  console.assert(obj_3[1] === obj_2[key]);
}
```

[TOP](#reference-type-exercises)

---

## Object Exercises

__Complete the Assertions__  
[on pytut](http://www.pythontutor.com/javascript.html#code=let%20a_1%20%3D%20%7B%7D%3B%0Alet%20a_2%20%3D%20a_1%3B%0Aconsole.assert%28a_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20a_2%29%3B%0A%0Alet%20b_1%20%3D%20%7B%7D%3B%0Alet%20b_2%20%3D%20%7B%7D%3B%0Aconsole.assert%28b_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20b_2%29%3B%0A%0A//%20---%0A%0Alet%20a_1.x%20%3D%203%3B%0Alet%20a_2.x%20%3D%203%3B%0Aconsole.assert%28a_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20a_2%29%3B%0A%0Alet%20b_1.x%20%3D%205%3B%0Alet%20b_2.x%20%3D%205%3B%0Aconsole.assert%28b_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20b_2%29%3B%0A%0A&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  let a_1 = {};
  let a_2 = a_1;
  console.assert(a_1 /* === or !== ? */ a_2);

  let b_1 = {};
  let b_2 = {};
  console.assert(b_1 /* === or !== ? */ b_2);

  // ---

  let a_1.x = 3;
  let a_2.x = 3;
  console.assert(a_1 /* === or !== ? */ a_2);

  let b_1.x = 5;
  let b_2.x = 5;
  console.assert(b_1 /* === or !== ? */ b_2);
}
```

__Complete the Assertions__  
[on pytut](http://www.pythontutor.com/javascript.html#code=%20%20let%20a_1%20%3D%20%7B%7D%3B%0A%20%20let%20a_2%20%3D%20a_1%3B%0A%20%20console.assert%28a_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20a_2%29%3B%0A%0A%20%20let%20b_1%20%3D%20%7B%7D%3B%0A%20%20let%20b_2%20%3D%20%7B%7D%3B%0A%20%20console.assert%28b_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20b_2%29%3B%0A%0A%20%20//%20---%0A%20%20%0A%20%20const%20key%20%3D%20%22x%22%3B%0A%0A%20%20let%20a_1%5Bkey%5D%20%3D%203%3B%0A%20%20let%20a_2%5Bkey%5D%20%3D%203%3B%0A%20%20console.assert%28a_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20a_2%29%3B%0A%0A%20%20let%20b_1%5Bkey%5D%20%3D%205%3B%0A%20%20let%20b_2%5Bkey%5D%20%3D%205%3B%0A%20%20console.assert%28b_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20b_2%29%3B&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  let a_1 = {};
  let a_2 = a_1;
  console.assert(a_1 /* === or !== ? */ a_2);

  let b_1 = {};
  let b_2 = {};
  console.assert(b_1 /* === or !== ? */ b_2);

  // ---

  const key = "x";

  let a_1[key] = 3;
  let a_2[key] = 3;
  console.assert(a_1 /* === or !== ? */ a_2);

  let b_1[key] = 5;
  let b_2[key] = 5;
  console.assert(b_1 /* === or !== ? */ b_2);
}
```

__Fill in the Blanks__  
[on pytut](http://www.pythontutor.com/live.html#code=%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20%20%20%3B%20//%20write%20this%20line%20%20%20%20%3B%20//%20write%20this%20line%0Aconsole.assert%28obj_1%20!%3D%3D%20obj_2%29%3B%0Aconsole.assert%28obj_1.x%20%3D%3D%3D%20obj_2.x%29%3B%0Aconsole.assert%28obj_1.x%20%3D%3D%3D%20%22a%22%29%3B%0A%0Alet%20key%20%3D%20%22y%22%3B%0Aconsole.assert%28obj_1%5Bkey%5D%20%3D%3D%3D%20obj_2%5Bkey%5D%29%3B%0Aconsole.assert%28obj_1%5Bkey%5D%20%3D%3D%3D%20'x'%29%3B%0A%0A%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20%20%20%3B%20//%20write%20this%20line%0Aconsole.assert%28obj_1%5Bobj_2.y%5D%20%3D%3D%3D%20obj_2%5Bobj_1.y%5D%29%3B%0Aconsole.assert%28obj_1%5Bobj_2.y%5D%20%3D%3D%3D%20obj_1%5B'x'%5D%29%3B%0A%0A%20%20%20%20%3B%20//%20write%20this%20line%0A%20%20%20%20%3B%20//%20write%20this%20line%0Aconsole.assert%28obj_1%20%3D%3D%3D%20obj_2%29%3B%0Aconsole.assert%28obj_3%20!%3D%3D%20obj_1%29%3B%0Aconsole.assert%28obj_3%20!%3D%3D%20obj_2%29%3B%0Aconsole.assert%28obj_3%5Bkey%5D%20%3D%3D%3D%20obj_1.y%29%3B%0Aconsole.assert%28obj_3%5B'x'%5D%20%3D%3D%3D%20key%29%3B&cumulative=false&curInstr=1&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
       ; // write this line
       ; // write this line    ; // write this line
   console.assert(obj_1 !== obj_2);
   console.assert(obj_1.x === obj_2.x);
   console.assert(obj_1.x === "a");

   let key = "y";
   console.assert(obj_1[key] === obj_2[key]);
   console.assert(obj_1[key] === 'x');

       ; // write this line
       ; // write this line
   console.assert(obj_1[obj_2.y] === obj_2[obj_1.y]);
   console.assert(obj_1[obj_2.y] === obj_1['x']);

       ; // write this line
       ; // write this line
   console.assert(obj_1 === obj_2);
   console.assert(obj_3 !== obj_1);
   console.assert(obj_3 !== obj_2);
   console.assert(obj_3[key] === obj_1.y);
   console.assert(obj_3['x'] === key);
}
```

[TOP](#reference-type-exercises)

---

## Comparison Exercises

__Swap 'em__  
[on pytut](http://www.pythontutor.com/javascript.html#code=const%20obj%20%3D%20%7Bprop%3A%20%22array%22%7D%3B%0Aconst%20arr%20%3D%20%5B%22object%22%5D%3B%0Alet%20_%20%3D%20null%3B%0A%0A//%20swap%20the%20values%20stored%20in%20each%20structure%0A//%20%20using%20dot%20notation%20for%20the%20object%0A//%20%20using%20direct%20access%20for%20the%20array&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)
```js
{
  const obj = {prop: "array"};
  const arr = ["object"];
  let _ = null;

  // swap the values stored in each structure
  //  using dot notation for the object
  //  using direct access for the array
}
```

__Swap 'em__  
[on pytut](http://www.pythontutor.com/live.html#code=const%20obj%20%3D%20%7Bprop%3A%20%22array%22%7D%3B%0Aconst%20arr%20%3D%20%5B%22object%22%5D%3B%0Alet%20_%20%3D%20null%3B%0A%0A//%20fill%20in%20these%20blanks%0Aconst%20obj_key%20%3D%20%3B%0Aconst%20arr_index%20%3D%20%3B%0A%0A_%20%3D%20arr%5Barr_index%5D%3B%0Aarr%5Barr_index%5D%20%3D%20obj%5Bobj_key%5D%3B%0Aobj%5Bobj_key%5D%20%3D%20_%3B%0A%0Aconsole.assert%28arr%5Barr_index%5D%20%3D%3D%3D%20%22object%22,%20%22first%20assert%22%29%3B%0Aconsole.assert%28obj%5Bobj_key%5D%20%3D%3D%3D%20%22array%22,%20%22second%20assert%22%29%3B&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)  
```js
{
  const obj = {prop: "array"};
  const arr = ["object"];
  let _ = null;

  // fill in these blanks
  const obj_key = ;
  const arr_index = ;
  
  _ = arr[arr_index];
  arr[arr_index] = obj[obj_key];
  obj[obj_key] = _;
  
  console.assert(arr[arr_index] === "object", "first assert");
  console.assert(obj[obj_key] === "array", "second assert");
}
```

__Relative vs Absolute__  
[on pytut](http://www.pythontutor.com/javascript.html#code=//%20array%20indices%20are%20relative%0Aconst%20arr%20%3D%20%5B%22a%22,%20%22b%22%5D%3B%0Aconst%20index%20%3D%200%3B%0A%0Aconst%20read_arr_1%20%3D%20arr%5Bindex%5D%3B%0Aarr.shift%28%29%3B%20//%20removes%20the%20first%20item%0Aconst%20read_arr_2%20%3D%20arr%5Bindex%5D%3B%0A%0Aconsole.assert%28read_arr_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20read_arr_2%29%3B%0A%0A//%20object%20keys%20are%20absolute%0Aconst%20obj%20%3D%20%7Bx%3A%20%22a%22,%20y%3A%20%22b%22%7D%3B%0Aconst%20key%20%3D%20%22y%22%3B%0A%0Aconst%20read_obj_1%20%3D%20obj%5Bkey%5D%3B%0Adelete%20obj.x%3B%0Aconst%20read_obj_2%20%3D%20obj%5Bkey%5D%3B%0A%0Aconsole.assert%28read_obj_1%20/*%20%3D%3D%3D%20or%20!%3D%3D%20%3F%20*/%20read_obj_2%29%3B&mode=edit&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D)  
```js
{
  // array indices are relative
  const arr = ["a", "b"];
  const index = 0;

  const read_arr_1 = arr[index];
  arr.shift(); // removes the first item
  const read_arr_2 = arr[index];

  console.assert(read_arr_1 /* === or !== ? */ read_arr_2);

  // object keys are absolute
  const obj = {x: "a", y: "b"};
  const key = "y";

  const read_obj_1 = obj[key];
  delete obj.x;
  const read_obj_2 = obj[key];

  console.assert(read_obj_1 /* === or !== ? */ read_obj_2);
}
```

[TOP](#reference-type-exercises)

---

## Nesting Reference Types

### Nesting Arrays

__complete the asserts__
[on pytut](http://www.pythontutor.com/live.html#code=let%20arr_1%20%3D%20%5B%5D%3B%0Alet%20arr_2%20%3D%20%5B%5D%3B%0A%0Aarr_1.push%28arr_2%29%3B%0Aarr_2.push%28arr_1%29%3B%0Aconsole.assert%28arr_1%5B0%5D%20/*%20%3D%3D%3D%20or%20!%3D%3D%20*/%20arr_2%29%3B%0Aconsole.assert%28arr_2%5B0%5D%20/*%20%3D%3D%3D%20or%20!%3D%3D%20*/%20arr_1%29%3B%0A%0Aarr_1.push%28%5B%5D%29%3B%0Aarr_2.push%28%5B%5D%29%3B%0Aconsole.assert%28arr_1%5B1%5D%20/*%20%3D%3D%3D%20or%20!%3D%3D%20*/%20arr_2%5B1%5D%29%3B%0A%0Aarr_1%5B0%5D.push%28'A'%29%3B%0Aconsole.assert%28arr_1%5B0%5D%5B2%5D%20/*%20%3D%3D%3D%20or%20!%3D%3D%20*/%20arr_2%5B2%5D%29%3B%0A%0Aarr_2%5B0%5D.push%28'B'%29%3B%0Aconsole.assert%28arr_2%5B0%5D%5B2%5D%20/*%20%3D%3D%3D%20or%20!%3D%3D%20*/%20arr_1%5B2%5D%29%3B%0A%0Aarr_1%5B1%5D.push%28'X'%29%3B%0Aarr_2%5B1%5D.push%28'X'%29%3B%0Aconsole.assert%28arr_1%5B1%5D%5B0%5D%20/*%20%3D%3D%3D%20or%20!%3D%3D%20*/%20arr_2%5B1%5D%5B0%5D%29&cumulative=false&curInstr=9&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
{
  let arr_1 = [];
  let arr_2 = [];

  arr_1.push(arr_2);
  arr_2.push(arr_1);
  console.assert(arr_1[0] /* === or !== */ arr_2);
  console.assert(arr_2[0] /* === or !== */ arr_1);

  arr_1.push([]);
  arr_2.push([]);
  console.assert(arr_1[1] /* === or !== */ arr_2[1]);

  arr_1[0].push('A');
  console.assert(arr_1[0][2] /* === or !== */ arr_2[2]);
  
  arr_2[0].push('B');
  console.assert(arr_2[0][2] /* === or !== */ arr_1[2]);

  arr_1[1].push('X');
  arr_2[1].push('X');
  console.assert(arr_1[1][0] /* === or !== */ arr_2[1][0])
}
```

__fill in the blanks__
```js
{
  let arr_1 = [];
  let arr_2 = [];

  arr_1.push(arr_2);
  arr_2.push(arr_1);
  console.assert(arr_1[0] /* === or !== */ arr_2);
  console.assert(arr_2[0] /* === or !== */ arr_1);

  arr_1.push([]);
  arr_2.push([]);
  console.assert(arr_1[1] /* === or !== */ arr_2[1]);

  arr_1[0].push('A');
  console.assert(arr_1[0][2] /* === or !== */ arr_2[2]);
  
  arr_2[0].push('B');
  console.assert(arr_2[0][2] /* === or !== */ arr_1[2]);

  arr_1[1].push('X');
  arr_2[1].push('X');
  console.assert(arr_1[1][0] /* === or !== */ arr_2[1][0])
}
```

### Nesting Objects

### Nesting Arrays and Objects

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
