# REGEX TUTORIAL FOR BEGINNERS 

    I will cover the components of a regular expression used to match Hex Values.

## Summary

    The regex I will be discribing are Hex values, commonly used for color using the hexadecimal color code format. 
    Hex triplet / hex color code is meant to represent colors on a web page.
    For the hex color code there are two formats, and both start with a #:
         1- The standard hex triplet
         2- The shorthand hex format

    Example:  /^#?([a-f0-9]{6}|[a-f0-9]{3})$/




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




## -----------------   Regex Components  ------------------ ##

### Anchors

    Code Snippet:   /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

    Definition: Anchors are used at the start and end of a string or expression. 

    -  /^ and $/ signify the beginning or end of our expression.



### Quantifiers

    Code Snippet:  /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

    Definition: Quantifiers are used to communicate how many characters are expected, and specify how many instances of a character, group, or character class must be present in the input for a match to be found. 
    By default, quantifiers will match as many characters as possible. 
    If the ",+,?,{}" characters are found within regular expressions, they are considered quantifiers. 
        - The ? indicates the expression to match 0 or 1 time. 
        - There are 2 types of formats: the or operator to distinguish which format we are using. 
        - In our Hex Value regular expression we have 
        * {6} (Hex Triplet Format) and 
        * {3} (Shorthand Hex Format)
    The length of the component preceding these quantifiers should be 6 for {6} and 3 for {3}.
          ----> Hex Triplet Formats Include: #000000, #FFFFFFF, #0099CC
          ----> Shorthand Hex Format: #000, #FFF, #09C (the hex triplet format would just double each character: #09C -> #0099CC)


### OR Operator

    Code Snippet:  /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

    Definition: The "or" operator within a regular expression is defined using " | " element. 
    The "or" operator indicates that it could either of the components that we are separating with the " | ". 
        - For the hex value regular expression: ([a-f0-9]{6}|[a-f0-9]{3}), the "or" operator separates these 2 components. 
        - The hex value could either be 6 characters [a-f0-9]{6} or 3 characters [a-f0-9]{3}.



### Character Classes

    Code Snippet:  /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

    Definition: Character classes are components within our regular expression that indicate what type of characters to expect. 
    Character classes are confined within brackets []. 
    For this example: [a-f0-9] and [a-f0-9] , which searches for the same values.
    -    a-f searches for letters 
    -    0-9 searches for digits 0-9.




### Flags

    Definition:
    A flag changes the default searching behaviour of a regular expression.

    Code Snippet: 
    i   - The search is case-insensitive: no difference between A and a;
    g   - The search looks for all matches;
    m   - "Multiline" mode (the characters ^ and $ match the beginning and ending of every single line instead of the beginning and ending of the whole string);
    s   - Enables “Dot All” mode, that allows a dot . to match newline character \n;
    u   - Enables full "Unicode" support, that enables correct processing of surrogate pairs;
    y   - “Sticky” mode: searching at the exact position in the text from the inex (lastIndex propriety).



### Grouping and Capturing

    Code Snippet: ((a)(b(c)))

    Definition: 
    Capturing and Grouping are expressions able to unify a pattern and match it as a complete block. In other words, they find strings of characters that match the regular expression.  
      - Grouping a pattern: use of parentheses (), and between them the pattern we wish to group. This type of grouping is called a capturing group. 
      - A Non-capturing group is given by (?:). 



### Bracket Expressions

    Code Snippet:  /^#?([a-f0-9]{6}|[a-f0-9]{3})$/
    Definition: Bracket expressions signify the beginning of a character class or quantifier statement. Parenthesis are used to define a bracket expression/s.



### Greedy and Lazy Match

    Code Snippet: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

    Definition: A greedy match tries to match an element as many times as possible. A lazy match tries to match an element as few times as possible. 
    
     - ? signifies lazy quantifier, because it causes the regular expression engine to match as few occurances as possible. 
     - It is possible to turn this lazy match into a greedy one by adding a ?.



### Boundaries

    Code Snippet: /\bb[aeiou]t\b/    |   /\BB[aeiou]t\B/

    Definition: Boundaries are places between characters.
    There are two types of boundaries:
    1 - Word boundaries (\b) : denotes a place between a word and a non-word character; the start of the string; as well as the end of the string.
    2 - Non-word boundaries (\B) : the negation of \b . It matches any position a word boundary doesn't. 



### Back-references/ Backreferencing

    Code Snippet: "(A)b(e)d"

    Definition: This expression refers to a captured match, saved in memory, by a capturing group.
    It matches something, saves it in the memory and then we're able to use this saved value in some other place. 




### Look-ahead and Look-behind, aka Lookarounds

    Code Snippet:  X(?=Y) = look-ahead &  ?<=Y)X = look-behind

    Definition: Expressions that detect matches for a pattern that are preceded and followed by another pattern.

    Look-ahead: 
       Positive look-ahead: \d+(?=€)
       Negative look-ahead: X(?!Y)

    Look-behind:
      Positive look-behind: ?<=Y)X
      Negative look-behind: (?<!...)



## Author

    Mariana Marques, M.S Computer Graphics
    VR/AR Developer at Cohen&Company -Asset Management-

    Github repo: https://github.com/mmvrstudio
    2022

