---
layout: post
author: Lovelli Fuad
title: "Got My Very First Dev Swag in the Mail. It's Hacktoberfest No. 5!"
description: I joined Hacktoberfest last year and got my first dev swag this year. You too can take part in this community event this October. 
permalink: hacktoberfest-dev-swag
date: 2019-03-29 05:45 PM
updated: 2020-03-04 01:21 AM
updated-by: "Bob Bock"
categories: [community/events, tutorials]
tags: [beginners, open-source, reviews]
lang: en
featured-image: 2-ftt.png
featured-image-description: S-S-S-SWAAAG!
featured-image-alt: S-S-S-SWAAAG!
---

<div class="mb-4 lead"><b>Disclaimer:</b> The community event ended two years ago in October, but my first dev swag was just delivered to me a few <b>business days</b> ago.</div>

<hr class="mt-2 mb-4">

Hacktoberfest motivates newbies to contribute to **open source projects**. In case you need to know, last year was my first time participating fully, and I did not regret a minute of it. Although come to think of it now, there were a few things I could have done to maximize my participation. 

If you’ve been thinking about collaborating with others, open source is a great start. Every year since 2013, the community celebrates open source software by rewarding contributors during the month of October. 

Don’t worry so much about the coding bits, because the focus of Hacktoberfest is *to contribute to a software project*. It is first-timer friendly, and you are not limited to only your coding skill sets. Any area where you might be able to help is within your reach: social media marketing, copywriting, editing, design, testing, bug reporting, business, etc.

Okay, maybe business is still a little way off, but here are some things you can do to get started (right away):

<div class="points mt-4 ml-3"><b><span class="grey">Check for broken and/or outdated links.</span></b> This is mostly what I did. I contributed to a WebDevStudio project creating WordPress starter themes, so there were plenty of links referencing WordPress’s Codex, which has moved to a different subdomain but still at Wordpress.org. Some of these links are not broken; they simply need to be updated to point to the most recent webpages.</div> 

<div class="points mt-2 ml-3"><b><span class="grey">Fix the typos.</span></b> Typos are bugs! And you need to fix them. Content can be buggy, too, especially if the website is localized into other languages. Go for the obvious grammar and misspelling ones, rather than the more subtle issues of style.</div> 

<div class="points mt-2 ml-3 mb-4"><b><span class="grey">Make sure the viewport is for responsive pages.</span></b> Modern websites are built with mobile in mind, so they've got to be responsive and stay responsive. You should be able to go over the website code and check if the viewport meta tag is correctly set up.</div>

You can (and you should) copy your projects's URL and paste it on to any mobile SEO tool to check for things like the viewport tag, load time, image optimization, etc. is correctly used. If the viewport is not, for example, responsive, that could just be your very first PR.

{% highlight ruby %}
  <meta name=viewport content="width=device-width, initial-scale=1">
{% endhighlight %}

<div class="mt-4 mb-4"><h2><span class="grey">Making Your First Ever 'Pull Request'</span></h2></div>

Luckily, I have read about how to make a Pull Request/PR years back when I first learned to use Git and GitHub. So I wasn’t all that unfamiliar with the way open source projects work, but like I said, it was years ago. To make your first real PR, you need to learn to create a PR on GitHub. And you need to practice. 

There’s a bunch of very neat tutorials from Hacktoberfest’s host, Digital Ocean. I encourage you to go to their website and read their <a href="https://www.digitalocean.com/community/tutorial_series/an-introduction-to-open-source" class="pinklink">Introduction to Open Source</a> thoroughly before installing Git on your computer. Follow the Git installation guide <a href="https://www.digitalocean.com/community/tutorials/how-to-contribute-to-open-source-getting-started-with-git#contributing-to-open-source-projects" class="blue">there</a>, too. 

But if installing Git looks like a lot of extra work, you can definitely skip it. There are open source projects, such as the freeCodeCamp repository, that will let you help improve articles by editing <a href="https://medium.freecodecamp.org/hacktoberfest-2018-how-you-can-get-your-free-shirt-even-if-youre-new-to-coding-96080dd0b01b" class="blue"><b>directly from your browser</b></a>. 

