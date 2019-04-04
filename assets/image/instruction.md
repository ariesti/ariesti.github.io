## How to get this to work with the blog post

We're going to try to follow the instructions as laid out by the author of this blog right [here](https://pnmcartodesign.wordpress.com/2018/10/01/how-to-create-a-featured-image-template-for-a-jekyll-blog-site/) on how to create a featured image template for a GitHub blog. 

1. Create a template file in *_includes* directory to display the HTML *img* element named *post-featured-image.html* and include the following code:

```<img class="feat-img" src="{{ site.baseurl }}/assets/images/{{ include.image }}" alt="{{ include.alt | default: 'image representing a theme in this article' }}" />```

2. All images stay in the **_/assets/image directory_** with two variables **include.image** and **include.alt** corresponding to the Front Matter of the post. 

3. Front matter variables:

* featured-image: the image file name and extension
* featured-image-alt: alternative text for the image

4. Sample code

In the Post File [2018-09-30-Sample-Post.md]

```
---
layout: post
title:  A Sample Post
date:   2018-09-30
author: Mike the Blogger
description: This is the one blog post to rule them all
featured-image: my-awesome-photo.jpg
featured-image-alt: Mike the Blogger speaking at Times Square, New York City, New York
categories: Side Hustle
---
```

The post.html; located in the _layouts directory

```
<!-- some page content -->
<header class="post-header">
   <h1 class="post-title">{{ page.title }}</h1>
   <time datetime="{{ page.date | date_to_xmlschema }}">{{ page.date | date: "%b %-d, %Y" }}</time>
   {% if page.author %} • {{ page.author }}{% endif %}
   <!-- call the featured-post-image.html template file -->
   {% if page.featured-image %}{% include post-featured-image.html image=page.featured-image alt=page.featured-image-alt %}{% endif %}
</header>
<!-- other page content -->
```

The index.html, located in project's root directory
```
<!-- some HTML content -->
{% for post in site.posts limit:3 %}
    <div>
        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
        <!-- call the featured-post-image.html template file -->
        {% if post.featured-image %}{% include post-featured-image.html image=post.featured-image alt=post.featured-image-alt %}{% endif %}
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        {% if page.author %} • <span itemprop="author" itemscope itemtype="http://schema.org/Person"><span itemprop="name">{{ page.author }}</span></span>{% endif %}
    </div>   
{% endfor %}
<!-- some other HTML content -->
```
NOTE: Currently the featured images are used for Facebook social media posts, to accompany the articles. Also, major blunder: I have not been able to make head.html include file to work with the default layout, so I just copy and paste everything into the default layout file and work from there. 
