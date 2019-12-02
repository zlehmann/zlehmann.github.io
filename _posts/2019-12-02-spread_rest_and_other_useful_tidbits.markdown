---
layout: post
title:      "Spread ... Rest ... And Other Useful Tidbits"
date:       2019-12-02 19:22:15 +0000
permalink:  spread_rest_and_other_useful_tidbits
---


The spread operator (...) was introduced to JavaScript in ES6 and is a pretty handy little addition. Here's the official description from MDN:
> Spread syntax allows an iterable such as an array expression or string to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected, or an object expression to be expanded in places where zero or more key-value pairs (for object literals) are expected.
> 

There are two parts to his magical little tool though. First we'll look at the Rest part, which is really a parameter. Rest allows us to kind of chop up something to make it more usable. It is super handy when dealing with objects or parameter lists!

```
const dog = {
  name: "Bella",
  breed: "Golden Doodle",
  favFood: "Turkey"
};

const { name, ...restDog } = dog;

console.log(name); // "Bella"
console.log(restDog); // { breed: "Golden Doodle", favFood: "Turkey" }
```
You can think of it like as saying, here is a few key parameters I'm interested in, and then the rest of them you can group up together. 
```
function func(a, b, ...rest) { etc.}

//func's parameters are a, b, and a [list of all the remaining parameters]
```
This can be super useful if you're not exactly sure what your incoming object is going to look like, but you know there are a few important bits you need to get from it. 

Spreading is sort of the reverse of this. Instead of separating things into groups, you are spreading one into the other. The naming is a little odd, but its a way of combining things. 
```
const dwarvesWithoutBofur = ["Dwalin", "Balin", "kili", Fili", "Dori", "Nori", "Ori", "Oin", "Gloin", "Bifur", "Bombur", "Thorin"];

const wholeParty = ["Bofur", ...dwarvesWithoutBofur];
//all 13 of Tolkien's dwarves
```

You can also use the spread operator to add properties to an object without changing any of the other properties. Anyone using React is probably aware of how helpful that is!
