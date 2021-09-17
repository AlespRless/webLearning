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
    ```

    inputs will be turned into strings:  
    ```
    ==>let arr = [9, 89]  
    ==>console.log(arr.sort())  
    <==[89, 9]  
    ```
    sortNumbers:  
    `compareNumbers(a, b) => a - b `  

    sort by object's props
    ```
    var items = [
      { name: 'Edward', value: 21 },
      { name: 'Sharpe', value: 37 },
      { name: 'And', value: 45 },
      { name: 'The', value: -12 },
      { name: 'Magnetic' },
      { name: 'Zeros', value: 37 }
    ];

    // sort by value
    items.sort(function (a, b) {
      return (a.value - b.value)
    });

    // sort by name  
    items.sort(function(a, b) {
      var nameA = a.name.toUpperCase(); // ignore upper and lowercase
      var nameB = b.name.toUpperCase(); // ignore upper and lowercase
      if (nameA < nameB) {
        return -1;
      }
      if (nameA > nameB) {
        return 1;
      }

      // names must be equal
      return 0;
    });
    ```
