# Regex-Cheat-Sheet-for-Devs

REGEX is a sequence of characters that defines a search pattern. Regex is a very useful tool that provide more flexible and powerful pattern matching.

## Summary

This gist covers regex componenets listed in [#Table of Contents](#table-of-contents) with examples.

Here is a quick example that might help you understand this concept a little bit better.
Say you're searching for phone numbers- searching for a pattern of numbers that is starts with 3 numeric values, that might be in parenthesis, followed by a (-) or a (.), followed by another 3 numbers that either end with (-) or a (.), followed by 4 numbers. (123-456-7890 OR 123.456.7890). This below is how we would search for phone numbers that meet that criteria.

```
/\(?\d{3}[-.)](\d{3})[-.]\d{4}$/
```

- \d : searches for any digit between 0-9;
- \d\d\d-\d\d\d-\d\d\d\d (metachar, metachar,metachar, followed by a literal character "-" or ")" or ".") and so on and so forth.

Now, let's get in to the contents.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Escapes](#character-escapes)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Questions](#questions)

## Regex Components

Regex must be wrapped in slash(/) characters

### Anchors

- Anchors can both be preceded by an exact string or a range of possible matches

```
^ : marks the begining of a string with the characters that folllow. *is case sensitive*
$ : maks the ending of a string.


```

### Quantifiers

- Quantifiers set the limmits of the string that your regex matches

```
\*: quantifier 0 or more

+: 1 or more

?: 0 or 1; adding ? at the end of each of these quantifiers will match as few as possible

{}: allows three different ways to set limits
    - {n}: mathes extactly n number of times
    - {n, }: mathes at least n number of times
    - {n,x}: matches min of n and max of x times
```

### OR Operator

(|)

- the OR operator allows us to use the logic outisde of bracket expression

```
[abc] = (a|b|c)
```

### Character Escapes

(\)

- allows the regex to escape a character that otherwise would be interpreted literally.

```
the OR operator for example, (|), when used with a blackslash in front, (\|), regex would search for the | rather than acting as an OR operator
```

### Character Classes

```
. : Matches any character except the newline character (\n)

\d : Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

\w : Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].

\s : Matches a single whitespace character, including tabs and line breaks
```

### Flags

- Flags are the only exception where it does not need to be wrapped in slashes(/) like all regex. They are placed at the end of a regex, after the second slash. Allows us to define additional functionaloty of limits of that regex. Few examples include:

```
g: Global search- tested against all possible matches in a string
i: Case insensitive search
m: multi line search - input string is treated as multiple lines
```

### Grouping and Capturing

- Capturing groups are a way to treat multiple characters as a single unit.

```
ex) if we are tring to match (puppies), it creates sinlge units of "p" "u" "p" "p" "i" "e" and "s".
```

### Bracket Expressions

- other wise known as "positive character group"

```

[] : anything inside the square brackets represents a range of characters that we want to match

ex:) [gus] will search for anything that includes g, u, or s regardless the length of the string

ex) [a-z] looks for all characters from a-z, case sensitive of course. \*need [A-Z] to search for capital letters

ex) [0-9] searhces for 0-9
[-_]: - OR \_

```

### Greedy and Lazy Match

- In greedy search, for every position in the string, it tries to match the pattern at that position. And if there is no match, it goes to the next position
- Lazy match does the exact opposite where it repeats minimal number of times

```
ex) Say that we are searching for any string in quatation marks("")

let str = "Harry" and his friends "Ron" and "Hermione" went to Hogwarts

- Greedy search would give us : "Harry" and his friends "Ron" and "Hermione"
- Lazy search would give us: "Harry", "Ron", "Hermione"

```

### Boundaries

(\b)

- Boundaries and [Anchors](#anchors) are similar in a sense that they are assertions about the engine's current position in the string. They do not consume characters. Anchors determine the begining and the end of a string where as boundaries determine what can be matched to the left and the rigt of the position

```

ex) \b dog \b will not match "dog" in \_dog or dog22 becuase there is no boundary bw the letter and the characters. but it will match "dog" in " happy dog"

```

### Back-references

- Back-references refers to a previous part of the matched regex- these are specified with backlash and a single digit('\1'). This is used to march the same content as a previously matched subexpression

## Questions

For any questions, you can either reach out to me on GitHub or via e-mail

- Username: @addiguskey
- GitHub Link: https://github.com/addiguskey
- E-mail: addisonguskey@gmail.com
