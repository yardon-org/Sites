---
title: Sierra_Mk2
date: 2017-12-21 17:12:56
tags:
-   clover,ulysses
categories:
-   hackintosh
---
previously we had a working system, or so I thought. However, the presence of a part 2 implies that not all was well. There were still 3 further issues.

- Airdrop wasn't showing up on my system, despite a compatible bluetooth USB stick.
- Secondly, I wanted to try out Ulysses editor, and it simply wouldn't run.
- NuGet in visual studio would show up in the menu, but fail to connect to the server.

Let's tackle these from easy to not yet solved:

Nuget proved to be a simple matter of adding Visual Studio to the accessibility tab under Security & Privacy. I'd seen this mentioned in the dropbox install and thankfully it worked for Visual Studio.

Sorting Ulysses proved tougher. It wouldn't run under my old El Capitan install either. I was playing around with Clover and managed to render my working boot unusable. Booting from the USB worked fine. Wistfully, I tried to launch Ulysses and to my surprise, it ran! I decided to try a clean install of High Sierra and remove my El Capitan system. This time I endeavored to create a working system working without the aid of Unibeast or Multibeast.

I read the clover Wiki (finally!) and grasped that if I put the required Kexts into the Clover directory on the EFI partition, then there was no need to use multibeast to get networking and sound. A couple of reboots later and I had a pristine High Sierra system up and running, with networking, nVidia graphics and sound (Once I remembered to drop the MATS table). Ulysses was now launching without any issues. When I compared the Clover config.plist between the two systems, it was obvious that Multibeast was setting a lot more options in the ACPI section as well as adding more kexts to my system. I don't know which one caused the issue, but it definitely looks like one or the other was at the root of the Ulysses problem.

Airdrop still isn't working which is a bit of a pain as my broadband upload speed is less than 300 Kb/s, so Airdrop would be a great way to get the pics and videos off my phone. I've already tried the browseallinterfaces route with no luck. I see the airdrop icon in finder, but no descriptive text. Oh, and there's no sign of the hackintosh from iPhone or iPad. As I have a wired ethernet connection, I am not going to fork out for an unneeded wifi card to see if this solves it. For now I'll log onto iCloud and download videos and pictures from there.

The final thing I had to get working was to dual boot of by Solus linux install. It was proving difficult until I discovered the bdmesg utility. It confirmed that I had specified the correct volume UUID but the path to the bootloader could not be found. It was then I discovered that Clover uses **back-slashes** rather than **slashes** in the path...
