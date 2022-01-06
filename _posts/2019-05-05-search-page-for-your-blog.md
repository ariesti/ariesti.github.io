---
layout: post-basic
author: Lovelli Fuad
title: "A Super Simple Search Page for Finger Tip-Top"
description: With some help from Google CSE (Custom Search Engine), we now have a manual search page. You can get one too. 
lead: There aren’t that many pages or posts yet on Finger Tip-Top. So a manual search should be enough to find what you’re looking for.
permalink: blog/search-page-for-Jekyll-blog
date: 2019-05-05 05:01 PM
main-categories: [web]
other-categories: [admin, tutorials]
tags: [beginners, ui, websites]
lang: en
featured-image-description: A blog search page is not vital, but it's nice to have.
featured-image-alt: Search page 
---
<div class="container">
    <div class="row text-center text-lg-left">
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img class="img-fluid img-thumbnail" src="https://p1.pxfuel.com/preview/772/125/208/volkswagen-yellow-car-vehicle-retro-vintage.jpg" alt="">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img class="img-fluid img-thumbnail" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/Piper_PA18-95_Cub_G-AMEN_%286722495171%29.jpg/800px-Piper_PA18-95_Cub_G-AMEN_%286722495171%29.jpg" alt="">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img class="img-fluid img-thumbnail" src="https://c.pxhere.com/photos/36/2e/fashion_woman_female_girl_yellow_skirt_white_blouse-885771.jpg!d" alt="">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img class="img-fluid img-thumbnail" src="https://p1.pxfuel.com/preview/30/895/646/yellow-flowercenter-pompom-flower.jpg" alt="">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img class="img-fluid img-thumbnail" src="https://source.unsplash.com/sesveuG_rNo/400x300" alt="">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img class="img-fluid img-thumbnail" src="https://c1.wallpaperflare.com/preview/242/611/811/bike-cycle-bicycle-sport.jpg" alt="">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img alt="" src="https://p1.pxfuel.com/preview/373/290/425/architecture-building-infrastructure-design-yellow-condominium.jpg" class="img-fluid img-thumbnail">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img class="img-fluid img-thumbnail" src="https://media.defense.gov/2016/Jul/27/2001585024/1280/1280/0/160714-D-DB155-007.JPG" alt="">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img alt="" src="https://p1.pxfuel.com/preview/919/551/748/garage-batman-door-unique.jpg" class="img-fluid img-thumbnail">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img alt="" src="https://c1.wallpaperflare.com/preview/860/98/476/interior-minimal-minimalism-white.jpg" class="img-fluid img-thumbnail">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img alt="" src="https://live.staticflickr.com/3798/14105339228_e6df180fd2_c.jpg" class="img-fluid img-thumbnail">
          </a>
    </div>
    <div class="col-lg-3 col-md-4 col-6">
      <a href="#" class="d-block mb-4 h-100">
            <img class="img-fluid img-thumbnail" src="https://i2.pickpik.com/photos/456/773/111/cake-cheese-cheesecake-yellow-preview.jpg" alt="">
          </a>
    </div>
    </div>
<figcaption class="figure-caption alpha">What about a visual search?</figcaption>
</div>

<div class="fix-7x-12 toCenter mb-0 w3-medium">
<p>A search page or search functionality for a blog is not vital, but I wanted to add a search page early on. Because it’s going to be difficult to find anything once the blog has hundreds of blog posts. A search functionality is a nice extra touch to help readers who are interested in a particular topic but people can still read blog posts without it.</p>
<p>The search page I had in mind is not just a blank box to fill with search phrases. No, no. I wanted visitors to be able to 1) search for anything they are looking for, and 2) be able to see the big picture at once—all the categories and tags that they might not know they were looking for. I got the idea for something like this from browsing through a list of available free themes from Jekyll. Instead of a blank search box floating on a blank page, <a href="http://projectpages.github.io" class="blue" rel="nofollow">the theme</a> displays a list of project names below the search box.</p>
<p>Finger Tip-Top’s search page includes all the categories and tags and a Google search functionality. This is pretty easy to do with the free Google custom search, which requires only 3 simple steps to set up:</p></div>

<div class="fix-7x-12 toCenter mx-0 px-0 w3-medium">
<p>1.	Go to Google custom search’s website at <a href="https://cse.google.com" class="blue" rel="nofollow">cse.google.com</a>.</p>
<p>2.	Create a new search engine. Let Google know the name of your site and the language of the posts.</p>
<p>3.	Copy the script code and paste it into your page layout.</p>
</div>

<div class="fix-7x-12 toCenter mb-5 w3-medium">
<p>It’s super easy and quick. Later, you can tweak the advanced setting even further to include things like image search, safe search, and other tweaks, such as limiting the regions. Since Google is going to be serving the search results, searchers will also have the option to search the entire web.</p> 
<p>Jekyll actually allows for a simple <a href="https://blog.webjeda.com/instant-jekyll-search/" class="pinklink" rel="nofollow">instant search</a> that displays the search result “live” as the search phrase is being typed. It is pretty neat and easy to make, without the need for JQuery or plug-ins. I might create one in the near future, but for now I think the search page will have to do.</p>
<p>So where is this super simple search page, you ask? You can access it by clicking the "Search" tab on the top of the site, or... you can just follow the link below and see for yourself:</p>
</div>

<div class="fix-7x-12 toCenter mb-5 w3-medium"><a href="https://fingertip.top/search/" class="pinklink" rel="nofollow">www.fingertip.top/search/</a></div>
