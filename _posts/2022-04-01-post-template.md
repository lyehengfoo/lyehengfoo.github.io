---
title: "Post Template"
date: 2021-06-09 14:52:00:00 +00:00
author: lyehengfoo
layout: post
image: /assets/img/2021/06/deep-fried.png
icon: gear3
tags: woodwork
---

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus porttitor diam vel mauris tempus commodo. Morbi sit amet finibus erat, id fermentum ligula. Integer vel purus a orci facilisis pharetra. Nullam odio diam, iaculis interdum pellentesque nec, laoreet non diam. Integer eget nibh sapien. Phasellus faucibus mattis leo in egestas. Integer convallis risus ac sem hendrerit, sit amet imperdiet justo cursus. Donec fringilla varius justo nec placerat.

Sed id congue nisl. In interdum elit vitae odio auctor, in bibendum nulla viverra. Fusce ac vulputate nunc, ac malesuada odio. Pellentesque viverra auctor ultricies. Vestibulum finibus lorem tellus, et imperdiet nibh egestas vel. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Fusce at congue metus, a ullamcorper lectus. Ut nec nisi eu augue sodales sodales. Nullam fermentum lectus laoreet odio vestibulum, congue maximus lectus semper.

[GitHub](https://github.com) 

## Heading 1

*test1*

**test2**

***test3***


```c
printf("Hello World!");
```

## Includes

If you would like to use images in your posts, you can use the **image.html** include. 
***Please note:*** the images should be located in the directory structure: 
**assets/img/*[YEAR]*/*[MONTH]*/image.png**

```yaml
{% raw %}{%{% endraw %}
    include image.html
    year='2021'
    month='06'
    file='image.png'
    alt='This is the alternative text for this image'
    caption='This is a caption that will appear below the image'
{% raw %}%}{% endraw %}
```

Or include direct image:

```
![Coffee](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80 "Beautiful Coffee")

[![Coffee](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80 "Beautiful Coffee")](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80)

```

![Coffee](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80 "Beautiful Coffee")

[![Coffee](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80 "Beautiful Coffee")](https://images.unsplash.com/photo-1561336313-0bd5e0b27ec8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80)


If you would like to embed videos in your posts, you can use the **embed-video.html** include:

```yaml
{% raw %}{%{% endraw %}
    include embed-video.html
    src='https://thevideotoembed.com/'
{% raw %}%}{% endraw %}
```