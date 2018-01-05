# Javascript-Data-Structures-Objects-and-Arrays

In the previous lessons we have gone over data types and various ways to work with them. data types are just the basic building blocks of programming and we need data structures, and objects to use those building blocks and build something even greater with them.

In this section we will explore various ways to use our basic building blocks in Javascript.

## Data Sets
In the real world do you rarely deal with just one number or value at a time. To digitally represent a collection of values, in Javascript we use arrays.

Arrays are denoted with `[value1, value2]`

You can access your array values by referencing the variable name storing the array followed by the index of the value you want. e.g.

```
var arr = ['John', 'Elijah']

arr[0] \\ 'John'
```

Note that arrays start with index 0 and hence `arr[0]` returned the first value in the array collection.

## Properties

We have seen properties in action in our previous lectures. For example the `Math` object has properties attached to it that we have used already.

There are two ways to access a property in Javascript. `value.x` and `value[x]`. These two methods are slightly different. The dot notation fetches the property that it calls while the bracket notation evaluates the expression of the property calls.

## Methods

methods are functions that are attached to your Javascript objects. For example the string data structure has a `toUpperCase` function attached to it. This means that when you call this function on a valid string, it will up case that string value.

```
var str = 'hello';
str.toUpperCase(); // 'HELLO'
```
Almost all data types have many methods and properties attached to them. Understanding how to use them will be crucial to your success.

## Objects

When we want an arbitrary collection of properties we use the Javascript Object. Objects are denoted with curly brace notation `{}`.

Objects are created by a key name followed by a colon and the value. You can have multiple key value pairs in a object by separating them by commas.

```
var John = {
  name: 'John Kim',
  occupation: 'Software Engineer',
  numberOfKids: 1,
  hobbies: ['Programming', 'Video Games', 'Basketball']
}

console.log(John.name) // John Kim
console.log(John.hobbies[0]) // Programming
```

There are few notes before we move on. Objects are like any other data types, meaning we can pass them as parameters or store them in arrays.

Also you can have objects that have objects as values.

```
var out = {
  in: {
    hello: 'world'
  }
}

console.log(out.in.hello) // 'world'
```

## Mutability

for other data types, you can not change the property value associated to them. They are inherently immutable. For example the data type number 2, you cannot change the value of 2 to another value. However with objects you can change the values. Objects also behave a little differently when it comes to comparing them to each other. With objects, having two objects with the same properties values does not equal each other. Take the below example.

```
var obj1 = {value: 1}
var obj2 = {value: 1}

console.log(obj1 === obj2) // false
```

even if the value property is the same the two objs are different.

## Computing Correlation

A lot of computing work involves representing real world things into a digital form. Programmers can create their own world and rules in code. Let's take a chessboard for example and try to represent it in code. A chessboard is 8 x 8 so we can use a nested array.

```
var chessboard = [
  [BR,BK,BB,BQ,BC,BB,BK,BR],
  [BP,BP,BP,BP,BP,BP,BP,BP],
  [XX,XX,XX,XX,XX,XX,XX,XX],
  [XX,XX,XX,XX,XX,XX,XX,XX],
  [XX,XX,XX,XX,XX,XX,XX,XX],
  [XX,XX,XX,XX,XX,XX,XX,XX],
  [WP,WP,WP,WP,WP,WP,WP,WP],
  [WR,WK,WB,WC,WQ,WB,WK,WR],
]

console.log(chessboard[0][3]) // BQ
console.log(chessboard[0][3]) // WR
```

As you can see we now have a digital representation of where each piece is programatically.

Note that this is not the only to represent a chessboard and your imagination is what will only limit you.

## Common Methods and Properties in Javascript

This section will be a little different than the book. in this section we will go over the most common and useful properties and methods when working with certain built in Javascript data types and objects

The following is a list of properties and methods that will be helpful to you. It is not a complete list of methods and properties so look at the official documentations. Most of the definitions come from the below docs

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects

