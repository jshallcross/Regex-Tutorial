# Regex Tutorial - Matching An Email
---
A regex is also known as a regular expression. A regex is a pattern that is used to match combinations of characters. A regex can be used in your code to find and even replace specific character patterns. A regex can be used to match hex values, URL's, html tags, phone numbers and in this tutorial an email address.


## Summary
---
Below is our regex. We will explain all the characters and their functions.

`/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/`

This regex will match an email address to validate the users input to verify they have provided a properly formatted email address.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Greedy Match](#greedy-match)


## Regex Components
---

### Anchors
---
`/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/`

The `^` is at the beginning and the `$` is the end of a regex expression.

The `^` beginning anchor is used to match any string that starts with the character or characters that follow in in the expression. A simple example would be `^Start` would match with any string that begins with the word 'Start'

The `$` is the ending anchor that would match any strings ending with the characters preceding in the expression. A simple example would be `^End` would match with any string that begins with the word 'End' 

In our regex `/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/` we are looking for certain characters before and after the `@` and the `.`

Our exact requirements will be explained in more detail below.



### Quantifiers
---
`/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/`

At the end of our regex are curly brackets `{}`. These are our quantifiers and in our regex they are `{2,4}`.

Quantifiers tell us how many of the preceding characters exist in order to return a match.

Our regex quantifier `[a-zA-z]{2,4}` is looking for a minimum of two(2) and a maximum of four(4) characters after the `.`.

This will help validate that the user has inputted a valid email address as emails end with domains like '.ca', '.com' and '.net'.

Quantifiers: Min / Max `{2,4}` Exact Count `{5}` No Upper Limit `{3,}` will look for sequences of 3 or more. 


### OR Operator
---
The square brackets `[]` in a regex are called the OR operators.

`/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/` Our regex has three(3) OR operators.

The brackets tell us that the search can match any of the items listed between the brackets. A simple example would be `[a-z]` would match a string that includes any lowercase letters in the alphabet.

Our first OR operator comes before the `@` symbol `[a-zA-Z0-9._-]` and is looking for the following:

1. Any lowercase letter `a-z`
2. Any uppercase letter `A-Z`
3. Any integer `0-9`
4. A dot `.`
5. An underscore `_`
6. A dash `-`

Our second OR operator comes after the `@` symbol and before the `.`, `[a-zA-Z0-9.-]` and is looking for:

1. Any lowercase letter `a-z`
2. Any uppercase letter `A-Z`
3. Any integer `0-9`
4. A dot `.`
5. A dash `-`

Our third OR operator comes after the `.`, `[a-zA-Z]` and is looking for:

1. Any lowercase letter `a-z`
2. Any uppercase letter `A-Z`

We also know that this last OR operator is followed by Quantifiers `{2,4}` which means the `a-zA-Z` must also be between 2 and 4 characters.



### Character Classes
---
Character Classes are identified with a backslash `\`.

`/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/`

In our regex it is found before the `.`

Having a backslash before the dot `\.` tells us that we are looking for a dot. 

In our regex the first OR operator before the `@` symbol we are searching for adresses that MAY contain a period. For example "jon.shallcross@hotmail.com". However an email could also NOT include a dot such as "jonshallcross@hotmail.com. 

The `\.` is there to ensure that in our example the email has a dot`.` after the "hotmail" and before the "com".


### Flags
---
Flags are the forward slashes `/ /` that are at the start and end of the regex

`/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/`

Slashes let javascript know that we are creating a regular expression. There are more advanced flags `i` `g` `m` `s` `u`and `y` However we are not using those in our regex.

More information can be found at ('https://javascript.info/regexp-introduction')



### Greedy Match
---
A Greedy Match is created when a regex includes a `+`

Our Regex has two `+`. `/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/`

In our regex the characters before and after the `@` are both followed by the `+`. In our case the `+` will match the characters above as many times as it can.

In our regex there is no limit to how many characters come before and after the `@`.

You could use Quantifiers `{1,10}` for example to ensure that there are between 1 and 10 characters before or after the `@`.






## Author
Jon Shallcross is currently attending the University of Toronto Online Coding Bootcamp.

GitHub: ('https://github.com/jshallcross')
