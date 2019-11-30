---
layout: post
title:      "Better Understanding the Virtual DOM"
date:       2019-11-30 15:05:05 +0000
permalink:  better_understanding_the_virtual_dom
---


I guess we need to start at the DOM itself! The Document Object Model is an object-based representation of a HTML document. It is also the access point for manipulating the object. You can think of it like a json object structured in a similar way to this:
```
{
  header: 'some html tags for the header'
	body: 'the content of your page'
	  ul: 'some unordered list'
		  li: 'some list element'
	footer: 'html tags for your footer'
```
Obviously its usually more complex than this, but its still just a data object and can be changed like any other object. If you wanted to update part of this object you would make the appropriate query for that item (i.e. something like liItem = document.getElementById.....). As the web evolved, and more content updates were being made faster than ever, this method started to hit some walls. 

The virtual DOM, sometimes called the shadow DOM, is another object that further encapsulates the dom. This was created to solve the problem of frequently updating the DOM and did so in a more performant way. the virtual DOM can be thought of as a copy of the actual DOM that can be frequently and easily manipulated and updated without using clunky DOM APIs. Once something is updated, the original DOM can update only the specific elements that have changed, greatly increase the performance of the user experience. 

Using the virtual DOM without a framework can be a bit tedious though, which is way frameworks like react and vue are growing in popularity. But in essence, all  they do is make interfacing with the virtual DOM easier, which in turn makes interfacing with the actual DOM a LOT easier. 
