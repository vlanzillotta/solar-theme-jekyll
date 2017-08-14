---
title: Superduper
author: Vince
layout: post
permalink: /superduper/
categories:
  - Blog Posts
tags:
  - Apps
  - Hackintosh
  - OS X
---
In my [last post][1], I wrote about how I installed Apple OS X on my gaming PC. What I didn&#8217;t mention, was how I almost ruined the entire install not long after. The only thing that kept my Hackintosh project from becoming two days worth of wasted time was the disk cloning tool, [Superduper][2]. When the build was completed I started installing applications. While doing this, I ran into problems getting Parallels 7 (a virtual machine application) to launch Windows 7*. After adjusting Parallels&#8217;s settings to no success, I knew that it was a problem with the system itself. I decided (poorly) to start adjusting my kernel extensions, thinking that it may be a driver compatibility issue. I then reset my system, and it crashed almost immediately.

The system would make it as far as the Apple logo and then a wall of text would fill the screen and the system would freeze. Even booting in safe mode would crash. I knew I messed up my kernel extensions badly, but the only way to undo my changes would require first getting to my desktop. I was stuck.

This is when Superduper lived up to its name. Instead of trying to boot into my now unfixable OS X install, I was able to boot into the cloned drive that I had made six hours earlier. The drive named &#8216;Recovery&#8217; was listed along with Windows 7 and Lion in my Cerberus boot loader. The &#8216;Recovery&#8217; install had my original, working kernel extensions so it booted up fine and brought me to the desktop without a problem.

I was back to the OS X install from that morning which, while lacking the past six hours of installed applications, was working just as well as the original. This allowed me to run Superduper again, copying the backup drive over the original broken install. The only hitch was that Superduper wrote over the Cerberus boot loader so I had to boot off my Unibeast USB stick to get back into the OS. Once I did that however, I quickly reinstalled Cerberus and all was well again.

This was not my first experience messing up an entire OS install. This was however the first time I had a solid, easy, and reliable safety net. Without Superduper, I probably would have formatted my entire drive and scrapped the entire project in discouragement. Now I feel confident with the knowledge that should I have another catastrophic failure, I have a bootable drive (or two, or three) where my OS remains locked in a safe and stable moment in time.

Note: Thanks to [@vonchez][3] for pointing out the [Carbon Copy Cloner][4] is a free alternative to Superduper. Had I known about Carbon Copy Cloner before the project I would probably be praising it today.

<sub>*I would later fix the issue by turning on hardware virtualization in my BIOS settings.</sub>

 [1]: http://www.objectivev.com/Hackintoshing
 [2]: http://www.shirt-pocket.com/SuperDuper/SuperDuperDescription.html
 [3]: https://twitter.com/#!/vonchez
 [4]: http://www.bombich.com/