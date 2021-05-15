# Javascript-Array-Methods

<h3 align="center">Javascript Array Methods</h3>

<p align="center">
    Welcome to my review notes!
    <br />
</p>

<p>This repository is designed to be used for active recall and review exercises.  Included are thirteen of the most frequently used Javascript array methods.  Please feel free to take and use freely!</p>

<p>Resources cited at bottom.</p>


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ul>
    <li>
      <a href="#about-the-project">About The Project</a>
  </ul>
      <ul>
      </ul>
    <ol>
    <li><a href="#map">Map</a></li>
    <li><a href="#reduce">Reduce</a></li>
    <li><a href="#filter">Filter</a></li>
    <li><a href="#forEach">forEach</a></li>
    <li><a href="#sort">sort</a></li>
    <li><a href="#slice">slice</a></li>
     <li><a href="#pop">pop</a></li>
     <li><a href="#shift">shift</a></li>
     <li><a href="#push">push</a></li>
    <li><a href="#unshift">unshift</a></li>
    <li><a href="#includes">includes</a></li>
    <li><a href="#indexOf">indexOf</a></li>
    <li><a href="#every">every</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)


A few quick notes:
* Learn with Leon is the best.
* Examples of each array method will be added to this repository in the future.  Maybe I'll give each folder a README and break up this long one.
* Resources posted at the bottom in the acknowledgments.

Examples of each array method will be added to the repository throughout the week.

Resources posted at the bottom in the acknowledgments.

## Map
Map calls a provided function once for each element in the array, then creates a new array with the updated values.


### First example:<br>
<br>
let numbers = [1, 4, 9] <br>
let roots = numbers.map(function(num) { <br>
    return Math.sqrt(num) <br>
})
// roots is now     [1, 2, 3] <br>
// numbers is still [1, 4, 9] <br>

### Second example:<br>
<br>
Given an array of integers, return a new array with each value doubled.<br>
<br>
For example:<br>
<br>
[1, 2, 3] --> [2, 4, 6]<br>
<br> 
function maps(x){ <br>
  return x.map(n => n * 2); <br>
}


### Third example:<br>
(from MDN)<br>
let numbers = [1, 4, 9] <br>
let roots = numbers.map(function(num) { <br>
    return Math.sqrt(num) <br>
})
// roots is now     [1, 2, 3] <br>
// numbers is still [1, 4, 9] <br>


## Reduce
the reduce() method executes a reducer function (that we make) on each element of the array, resulting in a single output value. 


### First example:<br>
Given a non-empty array of integers, return the result of multiplying the values together in order. <br>
Example:<br>
[1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24<br>
<br>
const grow = (nums) => nums.reduce((product, num) => product * num, 1);
} <br>

### Second example:<br>
Given an array of Boolean values and a logical operator, return a Boolean result based on sequentially applying the operator to the values in the array. <br>

As Example:<br>
booleans = [True, True, False], operator = "AND" <br>
True AND True -> True <br>
True AND False -> False <br>
return False <br>
<br>


var ops = { <br>
  'AND': (a, b) => a && b,<br>
  'OR': (a, b) =>  a || b,<br>
  'XOR': (a, b) => a !== b<br>
}<br>
<br>
function logicalCalc(array, op){<br>
  return array.reduce(ops[op]);<br>
}<br>

