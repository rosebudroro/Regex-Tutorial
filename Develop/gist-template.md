# Regex Tutorial

Regular expressions, also known as regex, are a series of special characters that define a search pattern. Regex can replace several lines of programming code as it can search and match text. It is universal as it is supported in all scripting languages such as Javascript, Python, C++ etc. 

## Summary

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

The code above is a search pattern for matching an email. It will check to see if a string fulfills the requirements described in the regex above. The pattern is enclosed within forward slashes `/` because a regex is considered a literal. We will break each section down in detail.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)


## Regex Components

### Anchors

The position anchors ^ and $ are considered anchors.

The ^ anchor signifies a string that begins with the characters that follow it.
The $ anchor signifies a string that ends with the characters that precede it. 

### Quantifiers
Quantifiers sets the limits of the string that your regex matches or an individual section of that strong.

`*` Matches the pattern zero or more times
`+` Matches the pattern one or more times
`?` Matches the pattern zero or one time
`{ }`  Curly brackets can provide ways to set limits for a match:
	{ n } - matches the pattern exactly n number of times
	{ n, } - matches the pattern at least n number of times
	{ n, x } - matches the pattern from a minimum of n number of times to a maximum of x number of times

So in our email regex:

`[ ] +`     means it matches the pattern one or more times.
`{2,6}`     means it can occur at least 2 times but to a maximum of 6 times.


### Character Classes
A character class in a regex defines a set of characters. They provide a concise way to match a single character.

[  ] Matches any single character within the Brackets
[A-Z ] Matches any Capital Letter from A through Capital Letter Z 
[a-z] Matches any lowercase letter from a through lowercase letter z
[0-9] Matches any single digit from 0 to 9

Character Ranges
Special Character Escaping, some characters have predetermined special meaning so to match these specific characters, you need to escape them with a blackslash.

In our expression `(a-z0-9_\.-)`  ` \.- ` is stating that we are including all lowercase letters from a through z, all digits from 0 to 9, an underscore and as well as including the special characters of a period and a hyphen in our match.

Important note, with the classes above, we don’t need to include every character, it can meet any character that is included in the class and can be in any order.

Shorthand Character Classes
Regular expressions that are shorthand notation for commonly used characters:

`\d` is a character classes that is equivalent to the bracket expression [0-9]
`\w` represents any word character that is equivalent to [a-zA-Z0-9_]
`\s`represents any white space character (space, tab, newline etc)


### Grouping and Capturing

Focuses on portions of a regex pattern with parentheses so actions like quantifiers can be applied to what is inside the parentheses. In the expression `/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/` there are three groups, all seperated by parenthesis.
Grouping and Capturing are techniques used to extract specific parts of the pattern.
Grouping uses parenthesis `( )` to enclose a portion of the pattern so you can apply quantifiers and modifiers to that specific group of characters. Each section within parenthesis is known as a subexpression.

Grouping constructs have two primary categories: capturing and non-capturing. Capturing groups are numbered based on the order of the opening parenthesis. Typically, there are methods or functions provided to retrieve the captured groups by name or index.

In our email regex, there are 3 grouping groups.

`([a-z0-9_.-]+)`
`([\da-a.-]+)`
`([a-z]{2,6})`

### Bracket Expressions

`[a-z0-9_\.-]`

Bracket expressions are anything inside a set of square brackets that we want to match.
When they use a hyphen, it indicates a range of those possible characters, in this case. All the lowercase letters from a-z. (remember regex is case sensitive)
Essentially, `[abcdefghijklmnopqrstuvwxyz]` and `[a-z]` are the same thing. 

So in matching our email, it will look for

[a-z] This string can contain any lowercase letter between a-z.
[0-9] The string can contain any number between 0-9.
[ _ ] The string can contain an underscore.
[ \.-]



In conclusion, the regular expression pattern is checking for an email address by ensuring it consists of a username that contains any lowercase letter from a through z, any digit from 0-9, and underscore, period and hyphen followed by the @ symbol then a domain name that consists of any digit from 0-9, any lowercase letter from a through z, a period and a hyphen followed by a “ . “ and a TLD that is any lowercase letter from a through z, a period and that is between 2 and 6 characters long!


## Author

Hello! I'm a coder, I hoped this tutorial helped. Thank you for reading! To see more of my projects: <a href="https://github.com/rosebudroro">Github</a>