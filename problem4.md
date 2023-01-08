# Codewars Kata 4

### Find the outlier

You will be given an array of integers with at least three elements. All elements will be either even or odd, save for one. Write a function that returns the outlier of the array. 

*Solution*
```
function findOutlier(integers){
  let evenOutlier = []
  let oddOutlier = []
  for (const element of integers){
    if(element % 2 === 0){
      evenOutlier.push(element)
    } else {
      oddOutlier.push(element)
  }
}
  return oddOutlier.length === 1 ? oddOutlier[0] : evenOutlier[0]
}

console.log(`findOutlier return ${findOutlier([1,2,1,1,1,1])}`)
console.log(`findOutlier return ${findOutlier([2,2,2,2,4,1,2,2])}`)
```

*Breakdown of Solution*

```
let evenOutlier = []
let oddOutlier = []
```

We establish two empty arrays, one for an even outlier, and one for an odd outlier, since we won't know which type of value will be returned. 

And now we're back in for....of loop land in which `element` is our variable element, and `integers` is our set of iterables (and our argument array). Our if statement first checks to see if an element has a remainder of 0 when divided by 2, in which case all value(s) will be pushed into evenOutlier array. If they are not, the value(s) will be pushed to the oddOutlier array. 

Finally, we run a ternary operator to see which of our two array is equal to only 1, thus making it the array with the outlier integer
```
return oddOutlier.length === 1 ? oddOutlier[0] : evenOutlier[0]
```

This is basically an abbreviated if/else statement. In plain English, the above operation states "if the length of the oddOutlier array is equal to 1, then return the value that is positioned at index 0. If that's not the case, then return the value from evenOutlier postioned at index 0. 

-HS