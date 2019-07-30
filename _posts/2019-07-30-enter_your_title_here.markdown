---
layout: post
title:      "Big O - A shortcut to the good stuff"
date:       2019-07-30 12:27:28 -0400
permalink:  enter_your_title_here
---


A major topic that you don't seem to hear much about during your time in coding bootcamp seems to be EVERYWHERE the moment you start talking to technical recruiters. The Big O. What the heck is it, and what do you need to know about it when you're looking for your first dev job?

In a simplified technical sense Big O is a way of measuring how efficient your code is. It has become the way developers talk about size and speed of code so that possible solutions to a problem can be compared against each other in a meaningful way. Using Big O devs can have conversations like "Algorithm X is more efficient than Y, at least most of the time."

It's important to understand that when you are discussing the efficiency of an algorithm, you are discussing how that algorithm performs on a wide range of inputs. For example if your algorithm is searching an array for a specific value, the efficiency of method X might be very good for short arrays, but terrible for larger arrays. It's because of this variable input that Big O notation is often a discussion about the worst case scenario, usually the scenario with big datasets being received. Writing an algorithm so find an element in an array that works lightning fast on arrays with a length of only 10 is great, but not particularly practical unless you know you will get short arrays as your input all of the time.

There are a few "categories" of Big O that algorithims generally fall into that you should really know when talking to technical recruiters. Big O is a lot more complex that what I'll outline here, but as someone how has had very little exposure to the concept this is a good starting point. 

![](https://www.geeksforgeeks.org/wp-content/uploads/mypic.png)
The lines illustrated above are your guide posts for how to talk about Big O. Algorithims will typically be one of these lines, or very close to it, and it is this chart you want to keep in the back of your mind for deciding how to write your code. But how do I know which line my algorithim belongs to?

Different operations in your code have different time and space attributes. Setting a value to a variable for example is a constant time operation. You are setting a piece of physical memory to a value. In Big O notation this is an O(1) operation, or a constant complexity. It is about as fast an operation the computer can perform. Now consider iterating through an array. Even if you do nothing with the values you iterate through, the number of times the computer is looking at that array is dependent on the size of the array. The size of an array (or any input really) is represented by n. So in the iteration example the Big O notation would be O(n), or linear complexity.

So what happens if we add a comparison into our iteration loop? Let's make it easy and see if the value in the array is equal to another specific value, for instance checking to see if an element in the array is equal to 5. You might expect this new looping operation to be worse than just iterating over each element and doing nothing with it. Technically you would be right, the new loop would be O(n +1), and that's bigger than O(n) so it's less efficient! But in Big O notation you are often looking at the efficiency of these operations in respect to infinity. Most developers would ignore the constant of 1 and say the two loops are equal because O(infinity) and O(infinity +1) are functionaly equivalent.

What happens when you nest a loop inside another loop? Well we know if we iterate through a loop once, our Big O is O(n). If we add a loop inside the first loop we would get O(n^2), or a quadratic complexity. There are plenty of other common forms we see in programming that have O notation shortcuts, these are only a few. More importantly is knowing how to piece them together. If you have two loops one after another you would add the n together O(n) + O(n) rather than multiple them.

Hopefully that helps! 


