#  Week 4 - Wednesday

## Maximum Length Difference ✔️

### Description 

You are given two arrays a1 and a2 of strings. Each string is composed with letters from a to z. Let x be any string in the first array and y be any string in the second array.

Find max(abs(length(x) − length(y)))

If a1 and/or a2 are empty return -1 in each language except in Haskell (F#) where you will return Nothing (None).

### Example 

```

a1 = ["hoqq", "bbllkw", "oox", "ejjuyyy", "plmiis", "xxxzgpsssa", "xxwwkktt", "znnnnfqknaz", "qqquuhii", "dvvvwz"]
a2 = ["cccooommaaqqoxii", "gggqaffhhh", "tttoowwwmmww"]
mxdiflg(a1, a2) --> 13

```

<details>
  <summary>Solution</summary>
  
  ```js
  
  function mxdiflg(a1, a2) {
    if (a1.length === 0 || a2.length === 0) return -1;

    let a1Max = Math.max(...a1.map((str) => str.length));
    let a2Max = Math.max(...a2.map((str) => str.length));
    let a1Min = Math.min(...a1.map((str) => str.length));
    let a2Min = Math.min(...a2.map((str) => str.length));

    return a1Max - a2Min > a2Max - a1Min ? a1Max - a2Min : a2Max - a1Min;
  }
  
  ```
</details>