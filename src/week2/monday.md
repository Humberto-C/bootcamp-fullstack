#  Week 2 - Monday

## Palindrome strings ✔️

A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This includes capital letters, punctuation, and word dividers.

Implement a function that checks if something is a palindrome. If the input is a number, convert it to string first.

### Examples
```
isPalindrome("anna")   ==> true
isPalindrome("walter") ==> false
isPalindrome(12321)    ==> true
isPalindrome(123456)   ==> false
```

<details>
  <summary>Solution</summary>
  
  ```js
    
  function isPalindrome(line) {
  if(typeof line == 'number') line = line.toString();
  return line == line.split('').reverse().join('') ? true : false;
  }
  ```
  
</details>


## Multiple of index ✔️

Return a new array consisting of elements which are multiple of their own index in input array (length > 1).

### Some cases:

```
[22, -6, 32, 82, 9, 25] =>  [-6, 32, 25]

[68, -1, 1, -7, 10, 10] => [-1, 10]

[-56,-85,72,-26,-14,76,-27,72,35,-21,-67,87,0,21,59,27,-92,68] => [-85, 72, 0, 68]
```

<details>
  <summary>Solution</summary>
  
  ```js
  
  function multipleOfIndex(array) {
  return array.filter((x, index) => x % index === 0);
  }
  ```
  
</details>


## Well of Ideas - Easy Version ✔️

For every good kata idea there seem to be quite a few bad ones!

In this kata you need to check the provided array (x) for good ideas 'good' and bad ideas 'bad'. If there are one or two good ideas, return 'Publish!', if there are more than 2 return 'I smell a series!'. If there are no good ideas, as is often the case, return 'Fail!'.

<details>
  <summary>Solution</summary>
  
   ```js
  function well(x){
    let goods = x.reduce((acc, el) => {
      if(el == 'good')  acc++;
      return acc;
    },0) 
    return goods > 2  ? "I smell a series!" : goods > 0 ? "Publish!" : "Fail!";
  }
```
  
</details>

## Decode the Morse code ✔️

In this kata you have to write a simple Morse code decoder. While the Morse code is now mostly superseded by voice and digital data communication channels, it still has its use in some applications around the world.
The Morse code encodes every character as a sequence of "dots" and "dashes". For example, the letter A is coded as ·−, letter Q is coded as −−·−, and digit 1 is coded as ·−−−−. The Morse code is case-insensitive, traditionally capital letters are used. When the message is written in Morse code, a single space is used to separate the character codes and 3 spaces are used to separate words. For example, the message HEY JUDE in Morse code is ···· · −·−−   ·−−− ··− −·· ·.

NOTE: Extra spaces before or after the code have no meaning and should be ignored.

In addition to letters, digits and some punctuation, there are some special service codes, the most notorious of those is the international distress signal SOS (that was first issued by Titanic), that is coded as ···−−−···. These special codes are treated as single special characters, and usually are transmitted as separate words.

Your task is to implement a function that would take the morse code as input and return a decoded human-readable string.

### For example:

```
decodeMorse('.... . -.--   .--- ..- -.. .')
//should return "HEY JUDE"
```

NOTE: For coding purposes you have to use ASCII characters . and -, not Unicode characters.

The Morse code table is preloaded for you as a dictionary, feel free to use it:

Coffeescript/C++/Go/JavaScript/Julia/PHP/Python/Ruby/TypeScript: MORSE_CODE['.--']

<details>
  <summary>Solution</summary>
  
   ```js
  decodeMorse = function(morseCode){
  return morseCode.split('   ') //separate the string into words array
    .reduce((acc, el) => { // every word into letters and translate them to normal strings
    
    acc += el.split(' ').map((x) => MORSE_CODE[x]).join('') + ' ';
    return acc;
    
    }, '') 
    .trim();//delete blank spaces at the end
  }
  ```
  
</details>
