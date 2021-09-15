---
title:  "Python Revision Tour II - Notes"
date:   2021-09-13 11:40:42 +0530
categories: notes
permalink: /:title
---
## Strings

Strings in Python are sequences of characters. The characters can be accessed using `stringName[index]`, index starts from 0 from the left and -1 to the right.

Length of strings can be determined using `len(stringName)` which returns an int with no. of characters in the string.

Note
: You cannot change individual letters in a string by assignment (hence it is an immutable datatype). `stringName[2]="a"` gives an error.

Strings can be traversed using `for ch in stringName:`. `ch` takes the value of each character in the string.

### String operators

- `+`  : "power" + "ful" = "powerful"
- `*`  : 3 * "ful" = "fulfulful"
- `in` : "ab" in "abcd" = True
- `==` : "ab" == "ab" = False (Note: This is case sensitive!)

### `ord` and `chr`

`ord`
: Gives ASCII value of character, e.g `ord("A")` = 65
`chr`
: Gives character from ASCII value, e.g `chr(65)` = "A"

### Slicing

Using `stringName[n:m]` will give the slice of the string of characters with indices n to m (n inclusive, m exclusive).
Using `stringName[n:]` will give the slice of the string of characters from indice n to the end of string (n inclusive).
Using `stringName[:m]` will give the slice of the string of characters from the start of string to indice m (m exclusive).
Using `stringName[n:m:s]` will give the slice of the string of every sth character with indices n to m (n inclusive, m exclusive) (using s=2 will skip every other character).

This works for negative indices too. If indices are out of bounds, empty string is returned rather than an error.

### String functions

|Function|Description|Returns|
|`capitalize()`|Capitalizes first letter|String|
|`find(sub,[start,[end]])`|Finds sub in string and returns index|int or null|
|`isalnum()`|Checks if string is alphanumeric|Boolean|
|`isalpha()`|Checks if string is alphabetical|Boolean|
|`isdigit()`|Checks if string is numerical|Boolean|
|`isspace()`|Checks if string only contains whitespace|Boolean|
|`islower()`|Checks if string only contains lowercase characters|Boolean|
|`isupper()`|Checks if string only contains uppercase characters|Boolean|
|`istitle()`|Checks if string only contains titled words|Boolean|
|`lower()`|Converts all characters to lowercase|String|
|`upper()`|Converts all characters to uppercase|String|
|`title()`|Converts the string to a titled string|String|
|`startswith(sub)`|Checks if string starts with sub|Boolean|
|`swapcase()`|Inverts case|String|
|`partition(sep)`|Partitions string using the given separator|Tuple|
|`count(sub)`|Counts the no. of instances of sub|int|
|`lstrip()`|Removes leading whitespace|String|
|`rstrip()`|Removes trailing whitespace|String|

## Lists

Lists can be created using `listName = list()`, or using `listName = list(<sequence>)`, where the sequence can be a String, tuple, another list, etc. A list can be directly input by the user using `listName = eval(input())`.

A list can be traversed using `for elmt in listName:`, `elmt` takes on the values of elements one-by-one.

### List operators

- `+`  : `[1,2,3,4] + [5,6,7]  = [1,2,3,4,5,6,7]`
- `*`  : `3 * [1,2,3] = [1,2,3,1,2,3,1,2,3]`

Lists can also be sliced, very similarly to Strings.
However unlike strings, list elements and slices can be directly changed by assignment, e.g. `listName[0:2] = [5,67]` is valid.

## List manipulation

- `lst.append(item)`     : Adds `item` to the end of list.
- `lst[index] = value`   : Directly changing values.
- `del lst[index/slice]` : Deletes given part of list.

Note
: `del lst` deletes the entire `lst` object.

Note
: To make a true copy of a list, use `lst2 = list(lst)`. This creates a new independent copy of the list.

### List functions

|Function|Description|Returns|
|`lst.index(item)`|Returns first index of item|int|
|`lst.append(item)`|Adds item to list|null|
|`lst.extend(lst2)`|Adds `lst2` to end of `lst`|null|
|`lst.insert(pos, item)`|Adds item to list; pos is the index of item BEFORE WHICH item is to be added|null|
|`lst.pop()`|Removes last element from list and returns it|any datatype|
|`lst.pop(index)`|Removes element with index `index` from list and returns it|any datatype|
|`lst.remove(item)`|Removes first instance of `item` from list|null|
|`lst.clear()`|Empties list|null|
|`lst.reverse()`|Reverses list|null|
|`lst.sort()`|Sorts list in ascending order|null|
|`lst.count(item)`|Counts number of instances of `item` in `lst`|int|

## Tuples

Tuples can be created using `t = tuple()`, or using `t = tuple(<sequence>)`, where the sequence can be a String, another tuple, list, etc. A tuple can be directly input by the user using `t = eval(input())`.

Note
: Single element tuple must be assigned as `t = (3,)` as `t = (3)` makes t an integer.

Tuple operations, slices, indexing, etc. are the same as lists. However elements of a tuple cannot be edited in place as tuples are immutable.