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
    <div class="py-20 bg-size-cover bg-position-bottom-center d-flex align-items-end container-fluid" data-bg-src="https://fingertip.top/assets/image/snacks-in-vending-machine.png" style="min-height: 50vh; background-image: url(&quot;https://fingertip.top/assets/image/snacks-in-vending-machine.png&quot;);">
        <div class="container">
            <div class="row align-items-baseline mb-5 ps-xl-4 ps-lg-4 ps-md-4">
            <!-- Display the category -->
                <div class="col-auto">
                  <p class="fs-4 mb-0 text-capitalize" data-aos="fade-down" data-aos-delay="0"><a href="" class="text-light-1">Tips</a></p>
                </div>
            </div>
            <div class="row">
		<div class="col-12 mb-5 col-md-10 col-lg-9">
			<h2 class="display-3 text-light-1 ps-xl-16 px-lg-12 px-md-8 pt-8" style="-webkit-text-fill-color:orange;-webkit-text-stroke-width: 1px;-webkit-text-stroke-color: white;" data-aos="flip-left" data-aos-delay="250">Create a MetaMask Tipping Button and Start Collecting Ether</h2>
		</div>
			<p class="fs-5 text-light-1 text-xl-center text-xxl-center text-lg-center ps-md-8" data-aos="fade-down" data-aos-delay="250">
				<span class="text-light-1" data-aos="fade-down" data-aos-delay="250">20 Feb, 2021</span> /
				<a href="/categories/beginners" class="text-light-1" data-aos="fade-down" data-aos-delay="250">#beginners</a> <a href="/categories/make" class="text-light-1" data-aos="fade-down" data-aos-delay="250">#make</a>
			</p>
            </div>
        </div>
    </div>
</section>
<!-- Content section -->
<section class="bg-bg-3 pb-8">
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
                    For our example, this time we’ve set the amount to be 0.01 ETH and the <b>gas fee</b> to be 50.000 (total TX of 0.001 ETH). The standard is a limit of 21000 and a gas price of 0.00000002 ETH = total of 0.00042 ETH. (It’s not a random number.)
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
                <div class="tip-button vh-center"></div>
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
                    If it says “you need to install MetaMask to use this” you can try installing MetaMask on your browser following <a href="https://metamask.io/download.html" class="text-action-4">this guide</a>, if you want.
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    I'll break down the code used to get a button like that. Please keep in mind that you're free to use the code, as it doesn't belong to me. You don't need my permission to do so, but it'd be really nice if you could link to this post.
                </p>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    <b>So, what's in the code?</b>
                </p>
                <p class="pb-5 mb-0 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    A bit of HTML
                </p>
		    <pre style="font-family:monospace;" class="html4strict mb-0 fs-4">		
                    <p class="ps-8 bg-bg-2 mb-0">
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">div</span> <span style="color: #000066;">class</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">"tip-button"</span> <span style="color: #000066;">align</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">"center"</span>&gt;&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">div</span>&gt;</span>
<span style="color: #808080; font-style: italic;">&lt;!-- Metamask Script --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">div</span> <span style="color: #000066;">class</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">"message"</span>&gt;&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">div</span>&gt;</span>
		    </p>
		    </pre>
                <p class="pb-8 text-dark-1 fs-2" data-aos="fade-down" data-aos-delay="50">
                    A bit of CSS: insert button.
                </p>
                <pre class="actionscript mb-0 fs-4" style="font-family:monospace;">
                <p class="ps-8 bg-bg-2 mb-0">
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
            </div>
        </div>
    </div>
</section>

