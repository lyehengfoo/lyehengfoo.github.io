---
title: "How to Use the Deep-fried Jekyll Theme"
date: 2021-06-09 14:52:00:00 +00:00
author: steven
layout: post
image: /assets/img/2021/06/deep-fried.png
icon: deep-fried
tags: deep-fried
---

To use the Deep-fried Jekyll theme, simply fork the [GitHub](https://github.com) 
repository located at 
[github.com/kiltandcode/deep-fried-jekyll-theme](https://github.com/kiltandcode/deep-fried-jekyll-theme) 
and start modifying the **_config.yml** file. That's it!

Alternatively, if you're using 
[GitHub Pages](https://github.blog/2017-11-29-use-any-theme-with-github-pages/), you can 
add the following to your site's **config.yml** file:

```yaml
remote_theme: kiltandcode/deep-fried-jekyll-theme
```

## Related Posts

The Deep-fried Jekyll theme includes the ability to display related posts at the 
bottom of each article. This can be enabled in the **_config.yml** file and will use the 
**tags** metadata property located in the front matter of the post.

For example, using the following in the front matter will display related posts with 
the tag **"deep-fried"**:

```yaml
tags: deep-fried
```

## Stylesheets

The Deep-fried Jekyll theme has a couple of built-in stylesheets that are referenced 
in the **_config.yml** file, and you can add as many additional stylesheets as you would 
like by appending to the following section:

```yaml
# Stylesheets
stylesheets:
  - '/css/stylesheet.css'
  - '/css/syntax.css'
```

## Icons

The Deep-fried Jekyll theme has the ability to add an icon at the top of each post. 
The icon can be referenced as a metadata property in the front matter of the post as 
follows: 

```yaml
icon: deep-fried
```

In the **_data** directory of the Deep-fried Jekyll theme, there is the file **icons.yml** 
that will store all of the icons and their locations:

```yaml
deep-fried:
  src: /assets/img/icons/deep-fried.png
```

## Authors

Similar to icons, you can assign an author to each post. The author can be referenced as 
a metadata property in the front matter of the post as follows:

```yaml
author: steven
```

In the **_data** directory of the Deep-fried Jekyll theme, there is the file **authors.yml** 
that will store all of the authors and their names:

```yaml
steven:
  name: 'Steven McLintock'
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

If you would like to embed videos in your posts, you can use the **embed-video.html** include:

```yaml
{% raw %}{%{% endraw %}
    include embed-video.html
    src='https://thevideotoembed.com/'
{% raw %}%}{% endraw %}
```