## How to get this to work with the blog post

We're going to try to follow the instructions as laid out by the author of this blog right [here](https://pnmcartodesign.wordpress.com/2018/10/01/how-to-create-a-featured-image-template-for-a-jekyll-blog-site/) on how to create a featured image template for a GitHub blog. 

1. Create a template file in *_includes* directory to display the HTML *img* element named *post-featured-image.html* and include the following code:

```<img class="feat-img" src="{{ site.baseurl }}/assets/images/{{ include.image }}" alt="{{ include.alt | default: 'image representing a theme in this article' }}" />```

2. All images stay in the */assets/image directory*
