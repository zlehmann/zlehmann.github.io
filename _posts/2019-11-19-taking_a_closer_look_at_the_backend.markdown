---
layout: post
title:      "Taking a Closer Look at the Backend"
date:       2019-11-19 14:20:24 +0000
permalink:  taking_a_closer_look_at_the_backend
---


There's a 'dumps like a truck' joke somewhere in here but I'm too sleep-deprived to follow through on it.

Databases are literally everywhere. Every app on the web uses them to some extent. One thing I've noticed as I continue my search for my first dev job, is how little developers seem to talk about them. I think the major reason for this is that which database is used for a project, is decided very early in the process. Since it is often an enormous undertaking to change the database in the backend, I think a lot of developers just play with the deck they are given. No sense talking about the differences between solutions if you can't change it anyway.

But why are there so many databases to choose from, and what makes them different? That's something I've always wanted to know so let's take a little time and explore them a little!

# Relational vs. Non-Relational
Relational databases are basically the old-school. Developed in the 70's these database types are the classics you see in a lot of projects. MySQL, Postgres, and Oracle are the big names. They all basically use the same setup, with a bunch of tables with unique row and column names that allow you to find and manipulate your data records. The relations come from how the tables are connected, through the use of join tables; everyone's favorite subject in bootcamp!

Non-relational databases are the new kids on the block (dating myself?). They do away with the strict schema typing that relational databases depend on, often using key-value pairings to perform the lookups for data. These types of systems are usually easier to implement, but don't allow for the strict data typing that may help eliminate "bad data" from propogating through your system. Non-relational databases allow you to work with unstructured or semi-structured data much more easily. Popular non-relational database systems in use today include MongoDB, Redis, and Cassandra.

# So Which System Should I Use?
Well, as with all things tech related, the answer is, it depends. Systems like MySQL and POSTgres have been long standing industry standards, but were built a long time ago and haven't necessarily adapated to new technologies that improve lookup performance or storage. Newer systems like Mongo are much better, but don't necessarily provide the rigid structure that SQL based systems use. I think overall you will continue to see a lot of apps choosing non-relational systems in the future, especially as big data gets even bigger and the types and volume of data needed for projects increases. For more information check out this blog over at [Alooma](https://www.alooma.com/blog/types-of-modern-databases).


