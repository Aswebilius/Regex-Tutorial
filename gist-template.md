# Regex Tutorial

This tutorial is to touch on Regex (Regular Expressions) and how it works. Regular Expressions will be deconstructed so that we may understand them. In this tutorial you will find examples and explanations for these expressions.

## Summary

Regex is a string of text used to create patterns to locate and match text.

Here is an example of one such Regex: 

/^[a-z0-9_-]{5,16}$/g

This will look for text that is 5 to 16 characters long, contains numbers from 0-9, and can contain hyphens and underscores.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors, "^" and "$", are special characters used to match specific words at the beginning and end of the string respectively. This is used to further find specific matches. If both are used in the Regex such as ^Disney Land$ it will match to the exact string. Here are a few examples of how these anchors work: 

^Match Me = find all strings that start with the word 'Match'
Match Me$ = find all strings that end with the word 'Me'
^Match Me$ = find this exact string

### Quantifiers

Qunatifiers are specific characters ({}, (), *, +, ?) within the regular expression that signifies how many times a character or group of characters must be present within the string in order to match.

*    matches a string containing the first character followed by nothing or more of the last character
+    matches a string containing the first character followed by one or more of the last character until separated from another word by a white space
?     matches a string conataining the first character followed by nothing or one of the last character
{}} matches a string containing the first character followed by how ever many the number in the brackets of the last character in the string


Examples:

String = 'what how who where when why'

([w])\d* = would match to 'what who where when why' accepting the 'w' and all characters after it but would only match to the 'w' in 'how' leaving out the 'h' and 'o'.

([w])\d+ = would match to 'what who where when why' accepting the 'w' and all characters after it but would completely ignore 'how' in its entirety.

([w])\d? = would match to only the 'wh' in the words 'what who where when why' and the 'w' in 'how but ignore all the other characters.

([w])\w{3} = would match to 'what where when' accepting the 'w' and all characters after but would ignore 'how', 'who' and 'why' because they only contain {2} or less characters after the 'w'.

### OR Operator



### Character Classes

Character Classes can be thought of as identifiers that tell the engine to match only one out multiple unique character types like digits, words, and even just vacant white space.

Examples of these Character Classes are as follow:

.       will match any character
\d     will match a single digit 0-9
\w    will match a single a character from a-z
\s     will match with white space
\D    will match with any single non-digit character
\W   will match with any single non-character that is a-z
\S    will match with a single non-blank white space

Examples:
([a-z])\w matches to a single character in the range from a-z in the string.
([0-9])\d matches to a single digit in the range of 0-9 found in the string.
([a-z])\s matches to a single white space in the string.

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

Austin Swebilius is a future Front End Web Developer currently attending the Fullstack Development Coding Boot Camp at the University of Central Florida. Here is his Git Hub: 
