---
id: conditional-statements
title: Conditional Statements
sidebar_position: 1
description: Conditional Statements
---

# Conditional Statements

Conditional statements in JavaScript allow programs to make decisions based on various conditions. These conditions can be evaluated to either true or false, and depending on the outcome, different blocks of code are executed.

## Basic Syntax

The most fundamental conditional statement in JavaScript is the if statement. It checks a condition and executes a block of code if the condition is true. The syntax for an if statement is as follows:

```
if (condition) {
    // code to execute if condition is true
}
```

### Example: Checking Balance

Consider a scenario where you want to check if a user has enough balance to purchase an item. Here's how you could implement this using an `if` statement:

```js
// Set balance and price of item
let balance = 500;
let itemPrice = 100;

// Check if there are enough funds to purchase item
if (itemPrice <= balance) {
  console.log('You have enough money to purchase the item!');
} else {
  console.log('You do not have enough money in your account to purchase this item.');
}
```

In this example, the `if` statement checks if the price of the item is less than or equal to the user's balance. If the condition is true, it logs a success message; otherwise, it logs a failure message.

### Else Statement

The else statement allows you to specify alternative code to run if the condition in the if statement is false. The syntax combines if and else as follows:

```
if (condition) {
    // code to execute if condition is true
} else {
    // code to execute if condition is false
}
```

### Else If Statement

The else if statement in JavaScript allows you to check multiple conditions sequentially. It is used after an if statement and before an optional else statement. The else if statement checks whether a new condition is true. If it is, the code block associated with that condition is executed. If none of the conditions are true, the code block under the else statement (if present) is executed.

**Basic Syntax**

The basic syntax for using else if is as follows:

```
if (condition1) {
    // code to execute if condition1 is true
} else if (condition2) {
    // code to execute if condition1 is false and condition2 is true
} else {
    // code to execute if both condition1 and condition2 are false
}
```

#### Example: Checking User Age

Let's say you're building a website that displays content based on the user's age. Here's how you might use if, else if, and else to tailor the experience:

```js
let userAge = 25;

if (userAge >= 18 && userAge < 30) {
  console.log("Welcome You're eligible for our special offer.");
} else if (userAge >= 30 && userAge < 40) {
  console.log('Hello Enjoy exploring our products.');
} else {
  console.log('Welcome We hope you enjoy browsing our site.');
}
```

In this example:

- If the user is between 18 and 29 years old, they receive a special welcome message.

- If the user is between 30 and 39 years old, they get a general welcome message.

- If the user is younger than 18 or older than 39, they receive a generic welcome message.

**Important Notes**

- There is no elseif syntax in JavaScript. Always use else if.

- Conditions are checked in order. Once a condition is found to be true, the corresponding block of code is executed, and the rest of the conditions are ignored.

- An else statement is optional and serves as a fallback if none of the if or else if conditions are met.

By using if, else if, and else, you can create complex logic flows in your JavaScript applications, enabling them to respond dynamically to various conditions.

### Ternary Operator

For simple conditions with two outcomes, the ternary operator provides a concise way to write conditional expressions. Its syntax is:

```
condition? expressionTrue : expressionFalse;
```

Here's how you could rewrite the balance check using a ternary operator:

```js
const message =
  itemPrice <= balance
    ? 'You have enough money to purchase the item!'
    : 'You do not have enough money in your account to purchase this item.';
console.log(message);
```

This single line of code performs the same check as the previous example but uses the ternary operator for brevity.
