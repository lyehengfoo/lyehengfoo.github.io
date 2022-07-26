---
title: "CSS Advanced Selectors Part 2 - Pseudo-classes and Pseudo-elements"
# date: 2022-01-01 14:30:00:00 +0800
author: foo
layout: post
icon: gear3
tags: web, css
published: false
---

In the previous articles, we have looked at basic and the more advanced **Combinator** selectors.

In this article, we will look at the use of pseudo-classes and psuedo-elements to make use of
this powerful CSS selector.

Here are a few common pseudo-classes that we could use.

## :link

## :visited

## :hover

## :active

## :focus

The descendant selector matches all elements that are descendants of a specified element.

To select all <p> elements inside <div> elements on a page, the selector would be:

```css
div p { }
```

To select all <li> elements that are children of a <ul> element inside a parent <div> element, the selector would be:

```css
div ul li { }
```

## :first-child

## :nth-child(n)

## :last-child

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

## :link


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




[GitHub](https://github.com) 

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

*test1*
**test2**
***test3***



```
![Coffee](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80 "Beautiful Coffee")

[![Coffee](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80 "Beautiful Coffee")](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80)

```

![Coffee](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80 "Beautiful Coffee")

[![Coffee](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80 "Beautiful Coffee")](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80)


How to embed image / video using **image.html** / **embed-video.html** include:

```yaml
{% raw %}{%{% endraw %}
include image.html file='profilephoto2.jpg' alt='Lye Heng Foo'
{% raw %}%}{% endraw %}
```

```yaml
{% raw %}{%{% endraw %}
    include embed-video.html
    src='https://thevideotoembed.com/'
{% raw %}%}{% endraw %}
```

Example:

{% include image.html file='profilephoto2.jpg' alt='Lye Heng Foo' %}
