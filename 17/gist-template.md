# Regex Cheatsheet
Understanding Regex

## Summary
This is a quick example on the use and functionality of regex. The sequence of matching an email(/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/) will be used to demonstrate how regex is used.

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
/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/
Anchors assert a position before, after, or between characters. Common examples include ^ (start of a line) and $ (end of a line).

### Quantifiers
/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/
Quantifiers specify the number of occurrences of a character or a group. Examples include * (zero or more), + (one or more), and ? (zero or one).

### OR Operator
^(0[1-9]|1[012])[-/.](0[1-9]|[12][0-9]|3[01])[-/.][0-9]{4}$
The pipe symbol (|) functions as an OR operator in regex, allowing you to match one pattern or another.

### Character Classes
Character classes match one character out of a set of characters. For example, [a-zA-Z0-9] matches any uppercase or lowercase letter.

### Flags
const regex = /hello/i;
console.log(regex.test("Hello"));  // Output: true

Flags are optional parameters that can be added to a regex pattern to modify its behavior. Common flags include i for case-insensitive matching and g for global matching.

### Grouping and Capturing
const regex = /hello/i;
console.log(regex.test("Hello"));  // Output: true
arentheses () are used for grouping and capturing. They create a capture group, allowing you to apply quantifiers to part of your regex pattern and capture the matched text.


### Bracket Expressions
const regex = /[a-zA-Z]/;
console.log(regex.test("Hello 42 World"));  // Output: true (matches 'H')
Bracket expressions are similar to character classes and match a single character out of a set specified within square brackets. For example, [aeiou] matches any vowel.


### Greedy and Lazy Match
const regex = /".+"/;
const input = 'This is "a test" string with "multiple" occurrences.';
const match = regex.exec(input);
console.log(match[0]);  // Output: "a test" string with "multiple" occurrences"
Quantifiers are greedy by default, meaning they match as much text as possible. Adding a ? after a quantifier (*?, +?, ??, {n,m}?) makes it lazy, matching as little text as possible.


### Boundaries
const regex = /\btest\b/;
const input = "This is a test. Testing is important.";
console.log(regex.test(input));  // Output: true (matches the word "test")
Boundaries assert positions where certain conditions are met, such as word boundaries (\b) or non-word boundaries (\B).

### Back-references
const regex = /\b(\w+)\s+\1\b/;
const input = "hello hello world world";
console.log(regex.test(input));  // Output: true (matches repeated words)
Back-references allow you to match the same text that was matched by a capturing group earlier in the regex pattern. For example, \1 refers to the first captured group.

### Look-ahead and Look-behind
const regex = /(?<=\$)\d+/;
const input = "The price is $50.";
const match = regex.exec(input);
console.log(match[0]);  // Output: '50' (matches '50' because it is preceded by '$')
Look-ahead ((?=...)) and look-behind ((?<=...)) assertions are used to ensure that a pattern is or isn't followed by another pattern, without including the second pattern in the match.

## Author
Edward (eDDy) Caldwell: Currently a student at ASU Full-Stack WD Bootcamp program. Github: https://github.com/eDDyBoWbOw