### Third example:<br>
(assuming there's a list of items and their prices, like gum = 2, soda = 3, candy = 5) <br>
const total = items.reduce((item, currentTotal) => { <br>
     return item.price + currentTotal <br>
     }, 0) <br>
     
The 0 is telling the function where to start - at zero.  Then it iterates through the array and starts with the first (eg: gum, 2), and displays the current total plus the price of the item.  So for the very first row, it starts at 0 plus 2 = current total of 2.  Then it stays at 2 and adds 3, to make the current total 5.  Then current total 5, plus candy is 5, total is 10.

## Filter
Filter returns a new array, only including elements that pass the test in the first array. Such as < 100, divisible by 2, string length longer than 5, etc.


### First example:<br>
Complete the function which takes two arguments and returns all numbers which are divisible by the given divisor. First argument is an array of numbers and the second is the divisor.<br>
Example: divisibleBy([1, 2, 3, 4, 5, 6], 2) == [2, 4, 6] <br>
<br>
function divisibleBy(numbers, divisor) { <br>
  return numbers.filter(n => n % divisor === 0) <br>
} <br>

### Second example:<br>
Take an array and remove every second element from the array. Always keep the first element and start removing with the next element.<br>
<br>
Example: <br>
<br>
["Keep", "Remove", "Keep", "Remove", "Keep", ...] --> ["Keep", "Keep", "Keep", ...]<br>
<br>
function removeEveryOther(arr){ <br>
  return arr.filter(function(elem, index) { <br>
    return index % 2 === 0; <br>
  }); <br>
} <br>
or alternatively: <br>
const removeEveryOther = arr => arr.filter((item, i) =>  i % 2 == 0); <br>

### Third example:<br>
<br>
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];<br>
<br>
const result = words.filter(word => word.length > 6);<br>
<br>
console.log(result);<br>
// expected output: Array ["exuberant", "destruction", "present"]<br>

#### Bonus Fourth Example! This one's pretty neat:

Consider an array/list of sheep where some sheep may be missing from their place. We need a function that counts the number of sheep present in the array (true means present). <br>
<br>
For example,  <br>
 <br>
[true,  true,  true,  false, <br>
  true,  true,  true,  true ,<br>
  true,  false, true,  false,<br>
  true,  false, false, true ,<br>
  true,  true,  true,  true ,<br>
  false, false, true,  true]<br>
  <br>
The correct answer would be 17.<br>
<br>
Hint: Don't forget to check for bad values like null/undefined. <br>
<br>
function countSheeps(arrayOfSheeps) { <br>
  return arrayOfSheeps.filter(Boolean).length; <br>
} <br>



## forEach
   forEach iterates through each element in the array.  This means it executes the function (that we provide) once on each item in the array, beginning to end. <br>
   forEach expects a synchronous function.<br>
<br>
forEach does not wait for promises. Make sure you are aware of the implications while using promises (or async functions) as forEach callback.<br>
<br>

   It can accept up to three arguments.<br>
   <br>

### First example, Converting a for loop to a forEach:
const items = ['item1', 'item2', 'item3'] <br>
const copyItems = []<br>
<br>
// before<br>
for (let i = 0; i < items.length; i++) {<br>
  copyItems.push(items[i])<br>
}<br>
<br>
// after<br>
items.forEach(function(item){<br>
  copyItems.push(item)<br>
})<br>
<br>
### Second example, modifying the array during iteration:
<br>
let words = ['one', 'two', 'three', 'four']<br>
words.forEach(function(word) {<br>
  console.log(word)<br>
  if (word === 'two') {<br>
    words.shift() //'one' will delete from array<br>
  }<br>
}) // one // two // four<br>
<br>
console.log(words);  //['two', 'three', 'four']<br>

<br>
### Third example, with promises: <br>
   <br>
   let ratings = [5, 4, 5]; <br>
let sum = 0; <br>
<br>
let sumFunction = async function (a, b) <br>
{ <br>
  return a + b <br>
} <br>
<br>
ratings.forEach(async function(rating) { <br>
  sum = await sumFunction(sum, rating) <br>
}) <br>
<br>
console.log(sum) <br>
// Naively expected output: 14 <br>
// Actual output: 0 <br>
   

## Sort
The sort() method sorts the elements of a typed array numerically in place and returns the typed array. This method has the same algorithm as Array.prototype.sort(), except that sorts the values numerically instead of as strings. TypedArray is one of the typed array types here.<br>
<br>
The sort() method sorts the elements of an array in place and returns the sorted array. The default sort order is ascending, built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.<br>

<br>

