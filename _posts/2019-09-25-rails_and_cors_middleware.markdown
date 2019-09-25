---
layout: post
title:      "Rails and CORS Middleware"
date:       2019-09-25 15:43:43 +0000
permalink:  rails_and_cors_middleware
---


You just spent the last few nights after working banging away at your portfolio site in your local environment. You've finally got your rails backend communicating with your react frontend, the css is good enough for now. It's time to get this thing up on the web and make sure it's all going according to plan. You push your code up to Heroku and....CORS error.

It's really frustrating for a relatively new programmer to run into these problems. It just worked on my local machine!! It's important to understand why these errors come up though so I recommend you check out this article for the details: Paul [Nicholson is the man.](https://medium.com/@Nicholson85/handling-cors-issues-in-your-rails-api-120dfbcb8a24)

But for those of you in a rush I'll cut to the good stuff. The thing that tripped me up for a while with these kinds of errors is understanding the problem needs to be addressed on the backend. It looks like a frontend error. The front end is trying to pull data in from rails and failing, it must be something with my fetch! But really the frontend is just reporting the error. The real problem is in the backend, that's where Rack-Cors comes in. 

[Rack-Cors](https://github.com/cyu/rack-cors) is a Rails middleware gem that provides support for cross-origin resource sharing. It is also super simple to use which is a huge selling point in my book! Basically all you need to do is add the gem to your gem file, and then the following code block to your application.rb file:
```
#application.rb
config.middleware.insert_before 0, Rack::Cors do
  allow do
     origins '*'
     resource '*', :headers => :any, :methods => [:get]
   end
end
```

Success! Your portfolio site is live and now you can polish it up and get that new dream job!
