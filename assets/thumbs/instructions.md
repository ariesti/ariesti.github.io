
# How to Use the Thumbnails Stored in Thumbs

1. We already have a common Twitter cards code in use: 

```html
      <meta name="twitter:card" content="summary_large_image"/>
			<meta name="twitter:title" content="{%if page.title %}{{ page.title }}{% else %}{{ site.title }}{% endif %}">
			<meta name="twitter:description" content="{% if page.description %}{{ page.description }}{% else %}{{ site.description }}{% endif %}">
			<meta name="twitter:site" content="@lovellifuad" />
			<meta name="twitter:creator" content="@lovellifuad">
			<meta name="twitter:card" content="summary">
```
So we are going to add the twitter:image line when we have the thumbnails ready:

```html
      <meta name="twitter:image" content="{{ site.url }}/assets/thumbs/{{ page.image }}" />
```

2. The rules for the Twitter thumbnail image:

* Images for this Card support an aspect ratio of 1:1.
* Minimum dimensions are 144x144 or maximum 4096x4096. 
* Images must be less than 5Mb in size. 
* The image will be cropped to a square on all platforms.
* JPG, PNG, WEBP and GIF formats are supported. 
* Only the first frame of an animated GIF will be used. 
* SVG isn't supported. 


			
