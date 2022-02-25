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

For each test above:
Decide on what it should produce by using either VScode preview or the CommonMark demo site
Showing the code in MarkdownParseTest.java for how you turned it into a test
For your implementation, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.
For the implementation you reviewed, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

snippet 1: 
`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)

snippet 2:
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)

snippet 3:
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
    https://ucsd-cse15l-w22.github.io/
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)

And then there's more text

Answer the following questions with 2-3 sentences each:
- Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.
- No, I do not think there can be a code change less than 10 lines that would make the program work for inline code with backticks. Not only would we have to look for the beginning and end of each backtick that indicates where the code section ends, we also have to check to make sure the backticks are included in the link when the backtick is inside the parentheses. 

- Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.
- Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.