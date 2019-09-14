---
layout: post
title:      "Recursion - A quick run through"
date:       2019-09-14 16:40:28 +0000
permalink:  recursion_-_a_quick_run_through
---


Recursion is the act of a function calling itself. The idea is very simple on paper, but I have found in practice, it can be extremely confusing.  Even something as straight forward as a factorial starts to make your head spin when you try to desribe what is happening every step of the way. 
```
function factorial(x) {
  if (x < 0) return;
  if (x === 0) return 1;
  return x * factorial(x - 1);
}
```
The thing I find really interesting about recursive functions is how they work under the hood. You can look at this and recognize the pattern and decipher what the function is trying to do, but that won't get you very far if you have to debug a more complex recursive fuction. 

In the case above the function is in essence winding down from x to where x === 0. It would be something like this:
```
factorial(3);
>>
factorial(3) returns 3 * factorial(2)
factorial(2) returns 2 * factorial(1)
factorial(1) returns 1 * factorial(0)
factorial(0) returns 1
```
That pattern makes sense to us, its pretty easy to follow. But remembering that the stack is going to cause these calls to return in the reverse order is the important part.

```
factorial(0) returns 1                 => 1
factorial(1) returns 1 * factorial(0)  => 1 * 1
factorial(2) returns 2 * factorial(1)  => 2 * 1 * 1
factorial(3) returns 3 * factorial(2)  => 3 * 2 * 1 * 1
 // 6
```

This sort of 'unwinding' of the returns becomes really apparent when you start working with arrays, lists, or strings and can be a great way to reverse the order of things quickly.  
