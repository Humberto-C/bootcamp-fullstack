#  Week 1 - Tuesday

## Ensure question Challenge ✔️

Given a string, write a function that returns the string with a question mark ("?") appends to the end, unless the original string ends with a question mark, in which case, returns the original string.

For example (Input --> Output)

```
"Yes" --> "Yes?" 
"No?" --> "No?"
```

<details>
  <summary>Solution</summary>
  
  ```js
     function ensureQuestion(s) {
        return s[s.length - 1] == '?' ? s : s + '?' ;
     }  
  ```
  
</details>

## Reversed Words Challenge ✔️

Complete the solution so that it reverses all of the words within the string passed in.

### Example:

```
"The greatest victory is that which requires no battle" --> "battle no requires which that is victory greatest The"
```

<details>
  <summary>Solution</summary>
  
  ```js
     
    function reverseWords(str){
      return str.split(' ').reverse().join(' '); // reverse those words
    }
  
  ```
  
</details>





