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

Anchors, "^" and "$", are special characters used to match specific words at the beginning and end of the string respectively. This is used to further find specific matches. If both are used in the Regex such as ^Disney LandS it will match to the exact string. Here are a few examples of how these anchors work: 

^Match Me = find all strings that start with the word 'Match'
Match Me$ = find all strings that end with the word 'Me'
^Match Me$ = find this exact string

### Quantifiers

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
