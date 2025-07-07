---
id: custom-objects
title: Custom Objects
sidebar_position: 2
description: Custom Objects
---

# Custom Objects

As we have seen from ou discussion on "Built in Objects", Javascript is "Object Oriented":

> "Object-oriented programming is about modeling a system as a collection of objects, where each object represents some particular aspect of the system. Objects contain both functions (or methods) and data. An object provides a public interface to other code that wants to use it but maintains its own private, internal state; other parts of the system don't have to care about what is going on inside the object."
>
> [https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_programming](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_programming)

## Object Literal Notation

The most simple and straight-forward way to create an object in JavaScript is to use "Object Literal Notation" (sometimes referred to as "object initializer" notation). The syntax for creating an object using this notation is as follows:

```javascript
let obj = {
  property_1: value_1,
  property_2: value_2,
  // ...,
  'property n': value_n,
}; // properties can also be defined as a string`
```

So, if we wanted to create an object with the following properties:

- **name** (string)
- **age** (number)
- **occupation** (string)

and methods...

- **setName** ("setter" to set a new value for the "name" property)
- **setAge** ("setter" to set a new value for the "age" property)
- **getName** ("getter" to get the current value of the "name" property)
- **getAge** ("getter" to get the current value of the "age" property)

using "Object Literal" notation, we would write the code:

```js
let architect = {
  name: 'Joe',
  age: 34,
  occupation: 'Architect',

  setName: function (newName) {
    this.name = newName;
  },

  setAge: function (newAge) {
    this.age = newAge;
  },

  getName: function () {
    return this.name;
  },

  getAge: function () {
    return this.age;
  },
};
```

and access the data (properties) and functions (methods) using the following code, ie:

```js
console.log(architect.name); // "Joe"
// or
console.log(architect.getName()); // "Joe"
```

We must use the **“this”** keyword whenever we refer to one of the properties of the object inside one of it’s methods. This is due to the fact that when a method is executed, "age" (for example) might already exist in the global scope, or within the scope of the function as a local variable. To be absolutely sure that we are referring to the correct "age" property of the current object, we must refer to the "execution context" - ie: the object that is actually making a call to this method. We know the object has an "age" property, so in order to be more specific about _which_ age variable that we want to change, we leverage the keyword **this**. "this" will refer to the "execution context", ie: the object that called the function! So, **"this.age"** can be read literally as **"the age property on this object"**, which is exactly the property that we wish to edit.

However, while "this" allows us to be specific with which **properties** that we refer to in our **methods**, it can lead to some confusing scenarios. For example, what if we added a new "outputNameDelay()" method to our architect object that writes the architect's name to the console after 1 second (1000 milliseconds):

```js
// ...
outputNameDelay: function(){
  setTimeout(function(){
    console.log(this.name);
  },1000);
}
// ...
architect.outputNameDelay(); // outputs undefined
```

Everything looks correct and we have made proper use of the "this", however because the setTimeout function is not executed as a method of our architect object, we end up with "undefined" as output to the console. There are a number of fixes for this issue, however the most common is by using an ["arrow function"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) as we have seen when first discussing JavaScript. The reason that this works is because Arrow functions use a "lexical" this (ie: the "this" value of the parent scope).

```javascript
// ...
outputNameDelay: function(){
    setTimeout(() => {
      console.log(this.name);
    },1000);
}
// ...
architect.outputNameDelay(); // outputs "Joe"
```

## The "class" keyword

If we wish to create multiple objects of the same "type" (ie: that have the same properties and methods, but with different values), we can leverage the "class" and "new" keywords, ie:

<!-- prettier-ignore-start -->
```javascript
class Architect {
  name;
  age;
  occupation = 'architect'; // default value of "architect" for occupation

  constructor(setName = '', setAge = 0) { // handle missing parameters with '' and 0
    this.name = setName;
    this.age = setAge;
  }

  setName(newName) {
    this.name = newName;
  }

  setAge(newAge) {
    this.age = newAge;
  }

  getName() {
    return this.name;
  }

  getAge() {
    return this.age;
  }
}

// define new "architect objects using the "new" keyword with the "architect" class

let architect1 = new Architect('Joe', 34);
let architect2 = new Architect('Mary', 49);

// samples of accessing properties and methods on both objects

console.log(architect1.name); // "Joe"

console.log(architect1.getName()); // "Joe"
console.log(architect2.getName()); // "Mary"
```
<!-- prettier-ignore-end -->

Here, we specify the properties (with default values), a "constructor" function to take initialization parameters, as well as specify all of the methods within the "class" block.

> **NOTE:** For more information / advanced topics on objects in JavaScript, such as: ["Private Methods / Properties"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Private_properties), "[Getters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) / [Setters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set)" and ["Inheritance"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends) see the documentation on [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes).
