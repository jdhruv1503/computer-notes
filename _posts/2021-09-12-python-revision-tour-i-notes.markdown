---
title:  "Python Revision Tour I - Notes"
date:   2021-09-12 11:40:42 +0530
categories: notes
permalink: /:title
---
## Tokens

Tokens (or lexical units) are the smallest unit of a program. Their types are:

- Keywords
- Operators
- Literals
- Identifiers
- Punctuators

### Keywords

Predefined words with special meaning such as `True`, `assert`, `break`, `elif`, `while`, etc.

### Identifiers

Names given to parts of a program such as functions, variables, etc.

- Must be non-keyword word with no spaces
- Must be made up of letters, numbers, and underscores
- Cannot begin with a number

### Literals

String literal
: Sequence of characters. Can be single-line (e.g. `'String'`) or multi-line (e.g. `'''Hello \n World'''`)

Numeric literal
: Can be decimal integers (e.g. `2322`), octal integers (e.g. `0o77`), hexadecimal integers (e.g. `0xAF`), floating points (e.g. `-14.55`), or complex numbers (e.g. `5 + 6J`)

Boolean literal
: Can only represent True and False

None literal
: Can only represent special value None.

### Operators

Tokens that trigger some computation. For example, `and`, `+`, `/`, `<=`, `==`, `=`, etc.

### Punctuators

Punctuation to organize the program, such as `'`, `"`, `[]`, `{}`, `:`, etc.

## Variables and typing

In Python, variables use dynamic typing, i.e. datatype of a variable can be changed during runtime.

## Simple input/output

Input can be taken by `variableName = input(stringToBeDisplayed)`. This will return a string `variableName` with the user input.

Output can be given by `print(string1ToBeDisplayed, string2ToBeDisplayed, ..., sep=sepString)`. The different strings will be separated by sepString (space by default).

## Datatypes

Immutable datatype
: Cannot be changed during runtime. They are `int`,`boolean`,`string`,`tuple`,`float`.

Mutable datatype
: Can be changed during runtime. They are `list`,`dictionary`,`set`.

### Typecasting

Variable datatype can be forcefully changed using `variableName = newDatatype(oldVariable)`. For example, `myInt = int(input())` will take an input and convert the input string to an integer.

## Math library functions

Using `import math` we can use library functions such as 

- `ceil` (round up)
- `sqrt` (square root)
- `exp` (exponent with base e)
- `fabs` (absolute value)
- `floor` (round down)
- `log` (logarithm)
- `log10` (log base 10)
- `pow` (power)
- `sin`,`cos`,`tan` (trigonometry)
- `degrees`,`radians` (inter conversion)
- `fmod` (modulus)
- `factorial` (factorial)
- `gcd` (GCD)
