---
layout: post
title:      "Why Would We Want Different Data Structures in the Back-End and Front-End?"
date:       2019-12-10 21:21:43 +0000
permalink:  why_would_we_want_different_data_structures_in_the_back-end_and_front-end
---


Computer science is a fascinating subject, and every article I read on it seems to take me a hundred steps further down the rabbit hole. I just read this article on [database and "live" programming data types](https://www.evanjones.ca/ordered-vs-unordered-indexes.html) by Evan Jones that, I have to be honest, didn't really *pull* me in with the title; but it didn't take long before I was open-mouthed reading in a frenzy. 

So before you start reading that article let's talk a little about the subject of data-types in this context and get an idea for what we're getting into. 

In essence the article is comparing data-types typically used to store data in databases (persisted on disk) versus data-types used "in-memory" (RAM). The former are the data-types that the backend database like SQLite, Postgres, or Mongo us, the latter is what you would use say in your React state. They both do similar things but in slightly different ways. They are both "storing" data for your app to us. Persisted data is typically used when talking about things you're writing to a disk, things your app might need forever even between sessions. In-memory data storage is things that you need in the immediate future, like the state of certain UI components etc. 

Jones says that hash tables and similar data-types are super common for in-memory storage, while databases are almost always an ordered index like a binary tree. If you want to know more about those two data structures I suggest spending some time on google, there is a lot of literature out on data types and their[ respective pros and cons](https://www.geeksforgeeks.org/advantages-of-bst-over-hash-table/) out there. The short version is that hash tables allow you to access single records very quickly while binary trees are better at returning a range of values. So if you query a data structure with something like "find me record #3487," the hash table will be faster. But if you query for something like "find me records #3487 through #5780," the binary tree is faster. There are of course edge cases with both of these situations...nothing is ever easy in CS.

So why did databases "evolve" to use binary trees over hash tables? Well its a question of versatility more than anything. I'm hard pressed to think of an app that would only ever need to access single records to perform a meaningful service to a user. The bottom line is that while you might take a small performance hit making single requests (which might not be likely in the first place), you win out whenever you start making "larger" queries or more complex queries. So it really boils down to a question of economics. Although after reading all of this, the next tunnel I go down might being researching if there are "hash map" databases that are optimized for single record lookups and when that might be more appropriate!
