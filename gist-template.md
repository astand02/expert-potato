# Matching An Email(REGEX Tutorial)

The purpose of this tutorial is to explain how to match emails using regex by using the expression `/^([a-zA-Z0-9_.-]+)@([\da-zA-Z.-]+).([a-zA-Z.]{2,})$/`. This information may be beneficial if you are validating emails using tools or platforms like Inqurier or MongoDB.

## Summary

This tutorial will guide you through the components of a regular expression, which is a string of characters used to define a search pattern. Regular expressions are frequently utilized to identify patterns within a string, replace characters within a string, or validate input. Specifically, this tutorial will demonstrate how regular expressions can be applied to match an email.

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

## Regex Components

`/^([a-zA-Z0-9_.-]+)@([\da-zA-Z.-]+).([a-zA-Z.]{2,})$/`

### Anchors

The regular expression utilized to match an email comprises of two anchors. The `^` anchor specifies that the code group within the initial set of parentheses must be matched, implying that the data presented before the @ symbol must be inputed in the code string. This guarantees that a user cannot submit an email address without including the mandatory NAME section at the start of an email address. The `$` anchor indicates that you are at the end of the string.

### Quantifiers

The number of characters that a regular expression will match can be determined by using a quantifier. In this particular regular expression, there are two quantifiers being used. The first quantifier is the `+` symbol, it connects the user's email service, email name, and .com. The second quantifier, `{2,6}`, allows for a range of `2-6` characters within the character set of `[a-z\.]`. These quantifiers are commonly used after a character class or bracket expression, which defines the specific set of characters that the regular expression will match.

### OR Operator

The `|` modifier functions as a boolean OR, allowing for its use in the current expression or any future ones. It has the capability to match most expressions before or after the `|` and can operate within a group or throughout the entire expression. It is important to mention that there are no instances of OR operators within the provided example above.

### Character Classes

The second set of braces in the given expression above utilizes the \d modifier to define a specific pattern. This pattern represents a character class that corresponds to a single digit ranging from 0 to 9. Its purpose is to match a solitary digit, for instance, "1", and not multiple digits such as "10".

### Flags

Regex flags are utilized for more complex searches. In this instance, we are implementing a multi-line flag, indicated by the `^` at the start and `$` at the end of the regex. This enables the expression to span across multiple lines without disrupting the code.

### Grouping and Capturing

The parentheses in the RegEx example shown above are used for grouping, which helps separate meta characters from literal characters. Furthermore, grouping and capturing can be used to isolate a specific part of a string, allowing you to replacing that segment of the string if needed.

Capture group one of this expression is `([a-z0-9_\.-]+)` this corresponds to the user  `email name`. The second capturing group is `([\da-z\.-]+)` which matches the `email service`. Finally, the third capture group is `([a-z\.]{2,6})` and it is matched to `.com`.

### Bracket Expressions

The use of brackets in the expression allows you to search for all data enclosed within the brackets. In the beginning of the expression [a-zA-Z0-9_.-], the brackets indicate that the search can include letters from 'a' to 'z', capitalized letters from 'A' to 'Z', numbers from 0 to 9, underscores, or hyphens.

### Greedy and Lazy Match

The greediness of an expression determines how much it can match, while its laziness allows it to match the smallest possible group. If the string ends before the pattern is fully matched, the search will backtrack and try to match the next pattern expression. This process continues until the pattern is either completed or fails to validate. Once a match is found for the expression, the search moves on to the next expression. In the example given both greedy and lazy matches are used, including the `+` qantifier which matches as many times as possible and the `{}` quantifier which matches a specific range of times for the last capture group.

### Boundaries

Email validation does not require boundaries as the '@' symbol serves as a natural boundary for any email address. The user email name, email service, and .com are considered separate words with boundaries. This is especially important as the email address must be identified as a complete entity.

### Back-references

Back-references, in the context of regular expressions, refer to previously matched groups that seek to find identical text once more. However, it is important to note that back-references were not used within the regular expression shown above.

## Author

Feel free to contact me directly at standridgealison@gmail.com for more information about this project. To check out my other github repositories click the link https://github.com/astand02.
