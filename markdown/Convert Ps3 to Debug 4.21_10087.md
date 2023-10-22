## Post #1
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-26T17:08:53+00:00
- Post Title: Convert Ps3 to Debug 4.21

Ok here is a guide on how to convert your ps3 to a debug unit so you can debug ps3 games.
Things this will let you do.
1.Dump the entire ps3 ram while a game runs.
2.Step through ps3 code to debug a game
3.Edit the ram in real time and make codes or other things.

Things you need.
#1 - PS3 on 3.55 firmware.
easiest way is to use the 999 downgrade from the rebug people. [http://rebug.me/](http://rebug.me/)
#2 You need to enable the qa flag on your ps3 while in 3.55 firmware.
To do this you need to use [http://rebug.me/toggle-qa/](http://rebug.me/toggle-qa/)
#3 Dump your ps3 root key
To do this you need [http://wololo.net/downloads/index.php/download/1385](http://wololo.net/downloads/index.php/download/1385)
#4 ok now that your console is qa flagged and you have dumped your root key go ahead and install the rebug firmware REBUG_4.21.2_REX_PS3UPDAT.PUP
#5 now you need to install the rebug toolbox [http://rebug.me/rebug-toolbox/](http://rebug.me/rebug-toolbox/)
#6 
> Use EXPORT FLASH TO FILE function found in the UTILITIES menu to dump your NOR/NAND to dev_usb000 and then use c2d.exe(http://www.sendspace.com/file/fi9pp8) to convert your dump to DEX.
>
> Rename your original CEX dump to CEX-FLASH.EID0.NORBIN (16mb) or CEX-FLASH.EID0.NANDBIN (239mb or 256mb)
>
> Rename your converted DEX dump to DEX-FLASH.EID0.NORBIN (16mb) or DEX-FLASH.EID0.NANDBIN (239mb or 256mb)
>
> Once you have prepared your NOR/NAND dumps place them on a USB device and connect it to dev_usb000.
>
> Now that you have your valid dumps named properly and connected to dev_usb000 it is a simple as selecting the option and following the onscreen prompts. Takes less than 10secs once you have your dumps prepared.

Now that you have switched to the debug kernel you can run the ps3 sdk tools and all of their functions with no problem.

Note to debug a game it must have an update. Then you must grab the games update eboot and convert it to a debug eboot before launching the game to debug it.
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-01-27T17:39:11+00:00
- Post Title: Convert Ps3 to Debug 4.21

Sounds useful. Now if only I had a working PS3 (since it YLOD'd on me again)...
## Post #3
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-05-21T05:07:33+00:00
- Post Title: Convert Ps3 to Debug 4.21

[more info](http://www.youtube.com/embed/lDgyyiSDU30)
