#Quick Start/Best Practices

## Intro
Lets get started with writing a Gist.  Remember they should be on a specific topic...either a product or a process.

## Basics
Gists are written and styled in [markdown](https://en.wikipedia.org/wiki/Markdown). Markdown is a [markup language](https://en.wikipedia.org/wiki/Markup_language).  A markup language is a way *...for marking or tagging a document that indicates its logical structure (as paragraphs) and gives instructions for its layout on the page...*
<sup>[1](http://www.merriam-webster.com/dictionary/markup%20language)</sup>

Gists can be written directly in GitHub or with a text editor on your desktop ( [Notpad\+\+](https://notepad-plus-plus.org/), [TextWrangler](http://www.barebones.com/products/textwrangler/), [vim](http://www.vim.org/), etc...\)  It is important to know how to use GitHub (and also have an account!) since we will be storing all of our Gists in a single repository.  If you need help with GitHub please refer to [GitHub Guides](https://guides.github.com/activities/hello-world/) we can also use time at a huddle to introduce it.

## Markdown

###Text
Formatting text is pretty straight forward.  You wrap the next you want to make **bold**, *italic*, etc... with special characters that tell the computer to make everything indside those characters the desired formatting.  Below are some examples:
- **bold** by wrapping it with \*\* or \__ on either side of the text
  - example: \*\* Rory \*\* is awesome = **Rory** is awesome.  
- *italics* by wrapping it with \* or \_ on either side of the text
  - example: \* Rory \* is awesome = *Rory* is awesome. 
- one can also combine the two
  -  example: \_\*\*Rory\*\* is awesome\_ = _Rory **is** awesome_
- strike through text by wrapping it with with \~\~ on either side of the text (this only works on github markdown)
  - example Rory is `~~` not `~~` awesome = Rory is ~~not~~ awesome

###Code 
It is a common practice to distinguish code from other text.  Further, a monospaced font is often used in writing code to insure clear formatting.  To do this in a Gist:

- Wrap code with \` for a small snippets
  - example: `print Rory is awesome` 
- Use: \`\`\`  a block of code 

```
if Rory = awesome 
    print 'Rory is awesome'
elif Rory != awesome
    print 'Rory sucks'
else
    print 'Rory is alright'
```

### Headings
Use \# to indicate a heading.  The more \# used in a row, the smaller the heading will be.  For example: \# > \#\# >\#\#\#

### Lists
Lists can be done one of two ways: ordered or unordered. 
- Items in an unordered lists are marked with a \- or \* or \+ in the end they all do the same thing... make a -
- Items in an ordered list are marked with `1., 2., 3.`

## Style/Best Practices
- Gist file names should be written in camel case as so `roryIsAwesome.md`
- Always start with a tile, it should explain what the Gist is all about.  Further, it should be styled at the one \# level.
- Include an **Intro** section to go more in depth to what the Gist is about making it clear to the reader what they will get out of it
- Update the [Gist Index](https://github.com/otihub/datgists/edit/master/index.md) with the requisit information so people can find it later.
- Add all images to the `images` directory

## Additional Resources
- [GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/)
- [Markdown Basics](https://help.github.com/articles/markdown-basics/)
