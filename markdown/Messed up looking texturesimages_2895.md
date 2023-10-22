## Post #1
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-01-16T22:15:28+00:00
- Post Title: Messed up looking textures/images?

I've been trying to get some textures from the .hack//G.U. games (namely the card images) and I've kinda succeded, but they look terribly wrong.

Here's an example:



That's the image how Texture Finder made it(with pixel format "332=8"). After some tweaking with irfanview I got this:



That's almost it. Here's how the image should look like btw:



It seems like a problem with the palette. So, an ideas how to get from the first image to the last?

Incase you want to take a look at the file yourself. [Here](http://phorte.ph.ohost.de/xcvs_cg_009.tmp) it is.
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-01-17T01:43:46+00:00
- Post Title: Messed up looking textures/images?

EDIT: I didn't see the sample. Looking at it now
EDIT 2: Nothing. It wasn't it. I converted the sample manually right

Probably, you've started to get the palette from a wrong place.

It starts at offset 272, it's 1024 bytes long.

The image seems to have blue and red colors swapped according to the "original" picture that you've posted (BGR instead of the PC-standard RGB). I will check it.

EDIT 3: Yes, red and blue colors are swapped. After correcting it, I get the correct image   )
## Post #3
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-01-17T18:18:14+00:00
- Post Title: Messed up looking textures/images?

I didn't actually have an idea what I was doing when I made the topic, but now the images look right with your info. 
Thanks a lot
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-17T20:25:46+00:00
- Post Title: Messed up looking textures/images?

BGR isn't that uncommon, it is used in the .bmp format for example.
I think this also has a good reason, but I can't remember why.
