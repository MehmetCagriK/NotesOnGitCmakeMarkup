"You should get excited about documenting your own code" - Wise Man.
Unlike source code which is written for computers, documentation is for humans.
Not only you! You should document your code for other people to understand too.

Having a good documentation allows people to use your products or even help you 
developing them. It is even helpful for your job application in case potential
employer wanted to check your earlier public projects. Needless to say, future 
you will n0t remember every detail about your source code so you will be 
helping yourself with good documentation. Trying to understand source code 
without a documentation is like reverse-engineering someone's thought process.

README files are simple form of documentation. They are generally in project 
top directory to give first clue about what project is about.

There are no set-in-stone rules for preparing README files but below are some
suggestions for better README files.

- A README should provide just enough content to get a user up and running with
  your code. Start with a title and descrtion, a sentence or two is just fine. 
  But it should give a clear information about what is your project about.

- It is better to have sections about dependencies, installation instructions,
  usage and/or known bugs.

- Size does not matter(a rare case!). Information must be given clearly and 
  concisely. Give essential information and do not assume user knows 
  everything. Put yourself in a user's shoes: what would be hard to understand
  at first sight?

- Give information or a link to your license of code.

- Have a section that informs users about contributing your project like code of
  conduct etc.

Markdown
Markdown is a light markup language often used for README files.It is 
straightforward and much of its syntax is intuitive.

Markdown let's you generate well formatted README documents by translating them
to HTML. Many known websites like GitHub, StackOverflow, Reddit all use 
versions of markdown for quick and easy formatting of your content.

We mentioned versions of markdown. They are like real life dialects of a 
language, with minor differences. They are called flavor of markdown.
Below you will see syntax of GitHub flavoured markdown.

BOLD
To make a text bold surround it with double asterisks.
```
**I am bold**
```

ITALIC
To italicize a text, surround it with underscores.
```
I like _italian_ pizza.
```

CODE
Inline code is useful for indicating you are writing code, not regular words.
Surround your code text with double backticks.
``int * number = 0;``

But if you want to quote a code block, use triple backticks.
```
```
git status
git add
git commit
```
```
/code

TITLES
From bigger to smaller, you can write titles from **h1** through **h6** with 
# symbols.
/code
## This is an h2
##### This is an h5
/code

STRIKETHROUGH
To make your text strikethrough, surround it with ~~(double tilde)
/code
This text is ~~strikethrough~~
/code

LINK
You can create an inline link by enclosing your link's name with [ ] and then
enclosing your URL with ( ).
/code
This site was built using [GitHub Pages](https://pages.github.com/).
/code

SECTION LINKS
You can link directly to a section in a rendered file by hovering over the 
section heading to expose the link:i

RELATIVE LINKS
You can create links to other files relative to your current markdown document.
Assume README.md is in top directory and image.jpg is under docs directory.
/code
[Check image](docs/image.jpg)
/code

Note: GitHub will automatically transform your relative link or image path 
based on whatever branch you're currently on, so that the link or path always 
works. You can use all relative link operands, such as ./ and ../ .

LISTS
Finally we are on the lists.For unordered lists, you can use - or * .
For ordered lists, precede each line with a number and a dot afterwards.
You can combine ordered and unordered lists together.
/code
1. Make my changes
    1. Fix bug
    2. Improve formatting
        - Make the headings bigger
2. Push my commits to GitHub
3. Open a pull request
    * Describe my changes
    * Mention all the members of my team
        * Ask for feedback
/code

TASk LISTS
To create a tasklist, preface items with [ ]. To mark a task as complete, use
[x].
/code
- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request
/code

ESCAPE CHARACTER
You can use backslash(\) before characters that break markdown patterns.

MENTIONING OTHER USERS AND TEAMS
To mention a user or a team, type @ before their name to trigger a notification
and bring their attention to an issue or pull request.

PHARAGRAPHS AND BREAKS
Leave a blank line between pharagraphs to seperate them.