### First example, a simple numerical sort:
const uint8 = new Uint8Array([40, 10, 50, 20, 30]); <br>
uint8.sort();<br> 
<br>
console.log(uint8); <br>
// expected output: Uint8Array [10, 20, 30, 40, 50] <br>
<br>

### Second example, alphabetical sort:
const months = ['March', 'Jan', 'Feb', 'Dec']; <br>
months.sort(); <br>
console.log(months); <br>
// expected output: Array ["Dec", "Feb", "Jan", "March"] <br>
<br>
const array1 = [1, 30, 4, 21, 100000]; <br>
array1.sort(); <br>
console.log(array1); <br>
// expected output: Array [1, 100000, 21, 30, 4] <br>
<br>

### Third example, sorting by value:
<br>
var items = [ <br>
  { name: 'Edward', value: 21 },<br>
  { name: 'Sharpe', value: 37 },<br>
  { name: 'And', value: 45 },<br>
  { name: 'The', value: -12 },<br>
  { name: 'Magnetic', value: 13 },<br>
  { name: 'Zeros', value: 37 }<br>
];<br>
<br>
// sort by value<br>
items.sort(function (a, b) {<br>
  return a.value - b.value;<br>
});<br>
<br>

## Slice
The slice() method returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included) where start and end represent the index of items in that array. The original array will not be modified.   

Great examples here: https://www.javascripttutorial.net/javascript-array-slice/

### First example:<br>
Write a function to get the first elements of asequence. Passing a parameter n (default=1) will return the first n elements of the sequence. <br>
<br>
If n == 0 return an empty sequence []<br>
<br>
As Example: <br>
var arr = ['a', 'b', 'c', 'd', 'e']; <br>
first(arr) //=> ['a']; <br>
first(arr, 2) //=> ['a', 'b'] <br>
first(arr, 3) //=> ['a', 'b', 'c']; <br>
first(arr, 0) //=> []; <br>
<br>
function first(arr, n=1) { <br>
   return arr.slice(0,n); <br>
} <br>

### Second example, copying a portion of an array::<br>
The typical use of the slice() method is to copy a portion of an array without modifying the source array. Here is an example:<br>
<br>
var colors = ['red','green','blue','yellow','purple']; <br>
var rgb = colors.slice(0,3); <br>
console.log(rgb); // ["red", "green", "blue"] <br>
Code language: JavaScript (javascript) <br>
The rgb array contains the first three elements of the colors array. The source array colors remains intact.<br>



### Third example, converting an array-like object into an array:<br>
The slice() method is used to convert an array-like object into an array. For example: <br>
<br>
function toArray() { <br>
  return Array.prototype.slice.call(arguments); <br>
} <br>
<br>
var classification = toArray('A','B','C'); <br>
<br>
console.log(classification); // ["A", "B", "C"] <br>
Code language: JavaScript (javascript) <br>



## Pop
The pop() method removes the last element from an array and returns that element. This method changes the length of the array.




### First example:
const plants = ['broccoli', 'cauliflower', 'cabbage', 'kale', 'tomato'];<br>
<br>
console.log(plants.pop());<br>
// expected output: "tomato"<br>
<br>
console.log(plants);<br>
// expected output: Array ["broccoli", "cauliflower", "cabbage", "kale"]<br>
<br>
plants.pop();<br>
<br>
console.log(plants);<br>
// expected output: Array ["broccoli", "cauliflower", "cabbage"]<br>

### Second example:
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];<br>
<br>
var popped = myFish.pop();<br>
<br>
console.log(myFish); // ['angel', 'clown', 'mandarin' ]<br>
<br>
console.log(popped); // 'sturgeon'<br>
### Third example:
var myFish = {0:'angel', 1:'clown', 2:'mandarin', 3:'sturgeon', length: 4};<br>
<br>
var popped = Array.prototype.pop.call(myFish); //same syntax for using apply( )<br>
<br>
console.log(myFish); // {0:'angel', 1:'clown', 2:'mandarin', length: 3}<br>
<br>
console.log(popped); // 'sturgeon'<br>
<br>


