#Problem 3 expanded (another example of a for...of look)

```
function evenNumbers(numberSet){
  let totalEvens = 0
  for (const element of numberSet) {
    if(element %2 ===0 ){
      totalEvens ++
    }
  }
  return totalEvens
}

console.log(`evenNumbers return ${evenNumbers([1,2,3,4,5,6,7,8,9,10,12,14,16,18])}`);
```

In the above function we are checking to see how many even numbers are present within an array. Similar to problem 3, I wrote a for...of loop to check for this, in which `element` is my variable, and `numberSet` is my iterable and my argument. The `if` statement indicates that if a present element returns a remainder of 0 then the count of total elements that this satisfies will increment by one. 

-HS