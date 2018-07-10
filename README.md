## eZ80-prettify

`eZ80-prettify` is a small eZ80 prettifier that lives in your browser. 

This is a personal tool, so it formats using my personal preferences and may not work with all compilers/directives.  
All of the code is in the public domain, so feel free to fork the project and customize it with your own preferences!

### Customizing `eZ80-prettify`

In the file named `index.html`, there is a relatively small script tag. Towards the top, there are a bunch of `const` variable initializations. These are your settings.

 - `INCREASE_INDENT`:
    - This is an array of RegExes, stored as strings. The regexes start at the beginning of a line and are case insensitive.
    - These RegExes match lines where the indentation level should be increased. The indentation increase does not affect the the line, but all lines after it.
 - `DECREASE_INDENT`:
    - This is also an array of RegExes, stored as strings. The regexes start at the beginning of a line and are case insensitive.
    - These match lines where the indent level should be decreased. *Unlike the lines matched by RegExes in the* `INCREASE_INDENT` *array, lines matched with these RegExes are affected.*
 - `NO_INDENT`:
    - Like the `INCREASE_INDENT` and `DECREASE_INDENT` arrays, this is an array of RegExes, stored as strings. The regexes start at the beginning of a line and are case insensitive.
    - These match lines where the indent level has no affect. Lines matched are always placed right at the beginning, with no indentation. It does not affect lines after the line matched.
 - `USE_TABS`:
    - This is a boolean value (`true` or `false`) that should be set to `true` if tabs are preferred over spaces.
 - `SPACES_PER_INDENTATION_LEVEL`:
    - This is the number of spaces used per indent level. It only has an affect on the indentation if `USE_TABS` is `false`.
 - `COMMENT_REGEX`:
    - This is a RegEx, **NOT** stored as a string, that matches comments not on the beginning of a line. It is a full RegEx, and must include the `^` start-of-line modifier and/or any wanted flags.

You can also modify the function, `prettify`, but that is left up to the developer.