## Push
The push() method adds one or more elements to the end of an array and returns the new length of the array.   


### First example:<br>
Create a function with two arguments that will return an array of the first (n) multiples of (x). <br>
Return the results as an array.<br>
<br>
As Example: <br>
countBy(1,10) === [1,2,3,4,5,6,7,8,9,10] <br>
countBy(2,5) === [2,4,6,8,10] <br>
<br>
function countBy(x, n) { <br>
    var z = []; <br>
    for (i = 1; i <= n; i++) { <br>
        z.push(x * i); <br>
    } <br>
    return z; <br>
}<br>

### Second example:<br>
const animals = ['pigs', 'goats', 'sheep']; <br>
<br>
const count = animals.push('cows');<br>
console.log(count);<br>
// expected output: 4<br>
console.log(animals);<br>
// expected output: Array ["pigs", "goats", "sheep", "cows"]<br>
<br>
animals.push('chickens', 'cats', 'dogs');<br>
console.log(animals);<br>
// expected output: Array ["pigs", "goats", "sheep", "cows", "chickens", "cats", "dogs"]<br>


### Third example:<br>
let vegetables = ['parsnip', 'potato'] <br>
let moreVegs = ['celery', 'beetroot'] <br>
<br>
// Merge the second array into the first one <br>
// Equivalent to vegetables.push('celery', 'beetroot') <br>
Array.prototype.push.apply(vegetables, moreVegs) <br>
<br>
console.log(vegetables)  // ['parsnip', 'potato', 'celery', 'beetroot'] <br>
<br>


## Shift
The shift() method removes the first element from an array and returns that removed element. This method changes the length of the array.<br>
Does this remind you of another array method in this guide?  <br>
I remember the shift method by remembering that the shift key needs to be pressed BEFORE the second key, therefore the shift method removes the FIRST element.  Kinda clunky but works for me.  Which array method removes and returns the last element in an array?<br>
hint: pop()<br>
I remember this one like, pop rocks are desserts, desserts come at the end.

### First example:
const array1 = [1, 2, 3];<br>
<br>
const firstElement = array1.shift();<br>
<br>
console.log(array1);<br>
// expected output: Array [2, 3]<br>
<br>
console.log(firstElement);<br>
// expected output: 1<br>


### Second example:
var myFish = ['angel', 'clown', 'mandarin', 'surgeon'];<br>
<br>
console.log('myFish before:', JSON.stringify(myFish));<br>
// myFish before: ['angel', 'clown', 'mandarin', 'surgeon']<br>
<br>
var shifted = myFish.shift();<br>
<br>
console.log('myFish after:', myFish);<br>
// myFish after: ['clown', 'mandarin', 'surgeon']<br>
<br>
console.log('Removed this element:', shifted);<br>
// Removed this element: angel<br>

### Third example, using shift in a for loop:
<br>
var names = ["Andrew", "Edward", "Paul", "Chris" ,"John"];<br>
<br>
while( typeof (i = names.shift()) !== 'undefined' ) {<br>
    console.log(i);<br>
}<br>
// Andrew, Edward, Paul, Chris, John<br>


## Unshift
The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.
When more than one element is added at once, they are all added to the beginning together.<br>
### First example:
const array1 = [1, 2, 3];<br>
<br>
console.log(array1.unshift(4, 5));<br>
// expected output: 5<br>
<br>
console.log(array1);<br>
// expected output: Array [4, 5, 1, 2, 3]<br>
<br>
### Second example:
let arr = [4, 5, 6]<br>
<br>
arr.unshift(1, 2, 3)<br>
console.log(arr);<br>
// [1, 2, 3, 4, 5, 6]<br>
<br>
arr = [4, 5, 6] // resetting the array<br>
<br>
arr.unshift(1)<br>
arr.unshift(2)<br>
arr.unshift(3)<br>
<br>
console.log(arr)<br>
// [3, 2, 1, 4, 5, 6]<br>

