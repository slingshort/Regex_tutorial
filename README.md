# Regex Tutorial for Email Matching

This tutorial will be a breakdown of the components of this email address matching regex:
``` javascript
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ 
```

A regex, otherwise known as a regular expression is are javascript objects which are patterns used to match strings. They are commonly used as validators to limit user input or to sort easily through data.

## Breakdown of Components
 - [Anchors](#anchors)
 - [Bracket Exressions](#bracket-expressions)
 - [Quantifiers](#quantifiers)
 - [Grouping Constructs](#grouping-constructs)
 - [Character Escapes](#character-escapes)
 - [Character Classes](#character-classes)

## Anchors
The ```^``` character signifies the begeinning of the regex string and the ```$``` character signifies the end of the regex string. That is to say a regex expression is always contained within the anchors ```^``` and ```$```. Because the regex is considered as a literal, it also must be wrapped in back-slash characters (```/```).

## Bracket Expressions
In a regex, anything inside a set of square brackets (```[]```) contains the patterns we want to match. Looking at the first part regex above:
```javascript
[a-z0-9_/.-]
```
```[a-z]``` represents all letters from a-z, ```[0-9]``` represents numbers from 0-9, and the string proceeding these ranges ```(_/.-)``` represents individual characters that are accepted in the match. These separate components of the given bracket expression are conventionally compiled in such order, hence the expression above. At this point, we are just testing for any, not necessarily all.

## Quantifiers
Quantifiers proceed bracket expressions to set the limits of the string in which the regex matches.
In the above regex there are two quantifiers:
- ```+``` which matches the pattern one or more times
- ```{n,x}``` which matches the pattern a minimum of ```n``` times and a maximum of ```x``` times.
That is to say that for:
```javascript
[a-z0-9_\.-]+
```
and 
```javascript
[\da-z\.-]+
```
We are matching for a string that contains 1 or more characters that match the bracket expression. And for:
```javascript
[a-z\.]{2,6}
```
we are matching for a string that contains 3-6 characters.

## Grouping Constructs
In a regex, parentheses (```()```) are used for separation of concerns. In the above regex, each separate matching pattern is contained within parentheses and sepearted

## Chracter Escapes
In a regex, the backslash (```\```) character 'escpates' a charachter that would otherwise be interpreted literally. For example in the above regex. A ```.``` is usually used to match any character except a newline character (```\n```), so this is 'escaped' by the backslash character that preceeds it. ```@``` does is not a special character in regex, therefore does not need to be preceeded by a backslash. 

Special characters only old significance OUTSIDE of bracket expressions. 


## Character Classes
Character classes are used to define a set of common characters in an input string. In the second part of the above regex:
```javascript
[\da-z\.-]+
```
```\d``` is used to match any Arabic numeral digit. It is equivalent to the bracket expression ```[0-9]``` which was stated in the first part of the regex.