Learning about open source projects and how to contribute is only the beginning. You still need to find projects you can actually contribute to. Many are reserved for first-timers to take part in during the Hacktoberfest community event. And if you do a bit of internet search, you will find many such project lists.

Just need to do some digging to find those repos. 

These are some other interesting first-timer guides to open source projects. Each includes links to where to find your first:

* <a href="https://auth0.com/blog/a-first-timers-guide-to-an-open-source-project/" class="pinklink">A First Timer's Guide to an Open Source Project</a> from <code>AuthO</code>

* <a href="https://opensource.guide/" class="pinklink">Open Source Guide]() and <a href="https://opensourcefriday.com/#participate" class="pinklink">Open Source Friday</a> from <code>GitHub</code> and friends

* <a href="https://blog.devcenter.co/contributing-to-your-first-open-source-project-a-practical-approach-1928c4cbdae" class="pinklink">Contributing to Your First Open Source Project: A Practical Approach</a>

<div class="mt-4 mb-4"><h2><span class="grey">How to Participate</span></h2></div>

As you can probably imagine, getting started is easy as 1-2-3: 

1.	Before registering for Hacktoberfest, you need to setup a GitHub account that you’ll use during the community event. You can do that from GitHub: <a href="https://github.com/join" class="blue">github.com/join</a>.

2.	Register through the Hacktoberfest registration page. 

3.	Make 5 PRs and follow the instructions to receive your dev swag. 

But if you tried to contribute to these open source projects outside of Hacktoberfest it would have taken you some time, and probably more than 5 issues, before your contribution is considered "good enough." After my first contribution in 2018, I still return to the projects to see how else I can make myself useful. So here's some of my after thoughts:

<div class="mt-4 mb-4"><h4><span class="grey">It is not enough to just interact on GitHub.</span></h4></div>

If your project has a mailing list, you should definitely join it. In theory, reading up on the project’s reporting guideline, Slack channel discussion, and developer forums would help you select a decent issue to work on. The project’s contributing guideline also would lay out the basics to help you prepare your PRs. 

<div class="mt-4 mb-4"><h4><span class="grey">Ask for help from other developers.</span></h4></div>

This is hard. But it’s one of the main benefits of working on open source projects: you get to work with other developers. When you need (and you will need it) some help, you should ask for assistance from other developers and communicate. This ensures that you are able to work on the items you have set out to work on. They can point you to the right direction or advice you on where to look for stuff. 

<div class="mt-4 mb-4"><h4><span class="grey">Get familiar with the community swag lists.</span></h4></div>

Turns out that the open source community has a culture of rewarding contributors with swag! Each of the companies have their own requirement for the free gifts they give for your time and your help. Why not make the most of your contributing month? During Hacktoberfest, try to contribute to the companies that offer dev swags. They could also motivate you to continue contributing regularly to projects that match your schedule and qualifications. 

<div class="mt-4 mb-4"><h4><span class="grey">Consider creating your own open source projects.</span></h4></div>

If existing projects are no longer sufficient, you’d want to consider creating your own. With the right dev swags (and marketing mix) you might be able to attract rising talents that could lead to somewhere amazing. 


<div class="mt-4 mb-4"><h2><span class="grey">It's Not All About the S-S-SWAAAG! But when it is, it's lit...</span></h2></div>

<figure class="figure-img img-fluid rounded mb-4">
  <img src="/assets/image/2-ftt.png" class="figure-img img-fluid rounded" alt="Finally got my swag in the mail">
  <p class="alpha">My first dev swag</p>
</figure>

This issue has come up in online forum discussions. After some time, the package tracking for Hacktoberfest swag became unavailable.. so people weren't able to find out where their package was or where the rewards got stuck. I was told that my package was already dispatched in time but was rejected due to conflict of address. The design team had to resend my package, and luckily the second time was a charm. 

Indonesian customs fee for imported goods does not charge any item that is less than $100 in value, but somehow my dev swag was held in customs, as proven by the customs tariff receipt handed to me. I had to pay about $1.5 for customs, which is hilarious! The package itself is not even a taxable item. It took my swag about one month to make it to the post office.  
