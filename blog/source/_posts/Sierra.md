---
title: Sierra
date: 2017-12-21 16:58:57
tags: 
-   clover,
-   bootloader,
-   installation
categories:
-   Hackintosh
---
##(Not so) High Sierra.

For those you who read my previous post, you'll know that I run a dual boot Hackintosh/Solus system by choice. Now I don't know how many of you have been tempted to try a Hackintosh system, but I suspect several of you who have tried, will have hit issues when attempting to boot your system. I will say that one of most useful sites in getting your Hackintosh system off the ground is [TonyMac](www.tonymacx86.com)

Sometimes, it's not as straightforward as the guide implies (yes, I was one of the unlucky ones.) and it's all too easy to flounder. It took me nearly two weeks to get my first install of Mountain lion up and running. It seemed like I'd only just got the hang of it, when Mavericks was released, but that's been covered in my earlier post. It's only recently, after several years, that I've managed to get a grip on Clover.

A lot of it is down to me failing to devote enough time and brainpower to the issue. I've been guilty of the "if it ain't broke..." syndrome. Whenever an upgrade broke something, running Multibeast would usually fix it. Even if I had to use on older version to get my sound working.

A sea change happened with the coming of High Sierra. I'd bypassed an upgrade to Sierra (from El Capitan) but a curiosity to try out .net core 2.0 technologies meant I had to upgrade to High Sierra to install the libraries.

I first tried a simple upgrade on my existing system, but this failed and left the system in an unbootable state. Thankfully my second system was ok and in the light of this I decided to go for a clean install on the first drive.

It took several attempts to create a bootable USB. The faithful old Unibeast just wouldn't create a bootable system. I was debating whether to remove my graphics card, but the fact others had succeeded without doing so spurred me on. (Also, I don't like pulling cards out of a 5 year old PC).

I took the decision to desert Unibeast and try to create a bootable USB myself. It's not that hard actually, (here is a youtube video showing the technique) You basically use apple routines to do so. I installed the latest version of Clover to the USB and tried again. The boot screen lasted a lot longer than it had with Unibeast, but still ended in failure.

TonyMac came to the rescue again, a forum post suggested dropping the MATS table (add description to show where). Finally success! The USB booted up into a High Sierra install screen. I decided to use the new apfs filesystem introduced by Apple at this release. Big mistake. Once High Sierra was installed on the requisite disk, I went into the final reboot and... nothing. The Gigabyte splash screen showed up, then a blank screen. Neither F12 for the boot menu or Del to enter the BIOS made no difference. My machine was stuck and I went to bed that night a worried man.

After a restless night, I decided that logic decreed it had to be something to do with apfs and the only way forward was to physically remove the disk. Being lazy, I crawled under my desk and opened up the PC, trying desperately to remember if it was the Samsung or SanDisk that I'd just formatted. I guessed correctly that it was the Samsung. Once removed, the system booted again!. Thank god I had an external HDD dock so I was able to reformat the Samsung back to HFS+.

A good few minutes of swearing and bending my fingers later, the disk was back in place and I tried again, this time avoiding the conversion to apfs. The install was uneventful. I copied the USB config.plist to the HDD and bingo! High Sierra here we come.

I ran Multibeast to get sound and networking, installed the nVidia graphics driver and... awful graphics. It was then I remembered to add the nVidia web driver flag.

So, I have a working High Sierra install... or do I?
