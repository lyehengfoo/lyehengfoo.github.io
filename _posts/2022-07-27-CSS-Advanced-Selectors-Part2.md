---
title: "CSS Advanced Selectors Part 2 - Pseudo-classes and Pseudo-elements"
# date: 2022-01-01 14:30:00:00 +0800
author: foo
layout: post
icon: web
tags: web, html, css
# published: false
---

In the previous articles, we have looked at basic and the more advanced **Combinator** selectors.

In this article, we will take a look at the use of a few common pseudo-classes and psuedo-elements,
and how to make use of these powerful CSS selectors.

## What are Pseudo-classes?

A pseudo-class is used to define a special state of an element.

For example, it can be used to:
- Style an element when a user mouses over it
- Style visited and unvisited links differently
- Style an element when it gets focus

## Anchor Pseudo-classes

These are the few pseudo-classes that can use with the anchor element:

```css
a:link {}   /* for unvisited link */
a:visited {}   /* for visited link */
a:hover {}   /* for when mouse is hovered over the link */
a:active {}   /* for when the link is selected */
```

**NOTE:**
a:hover MUST come after a:link and a:visited in the CSS definition in order to be effective!
a:active MUST come after a:hover in the CSS definition in order to be effective!


## Other useful Pseudo-classes

These pseudo-classes can be used over elements.  Examples:

```css
div:hover {}   /* for when mouse is hovered over the div section */
p:first-child {}   /* matches the first <p> child element of any element */
li:nth-child(2) {}   /* matches the second <li> child element of a list */
p:nth-child(odd) {}   /* matches all odd <p> child element of any element */
tr:nth-child(even) {}   /* matches all even <tr> child element of a table */
p:last-child {}   /* matches the last <p> child element of any element */
input:focus {}   /* for when the input element is in focus */
```

For a more complete list of all the available pseudo-classes to use, you may visit 
[W3Schools CSS Pseudo-classes] (https://www.w3schools.com/css/css_pseudo_classes.asp)

## What are Pseudo-elements?

A CSS pseudo-element is used to style specified parts of an element.

For example, it can be used to:
- Style the first letter, or line, of an element
- Insert content before, or after, the content of an element

Please take note that pseudo-elements starts with double colon (::), whereas
pseudo-classes starts with a single colon (:).

## Some useful Pseudo-elements

```css
::first-letter {}   /* select the first letter of the text */
::first-line {}   /* select the first line of the text */
::before {}   /* use to insert some conent before the content of an element */
::after {}   /* use to insert some conent after the content of an element */
::marker {}   /* use to style the markers of list items */
::selection {}   /* matches the portion of an element that is selected by user */
```

## Examples of usages of Pseudo-elements

The following example insert a small bulleye image before the start of the heading h1 text.

```css
h1::before {
  content: url(bulleyes.gif);
}
```

The following example turns the user selected text to bright red on a yellow background.

```css
::selection {
  color: red;
  background: yellow;
}
```

