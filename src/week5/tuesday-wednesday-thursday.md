#  Week 5 - Tuesday

## Separating Strings 

### Description 

Create a function that takes a string and separates it into a sequence of letters.

The array will be formatted as so:

```js
[['J','L','L','M']
,['u','i','i','a']
,['s','v','f','n']
,['t','e','e','']]
```

The function should separate each word into individual letters, with the first word in the sentence having its letters in the 0th index of each 2nd dimension array, and so on.

Shorter words will have an empty string in the place once the word has already been mapped out. (See the last element in the last part of the array.)

### Examples

```js

sepStr("Just Live Life Man")
// => [['J','L','L','M'],
// => ['u','i','i','a'],
// => ['s','v','f','n'],
// => ['t','e','e','']]);

sepStr("The Mitochondria is the powerhouse of the cell")
// => [ [ 'T', 'M', 'i', 't', 'p', 'o', 't', 'c' ],
// => [ 'h', 'i', 's', 'h', 'o', 'f', 'h', 'e' ],
// => [ 'e', 't', '', 'e', 'w', '', 'e', 'l' ],
// => [ '', 'o', '', '', 'e', '', '', 'l' ],
// => [ '', 'c', '', '', 'r', '', '', '' ],
// => [ '', 'h', '', '', 'h', '', '', '' ],
// => [ '', 'o', '', '', 'o', '', '', '' ],
// => [ '', 'n', '', '', 'u', '', '', '' ],
// => [ '', 'd', '', '', 's', '', '', '' ],
// => [ '', 'r', '', '', 'e', '', '', '' ],
// => [ '', 'i', '', '', '', '', '', '' ],
// => [ '', 'a', '', '', '', '', '', '' ]]

```

<details>
  <summary>Solution</summary>
  
  ```js
  
  function sepStr(str) {
str = str.split(' ');
let newArr = [];
//finding the longest word in the array 
let longestItem = str.reduce((acc, el) => { 
    if(el.length > acc) acc = el.length;
    return acc;
} ,0)
// making and pushing sub arrays
for(let i = 0; i < longestItem; i++){
    newArr.push(
        str.reduce((acc, el) => {
            el[i] ? acc.push(el[i]) : acc.push('');
            return acc;
        }, [])
    );
}

return newArr;

}
  
  ```
</details>

#  Wednesday
 
## Highest Scoring Word 

### Description 
  
Given a string of words, you need to find the highest scoring word.

Each letter of a word scores points according to its position in the alphabet: a = 1, b = 2, c = 3 etc.

You need to return the highest scoring word as a string.

If two words score the same, return the word that appears earliest in the original string.

All letters will be lowercase and all inputs will be valid.
  
<details>
  <summary>Solution</summary>
  
  ```js
  function high(x){
    let abc = '0abcdefghijklmnopqrstuvwxyz';
    let scores = x.split(' ').map((word) => (
        word.split('').reduce((acc, el) => acc += abc.indexOf(el), 0)
    ))
    return x.split(' ')[scores.findIndex((x, index) => x === Math.max(...scores))];
  }
  ```
  
</details>
  

#  Thursday
  
## Where is my parent!?(cry) 

### Description
  
Mothers arranged a dance party for the children in school. At that party, there are only mothers and their children. All are having great fun on the dance floor when suddenly all the lights went out. It's a dark night and no one can see each other. But you were flying nearby and you can see in the dark and have ability to teleport people anywhere you want.
  
Legend:
-Uppercase letters stands for mothers, lowercase stand for their children, i.e. "A" mother's children are "aaaa".
-Function input: String contains only letters, uppercase letters are unique.
  
Task:
Place all people in alphabetical order where Mothers are followed by their children, i.e. "aAbaBb" => "AaaBbb".
  
<details>
  <summary>First Solution</summary>
  
  ```js
  function findChildren(dancingBrigade) {
	let newStr = '';
	dancingBrigade.toLowerCase().split('').sort()
		.reduce((acc, el) => {
			if(acc.indexOf(el) < 0) {
				newStr += el.toUpperCase();	
				acc = el;
			}
			else {
				newStr += el;
				acc += el;
			};
			return acc;
	}, '')
		return newStr;
  }  
  ```
  
</details>

  
  
