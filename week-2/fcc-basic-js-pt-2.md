> complete the rest of [basic JS exercises](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/basic-javascript) on FCC and paste each of your solutions into this file.  This will allow you to use your FCC exercises as a study reference later on  
> [completed example](https://github.com/AlfiYusrina/hyf-javascript1/blob/master/week1/freecode_camp_solutions.MD) 


## Counting Cards
```js
    function cc(card) {
      // Only change code below this line
      switch(card){
        case 2:
        case 3:
        case 4:
        case 5:
        case 6:
          count++;
          break;
        case 10:
        case "J":
        case "Q":
        case "K":
        case "A":
          count--;
          break;
      }
      if (count > 0){
        return count + " Bet";
      } else {
        return count + " Hold";
      }
      // Only change code above this line
    }
```

## Build JavaScript Objects

```js

// Only change code below this line.

var myDog = {
  "name": "xx",
  "legs": 4,
  "tails": 1,
  "friends": ["x", "s"],
};
```

## Accessing Object Properties with Dot Notation

```js
    // Setup
var testObj = {
  "hat": "ballcap",
  "shirt": "jersey",
  "shoes": "cleats"
};

// Only change code below this line

var hatValue = testObj.hat;      // Change this line
var shirtValue = testObj.shirt;    // Change this line
```

## Object Properties with Bracket Notation

```js
// Setup
var testObj = {
  "an entree": "hamburger",
  "my side": "veggies",
  "the drink": "water"
};

// Only change code below this line

var entreeValue = testObj["an entree"];   // Change this line
var drinkValue = testObj["the drink"];  // Change this line
```

## Accessing Object Properties with Variables
```js
// Setup
var testObj = {
  12: "Namath",
  16: "Montana",
  19: "Unitas"
};

// Only change code below this line;

var playerNumber = 16;       // Change this Line
var player = testObj[playerNumber];   // Change this Line
````

## Updating Object Properties
```js

// Setup
var myDog = {
  "name": "Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};

// Only change code below this line.
myDog.name = "Happy Coder";
```

## Add New Properties to a JavaScript Object
```js
// Setup
var myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};

// Only change code below this line.
myDog.bark = "woof";
```

## Delete Properties from a JavaScript Object
```js
// Setup
var myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"],
  "bark": "woof"
};

// Only change code below this line.
delete myDog.tails;
```

## Using Objects for Lookups
```js
// Setup
function phoneticLookup(val) {
  var result = "";

  // Only change code below this line
  var lookup = {
    "alpha": "Adams",
    "bravo": "Boston",
    "charlie": "Chicago",
    "delta": "Denver",
    "echo": "Easy",
    "foxtrot": "Frank",
  }
  result = lookup[val];

  // Only change code above this line
  return result;
}

// Change this value to test
phoneticLookup("charlie");
```

## Testing Objects for Properties
```js
// Setup
var myObj = {
  gift: "pony",
  pet: "kitten",
  bed: "sleigh"
};

function checkObj(checkProp) {
  // Your Code Here
  if (myObj.hasOwnProperty(checkProp) === true) {
  return myObj[checkProp];
  } else {
    return "Not Found";
  }
}

// Test your code by modifying these values
checkObj("gift");
```

## Manipulating Complex Objects
```js
var myMusic = [
  {
    "artist": "Billy Joel",
    "title": "Piano Man",
    "release_year": 1973,
    "formats": [ 
      "CD",
      "8T",
      "LP"
    ],
    "gold": true
  }
  // Add record here
,{
    "artist": "lalalal ala",
    "title": "asmamama",
    "release_year": 5973,
    "formats": [ 
      "sd",
      "3r",
      "Lff"]
  }
];
```

## Accessing Nested Objects
```js
// Setup
var myStorage = {
  "car": {
    "inside": {
      "glove box": "maps",
      "passenger seat": "crumbs"
     },
    "outside": {
      "trunk": "jack"
    }
  }
};

var gloveBoxContents = myStorage.car.inside["glove box"]; // Change this line
```

## Accessing Nested Arrays
```js
// Setup
var myPlants = [
  { 
    type: "flowers",
    list: [
      "rose",
      "tulip",
      "dandelion"
    ]
  },
  {
    type: "trees",
    list: [
      "fir",
      "pine",
      "birch"
    ]
  }  
];

// Only change code below this line

var secondTree = myPlants[1].list[1]; // Change this line
```

## Record Collection

```js
// Setup
var collection = {
    "2548": {
      "album": "Slippery When Wet",
      "artist": "Bon Jovi",
      "tracks": [ 
        "Let It Rock", 
        "You Give Love a Bad Name" 
      ]
    },
    "2468": {
      "album": "1999",
      "artist": "Prince",
      "tracks": [ 
        "1999", 
        "Little Red Corvette" 
      ]
    },
    "1245": {
      "artist": "Robert Palmer",
      "tracks": [ ]
    },
    "5439": {
      "album": "ABBA Gold"
    }
};
// Keep a copy of the collection for tests
var collectionCopy = JSON.parse(JSON.stringify(collection));

