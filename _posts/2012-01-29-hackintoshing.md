---
title: Hackintoshing
author: Vince
layout: post
permalink: /hackintoshing/
categories:
  - Blog Posts
tags:
  - Hackintosh
  - Weekend project
---
A few weeks ago I made it a weekend project to get Apple OS X Lion installed on my custom built gaming PC.

## Why?

  1. Because I can. I&#8217;ve been reading about &#8220;Hackintoshing&#8221; for a while now and after seeing that my hardware **should** work with OS X I figured why not try it out?

  2. Power. At the time, my main computer was a 2011 Mac Mini and while it&#8217;s great and has not slowed down on me yet, I saw my quad core gaming PC sitting next to it and wondered just how speedy it could run my preferred OS if set up properly.

  3. Simplicity. As mentioned, I was running two systems. My main computer (the Mac Mini) and my gaming rig (the PC). That meant having twice as many wires behind my desk and running two systems in one space. I hoped that having one machine for both purposes could make for a more elegant solution

## The Prep

**The Hardware**

Here is what I had to work with.

  * The Mac Mini
  * The PC
  * A handful of USB sticks
  * Blank DVDs
  * Four internal hard drives.

**The Software**

  * OS X 10.6 Snow Leopard (DVD)
  * OS X 10.7 Lion (Image file purchased from the Mac App Store)
  * Unibeast and Multibeast (More on these later)

## Resources

In the prior weeks I compiled a pretty good list of bookmarked tutorials and reference material.

  * [Reddit.com/r/Hackintosh][1]
  * [Tonymacx86 tutorial for getting snow leopard installed with iboot and Multibeast][2]
  * [Tonymacx86 tutorial for going from snow leopard to lion][3]
  * [A list of compatable hardware][4]
  * [Unibeast instructions][5]
  * [Drivers for my video card][6]
  * [Multibeast][7]

## The Build

About a month ago I built my gaming PC so this is what I started out with.

  * Motherboard : Asus P8P67 LE
  * Video card: EVGA Gefore GTX 560ti
  * Memory : 16gb Kingston Hyper X
  * Hard Drive 1 : 1.5TB Main Windows 7 drive
  * Hard Drive 2: 500GB secondary drive (carry over from previous PC)

The first step was to open up the system and unplug everything from the motherboard except for the power supply, the video card and the 500GB hard drive. The idea was to eliminate as many points of failure as possible. Once the OS was installed I could start attaching peripheral items like the DVD drive and the Windows hard drive. The Windows drive would be the last thing to be attached once I was sure the system was running smoothly.

Next was to go into the BIOS and set up a few key things. The main two settings that must be set are the boot order and to set *SATA* mode to *ACHI*. I&#8217;m not really sure what setting the *SATA* mode to *ACHI* does, but according to this [tutorial][2], it&#8217;s a must.

Once the BIOS was set up, it was time to boot off my Unibeast thumb drive. To create this drive I downloaded Unibeast and used [this][5] tutorial to create a USB drive that would both act as a boot loader and the system install disk. This process was not as easy as expected. I had to re-run Unibeast to make the USB stick about 4 times before the software would install OS X all the way to 100%. Each time booting off the thumb drive I had to add the boot parameter &#8220;GraphicsEnabler=No&#8221; to stop OS X from trying to use my video card for any sort of graphic acceleration. If I did not set this every time, the system would crash because OS X has no native support for the GTX 5xx series of video cards. Eventually though, the install completed and I was presented with a low resolution but functional OS X interface.

The next step was to install kernel extensions or KEXT files that would tell OS X how to use my motherboard and video card. I downloaded Multibeast, which contains a variety of KEXT files for many types of hardware. I consulted the [compatibility list][4] for which KEXT files to install for my specific motherboard. To get video acceleration working I had to use [GTX 5XX Enabler][6]. This was also the the best time to install a boot loader so I could pick which OS I would want to use once I pluged my main Windows drive back in.

<div id="attachment_48" style="width: 310px" class="wp-caption alignnone">
  <a href="http://www.objectivev.com/wp-content/uploads/2012/01/Screen-Shot-2012-01-28-at-10.45.57-AM.png" rel="lightbox[15]" title="Screen Shot 2012-01-28 at 10.45.57 AM"><img src="http://www.objectivev.com/wp-content/uploads/2012/01/Screen-Shot-2012-01-28-at-10.45.57-AM-300x188.png" alt="" title="Screen Shot 2012-01-28 at 10.45.57 AM" width="300" height="188" class="size-medium wp-image-48" /></a>
  
  <p class="wp-caption-text">
    Multibeast options
  </p>
</div>

I used the boot loader Chimera that came with Multibeast and installed it along with the KEXT files. Chimera also set up a config file to control boot options. I could now turn GraphicsEnabler to “YES” and have the system use my video card to help with graphic acceleration.

