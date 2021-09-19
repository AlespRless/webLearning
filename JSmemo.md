### 1. Arrow function
  + => (√)   -> (×)
  + The value of "This" in arrow function is the same with the one outside.
  + Arrow functions can't be hoisted.
  + "return" and "{}" can be omitted.
  + Arrow functions are not supported in IE and the earlier versions.
### 2. Array
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
### 3. Object
  + enumeration method
      * for in : Access all ___enumerable___ properties of an object and its ___prototype chain___
      * Object.ket(o) : Access all ___enumerable___ properties of an object 
      * Object.getOwnPropertyNames(o) : Access all  ___properties___ of an object 
  + create a object
      * Object initializer (Add brackets when using literals)
        ```
        var obj = { property_1: value_1,   
                    2: value_2,   
                    ["property" +3]: value_3,  
                    "property n": value_n }; 
        ```
      * constructor function
        ```
        function Car(make, model, year) {
          this.make = make;
          this.model = model;
          this.year = year;
        }
        var mycar = new Car("Eagle", "Talon TSi", 1993);
        ```
      * Object.create()
        ```
          // Animal properties and method encapsulation
          var Animal = {
            type: "Invertebrates", 
            displayType : function() { 
              console.log(this.type);
            }
          }

          var animal1 = Object.create(Animal);
          animal1.displayType(); // Output:Invertebrates

          var fish = Object.create(Animal);
          fish.type = "Fishes";
          fish.displayType(); // Output:Fishes
        ```  
  + prototype chain
      ![1632055256138](https://user-images.githubusercontent.com/71930297/133927859-aa3f1b97-baab-48ee-87c7-35925e88b2b0.jpg)
  + you can delete a not inherited property by ___delete___
    you can also delete a ___global property___ which is not declared by ___var___
### 4.Promise
  + failure handling
    you can only catch the failures when Thread execution has entered ___try catch___ but the ___try catch___ has not finished 
  + Promise rejection
    ___rejectionhandled___ & ___unhandledrejection___
    A particularly useful example: when you use Node.js, some dependency modules may have Rejected Promises that are not handled,which are printed to the console at runtime. You can capture this information in your own code and then add handlers corresponding to ___unHandledrejection___ for analysis and processing, or just to make your output cleaner.
    ```
    window.addEventListener("unhandledrejection", event => {
      /* 你可以在这里添加一些代码，以便检查
      event.promise 中的 promise 和
      event.reason 中的 rejection 原因 */

      event.preventDefault();
    }, false);
    ```
  + Promise's combination
  ___Promise.all()___ wait for all the promises
  ___Promise.race()___ choose the fastest one no matter failure or success
  + nested Promise
    it's not a good idea to use nested Promises unless you want to achieve high precision of failure catching
    ```
    doSomethingCritical()
      .then(result => doSomethingOptional()
        .then(optionalResult => doSomethingExtraNice(optionalResult))
        .catch(e => {console.log(e.message)})) // 即使有异常也会忽略，继续运行;(最后的catch会输出doSomethingExtraNice的错误信息)
      .then(() => moreCriticalStuff())
      .catch(e => console.log("Critical failure: " + e.message));
    ```

