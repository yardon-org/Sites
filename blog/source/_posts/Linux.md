---
title: The best (and worst) of Linux
date: 2017-12-25 11:44:35
tags:
---
##Linux The best (and Worst)##
I was recently reminded of why Linux is so good. If you read my last ~~rant~~ post you'll know I am currently without Broadband, and if it wasn't for my brilliant next door neighbour allowing me to access his Wifi, I'd be up the creek without a paddle.

I managed to procure a wifi dongle, but on Solus, I was unable to compile the driver - I didn't have the "make" package installed for a start. If I'd been running windows then no doubt the divers would have been pre-installed, but as this adds to bloat, it doesn't qualify as a bad point.

I was amazed that I was able to set up a HotSpot on my phone and tether it via bluetooth through linux (particularly as it's an iPhone). This gave me access to the internet and the solus repositories. After installing make and the linux headers I was ready to try again (yes, my data allowance took a battering!)

The install.sh script failed again with a wonderfully helpful error message stating unable to continue due to error 2... This is what I hate about Linux.

Fear not, the Solus forums had an answer and a link to a git repository holding the realtek wifi drivers. This worked and I'm now ~~crippling~~ make full use of my neighbours bandwith.

While we're at it, there is another thing I hate when using Linux. On my OSx system I have a Ubuntu server VM set up to provide access to an external USB HDD formatted using ext4. This is served via SMB. Why oh why doesn't the Samba documentation mention SMB users. Yes, you have to set one up if you don't want to use guest access. Took me an afternoon to figure out why I couldn't log in to the share using my Solus user.