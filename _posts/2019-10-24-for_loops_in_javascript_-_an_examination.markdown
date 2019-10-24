---
layout: post
title:      "For Loops in Javascript - An Examination"
date:       2019-10-24 12:19:36 +0000
permalink:  for_loops_in_javascript_-_an_examination
---


Loops are really, to me, the crux of what makes programming so powerful. It allows us to perform tasks on enormous data sets easily enabling us to process vast amounts of data without breaking a sweat. Therefore it is important to understand how this crucial piece of technology works. For me, the best way to learn something is by doing; so let's look at some examples.

Assuming we understand the basics of a "raw" for loop (where you initialize a counter and increment it manually), the for-in loop is a nice clean way of iterating through something when you need to perform an operation on each element. 
``` 
for (thing in iterable) {
    console.log(thing)
		}
```
Interestingly it might not work on arrays the way you think they would. Trying the above code on an array will actually print out the index values for each element in the array, not the value themselves.
```
const array = [1, 2, 3, 4, 5]

for (element in array) {
    console.log(element)
}
>0
>1
>2
>3
>4
```
If you want to iterate through the array and get the values at each position, you need to use the for-of loop.
```
for (element of array) {
    console.log(element)
}
>1
>2
>3
>4
>5
```
Another little nuance to be aware of when using these loop constructs, is that when working with JavaScript objects ( obj = {1:23, 2:24, 3:38, 4:85}), these loops above would return the key values.
```
for (thing in obj) {
    console.log(thing)
 }
 >1
 >2
 >3
 >4
 ```
 In order to examine the values of the properties you need to change your console log slightly.
```
for (thing in obj) {
    console.log(obj[thing])
}
>23
>24
>38
>85
```

