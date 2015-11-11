# Problem Explanation:
- You will create a program that will find the missing letter from a string and add it. If there is not missing letter it will return undefined. There is currently no test case for it missing more than one letter, but if anything recursion can be implemented or a second or more calls to the same function as needed. Also the letters are always provided in order so there is no need to sort them.

## Hint: 1
- You will need to convert from character to ASCII code using the two methods provided in the description.

## Hint: 2
- You will have to check for the difference in ASCII code as they are in order. Using a chart would be very helpful.

## Hint: 3
- You will need to figure out where to insert the letter and how to do it, along with handling the case that there is not missing letter as it needs an specific return value.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:
First:

```js
function fearNotLetter(str) {
  // Create our variables.
  var firstCharacter = str.charCodeAt(0);
  var valueToReturn = '';
  var secondCharacter = '';

  // Function to find the missing letters
  var addCharacters = function(a, b) {
    while (a - 1 > b) {
      b++;
      valueToReturn += String.fromCharCode(b);
    }

    return valueToReturn;
  };

  // Check if letters are missing in between.
  for (var index = 1; index < str.length; index++) {
    secondCharacter = str.charCodeAt(index);

    // Check if the diference in code is greater than one.
    if (secondCharacter - firstCharacter > 1) {
      // Call function to missing letters
      addCharacters(secondCharacter, firstCharacter);
    }

    // Switch positions
    firstCharacter = str.charCodeAt(index);
  }

  // Check whether to return undefined or the missing letters.
  if (valueToReturn === '')
    return undefined;
  else
    return valueToReturn;
}
```
```js
Second:

function fearNotLetter(str) {
  
  for(var i = 0; i < str.length; i++) {
    /* code of current character */
    var code = str.charCodeAt(i);
    /* if code of current character is not equal to first charcter + no of iteration
    hence character has been escaped*/
    if ( code !== str.charCodeAt(0) + i) {
      /* if current character has escaped one character find previous char and return*/
      return String.fromCharCode(code-1);
    }  
  }
  return undefined;
}
```


# Code Explanation:
- Read comments in code.

# Credits:
If you found this page useful, you can give thanks by copying and pasting this on the main chat:  **`thanks @Rafase282`**
**`thanks @rohitnwn`**

> **NOTE:** Please add your username only if you have added any **relevant main contents** to the wiki page. (Please don't remove any existing usernames.)