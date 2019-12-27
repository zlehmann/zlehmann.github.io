---
layout: post
title:      "What Makes SQLite, Well...Lite?"
date:       2019-12-27 17:44:18 +0000
permalink:  what_makes_sqlite_well_lite
---


Anyone who works in web development has heard of SQLite. If you haven't, go spend some time with Google and acquaint yourself! SQLite sometimes isn't thought of as a "professional" database solution. Based on the DB-Engines.com 2019 records, you might see why. It lags well behind the big-3, Oracle, MySQL, and Microsoft SQL. It's also a healthy distance behind the up and comers Mongo and Postgres. There is a reason it's not up there in the upper tier of relational databases; it doesn't require a server to run. 

But this is what makes SQLite so attractive to recreational coders, or people that are trying to spin up projects quickly and might not want to necessarily manage an entire server just for the backend. Especially for students looking to get a project up and running quickly, SQLite is a great way to get all the features of a Relational database, with a lot less setup.

SQLite is self-contained which means it requires minimal support from the operating system, setup files, or external libraries. Because of this it doesn't need any configuration or hours of throwing bash commands at a terminal to set it up  and make sure that its working properly. But even with all of this "lite-ness" it doesn't sacrifice its ACID compliance standing. 

So what's the catch? Well, there's a big one. SQLite does not have any form of user management. Any user can read or write to the database without any permissions being granted. So while it may be a great way to spin up small projects, I would shy away from storing anything too important in them!
