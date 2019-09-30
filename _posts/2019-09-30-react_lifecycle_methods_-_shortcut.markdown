---
layout: post
title:      "React Lifecycle Methods - Shortcut"
date:       2019-09-30 17:50:51 +0000
permalink:  react_lifecycle_methods_-_shortcut
---


Lifecycle methods can be thought of as the series of steps that a component takes in React from it's initialization to its eventual death ( from mounting to unmounting in other words). Here we will quickly give you a snap shot of those methods and when they are triggered and what they are typically used for. A component essentially has 3 different phases of its lifecycle: mounting, updating, and unmounting. 

**Mounting**
Unsurprisingly the first step in the components lifecycle is its constructor (if its a class component and not just  a functional component). This is where we  define the components state, and set its props if necessary. A typical constructor looks like this:
```
class MyComponent extends Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 0,
    };
  }
}
```

This is also where you may need to bind methods: `onChange={this.handleChange.bind(this)}`

The next method called in the mounting phase is the getDerivedStateFromProps method. It is used to set the components state based on the prop values passed to in on mounting. It's not used all that often, but its good to know that it is there. Following getDerivedStateFromProps is the most comment lifecycle method: render.

Render is where all the work happens and the jsx is formulated to produce the working component. After the component is rendered, but we're still technically in the mounting phase, the componentDidMount method is called. This is where we typically run code that fetches data from our APIs, or anything else that is processing heavy and may not complete instantly and need time to finish in an async loop. 

**Updating**
The first method run here is getDerivedStateFromProps, again. Here however, it is a bit more useful. We can use this method to update the state based on any prop changes. The shouldComponentUpdate method is called next. Normally if the state of a component is updated, the component should update. That is one of the things that makes React great. However sometimes we need to run checks or perform other functions before React automatically updates the component. This method allows us to intercept that auto updating feature when needed. 

Next we render again, because something is updating, we need to rerender the component to make the changes! However right before the update actually makes any changes to the DOM we have one last method fire that lets us make absolutely sure we're ready; getSnapshotBeforeUpdate. This is usually paired with the next method componentDidUpdate to act as a check with our previous state and what we think our new state should be. Then the updates take affect and we move on to...

**Unmounting**
We begin the end with componentWillUnmount which allows us to cancel any outgoing requests that aren't needed anymore and cleanup any left over scraps from our component that we don't need anymore. Then we have the getDerivedStateFromError, which let's us see if one of the component's descendants ran into trouble and display an error message if it did. Last we have the componentDidCatch, which is similar in that it will tell us if an error occurred in our child components. 

But all that text really just explains this chart, which is what my brain has a much easier time digesting:
![](https://i0.wp.com/programmingwithmosh.com/wp-content/uploads/2018/10/Screen-Shot-2018-10-31-at-1.44.28-PM.png?resize=1024%2C567&ssl=1)
