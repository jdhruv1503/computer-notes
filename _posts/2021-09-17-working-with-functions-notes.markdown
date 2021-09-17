---
title:  "Working With Functions - Notes"
date:   2021-09-17 11:40:42 +0530
categories: notes
permalink: /:title
---

## General format of a function

```
def functionName(arguments):
    // add processing here
    return returnedVariableorConstant
```

## Invoking a function

Invoking can be done simply by using `variableName = functionName(arguments)` or simply `functionName(arguments)` if the function doesn't return a value.

## Types of function

The types of function are:

- Builtin functions
- Module functions
- User defined functions

## Flow of execution

Whenever function is invoked, flow of execution will move to the function's body, **until the return statement is reached**, at which point the execution pointer will move back to the previous point. This means that any statements after the return statement **will not be executed.**

For example, in the following program:

```
1.  def calcSum(x,y):
2.      s = x + y
3.      return s
4.  num1 = 342
5.  num2 = 8499
6.  sum = calcSum(num1, num2)
7.  print(sum)
```

The flow of execution will be:

> 4-5-6-1-2-3-6-7

## Arguments

The types of arguments are:

- Positional (required) arguments
- Default arguments
- Keyword (named) arguments

### Positional arguments

For example, `def func(a,b,c)` has 3 positional arguments. All 3 of these will need to be provided when function is called, and in the appropriate order.

### Default arguments

For example, `def func(a,b,c=2)` has 2 positional and 1 default arguments. The first 2 of these will need to be provided when function is called, and in the appropriate order. The third one will use default value `2` when a value is not provided.

These can only appear at the end of the argument list, i.e. `def func(a,b=2,c)` is invalid.

### Named arguments

Named arguments are when arguments can be written in any order as long as they are **all** named, i.e. for `def func(a,b,c)`, a valid function call would be `var = func(c=10, a=33, b=28)`.

## Returning values

A variable value can be returned using `return variableName`. However, simply `return` can be used to not return any value, and simply return back to the code block that called the function.

Multiple values can be returned using `return var1, var2, ...` and the function can be called as `a = function()`. Then, `a` will be a tuple containing `(var1, var2, ...)`. We can also directly unpack the tuple using `v1, v2, ... = function()`

## Scope

- Global scope: For variables initialized outside any function, or in the main body.
- Local scope: For variabled initialized inside a function, which can't be used outside the function.

In case of a conflict where multiple variables in different scopes have same name, python uses LEGB rule as follows:

1. Local scope variable
2. Enclosing scope variable
3. Global scope variable
4. Built-in variable

So, functions **can** make changes directly to variables in main scope, as long as they are mutable.