## Post #1
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2011-03-03T01:00:06+00:00
- Post Title: Models and animations from PS2 UT?

Hi, I was wondering if anyone here knows how to extract models and animations from the PS2 version of Unreal Tournament. I used UMDextract to extract the largest files I have, which are PSX2SHIP.umd and PSX2LINS.umd (none of the other files are nearly as large, and they weren't UMD files). They contained maps, a few sounds, and some skins. The problem is, they didn't have any models, animations, or any system files. I don't think UMDextract missed anything, because the total size of the extracted files is pretty much the same as the umd files. 

It's been a long time since I extracted all of the files from my game, so I might be missing something important. 
If anyone could point me in the right direction, I'd really appreciate it.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-04T05:00:37+00:00
- Post Title: Models and animations from PS2 UT?

They are in common.lin. Looking how to crack it.

[http://www.oldunreal.com/cgi-bin/yabb2/ ... 1298502114](http://www.oldunreal.com/cgi-bin/yabb2/YaBB.pl?num=1298502114)

This may interest you. I was unable to crack the lin files unfortunately... =/
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-04T14:37:14+00:00
- Post Title: Models and animations from PS2 UT?

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2011-03-04T18:56:27+00:00
- Post Title: Models and animations from PS2 UT?

Thanks, I was missing common.lin.  

In the first link you posted, I got those models from a zip file that had a few models in .max format, which is why I was able to make that pack. I'm mainly looking for the skaarj's animations, and maybe the weapons.

Thanks again for your help.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-04T19:02:50+00:00
- Post Title: Models and animations from PS2 UT?

I see! XD So it was you! So, you can extract data from the LIN files, or is it still a locked format? I am interested if somebody can get the u files from it.
## Post #6
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2011-03-05T03:01:48+00:00
- Post Title: Models and animations from PS2 UT?

I don't know enough to extract the files.   

Hopefully somebody out there does. I do know that the PC version of UT has the PS2ConvertCommandlet that can make .lin files. I'm not sure if it's the same thing that Epic/DE used to make their .lin files, though.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-05T06:46:31+00:00
- Post Title: Models and animations from PS2 UT?

Tested it and it doesn't seem to work. Header information is wrong as is structure. The LIN files in PS2 UT are in fact data containers. Maybe they are converted on top of that but they are definitely a kind of archive/container.

Edit: In any case, I think it may be that few have looked at the LIN files to get exactly what it is doing. Some claim they are not containers when they clearly are, as it indexes and shows the folder structure of its contents. There's a definite indication to botpack.u as well as PS2 specific .u files. I would love to get my hands on this as well being as I play in Unreal a lot.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-10T20:14:24+00:00
- Post Title: Models and animations from PS2 UT?

Small update on this: It almost seems like a fairly common form of compression (zlib?). The files are obviously supposed to be bigger than being let on, suggesting a heavy, almost zip-like compression. I will make a topic regarding it though there have been topics in relation to it. Hopefully somebody can help.
## Post #9
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2011-03-11T17:29:18+00:00
- Post Title: Models and animations from PS2 UT?

That would be great. Thanks again for helping.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-11T20:29:00+00:00
- Post Title: Models and animations from PS2 UT?

No problem,  wish I could figure it out myself but I can mainly only give rough examinations with hex and if tools existed, would have decompressed them. Anyways, if extraction and decompression becomes possible, then all that would be left is UE Viewer. If UE Viewer doesn't support them, I'm certain Gildor will add it, he just wouldn't add lin support since he has nothing on it, he'd likely add support for the decompressed files.
## Post #11
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-06T22:42:49+00:00
- Post Title: Models and animations from PS2 UT?

I figured out the .lin using the ones from Magna Carta PS2 for my research.
data about is can be found [here](http://forum.xentax.com/viewtopic.php?f=10&t=6319) and [Here](http://mce.do.am/forum/25-44-1)

there's an experimental tool for this file format hosted on my site, it MIGHT work on the files AlCapowned descriped too.

no rebuild support yet, im hoping to have that done soon~ish

could someone send me a .lin from UT PS2, i'd like to take a closer look at one
