# Regex-Tutorial

In this tutorial, we will be taking a brief look into what Regex (regular expressions) are and how they work. While regular expressions may seem to be overwhelming at first glance,
just like with any language, they can be broken down into its most simple parts and easily understood.

## Summary

Regex (short for regular expression) is a string of text that allows you to create search patterns that match, manage, and locate text. An example code snippet of regex shows as following:
* A regular expression used to match an e-mail address
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Regular expressions can also be used from the command line and within text-editors to find text within a file. 

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

### Anchors

^ asserts position at start of the string
$  asserts position at the end of the string, or before the line terminator right at the end of the string (if any)
The caret ^ defines the beginning of the string. The dollar sign $ defines the end of the string.

The pattern is forced to become anchored at the start of the search or at the position of the last successful match.
### Quantifiers

Quantifiers indicate that the preceding token must be matched a certain number of times. A quantifire can be greedy or lazy that is explained below.
 example The plus + will match one or more of the preceding token. In this case it will attempt to match [a-z0-9_\.-]. Two numbers with curly brackets {2,6} will match from two to six from the previous token. In this case it will match [a-z\.]. As further examples: {2} would match exactly two, and {2,} would match two or more.


  
### OR operator
| Acts like a boolean OR. Matches the expression before or after the |. It can operate within a group, or on a whole expression. The patterns will be tested in order. Just as in java will match either set of characters. It will look for this OR that.

### Character classes
Character classes match a character from a specific set. There are a number of predefined character classes and you can also define your own sets.
A character set [ABC] will match any single character in the set. In our example [a-z0-9_\.-] will match any character within the square brackets. A range [A-Z] will match a character included between the two characters separated by the hyphen. In our example a-z will match any character between a and z. 0-9 will match any character between zero and nine.


### Flags
Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression.
example
Ignore case (i) will make the entire expression case-sensitive.
Global search (g) will store the index of the last match.
Multiline (m) will cause the beginning and end anchors to match the start and end of a line instead of the whole string.
Unicode (u) allows extended unicode escapes in the form \x{FFFFF}.
Sticky (y) will only match from its last index position and ignores the global search flag.
Dotall (s0 causes dot (.) to match any character.

### Grouping and Capturing
(ABC) Capturing groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
(?<name>ABC) named capturing group captures groups of a specific name.
\1 is a numeric Referance
(?:ABC) Groups multiple tokens together without creating a capture group.
  example
   there are three capturing groups: ([a-z0-9_\.-]+), ([\da-z\.-]+), ([a-z\.]{2,6}). This allows for a substring to be verified before @, another one before \., and the final one for the domain extension of the email address.

### Bracket Expressions
A bracket expression enclosed in square brackets is a regular expression that matches a single character, or collating element. If the initial character is a circumflex ^, then this bracket expression is complemented.
### Greedy and Lazy Match
'Greedy' means matching the longest possible string. A Greedy quantifier tells the engine to match as many instances of its quantified token or subpattern as possible. This behavior is called greedy.

'Lazy' means matching the shortest possible string. A lazy quantifier tells the engine to match as few of the quantified tokens as needed. As you'll see in the table below, a regular quantifier is made lazy by appending a ? question mark to it.
### Boundaries
The \b is an anchor like the caret and the dollar sign. It matches at a position that is called a “word boundary”. This match is zero-length.

Characters that are matched by the short-hand character class \w are the characters that are treated as word characters by word boundaries.
### Back-references
Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag.
### Look-ahead and Look-behind
(?=ABC) is a postive lookahead and it matches a group after the main expression without including it in the result.

(?!ABC) is a negitive lookahead and it specifies a group that can not match after the main expression (if it matches, the result is discarded)

(?<=ABC>) is a postive lookbehind and matches a group before the main expression without including it in the result.

(?<!ABC) is a negitive lookbehind and Specifies a group that can not match before the main expression (if it matches, the result is discarded).

Lookaheads and lookbehinds forces the main expressions to be what you have defined it as. Without it being exactly what it is it will not be accepted as a valid input.



^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$
/
^ asserts position at start of the string
1st Capturing Group ([a-z0-9_\.-]+)
Match a single character present in the list below [a-z0-9_\.-]
+ matches the previous token between one and unlimited times, as many times as possible, giving back as needed (greedy)
a-z matches a single character in the range between a (index 97) and z (index 122) (case sensitive)
0-9 matches a single character in the range between 0 (index 48) and 9 (index 57) (case sensitive)
_ matches the character _ with index 9510 (5F16 or 1378) literally (case sensitive)
\. matches the character . with index 4610 (2E16 or 568) literally (case sensitive)
- matches the character - with index 4510 (2D16 or 558) literally (case sensitive)
@ matches the character @ with index 6410 (4016 or 1008) literally (case sensitive)
2nd Capturing Group ([\da-z\.-]+)
\. matches the character . with index 4610 (2E16 or 568) literally (case sensitive)
3rd Capturing Group ([a-z\.]{2,6})
$ asserts position at the end of the string, or before the line terminator right at the end of the string (if any)