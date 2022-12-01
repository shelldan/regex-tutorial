# Regex Tutorial - Match an Email 

A **regex**, which is short for **regular expression**, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input. 

## Summary

In this tutorial, it will covers and breaks down the components of a regular expression to match an email. 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Each component of this regex has a unique responsibility to make sure that a user enters an email address that begins with an unspecified number of characters preceding the `@` symbol, followed by a domain.

## Table of Contents

- [Anchors](#anchors)
- [Bracket Expressions](#bracket-expressions)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

A regex is considered a literal, so the pattern must be wrapped in slash characters `/`. If we examine the 'Matching an Email' regex, you'll see that this is true:

`/`^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$`/`

Now let's take a look at the components of a regex. 

### Anchors

/`^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$`/

The characters `^` and `$` are both considered to be **anchors**.

The `^` anchor signifies start of string or line. This could be in one of two formats:

* An exact string match, such as `^abc`, where the strings `abcdefg` or `abc` match, but `ABC` and `ABCdefg` do not. This is because a regex is **case-sensitive**.

* A range of possible matches, displayed using bracket expressions. We'll discuss this in the next section. 

The `$` anchor signifies end of string or end of line. Just as with the `^` character, it can be preceded by an exact string or a range of possible matches. 


### Bracket Expressions
/^(`[a-z0-9_\.-]`+)@(`[\da-z\.-]`+)\.(`[a-z\.]`{2,6})$/

Anything inside a set of square brackets `[]` represents a range of characters that we want to match. 

In our 'Matching an Email' regex example, we can breakdown the bracket expressions as follows: 

* `[a-z]` - The string can contain any lowercase letter between `a-z`. 
* `[0-9]` - The string can contain any number between `0-9`.
* `[_\.-]` - The string can contain underscore, backward-slash, period, and hyphen.
* `[\da-z]` - The string can contain any number between `0-9` and `a-z`; `\d` is a common character class, which will be discussed in next section.

### Quantifiers
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]`{2,6}`)$/

`Quantifiers` sets the limits of the string that your regex matches (or an individual section of the string). They frequently include the minimum and maximum number of characters that your regex is looking for. 

In our 'Matching an Email' regex example, we can breakdown the quantifiers as follows: 

* `+` - Matches the pattern one or more times
* `{}` - Curly brackets can provide three different ways to set limits for a match: 
    * `{ n }` - Matches the pattern exactly `n` number of times 
    * `{ n, }` - Matches the pattern at least `n` number of times
    * `{ n, x }` - Matches the pattern from a minimum of `n` number of times to a maximum of `x` number of times. In our 'Matching an Email' regex example, we want to match the pattern for a minimum of 2 times to a maximum of 6 times.

### Grouping Constructs
/^`([a-z0-9_\.-]+)`@`([\da-z\.-]+)`\.`([a-z\.]{2,6})`$/

The primary way to group a section of a regex is by using parentheses `()`. Each section within parentheses is known as a **subexpression**. 

In our 'Matching an Email' regex example, we can breakdown the grouping constructs as follows:

* `([a-z0-9_\.-]+)` - Matches any string that includes any combination of lowercase letters between a and z, any number between 0 and 9, and the special characters of an underscore, backslash, period, and hyphen; and you could match the pattern one or more times. 
* `([\da-z\.-]+)` - Matches any string that includes any combination of number between 0 and 9, lowercase letters between a and z, and the special characters of a backslash, period, and hyphen; and you could match the pattern one or more times. 
* `([a-z\.]{2,6})` - Matches any string that includes any combination of lowercase letters between a and z and the special characters of a backslash and period; and you could match the pattern with minimum of 2 times to maximum of 6 times. 

### Character Classes

/^([a-z0-9_\.-]+)@([`\d`a-z\.-]+)\.([a-z\.]{2,6})$/

A **character class** in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. 

Here are some of common character classes:
* `.` - Matches any character except the newline character `\n`
* `\d` - Matches any Arabic numeral digit. This class is equivalent to the bracket expression `[0-9]`.

### The OR Operator

You could use the `|` operator to match characters or expression of either the left or right of the `|` operator. For example the `(t|T)` will match either `t` or `T` from the input string. 

### Flags

Regular expressions may have flags that affect the search. There are only 6 of them in JavaScript:

* `i` - With this flag the search is case-insensitive: no difference between `A` and `a` 
* `g` - With this flag the search looks for all matches, without it – only the first match is returned.
* `m` - Multiline mode.
* `s` - Enables `dotall` mode, that allows a dot `.` to match newline character `\n`
* `u` - Enable full Unicode support. The flag enables correct processing of surrogate pairs.
* `y` - `Sticky` mode: searching at the exact position in the text 

### Character Escapes
/^([a-z0-9_\.-]+)@([\da-z\.-]+)`\.`([a-z\.]{2,6})$/

The backslash `\`in a regex **escape** a character that otherwise would be interpreted literally. For example, the dot `.` is used to match any character, but adding a backslash before the dot `\.` means that the regex should look for the dot `.` only. 

## Author
Shelldan, a student learning to code. 

GitHub: [Shelldan](https://github.com/shelldan?tab=repositories)

