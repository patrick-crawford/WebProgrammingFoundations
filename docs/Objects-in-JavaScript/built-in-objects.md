---
id: built-in-objects
title: Built in Objects
sidebar_position: 1
description: Built in Objects
---

# Built in Objects

As we have seen, JavaScript is a flexible and widely adopted programming language. It provides a wealth of integrated objects that enable numerous capabilities across both client-side and server-side environments. These objects encompass fundamental JavaScript operations such as working with a [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map), [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math), [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date), [Error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error), [etc...](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects) We also have Node.js-specific objects tailored for managing file systems, processing HTTP requests, and other server-side operations.

Let's begin by discussing some of the built-in objects that come bundled with the JavaScript language, as well as some of the key functions that exist in the Node.js ecosystem.

## String

Here are a few examples of how you can declare a [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) in JavaScript, first using a string literal (which we have already discussed), followed by a call to the [`new` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) and the `String` object's constructor function:

```js
/*
 * JavaScript String Literals
 */
let s = 'some text'; // single-quotes
let s1 = 'some text'; // double-quotes
let s2 = `some text`; // template literal using back-ticks
let unicode =
  '中文 español Deutsch English देवनागरी العربية português বাংলা русский 日本語 ਪੰਜਾਬੀ 한국어 தமிழ் עברית'; // non-ASCII characters

/*
 * JavaScript String Constructor: `new String()` creates a new instance of a String
 */
let s3 = new String('Some Text');
let s4 = new String('Some Text');
```

If we want to convert other types to a `String`, we have a few options:

```js
let x = 17;
let s = '' + x; // concatenate with a string (the empty string)
let s2 = String(x); // convert to String. Note: the `new` operator is not used here
let s3 = x.toString(); // use a type's .toString() method
```

