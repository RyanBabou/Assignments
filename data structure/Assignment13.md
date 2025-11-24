# Assignment 13
## Task
1. The space complexity is O(N^2) because the function creates a new array that can grow to hold about N * (N − 1) new strings, which is proportional to N^2.
2. The space complexity is O(N) because the function creates a new array that stores all N elements from the original array.
3.  
 ```text
  function reverseInPlace(array) {
  let left = 0;
  let right = array.length - 1;
  while (left < right) {
    let temp = array[left];
    array[left] = array[right];
    array[right] = temp;
    left++;
    right--;
  }
  return array;
}
```
4. 

| Version    | Time Complexity | Space Complexity |
|----------- |-----------------|------------------|
| Version #1 |      O(N)       |   O(N)           |
| Version #2 |      O(N)       |   O(1)           |
| Version #3 |      O(N)       |   O(N)           |
   
## Link
https://drive.google.com/file/d/18evhQ3vWnOKCkPiMZ-tKWxr7gYgK98gX/view?usp=sharing
