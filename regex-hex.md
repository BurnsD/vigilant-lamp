# Regex Tutorial: Hex Value

Regular expressions, also known as "Regex" are used when you have a need to search for an email, username, phone number, etc. They can also be utilized to validate a specific pattern of user input. Regex are strings made up of characters that function as a search pattern, by indentifying literal and meta characters in the expression to have that value returned in the search. 
In this tutorial I will go over the regular expression for matching a hex value as show below.

## Summary

The following shows the regular expression for matching a hex value:
```md
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```
Matching a hex value is beneficial because it's ability to represent large numbers such as binary or in the case of web development finding the hex value for colors within CSS. Using this method to find a specific color in order to update a theme of an application, can be crucial to saving time searching through large files. In the case for Web Development Hex values will be written as a hashtag or "pound sign" followed by 6 digits or 3 digits like this: 
```md
#353535   or    #555
```
A 3 digit hex code is shorthand for a 6 digit hex code. Each digit is clarifying the value of Red, Green, and Blue (RGB or RR,GG,BB)
For example the following with both provide the same values for dark green. 
```md
#0a0  and  #00aa00
```
## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)

## Regex Components
Regular expressions use two types of characters, Literal and Meta characters.

Literal Characters - Will ask for the exact value of a character within the expression.

Meta Characters - Indicate a pattern that needs to be searched for within the text.
### Anchors
Anchors are a form of Meta Characters, in our example ```/^#?([a-f0-9]{6}|[a-f0-9]{3})$/``` our anchors will be `^` and `$`


+ `^` - Indicates the start of the regex string and the following characters will searched.
+ `$` - Indicates the end of the regex string and ends the characters being searched for.

### Quantifiers
Quantifiers are at the end of each grouping within the regex, in our example ```/^#?([a-f0-9]{6}|[a-f0-9]{3})$/``` 

We have two quantifiers `{6}` and `{3}`

The value held within curly brackets `{x}`, indicates the serach will need to match the regex pattern exactly x number of times. 

In the case of hex value regex `[a-f0-9]` needs to be matched 6 times `{6}` and 3 times `{3}` in the second grouping.

### OR Operator
OR Operator is represented in regex as `|` also known as the pipe character, in our example ```/^#?([a-f0-9]{6}|[a-f0-9]{3})$/``` 

The pipe character is seperating `[a-f0-9]{6}` or `[a-f0-9]{3}` meaning that we want to search `[a-f0-9]` 6 times --or-- 3 times.

### Character Classes
Character classes are ways to define sets of characters. 

Some common character classes not shown in our example are:

+ `\d` - Matches `[0-9]`

+ `\w` - Matches `[A-Za-z0-9_]`

+ `\s` - Matches whitespace

+ `.`  - Matches any character

In our example, ```/^#?([a-f0-9]{6}|[a-f0-9]{3})$/``` We use a character class refered to as Bracket Expression. I will cover this seperatly down below. 

### Flags
Flags which are placed either after the second slash or the end of the regex bring functinoality or limitations to the regex. 
Common examples are:

+ `g` - Global Search

+ `i` - Case-insensitive Search

+ `m` - Multi-line Search

+ `s` - Allows `.` to match newline characters

Our example or Matching a Hex value does not utilize the use of a flag.
### Grouping and Capturing
Grouping Constructs are utilized as a regular expression gets more complex, containing different groupings within one expression. Groups are sectioned witin subexpressions or parantheses. 

In our example of matching a Hex value, we only have one grouping and do not utilize a grouping construct.
### Bracket Expressions
Brackets `[]` are commonly used within regex. 

What value you declare inside the square brackets indicates what will be found in your match.
Let's break down our example of matching a hex value ```/^#?([a-f0-9]{6}|[a-f0-9]{3})$/```

+ `[a-f]` will return any combination of the following lowercase letters. a,b,c,d,e,f This could also be done with the following: `[a, b, c, d, e, f]

+ `[0-9]` will return any numbers from 0 to 9.

+ `[a-f0-9]` Now we have merged this two expressions together so that we can match for a hex value consisting of a value from `[a-f]` and `[0-9]`


## Author
Written By: Dustin Burns

Github: https://github.com/BurnsD