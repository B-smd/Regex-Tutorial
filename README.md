# Regex-Tutorial

Regular Expressions (shortened as Regex) are patterns used to matched character combinations in strings.
This tutorial will help you to understand and define the sequence of special characters to verify 
a search pattern in text.

## Summary

An example code snippet of regex shows as following:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This regular expression can be used to verify that user input is a valid email address. 
I have tested 3 email address: `davidbrown@gmail.com`, `angelamarkle8833@yahoo.com` 
and `yonathanandrew@kpnplanet.nl`, all of them are matches.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors don't match any character, they match a position before, after or between characters.
The caret `^` is the starting anchor, and the dollar sign `$` is the end anchor.

### Quantifiers

The quantifiers is a range of numbers place between two curly brackets ({}). 
On the regex example above, before the end of the expression `$` is placed {2,6},
this quantifier states that each section of the string needs to be a minimum of 2 characters
long and a maximum length of 6 characters.
Examples of quantifiers:
- `*` --> 0 or more of preceding characters
- `+` --> 1 or more of preceding characters
- `?` --> 0 or 1 of preceding characters
- `{min, max}` for example you can put {2, 6}, min 2 and max 6 of preceding characters
- `{n}` you can put any number of preceding characters

### Grouping Constructs

Another example code snippet of regex shows as following:

`(<a href=')(.*?)('>)(.*?)(</a>)`

Matched `<a href='http://wwww.regex.tutorial.aus/Contact.bsmd'>contact form</a>`
It uses five grouped subexpressions each within parentheses, to perform the pattern matching.
Explanation of the purpose of subexpression:
- `(a href=')` --> Find the literal text, "<a href='",identifying the starting part of an anchor tag, up to the starting position of the target URL.
- `(.*?)` --> Matches a series of consecutive characters in a lazy manner. This group matches the URL defined within an anchor.
- `('>)` --> Finds the two literal characters that close the anchor's opening tag.
- `(.*?)` --> This group finds the text between the anchor's opening and closing tag.
- `(</a>)` --> Matches the end tag for the anchor.

### Bracket Expressions

A bracket expression matches any character among those listed between the opening and closing square brackets `[]`.
However if we put the caret `^` before, it will match any character except: the character we put in the bracket.
Examples of using the bracket:
- `[abc]` --> Matches words only containing a, b or c.
- `[^abc]` --> Matches any character except: a, b or c.
- `[a-z]` --> Matches any character in the range: a-z.
- `[^a-z]` --> Matches any character not in the range: a-z.
- `[a-zA-Z0-9]` --> Matches any character in the range: a-z (lowercase letters), A-Z (uppercase letters) and 0-9 (numbers).

### Character Classes 

A character class is also called a character set allows you to match any symbol from a certain character set. 
Suppose that you have a phone number like this:
                `+62-(413)-344-9870` and you want to turn it into a plain number: `624133449870`. 
Character classes in regular expressions can help you to do this. With the digit character class `\d` which matches any
single digit. 
The most commonly used character classes are:
- `\d` --> Matches any digit from 0-9
- `\s` --> Match a single whitespace
- `\w` --> Matches A_Za-z0-9_
- `.` --> Dot is matches any single character whatsoever

### The OR Operator

Alternation is the term in regular expression that is actually a simple "OR". In a regular expression it is denoted with
a vertical line character`|`. Indicates that match can be one of the two terms on either side of the pipe.
Examples of using the pipe `|`;
- `roses|orchid` --> Matches the words: "roses" or "orchid"
- `((part1|part2)|(part1, part2))$` --> Matches the words: "part1" or "part2" or both "part1, part2"

### Flags

A flag is an optional parameter to a regex that modifies it is behaviour of searching. There are 6 flags 
(i, g, m, s, y and u) using a single lowercase alphabetic character, each serving a different purpose.
But for the flags: "s, y and u", they are not every browser supported. The three flags mostly every browser supported:
`g`lobal, case `i`nsentive and `m`ultiline.
Examples of using flag:
- `/roses/i` --> Matches "roses" or "ROSES"
- `/roses/g` --> Matches all "roses" for the pattern, not just stop at the first one
- `/^A.+/m` --> Matches `A(roses\n ROSES)\n(a beautiful/\n FLOWER)\n indeed`, The `^` character matches the start of every line, because of the `m` flag. Altogether the expression looks for an `A` at the beginning of every line and if found, it matches the whole line, till the end.
  
### Character Escapes

All of the character escapes are defined in a regular expression using a backslash `\` followed by one or more letters,
numbers or symbols. A common way to escape any single-byte character in a regex is to use 'hex escaping'.
For example, it can be specified in hexadecimal:
- `\x61` --> Match "a"
- `\x09` --> Match "a tab" character.
There are a few other commonly supported escape sequences that will specify individual ASCII characters.
These are: `\r` (carriage return), `\n` (newline), `\v` (vertical tab), and `\f` (form feed).
If you try to use an escape sequence like `\h`, `\i`, or `\j`, you will just end up with the same literal character as 
if you hadn't escaped it at all. This is because most regular expression engines will just ignore the backlash if it
comes before a character that doesn't have any special escaped meaning. But if you use the `\d` escape sequence, it will 
represent 'any single digit character from 0 to 9'.

## Author

Bambang Sugiarto Micha Djaja, became an architect graduate from The Institut Teknologi Sepuluh Nopember 
(abbreviated as ITS), Surabaya, Indonesia, on the 1st November, 1980. 
He is an entrepreneur :
- 12/1984 - 11/2000, PT SBPI (Surya Bangun Persada Indah) - Construction Company, Surabaya, Indonesia.
- 06/1991 - 11/2000, Profa Design - Interior and Furniture Company, Jakarta, Indonesia.
- 10/2002 - 08/2011, Midpower Holdings Pty Ltd - Ditributor, Perth, Australia.
- 10/2013 - 10/2018, Midpower Holdings Pty Ltd - Coffe Shop, Perth, Australia.
- 10/2018 - 01/2022, Midpower Holdings Pty Ltd - Passenger Transport Vehicle, Perth, Australia.
Because of Covid19, He want to change his company to do a Web Developer, so He started learning web development at
Coding Bootcamp The University of Western Australia (UWA) on the 7th February 2022 and He will receive his certificate 
in August 2022. He has enjoyed learning a variety of things.

GitHub Profile: https://github.com/B-smd

GitHub Gist: https://gist.github.com/b6096a7c2a8847dd39ff00506f2002fa.git