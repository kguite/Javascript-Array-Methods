# Javascript-Array-Methods

<h3 align="center">Javascript Array Methods</h3>

<p align="center">
    Welcome to my notes!
    <br />
</p>



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

### Syntax:<br>
#### Arrow Function:<br>
map((element, index, array) => { ... } )
<br>
#### Callback Function:<br>
map(callbackFn, thisArg)
<br>
#### Inline Callback Function:<br>
map(function callbackFn(element, index, array) { ... }, thisArg)
<br>
<br>
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
Reduce lorem epsom

### Syntax:<br>
#### Arrow Function:<br>
map((element, index, array) => { ... } )
<br>
#### Callback Function:<br>
map(callbackFn, thisArg)
<br>
#### Inline Callback Function:<br>
map(function callbackFn(element, index, array) { ... }, thisArg)
<br>
<br>
### First example:<br>
Given a non-empty array of integers, return the result of multiplying the values together in order. <br>
Example:<br>
[1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24<br>
<br>
const grow = (nums) => nums.reduce((product, num) => product * num, 1);
} <br>

### Second example:<br>



### Third example:<br>


## Filter
Filter blank

### Syntax:<br>
#### Arrow Function:<br>
map((element, index, array) => { ... } )
<br>
#### Callback Function:<br>
map(callbackFn, thisArg)
<br>
#### Inline Callback Function:<br>
map(function callbackFn(element, index, array) { ... }, thisArg)
<br>
<br>
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





## forEach
   forEach iterates through each element in the array.  This means it executes the function once on each item in the array, beginning to end. <br>
   It can accept up to three arguments.<br>
   <br>
   There are three main syntax types:<br>
   Arrow Function:
   forEach((element, index, array) => { ... } )

   Callback Function:
   forEach(callbackFunction, arg)

   Inline Callback Function:
   forEach(function callbackFunction(element, index, array) { ... })
   
   

## Sort

## Slice

## Pop

## Push

## Shift

## Unshift

## Includes

## indexOf

## Every








<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.





