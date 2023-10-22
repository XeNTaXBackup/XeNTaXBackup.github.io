## Post #1
- Username: iTzCorky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 11, 2014 7:56 am
- Post datetime: 2014-06-11T10:28:04+00:00
- Post Title: Help Needed (Hex2Obj) Battlefield 4

Hello everyone im new around here so don't be to harsh on me. I am trying to learn a new skill and it seems to be impossible lol. I was reading the tutorial on Hex2Obj and was trying to use it for Battlefield 4 but more specifically on a character. I have the .mesh and .chunk files for it and it would make my day if someone could help me understand how this works exactly specifically in the Hex Editor, in this tutorial for Hex2Obj it talked about how to search for patterns and that was where I got lost. I am not sure if I can post the .mesh and .chunk file for this so I won't until I know I am allowed. Any tips would be great
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-11T11:07:39+00:00
- Post Title: Help Needed (Hex2Obj) Battlefield 4

the hex2obj tutorial is for simple formats only.
iirc the BF4 models are stored in *.chunk files and use half floats
which are a little bit harder to identify than floats in a hexeditor.

Are you capable to identify floats? If "no",  you should start with the simple example in the hex2obj tutorial (tut button).

use forum search, read here for example:
[viewtopic.php?f=16&t=10966&hilit=battlefield](http://forum.xentax.com/viewtopic.php?f=16&t=10966&hilit=battlefield)
(when I wrote "easy" it was addressed to luxor who has much experience with data formats,
for beginners this chunk format is hard to solve)

dainazinas made a maxscript to import chunk files, should be somewhere here:
[viewtopic.php?f=16&t=11300](http://forum.xentax.com/viewtopic.php?f=16&t=11300)
## Post #3
- Username: iTzCorky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 11, 2014 7:56 am
- Post datetime: 2014-06-11T11:31:24+00:00
- Post Title: Help Needed (Hex2Obj) Battlefield 4

> Reply from shakotay2
>
> the hex2obj tutorial is for simple formats only.
iirc the BF4 models are stored in *.chunk files and use half floats
which are a little bit harder to identify than floats in a hexeditor.

Are you capable to identify floats? If "no",  you should start with the simple example in the hex2obj tutorial (tut button).

use forum search, read here for example:
viewtopic.php?f=16&t=10966&hilit=battlefield
(when I wrote "easy" it was addressed to luxor who has much experience with data formats,
for beginners this chunk format is hard to solve)

dainazinas made a maxscript to import chunk files, should be somewhere here:
viewtopic.php?f=16&t=11300

Hey thanks for the reply and for identifying them I would say no XD but I would love to learn. I have a few questions though if you don't mind. When looking through the hex of the .chunk what exactly am I looking for? In the tutorial you say the pattern but I am so lost lol. Also would it be possible for me to post up the .chunk file for you to look at? I don't want a straight forward answer but a point in the right direction.

EDIT:
Give me a little time to read up on Half Floats before doing anything XD I will post back when I have read through this to get a better understanding of floats and half floats.
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-11T14:18:56+00:00
- Post Title: Help Needed (Hex2Obj) Battlefield 4

why hasn't anyone made tools for bf4 yet? like it's not even hard.

If I get into the hardline beta I'll take a look
## Post #5
- Username: iTzCorky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 11, 2014 7:56 am
- Post datetime: 2014-06-11T16:59:37+00:00
- Post Title: Help Needed (Hex2Obj) Battlefield 4

> Reply from cra0
>
> why hasn't anyone made tools for bf4 yet? like it's not even hard.

If I get into the hardline beta I'll take a look

There are a few one that comes to mind is it can find the chunk files from the mesh files and it does it for all of them and puts them in folders its a pretty neat tool.
## Post #6
- Username: iTzCorky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 11, 2014 7:56 am
- Post datetime: 2014-06-14T03:59:19+00:00
- Post Title: Help Needed (Hex2Obj) Battlefield 4

YAY I can officially say I found the GUID myself in the mesh file even though it took me a long time and a lot of reading I finally figured it out by looking at the data on the left side in Hex Workshop and found it right at the top  so next I shall attempt to extract a model myself and I will not ask for help unless I get stuck for the next 5 hours and yes I will be trying this for the next 5 hours or so. But One quick question the rest of the LOD's what are those supposed to be? I have found several LOD in the mesh file.

EDIT: Well ummmmmm No idea what I did here but figured it would be funny to throw out there. This was supposed to be a character XD 



EDIT 2: Okay so I have tried everything to get this going with no luck still. It is the mp recon from Battlefield 4 the headgear and the locations of meshes I found were here, 0x22050, 0x24DC8, 0x25974, 0x28D70, 0x290D0, 0x2FFA0. Any help would be great
