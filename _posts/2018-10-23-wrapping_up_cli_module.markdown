---
layout: post
title:      "NYC Beer! My Object Oriented CLI Project."
date:       2018-10-23 15:50:35 -0400
permalink:  wrapping_up_cli_module
---


This past weekend I finished writing my CLI final project! It feels pretty amazing to be moving forward with the program and I already feel like I'm well past where I was as a programmer from when I started. Granted that isn't very far, but still I feel quite accomplished. I really enjoyed working on the object oriented lessons of this module. I never really worked with classes and objects before but finally feel like I'm getting the hang of it. 

It has also opened up the idea of abstraction and I can't stop reading about it. The art of abstracting complex real world situations is fascinating. How simply thinking about your code can influence how you build it. What is this object? what attributes does it have? How does this object interact with other objects? I find that planning process to be really interesting and fun to do.

So my final OO CLI project had to scrape data from a website to provide the user with information and allow them to make some selection from that data to get more information about what they selected. I decided that I would make an app that scraped data from the Beer Advocates website. The BA website has a list of all the breweries in New York City and each brewery has a list of beers that has been given ratings by BA users. I make my own beer at home so I thought this would be a great project to show off my love of brewing and my prowess as an object oriented programmer!

The app isn't super complicated. When it launches it presents a list of all of the breweries in NYC. It then prompts the user for an input representing one of the breweries. Once selected, the app will then display all of the beers from that brewery. The app is scraping data for multiple pages. The first scrapes the brewery list from the NYC page of the BA site. Then, each time the user picks a brewery, it is scraping that brewery's profile page for a list of all the beers they've created that has been rated by BA users. It also displays data about those beers including the alchol by percent volume, the style of the beer, how many ratings it has gotten from users, and what the average rating for that beer is. 

When the app scrapes this information it is creating an instance of a class associated with the data it is scraping. For instance each brewery is an instance of the Brewery class. Each beer is an instance of the Beer class. One of the instance variables for the Brewery class is an array of Beer instances containing all of the beers that specific brewery makes. 

I'm excited (and nervous!) to finally be done with this first project and see what the reviewers have to say!
