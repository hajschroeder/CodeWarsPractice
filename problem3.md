#Problem 3

*Vowel Counter*

Write a function that returns the count of all vowels within a string 

##Solution 1
```
function getCount(str){
  return (str.match(/[aeiou]/gi) || []).length
}
```
This solution is very similar to the previous problem. We are using the same regular expression, but instead of replacing a specified character, we are looking for character matches. It is important that we include within the matches `[]` which for our purposes indicate empty space. If given a string with no vowels such as `wyd rn` then the .length method will not work with a null set, which is what match() will return unless it is told to look for.

##Solution 2
```
function getCount(str){
  let totalVowels=0;
  const vowels = ['a', 'e', 'i', 'o', 'u']
  for (const char of str){
    if(vowels.includes(char.toLowerCase())){
      totalVowels++
    }
  }
  return totalVowels
}
```
This solution is a bit more straightforward but less elegant. We establish a variable to hold our vowel count, which we initially set to zero. We then build an array of all the characters we want to find.
```
/// 
  let totalVowels=0;
  const vowels = ['a', 'e', 'i', 'o', 'u']
///
```

Following this, we implement a for...of loop. This loop works by accepting a variable which will be the index item that is run through our iterable. In this case, we state that `char` (our index) will be iterated through `str` (which is both our iterable and our functions argument). Our if statement is written to state that if, within our established vowel array, there includes matching elemtns, the count (`totalVowels`) will be incremented by one for each element present. 

-HS