Whether you use a literal or the constructor function, in all cases you will be able to use
the various [functionality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/prototype#Properties) of the [`String` type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

### Common Properties and Methods

- [`s.length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length) - will tell us the length of the string (UTF-16 code units)

- [`s.charAt(1)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt) - returns the character at the given position (UTF-16 code unit). We can also use `s[1]` and use an index notation to get a particular character from the string.

- [`s.concat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat) - returns a new string created by concatenating the original with the given arguments.

- [`s.padStart(2, '0)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padStart) - returns a new string padded with the given substring until the length meets the minimum length given. See also [`s.padEnd()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padEnd).

- [`s.includes("tex")`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes) - returns `true` if the search string is found within the string, otherwise `false` if not found.

- [`s.startsWith("some")`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith) - returns `true` if the string starts with the given substring, otherwise `false`.

- [`s.endsWith("text")`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith) - returns `true` if the string ends with the given substring, otherwise `false`.

- [`s.indexOf("t")`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf) - returns the first index position of the given substring within `s`, or `-1` if the substring is not found within `s`. See also [`s.lastIndexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf)

- [`s.match(regex)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match) - tries to match a [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions) against the string, returning the matches.

- [`s.replace(regex, "replacement")`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) - returns a new string with the first occurrence of a matched RegExp replaced by the replacement text. See also [`s.replaceAll()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll), which replaces _all_ occurrences.

- [`s.slice(2, 3)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice) - returns a new string extracted (sliced) from within the original string. A beginning index and (optional) end index mark the position of the slice.

- [`s.split()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) - returns an Array (see discussion below) of substrings by splitting the original string based on the given separator (`String` or `RegExp`).

- [`s.toLowerCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase) - returns a new string with all characters converted to lower case.

- [`s.toUpperCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase) - returns a new string with all characters converted to upper case.

- [`s.trim()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim) - returns a new string with leading and trailing whitespace removed.

> **NOTE:** JavaScript also supports [template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals), also sometimes called template _strings_. Template literals use back-ticks instead of single- or double-quotes, and allow you to interpolate JavaScript expressions. For example:
>
> ```js
> let a = 1;
> let s = 'The value is ' + 1 * 6;
> // Use ${...} to interpolate the value of an expression into a string
> let templateVersion = `The value is ${1 * 6}`;
> ```

## Array

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) is also technically an `Object` with various [properties and methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Array_instances) we can use for working with lists in JavaScript.

### Declaring JavaScript Arrays

Like creating a `String`, we can create an `Array` in JavaScript using either a literal (which we have seen) or the `Array` constructor function:

```js
let arr = new Array(1, 2, 3); // array constructor
let arr2 = [1, 2, 3]; // array literal
```

### Accessing Elements in an Array

We can use index notation to obtain an element at a given index:

```js
let numbers = [50, 12, 135];
let firstNumber = numbers[0];
let lastNumber = numbers[numbers.length - 1];
```

JavaScript also allows us to use a technique called [Destructuring Assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) to unpack values in an Array into distinct variables. Consider each of the following methods, both of which accomplish the same goal:

```js
// Co-ordinates for Seneca's Newnham Campus
let position = [43.796, -79.3486];

// Separate the two values into their own unique variables.

// Version 1 - index notation
let lat = position[0];
let lng = position[1];

// Version 2 - destructure
let [lat, lng] = position;
```

This technique is useful when working with structured data, where you know exactly how many elements are in an array, and need to access them:

```js
let dateString = `17/02/2001`;
let [day, month, year] = dateString.split('/');
console.log(`The day is ${day}, month is ${month}, and year is ${year}`);
```

Here we `.split()` the string `'17/02/2001'` at the `'/'` character, which will produce the Array `['17', '02', '2001']`. Next, we destructure this Array's values into the variables `day`, `month`, `year`.

You can also ignore values (i.e., only unpack the one or ones you want):

```js
let dateString = `17/02/2001`;
// Ignore the first index in the array, unpack only position 1 and 2
let [, month, year] = dateString.split('/');
console.log(`The month is ${month}, and year is ${year}`);

let emailAddress = `jsmith@myseneca.ca`;
// Only unpack the first position, ignoring the second
let [username] = emailAddress.split('@');
console.log(`The username for ${emailAddress} is ${username}`);
```

### Common Properties and Methods

- [`arr.length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length) - a property that tells us the number of elements in the array.

**Methods that modify the original array**

- [`arr.push(element)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) - a method to add one (or more) element(s) to the end of the array. Using `push()` modifies the array (increasing its size). You can also use [`arr.unshift(element)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) to add one (or more) element to the _start_ of the array.
- [`arr.pop()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) - a method to remove the last element in the array and return it. Using `pop()` modifies the array (reducing its size). You can also use [`arr.shift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) to remove the _first_ element in the array and return it.

**Methods that do not modify the original array**

- [`arr.concat([4, 5], 6)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat) - returns a new array with the original array joined together with other arrays or values provided.
- [`arr.includes(element)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) - returns `true` if the array includes the given element, otherwise `false`.
- [`arr.indexOf(element)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf) - returns the index of the given element in the array, if it exists, otherwise `-1` (meaning not found).
- [`arr.join("\n")`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join) - returns a string created by joining (concatenating) all elements in the array with the given delimiter (`String`).

**Methods for iterating across the elements in an Array**

JavaScript's `Array` type also provides a [long list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#) of useful methods for working with list data. All of
these methods work in roughly the same way:

```js
// Define an Array
let list = [1, 2, 3, 4];

// Define a function that you want to call on each element of the array
function operation(element) {
  // do something with element...
}

// Call the Array method that you want, passing your function operation
list.arrayOperation(operation);
```

JavaScript will call the given function on every element in the array, one after
the other. Using these methods, we are able to work with the elements in an Array
instead of only being able to do things with the Array itself.

As a simple example, let's copy our `list` Array and add 3 to every element.
We'll do it once with a for-loop, and the second time with the `forEach()` method:

```js
// Create a new Array that adds 3 to every item in list, using a for-loop
let listCopy = [];

for (let i = 0; i < list.length; i++) {
  let element = list[i];
  element += 3;
  listCopy.push(element);
}
```

Now the same code using the `Array`'s `forEach()` method:

```js
let listCopy = [];

list.forEach(function (element) {
  listCopy.push(element + 3);
});
```

We've been able to get rid of all the indexing code, and with it, the chance
for [off-by-one errors](https://en.wikipedia.org/wiki/Off-by-one_error). We
also don't have to write code to get the element out of the list: we just use
the variable passed to our function.

These `Array` methods are so powerful that there are often functions that do
exactly what we need. For example, we could shorten our code above even further
but using the `map()` method. The `map()` method takes one `Array`, and calls
a function on every element, creating and returning a new `Array` with those
elements:

```js
let listCopy = list.map(function (element) {
  return element + 3;
});
```

Here are some of the `Array` methods you should work on learning:

- [`arr.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) - calls the provided function on each element in the array.
- [`arr.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) - creates and returns a new array constructed by calling the provided function on each element of the original array.
- [`arr.find()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find) - finds and returns an element from the array which matches a condition you define. See also [`arr.findLast()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLast), [`arr.findIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex), and [`arr.findLastIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLastIndex), which all work in similar ways.
- [`arr.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) - creates and returns a new array containing only those elements that match a condition you define in your function.
- [`arr.every()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every) - returns `true` if all of the elements in the array meet a condition you define in your function.

There are more [`Array` methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Array_instances) you can learn as you progress with JavaScript, but these will get you started.

### Iterating over String, Array, and other collections

The most familiar way to iterate over a `String` or `Array` works as you'd expect:

```js
let s = 'Hello World!';
for (let i = 0; i < s.length; i++) {
  let char = s.charAt(i);
  console.log(i, char);
  // Prints:
  // 0, H
  // 1, e
  // 2, l
  // ...
}

let arr = [10, 20, 30, 40];
for (let i = 0; i < arr.length; i++) {
  let elem = arr[i];
  console.log(i, elem);
  // Prints:
  // 0, 10
  // 1, 20
  // 2, 30
  // ...
}
```

The standard `for` loop works, but is not the best we can do. Using a `for` loop
is prone to various types of errors: off-by-one errors, for example. It also
requires extra code to convert an index counter into an element.

An alternative approach is available in ES6, [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of):

```js
let s = 'Hello World!';
for (let char of s) {
  console.log(char);
  // Prints:
  // H
  // e
  // l
  // ...
}

let arr = [10, 20, 30, 40];
for (let elem of arr) {
  console.log(elem);
  // Prints:
  // 10
  // 20
  // 30
  // ...
}
```

Using `for...of` we eliminate the need for a loop counter altogether, which has
the added benefit that we'll never under- or over- shoot our collection's element
list; we'll always loop across exactly the right number of elements within the
given collection.

The `for...of` loop works with all collection types, from `String` to `Array` to
`arguments` to `NodeList` (as well as newer collection types like
[`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map),
[`Set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set), etc.).

## Date

The [Date object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) represents a single moment in time and provides methods to work with dates and times.

### Creating Dates

We can create a new Date object Using the new Date() Constructor

```js
let now = new Date(); // Current date and time
```

If we wish to set a specific date and time, ie: "May 21st 2024 at 12:34:56" (using a 24-hour format), we have a number of options:

```js
let specificDate = new Date('May 21, 2024 12:34:56'); // DISCOURAGED: may not work in all runtimes
let specificDate = new Date('2024-05-21T12:34:56'); // This is standardized and will work reliably
let specificDate = new Date(2024, 4, 21); // The month is 0-indexed
let specificDate = new Date(2024, 4, 21, 12, 34, 56); // Also passing hours, minutes & seconds
let specificDate = new Date(1684639396000); // Passing epoch timestamp
```

### Common Properties and Methods

`let currentTime = new Date();` - will give us the current date / time

**Methods to Set Individual Parts of the Date Object**

```js
let date = new Date();

date.setFullYear(2024); // Sets the year
date.setMonth(5); // Sets the month (0-based)
date.setDate(21); // Sets the day
date.setHours(12); // Sets the hour
date.setMinutes(34); // Sets the minutes
date.setSeconds(56); // Sets the seconds

// etc... (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
```

**Methods to Get Individual Parts of the Date Object:**

```js
let date = new Date();

console.log(date.getFullYear()); // Gets the year
console.log(date.getMonth()); // Gets the month (0-based)
console.log(date.getDate()); // Gets the day
console.log(date.getHours()); // Gets the hour
console.log(date.getMinutes()); // Gets the minutes
console.log(date.getSeconds()); // Gets the seconds

// etc... (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
```

**Methods to Output the Full Date String**

```js
let date = new Date();

console.log(date.toString()); // outputs a string representing this date interpreted in the local timezone
console.log(date.toDateString()); // outputs a string representing the date portion of the date interpreted in the local timezone
console.log(date.toTimeString()); // outputs a string representing the time portion of the date interpreted in the local timezone
console.log(date.toLocaleString('fr-CA')); // outputs a string with a language-sensitive representation of the date and time (ie "Canadian French")
console.log(date.toLocaleDateString('fr-CA')); // outputs a string with a language-sensitive representation of the date portion only (ie "Canadian French")
console.log(date.toLocaleTimeString('fr-CA')); // outputs a string with a language-sensitive representation of the time portion only (ie "Canadian French")
console.log(date.toISOString()); // outputs a string in simplified extended ISO format (always 24 or 27 characters long: YYYY-MM-DDTHH:mm:ss.sssZ or ±YYYYYY-MM-DDTHH:mm:ss.sssZ)
console.log(date.toUTCString()); // outputs a string representing the date in UTC (Universal Time Coordinated) time zone
```

### Comparing Dates

To compare dates, we can use our familiar "greater than" / "less than", "equals", etc, operators:

```js
let date1 = new Date(2024, 5, 21);
let date2 = new Date(2024, 5, 22);

if (date1 < date2) {
  console.log('Date1 is earlier than Date2');
} else if (date1 > date2) {
  console.log('Date1 is later than Date2');
} else {
  console.log('Dates are equal');
}
```

## Node.js Globals

The following section outlines some [global objects](https://nodejs.org/api/globals.html), functions and variables that ship with the Node.js / JavaScript language.

### console

The [console object](https://nodejs.org/docs/latest/api/console.html) provides a simple debugging console that is similar to the JavaScript console mechanism provided by web browsers.

Some of the key methods that we will be using are:

<ul>
<li><a href="https://nodejs.org/docs/latest/api/console.html#consolelogdata-args" target="_blank">console.log()</a></li>
<li><a href="https://nodejs.org/docs/latest/api/console.html#consoletimelabel" target="_blank">console.time()</a> / <a href="https://nodejs.org/docs/latest/api/console.html#consoletimeendlabel" target="_blank">console.timeEnd()</a></li>
<li><a href="https://nodejs.org/docs/latest/api/console.html#consoledirobj-options" target="_blank">console.dir()</a></li>
</ul>

### \_\_dirname

[\_\_dirname](https://nodejs.org/docs/latest/api/modules.html#__dirname) is used to obtain name of the directory that the currently executing script resides in.

For example: if our .js file is located in /Users/pcrawford/ex1.js:

```js
console.log(__dirname);
// outputs /Users/pcrawford
```

### \_\_filename

[\_\_filename](https://nodejs.org/docs/latest/api/modules.html#__filename) is be used to obtain file containing the code being executed as well as the directory. This is the resolved absolute path of this code file.

For example: if our .js file is located in /Users/pcrawford/ex1.js:

```js
console.log(__filename);
// outputs /Users/pcrawford/ex1.js
```

### setTimeout()

The [setTimeout()](https://nodejs.org/docs/latest/api/timers.html#settimeoutcallback-delay-args) function will execute a piece of code (function) after a certain delay. It accepts 3 parameters:

<ul>
<li><strong>callback</strong> Function: The function to call when the timer elapses.</li>
<li><strong>delay</strong> number: The number of milliseconds to wait before calling the callback</li>
<li><strong>[, …arg]</strong> Optional arguments to pass when the callback is called.</li>
</ul>

For example:

```js
// outputs "Hello after 1 second" to the console
setTimeout(function () {
  console.log('Hello after 1 second');
}, 1000);
```

### setInterval()

The [setInterval()](https://nodejs.org/docs/latest/api/timers.html#setintervalcallback-delay-args) function will execute a piece of code (function) after a certain delay and continue to call it repeatedly. It accepts 3 parameters (below) and returns a <a href="https://nodejs.org/docs/latest/api/timers.html#timeout" target="_blank">timeout</a> object

<ul>
<li><strong>callback</strong> Function: The function to call when the timer elapses.</li>
<li><strong>delay</strong> number: The number of milliseconds to wait before calling the callback</li>
<li><strong>[, …arg]</strong> Optional arguments to pass when the callback is called.</li>
</ul>

**Note:** Unless you want the interval to continue forever, you need to call <a href="https://nodejs.org/docs/latest/api/timers.html#clearintervaltimeout" target="_blank">clearInterval()</a> with the timeout object as a parameter to halt the interval

For example:

```js
let count = 1; // global counter
let maxCount = 5; // global maximum

let myCountInterval = setInterval(function () {
  console.log('Hello after ' + count++ + ' second(s)');
  checkMaximum();
}, 1000);

let checkMaximum = function () {
  if (count > maxCount) {
    clearInterval(myCountInterval);
  }
};
```

### URL

The [URL](https://nodejs.org/docs/latest/api/url.html) class is used to create a new URL object by parsing the full URL string, ie:

```js
let myURL = new URL('https://myProductInventory.com/products?sort=asc&onSale=true');
```

Once we have a new URL object, we can access / modify aspects of it via their associated properties:

```js
console.log(myURL);

/*
URL {
  href: 'https://myproductinventory.com/products?sort=asc&onSale=true',
  origin: 'https://myproductinventory.com',
  protocol: 'https:',
  username: '',
  password: '',
  host: 'myproductinventory.com',
  hostname: 'myproductinventory.com',
  port: '',
  pathname: '/products',
  search: '?sort=asc&onSale=true',
  searchParams: URLSearchParams { 'sort' => 'asc', 'onSale' => 'true' },
  hash: ''
*/
```

To access the parsed query parameters (ie the "search" property), we can use a ["for...of"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) loop to iterate over key-value pairs the "searchParams": property:

```js
for (const [key, value] of myURL.searchParams) {
  console.log('key: ' + key + ' value: ' + value);
}

/*
key: sort value: asc
key: onSale value: true
*/
```

### Error

The [Error object](https://nodejs.org/docs/latest/api/errors.html#class-error) is used to represent an error ("exception") that occurs during the execution of our code. It provides a way to capture and handle the exception with useful information such as the error message and the stack trace.

**Handling Errors**

Consider the following example that generates the runtime error: `TypeError: Assignment to constant variable.`:

```js
const PI = 3.14159;

console.log('trying to change PI!');

PI = 99;

console.log('Haha! PI is now: ' + PI);
```

Here, we are trying to change the value of a constant: PI. If we try to run this short program in Node.js, the program will crash before we get a chance to see the string "Haha! PI is now: 99", or even "Haha! PI is now: 3.14159". There is no elegant recovery and we do not exit the program gracefully.

Fortunately, before our program crashes in such a way, Node.js will "throw" an ["Error"](https://nodejs.org/docs/latest/api/errors.html#class-error) object that we can intercept using the ["try...catch"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) statement:

```js
const PI = 3.14159;

console.log('trying to change PI!');

try {
  PI = 99;
} catch (ex) {
  console.log('uh oh, an error occurred: ' + ex.message);
  // outputs: uh oh, an error occurred: Assignment to constant variable.
}

console.log('Alas, it cannot be done, PI remains: ' + PI);
```

By utilizing properties such as [Error.message](https://nodejs.org/docs/latest/api/errors.html#errormessage) & [Error.stack](https://nodejs.org/docs/latest/api/errors.html#errorstack), we can gain further insight to exactly what went wrong and we can either refactor our code to remedy the error, or acknowledge that the error will happen and handle it gracefully.

**"Throwing" custom Errors**

We can also "throw" our own error using the ["throw"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw) keyword with a new instance of the "Error" class, for example:

```js
function divide(x, y) {
  if (y == 0) {
    throw new Error('Division by Zero!');
  }
  return x / y;
}

let a = 3,
  b = 0,
  c;

try {
  c = divide(a, b);
} catch (ex) {
  console.log(`uh oh, an error occurred: ${ex.message}`);
  // outputs: uh oh, an error occurred: Division by Zero!
  c = NaN;
}

console.log(`${a} / ${b} = ${c}`); // 3 / 0 = NaN
```
