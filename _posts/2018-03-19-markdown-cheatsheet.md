---
layout: post
title: "Jekyll and Markdown Cheatsheet"
comments: true
description: "Jekyll and Markdown Cheatsheet"
keywords: "markdown, typography components, dummy content"
---
## Let's get started

I'm starting my new blog now, and unlike applications to manage blogs, CMS etc, I didn't want anything too complicated to just write random stuff. I found a good solution when I read about "static site generators", like [https://jekyllrb.com/](Jekyll), which I found very interesting. More than that, Jekyll has an absurdly easy integration with [https://pages.github.com/](Github Pages). 

The pages (or blog posts) can be written using simple Makedown, which is pretty cool.

Let's go:

### Tutorials about Github Pages and Jekyll:

1. [https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/)

2. [http://jordankobellarz.github.io/jekyll/github/2015/01/14/como-criar-em-10-minutos-um-blog-gratis-com-jekyll-e-github-pages.html](http://jordankobellarz.github.io/jekyll/github/2015/01/14/como-criar-em-10-minutos-um-blog-gratis-com-jekyll-e-github-pages.html)
 
### Easy way to start learning about Markdown:

1. Online Makedown editor: [https://stackedit.io/](https://stackedit.io/)
2. This cheatsheet below:

<div class="divider"></div>

# Markdown Cheatsheet

## Typography Elements in One

Let's start with a informative paragraph. **This text is bolded.** But not this one! _How about italic text?_ Cool right? Ok, let's **_combine_** them together. Yeah, that's right! I have code to highlight, so `ThisIsMyCode()`. What a nice! Good people will hyperlink away, so [here we go](#) or [http://www.example.com](http://www.example.com).

<div class="divider"></div>

## Headings H1 to H6

# H1 Heading

## H2 Heading

### H3 Heading

#### H4 Heading

##### H5 Heading

###### H6 Heading

<div class="divider"></div>

## Footnote

Let's say you have text that you want to refer with a footnote, you can do that too! This is an example for the footnote number one [[^1]]. You can even add more footnotes, with link! [[^2]]

<div class="divider"></div>

## Blockquote

> Start by doing what's necessary; then do what's possible; and suddenly you are doing the impossible. --Francis of Assisi

**NOTE:** This theme does NOT support nested blockquotes.

<div class="divider"></div>

## List Items

1. First order list item
2. Second item

* Unordered list can use asterisks
- Or minuses
+ Or pluses

<div class="divider"></div>

## Code Blocks

```javascript
var modularpattern = (function() {
    // your module code goes here
    var sum = 0 ;

    return {
        add:function() {
            sum = sum + 1;
            return sum;
        },
        reset:function() {
            return sum = 0;    
        }  
    }   
}());
alert(modularpattern.add());    // alerts: 1
alert(modularpattern.add());    // alerts: 2
alert(modularpattern.reset());  // alerts: 0
```

```python
s = "Python syntax highlighting"
print s
```

```
No language indicated, so no syntax highlighting.
But let's throw in a <b>tag</b>.
```

<div class="divider"></div>

## Table

### Table 1: With Alignment

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

### Table 2: With Typography Elements

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

<div class="divider"></div>

## Horizontal Line

The HTML `<hr>` element is for creating a "thematic break" between paragraph-level elements. In markdown, you can create a `<hr>` with any of the following:

* `___`: three consecutive underscores
* `---`: three consecutive dashes
* `***`: three consecutive asterisks

renders to:

___

---

***

<div class="divider"></div>

## Media

### YouTube Embedded Iframe

<div class="video-container"><iframe src="https://www.youtube.com/embed/hTWKbfoikeg" frameborder="0" allowfullscreen></iframe></div>

### Image

![Github](http://s2.glbimg.com/nBsW9iMGHEMYJtADdQ9JdWXGP3k=/695x0/s.glbimg.com/po/tt2/f/original/2015/02/11/github-logo.jpg)

---
Footnote:

[^1]: 1: Footnote number one yeah baby!

[^2]: 2: A footnote you can link to - [click here!](#)
