# Problem Explanation:
- Return true if the string in the first element of the array contains all of the letters of the string in the second element of the array..

## Hint: 1
- If everything is lowercase it will be easier to compare.

## Hint: 2
- Our strings might be easier to work with if they were arrays of characters.

## Hint: 3
- A loop might help. Use `indexOf()` to check if the letter of the second word is on the first.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function mutation(arr) {
  var test = arr[1].toLowerCase();
  var target = arr[0].toLowerCase();
  test = test.split('');
  target = target.split('');
  for (i=0;i<test.length;i++) {
    if (target.indexOf(test[i]) < 0)
      return false;
  }
  return true;
 }
```

```js
function mutation(arr) {
  var first = arr[0].toLowerCase().split('');
  var second = arr[1].toLowerCase().split('');
  var temp = 0;
  for (var s = 0; s < second.length; s++) {
    if (first.indexOf(second[s]) > -1) {
      temp += 0;
    } else
      temp += 1;
  }

  if (temp === 0)
    return true;
  else
    return false;
}
```

# Code Explanation:
- First, we make the two strings in the array lowercase.  
- Second, we split the individual strings in to 2 separate arrays of characters. test variable holds what we are looking for. target variable is where we are looking.   
- Third, we loop through our test characters, and if they are not _all_ found we return false.

# Credits:
If you found this page useful, you can give thanks by copying and pasting this on the main chat: `Thanks @sxmxc @Rafase282`

> **NOTE:** Please add your username only if you have added any **relevant main contents** to the wiki page. (Please don't remove any existing usernames.)
