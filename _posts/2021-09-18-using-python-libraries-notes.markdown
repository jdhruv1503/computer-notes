---
title:  "(Extra) Using Python Functions - Notes"
date:   2021-09-18 11:40:42 +0530
categories: notes
permalink: /:title
---

## Libraries

Libraries in Python are a collection of modules.

Modules can be used to reuse code between programs.

## Modules

The parts of a module are:

- Docstrings ("""documentation strings in triple quotes""")
- Variables and constants
- Classes
- Objects
- Statements
- Functions

### An example module

```
# tempConversion.py
"""Conversion functions b/w fahrenheit and celsius"""

#Functions
def toC(x):
    """"Returns x converted to degree C"""
    return 5*(x-32)/9.0

def toF(x):
    """"Returns x converted to degree F"""
    return 9*x/5.0 + 32

#Constants
FREEZE_C = 0.0
FREEZE_F = 32.0
```

## Usage of modules

Modules need to be imported using `import moduleName` or `from moduleName import objectName`. After this, its functions can be called using `moduleName.functionName()`

Aliases can be given as `import moduleName as aliasName`. Then functions can be called using `aliasName.functionName()`

If a `from x import y` is used, for example `from math import pi`, then instead of `math.pi` we must use simply `pi`. This is because `from` importing adds all the objects to your program's environment directly. Alternatively we may use `from math import *` to import everything from `math` but not have to use the `math.` suffix before every function.

## Standard Python modules

### Built-in mathematical functions

|Function name|Description|
|`len(sequence)`|Returns length of `sequence` (list, tuple, string, etc.)|
|`pow(a,b)`|Returns value of a^b|
|`str(a)`|Converts `a` to a string|
|`int(a)`|Converts `a` to an integer|
|`float(a)`|Converts `a` to a float|
|`type(a)`|Returns datatype of `a`|
|`abs(a)`|Returns absolute value of `a`|
|`divmod(a,b)`|Divides `a` and `b` and returns a tuple `(quotient, remainder)`|
|`sum(iterable)`|Returns sum of elements of `iterable` (list, tuple)|
|`max(iterable)`|Returns maximum element of `iterable` (list, tuple)|
|`min(iterable)`|Returns minimum element of `iterable` (list, tuple)|
|`oct(a)`|Returns octal string of `a`|
|`hex(a)`|Returns hexadecimal string of `a`|

### Built-in string functions

|Function name|Description|
|`stringName.join(string2)`|Joins `stringName` between every element in `string2`, e.g. if `stringName` is `"*"` and `string2` is `"Hello"` then this function returns `"H*e*l*l*o"`|
|`stringName.split(string2)`|Splits `stringName` using separator `string2`, and returns a list containing split substrings|
|`stringName.replace(string2, string3)`|Replaces every instance of `string2` in `stringName` with `string3`|

### Random library functions

|Function name|Description|
|`random()`|Returns a random float between `0.0` and `1.0`|
|`randint(a,b)`|Returns a random integer between `a` and `b`, both inclusive|
|`random.uniform(a,b)`|Returns a random float between `a` and `b`, both inclusive|
|`random.randrange(start, stop, range)`|Returns a random element from `range(start, stop, range)`|

## Creating a simple package

Create a folder structure with valid folder names (underscore separated). In the root directory of the package folder, **as well as each subfolder** there must be an empty file `___init___.py`.

Then, add this folder to the `site-packages` folder of Python. The `site-packages` can be located by running this script:

> import sys
> print(sys.path)

After this, the package can be used using `import libraryName` or `import libraryName.subfolderName.pyFileNameinSubfolder`.