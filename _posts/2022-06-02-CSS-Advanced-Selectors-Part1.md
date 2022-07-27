---
title: "CSS Advanced Selectors Part 1 - The Combinator Selectors"
# date: 2022-01-01 14:30:00:00 +0800
author: foo
layout: post
icon: web
tags: web, html, css
# published: false
---

There are various selectors that we could use to select the element(s) in our HTML page.
We have covered simple basic CSS selectors in the previous article. In this article,
we will now cover the advanced CSS combinator selectors.

There are 4 CSS Combinator Selectors.

## Descendant selector

The descendant selector matches all elements that are descendants of a specified element.

To select all <p> elements inside <div> elements on a page, the selector would be:

```css
div p { }
```

To select all <li> elements that are children of a <ul> element inside a parent <div> element, the selector would be:

```css
div ul li { }
```

## Child selector

The child selector selects all elements that are the children of a specified element, even if
there are other elements in-between the parent and the child.

To select all <p> elements that are **direct** children of a <div> element inside a parent <div> element, the selector would be:

```css
div > p { }
```

To illustrate further the difference between *descendant* and *child* selectors, let's look at
the following HTML example:

```html
<ul class="mylist">
  <li>Item 1</li>
  <li>Item 2
    <ul>
      <li>Item 2A</li>
      <li>Item 2B</li>
    </ul>
  </li>
  <li>Item 3</li>
</ul>
```

To select all <li> items (1, 2, 2A, 2B and 3) inside **.mylist**, we would use:

```css
.mylist li { }
```

To select **only** the <li> items that are **direct** children of **.mylist** (1, 2 and 3),
we would use:

```css
.mylist > li { }
```

## Adjacent sibling selector

The adjacent sibling selector is used to select an element that is directly after another specific element.

Sibling elements must have the same parent element, and **"adjacent"** means **"immediately following".**

Here is an example to select the **first <p> element** that are placed immediately after <div> elements.

```css
div + p { }
```

## General sibling selector

The general sibling selector selects all elements that are next siblings of a specified element.

Here is an example to select **all <p> elements** that are next siblings of <div> elements.
 
```css
div ~ p { }
```
