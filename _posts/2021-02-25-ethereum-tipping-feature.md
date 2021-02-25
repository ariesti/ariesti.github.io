---
layout: post-words
author: Lovelli Fuad
title: "Create a MetaMask Tipping Button and Start Collecting Ether"
tagline: Are you ready to tip in Ether?
lead: "Yet another way to make it easier for the audience to support you as their favourite content creator."
description: A guide to coding your own simple ETH tipping button.
permalink: blog/ethereum-tipping-feature
date: 2021-02-25 19:00
main-categories: [tips]
other-categories: [guide, code snippets]
tags: [ux, make, website]
lang: en
featured-image: snacks-in-vending-machine.png
featured-image-description: This guide will help you make a simple ETH tipping button you can complete in a quick snacking portion. 
featured-image-alt: The most popular vending machine snacks lining up inside a vending machine. 
---
<div class="fix-7x-12 toCenter mb-0 w3-medium">
  <p>People have been using this altcoin as an alternative to fiat money and to Bitcoin in online transactions. Ethereum (ETH) is an awesome currency. Many tokens are built on top the Ethereum blockchain. It’s well and alive.</p>
</div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h2 class="font-weight-bold">Tipping is All the Rage These Days</h2></div>
<div class="fix-7x-12 toCenter mb-0 w3-medium">
  <p>By adding a code snippet, you can receive ETH as a tip. Anyone with a MetaMask wallet can send it to you in just one click. When your audience clicks the button, MetMask will open and confirms the amount to be sent to the specified wallet address.</p>
  <p>For this example, we’ve set the amount to be 0.01 ETH and the gas fee to be 50.000 (total TX of 0.001 ETH). The standard is a limit of 21000 and a gas price of 0.00000002 ETH = total of 0.00042 ETH. (It’s not a random number.) </p></div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h2 class="font-weight-bold">How Does It All Work?</h2></div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h3 class="font-weight-bold">The button</h3></div>
<div class="fix-7x-12 toCenter mb-0 w3-medium">
  <p>You can create your own button. The button style that I used is directly from the MetaMask Github repo, and they’ve got plenty to choose from:</p>
  <p>[live demo]</p>
  <p>Try and click it. See what message it gives you.</p>
  <p>If it says “you need to install MetaMask to use this” you can try installing MetaMask on your browser following <a href="https://metamask.io/download.html">this guide</a>, if you want. </p>
</div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h3 class="font-weight-bold">A bit of HTML</h3></div>
<div class="fix-7x-12 toCenter mb-0 w3-medium" markdown="1">
### A bit of HTML

```html
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

</div>



