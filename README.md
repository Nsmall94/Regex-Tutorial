# Regex-Tutorial

## User Story
AS A web development student
I WANT a tutorial explaining a specific regex
SO THAT I can understand the search pattern the regex defines

## Summary

A Regex or regular expression is a sequence of characters that define a search pattern. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings. It also looks for input validations. It is a technique commonly developed in theoretical computer science.
An example of a Regex is 
\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$

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
* `^abc$`	-^start / $end of the string
    * `^` Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled.This matches a position, not a character.
    * `$` Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.

* `\b\B`	-word, not-word boundary
    * `\b` Matches a word boundary position between a word character and non-word character or position (start / end of string). See the word character class (w) for more info.
    * `\B` Matches any position that is not a word boundary. This matches a position, not a character.
    * See Boundaries for more detailed Information

### Quantifiers
Quantifiers indicate that the preceding token must be matched a certain number of times. A quantifire can be greedy or lazy that is explained below.

* `a*a+a?`	-0 or more, 1 or more, 0 or 1
    * "+" Matches 1 or more of the preceding token.
    * "*" Matches 0 or more of the preceding token.
    * "?" Matches 0 or 1 of the preceding token, effectively making it optional.
    * "?" Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.

### OR Operator
* `|` Acts like a boolean OR. Matches the expression before or after the |.
It can operate within a group, or on a whole expression. The patterns will be tested in order. Just as in java will match either set of characters. It will look for this OR that.

### Character Classes
Character classes match a character from a specific set. There are a number of predefined character classes and you can also define your own sets.

* `[ABC]` Characters inside brakets will match any character in the set.
* `[^ABC]` Adding a caret will match any character that is not in the set.
* `[A-Z]` Add a dash between two characters will select a Range.
* `.` Will Match any characters expect linebreaks. Its like a wildcard and will accpet any input.
* `[\s\S]` A character set that can be used to match any character, including line breaks, without the dotall flag. An alternative is [^] carrot in brackets, but it is not supported in all browsers.
* `\w` Matches any word character (alphanumeric & underscore). Only matches low-ascii characters (no accented or non-roman characters).
* `\W` Matches any character that is not a word character (alphanumeric & underscore).
* `\d` Matches any digit character (0-9)
* `\p` Matches a character in the specified unicode category.

### Flags
Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression.

* `i` Ignores case
* `g` Global search retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.
* `m` Multiline flag When the multiline flag is enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.
* `u` Unicode
* `y` The expression will only match from its lastIndex position and ignores the global (g) flag if set. Because each search in RegExr is discrete, this flag has no further impact on the displayed results.
* `s` Dot (.) will match any character, including newline.

### Grouping and Capturing
bby using () you can group a part of regular expression, By doing this you can apply a quantifier.
an example of this would be (ABC)

### Bracket Expressions
A bracket expression enclosed in square brackets is a regular expression that matches a single character, or collating element. If the initial character is a circumflex ^, then this bracket expression is complemented.

### Greedy and Lazy Match
"Greedy" means matching the longest possible string
"Lazy" means matching the shortest possible string

### Boundaries
`\b` is used as an anchor used to match the position of a word, also known as a word boundry.
An example of use would '\bword\b' this is because '\b' allows you to perform a "whole words only" search using a regular expression 

### Back-references
Backreferences match the same text as previously matched by a capturing group.

### Look-ahead and Look-behind
Lookaheads and lookbehinds forces the main expressions to be what you have defined it as. Without it being exactly what it is it will not be accepted as a valid input.

## Gist Link 
https://gist.github.com/Nsmall94/52d662ed73c282284b852a8d46661a0b

## Author
Nick Small

### Sources used
https://www.regular-expressions.info/tutorial.html