### Third example:
var languages = ["JavaScript", "Python", "Java", "Lua"];<br>
<br>
var count = languages.unshift("C++");<br>
console.log(languages); // [ 'C++', 'JavaScript', 'Python', 'Java', 'Lua' ]<br>
console.log(count); // 5<br>
<br>
var priceList = [12, 21, 35];<br>
<br>
var count1 = priceList.unshift(44, 10, 1.6);<br>
console.log(priceList); // [ 44, 10, 1.6, 12, 21, 35 ]<br>
console.log(count1); // 6<br>
<br>

## Includes
The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate.<br>
Remember: "Does this include this? answer is yes or no"

### First example:
const array1 = [1, 2, 3];<br>
<br>
console.log(array1.includes(2));<br>
// expected output: true<br>
<br>
const pets = ['cat', 'dog', 'bat'];<br>
<br>
console.log(pets.includes('cat'));<br>
// expected output: true<br>
<br>
console.log(pets.includes('at'));<br>
// expected output: false<br>

### More examples:
[1, 2, 3].includes(2)      // true
[1, 2, 3].includes(4)      // false
[1, 2, 3].includes(3, 3)   // false
[1, 2, 3].includes(3, -1)  // true
[1, 2, NaN].includes(NaN)  // true


## indexOf
finds the index of a given substring within a string.

### First example, finding the index of a substring within a string:
let str = 'finding substring in string';<br>
let index = str.indexOf('str');<br>
<br>
console.log(index); // 11<br>
// note the 11 index finds the first 'str' within the string.<br>
### Second example, counting occurrence of a substring within a string:
let str = 'You do not know what you do not know until you know.';<br>
let substr = 'know';<br>
<br>
let count = 0;<br>
<br>
let index = str.indexOf(substr);<br>
while(index !== -1) {<br>
    count++;<br>
    index = str.indexOf(substr, index + 1);<br>
}<br>
<br>
console.log(count);<br>
Code language: JavaScript (javascript)<br>
How it works:<br>
### Third example, what if there isn't a substring in the string?<br>
const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];<br>
<br>
console.log(beasts.indexOf('giraffe'));<br>
// expected output: -1<br>
// -1 means that substring is not found.<br>

## Every(fn)
The every() method is similar to the some() method, but instead of checking for at least one item, it checks to make sure every single item falls under the test.<br>

The function fn is called on each element of the array similar to map. If any/all results are true, returns true, otherwise false.<br>

These methods behave sort of like || and && operators: if fn returns a truthy value, arr.some() immediately returns true and stops iterating over the rest of items; if fn returns a falsy value, arr.every() immediately returns false and stops iterating over the rest of items as well.<br>

Note: Calling this method on an empty array will return true for any condition!<br>

### First example:<br>
(assuming there's a price list with a variety of items and their prices, $1-$100) <br>
const cheapPrice = items.every((item) => { <br>
    return item.price <= 75 <br>
   })  <br>
 // will return false, because some items are more than $75. if we changed this to 750, it would return true. <br>

### Second example:<br>
function arraysEqual(arr1, arr2) {<br>
  return arr1.length === arr2.length && arr1.every((value, index) => value === arr2[index]);<br>
}<br>
<br>
alert( arraysEqual([1, 2], [1, 2])); // true<br>
<br>

### Third example:<br>
Polyfill! On Javascript MDN, there's a code that can be inserted at the beginning of your script to be sure that every() can be used.<br>

"every was added to the ECMA-262 standard in the 5th edition, and it may not be present in other implementations of the standard. You can work around this by inserting the following code at the beginning of your scripts, allowing use of every in implementations which do not natively support it."

"This algorithm is exactly the one specified in ECMA-262, 5th edition, assuming Object and TypeError have their original values, and that callbackfn.call evaluates to the original value of Function.prototype.call."

MORE INFO HERE: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every



<!-- RESOURCES -->
## Resources:
    MDN
    https://www.javascripttutorial.net/
    Codewars.com
    https://javascript.info/array-methods

<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.





