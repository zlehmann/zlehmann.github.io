---
layout: post
title:      "Sinatra Portfolio Project - Virtual Flybox"
date:       2019-01-01 22:41:53 +0000
permalink:  sinatra_portfolio_project_-_virtual_flybox
---


I am just wrapping up my Sinatra portfolio project. I decided to build a virtual flybox app. For those of you that are not fly fishermen or women, a flybox is what you keep your flies (think of as bait or lures) in. The app lets users create an account, create flyboxes, and create flies. I built in the ability for users to edit or remove flyboxes and flies as well. 

I learned a lot about databases working on this project. I have used relational databases a bit for work in the past but I've never had to set one up using code in this way before. I ran into trouble with the ActiveRecord nomenclature for the relationships. It still confuses me when to use the plural and singular when setting up the join tables. I had a problem with my app for a while where the flies and flyboxes didn't actually join together properly. It turned out I had originally called the join table flies_flyboxes when it should have been fly_flyboxes. I minor glitch but it took a long time to debug and work out the kinks. 

Other than that it was pretty straight forward. I tried to spice it up a little with some custom css just to get it looking halfway decent. The MVC layout is pretty familiar to me. I had worked with Django and Python on a few hobby projects years ago so I felt like that was relatively easy for me to get my head around. I really liked how the example app given to us in the project readme had helper functions right in the application controller. That was a really slick addition that I would not have thought to look for myself. 
