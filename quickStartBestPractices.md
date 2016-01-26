#Quick Start/Best Practices

## Intro
Lets get started with writing a Gist.  Remember they should be on a specific topic...either a product or a process.

## Basics
Gists are written and styled in [markdown](https://en.wikipedia.org/wiki/Markdown). Markdown is a [markup language](https://en.wikipedia.org/wiki/Markup_language).  A markup language is a way *...for marking or tagging a document that indicates its logical structure (as paragraphs) and gives instructions for its layout on the page...*
<sup>[1](http://www.merriam-webster.com/dictionary/markup%20language)</sup>

Gists can be written directly in GitHub or with a text editor on your desktop \((Notpad++)https://notepad-plus-plus.org/), [TextWrangler](http://www.barebones.com/products/textwrangler/), [vim](http://www.vim.org/), etc...\)














#How to Write a Gist for the DAT

##Intro
Gist are awesome!  They help you share your knowledge and insights to your colleagues.  They can be about anything but here they will focus on either:
- creating a specific product (i.e. How to make the Monthly Syria Program Map)
- a specfic task or processs (i.e. how to write a Gist or how to use gdal to conver csvs into shapefiles)

This gist will act as a one stop shop to get Data Analysis Team members up to speed on how they work so they can begin writing their own.  This means that you should have the technical knowledge on how to write them as well as an understanding to the standard formating and best practices we use for them.

##Disclosure 
Since these are public gists please make sure to scrape all:
- PII
- Filepaths to datasets
- Specific program names
- Any other sensitive information or materials

##Markdown Basics
Gists are written and styled in [markdown](https://en.wikipedia.org/wiki/Markdown). Markdown is a [markup language](https://en.wikipedia.org/wiki/Markup_language).  A markup language is a way *...for marking or tagging a document that indicates its logical structure (as paragraphs) and gives instructions for its layout on the page...*
<sup>[1](http://www.merriam-webster.com/dictionary/markup%20language)</sup>

We will layout some basic structure and content to have in a gist as well as go into markdown a bit, however its just the basic as there are other resources that cover markdown more indepth.
- [github flavoured markdown](https://help.github.com/articles/github-flavored-markdown/)
- [mastering markdown](https://guides.github.com/features/mastering-markdown/)

###Text
There are different ways to format text: 
- **bold** by wrapping it with \*\* or \__ on either side of the text
  - example: \*\* Rory \*\* is awesome = **Rory** is awesome.  
- *italics* by wrapping it with \* or \_ on either side of the text
  - example: \* Rory \* is awesome = *Rory* is awesome. 
- one can also combine the two
  -  example: \_\*\*Rory\*\* is awesome\_ = _Rory **is** awesome_
- strike through text by wrapping it with with \~\~ on either side of the text (this only works on github markdown)
  - example Rory is `~~` not `~~` awesome = Rory is ~~not~~ awesome

###Code 	
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

###Headings
Use \# to indicate a heading.  The more \# used in a row, the smaller the heading will be.  For example: \# > \#\# >\#\#\#

###Lists
Lists can be done one of two ways: ordered or unordered. 
- Items in an unordered lists are marked with a \- or \* or \+ in the end they all do the same thing... make a -
- Items in an ordered list are marked with `1., 2., 3.`


##Style
- Always start with a tile, it should explain what the Gist is all about.  Further, it should be styled at the one \# level.
- Include an **Intro** section to go more in depth to what the gist is about, 

