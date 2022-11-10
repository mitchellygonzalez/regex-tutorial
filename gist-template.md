# Regex Tutorial
Below you'll find an explanation to a specific regex. In addition, I have provided the definitions and some examples of different regex components that you may refer back to as needed. Some are not utilized in the specific regex I will be referring to, but serve to help you gain a better understanding of Javascript regular expressions aka regex.

## Summary
A regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions may be used to find specific patterns of characters within a string, or rather, to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.



Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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
Anchors assert that the engine's current position in the string matches a specific location. They don't match a character persay, but rather match a position before or after certain characters. It is also very efficient. If we tell the engine that we would like to find a complex pattern in a specific location, it does not spend time looking elsewhere, it will simply look in that location. 
- Examples:
    - ^ - matches the beginning of the text 
    - $ - matches the end of the text


### Quantifiers
Quantifiers specify the number of times a character, group, or character class must be present in the input in order for a match to be found. Below we'll distinguish between "Greedy" and "Lazy" quantifiers. 
- Examples:
    - x* - matches the preciding item "x", 0 or more times
    - x+ - matches the preciding item "x", 1 or more times
    - x? - matches the preciding item "x" 0 or 1 time. 
    - x{n} - where "n" is a positive integer, matches at least "n" occurences of the preciding item "x".
    - x{n,} - where "n is a positive interger, matches at least "n" occurences of the preciding item "x"
    - x{n,m} - where "n" is 0 or a positive integer, "m" is a positive integer, and m is greater than n, matches at least "n" and at most "m" occurences of the preciding item 

Greedy vs Lazy:
Quantifiers that include * an + are considered "greedy" indicating that they prefer to match up with as many characters in the string as possible. Those that include a ? after the quantifier indicate that it is considered a lazy, because it will match as few of the quantifiers as possible to produce a result.


### OR Operator
A common example of an OR operator is the | symbol. This tells the regex engine to match between two or several options. 
- Examples:
    - 1 | one - (meaning 1 or one)
    - 1 | 2 | 3 - (meaning 1 or 2 or 3)


### Character Classes
This tells the engine to match as little as one character by simply placing the desired characters inside of a bracket, and utilizing a - character inside the bracket to indicate a range. We may also incorporate more than one range. The order does not matter. 
- Examples:
    - [0-5] -  0 through 5
    - [5-9] -  5 through 9
    - [a-c] -  a through c
    - [0-5a-c] - a hexadecimal digit
- Character classes themselves...
    - ^ searches for anything not within the set
    - - a dash sets a range
    - . a period will match anything other than linebreaks
    - \d matches a single digit character
    - \D matchhes a single character that is not a digit
    - \w matches a single word character
    - \W matches a single charatcer is not a word character/letter


### Flags
Flags are single lowercase letters that sybolize different functionalities, which modify the behavior of the engine's search. There are 6 flags in Javascript and each of them affect the search
- Examples:
    - i - it will be case-insensitive
    - g - meaning it's global, and therefore makes it search all matches, otherwise only the first match would be returned
    - s - dotall, meaning the . will match newline character \n
    - u - unicode, meaning it will enable the correct processing of surrogate pairs
    - y - aka "sticky" mode. Indicating the expression will start from the index indicatied within the lastIndex property
    - m - makes the symbols ^ and $ match the beginning and ending of every line rather than the beginning and ending of the entire string


### Grouping and Capturing
This instance gives us the ability to refer to a certain pattern that may occur multiple times. Rather than repeating a regex, it's best to group and capture.
- Example:
    - () using enclosed parentheses are useful in grouping together what we would like to find within repeated substrings. Utilizing this method is referred to as a "capturing groups"


### Bracket Expressions
Using enclosed brackets --somewhat similar to parentheses-- allow us to refer to a set of characters to match. Anything can be matched. It can also provide non-matching characters by utilizing a ^ symbol
- Examples:
    - [abc] will match a, b, or c
    - [^abc] will match all characters except a, b, or c


### Greedy and Lazy Match
Greedy Match: will attempt to search the longest possible string. It will match as many of those requested characters/patterns as possible.

Lazy Match: will attempt to search the shortest possible string
- Example: 
    - The ? character makes it a "lazy" search, aka shortest possible. 


### Boundaries
Boundaries match a position referred to as a "word boundary. Word boundaries can be positioned before the first character inside a string if its a word character. It can also be after the last character in a string if the last character is a word character. Lastly, it can be between two characters in a string if one is a word character, but the other is not. 
- Example: 
    - \b is the symbol for a word boundary. You may place it in the positions described above. 


### Back-references
Back-references refer to a previous part of the matched regular expression. It includs a \ and a single digit.
- Example:
    - \1 is an example of a back-reference. This would back reference to to the first group.
    - $1 is another backreference example, it is the same as using the previous example \1.
    - \2 and $2 would both refer back to the second captured group.


### Look-ahead and Look-behind
Below are examples of positive and negative look-aheads:
- Positive lookahead: it will match 'x' when followed by 'y'
    - Example: x(?=y)
- Negative lookahead: it will match 'x' when it's not followed by 'y'
    - Example: x(?=!y)

Below are examples of positive and negative look-behinds:
- Positive lookbehind: it will consider the same pattern as a positive lookahead, however the pattern will be considered after the matching part.
    - Example: x(?<=y)
- Negative lookbehind: it will consider the same pattern as a negative lookahead, however the pattern will be considered before the matching part.
    - Example: x(?<!y)

## Author
My name is Mitchell Y. Gonzalez, I'm a student at the Columbia University Coding bootcamp. If you have any questions about this gist, you may email me at mitchellygonzalez@gmail.com. 

My Github is https://github.com/mitchellygonzalez