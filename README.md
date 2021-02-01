# ca-promises

Review code here: https://github.com/SOliv1/ca-promises-js


### Introduction
In web development, asynchronous programming is notorious for being a challenging topic.
An asynchronous operation is one that allows the computer to “move on” to other tasks while waiting for the asynchronous operation to complete. Asynchronous programming means that time-consuming operations don’t have to bring everything else in our programs to a halt.
There are countless examples of asynchronicity in our everyday lives. Cleaning our house, for example, involves asynchronous operations such as a dishwasher washing our dishes or a washing machine washing our clothes. While we wait on the completion of those operations, we’re free to do other chores.
Similarly, web development makes use of asynchronous operations. Operations like making a network request or querying a database can be time-consuming, but JavaScript allows us to execute other tasks while awaiting their completion.
This lesson will teach you how modern JavaScript handles asynchronicity using the Promise object, introduced with ES6. Let’s get started!
### JAVASCRIPT PROMISES
#### What is a Promise?
Promises are objects that represent the eventual outcome of an asynchronous operation. A Promise object can be in one of three states:

Pending: The initial state— the operation has not completed yet.
Fulfilled: The operation has completed successfully and the promise now has a resolved value. For example, a request’s promise might resolve with a JSON object as its value.
Rejected: The operation has failed and the promise has a reason for the failure. This reason is usually an Error of some kind.
We refer to a promise as settled if it is no longer pending— it is either fulfilled or rejected. Let’s think of a dishwasher as having the states of a promise:

Pending: The dishwasher is running but has not completed the washing cycle.
Fulfilled: The dishwasher has completed the washing cycle and is full of clean dishes.
Rejected: The dishwasher encountered a problem (it didn’t receive soap!) and returns unclean dishes.
If our dishwashing promise is fulfilled, we’ll be able to perform related tasks, such as unloading the clean dishes from the dishwasher. If it’s rejected, we can take alternate steps, such as running it again with soap or washing the dishes by hand.

All promises eventually settle, enabling us to write logic for what to do if the promise fulfills or if it rejects.

##### Cheatsheat reveiw: https://www.codecademy.com/learn/introduction-to-javascript/modules/javascript-promises/cheatsheet

##### Chaining Multiple Promises
One common pattern we’ll see with asynchronous programming is multiple operations which depend on each other to execute or that must be executed in a certain order. We might make one request to a database and use the data returned to us to make another request and so on! Let’s illustrate this with another cleaning example, washing clothes:

We take our dirty clothes and put them in the washing machine. If the clothes are cleaned, then we’ll want to put them in the dryer. After the dryer runs, if the clothes are dry, then we can fold them and put them away.
This process of chaining promises together is called composition. Promises are designed with composition in mind! Here’s a simple promise chain in code:

firstPromiseFunction()
.then((firstResolveVal) => {
  return secondPromiseFunction(firstResolveVal);
})
.then((secondResolveVal) => 
  console.log(secondResolveVal);
});
Let’s break down what’s happening in the example:
We invoke a function firstPromiseFunction() which returns a promise.
We invoke .then() with an anonymous function as the success handler.
Inside the success handler we return a new promise— the result of invoking a second function, secondPromiseFunction() with the first promise’s resolved value.
Invoke a second .then() to handle the logic for the second promise settling.
Inside that .then(), we have a success handler which will log the second promise’s resolved value to the console.
In order for our chain to wohttps://gist.github.com/494218d15bfd0b13cacbf18c9188ea3ark properly, we had to return the promise secondPromiseFunction(firstResolveVal). This ensured that the return value of the first .then() was our second promise rather than the default return of a new promise with the same settled value as the initial.
Write promise chains!
#### cheatsheat:https://www.codecademy.com/learn/introduction-to-javascript/modules/javascript-promises/cheatsheet
provided code. We require in three functions: checkInventory(), processPayment(), 

view code:
https://gist.github.com/70dc1b57e133639a695b2ca108e05768https://gist.github.com/494218d15bfd0b13cacbf18c9188ea3a
https://gist.github.com/494218d15bfd0b13cacbf18c9188ea3a
