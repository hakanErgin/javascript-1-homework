> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/variable-exercises/master/multiple-assignments.md) into this file and complete the exercises!   
> references: [javascript.info variables](https://javascript.info/variables), [variables and hoisting](https://github.com/janke-learning/variables-and-hoisting) 

# Multiple Assignments

There are mechanisms for assigning multiple variables on one line:
* _chaining assignments_ - ```a = b = c = 4;```
* _comma-separated assignments_ - ```a = 1, b = 2, c = 3;```

These exercises will help you practice multiple assignments on one line:
1. [chaining assignments](#chaining-assignments)
1. [comma-separated assignments](#comma-separated-assignments)

---

## Chaining Assignments

### completed examples
* the first: [pytut](http://www.pythontutor.com/javascript.html#code=var%20a%20%3D%20'b'%3B%0Avar%20b1%20%3D%20'a',%20b2%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20b1%3B%0Ab1%20%3D%20b2%20%3D%20a%3B%0Aa%20%3D%20_%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D), [parsonized](https://janke-learning.github.io/parsonizer/?snippet=var%20a%20%3D%20'b'%3B%0Avar%20b1%20%3D%20'a'%2C%20b2%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20b1%3B%0Ab1%20%3D%20b2%20%3D%20a%3B%0Aa%20%3D%20_%3B)
* the second: [pytut](http://www.pythontutor.com/javascript.html#code=var%20a%20%3D%20'c'%3B%0Avar%20b1%20%3D%20'a',%20b2%20%3D%20'a'%3B%0Avar%20c1%20%3D%20'b',%20c2%20%3D%20'b',%20c3%3B%0Ac3%20%3D%20'b'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a%3B%0Aa%20%3D%20b1%3B%0Ab1%20%3D%20b2%20%3D%20c1%3B%0Ac1%20%3D%20c2%20%3D%20c3%20%3D%20_%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D), 
[parsonized](https://janke-learning.github.io/parsonizer/?snippet=var%20a%20%3D%20'c'%3B%0Avar%20b1%20%3D%20'a'%2C%20b2%20%3D%20'a'%3B%0Avar%20c1%20%3D%20'b'%2C%20c2%20%3D%20'b'%2C%20c3%3B%0Ac3%20%3D%20'b'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a%3B%0Aa%20%3D%20b1%3B%0Ab1%20%3D%20b2%20%3D%20c1%3B%0Ac1%20%3D%20c2%20%3D%20c3%20%3D%20_%3B)

### exercises
* [the first](http://www.pythontutor.com/live.html#code=var%20a%20%3D%20'b'%3B%0Avar%20b1%20%3D%20'a',%20b2%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A//%20--%20can%20be%20done%20in%203%20lines&cumulative=false&curInstr=3&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
// your solution here
```
* [the second](http://www.pythontutor.com/live.html#code=var%20a%20%3D%20'c'%3B%0Avar%20b1%20%3D%20'a',%20b2%20%3D%20'a'%3B%0Avar%20c1%20%3D%20'b',%20c2,%20c3%3B%0Ac2%20%3D%20'b',%20c3%20%3D%20'b'%3B%0Avar%20_%20%3D%20''%3B%0A%0A//%20---%20can%20be%20done%20in%204%20lines%20---&cumulative=false&curInstr=5&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
// your solution here
```

[TOP](#multiple-assignments)

---

## Comma-Separated Assignments

### completed examples
* basic swap: [pytut](http://www.pythontutor.com/javascript.html#code=var%20a%20%3D%20'b',%20b%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a,%20a%20%3D%20b,%20b%20%3D%20_%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D), [parsonized](https://janke-learning.github.io/parsonizer/?snippet=var%20a%20%3D%20'b'%2C%20b%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a%2C%20a%20%3D%20b%2C%20b%20%3D%20_%3B)
* double swap - two lines: [pytut](http://www.pythontutor.com/javascript.html#code=var%20a,%20b,%20c%3B%0Aa%20%3D%20'b',%20b%20%3D%20'c',%20c%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a,%20a%20%3D%20c%3B%0Ac%20%3D%20b,%20b%20%3D%20_%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D), [parsonized](https://janke-learning.github.io/parsonizer/?snippet=var%20a%2C%20b%2C%20c%3B%0Aa%20%3D%20'b'%2C%20b%20%3D%20'c'%2C%20c%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a%2C%20a%20%3D%20c%3B%0Ac%20%3D%20b%2C%20b%20%3D%20_%3B)
* double swap - one line: [pytut](http://www.pythontutor.com/javascript.html#code=var%20a,%20b%20%3D%20'c',%20c%20%3D%20'a'%3B%0Aa%20%3D%20'b'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a,%20a%20%3D%20c,%20c%20%3D%20b,%20b%20%3D%20_%3B&curInstr=0&mode=display&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D), [parsonized](https://janke-learning.github.io/parsonizer/?snippet=var%20a%2C%20b%20%3D%20'c'%2C%20c%20%3D%20'a'%3B%0Aa%20%3D%20'b'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a%2C%20a%20%3D%20c%2C%20c%20%3D%20b%2C%20b%20%3D%20_%3B)

### exercises
* [basic swap](http://www.pythontutor.com/live.html#code=var%20a%20%3D%20'b',%20b%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A//%20---%20solve%20this%20in%20one%20line%20---&cumulative=false&curInstr=2&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
// your solution here
```
* [double swap - two lines](http://www.pythontutor.com/live.html#code=var%20a,%20b,%20c%3B%0Aa%20%3D%20'b',%20b%20%3D%20'c',%20c%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A//%20---%20solve%20this%20in%202%20lines%20---&cumulative=false&curInstr=3&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
// your solution here
```
* [double swap - one line](http://www.pythontutor.com/live.html#code=var%20a%20%3D%20'b',%20b%20%3D%20'c',%20c%20%3D%20'a'%3B%0Avar%20_%20%3D%20''%3B%0A%0A_%20%3D%20a,%20a%20%3D%20c,%20c%20%3D%20b,%20b%20%3D%20_%3B&cumulative=false&curInstr=3&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)
```js
// your solution here
```

[TOP](#multiple-assignments)

___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
