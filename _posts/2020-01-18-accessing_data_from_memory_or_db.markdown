---
layout: post
title:      "Accessing Data from Memory or DB?"
date:       2020-01-18 15:29:25 +0000
permalink:  accessing_data_from_memory_or_db
---


I came across an interesting, well I thought it was interesting, problem the last few days at work. I am building a web interface for a very large dataset. We have run into a handful of problems already with trying to find the most efficient way of accessing our data for the user. Most recently I was tasked with figuring out a way to slice a large data table based on a date range.

On the surface it isn't too difficult a question, but in application it actually got to be a pretty interesting little experiment. As a habit I first used code that existed. We had already written up a SQL query to fetch all the data we wanted within a specified time interval. So I just passed this into my interface function and booted up the server to see what happpened. But immediately there was a problem. The date inputs changed based on another user field drop down box. If I changed the drop down, the date field re-rendered (you can only pick a date relevant to the field you choose), which rerendered my UI objects. 

This in and of itself isn't really a problem, except that the query was responding really slow to the re-renders. I noticed that the query actually didn't slice the data based on the dates chosen. We were just feeding the whole data table into my UI. So I did the next logical thing to me. I did the slicing in my function on the front end. Well that "technically" worked, it was wayyyyy too slow to use for production.

So after some sitting there thinking, I decided to try moving the query into my function. This way the SQL only fired off after the parameters were set and the user clicked go. The performance increase was nuts! I guess letting the SQL backend do that slicing for me is a lot better than doing the slicing in memory on the front end. I still don't necessarily understand 'why' other than memory and the hard drive are two separate things. But I will definitly file this example away in the back of my mind as the preferred method from now on!
