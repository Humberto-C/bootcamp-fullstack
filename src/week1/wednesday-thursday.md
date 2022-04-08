# Week 1 - Wednesday

## Find the smallest integer in the array ✔️

Given an array of integers your solution should find the smallest integer. 
You can assume, for the purpose of this kata, that the supplied array will not be empty.

For example:

- Given [34, 15, 88, 2] your solution will return 2
- Given [34, -345, -1, 100] your solution will return -345

<details>
  <summary>Solution</summary>
  
  ```js
  
    findSmallestInt(args) {
      return Math.min(...args);
    }
  ```

</details>

# Week 1 - Thursday

## Odd or Even? ✔️

Given a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

### Examples:

Input: [0]
Output: "even"

Input: [0, 1, 4]
Output: "odd"

Input: [0, -1, -5]
Output: "even"

<details>
  <summary>Solution</summary>
  
  ```js
     
      function oddOrEven(arr) {
          return arr.length == 0 ? 'even' : arr.reduce((acc, el) => acc += el) % 2 == 0 ? 'even' : 'odd';
      }
  
  ```

</details>

