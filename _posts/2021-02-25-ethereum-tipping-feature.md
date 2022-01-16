---
layout: post-plain
author: Lovelli Fuad
title: "Create a MetaMask Tipping Button and Start Collecting Ether"
tagline: Are you ready to tip in Ether?
lead: "Yet another way to make it easier for the audience to support their favourite content creator."
description: A mini guide to coding your own ETH tipping button. So simple it will only take you a bag of chips to complete. 
permalink: blog/ethereum-tipping-feature
date: 2021-02-25 19:00
main-categories: [tips]
other-categories: [guide, code snippets]
tags: [beginners, make]
lang: en
featured-image: snacks-in-vending-machine.png
featured-image-alt: The most popular vending machine snacks lining up inside a vending machine. 
---
<!-- Banner coded manually -->
<section class="container mt-10 mb-8">
    <div class="py-20 bg-size-cover bg-position-bottom-center d-flex align-items-end container-fluid" data-bg-src="https://fingertip.top/assets/image/snacks-in-vending-machine.png" style="min-height: 50vh; background-image: url(&quot;https://fingertip.top/assets/image/snacks-in-vending-machine.png&quot;);" data-aos="fade-down" data-aos-delay="250">
        <div class="container">
            <div class="row align-items-baseline mb-5 ps-xl-4 ps-lg-4 ps-md-4">
            <!-- Display the category -->
                <div class="col-auto">
                  <p class="fs-4 mb-0 text-capitalize bg-bg-1 p-1" data-aos="fade-down" data-aos-delay="0"><a href="" class="text-light-1">Tips + Tricks</a></p>
                </div>
            </div>
            <div class="row">
		<div class="col-12 mb-5 col-md-10 col-lg-9">
			<h2 class="display-3 text-light-1 ps-xl-16 px-lg-12 px-md-8 pt-8" style="-webkit-text-fill-color:orange;-webkit-text-stroke-width: 1px;-webkit-text-stroke-color: white;" data-aos="fade-down" data-aos-delay="250">Create a MetaMask Tipping Button and Start Collecting Ether</h2>
		</div>
			<p class="fs-5 text-light-1 text-xl-center text-xxl-center text-lg-center ps-md-8" data-aos="fade-down" data-aos-delay="250">
				<span class="text-light-1" data-aos="fade-down" data-aos-delay="250">25.02.2021</span> /
				<a href="/categories/beginners" class="text-light-1" data-aos="fade-down" data-aos-delay="250">#beginners</a> <a href="/categories/make" class="text-light-1" data-aos="fade-down" data-aos-delay="250">#make</a>
			</p>
            </div>
        </div>
    </div>
