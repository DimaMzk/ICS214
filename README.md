# ICS214 - Concat Reference
[Original Wiki](https://github.com/DimaMzk/ICS214/wiki)

# Statements

Statements usually end in a `;`. Here are a few examples of statements:

**Declaration Statements:**
```cpp
int x;
```

**Jump Statements:**
```cpp
break; continue;
```

**Expression Statements:**
```cpp
x == 5
```

**Compound Statements:**
```cpp
{ x = 5;, y = 3}
```

**Selection Statements (Conditionals):***
```cpp
for (x > 5) { ... }
```

**Try Blocks:**
```cpp
try { ... }
```


# The `main()` function

Every C++ program **_must_** have a function named `main()`, which returns an int.

Programs will start execution with the first statement in `main()`, and go from there

## Why return an int?

The int that is returned tells the system how the program terminated. Generally, anything other than 0, is considered an error.


# #include

`#include` is a preprocessor directive to include the contents of a given file.

For example, for built in libraries:
```cpp
#include <iostream>
```
Will paste in contents of iostream directly where the #include was called

For custom files, you would use `<>` instead of `""`
```cpp
#include "CustomFile.h"
```


# Comments

Here are some examples of comments in `C++`

```cpp
std::cout << "Hi"; // Comment at end of statement

// Single Line comment on its own

/* This is a multi-line comment
   Sometimes they are called block-comments
   Whatever floats your boat */
```

## Some tips for commenting

At the library, program, or function level, use comments to describe **_what_**.
```cpp
// This function uses newton's method to approximate the root of a given equation.
int newton(int var) {
```

Inside the library, program, of function, use comments to describe **_how_**.
```cpp
char finalGrade(int grades[]) {
    /* To calculate the final grade,
       We sum all the weighted midterm homework scores,
       and divide by the number of scores to assign a percentage.
       This percentage is used to calculate a letter grade */
```

At the statement level, use comments to describe **_why_**.
```cpp
// We need to multiply this by two, because they are only bought in pairs
cost = quantity * 2 * storePrice;
```


# Variables

Variables have an identifier (name), a type (what it can hold [int]), and a value (5)

The type determines how the value in memory should be interpreted.

For example:
```cpp
int myCoolVariableName = 5;
```
Has three parts. `int` tells `C++` that this is a `integer` variable, and to allocate (a minimum of) two bytes to store in. 
`myCoolVariableName` is the identifier for the variable. This is how to reference the variable in the future.
` = 5` is the definition of the variable. In this case, we are setting it to the literal `5`

## Initialising a variable

There are three ways to initialise a variable

**Copy initialisation (With the assignment Operator):**
```cpp
// copy initialisation of value 5 into variable width
int width = 5;   
```

**Direct initilisation (Using parenthisis):**
```cpp 
// Direct initialisation of value 5 into variable width
int width( 5 );
```

**Uniform initialisation (a.k.a brace initialisation `C++11`):**
```cpp
// brace (uniform) initialisation of value 5 into variable width
int width{ 5 };

// Zero initialisation to value 0
int width{};

// Error: An integer variable can not hold a non-int value (Compiler will yell at you)
int width{ 4.5 };
```

### Why use uniform initialisation?

Uniform (brace initialisation) is prefered because in disallows `narrowing conversion`.
```cpp
int x = 4.5;  // The fraction is  dropped, x will be 4
int y{ 4.5 }; // The compiler will complain, and stop the build
```

# Variable Sizes

Here are the **_minimum_** Guaranteed sizes you can get in `C++`
| Category | Type | Minimum Size | Notes |
| --- | --- | --- | --- |
| Boolean | `bool` | `1` byte ||
| Character | `char` | `1` byte | Always 1 |
|| `wchar_t` | `1` byte ||
|| `char16_t` | `2` bytes | `C++11` type |
|| `char32_t` | `4` bytes | `C++11` type |
| Integer | `short` | `2` bytes ||
|| `int` | `2` bytes ||
|| `long` | `4` bytes ||
|| `long long` | `8` bytes | `C99/C++11` type |
| Floating Point | `float` | `4` bytes ||
|| `double` | `8` bytes ||
|| `long double` | `8` bytes ||
