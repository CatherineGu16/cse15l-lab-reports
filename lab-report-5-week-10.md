# **Lab Report 5: Differences in MarkdownParse**

## How I found the differences:
I found the differences by first running the `diff` command: <br />
`diff CSE15L-RoseateSpoonbill/output.txt quiz-markdown/markdown-parse/results.txt` <br />
which compared the file that was generated from running a make test in the group implementation and then the file from running the commonmark markdown-parse implementation. The outcome of running the command showed me what was in our group result for a certain line number followed by a `---` and then the commonmark result. I then used the terminal to find which test corresponds to the line number by opening the .txt files and using `:set number` in vim and manually searching for the line number using the arrow keys.
## Test #1: 194.md on line 212
194.md contents: ``[Foo*bar\]]:my_(url) 'title (with parens)' ``

`diff` results: group vs markdown: <br />
![diff212](photos\diff212.PNG)
<br />

In this test-file, our version provides the correct output but the commonmark version incorrectly finds a link. The correct output should be *no link* added because the code should make sure that the next character right after the `]` is `(`. A valid link cannot have other characters between the closing and opening parentheses.
The expected result of the .md file is: no links detected <br />

## Test #2: 342.md in line 542
342.md contents: ``[not a `link](/foo`)``

`diff` results: group vs markdown: <br />
![diff542](photos\diff542.PNG)
<br />

In test-file 342.md, the output of our implementation is correct but the commonmark implementation is not because it ignored the backticks that indicate a code block and included that as regular text. One bug in the commonmark version is that it does not omit the text found in code blocks. A fix for this would be to have another `if` statement that will check for matching sets of backticks and skip the contents inside when searching for links.
The code fix could be inserted within this block of code: <br />
![code](photos\212codefix.PNG)

The expected result of the .md file is: no link detected <br />