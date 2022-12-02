# Sample code used

```js

// Bubble sort Implementation using Javascript
 
 
// Creating the bblSort function
 function bblSort(arr){
    
 for(var i = 0; i < arr.length; i++){
    
   // Last i elements are already in place 
   for(var j = 0; j < ( arr.length - i -1 ); j++){
      
     // Checking if the item at present iteration
     // is greater than the next iteration
     if(arr[j] > arr[j+1]){
        
       // If the condition is true then swap them
       var temp = arr[j]
       arr[j] = arr[j + 1]
       arr[j+1] = temp
     }
   }
 }
 // Print the sorted array
 console.log(arr);
}
 
 
// This is our unsorted array
var arr = [234, 43, 55, 63,  5, 6, 235, 547];
 
 
// Now pass this array to the bblSort() function
bblSort(arr);
```

From: <https://www.geeksforgeeks.org/bubble-sort-algorithms-by-using-javascript/>

# Obfuscation

The following site has been used to produce the obfuscated code: <https://www.javascriptobfuscator.com/Javascript-Obfuscator.aspx>.
Furthermore, the function name in the obfuscated code has been renamed manually from `bblSort` to `xyz`.

# Input

Deobfuscate the following code and tell me what it does:

```js
var _0x9154=["\x6C\x65\x6E\x67\x74\x68","\x6C\x6F\x67"];function xyz(arr){for(var _0xebddx3=0;_0xebddx3< arr[_0x9154[0]];_0xebddx3++){for(var _0xebddx4=0;_0xebddx4< (arr[_0x9154[0]]- _0xebddx3- 1);_0xebddx4++){if(arr[_0xebddx4]> arr[_0xebddx4+ 1]){var _0xebddx5=arr[_0xebddx4];arr[_0xebddx4]= arr[_0xebddx4+ 1];arr[_0xebddx4+ 1]= _0xebddx5}}};console[_0x9154[1]](arr)}var arr=[234,43,55,63,5,6,235,547];xyz(arr)
```

# Answer

This code defines a function `xyz` that takes in an array of numbers, `arr`. The function sorts the elements of the array in ascending order, then logs the sorted array to the console.

Here is the deobfuscated code:

```js
Copy codevar _0x9154 = ["length", "log"];
function xyz(arr) {
  for (var i = 0; i < arr[_0x9154[0]]; i++) {
    for (var j = 0; j < (arr[_0x9154[0]] - i - 1); j++) {
      if (arr[j] > arr[j + 1]) {
        var temp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = temp;
      }
    }
  }
  console[_0x9154[1]](arr);
}
var arr = [234, 43, 55, 63, 5, 6, 235, 547];
xyz(arr);

```

This code uses a variation of the bubble sort algorithm to sort the elements of the array in ascending order.