SUCCESS&#8230;so far.

The system was operational. Sound, check, graphics, check, ethernet, check. As far as the OS was concerned I was using a Mac Pro from early 2008 with 2011&#8217;s processor and video card. I was even confident enough to plug the Windows drive back in. It showed up along side OS X in the boot loader and worked as well as ever.

<div id="attachment_34" style="width: 310px" class="wp-caption alignnone">
  <a href="http://www.objectivev.com/wp-content/uploads/2012/01/IMG_00531.jpg" rel="lightbox[15]" title="IMG_0053"><img src="http://www.objectivev.com/wp-content/uploads/2012/01/IMG_00531-300x225.jpg" alt="" title="IMG_0053" width="300" height="225" class="size-medium wp-image-34" /></a>
  
  <p class="wp-caption-text">
    OS X running on my PC
  </p>
</div>

<div id="attachment_35" style="width: 310px" class="wp-caption alignnone">
  <a href="http://www.objectivev.com/wp-content/uploads/2012/01/IMG_00551.jpg" rel="lightbox[15]" title="IMG_0055"><img src="http://www.objectivev.com/wp-content/uploads/2012/01/IMG_00551-300x225.jpg" alt="" title="IMG_0055" width="300" height="225" class="size-medium wp-image-35" /></a>
  
  <p class="wp-caption-text">
    About This Mac system information screen
  </p>
</div> I was even able to get dual displays working.

Now what is missing? Two things I need 1) Bluetooth for my wireless mouse and 2) a wifi adapter since my Linksys adapter is not supported by OS X. I consulted the compatibility list and selected the [TRENDnet TEW-649UB][8] wifi adapter and a [Belkin Bluetooth adapter][9]. The Bluetooth adapter was plug and play while the wifi adapter required software drivers from TRENDnet to work. Low and behold everything worked.

  * Graphics :check
  * Sound (headphone & mic): check
  * Wifi: check
  * Bluetooth: check
  * USB ports : check

I threw in two more 2TB hard drives. One as a shared media drive and one as a backup drive. I was done.

## The Safety Net

After everything was installed properly the main OS only took up about 6GB. Now would be a good time to backup the past 24 hours of work. I installed the free version of [Superduper][10], a drive cloning app that makes a bootable copy of your hard drive. I partitioned 50gb out of my backup drive and cloned the OS install to the new partition. Now when booting up the boot loader shows 3 items &#8220;OS X&#8221;, &#8220;Windows 7&#8243; and &#8220;Recovery&#8221; which is what I named the backup copy.

The rest of the backup drive would be used for Time Machine, a chronological backup solution built into OS X. Time Machine is good for when you mess up something and have to &#8220;rewind&#8221; the system an hour or a day. The recovery drive made by Superduper is for when you mess up the system so bad you can&#8217;t even access the hard drive. More on that another time.

## The Test

As of today the build remains solid, no kernel panics, no power issues, no craziness of any kind yet. The real test is to see how stable/usable this build is for at least one month. At the end of that month, if everything is still working well, I will be looking for something to do with the Mac Mini. Most likely it will be sold.

<div id="attachment_53" style="width: 310px" class="wp-caption alignnone">
  <a href="http://www.objectivev.com/wp-content/uploads/2012/01/IMG_0058.jpg" rel="lightbox[15]" title="IMG_0058"><img src="http://www.objectivev.com/wp-content/uploads/2012/01/IMG_0058-300x225.jpg" alt="" title="IMG_0058" width="300" height="225" class="size-medium wp-image-53" /></a>
  
  <p class="wp-caption-text">
    Running Hackintosh with two monitors next to my Mac Mini
  </p>
</div>

 [1]: http://www.reddit.com/r/hackintosh/
 [2]: http://tonymacx86.blogspot.com/2010/04/iboot-Multibeast-install-mac-os-x-on.html
 [3]: http://tonymacx86.blogspot.com/2011/07/xmove-Multibeast-install-os-x-107-lion.html
 [4]: http://wiki.osx86project.org/wiki/index.php/HCL_10.7.2
 [5]: http://tonymacx86.blogspot.com/2011/10/Unibeast-install-mac-os-x-lion-using.html
 [6]: http://www.osx86.net/downloads.php?do=file&id=2074
 [7]: http://tonymacx86.blogspot.com/2010/02/Multibeast-ultimate-post-installation.html
 [8]: http://www.tigerdirect.ca/applications/SearchTools/item-details.asp?EdpNo=5321189
 [9]: http://www.tigerdirect.ca/applications/SearchTools/item-details.asp?EdpNo=4214435&CatId=906
 [10]: http://www.shirt-pocket.com/SuperDuper/SuperDuperDescription.html