---
layout: post
title:      "Rails and Javascript Final Project"
date:       2019-05-10 17:24:48 +0000
permalink:  rails_and_javascript_final_project
---

Javascript has been a hard module for me. It really is a fundamentally different type of programming that what I had been exposed to in the past. This idea of passing whole functions to other functions to other functions still makes my head spin, but I think I'm finally starting to get the hang of it. Looking back on it now it doesn't seem so bad, which is kind of what this whole "learn to code" experience has been like. This constant cycle of feeling like you know nothing and never will, to getting the hang of it, to feeling like you can at least fake it reliably is a recurring theme of my time spent on the course material. 

I have to say as a whole, I really like *what* JS can do for my apps. But I really don't like *it* per say. Like I said before, as a language I have had a hard time adjusting to it. But the capability it gives you on a web page is pretty hard to beat. So I guess I'll just have to get over it. 

Learning Javascript has been a blessing in that it really forces you to spend more time thinking about the underlying mechanics of the web to implement properly. What does this link actually do? What request is it going to send? What is the structure of the data I am going to get back? All things I don't think I thought much about before. 

My biggest hurdle was figuring out how to get my JS code to run when I submitted my new Captains form. For whatever reason it would never run. I littered my JS file with console.log() calls to try and figure out why I wasn't seeing the div I wanted on the page. Turns out, the JS file wasn't ever part of the equation. For whatever reason when I clicked on the submit button, it would fire off to the Captains controller, completely skipping over my JS fuctions. I wonder still if maybe it has something to do with the turbolinks gem. Something we never really worked with but I noticed on some of my googling that others have had other strange issues with it when using forms. Either that or for some reason my form partial just wouldn't render the JS when I submitted it. No idea! I was able to get it working by throwing my JS code into a <script> tag instead. Not as graceful but at least it let me finish the project!

Hard to believe how far I've come with all of this. I almost sorta, kinda, feel like maybe I could make this all work out...
