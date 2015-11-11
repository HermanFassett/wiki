![](http://i.imgur.com/jSJ4E7L.jpg)

# Problem Explanation:
The first thing to do is to get familiar with what the program is for, for this I would suggest you check the Wikipedia link as that is very important and from where you can also get the formula for the conversion. The hardest part are finding the formula, implementing it and for some modifying objects by the key. However, something that is not very clear is the fact that your program has to be able to check for any number of objects in the array which is what is tested on the second part.

## Hint: 1
The formula needed is: T = 2_pi _ sqrt(earthRadius + avgAlt to the cube / GM)

## Hint: 2
Use Math.round() to round up to the next whole number as requested. Using Math.ceil() will let you pass the first test but fail the second one.

## Hint: 3
Find out how to remove and add key to an object

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function orbitalPeriod(arr) {
  var GM = 398600.4418;
  var earthRadius = 6367.4447;
  var a = 2 * Math.PI;
  var newArr = [];
  var getOrbPeriod = function(obj) {
    var c = Math.pow(earthRadius + obj.avgAlt, 3);
    var b = Math.sqrt(c / GM);
    var orbPeriod = Math.round(a * b);
    delete obj.avgAlt;
    obj.orbitalPeriod = orbPeriod;
    return obj;
  };

  for (var elem in arr) {
    newArr.push(getOrbPeriod(arr[elem]));
  }

  return newArr;
}
```

# Code Explanation:
- The GM and `earthRadius` is given to us.
- To make the code easier to edit and read, I separated each part of the equation.
- Create a new array to store the `orbPeriods`.
- a is 2 times pi. The part that is a constant is on the global scope while the rest is part of a function.
- Create a function that will do the required work for any amount of objects.
- c is the power of `earthRadius` + the value of `avgAlt` to the cube.
- b is the square root of c divided by GM.
- Create `orbPeriod` to store the product of a & b, with the ceiling function applied to round up to the next whole number.
- Then we delete the key`avgAlt`, and add the new key and its value.

# Credits:
If you found this page useful, you can give thanks by copying and pasting this on the main chat:  **`thanks @Rafase282`**

> **NOTE:** Please add your username only if you have added any **relevant main contents** to the wiki page. (Please don't remove any existing usernames.)
