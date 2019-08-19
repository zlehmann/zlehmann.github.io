---
layout: post
title:      "Callbacks - A quick reference to cut through confusion"
date:       2019-08-19 15:57:27 +0000
permalink:  callbacks_-_a_quick_reference_to_cut_through_confusion
---


Don't panic, it's actually not as scary as you think.

Callbacks confused the heck out of me for a long time. I think just the syntax for writing something like that makes my brain hurt for some reason. But after a little practice you actually can think of it in a pretty linear way, even though they don't necessarily feel that way. 

In essence a callback is just a function that is passed to another function and invoked. It's nothing special in and of itself, but it allows you do something very important. When working in an event-driven environmental like JavaScript, you need a way to run code after another event has finished. Note I said finished there and not run. There's a big difference. Consider making calls to an API for some data. That request isn't resolved immediately, it takes time, and that time can vary depending on the distance the call is coming from the server, the data size, server hardware, and a host of other variables. 

Callbacks allow you to structure your code so that the methods you want to run on the returned data in the example above only fire after the data is finished being recieved. A classic callback example in JavaScript looks like this:

```
function doHomework(subject, callback) {
  alert(`Starting my ${subject} homework.`);
  callback();
}
function alertFinished(){
  alert('Finished my homework');
}
doHomework('math', alertFinished);
```
Passing in the callback function in doHomework allows you to invoke the alertFinished method after the homework is started. The reason is due to the event stack handler, but that's not as important to understand. The important thing here is what it allows you to do!
