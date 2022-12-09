# CodeWars Kata Problem 1

### Narcissistic Numbers

A narcissistic number is a number that, when the digits are taken individually, raised to the power of the total number of digits, and then have to raised values added together, the raised values equal the original number. 

For Example

> the number 153, if broken down to `1**3 + 5**3 + 3**3` will equal 153

Write a function that returns true if a number is narcissistic, false is it is not 

*Solution* 
```
function isNarcissistic(value){
  const integerSet = value.toString().split('').map(Number);
  const myExponent = integerSet.length;
  const isItNarc = integerSet.reduce(
    (total, indivInteger) => total + Math.pow(indivInteger, myExponent), 
    0
  );
  return isItNarc === value;
}

```

*Breakdown of solution* 
```
/// 
  const integerSet = value.toString().split('').map(Number)
  const myExponent = integerSet.length;
///
```
In our first line after declaring the function, we set a constant `integerSet` in which we grab our parameter, use the built-in Object.prototype.toString() method to ensure it can be manipulated, and then take the individual characters and turn them into array elements with Array.prototype.split(''). We then use Array.prototype.map() which takes Number as an argument and converts each element into an integer.

```
///
  const isItNarc = integerSet.reduce((total, indivInteger) => total + Math.pow(indivInteger, myExponent), 0);
return isItNarc === value;
///
```

These next two lines establish a new constant in which we further manipulate the data above. We grab our first constant `integerSet` and use the Array.prototype.reduce() method on it. Array.prototype.reduce() is a method which easily allows us to set three parameters, the first will be a placeholder for the accumulated value, the second will represent the integer within the array that the reduce() method is working through, and the third will establish our initial value (this parameter will be set after an arrow function within the method). *(Note: the MDN documentation refers to these parameters as `accumulator` and `currentValue`. These easily could have been the names chosen for our paremeters)* 

Within the arrow function following reduce() we have another built-in method, Math.pow(). The syntax for this method can easily be best understood as `Math.pow(base, exponent)`. In other words, 3**4 (3 raised to the power of 4) would be written as `Math.pow(3, 4)`. What the arrow function does is it accepts the reduce() parameter `total` (aka `accumulator`), adds it to the exponential value of the individual integers, and begins this process at 0. 

We end with our return statement which uses a conditional to see if the value we gained from the isItNarc variable function is an exact match with our initial function argument. If it is, it will return a boolean value of true, meaning we got ourselves a narcissist.  