---
layout: post
title:      "Linked Lists vs. Arrays"
date:       2019-12-22 13:47:49 +0000
permalink:  linked_lists_vs_arrays
---


As I'm working through the coding interview algorithim class by Stephen Grinder on Udemy, we just finished working with linked lists. Up until then I had heard of them a few times but really had no idea what they were, how they worked, or why you would want to use them. It didn't really make sense to me to go through the trouble of creating this data structure when you already have things like arrays. So I did a little research, and this is what I found.

Let's start off with how they are similar. They are both linear methods for storing data. Well, that's about it really. Arrays typically store values of the same type, but linked lists allow you to store pretty much anything you want in the node. Arrays are indexed which allow you look up the value of an element quickly, linked lists you need to iterate your way through the list until you get to the node you're looking for. So why used linked lists at all if they're slower?

Well arrays are of a fixed size. If you overrun an array, another array is created and appended to the original. Linked lists are dynamic and can size according to the data being put into it. Inserting and deleting values from a linked list are also faster to perform on a linked list than arrays. Because linked lists have pointers to the next and sometimes previous nodes, the size of elements in a linked list are slightly larger.

So when should you use one over the over? As with everything in development it depends. If you need to be able to look up a specific value in the data, an array may be a better option as it will give you a much faster lookup time. If you are storing data in a way that you need to iterate through the data many times, linked lists may be faster; especially if you will be adding and deleting elements often.
