---
layout: post
title:      "Pandas - Cute Fussy Eaters or Hardcore Data Structures?"
date:       2020-01-08 00:01:58 +0000
permalink:  pandas_-_cute_fussy_eaters_or_hardcore_data_structures
---


Both obviously!

Panel data is an econometrics (see already hardcore) term used to describe observations over multiple time periods for the same individuals. This is where pandas got their name. Pandas is a software library written for python that offers data structures for manipulating numerical tables and time series. All a really fancy way of saying data frames basically. 

If you've used R you probably are already pretty familiar with the data structures in pandas; data frames and series. Pandas allow a user to import data from various forms like csv, excel, and others. They also make working with tabular data a lot easier. They make joining, grouping, and merging super fast and easy. They also have some added nicities with how they handle null values that I've personally found very useful.

So how useful are they?

Let's say you have some tabular data containing dates, temperature, humidity, visibility, wind speed, and wind direction for some city. How would you find the maximum temperature of your data set? You might write something in python like this:

```
max_temp = 0
for row in data_set :
   if int(row['temp']) > max_temp:
	     max_temp = int(row['temp'])
print(max_temp)
```

Pretty straight forward. But what does this look like with pandas?

```
dataframe['temp'].max()
```
Well it is certainly shorter, all that much easier? Hard to say. But pandas gives you access to a LOT of functionality that do things like this for more complex operations. You can condense dozens of lines of code into a few snippets with pandas. It's easy to see why it has become so popular over the past decade!
