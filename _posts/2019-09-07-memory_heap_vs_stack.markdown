---
layout: post
title:      "Memory Heap vs. Stack"
date:       2019-09-07 14:24:14 +0000
permalink:  memory_heap_vs_stack
---


This subject is definitely a bit out of my comfort zone. As someone who is still working out all the intricacies of just building simple apps that work, having to think about how memory is being setup and used underneath my frameworks is a tall order. But I've read in a number of places that this is something I need to at least be aware of so here we are...

As far as Javascript goes, memory comes in two different forms. The Stack is where your local variable values in a function get stored. Heap is a larger more complex memory type that is dynamically changing values for you. Probably the most simplistic way of thinking about this would look something like:

* You declare and set the value of variable A = 24 inside a function --- Stack Memory
* You push the value of variable A into a global array --- Heap

The local stack is limited to approximately 1 MB of space. That's not a lot of room, but again, you are only storing primitive types of objects and they shouldn't be getting stored for too long. These are only values you need to use in the immeidate local environment. Everything else will be getting pushed up to Heap storage. This is typically where your functions, dates, arrays and other objects get stored.
