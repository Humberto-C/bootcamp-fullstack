#  Week 4 - Monday

## Two to One ✔️

### Description 

Take 2 strings s1 and s2 including only letters from ato z. Return a new sorted string, the longest possible, containing distinct letters - each taken only once - coming from s1 or s2.

### Example 

``` 
a = "xyaabbbccccdefww"
b = "xxxxyyyyabklmopq"
longest(a, b) -> "abcdefklmopqwxy"

a = "abcdefghijklmnopqrstuvwxyz"
longest(a, a) -> "abcdefghijklmnopqrstuvwxyz"

```

<details>
  <summary>Solution</summary>
  
  ```js
  
  function longest(s1, s2) {
    return (s1 + s2).split('').reduce((acc, el) => {
        if(acc.indexOf(el) < 0) acc += el;
        return acc;
    }).split('').sort().join('');
  }
  
  ```
  
</details>