</section>
<!-- Content section -->
<section class="bg-bg-3">
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-lg-10 col-xl-8 col-xxl-7">
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    People are using this altcoin called Ethereum (ETH) as an alternative to fiat money and to Bitcoin in online transactions. It is an awesome currency. It's well and live. And as you will later see, many tokens are built on top the Ethereum blockchain.
                </p>
                <h3 class="mb-4 mb-md-8" data-aos="fade-down" data-aos-delay="0">
                    Tipping is All the Rage These Days
                </h3>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    By adding a code snippet, you can receive Ether as a tip. Anyone with a MetaMask wallet can send it to you in just 'one click'. When your audience clicks the button, MetaMask will open and confirm the amount to be sent to the specified wallet address.
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    For our example, this time we’ve set the amount to be 0.01 ETH and the <b>gas fee</b> to be 50,000 (total TX of 0.001 ETH). The standard is a limit of 21000 and a gas price of 0.00000002 ETH = total of 0.00042 ETH. (It’s not a random number.)
                </p>
		<p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
		    {% include inarticle.html %}
		</p>
                <h3 class="mb-4 mb-md-8" data-aos="fade-down" data-aos-delay="0">
                    The Ether tipping button
                </h3>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    You can create your own button, but the button style that I use below is directly from the MetaMask Github repo:
                </p>
            </div>
            <div class="col-lg-10 col-xl-8 col-xxl-7 pb-8">
                <style>
                    .tip-button{width: 304px;height: 50px;background-size: 100%;background-image: url('/assets/image/3_pay_mm_off.png');cursor: pointer;}
                    .tip-button:hover{background-image:url('/assets/image/3_pay_mm_over.png');}
                    .tip-button:active{background-image:url('/assets/image/3_pay_mm_off.png');}
                </style>
                <div class="tip-button vh-center" data-aos="fade-right" data-aos-delay="50"></div>
                <!-- Metamask Script -->
                <script>
                    var my_address = '0x9f5F4Cf8ed30F04f772B63d02CDB8a9D5732e8BC'
                    var tipButton = document.querySelector('.tip-button')

                    tipButton.addEventListener('click', function() {

                    if (typeof web3 === 'undefined') {
                        return renderMessage('<div class="text-start">You need to install <a class="text-action-4" href="https://metamask.io/"><u>MetaMask</u></a> to use this.
			</a></div>')
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
                    <div class="message mt-8"></div>
            </div>
            <div class="col-lg-10 col-xl-8 col-xxl-7">
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    Try and click it.
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    See what message it gives you.
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    If it says "you need to install MetaMask to use this" you can try installing MetaMask on your browser following <a href="https://metamask.io/download.html" class="text-action-4">this guide</a>, if you want.
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    I'll break down the code used to get a button like that. Please keep in mind that you're free to use the code, as it doesn't belong to me. You don't need my permission to do so, but it'd be really nice if you could link to this post.
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    <b>So, what's in the code?</b>
                </p>
                <p class="pb-5 mb-0 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    A bit of HTML.
                </p>
		    <pre style="font-family:monospace;" class="html4strict mb-0 fs-4" data-aos="fade-right" data-aos-delay="50">		
                    <p class="ps-8 bg-bg-2 mb-0" data-aos="fade-right" data-aos-delay="50">
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">div</span> <span style="color: #000066;">class</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">"tip-button"</span> <span style="color: #000066;">align</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">"center"</span>&gt;&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">div</span>&gt;</span>
<span style="color: #808080; font-style: italic;">&lt;!-- Metamask Script --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">div</span> <span style="color: #000066;">class</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">"message"</span>&gt;&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">div</span>&gt;</span>
		    </p>
		    </pre>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    A bit of CSS: insert button.
                </p>
                    <pre class="actionscript mb-0 fs-4" style="font-family:monospace" data-aos="fade-right" data-aos-delay="50">
                    <p class="ps-8 bg-bg-2 mb-0" data-aos="fade-right" data-aos-delay="50">
.<span style="color: #006600;">tip</span>-<span style="color: #0066CC;">button</span> <span style="color: #66cc66;">&#123;</span>
  <span style="color: #0066CC;">width</span>: 250px;
  <span style="color: #0066CC;">height</span>: 40px;
  margin: 10px;
  background-<span style="color: #0066CC;">size</span>: <span style="color: #cc66cc;">100</span><span style="color: #66cc66;">%</span>;
  background-image: <span style="color: #0066CC;">url</span><span style="color: #66cc66;">&#40;</span><span style="color: #ff0000;">'assets/images/3_pay_mm_off.png'</span><span style="color: #66cc66;">&#41;</span>;
  cursor: pointer;
<span style="color: #66cc66;">&#125;</span>
&nbsp;
.<span style="color: #006600;">tip</span>-<span style="color: #0066CC;">button</span>:hover <span style="color: #66cc66;">&#123;</span>
  background-image: <span style="color: #0066CC;">url</span><span style="color: #66cc66;">&#40;</span><span style="color: #ff0000;">'assets/image/3_pay_mm_over.png'</span><span style="color: #66cc66;">&#41;</span>;
<span style="color: #66cc66;">&#125;</span>
&nbsp;
.<span style="color: #006600;">tip</span>-<span style="color: #0066CC;">button</span>:active <span style="color: #66cc66;">&#123;</span>
  background-image: <span style="color: #0066CC;">url</span><span style="color: #66cc66;">&#40;</span><span style="color: #ff0000;">'assets/image/3_pay_mm_off.png'</span><span style="color: #66cc66;">&#41;</span>;
<span style="color: #66cc66;">&#125;</span>
                </p>
                </pre>
	    <p class="py-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                On an HTML page, the above code goes between the style tags. Just adjust the width and height, depending on the image you're using, or else the image might now show up fully. Change the URL address for the button image to point to the image you want to use.
            </p>
            <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                And then finally, a bit of JavaScript.
            </p>
	        <pre class="javascript mb-0 fs-4" style="font-family:monospace" data-aos="fade-right">
                <p class="ps-8 bg-bg-2 mb-0" data-aos="fade-right">
<span style="color: #339933;">&lt;!--</span> Metamask Script <span style="color: #339933;">--&gt;</span>
<span style="color: #339933;">&lt;</span>script<span style="color: #339933;">&gt;</span>
<span style="color: #000066; font-weight: bold;">var</span> my_address <span style="color: #339933;">=</span> <span style="color: #3366CC;">'0x9f5F4Cf8ed30F04f772B63d02CDB8a9D5732e8BC'</span>
<span style="color: #000066; font-weight: bold;">var</span> tipButton <span style="color: #339933;">=</span> document.<span style="color: #660066;">querySelector</span><span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'.tip-button'</span><span style="color: #009900;">&#41;</span>
&nbsp;
tipButton.<span style="color: #660066;">addEventListener</span><span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'click'</span><span style="color: #339933;">,</span> <span style="color: #000066; font-weight: bold;">function</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
&nbsp;
  <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #000066; font-weight: bold;">typeof</span> web3 <span style="color: #339933;">===</span> <span style="color: #3366CC;">'undefined'</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    <span style="color: #000066; font-weight: bold;">return</span> renderMessage<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'&lt;div align=&quot;center&quot;&gt;You need to install 
    &lt;a href=&quot;https://metamask.io/&quot;&gt;&lt;u&gt;MetaMask&lt;/u&gt;&lt;/a&gt; 
    to use this.&lt;/a&gt;&lt;/div&gt;'</span><span style="color: #009900;">&#41;</span>
  <span style="color: #009900;">&#125;</span>
&nbsp;
  <span style="color: #000066; font-weight: bold;">else</span> <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #000066; font-weight: bold;">typeof</span> <span style="color: #000066; font-weight: bold;">typeof</span> web3 <span style="color: #339933;">!==</span> <span style="color: #3366CC;">'undefined'</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    <span style="color: #006600; font-style: italic;">// Request account access if needed</span>
    ethereum.<span style="color: #660066;">enable</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span>.<span style="color: #660066;">then</span><span style="color: #009900;">&#40;</span><span style="color: #000066; font-weight: bold;">function</span> <span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
      <span style="color: #006600; font-style: italic;">// Acccounts now exposed</span>
      web3.<span style="color: #660066;">eth</span>.<span style="color: #660066;">sendTransaction</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#123;</span>
        to<span style="color: #339933;">:</span> my_address<span style="color: #339933;">,</span>
        from<span style="color: #339933;">:</span> web3.<span style="color: #660066;">eth</span>.<span style="color: #660066;">accounts</span><span style="color: #009900;">&#91;</span><span style="color: #CC0000;">0</span><span style="color: #009900;">&#93;</span><span style="color: #339933;">,</span>
        value<span style="color: #339933;">:</span> web3.<span style="color: #660066;">toWei</span><span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'0.01'</span><span style="color: #339933;">,</span> <span style="color: #3366CC;">'ether'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span> 
        gas<span style="color: #339933;">:</span> <span style="color: #CC0000;">50000</span><span style="color: #339933;">,</span>
      <span style="color: #009900;">&#125;</span><span style="color: #339933;">,</span> <span style="color: #000066; font-weight: bold;">function</span> <span style="color: #009900;">&#40;</span>err<span style="color: #339933;">,</span> transactionHash<span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
  <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">&#40;</span>err<span style="color: #009900;">&#41;</span> <span style="color: #000066; font-weight: bold;">return</span> renderMessage<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'There was a problem!: '</span> <span style="color: #339933;">+</span> err.<span style="color: #660066;">message</span><span style="color: #009900;">&#41;</span>
&nbsp;
        <span style="color: #006600; font-style: italic;">// If you get a transaction hash, you can assume it was sent,</span>
        <span style="color: #006600; font-style: italic;">// or if you want to guarantee it was received, you can poll</span>
        <span style="color: #006600; font-style: italic;">// for that transaction to be mined first.</span>
        renderMessage<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'Thanks for the generosity!!'</span><span style="color: #009900;">&#41;</span>
      <span style="color: #009900;">&#125;</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#125;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
  <span style="color: #009900;">&#125;</span>
&nbsp;
<span style="color: #009900;">&#125;</span><span style="color: #009900;">&#41;</span>
&nbsp;
<span style="color: #000066; font-weight: bold;">function</span> renderMessage <span style="color: #009900;">&#40;</span>message<span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
  <span style="color: #000066; font-weight: bold;">var</span> messageEl <span style="color: #339933;">=</span> document.<span style="color: #660066;">querySelector</span><span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'.message'</span><span style="color: #009900;">&#41;</span>
  messageEl.<span style="color: #660066;">innerHTML</span> <span style="color: #339933;">=</span> message
<span style="color: #009900;">&#125;</span>
<span style="color: #339933;">&lt;/</span>script<span style="color: #339933;">&gt;</span>
                    </p>
                    </pre>
	    </div>
	    <div class="col-lg-10 col-xl-8 col-xxl-7">
                <h3 class="mb-4 mb-md-8" data-aos="fade-down" data-aos-delay="0">
                    How Does It All Work?
                </h3>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    I’ve put a MetaMask pay button on a widget for one of my blogger sites. All the CSS goes into the theme's Edit HTML, while the HTML and JavaScript goes into the HTML/CSS widget area. 
                </p>
	    </div>
	    <div class="col-6 pb-8 text-center">
            <a href="https://lovellifuad.com"><img src="https://i.postimg.cc/RVH0kcLZ/tipping-jar-on-my-blogger-site.png" alt="MetaMask button for the tipping jar" class="border border-action-4 img-fluid" data-aos="fade-down" data-aos-delay="0"></a>
		<figcaption class="mt-5">Use it for the tipping jar</figcaption>
            </div>
	    <div class="col-lg-10 col-xl-8 col-xxl-7">
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    In order for this to work though you need to have:
                </p>
                <ul class="pb-8 text-dark-1 fs-2">
                    <li class="pb-5">A MetaMask wallet</li>
                    <li class="pb-5">MetaMask extension on your browser</li>
                    <li class="pb-0">A blog/site your audience can visit</li>
                </ul>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    Sometimes you'll also get an error message that says "Not enough ETH to send". It's because your account doesn’t have enough ETH to cover the cost of gas. If the gas money > amount of tip, the transaction will also be reverted. 
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    The term <b>gas money</b> doesn't actually refer to the units of gas for a vehicle. It specifies an amount you need to pay for the <b>computation</b>. The price of gas (in <b>gwei</b>) fluctuates daily, but all unused gas money is going to be refunded at the end of a transaction. If the transaction fails, however, you’ll use up all your gas money and receive <u>nothing</u> back.
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    <b>Total cost of transaction or TX = Gas Limit * Gas Price</b>
                </p>
		<p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    In our code, we’ve specified 50,000 as the gas limit (written as just 'gas'). It's the maximum amount of gas money you are willing to spend for the transaction. A standard transaction in ETH will require 21,000. So by Ethereum's standard, if the transfer goes through, the remaining fund (50,000 – 21,000) will be returned to your wallet. 
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    The calculation is different when you're sending <b>tokens</b>, which are smart contracts built using the Ethereum blockchain. There are currently more than 400,000 tokens working their way on the Ethereum main network. The gas money for them can go anywhere between 50,000 to 100,000.   
                </p>
                <h3 class="mb-4 mb-md-8" data-aos="fade-down" data-aos-delay="0">
                    MetaMask on GitHub
                </h3>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    This entire code has been made available on GitHub, so be sure to check out the repo at <a href="https://github.com/MetaMask/TipButton" class="text-action-4">MetaMask/TipButton</a>, where you can choose from more button variations. 
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    Now, what do you say? Ready to collect Ether?
                </p>
            </div>	
        </div>
    </div>
</section>
