---
layout: post
title:      "First Class Functions"
date:       2019-08-17 14:17:38 +0000
permalink:  first_class_functions
---


If you've looked up any "top 10 javascript technical interview questions" article on the web, you've probably heard them talk about first class functions at some point. First class functions are a prerequisite for functional programming languages like javascript. All it really means is that you can pass functions as arguments to other functions:
```
function funcA () {
   console.log("I'm inside function A!")
	 }
	 
function funcB(foo) {
   foo()
}

funcB();
>>> I'm inside function A!
>>> undefined
```
Another example of first class functions in javascript is the map function. This functions accepts a function and a list, and returns a list where each element has had the function applied to it. A function like map can only work if the programming language uses first class functions. It also helps facilitate metaprogramming. 

First class functions also allow languages like javascript to use closures. When we nest a function inside another function, we are allowing the inner function to have access to the scope of the outer. It can see all the parameters that the outer function was passed and so on. 

[Eric Normand has an awesome video discussing this topic and I highly recommend watching!](https://lispcast.com/what-are-first-class-functions/)



