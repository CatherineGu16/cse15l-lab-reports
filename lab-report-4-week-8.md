# **Lab Report 4: Markdown Snippets**

## Repo Links:
- [My implementation](https://github.com/CatherineGu16/CSE15L-RoseateSpoonbill.git)
- [Reviewed Implementation](https://github.com/Shree-G/markdown-parse.git)

## Expected Results:
- Snippet1: [%60google.com, google.com, ucsd.edu]
- Snippet2: [a.com, a.com(()), example.com]
- Snippet3: [https://ucsd-cse15l-w22.github.io/]

## My Implementation
Snippet 1 JUnitFail: <br />
![snippet1](photos\snippet1_JUnitFail.PNG)
<br /> <br />

Snippet 2 JUnitFail: <br />
![snippet2](photos\snippet2_JUnitFail.PNG)
<br /> <br />

Snippet 3 JUnitFail: <br />
![snippet3](photos\snippet3_JUnitFail.PNG)
<br /> <br />

## Reviewed Implementation
Snippet 1 JUnitFail: <br />
![snippet1](photos\Rsnippet1_JUnitFail.PNG)
<br /> <br />

Snippet 2 JUnitFail: <br />
![snippet2](photos\Rsnippet2_JUnitFail.PNG)
<br /> <br />

Snippet 3 JUnitFail: <br />
![snippet3](photos\Rsnippet3_JUnitFail.PNG)
<br /> <br />

## Can the program be fixed in <10 lines?
### Snippet 1 Fix
- No, I do not think there can be a code change less than 10 lines that would make the program work for inline code with backticks. Not only would we have to look for the beginning and end of each backtick that indicates where the code section ends, we also have to check the situations where the backticks are ignored and treated as regular text (ie. inside the parentheses).

### Snippet 2 Fix
- Yes, having to search and pair up each set of parentheses or brackets would only take up a few lines if you used a stack that pushed and popped each set. The escape sequence can be treated appropriately using a simple if statement checking for the character right before the bracket or parentheses.

### Snippet 3 Fix
- No, the links will only become non-links when there is more than one new line entered in a row in the brackets and if the new line is strictly before and/or after the text int he parentheses. Our program would need to check that there is no more than one new line entered and then trim the excess before and after for the parentheses but allow for new lines between non-blank characters in the string in the brackets, resulting in hefty if statements.