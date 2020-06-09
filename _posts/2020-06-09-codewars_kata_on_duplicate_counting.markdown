---
layout: post
title:      "Codewars Kata on duplicate counting"
date:       2020-06-09 19:16:53 +0000
permalink:  codewars_kata_on_duplicate_counting
---


Okay, so the purpose of this blog is explain my thought process in building my solution for this kata. https://www.codewars.com/kata/54bf1c2cd5b56cc47f0007a1/javascript

Basically the idea is to count the number of distinct duplicates. So if you've got a string ```aabBb``` that would be 2 duplicates. Note that the solution is case-insensitive.

Okay, so here's the function below. I start out with three inital arrays. `resArr` has a value because of the way I am comparing and counting later along. First, I am iterating over the lower case text and pushing the text element (here `t`) to `array`. There are duplicates so that each element of `array` is now an array containing one letter or multiple of the same letters. The next step is to get only arrays with a length of more than one because these are where the duplicates occur.
Next I sort `resArr` and compare to see if the first letter of each array within `resArr` is equal or not. If they are not equal I add it to the `result` array. Because of the comparing from the last item to the non-existent last item plus 1, I need to start with `resArr` out with some value, in this case 1. Finally I return the array based on length of `result`.

```
function duplicateCount(text){
    // here are three arrays to start
    let array = []
    //let resArr = [1]
    let result = []
	  // next I convert the text to lower case since case does not matter for counting
    text = text.toLowerCase()
    for (let i=0; i<text.length; i++) {
       array.push(text.split('').filter(t => t===text[i]))
    }
    array = array.filter(arr=>arr.length>1)
    array.forEach( arr => {
      if (!resArr.includes(arr)) {
        resArr.push(arr)
      }
    })
    resArr = resArr.sort()  
    
    for (let i=0; i<resArr.length-1; i++) {
      if (resArr[i][0]!==resArr[i+1][0]) {
        result.push(resArr[i])
      }
      
    }
  
    if (result.length===0){
      return 0
    } else {
      return result.length
    }
  
  }
```
