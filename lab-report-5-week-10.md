# **Lab Report 5: Differences in MarkdownParse**

## How I found the differences:
I found the differences by first running the `diff` command: <br />
`diff CSE15L-RoseateSpoonbill/output.txt quiz-markdown/markdown-parse/results.txt` <br />
which compared the file that was generated from running a make test in the group implementation and then the file from running the commonmark markdown-parse implementation. The outcome of running the command showed me what was in our group result for a file followed by a `---` and then the commonmark result.
## Test #1: 212.md
212.md contents:<br />
![212contents](photos\212contents.PNG)

`diff` results: group vs markdown: <br />
![diff212](photos\diff212.PNG)
<br />

In this test-file, our version provides the correct output but the commonmark version incorrectly finds a link. The correct output should be *no link* added because the code looked through code within the backticks that indicate a code block. One bug in the commonmark version is that it does not omit the text found in code blocks. A fix for this would be to have another `if` statement that will check for matching sets of backticks and skip the contents inside when searching for links.
The code fix could be inserted within this block of code: <br />
![code](photos\212codefix.PNG)

The expected result of the .md file is: <br />
![expected](photos\212expected.PNG)

## Test #2: 542.md
542.md contents:<br />
![542contents](photos\542contents.PNG)

`diff` results: group vs markdown: <br />
![diff542](photos\diff542.PNG)
<br />

In this test-file both versions of markdown-parse is incorrect because both implementations do not take into account the reference version of inserting a link where the text in brackets can be specified to a certain link later correctly. The `[bar]` that was found in line two of the file is specified with `[bar]: /url "title"` later in the file dictating that `bar` is the text with link of `title`. Thus the commonmark implementation is incorrect because although it detects a link, the link name is incorrect.

The expected result of the .md file is: <br />
![expected](photos\542expected.PNG)
<br />

Source: [https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#links](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#links)
