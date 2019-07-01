---
layout: post
title:      "Fetch My Corgi - React Final Project"
date:       2019-07-01 14:15:23 +0000
permalink:  fetch_my_corgi_-_react_final_project
---


I can't believe this is my final project of bootcamp! I can't decide if it feels like it all went by in a blur or if it felt like it lasted a lifetime. But here we are with my final project submission! 

For my react final project I wanted to build an app that could help me and my partner find a corgi to adopt. Being super popular, they don't stay in a shelter for long before being scooped up. We have been trying to adopt a corgi for the last two years and are still coming up empty. Competition is fierce, so I decided to build an app that would parse the Petfinder API and show us all of the corgis within a hundred miles of our home so we can find our future pup faster!

I used a ruby on rails backend to build this app. Upon initialization the app sends a request to the Petfinder API for the most recent 100 corgi posts within 100 miles of Brooklyn, NY. It then iterates through the response and creates a Dog object in my database for each dog returned in the response. The same thing also happens on initialization for shelters. The rails server hosts my API that the react frontend calls for data to display. The rails server runs on port 3001, but the foreman package via NPM, the port is forwarded on 3000. I also namespaced the rails api so that it's route isn't confused somehow for anything on the react side of things (i.e. /api/dogs/243 rather than just dogs/243).

After cloning down the fetch-my-corgi repo, you can run the line below to start both the rails server and react server at once. 
```
foreman start -p 3000
```

This project was really fun to build. I felt like it pulled so much of the material that I have been learning over the past 9 months together. Finally! I have a much more solid grasp of how react works than when I started, although the redux side of things still confuses me now and again. I'm super happy with how this all came together. I can't wait to work on more projects and finally start to dive deeper into some of the concepts that I can still get to work, but don't fully understand all the nuts and bolts yet.
