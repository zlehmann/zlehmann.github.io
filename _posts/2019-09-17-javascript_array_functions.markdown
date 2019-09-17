---
layout: post
title:      "JavaScript Array Functions"
date:       2019-09-17 22:42:19 +0000
permalink:  javascript_array_functions
---


There are three array functions that make working with lists in JS a lot easier:
* Map()
* Reduce()
* and Filter()

Let's review these and make sure we know how they work!

Map()
Map essentially runs a function that returns a value on each element in an array. Let's say for instance you want to return the price of every item in a car. You could use map to do something like this:
```
const prices = products.map(product => product.price);
```

Reduce()
This function is very similar to the Map function with one major difference. It will return the value from the callback function to the next element in the array. This lets you accumulate values (or reduce them) into a single value. 
```
var totalInventory = products.reduce(function (accumulator, product) {
  return accumulator + product.inventory;
}, 0);
```
The code above would initialize an accumulator value at 0, and then add the inventory value of each product to it giving you the total inventory for all the products.

Filter()
Filter, not surprisingly, returns a subset of elements from an array. Continuing with our running example:
```
let tshirts = products.filter(function(product) {
    return product.type === "t-shirt"
}
```

