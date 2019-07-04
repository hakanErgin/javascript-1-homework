> paste [this markdown of exercises](https://raw.githubusercontent.com/janke-learning/variable-exercises/master/sentences-without-temps.md) into this file and complete the exercises!   
> references: [javascript.info variables](https://javascript.info/variables), [variables and hoisting](https://github.com/janke-learning/variables-and-hoisting) 

# Sentences without temp variables 

These exercises ask you to reassign variables so that at each step of execution the variables spell out the next word in a sentence.  See how few reassignments you can use per step!

You'll have to practice looking ahead of and behind the line you are writing to strategize how you will store and reuse data from earlier in your program.  This is one of the fundamental challenges in development.


### example solutions: 
1. the toad reads me: [pytut](https://goo.gl/pmpkJZ), [parsons](https://janke-learning.github.io/parsonizer/?snippet=%2F%2F%20the%20toad%20reads%20me%0Alet%20_1%20%3D%20%22%20%22%2C%20_2%20%3D%20%22%20%22%2C%20_3%20%3D%20%22%20%22%2C%20_4%20%3D%20%22%20%22%2C%20_5%20%3D%20%22%20%22%3B%0A%2F%2F%20the%0A_1%20%3D%20%22t%22%2C%20_2%20%3D%20%22h%22%2C%20_3%20%3D%20%22e%22%3B%0A%2F%2F%20toad%0A_2%20%3D%20%22o%22%2C%20_3%20%3D%20%22a%22%2C%20_4%20%3D%20%22d%22%3B%0A%2F%2F%20reads%0A_1%20%3D%20%22r%22%2C%20_2%20%3D%20%22e%22%2C%20_5%20%3D%20%22s%22%3B%0A%2F%2F%20me%0A_1%20%3D%20%22m%22%2C%20_3%20%3D%20%22%20%22%2C%20_4%20%3D%20%22%20%22%2C%20_5%20%3D%20%22%20%22%3B)
1. eating meat every meal: [pytut](https://goo.gl/bDVjKL), [parsons](https://janke-learning.github.io/parsonizer/?snippet=%2F%2F%20eating%20meat%20every%20meal%0Alet%20_1%20%3D%20'%20'%2C%20_2%20%3D%20'%20'%2C%20_3%20%3D%20'%20'%2C%20_4%20%3D%20'%20'%2C%20_5%20%3D%20'%20'%2C%20_6%3D%20'%20'%3B%0A%2F%2F%20eating%0A_1%20%3D%20%22e%22%2C%20_2%20%3D%20%22a%22%2C%20_3%20%3D%20%22t%22%2C%20_4%20%3D%20%22i%22%2C%20_5%20%3D%20%22n%22%2C%20_6%3D%20%22g%22%3B%0A%2F%2F%20meat%0A_4%20%3D%20_3%2C%20_3%20%3D%20_2%2C%20_2%20%3D%20_1%2C%20_1%20%3D%20%22m%22%2C%20_5%20%3D%20%22%20%22%2C%20_6%20%3D%20%22%20%22%3B%0A%2F%2F%20every%0A_1%20%3D%20_2%2C%20_3%20%3D%20_2%2C%20_2%20%3D%20%22v%22%2C%20_4%20%3D%20%22r%22%2C%20_5%20%3D%20%22y%22%3B%0A%2F%2F%20meal%0A_1%20%3D%20%22m%22%2C%20_2%20%3D%20_3%2C%20_3%20%3D%20%22a%22%2C%20_4%20%3D%20%22l%22%2C%20_5%20%3D%20%22%20%22%3B)
1. many men may melt my mind: [pytut](https://goo.gl/Gh8mCu), [parsons](https://janke-learning.github.io/parsonizer/?snippet=%2F%2F%20many%20men%20may%20melt%20my%20mind%0A%0Alet%20_1%20%3D%20'%20'%2C%20_2%20%3D%20'%20'%2C%20_3%20%3D%20'%20'%2C%20_4%20%3D%20'%20'%3B%0A%0A%2F%2F%20many%0A_1%20%3D%20'm'%2C%20_2%20%3D%20'a'%2C%20_3%20%3D%20'n'%2C%20_4%20%3D%20'y'%3B%0A%2F%2F%20men%0A_2%20%3D%20'e'%2C%20_4%20%3D%20'%20'%3B%0A%2F%2F%20may%0A_2%20%3D%20'a'%2C%20_3%20%3D%20'y'%3B%0A%2F%2F%20melt%0A_2%20%3D%20'e'%2C%20_3%20%3D%20'l'%2C%20_4%20%3D%20't'%3B%0A%2F%2F%20my%0A_2%20%3D%20'y'%2C%20_3%20%3D%20'%20'%2C%20_4%20%3D%20'%20'%3B%0A%2F%2F%20mind%0A_2%20%3D%20'i'%2C%20_3%20%3D%20'n'%2C%20_4%20%3D%20'd'%3B)
1. if fir trees ever fall: [pytut](https://goo.gl/tdJQwW), [parsons](https://janke-learning.github.io/parsonizer/?snippet=%2F%2F%20if%20fir%20trees%20ever%20fall%0A%0Alet%20_1%20%3D%20'%20'%2C%20_2%20%3D%20'%20'%2C%20_3%20%3D%20'%20'%2C%20_4%20%3D%20'%20'%2C%20_5%20%3D%20'%20'%3B%0A%0A%2F%2F%20if%0A_1%20%3D%20'i'%2C%20_2%20%3D%20'f'%3B%0A%2F%2F%20fir%0A_1%20%3D%20_2%2C%20_2%20%3D%20'i'%2C%20_3%20%3D%20'r'%3B%0A%2F%2F%20trees%0A_1%20%3D%20't'%2C%20_2%20%3D%20_3%2C%20_3%20%3D%20'e'%2C%20_4%20%3D%20_3%2C%20_5%20%3D%20's'%3B%0A%2F%2F%20ever%0A_1%20%3D%20_3%2C%20_2%20%3D%20'v'%2C%20_4%20%3D%20'r'%2C%20_5%20%3D%20'r'%3B%0A%2F%2F%20fall%0A_1%20%3D%20'f'%2C%20_2%20%3D%20'a'%2C%20_3%20%3D%20'l'%2C%20_4%20%3D%20_3%2C%20_5%20%3D%20'%20'%3B)

### challenges: 
1. [the toad reads me](https://goo.gl/imKwgj)  
```js
// the toad reads me
let _1 = " ", _2 = " ", _3 = " ", _4 = " ", _5 = " ";
// the
_1 = "t", _2 = "h", _3 = "e";
// toad
_2 = "o", _3 = "a", _4 = "d";
// reads
_1 = "r", _2 = "e", _5 = "s";
// me
_1 = "m", _3 = " ", _4 = " ", _5 = " ";
```  
1. [eating meat every meal](https://goo.gl/cwZijk)
```js
// eating meat every meal
let _1 = ' ', _2 = ' ', _3 = ' ', _4 = ' ', _5 = ' ', _6= ' ';
// eating
_1 = "e", _2 = "a", _3 = "t", _4 = "i", _5 = "n", _6= "g";
// meat
_4 = _3, _3 = _2, _2 = _1, _1 = "m", _5 = " ", _6 = " ";
// every
_1 = _2, _3 = _2, _2 = "v", _4 = "r", _5 = "y";
// meal
_1 = "m", _2 = _3, _3 = "a", _4 = "l", _5 = " ";
```  
1. [many men may melt my mind](https://goo.gl/16C62t)
```js
// many men may melt my mind

let _1 = ' ', _2 = ' ', _3 = ' ', _4 = ' ';

// many
_1 = 'm', _2 = 'a', _3 = 'n', _4 = 'y';
// men
_2 = 'e', _4 = ' ';
// may
_2 = 'a', _3 = 'y';
// melt
_2 = 'e', _3 = 'l', _4 = 't';
// my
_2 = 'y', _3 = ' ', _4 = ' ';
// mind
_2 = 'i', _3 = 'n', _4 = 'd';
```  
1. [if fir trees ever fall](https://goo.gl/8y5Lh2)
```js
// if fir trees ever fall

let _1 = ' ', _2 = ' ', _3 = ' ', _4 = ' ', _5 = ' ';

// if
_1 = 'i', _2 = 'f';
// fir
_1 = _2, _2 = 'i', _3 = 'r';
// trees
_1 = 't', _2 = _3, _3 = 'e', _4 = _3, _5 = 's';
// ever
_1 = _3, _2 = 'v', _4 = 'r', _5 = 'r';
// fall
_1 = 'f', _2 = 'a', _3 = 'l', _4 = _3, _5 = ' ';
```  




___
___
### <a href="http://janke-learning.org" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/50098409-22575780-021c-11e9-99e1-962787adaded.png" width="40" height="40"></img> Janke Learning</a>
