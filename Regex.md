# RegexTutorialJS

Bahar Mahmud, March 25th 2024

# Regex Tutorial for URL matching.

*A regular expression (Regex/Regexp), is a special text string for describing a search pattern. When included in code or 
search algorithms, regular expressions can be used to find certain patterns of characters within a string.


## Example:

```regexp
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/ 
```

**Explanation:**

-`/` Begins Regex
-`^` This is always at the begining of the string, to position the anchors.
-`(` Groups together multiple "tokens" to create a capture group. This can be used to retrieve a substring or backreference.
-`https` This indicates a sub-expression string that should be matched. "s"
- `?` This is a Greedy quantifier, which is basically denoting 0 or 1 occurrence of previous character (s) either http or https
^^ not 100% on this, pretty sure it takes a way the 's' from http
- `\/\/` This is an escaped character 
- `)` This Ends the capture grouped.
- `?` Greedy quaintifier indicating the entire previous section wrapped in () is optional. You can have it or not.
- `(` Begins captured group.
- `[` Begins bracket list.
- `/d` Is a metacharacter indicating any one digit character (0-9)
- `a-z` Indicates lower case letters between a-z.
- `\.` Escape sequence denoting the character `.`
- `-` Indicates `-` character
- `]` Ends bracket list.
- `+` Because its outside the brackets the Greedy quantifier is denoting that the previous bracket list characters, may occur one or more times.
- `)` Ends captured group.
- `\.` Escape sequence denoting the character `.`
- `(` Begins captured group.
- `[` Begins bracket list.
- `a-z.` Indicates lower case letters between a-z.
- `]` Ends bracket list.
`{2,6}` Occurence indicator denoting the previous bracket list characters may occur from 2 to 6 times.
- `)` Ends captured group.
- `(` Begins captured group.
- `[` Begins bracket list.
- `/` Escapes regex to match the character `/`
- `\w` Is a character class indicating any dingle Word Characters. Those are any characters including a-z, A-Z, 0-9, and _.
- `.` Escape sequence denoting the character `.`
- `-` Indicates `-` character
- `]` Ends bracket list.
- `*` The Greedy quantifier denoting that the previous bracket list characters may occur zero or more times
- `)` Ends captured group.
- `*` Greedy quantifier indicating that the entire previous captured group may occur zero or more times.
- `/` Escapes regex to denote a regular `/` character
- `?` Greedy quantifier indicating previous `/` character may have 0 or 1 occurrences.
- `$` Position acnhoring that ends the string.
- `/` Ends Regex.


## Table of Contents:

1.	[Anchors](#Anchors)
2.	[Quantifiers](#Quantifiers)
3.	[Character Classes](#Character-Classes)
4.	[Grouping and Capturing](#Grouping-and-Capturing)
5.	[Bracket Expressions](#Bracket-Expressions)
6.	[Greedy and Lazy Match](#Greedy-and-Lazy-Match)
7.	[Author](#Author)
8.	[User Story](#User-Story)
9.	[Acceptance Criteria](#Acceptance-Criteria)


## Regex Components

### Anchors

The Anchors are always at the begining and end of the string. For the example above, `^` is the symbol for the begining and `$` is for the end.

```text
^               Matches any string that starts with
$               Matches a string that ends with 
```


### Quantifiers

Quantifiers communicate to the regex engine that it MUST match the Quanity of the character or expression to its LEFT. 
There are two types of Quantifiers; Greedy and Lazy, each type has the same description.
- `* and *? `           Matches Zero or more times. 
- `+ and +? `           Matches One or more times.
- `? and ?? `           Matches Zero or One times.
- `{n} and {n}? `       Matches exactly n times.
- `{n,} and {n,}?  `    Matches atleast n times.
- `{n,m} and {n,m}? `   Matches from n to m times.

Examples include:

```text
https?          Because of the `?` Matches 'https', 'http'. 
[\da-z\.-]+     Because of the `+` it matches a single digit, group of letters (a-z), dot (.) or hyphen (-) 1 or more times
[a-z\.]{2,6}    Because of the `{2,6}` it matches 2 to 6 copies of the sequence [a-z\.]
[\/\w \.-]*     Because of the `*` it matches '/', '.', '-', 'www', '//'
```

### Character Classes

Character Classes ensure that a given sequence of characters matches a Larger set of characters. 


```text
[a-z]          Matches lowercase alphabetic characters between a and z
\w             Matches a single word
\d             Matches a single character that is a digit 0-9
.              Matches any character
```

### Grouping and Capturing

Grouping expressions allows us to keep things more organized and easier to exact the characters of a given group. This is used with parentheses "()".

```text
(https?:\/\/)     This group is basically saying it allows the URL code to being with "http://", "https://" or none of them.
([\da-z\.-]+)     This group which is the domain name. It matches 1 or more numbers, letters, dots or hypens. Ending it with a "+" linking it to the following line.
([a-z\.]{2,6})    Withe the + connecting this group together, this matches 2-6 copies of the sequences "[a-z\.]"
([\/\w \.-]*)     This group is is being matched as many times as they want because of the "*" at the end. 

```

### Bracket Expressions

Bracket expressions are expressions between "[]" brackets. In the example above, we have the following Bracket Expressions.

```text
[\da-z\.-]
[a-z\.]
[\/\w \.-]
```

### Greedy and Lazy Match

Greedy and Lazy Quantifers allow you to find the Greedy and the Lazy match. "Greedy" being the longest. "Lazy" being the shortest.

```text
([\da-z\.-]+)       The "+" operator is greedy as it allows character matching from one to an infinite amount of times.
```


## Author

Bahar Mahmud,
Github URL: https://github.com/BaharMahmud/RegexTutorialJS

Email: bahar.a.mahmud@gmail.com

## User Story

```text
AS A web development student
I WANT a tutorial explaining a specific regex
SO THAT I can understand the search pattern the regex defines
```

## Acceptance Criteria

```text
GIVEN a regex tutorial

WHEN I open the tutorial.
THEN I see a descriptive title and introductory paragraph explaining the purpose of the tutorial, a summary describing the regex featured in the tutorial, 
a table of contents linking to different sections that break down each component of the regex and explain what it does, and a section about the author with a link to the author’s GitHub profile.

WHEN I click on the links in the table of contents.
THEN I am taken to the corresponding sections of the tutorial.

WHEN I read through each section of the tutorial.
THEN I find a detailed explanation of what a specific component of the regex does.

WHEN I reach the end of the tutorial.
THEN I find a section about the author and a link to the author’s GitHub profile.
```

