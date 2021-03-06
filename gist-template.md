# Regex Tutorial

This tutorial is to touch on Regex (Regular Expressions) and how it works. Regular Expressions will be deconstructed so that we may understand them. In this tutorial you will find examples and explanations for these expressions.

## Summary

Regex is a string of text used to create patterns to locate and match text.

Here is an example of one such Regex: 

/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

This will look for any and all characters 'a' through 'z', will include '\', '.', and '-'. This regex is looking to match with URLs.

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

^Match Me = find all strings that start with the word 'Match'.

Match Me$ = find all strings that end with the word 'Me'.

^Match Me$ = find this exact string.

### Quantifiers

Qunatifiers are specific characters ({}, (), *, +, ?) within the regular expression that signifies how many times a character or group of characters must be present within the string in order to match.

*    matches a string containing the first character followed by nothing or more of the last character
+    matches a string containing the first character followed by one or more of the last character until separated from another word by a white space
?     matches a string conataining the first character followed by nothing or one of the last character
{}} matches a string containing the first character followed by how ever many the number in the brackets of the last character in the string


Example Expressions:

String = 'what how who where when why'

([w])\d* = would match to 'what who where when why' accepting the 'w' and all characters after it but would only match to the 'w' in 'how' leaving out the 'h' and 'o'.

([w])\d+ = would match to 'what who where when why' accepting the 'w' and all characters after it but would completely ignore 'how' in its entirety.

([w])\d? = would match to only the 'wh' in the words 'what who where when why' and the 'w' in 'how but ignore all the other characters.

([w])\w{3} = would match to 'what where when' accepting the 'w' and all characters after but would ignore 'how', 'who' and 'why' because they only contain {2} or less characters after the 'w'.

### OR Operator

OR Operators match to a choice of regular expressions when the character representing the OR Operation, '|' and '[]' are placed between any two characters in the  expression. The result is a combination of the two characters to match.

Example Expressions:

h(i|s)  matches a string that has 'h' followed by an 'i' or a 'e' and also captures those characters.

h[is]   matches a string that has 'h' without capturing 'i' or 'e'.

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

Example Expressions:

([a-z])\w matches to a single character in the range from a-z in the string.

([0-9])\d matches to a single digit in the range of 0-9 found in the string.

([a-z])\s matches to a single white space in the string.

### Flags

Flags are additional search parameters what when added to an expression adjusts the scope of the search and in some cases what the search is looking for. The flags use the following characters: 'g', 'm', 'i', 'u', 's', and 'y', with each one adjusting the search of the expression in a unique way. These flags can be used together but, not all browsers support some of them, and certain ones cancel out other flags.

Examples:

/g = Global, which makes the expression search for a match through out the entire string instead of ending the search after finding the first match.

/m = Multi-line, which makes the expression utilize the Anchors to match the start and end of a line omitting the rest of the string.

/i = Insensitive, which removes case-sensitivity from the expression so it will accept characters of both upper and lower case.

/u = Unicode, which makes the expressions search for a Unicode escape sequence in the string such as [FFFFF]. It is worth mentioning that not all browsers support this feature of regex.

s/ = Single line/Dotall, which makes the expression match any character even on a new line. Again, it is worth mentioning that not all browsers support this feature of regex.

y/ = Sticky, which makes the expression match only from its last index position and ignore the Global flag. Again, not all browsers support this feature of regex.

Example Expressions:

String Line 1 = 'what how who where when why'

String Line 2 = 'why how who where when what'

([a-z])/g  = matches all characters that are 'a' through 'z' throughout the entire string and including those on the next line.

^(what)/m = matches the first 'what' at the start String line 1 but, (what)$/m will match with the last 'what' at the end of String line 2.

(what)/i = matches to 'what' no matter if it is 'what', 'What', or 'wHat' in the string.

### Grouping and Capturing

Grouping matches a characters of a string so that it is matched as a block.

Example Expressions:

() = is use to capture a group of characters in the string.

(?:) = disables capturing the group of selected characters in the string.

(?<>) =  names the group of selected characters.

### Bracket Expressions

Bracket Expressions utilize `[]` to match any single character or a to create a range of characters to match to within the brackets. 
Interestingly the anchor '^' when used in the brackets first will make it so that the expression tries to match with any character not in the brackets. 

Example Expressions:

([a-z])/g = matches to characters in the range of 'a' to 'z' within the string.

([^a-d])/g = matches to any characters not in the range of 'a' to 'd' within the string.

### Greedy and Lazy Match

Greedy and Lazy matching utilize quantifiers that widen the scope of the search of the match through the text as far as possible.

Example:

* + {} are the quanitifers used to initiate a Greedy or Lazy Match

Example Expressions:

(w+?) = matches the 'w' character as few times as possible throughout the string in a Lazy Match.

### Boundaries

Boundaries are the spaces between characters in the string and consist of two specific characters '\b' and '\B'.

(what)\b = Matches a word boundary position between a word character and non-word character or position.

(what)\B = Matches a position that is not a word boundary.

### Back-references

When grouping is used the captured group is saved in memory for and back-referencing is the action of using these matches.

Example Expression:

([what])\1 = Matches the same text that was matched by the first capturing group.

([what])([who])\2\1 = Matches to the same text that was matched by the second and first capturing groups.

### Look-ahead and Look-behind

Look-ahead and Look-behind use the anchors '^' and '$' to specifically match with characters and then ends the search. The result will be either 'Match' or 'No Match'. Look-ahead and Look-behind does not capture characters but just determines if a match has occured or not.

Example Expressions:

w(?=h) = matches a 'w' as long as it is followed by 'h' but, 'h' won't be included in the match.

(?<=h)o = matches an 'o' as long as it is preceded by an 'h' but, 'h' won't be included in the match.

## Author

Austin Swebilius is a future Front End Web Developer currently attending the Fullstack Development Coding Boot Camp at the University of Central Florida. Here is his Git Hub: https://gist.github.com/Aswebilius/18267b1ded7f328d0b8d6ca42f180de7

