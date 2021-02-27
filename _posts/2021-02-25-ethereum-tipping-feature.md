---
layout: post-words
author: Lovelli Fuad
title: "Create a MetaMask Tipping Button and Start Collecting Ether"
tagline: Are you ready to tip in Ether?
lead: "Yet another way to make it easier for the audience to support you as their favourite content creator."
description: A mini guide to coding your own ETH tipping button. So simple it will only take you one bag of chips to complete. 
permalink: blog/ethereum-tipping-feature
date: 2021-02-25 19:00
main-categories: [tips]
other-categories: [guide, code snippets]
tags: [ux, make, website]
lang: en
featured-image: snacks-in-vending-machine.png
featured-image-alt: The most popular vending machine snacks lining up inside a vending machine. 
---
<div class="fix-7x-12 toCenter mb-0 w3-medium">
  <p>People are using this altcoin called Ethereum (ETH) as an alternative to fiat money and to Bitcoin in online transactions. It <b>is</b> an awesome currency. It's well and live. And as you will later see, many tokens are built on top the Ethereum blockchain.</p>
</div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h2 class="font-weight-bold">Tipping is All the Rage These Days</h2></div>
<div class="fix-7x-12 toCenter mb-0 w3-medium">
  <p>By adding a code snippet, you can receive Ether as a tip. Anyone with a MetaMask wallet can send it to you in just 'one click'. When your audience clicks the button, MetaMask will open and confirm the amount to be sent to the specified wallet address.</p>
  <p>For our example, this time we’ve set the amount to be 0.01 ETH and the <b>gas fee</b> to be 50.000 (total TX of 0.001 ETH). The standard is a limit of 21000 and a gas price of 0.00000002 ETH = total of 0.00042 ETH. (It’s not a random number.) </p></div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h2 class="font-weight-bold">How Does It All Work?</h2></div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h3 class="font-weight-bold">The Ether tipping button</h3></div>
<div class="fix-7x-12 toCenter mb-0 w3-medium">
  <p>You can create your own button, but the button style that I use below is directly from the MetaMask Github repo:</p>
</div>

<div class="fix-7x-12 toCenter mb-0 w3-medium">
<style>
.tip-button {
  width: 304px;
  height: 50px;
  background-size: 100%;
  background-image: url('/assets/image/3_pay_mm_off.png');
  cursor: pointer;
}

.tip-button:hover {
  background-image: url('/assets/image/3_pay_mm_over.png');
}

.tip-button:active {
  background-image: url('/assets/image/3_pay_mm_off.png');
}
</style>
<div class="tip-button toCenter"></div>
<!-- Metamask Script -->
<script>
var my_address = '0x9f5F4Cf8ed30F04f772B63d02CDB8a9D5732e8BC'
var tipButton = document.querySelector('.tip-button')

tipButton.addEventListener('click', function() {

  if (typeof web3 === 'undefined') {
    return renderMessage('<div align="center">You need to install <a class="blue" href="https://metamask.io/"><u>MetaMask</u></a> to use this.</a></div>')
  }

  else if (typeof typeof web3 !== 'undefined') {
    // Request account access if needed
    ethereum.enable().then(function () {
      // Acccounts now exposed
      web3.eth.sendTransaction({
        to: my_address,
        from: web3.eth.accounts[0],
        value: web3.toWei('0.01', 'ether'), 
        gas: 50000,
      }, function (err, transactionHash) {
        if (err) return renderMessage('There was a problem!: ' + err.message)

        // If you get a transactionHash, you can assume it was sent,
        // or if you want to guarantee it was received, you can poll
        // for that transaction to be mined first.
        renderMessage('Thanks for the generosity!!')
      })
    });
  }

})

function renderMessage (message) {
  var messageEl = document.querySelector('.message')
  messageEl.innerHTML = message
}
</script>
<div class="message"></div>
</div>

<div class="fix-7x-12 toCenter mb-0 w3-medium">
  <p>Try and click it.</p>
  <p>See what message it gives you.</p>
  <p>If it says “you need to install MetaMask to use this” you can try installing MetaMask on your browser following <a class="blue" href="https://metamask.io/download.html"><b>this guide</b></a>, if you want.</p>
  <p>I'll break down the code used to get a button like that. Please keep in mind that you're free to use the code, as it doesn't belong to me. You don't need my permission to use it, but it'd be really nice if you could link to this post.</p>
  <p>So, what's in the code?</p>
