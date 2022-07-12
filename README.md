# eloquent-javascript-notes
Interesting tidbits from the book Eloquent Javascript by Marjin Haverbeke

Read it for free: https://eloquentjavascript.net/

<img src="https://eloquentjavascript.net/img/cover.jpg" alt="eloquent JS book cover" width="200px">


## Chapter 1

- Javascript uses unicode (reference table for characters), `utf-16` encoding, and each character is mapped to 16 bits (1 code unit). 
Some characters take up more than 16 bits, so a string like “dog❤️” has length 5, as emojis take up two 16-bits units 

- `NaN` is meant to represent the result of a nonsensical operation. As such, it is the only value in Javascript that is not equal to itself 

- Operators precedence for booleans is `OR`, then `AND`, then comparison operators (>, <=...>), then the rest

- In JS type coercion, if one of the 2 operands is `null` or `undefined`, the result will be true only if the other operand is also `null` or `undefined`. 
Hence you can test if a value is `null` or `undefined` by checking `x == null`. 
This will only be true if x is either null or undefined

## Chapter 5

- Common operations on JS Strings (e.g. getting length, or using square brackets to access elements) deal with code-units (i.e. 16 bits pieces).
JavaScript’s charCodeAt method gives you a code unit, not a full character code. The codePointAt method, added later, does give a full Unicode character.
So we could use that to get characters from a string. But the argument passed to codePointAt is still an index into the sequence of code units. So to run over all characters in a string, we’d still need to deal with the question of whether a character takes up one or two code units.

- Back when the `for/of` loop was implemented, everyone was pretty aware of the UTF-16 Javascript problem. 
When you use it to loop over a string, it gives you real characters, not code units.
It is therefore safe to assume that in `for (let c of str)`, the value of `c` will be one character, regardless of it being a simple unicode character or a complex emoji.

- findIndex is a more complex version of indexOf. Instead of looking for a specific value, it accepts a condition and returns the index of the first element for which the condition is true. -1 Otherwise. It is similar to Array.find, but it returns the index instead of the element itself.
