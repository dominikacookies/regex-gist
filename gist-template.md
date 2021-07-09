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

` *	Match zero or more times.
+	Match one or more times.
?	Match zero or one time.
{ n }	Match exactly n times.
{ n ,}	Match at least n times.
{ n , m }	Match from n to m times.`

### Grouping Constructs
Grouping constructs are , like the name suggests, used to make groups within a regex expression such as subexpressions that are defined using parenthesis.
In our email format example, 
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
we use parenthesesis to specify the different places in which a particular regex match (subexpression) should happen, for example that at the end of the string there should be 2-6 letters or a period `([a-z\.]{2,6})$` .

### Bracket Expressions


### Character Classes
Character classes set the groups of characters that should result in a match. Going back to our example:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

`[a-z0-9_\.-]` means that a match will be made if:
- the string features a letter
- the string features a number
- the string features any of the following special characters: `_.-`

### The OR Operator

### Flags

### Character Escapes

## Author

This has been written by Dominika Pietrzak
