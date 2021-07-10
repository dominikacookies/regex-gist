# Regular Expressions : Email format

This document outlines main regular expression components using an expression for an email as an example.

## Summary

Throughout this document, as I describe regex components I will be referring to on that verifies email formatting and looks like so:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` .

## Table of Contents

  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
    - [Grouping Constructs](#grouping-constructs)
    - [Bracket Expressions](#bracket-expressions)
    - [Character Classes](#character-classes)
    - [The OR Operator](#the-or-operator)
    - [Flags](#flags)
    - [Character Escapes](#character-escapes)
  - [Author](#author)

## Regex Components

### Anchors
Anchors state at which position the regex match should occur when analysing your string. There are several types of anchors, the key ones to consider include:
- `^` : specifies that the match should occur at the biggining of the string
- `$` : specifies that the match should occur at the end of the string.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

If we take our email format regex above as an example you can see that it requires characters to be included at the beginning of the string, and between 2 - 6 letters

### Quantifiers
Specify how many matches should be made. Here:
`([a-z0-9_\.-]+)`
the quantifier `+` is used to dictate that one or more characters from the preceeding token should match.

There are different types of quantifiers, take a look:

*	Match zero or more times.
+	Match one or more times.
?	Match zero or one time.
{ n }	Match exactly n times.
{ n ,}	Match at least n times.
{ n , m }	Match from n to m times.

Taking the last one as an example, in our expression we specify that the end of the string 
`([a-z\.]{2,6})`
should contain between 2 and 6 characters.

### Grouping Constructs
Grouping constructs are , like the name suggests, used to make groups within a regex expression such as subexpressions that are defined using parenthesis.
In our email format example, 
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
we use parenthesesis to specify the different places in which a particular regex match (subexpression) should happen, for example that at the end of the string there should be 2-6 letters or a period `([a-z\.]{2,6})$` .

### Bracket Expressions
Bracket expressions specify that the characters used inside should result in a match, unless, there is a carat `^` at the beginning of the bracket, in which case it means that the characters that follow should NOT result in a match.
Here: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

`[a-z0-9_\.-]` means that a match will be made if:
- the string features a letter
- the string features a number
- the string features any of the following special characters: `_.-`

### Character Classes
Character classes are very similar to bracket expressions in that they specify what in string should result in a match. Here are a few examples of character classes:

.—Matches any character except the newline character (\n)

\d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

\w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].

\s—Matches a single whitespace character, including tabs and line breaks

### The OR Operator
The OR operator `|` is used to specify that the condition/character perceding or following it should result in a match, as an example, instead of:
`[0-9]` we could write:
`[0|1|2|3|4|5|6|7|8|9]`

### Flags
Flags are placed at the end of a regex to specify additional functionality or limits. The following 6 flags exist:
- i : ignore casing
- g: global aka search fo all occurances
- s: make `.` match newlines as well
- m: multiline - `^` and `$` match the begging and end of every line instead of whole string
- y: makes the expression start searching from a specified index
- u: matches 32-bit characters also

### Character Escapes
Some characters have a special meaning within regular expressions. To avoid them being interpreted in that way we can user the backlash which "escapes characters". 
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Here, in the first bracket expression, we escape the dot so that instead of saying: accept any one character except a new line we tell it to accept a dot.

## Author

This has been written by Dominika Pietrzak.
