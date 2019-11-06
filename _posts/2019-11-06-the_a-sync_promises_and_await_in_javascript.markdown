---
layout: post
title:      "The A-Sync, Promises, and Await in Javascript"
date:       2019-11-06 13:31:42 +0000
permalink:  the_a-sync_promises_and_await_in_javascript
---


In a similar fashion as a lot of my posts these days, this blog was inspired by an interview question that stumped me a bit. I have worked with promises obviously, anyone fetching data from a backend has done it, but the details about promises and the await method eluded me. So you, the lucky reader, get to travel with me while I once again sit down to debug my brain and figure out what piece of this puzzle I'm missing.

Let's start with asyncronous in general. We have a pretty good idea what this is about, but let's see what MDN says for the official definition:
> An asynchronous function is a function which operates asynchronously via the event loop, using an implicit Promise to return its result. But the syntax and structure of your code using async functions is much more like using standard synchronous functions.
> 
That is pretty much what we expected. a-sync functions allow us to start something, but not sit around and wait for the response. It allows the flow of our code and apps to continue while the request goes off to do its thing. In this definition we also see that Promises are used to return the result of these a-sync functions. Cool, 2 out of 3 things more or less cleared up. So what is this Await business all about?

Actually if we continue reading from the same definition we see the following:
> An async function can contain an await expression that pauses the execution of the async function and waits for the passed Promise's resolution, and then resumes the async function's execution and returns the resolved value. Remember, the await keyword is only valid inside async functions.
> 
Well wait a minute. Isn't the whole point of a promise that it allows us not to wait for the promise's resolution? In essence, yes. The async/await methodology basically allows someone to write an async function that behaves like synchronous functions. 

So why bother? Well there are some interesting advantages to using async/await to perform async functions. Most notably the code comes out much cleaner and easier to read, and allows for much more consistent error catching. 

Take a look. This is a pretty traditional async function using promises. The problem with this system is that the JSON.parse method may fail and we wouldn't get any error messages about it. 
```
    const oddRequest = () => {
        try {
          getJSON()
            .then(result => {
              // this parse may fail
              const data = JSON.parse(result)
              console.log(data)
            })
            //  handle asynchronous errors
             .catch((err) => {
               console.log(err)
             })
        } catch (err) {
          console.log(err)
        }
      }
```

Where as the async/await method below would allow us to catch those parsing errors. Not to mention its a tidy piece of code compared to above.
```
        const oddRequest = async () => {
          try {
            // this parse may fail
            const data = JSON.parse(await getJSON())
            console.log(data)
          } catch (e) {
            console.log(e)
          }
        }
```

Async/await also handles chaining of async functions much better. If you've ever written async functions with a lot of .then lines in it, you might want to reconsider!
