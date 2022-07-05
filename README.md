# eloquent-javascript-notes
Interesting tidbits from the book Eloquent Javascript by Marjin Haverbeke

Read it for free: https://eloquentjavascript.net/

<img src="https://eloquentjavascript.net/img/cover.jpg" alt="eloquent JS book cover" width="200px">


## Chapter 1

- Javascript uses unicode (reference table for characters), `utf-16` encoding, and each character is mapped to 16 bits. 
Some characters take up more than 16 bits, so a string like “dog❤️” has length 5, as emojis take up two 16-bits units 

- `NaN` is meant to represent the result of a nonsensical operation. As such, it is the only value in Javascript that is not equal to itself 

- Operators precedence for booleans is `OR`, then `AND`, then comparison operators (>, <=...>), then the rest

- In JS type coercion, if one of the 2 operands is `null` or `undefined`, the result will be true only if the other operand is also `null` or `undefined`. 
Hence you can test if a value is `null` or `undefined` by checking `x == null`. 
This will only be true if x is either null or undefined