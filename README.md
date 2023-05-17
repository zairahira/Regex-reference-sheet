# Regex-reference-sheet

  ## Regular expressions
- `\d` Representsts any number
- `\D` Representsts anything but a number
- `\s` Representsts any space
- `\S` Representsts anything but a space
- `\w` Any character
- `\W` anything but a character
- `.` matches any character except line break (when used in regex needs to be escaped like this \.)
- `\b` Representsts a space that follows a whole word. eg: my dog(there is a word and then space and then a word)

- `+` means one or more. Eg w+ means one or more character.
- `?` looking for 0 or 1 repetitions 
- `*` 0 or more repetitions
- `{n}` n number of repetitions 
eg `\d{5}` => exact 5 character digits repition
-  `\d{1,5}` => digit repitition from 1 to 5

### Escape these
the following need to be escaped when searching in regex as they have a different meaning individually

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

### search literal text

'Jennifer\s\w+\s'
means Jennifer-space-any number of characters-space

## match currency in `$`
`\$\d*\.\d{2}`

The regular expression `\$\d*\.\d{2}` matches a specific pattern in a string:

-   `\$`: Matches the dollar sign ($) character literally. It needs to be escaped with a backslash ($) because the dollar sign has a special meaning in regular expressions (end of string anchor).
-   `\d*`: Matches zero or more digits (0-9). The `\d` is a shorthand character class for any digit character.
-   `\.`: Matches a period (dot) character (.) literally. It also needs to be escaped with a backslash (.) because the period has a special meaning in regular expressions (matches any character except newline).
-   `\d{2}`: Matches exactly two digits (0-9).

Combining all the elements together, the regular expression `\$\d*\.\d{2}` looks for a pattern in a string that starts with a dollar sign, followed by zero or more digits, a period, and exactly two digits. This pattern is often used to match currency values in the format of dollars and cents, such as `$10.99` or `$1000.00`.

## whitespace escape

- `\e escape
- `\f` form feed
- `\n` newline
- `\r` carriage return 
- `\t` tab


## ranges

`[a-z]` search every lowercase letter
`[0-9]` search any # of numbers

