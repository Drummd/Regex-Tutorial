# Understanding Regex

Regex or regular expressions are a string of characters created in a framework of certain syntax rules. As you will see regex can help with properly managing your data. Regex is available in languages like Python, Google Analytics, Javascript, SQL, and C++ with multiple others. 

## Summary

Regex expressions are useful for defining filters and contain a series of characters that define a pattern of text to be matched and can filter it to be more specialized or generalized.
The following will be an email in regex form used as an example since the a general email is a consistent format.

 General format - (something)@(some_domain).(some_toplevel_domain)

 Regex ex. ^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$

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
Anchors in a reqular expression are what starts and ends the code. As seen in the example below the anchors would be the caret '^' and the dollar '$'.

    Regex ex. ^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$

### Quantifiers
Quantifiers indicate numbers of characters or expressions to match. As you can see in the example below our regex is looking for any letters from a-z in lowercase and uppercase, any numbers from 0-9, underscores, dashes and periods. the '+' means the email needs to have one of these attributes to pass as an email. 

    Regex ex. ([a-zA-Z0-9_\-\.]+)

### OR Operator
The OR operator gives you a choice of which character or number you want to choose. The operator looks like this '|'.

    Number ex. - (one|1) - this or operator will match the users email if they typed out one or put the number instead.
    Letter ex. - (a|A) - this or operator will match based on the letter you choose if it be lowercase or uppercase.

### Character Classes
Character classes can be a primary use for grouping, in our regex example we are taking characters that include a-z in uppercase and lowercase but this can be used differently with certain character classes.

    \w - can take any word character ( alphanumeric and underscore)
    \d - can take any digit [0-9]
    \s - whitespace (spaces, tabs, line breaks)

### Flags
A flag changes the behavior of a reqular expression and makes the regex search in a different way. Flags are denoted using a single lowercase alphabetic character. Here are some flags and what they are used for.

    Ignore Casing - Flag (i) - Makes the expression search case-insensitively
    Global - Flag (g) - Makes the expression search for all occurences
    Dot All - Flag (s) - Makes the wild character '.' match newlines as well
    Multiline - Flag (m) - Makes the boundary characters '^' and '$' match the beginning and ending of every line instead of the whole string
    Sticky - Flag (y) - Makes the expression start its searching from the index indicated in its last index property
    Unicode - Flag (u) - Makes the expression assume individual characters as code points, not code units and match the 32-bit character units

### Grouping and Capturing
Grouping is read as what is in the paranthesis and captures the groups information before moving on to the next grouping.
Using our original example lets look at some grouping.

    Regex ex. ^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$
    Group 1 - ([a-zA-Z0-9_\-\.]+)
    Group 2 - ([a-zA-Z0-9_\-\.]+)
    Group 3 - ([a-zA-Z]{2,5})
    - The information within is being captured and processed

### Bracket Expressions
Bracket expressions are used to hold a set of characters inside to match the emails characters , numbers and symbols.

    Regex ex. ^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$
    Bracket ex. [a-zA-Z0-9_\-\.] - this bracket shows exactly what it needs to pass as an email

### Greedy and Lazy Match
A greedy match will have regex find a pattern within the string and matches as many characters as possible.

    ex. The regex 'a+' will match as many 'a' s as possible in your string 'aaaa' 

A lazy match will attempt to repeat the sub-pattern as few times as possible before using longer matches

    ex. To make quantifiers lazy, just append ? to the existing quantifier, e.g. +?, {0,5}?

### Boundaries
Boundaries in a regex signify that the code between is what should be read and this can include within the regex as well.
The most notable boundary in a regex is the caret '^' and the dollar sign '$'.

    ex. A word boundary, given by the special character \b, is a position that bounds a word in a place where the word starts or ends.

### Back-references
Back-references are regular expression commands which refer to a previous part of the matched regular expression. These are specified with a backslash and a single digit

    ex. The backreference \1 (backslash one) references the first capturing group

### Look-ahead and Look-behind
Look-ahead and behind are used as a way to find only the certain matches requested.
    Look-Ahead
    Positive ex. The syntax is: X(?=Y), it means "look for X, but match only if followed by Y". There may be any pattern instead of X and Y.
    Negative ex. The syntax is: X(?!Y), it means "search X, but only if not followed by Y".

    Look-behind
    Positive ex. (?<=Y)X, matches X, but only if there’s Y before it.
    Negative ex. (?<!Y)X, matches X, but only if there’s no Y before it.

## Author
### Dalton Drumm
## Github
### https://github.com/Drummd/Regex-Tutorial
