# Regular Expressions  
*Notes from codeschool course*  

## Strings

RegEx expressions are formated like the following
`if (chars.match(/regular expression/))` where chars is the subject string, and regular expression is the pattern to check.

`|` is the or operator and allows for matching multiple strings.

`+` repeats the character until it doesn't match this allows for 1 or more of the character.

`[a-z]` is a character set that matches from within the set, in this case a-z case sensitive

`/[a-z]/i` i is the modifier that removes case sensitivity

`\s` represents whitespace in the pattern (space, tab, newline) so `[a-z\s]` allows for any letter or whitespace

`\w` represents the word set which is equivelent to `[a-zA-Z0-9]`

`?`  makes proceding optional

## Email Validation

`/\w+@\w+` will match the xxx@xxxxx portion of the email but . is not a `\w` character
`.` is a wildcard character and will match anything to match a literal "." need to escape it with `\.`

So far email validation is up to `/\w+@\w+\.\w+`

To be domain specific we can change it to `/\w+@\w+\.(com|net|org|edu)/i` where the `()` groups the content so in our example just putting net would not pass but if there were no "()" it would.

`^` means that the pattern must start at the begining of the string

`$` means it must end at the end of the string.

final email validator should be `/^\w+@\w+\.(com|net|org|edu)$/i`

## Confirmations  

`\b` adds boundarys on the match.  So`\bok\b` will match "ok" but not "okie"

`[^]` when caret is used in a set it means not

`\d` means any number = `[0-9]`

Capitalized sets do the opposite so `\D` is anything that is not a number

`{}` allows a count to be applied to the match meaning `\D{20,40}` means any non number character string that is at least 20 characters but not longer than 40

`/<pattern>/g` is the global modifier matches all instances of the match

`/<pattern>/m` is the multiline modifier matches ^ and $ match every line

`(?: group)` creates a non capture group and will not return the group info from the match.
