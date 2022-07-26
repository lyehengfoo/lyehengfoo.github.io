---
title: "CSS Basic Selectors"
# date: 2022-01-01 14:30:00:00 +0800
author: foo
layout: post
icon: gear3
tags: web, css
# published: false
---

There are various selectors that we could use to select the element(s) in our HTML page.
Simple basic CSS selectors are covered in this article. The advanced CSS selectors will be
covered in the following article.

There are 4 simple basic CSS Selectors.

## Element selector

Select all <p> elements on a page.

```css
p { }
```

Select all <h1> and <h2> elements on a page.

```css
h1, h2 { }
```

## Class selector

Select all elements with a specific class on a page.  (Example with attribute *class="myclass"* in the HTML page)

```css
.myclass { }
```

## ID selector

Select all elements with a specific ID on a page. (Example with attribute *id="myid"* in the HTML page)

```css
#myid { }
```

## Universal selector

The universal selector (*) selects all HTML elements on the page.

```css
* { }
```
