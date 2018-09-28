---
layout: post
title:      "Enter your title here"
date:       2018-09-28 17:59:21 +0000
permalink:  enter_your_title_here
---


Anyone who's spent even a little bit of time trying to learn how to write code will have quickly run into the idea of looping. Looping is a fundamental concept in coding and one that is used, most likely, in every program ever written. Loops are used whenever we need to execute the same lines of code over and over again. Eventually the loop is "broken" and the flow of code moves on to the next lines as normal. Loops can be broken in a lot of different ways, either by reaching some kind of criteria, or by manually coding an exit for the loop in the loop itself. Since loops are so useful I put together a quick cheatsheet of the different ruby loop methods for quick reference. This reference only covers the basic syntax to help you remember how to use the looping method quickly in your lessons.

**Loop**
```
loop do
   puts "whever you want"
	 # you can use the "break" command to make this function more like a while loop
end
```

**While**
```
i = 1
while i >= 10
   puts "we're counting to ten!"
   i += 1
end
```

**Until**
```
i = 1
until i >= 10
   puts "here we go again"
	 i += 1
end
```

**For**
Don't use these! I don't full understand why, but you should basically avoid this method when possible. Use the each method instead to iterate over an enumerable. 

**.each**
I guess this is technically an iterator which is a little different than a loop, but its used SO often that I had to include it. Use this to basically loop through a collection of something and do things to every element inside that collection you encounter.
```
array = ["thing1", "thing2", thing3"...]
array.each { |thing| puts thing}
``` 
So clean! The block can be expanded like below:
```
array.each do |thing|
  we can put whatever we want in here!
end
