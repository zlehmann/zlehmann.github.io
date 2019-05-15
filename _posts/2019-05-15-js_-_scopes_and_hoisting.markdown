---
layout: post
title:      "JS - Scopes and Hoisting"
date:       2019-05-15 20:44:39 +0000
permalink:  js_-_scopes_and_hoisting
---


If you've found this article, you've probably done a little coding in JavaScript already. You've probably coded a bit in other languages too. I bet you've even heard of scoping and maybe hoisting before and are thinking to yourself that you don't need to spend anymore time focusing on this. It's basic, I got it, no problem...

Well that's what I thought too until my latest code review. I got asked some point blank questions on how this works in JS and I was stumped. While I understood the vague nuances of the different variable declaration methods and how the compiling phase of excution worked; it was painfully obvious that I didn't understand the specific mechanics well. Maybe not even at all...

And so I took it upon myself (was assigned) to go on a little journey into the documentation and reaquaint myself with how this all works in JS and write up this summary as a way of ingraining the knowledge into my being, and maybe be able to share it with others who found themselves in a similar situation. 

# Declaration vs. Assignment
Alright, let's start at the beginning. This part is pretty easy, but it affects each process that comes after it and becomes surprisingly important! Declaration is how we "set up" variables and functions. It's our way of telling JS that we want to have a variable with a specific name:
```
var var_variable;
let let_variable;
const const_variable;
```
Assignment is where we, not surprisingly, assign a value to a declared location:
```
var_variable = "This is a var";
let_variable = "This is a let";
const_variable = "This is a const";
```
JS allows us to combine these lines into a streamlined fashion like this:
```
var var_variable = "This is a var";
```
But this isn't exactly how the compiler sees things as we'll get into later. 

# Scope
How does this affect scope? Well certain parts of your code can only "read" values associated with variables or functions that are within certain scopes. Global scope can be read by any line of code you write, hence the name. But what happens if you declare a value inside a block?
```
function some_func() {
  let variable = "something cool";
	const secret = "you don't know about";
}
```

If you try to read the value of either variable outside of that function, you'll get an error that it is undefined. This happens because the let and const variable types are block scoped; meaning their scope is confined to the block they are declared in. Var type variables are not block scoped and can be accessed outside their declaration block...which leads to some confusing errors a lot of times. It gets tricky when you start nesting functions within one another. Just remember the inner functions always have access to the outer functions, but not vice versa.  

So what happens if you try to re-declare a variable from different scopes?
```
const test = 10;

function myFunc() {
  const test = 20;
	return test;
}

myFunc();
```
What do you get back? Well it's interesting. JS assigns values to two separate var instances in memory. One in a global scope and one in the block scope for myFunc. myFunc has access to both the global version and the block scoped version of var, so which does it choose to return? Well it finds the value inside the block first when it is invoked and returns 20, but if we ask for just the value of test, we get 10!

# Hoisting
So what the heck is hoisting? Hoisting is JS's way of dealing with declarations. In essence JS evaluates every line of code twice, once in a compilation phase and once in an execution phase. In the execution phase, if a variable name is encountered that does not have a declaration before it, JS will "hoist" the declaration it did find in the compliation phase. This allows code like:
```
myFunc();

function myFunc() {
  //tons of lines of code...
}
```
to evaluate correctly. Because JS actually reads the function declaration in before we call it at line 1. Why then, does:
```
function myFunc() {
  console.log(hello);
	
	var hello = "World!";
 }
 
 myFunc();
```
return undefined?

It returns undefined because JS doesn't hoist everything. Specifically it does not hoist assignments. JS reads the function above more like this:
```
function myFunc() {
  var hello;
	console.log(hello);
	hello = "World!";
}
```

In order to get the value out of the hello variable, you will need to invoke its value after the assignment. Otherwise the JS mystery hoisters could ruin your day!
