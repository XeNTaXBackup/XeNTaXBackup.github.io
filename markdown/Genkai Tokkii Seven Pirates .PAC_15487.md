## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-11-13T04:22:58+00:00
- Post Title: Genkai Tokkii Seven Pirates .PAC

Can anyone help create scripts for this new format? I can't find anything for it that works. Thanks!

[https://mega.nz/#!DwtUiCBC!5DwxDfpmMs3t ... u7iW7sWQkk](https://mega.nz/#!DwtUiCBC!5DwxDfpmMs3tVqn_MwalSudPdbLZdyckEu7iW7sWQkk)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-13T08:07:25+00:00
- Post Title: Genkai Tokkii Seven Pirates .PAC

yeah, scripts! As you may know a full format analysis is required before you can create a script.
We've some capable "scripting heroes" in this forums but they can't/they won't care for any format
as you may have experienced.

A last time (hopefully) I'll show how easy it is to obtain the model by yourself using hex2obj;
it's so simple, take a look (ok, the uvs are a little bit harder):

And no, it's not a matter of finding/entering random numbers. People who think so are really lost, imho,
and damned to wait for someone who creates a script for them.  

CHARA001_MODEL001.PAC
Using a hex editor search binary for 000001000200, there's 9 finds, so probably nine submeshes 
to be present in this file (0000 0100 0200 represents the face indices (FIs) 0, 1, 2).
From the first find address (0xDA0B0) scroll down the face indices list 'til it's end at 0xDBA41.
Since most 3D formats use shorts (2 bytes -> WORD) as face indices we've to divide the size of this list by 2.

0xDBA42 - 0xDA0B0 = 0x1992 = 6546 -> /2 = 3273
Entering the startaddress and the FIs' count in step 1 and pressing go1 gives us 
the vertex count: 2553

From the upper part of the below picture you can see where the vertices to start and the vertex stride
(= FVFsize) which is 42 here (strange, more common values are 44 or 40 for example).

The pattern this stride is derived from are the 12 zeroes. This is unique for this pac format; other formats
will definitely have other patterns, if any.



7pirates-pac.JPG (179.3 KiB) Viewed 107 times


As for the uvs: they're looking a little bit strange, would take too much time for me to solve this.
Aah, yes, simple enough, enter 18 instead of 16 for the uv pos!
## Post #3
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-12-27T01:30:06+00:00
- Post Title: Genkai Tokkii Seven Pirates .PAC

Yeah, sorry shakotay2, I'm just so helpless when it comes to looking at hex I don't get any of it. I like need a super noob tutorial of how to find patterns and what not. I even tried to use your tool to try and figure out the PSVita GMO format in "Sword Art Online: Hollow Realiation", and I'm just like. lolwhatisthis. Thanks for tryna help though ;  w ;" I don't know a single thing about Hex, and learning it for me is really hard.
