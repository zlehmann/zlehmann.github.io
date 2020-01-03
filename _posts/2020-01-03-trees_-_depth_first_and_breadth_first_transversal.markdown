---
layout: post
title:      "Trees - Depth First and Breadth First Transversal"
date:       2020-01-03 14:58:30 +0000
permalink:  trees_-_depth_first_and_breadth_first_transversal
---


I have a particularly warm spot in my heart for tree data structures since I'm actually a certified arborist and spent most of my working life working with trees. There was a brief moment where I hated them though, it was right about the time of my second or third tech interview; the second time I had a coding challenge question asking me to use recursion to solve a tree problem. I had never seen this data structure before and has aboslutely zero idea how to approach solving it. 

Like most things with code, they really aren't as big and scary as they first seem. I have found a lot of subjects in tech are sort of impossible to figure out on your own without some guidance. But once said guidance has been found, you realize it's not that it's really that complicated, it's just not obvious how to approach it unless you've been exposed to it before. So what is a tree? It's a data structure that can make searching for particular values very fast. They can be thought of like this [image](https://www.google.com/url?sa=i&source=images&cd=&ved=2ahUKEwiMlaGN1OfmAhWZXc0KHaU2CT0QjRx6BAgBEAQ&url=https%3A%2F%2Fwww.geeksforgeeks.org%2Fbinary-search-tree-set-1-search-and-insertion%2F&psig=AOvVaw1SzTQWCPs-JDqf8f2PSFJO&ust=1578148654259950).

The coding challenges I first saw these on were little more than a few sentences of instructions and this kind of illustration. Not much to go on if you've never used trees before in your life. But like I said before, once you've been shown the way to think about these it's not so bad. When dealing with trees there are really two approaches to solving most problems that you'll hear about over and over. Breadth-first and width-first transversal. Transversing a tree is just the way we search for things. The transversing is the hard part. After that you usually just need to add the conditional statements to "find" what you're looking for and do whatever work needs doing.

So what is the difference between these two transversal methods. Perhaps unsurprisingly breadth first looks at each level of a tree before moving on to the next, whereas depth first will search down each arm of the tree before moving on to the next. What may be surprising is that there isn't much time or space complexity difference between to two methods. Except when the tree has other rules applied to it. A binary sorted tree for example will mean every value to the left of a node is less than every value above it. This kind of a system can make searching for specific values very fast as the recursive calls can be effectively cut in half on a depth-first method. 

There is a great [StackOverflow post](https://stackoverflow.com/questions/687731/breadth-first-vs-depth-first) that goes into more details on how to actually perform these searches with pseudo-code, but the good bit can be found copied below:
```
Store the root node in Container
While (there are nodes in Container)
   N = Get the "next" node from Container
   Store all the children of N in Container
   Do some work on N
```
