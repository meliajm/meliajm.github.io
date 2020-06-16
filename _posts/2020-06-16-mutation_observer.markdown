---
layout: post
title:      "Mutation observer"
date:       2020-06-16 14:33:07 -0400
permalink:  mutation_observer
---


Hello! I'm Troy McClure, you might remember me from... last week. 

So you want to observe a class name change in JavaScript and this occurred because someone else modified something that changed the DOM you are observing. Why would you want to do this? Probably because the interface you are interacting with can change as other users interact with it as well and maybe the class name change results in a styling change as well. Here are the docs from MDN https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver.

Here I'll go over an example of how the mutation observer works.

```const exampleObserver = new MutationObserver(someCallbackFunction)```

The callback function is where most of the action will occur.

```const someCallbackFunction = function(mutationsList) {
    for(let mutation of mutationsList) {
        console.log(mutation.target.className)        
    }
};```

So now we can see that our callback function takes in a list of mutations and as we iterate over the mutation list, we can console log them and see what the class name is as each mutation is changed.

```const config = { attributes: true, childList: true, subtree: true };```

We need a config to set us up so we know which mutations to observe.

Now we are ready to call the observer on a target node:
```exampleObserver.observe(targetNode, config) ```

I think of this as an event listener, except the event is not caused by the user on her interface necessarily. And also is good alternative to setInterval or setTimeout.

Oh! And to stop observing:
```observer.disconnect();```

And that's it!
