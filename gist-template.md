# Regex Tutorial - Email Matching Validation

A regular expression, or regex, is a search pattern used by developers. In the tutorial, you’ll understand the break down of each part of the expression and describe what it does for email validation. 

## Summary
The following regex pattern used for email validation:

```Regex-
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
The code is used to find Email addresses. In this tutorial we will dissect the following topics: Anchors, Quantifiers, OR Operators, Character Classes, Flags, Grouping and Capturing, Bracket Expressions, Greedy and Lazy Match, Boundries, Back-references, as well as Look-ahead and Look-behind.




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

These are considered anchors:

```
^ and $
```

Anchors match a position before, after or between characters. The anchors in the regular expression for matching an email are the carret ^ and the dollar symbol. The carret matches the beginning of the expression, and the $ matches the end of the expression, therefore the anchors represent the parameters of the regex.

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Both achors being used at the beginning and end of the code above.

### Quantifiers

With qunatifiers we can set the minimum/maximum length of the string.
Quantifies are considered **"greedy"** will try to find a match and if there is no match it will go to the next position.

- `*` Matches the pattern zero or more times.
- `?`  To look for the least amount of instances possible, a 'lazy' qualifier would be used by adding a ? after the qualifier.
- `+` operator acts as the qualifier which will look for one or more instances of everything in brackets.

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

We can see the the quantifiers towards the end of our example `{2,6}` is looking for a minimum string length of 2 and a maximum length of 6.

 The character set [a-z.] allows for any lowercase letter and period, which accounts for the "dot" in ".com" and other domains.

* The  forward slash /, which starts the regular expression.
* ^ indicates the start of the string that will be matched.
* @ matches the @ symbol that separates the username and domain name in an email address. 
* ([a-z\.]{2,6}) matches two to six characters that are either lowercase letters (a-z) or periods (.), and stores them as a capturing group. This represents the top-level domain (TLD) of the email address.
* $ symbol shows the end of the string that will be matched.

### OR Operator

In regular expressions, the OR operator is represented by the pipe (|) character. When using this character, it allows you to specify alternatives within a pattern. Take a look at this:

pattern1|pattern2|pattern3

When looking at the above example, and knowing what we know about the OR operator, we can tell that the pattern will be able to match "pattern1", "pattern2" or "pattern3". It provides more options for matching.

### Character Classes

A character class matches any symbol from a certain character set. They can be used to both match and exclude characters in your regular expressions. For example, the character class in this regex is the digit character class: `\d` , which matches any single digit between 0 to 9.

### Flags

While regex is a literal and must be wrapped in slash characters, the only exception to this rule are known as **flags**.

Typically they are added to the end of a pattern such as this: "/pattern/flags". 

* Case Insensitivity (i): This flag makes it so that the pattern is case-inensitive, meaning it will match both uppercase and lowercase letters.

* Global Matching (g): This flag enables global matching, meaning the pattern will find all matches in the input text, rather than just the first one.

* Multi-line Mode (m): This flag is used for multi-line matching. It can change the behavior of anchors and make them match the start and end of each line, rather than the entire text.

### Grouping and Capturing

The two main categories of grouping are known as **caturing** and **non-capturing**.
**Capturing groups** capture the matches with the intent to re-use them later and **non-capturing** do not.

Grouping constructs separate the expression into subgroups and capture the substrings of an input string. Parentheses `()` are used for grouping parts of the expression together. 

In the snippet for email matching there are three groups captured:

- The first subgroup is `([a-z0-9_\.-]+)` which matches the email username. 
- The next subgroup is `([\da-z\.-]+)` which matches the domain name or mail server. 
- Then the last subgroup, `([a-z\.]{2,6})`, captures the top-level domain, such as .com or .org.

### Bracket Expressions

Bracket Expressions are set of characters enclosed by (`[]`) and are also refered to as **Positive Character Group**.

The `[]` represent a range of characters that we would like to include in our match.

Bracked expressios for email validation includes the character sets of ```[a-z0-9_\.-]```, which is matching any letter a-z and is case senstive. It also matches a character 0-9 and matches the characters "_" , "-" , and "."; ```[\da-z\.-]```, which is matching a single digit from 0-9, any character a-z (case senstive), and the characters "." and "-".; ```[a-z\.]``` matches any character a-z(case senstive) and the character ".".

### Greedy and Lazy Match

- Greedy will match as many occurrences as possible.
- Lazy will match as few as possible.

### Boundaries

Boundaries refer to where relative to the current position of an anchor assertions can match.

* __Word boundries__ (`\b`) : matches positions where one side is a word character, letter, digit or etc.

* __Not-a-word boundaries__ (`\B`) match when neither side is a word character at any position in the string (`$=(@-%+)`) or when both sides are a word character.

### Back-references

Regular expression commands that refer to a previous part of the matched expression and use a backslash and single digit. For example:  `\1`.

### Look-ahead and Look-behind

*  __Look-ahead__ : positive or negative and allows to add a condition for "what follows". It commands to look for A but match only when it is followed by Z.
*  __Look-behind__: allows adding a pattern or condition if there's something before it/ Example: (?<=Y)X

## Author

More Info at [BeluchiIgbo](https://github.com/BeluchiIgbo)

