---
layout: post
title:      "Using setInterval with recursion"
date:       2020-06-23 18:07:04 +0000
permalink:  using_setinterval_with_recursion
---


Okay let's say you want to continuously check for some condition. Once that condition is reached, do something. Maybe then the conditions change and you want to check again if that original condition was met. So how do we do this?

First start the interval:

```
function runExampleIntervalWithRecursion() {
     // start first interval
     let intervalExample = setInterval(() => {
          // some variables
		      // some conditionals
		      let exampleCondition
		      if (!!exampleCondition) {
		           // do some work here
							 // we can think of this function below turning something on
					     exampleDoWorkFunction()
		           clearInterval(intervalExample)
		 }
		 // now is where some other things may happen
		 // we need to check if different conditions are met
		 // so that we can reset and see if the function we turned on above has now been turn off
		 let secondExampleInterval = setInterval(()=> {
		      // more variables maybe
					// more conditionals
					if (!!otherExampleCondition) {
					    // here is the recursion
							// now we are back to our original state where the function is turned off
							// and we are able to start from the beginning and keep running this function continuously
					    runExampleIntervalWithRecursion()
							clearInterval(secondExampleInterval)

					}
		 
     // this interval happens 5 seconds or 5000 ms		 
		 }, 1000)
		 
     // this interval happens 1 second or 1000 ms
     }, 1000);
}
```
