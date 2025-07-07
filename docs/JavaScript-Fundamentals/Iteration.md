---
id: iteration
title: Iteration
sidebar_position: 2
description: Iteration
---

# Iteration

Iteration is a fundamental concept in JavaScript, enabling developers to efficiently execute a block of code [multiple times](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code) based on specific conditions. Whether it's looping through arrays, traversing objects, or repeating actions until a certain criterion is met, iteration helps streamline processes and reduce redundancy in code.

JavaScript provides various iteration mechanisms, such as:

## For Loop

One of the most common iteration structures is the ["for"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) statement:

```
for (initialization; condition; afterthought)
  statement
```

For example:

```js
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

This code iterates through a sequence of numbers from 0 to 9, printing each number to the console. Here's a step-by-step explanation of how it works:

1. **Initialization (`let i = 0`)**: The loop starts by declaring a variable `i` and initializing it to 0. This variable acts as the loop counter, which keeps track of the current iteration.

2. **Condition (`i < 10`)**: Before each iteration of the loop, the condition `i < 10` is evaluated. If the condition is true, the loop body (the code inside the loop) is executed. If the condition is false, the loop stops executing.

3. **Iteration (`i++`)**: After the loop body is executed, the `i++` expression increments the value of `i` by 1. This is known as the iteration statement, which prepares for the next loop cycle.

4. **Loop Body (`console.log(i)`)**: Inside the loop, the `console.log(i)` statement is executed, printing the current value of `i` to the console.

Putting it all together, the loop starts with `i` equal to 0 and continues to execute the loop body (printing the value of `i`) and incrementing `i` by 1 on each iteration until `i` is no longer less than 10. The output will be the numbers 0 through 9, each on a new line.

Here's what happens in each iteration:

- **1st iteration**: `i` is 0, `console.log(i)` prints 0, `i` becomes 1.
- **2nd iteration**: `i` is 1, `console.log(i)` prints 1, `i` becomes 2.
- **3rd iteration**: `i` is 2, `console.log(i)` prints 2, `i` becomes 3.
- ...
- **10th iteration**: `i` is 9, `console.log(i)` prints 9, `i` becomes 10.

After the 10th iteration, `i` becomes 10, which makes the condition `i < 10` false, so the loop terminates.

## Do While Loop

Another form of iteration is the ["do...while"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while) statement:

```
do
  statement
while (condition);
```

For example:

```js
let i = 0;

do {
  console.log(i);
  i++;
} while (i < 10);
```

This code once again iterates through a sequence of numbers from 0 to 9, printing each number to the console. Here's a step-by-step explanation of how it works:

1. **Initialization (`let i = 0`)**: The loop starts by declaring a variable `i` and initializing it to 0. This variable acts as the loop counter, which keeps track of the current iteration.

2. **Loop Body (`console.log(i); i++`)**: Inside the `do` block, the `console.log(i)` statement is executed, printing the current value of `i` to the console. Then, the `i++` statement increments the value of `i` by 1.

3. **Condition (`i < 10`)**: After executing the loop body, the condition `i < 10` is evaluated. If the condition is true, the loop repeats and executes the body again. If the condition is false, the loop terminates.

Unlike a `for` loop, a `do...while` loop ensures that the loop body is executed at least once, even if the condition is false initially.

Putting it all together, the loop starts with `i` equal to 0 and continues to execute the loop body (printing the value of `i` and incrementing `i` by 1) until `i` is no longer less than 10. The output will be the numbers 0 through 9, each on a new line.

Here's what happens in each iteration:

- **1st iteration**: `i` is 0, `console.log(i)` prints 0, `i` becomes 1.
- **2nd iteration**: `i` is 1, `console.log(i)` prints 1, `i` becomes 2.
- **3rd iteration**: `i` is 2, `console.log(i)` prints 2, `i` becomes 3.
- ...
- **10th iteration**: `i` is 9, `console.log(i)` prints 9, `i` becomes 10.

After the 10th iteration, `i` becomes 10, which makes the condition `i < 10` false, so the loop terminates.

## While Loop

Finally, let's quickly discuss the ["while"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while) statement:

```
while (condition)
  statement
```

For example:

```js
let i = 0;

while (i < 10) {
  console.log(i);
  i++;
}
```

You will notice that this is very similar to the `do...while` loop, however the primary distinction lies in the condition check. In a `while` loop, the condition is evaluated before executing the block of code inside the loop. This means that if the condition evaluates to false at the start, the loop body will never execute. Conversely, a `do...while` loop guarantees that the loop body will execute at least once because the condition is checked after the execution of the loop body.
