---
layout: post
title:      "The Importance of Test Driven Development (TDD)"
date:       2019-11-14 14:44:08 +0000
permalink:  the_importance_of_test_driven_development_tdd
---


In the Flatiron program, we did every lab using the test driven development (TDD) methodology. I never really thought about it much, it made sense in a school room setting that something would be checking my work, the same way my math teachers in high-school checked my work. How else do you know if you're doing something write?

It wasn't until I finished at Flatiron that I really started seeing TDD around and hear it get talked about as a method of writing better code. For those of you not familiar with TDD, it is a method of code development where you writing out your tests first. Rather than writing tests to see if your function does what you want it to, you write a test that lays out what results and behaviors you expect to get back from the function first. Then you write your code to get the tests to pass. 

The differences might not be obvious to you at first, not at least, until you try to write code without tests. For me, not having that test framework to write against is harder in my opinion. It is too easy for me to get caught in a mental loop where I am considering a bunch of edge cases, or potential pain points in my code, that its hard for me to just write. I actually find it very benficial using TDD just as an exercise in organizing my thoughts before I write a single line of production code. 

Additionally TDD allows for a "living record" of sorts, detailing the progression of your code and what it is doing. The tests provide a reader with a history of what problems the code is trying to solve as it evolves over time, and offers insights into the edge cases that may have been encountered during its development. 

Even more importantly, it gives everyone in the development process some piece of mind that they haven't broken anything! If you know all the original tests were passing before you re-factored something, and they aren't anymore, you done likely screwed up. This holds the code to a higher standard and allows debugging to be more efficient. 

Honestly its hard to think of many reasons why you wouldn't want to develop in a TDD environment. The most likely answer to this would be time, but I can promise you, having the tests in place when working on difficult or complex problems will save you a ton of time re-factoring and bug hunting down the road. 
