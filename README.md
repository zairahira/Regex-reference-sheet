# Regex-reference-sheet

  - [Regular expressions](#regular-expressions)
    - [Escape these characters](#escape-these-characters)
    - [Search literal text](#search-literal-text)
    - [Match currency in `$`](#match-currency-in-)
    - [Whitespace escape](#whitespace-escape)
    - [Ranges](#ranges)
    - [Testing regex in JS](#testing-regex-in-js)
    - [Create a negated charecter set](#create-a-negated-charecter-set)
    - [Search end of the strings](#search-end-of-the-strings)
    
  ## Regular expressions
  
  | Regex Pattern | Description |
|---------------|-------------|
| `\d`          | Represents any number |
| `\D`          | Represents anything but a number |
| `\s`          | Represents any space |
| `\S`          | Represents anything but a space |
| `\w`          | Any character |
| `\W`          | Represents anything but a character |
| `.`           | Matches any character except line break (when used in regex needs to be escaped like this \\.) |
| `\b`          | Representsts a space that follows a whole word. eg: my dog(there is a word and then space and then a word) |
| `+`           | Means one or more. Eg w+ means one or more character. |
| `?`           | Looking for 0 or 1 repetitions |
| `*`           | 0 or more repetitions |
| `{n}`         | n number of repetitions eg \d{5} => exact 5 character digits repetition |
| `\d{1,5}`     | digit repetition from 1 to 5 |


### Escape these characters
The following characters need to be escaped when searching in regex as they have a different meaning individually.

    (
    )
    *
    +
    ?
    [
    \
    ^
    {
    |
    $

### Search literal text

'Jennifer\s\w+\s'
Means Jennifer-space-any number of characters-space

### Match currency in `$`
`\$\d*\.\d{2}`

The regular expression `\$\d*\.\d{2}` matches a specific pattern in a string:

-   `\$`: Matches the dollar sign ($) character literally. It needs to be escaped with a backslash ($) because the dollar sign has a special meaning in regular expressions (end of string anchor).
-   `\d*`: Matches zero or more digits (0-9). The `\d` is a shorthand character class for any digit character.
-   `\.`: Matches a period (dot) character (.) literally. It also needs to be escaped with a backslash (.) because the period has a special meaning in regular expressions (matches any character except newline).
-   `\d{2}`: Matches exactly two digits (0-9).

Combining all the elements together, the regular expression `\$\d*\.\d{2}` looks for a pattern in a string that starts with a dollar sign, followed by zero or more digits, a period, and exactly two digits. This pattern is often used to match currency values in the format of dollars and cents, such as `$10.99` or `$1000.00`.

### Whitespace escape

- `\e` escape
- `\f` form feed
- `\n` newline
- `\r` carriage return 
- `\t` tab


### Ranges

`[a-z]` search every lowercase letter. Same as `\w`.
`[0-9]` search any # of numbers. Same as `\d`



### Testing regex in JS

In JavaScript, the `test()` and `match()` functions are used for pattern matching with regular expressions. Here's a brief overview of their syntax and usage:

1.  `test()` function:
    
    -   Syntax: `regex.test(str)`
    -   Description: Tests whether a pattern (regular expression) matches a given string. It returns a boolean value (`true` or `false`) indicating whether the pattern is found in the string or not.
    -   Parameters:
        -   `regex` (regular expression): The pattern to match against the string.
        -   `str` (string): The string to test against the pattern.
    -   Example:
        
        ```javascript
        
        `const regex = /hello/;
        const str = 'Hello, world!';
        
        cnsole.log(regex.test(str)); // Output: false
        ```
        
2.  `match()` function:
    
    -   Syntax: `str.match(regex)`
    -   Description: Searches a string for a pattern (regular expression) and returns an array of matches. If no matches are found, it returns `null`.
    -   Parameters:
        -   `str` (string): The string to search for matches.
        -   `regex` (regular expression): The pattern to match against the string.
    -   Example:
        
        ```Javascript
        
        `const regex = /\d+/;
        const str = 'Hello, 123 world!';
        
        console.log(str.match(regex)); // Output: ['123']` 
        ```

Both `test()` and `match()` functions are commonly used in JavaScript for pattern matching and working with regular expressions. The `test()` function is primarily used to check if a pattern exists in a string, while the `match()` function is used to extract matching substrings from a string.


### Create a negated charecter set

To create a negated character set, you place a caret character (`^`) after the opening bracket and before the characters you do not want to match.

For example,  `/[^aeiou]/gi`  matches all characters that are not a vowel. Note that characters like  `.`,  `!`,  `[`,  `@`,  `/`  and white space are matched - the negated vowel character set only excludes the vowel characters.

> note: when `^` is used outisde a set, it is used to match the beginning of a string.

Outside of a character set, the caret is used to search for patterns at the beginning of strings.

```js
let firstString = "Ricky is first and can be found.";
let firstRegex = /^Ricky/;
firstRegex.test(firstString);
let notFirst = "You can't find Ricky now.";
firstRegex.test(notFirst);

```

The first  `test`  call would return  `true`, while the second would return  `false`.

### Search end of the strings

You can search the end of strings using the dollar sign character  `$`  at the end of the regex.

```js
let theEnding = "This is a never ending story";
let storyRegex = /story$/;
storyRegex.test(theEnding);
let noEnding = "Sometimes a story will have to end";
storyRegex.test(noEnding);

```

The first  `test`  call would return  `true`, while the second would return  `false`.

