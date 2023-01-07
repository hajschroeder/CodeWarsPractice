# CodeWars Kata Problem 2

### Vlad the Disemvoweler

Write a function that removes all vowels from a word or phrase (while being mindful of spaces). 

Example: the input "hello" should return `hll`, and "hello world" should return `hll wrld`

*Solution* 
```
function disemvowel(str){
  return str.replace(/[aeiou]/gi, '')
}
```

This is a fairly straightforward solution. We are simply writing a return statement that uses the String.prototype.replace() method that accepts a regular expression as an argument. In this regex, we are establishing that we values we want are all vowels ('a', 'e', 'i', 'o', and 'u'). The square brackets establish that this is our set we are looking for, the `g` following the brackets indicates that we are globally searching for these characters, and the `i`, indicates we are looking for them regardless of case. We then tell the replace() method that what we intend to replace these found characters with is null space (ie, string data with no data in between, or empty quotes)

-HS