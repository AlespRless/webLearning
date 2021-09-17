#### 1. Arrow function
  + => (√)   -> (×)
  + The value of "This" in arrow function is the same with the one outside.
  + Arrow functions can't be hoisted.
  + "return" and "{}" can be omitted.
  + Arrow functions are not supported in IE and the earlier versions.
#### 2. Array
  + .length isn't a readOnly prop
  + .sort: sort by <a href = "https://en.wikipedia.org/wiki/In-place_algorithm">In-place algorithm</a>
    
    `arr.sort([compareFunction])`  
    return a sorted array  
```
function compare(a, b) {
    if (a < b ) { // sort by some standards like a < b  
      return -1;  
    }  
    if (a > b ) {  
      return 1;  
    }  
    // a must be equal to b  
    return 0;  
}
 
//inputs will be turned into strings:

==>let arr = [9, 89]
==>console.log(arr.sort())
<==[89, 9]

//sortNumbers:  

`compareNumbers(a, b) => a - b `  