### Array Properties

- `Array.length`: Returns the length of the array

```
var arr = [1,2,3];
arr.length // 3
```

### Array Methods

Methods that Mutate the array.

- `pop`: removes the last element from an array and returns that element value.
- `push`: adds one or more elements to the end of an array and returns the new length of the array.
- `shift`: removes the first element from an array and returns that element.
- `unshift`: adds one or more elements to the front of an array and returns the new length of the array.
- `splice`: adds and/or removes elements from an array.
- `reverse`: reverse the order of the elements of an array in place.
- `sort`: 'sorts the elements of an array in place and returns the array'

```
var arr = [1, 2, 3, 4, 5]
console.log(arr.pop()) // 5
console.log(arr) // [1, 2, 3, 4]
console.log(arr.push(10)) // 5
console.log(arr) // [1, 2, 3, 4, 10]
console.log(arr.shift()) // 1
console.log(arr) // [2, 3, 4, 10]
console.log(arr.unshift(8)) // 5
console.log(arr) // [8, 2, 3, 4, 10]
var newArr = arr.splice(0,4);
console.log(arr) // 10
console.log(newArr) // [8, 2, 3, 4]
console.log(newArr.reverse()) // [4, 3, 2, 8]
console.log(newArr.sort()) //[2, 3, 4, 8]
```

Methods that accesses and returns some representation of the array.

- `concat`: Returns a new array with the combination of this array and other array / values.
- `includes`: returns a true if the value is in the array and false if not.
- `indexOf`: returns the first index of an element within the array. If not found returns -1
- `lastIndexOf`: returns the last index of an element within the array. If not found returns -1
- `join`: joins all elements of an array into a string
- `slice`: extracts a section of an array and returns a new array
- `toString`: returns a array as a string

```
var arr = [1,2,3]
var arr2 = [4,5,6]
console.log(arr) // [1, 2, 3]
console.log(arr2) // [4, 5, 6]
console.log(arr.concat(arr2)) // [1, 2, 3, 4, 5, 6]
console.log(arr.includes(1)) // true
console.log(arr2.includes(1)) // false
console.log(arr.indexOf(3)) // 2
console.log(arr2.indexOf(3)) // -1
console.log(arr.join('-')) // '1-2-3'
console.log(arr.slice(1, 3)) // [2, 3]
console.log(arr) // [1, 2, 3]
console.log(arr.toString()) // '1,2,3'
```

Methods that iterate through the array

- `every`: Returns true if every element in an array satisfies the provided testing function
- `some`: Returns true if at least one of the element in an array satisfies the provided testing function
- `filter`: Creates a new array with all of the elements of this array that satisfies the filtering function
- `find`: Returns the found value in the array, if an element in the array satisfies the provided testing function or undefined if not found.
- `findIndex`: returns the found index in the array, if an element in the array satisfies the provided testing function or -1 if not found
- `forEach`: calls the function for each element in the array. does not return
- `map`: creates a new array with the results of the calling of the provided function on every element
- `reduce`: Apply a function against an accumulation of each value of the array from right to left

```
var names = ['Elijah', 'Chimi', 'Mike']
console.log(names.every((e) => {return e.includes('i')})) // true
console.log(names.every((e) => {return e.includes('j')})) // false
console.log(names.some((e) => {return e.includes('j')})) // true

var filterNames = names.filter((e) => {return e.length > 4})
console.log(filterNames) // ['Elijah', 'Chimi']
console.log(filterNames.find((e) => {return e === 'Elijah'})) // Elijah
console.log(filterNames) // Notice none destructive for find
console.log(filterNames.findIndex((e) => {return e === 'Elijah'})) // 0

filterNames.forEach((e) => {
  console.log(e) // prints Elijah then Chimi
})

var mapArr = filterNames.map((e) => {return e.toUpperCase()})
console.log(mapArr) // ['ELIJAH', 'CHIMI']

var nums = [1,2,3]
console.log(nums.reduce((a, b) => {return a + b})) // 6
```

