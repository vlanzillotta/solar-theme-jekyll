---
title: Saving your home IP to dropbox.
author: Vince
layout: post
permalink: /saving-your-home-ip-to-dropbox/
categories:
  - Blog Posts
tags:
  - Bash
  - Dropbox
---
Ever need to know your home IP at another computer? Sure you have. Maybe you&#8217;re at work and need to SSH home to check up on something, or pull a file from your personal FTP server.

But what if your home IP address has changed since you last logged in? Guess you just have to wait until you get home, check your new IP address, write it down, and hope that the next time you need it, it hasn&#8217;t changed on you again.

Why not set up a two line basic shell script that grabs your IP address and saves it to a file in your Dropbox?

I use [canihazip.com/s/][1] because it returns nothing but my IP address. No HTML.

    #! /bin/bash
    curl -o  ~/Dropbox/myHomeIP.txt canihazip.com/s/
    

That&#8217;s it! Now you can add this to your [Cron][2], or any scheduler, for an always-up-to-date file that will be on every computer you use with your home IP address

Here is my Cron for this script. I like the script to be run every hour, every day, every week, and every month.

    0 * * * * ~/getremoteip.sh
    

It&#8217;s also worth mentioning that if your computer ever gets stolen, it will update this file within an hour and get the ball rolling on getting your property back.

 [1]: http://canihazip.com/s/
 [2]: http://en.wikipedia.org/wiki/Cron