</div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h3 class="font-weight-bold">A bit of HTML</h3></div>
<div class="fix-7x-12 toCenter mb-5 w3-medium" markdown="1">
```html
<div class="tip-button" align="center"></div>
<!-- Metamask Script -->
<div class="message"></div>
```
</div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h3 class="font-weight-bold">A bit of CSS: insert button</h3></div>
<div class="fix-7x-12 toCenter mb-0 w3-medium" markdown="1">
```css
.tip-button {
  width: 250px;
  height: 40px;
  margin: 10px;
  background-size: 100%;
  background-image: url('assets/images/3_pay_mm_off.png');
  cursor: pointer;
}

.tip-button:hover {
  background-image: url('assets/image/3_pay_mm_over.png');
}

.tip-button:active {
  background-image: url('assets/image/3_pay_mm_off.png');
}
```
</div>

<div class="fix-7x-12 toCenter mb-0 w3-medium">
  <p>On an HTML page, the above code goes between the style tags. I advise you to adjust the width and height, depending on the image you're using. Change the URL address for the button image to point to the image you want to use.</p>
</div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h3 class="font-weight-bold">A bit of JavaScript</h3></div>
<div class="fix-7x-12 toCenter mb-5 w3-medium" markdown="1">
```javascript
<!-- Metamask Script -->
<script>
var my_address = '0x9f5F4Cf8ed30F04f772B63d02CDB8a9D5732e8BC'
var tipButton = document.querySelector('.tip-button')

tipButton.addEventListener('click', function() {

  if (typeof web3 === 'undefined') {
    return renderMessage('<div align="center">You need to install <a href="https://metamask.io/"><u>MetaMask</u></a> to use this.</a></div>')
  }

  else if (typeof typeof web3 !== 'undefined') {
    // Request account access if needed
    ethereum.enable().then(function () {
      // Acccounts now exposed
      web3.eth.sendTransaction({
        to: my_address,
        from: web3.eth.accounts[0],
        value: web3.toWei('0.01', 'ether'), 
        gas: 50000,
      }, function (err, transactionHash) {
        if (err) return renderMessage('There was a problem!: ' + err.message)

        // If you get a transaction hash, you can assume it was sent,
        // or if you want to guarantee it was received, you can poll
        // for that transaction to be mined first.
        renderMessage('Thanks for the generosity!!')
      })
    });
  }

})

function renderMessage (message) {
  var messageEl = document.querySelector('.message')
  messageEl.innerHTML = message
}
</script>
```
</div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h2 class="font-weight-bold">Using It on Blogger Sites</h2></div>
<div class="fix-7x-12 toCenter mb-0 w3-medium" markdown="1">
I’ve put one button on a widget for one of my blogger sites. All the CSS goes into the theme’s Edit HTML, while the HTML and JavaScript goes into the HTML/CSS widget area. 

In order for this to work though you need to have:

- A MetaMask wallet
- MetaMask extension on your browser
- A blog/site your audience can visit

Sometimes you'll also get an error message that says "Not enough ETH to send", it is because your account doesn’t have enough ETH to cover the cost of gas. If the gas money > amount of tip, the transaction will also be reverted.  

The term **gas money** doesn't actually refer to the units of gas for a vehicle. It specifies an amount you need to pay for the *computation*. The price of gas (in *gwei*) fluctuates daily, but all unused gas money is going to be refunded at the end of a transaction. If the transaction fails, however, you’ll use up all your gas money and receive <u>nothing</u> back.

<blockquote class="twitter-tweet"><p lang="und" dir="ltr"><a href="https://t.co/wrPLEI6lcd">pic.twitter.com/wrPLEI6lcd</a></p>&mdash; Lovelli Fuad (@lovellifuad) <a href="https://twitter.com/lovellifuad/status/1364992555616636932?ref_src=twsrc%5Etfw">February 25, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<code>A brief moment of horror.</code>

**Total cost of transaction or TX = Gas Limit * Gas Price**

In our code, we’ve specified 50000 as the gas limit (written as just 'gas'). It's the maximum amount of gas money you are willing to spend for the transaction. A standard transaction in ETH will require 21000, so by Ethereum's standard, if the transfer goes through the remaining (50000 – 21000) will be returned to your wallet. 

Our calculation is different when you’re sending <b>tokens</b>. The gas money can go anywhere between 50000 to 100000. 
</div>
<div class="fix-7x-12 toCenter mb-5 w3-medium"><h2 class="font-weight-bold">MetaMask on GitHub</h2></div>
<div class="fix-7x-12 toCenter mb-0 w3-medium" markdown="1">

This entire code has been made available on GitHub, so be sure to check out the repo at <a href="https://github.com/MetaMask/TipButton" class="pinklink">MetaMask/TipButton</a>. Kudos to MetaMask. 

Of course there are ways we can make this code better, but that requires a bit of payment testing to get right. 

So, what do you say? Ready to collect Ether? 
</div>