### String Properties

- `String.length`: Returns the length of the String

```
var str = 'hello';
str.length // 5
```

### String Methods

- `charAt`: returns the character (exactly one UTF-16 code unit) at the specified index.
- `charCodeAt`: Returns a number that is the UTF-16 code unit value at the given index.
- `concat`: returns the combination of two strings
- `includes`: determines whether one string may be found within another string
- `indexOf`: returns the index of the first occurrence of the specified value, or -1 if not found
- `lastIndexOf`: returns the index of the last occurrence of the specified value, or -1 if not found

- `slice`: extracts a section of a string and returns a new string
- `substring`: returns the characters in a string between two indexes into the string
- `substr`: returns the characters in a string from start to a length

```
String.slice( begin [, end ] )
String.substring( from [, to ] )
String.substr( start [, length ] )
```

- `split`: splits a string into an array of strings
- `toLowerCase`: returns the string as lower case
- `toUpperCase`: returns the string as Upper Case
- `toString`: converts a object type to string
- `trim`: removes whitespaces from beginning and end of the string

```
var firstName = 'Elijah';
var lastName = 'Kim';
console.log(firstName.charAt(3)) // j
console.log(firstName.charCodeAt(3)) // 106
var fullName = firstName.concat(' ', lastName);
console.log(fullName) // Elijah Kim
console.log(fullName.includes('E')) // true
console.log(fullName.indexOf('i')) // 2
console.log(fullName.lastIndexOf('i')) // 8
console.log(fullName.slice(0,6)) // Elijah
console.log(fullName.substring(1, 3)) // li
console.log(fullName.substr(1, 3)) // lij
console.log(fullName) // Elijah Kim
console.log(fullName.split(' ')) // [ 'Elijah', 'Kim' ]
console.log(fullName.toLowerCase()) // elijah kim
console.log(fullName.toUpperCase()) // ELIJAH KIM

var arrSentence = ['hello', 'world']
console.log(arrSentence.toString()) // hello,world
var whiteSpaceSentance = '     hello     ';
console.log(whiteSpaceSentance) //      hello
console.log(whiteSpaceSentance.trim()) // hello
```

### Object methods

- `Object.values`: returns an array of a given object's own enumerable values.
- `Object.keys`: returns an array containing the names of all of the given object's own enumerable properties.

```
var obj = {
  name: 'John',
  age: 29,
  job: 'SWE'
}

console.log(Object.values(obj)) //['John', 29, 'SWE']
console.log(Object.keys(obj)) //['name', 'age', 'job']
```

## Challenges
### Tic Tact Toe

In this challenge, your task is to digitally represent the following tic tact toe board.

```
|X|O|X|
|X|X|O|
|O|O|X|
```
### Object Access

Using the below human Object complete the following tasks

1. log the human's full name in one string
2. change his hobbies to only have `Hacking, Surfing`
3. add the `Ruby` into his programmingLanguage

you can add things into an array with `arr.push(value)`

```
var human = {
  firstName = "Jake",
  lastName = "Larson",
  age = 34,
  hobbies: ['Hiking', 'Programming', 'Video Games'],
  skills: {
    programmingLanguage: ['Javascript', 'Java', 'Python']
  }
}
```

### Sum up all numbers in array

Using your knowledge of arrays, sum up all of the numbers in a array
```
var arr = [10,5,3]
// sum of all arr is 18
```
### Deep Compare

As you already know two objects are not equal to each other in Javascript, even if the key values inside
the object is exactly the same.

write a function that will deeply compare objects and return true if they have the same key value pairs inside the objects

```
var obj1 = { num: 5 }
var obj2 = { num: 5 }

console.log(deepCompare(obj1, obj2)) // this should equal true

function deepCompare() {
  // write code here
}

```