// Only change code below this line
function updateRecords(id, prop, value) {
  if (prop === "tracks" && value !== "") {
   if(collection[id][prop]) {
    collection[id][prop].push(value);
   }
   else {
    collection[id][prop]=[value];
   }
  } else if (value !== "") {
    collection[id][prop] = value;
  } else {
    delete collection[id][prop];
  }

  return collection;
}
// Alter values below to test your code
updateRecords(5439, "artist", "ABBA");
```

## Iterate with JavaScript While Loops
```js
// Setup
var myArray = [];

// Only change code below this line.
var i = 0;
while(i < 5) {
  myArray.push(i);
  i++;
}
```

## Iterate with JavaScript For Loops
```js

// Setup
var myArray = [];

// Only change code below this line.
for (var a = 1; a < 6; a++) {
    myArray.push(a);
}
```

## Iterate Odd Numbers With a For Loop
```js

// Setup
var myArray = [];

// Only change code below this line.

for (var a = 1; a < 10; a += 2) {
  myArray.push(a);
}
```

## Count Backwards With a For Loop
```js
// Setup
var myArray = [];

// Only change code below this line.
for (var a = 9; a > 0; a -= 2) {
  myArray.push(a);
}
```

## Iterate Through an Array with a For Loop
```js
// Setup
var myArr = [ 2, 3, 4, 5, 6];

// Only change code below this line
var total = 0;
for (var a = 0; a <myArr.length; a++) {
  total += myArr[a];
}
```

## Nesting For Loops (??)
```js
function multiplyAll(arr) {
  var product = 1;
  // Only change code below this line
  for(var i=0; i < arr.length; i++){
    for (var j=0; j < arr[i].length; j++){
      product = product * arr[i][j];
    }
  }
  // Only change code above this line
  return product;
}

// Modify values below to test your code
multiplyAll([[1,2],[3,4],[5,6,7]]);
```

## Iterate with JavaScript Do...While Loops
```js
// Setup
var myArray = [];
var i = 10;

// Only change code below this line.

do {
    myArray.push(i);
    i++;
}
while (i < 5) ;
```

##  Profile Lookup
```js
//Setup
var contacts = [
    {
        "firstName": "Akira",
        "lastName": "Laine",
        "number": "0543236543",
        "likes": ["Pizza", "Coding", "Brownie Points"]
    },
    {
        "firstName": "Harry",
        "lastName": "Potter",
        "number": "0994372684",
        "likes": ["Hogwarts", "Magic", "Hagrid"]
    },
    {
        "firstName": "Sherlock",
        "lastName": "Holmes",
        "number": "0487345643",
        "likes": ["Intriguing Cases", "Violin"]
    },
    {
        "firstName": "Kristian",
        "lastName": "Vos",
        "number": "unknown",
        "likes": ["JavaScript", "Gaming", "Foxes"]
    }
];
function lookUpProfile(name, prop){
// Only change code below this line
for (var x = 0; x < contacts.length; x++){
    if (contacts[x].firstName === name) {
        if (contacts[x].hasOwnProperty(prop)) {
            return contacts[x][prop];
        } else {
            return "No such property";
        }
    }
}
return "No such contact";
// Only change code above this line
}

// Change these values to test your function
lookUpProfile("Sherlock", "number");
```

## Generate Random Fractions with JavaScript
```js
function randomFraction() {
  // Only change code below this line.
  var result = 0;
  // Math.random() can generate 0. We don't want to     return a 0,
  // so keep generating random numbers until we get one     that isn't 0
  while (result === 0) {
    result = Math.random();
  }

  return result;  
  // Only change code above this line.
}
```

## Generate Random Whole Numbers with JavaScript
```js
var randomNumberBetween0and19 = Math.floor(Math.random() * 20);

function randomWholeNum() {

  // Only change code below this line.
return Math.floor(Math.random() * 10);
}
```

## Generate Random Whole Numbers within a Range
```js
function randomRange(myMin, myMax) {

  return Math.floor(Math.random() *( myMax - myMin + 1)) +myMin;

}

// Change these values to test your function
var myRandom = randomRange(5, 15);
```

## Use the parseInt Function
```js
function convertToInteger(str) {
return parseInt(str);  
}
convertToInteger("56");
```

## Use the parseInt Function with a Radix
```js
function convertToInteger(str) {
  return parseInt(str, 2);
}
convertToInteger("10011");
```

## Use the Conditional (Ternary) Operator
```js
function checkEqual(a, b) {
  return a == b ? true : false;
}

checkEqual(1, 2);
```

## Use Multiple Conditional (Ternary) Operators
```js
function checkSign(num) {
  return num == 0 ? "zero" : num < 0 ? "negative" : "positive";
}

checkSign(10);
```
