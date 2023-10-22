## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T01:15:08+00:00
- Post Title: Black Rock Shooter

Continued from 

[viewtopic.php?p=69288#p69288](http://forum.xentax.com/viewtopic.php?p=69288#p69288)

I did a quick search for PTMD tags, which I can assume is the number of textures.
The model file begins with INSM, followed by 2 shorts.
Or 2 bytes and 1 short.
Or maybe 4 bytes

But if you compare a couple larger models with smaller models, you'll quickly see that the number of textures matches the short at the top, so I would believe that it's 2 bytes and 1 short unless they restricted themselves to at most 15 textures per model, which can be reasonable also for a PSP (I don't know).

That offset to the first PTMD appears twice for the 5 files I've compared so far. Don't know why lol

The offsets you've listed, ya I would agree with that it looks like the same values for most of them.

The other offsets leads to similar values
Triangle offset seems to lead to 0x 00 00 00 14

The integer at offset 12 seems to increase somewhat proportional to the size of the file (and consequently, size of the model even if it's a bunch of texture data), so that might be a count for something.
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-15T02:45:48+00:00
- Post Title: Black Rock Shooter

> Reply from Ninja
>
> Still not able to make implicit triangles work.
Take a look at this from chr_m_egb01.mdl 
http://pastebin.com/7EPQL2sN
The data i'm showing you is the large chunk where each line starts with A2070012 
The left half of the 3rd long looks like offsets to the vert list, so maybe these are triangle descriptions?
The left byte of the 4th long changes frequently from 3 to 4 and back, lower down they go up to 16, could be mostly triangle and quad polygons??
Anyway, going to try doing triangles from the offsets, see if that works.

Edit: Yep, 3rd long is offset from start of 'triangle' list, left byte of 4th long is number of points in the polygon
http://pastebin.com/LRgrfyeg 
Hardcoded for one file, and the vertices and faces count are wrong, need to adjust them manually, but it's the method your looking at.
Index data can also be interleaved with vertex data (or pressed up against it), its presence is specified by 2 bits 11 bits into that flag I mentioned in the archive thread. Find the flag and the format will likely be trivial to display. (still haven't looked at any of the actual files, sorry for armchairing it, I've got 50 windows open right now and am trying to finish up another format for the next release of Noesis)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T04:09:20+00:00
- Post Title: Black Rock Shooter

Any idea what the vertex data consists of?
I'm just scrolling through it with 010 and seeing some floats...but then a lot of things that aren't floats in between. Half-floats and floats mixed together?
## Post #4
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-15T19:39:27+00:00
- Post Title: Black Rock Shooter

Was just looking as the possibility of half floats, floats have been working up until now.
Managed to get the first block into metasequoia.
When you come across 0x0000000B 0x00000014 0x****001D in the, lets call it a polygon table, it's messing up somehow, thinks is a problem with the variable size fields.
A207 = 24 bytes ..........!!!???
BA07 = 28 bytes 
BA47 = 32 bytes  
BA87 = 36 bytes  

Can't find enough data for UV's!!!

Found a small PTMD at the bottom of chr_m_yub01.mdl
Weird, it looks like a paletted image but the palette given is on 16 longs.
[http://i1235.photobucket.com/albums/ff4 ... l/pic1.jpg](http://i1235.photobucket.com/albums/ff428/codex34/general/pic1.jpg)
## Post #5
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-17T04:14:00+00:00
- Post Title: Black Rock Shooter

Finally got it to load correctly, think one of the tags is still incorrect, but ran out of files to test it on.
Just the model, no UVs or textures.
There are bones and textures in the format. CBA

Python extractor - it aint pretty....
[http://pastebin.com/rTMvuqku](http://pastebin.com/rTMvuqku)

Metasequoia file
[http://uppit.com/hchfmedsvwrs/chr_m_yub01.zip](http://uppit.com/hchfmedsvwrs/chr_m_yub01.zip)

Beats the cfs2 format for stupidity......
## Post #6
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-17T04:53:45+00:00
- Post Title: Black Rock Shooter

> Reply from Ninja
>
> Python extractor - it aint pretty....
http://pastebin.com/rTMvuqku
Awesome
How to use Python script?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-17T07:31:02+00:00
- Post Title: Black Rock Shooter

Hmm hopefully someone can figure out the PTMD's lol

What's going on with the faces?
## Post #8
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-18T04:51:50+00:00
- Post Title: Black Rock Shooter

I'll collect some ptmd files and post them in the graphics section.

They just implicit triangles like MrAdults said, stored as polygons.
I have a cold so doing the faces like I did seemed a good idea at the time 

replace it with:-

```
                vn = vnum -2 
                for q in range(0, vn):
                    rm = q % 2
                    kk = kcount+q
                    if rm == 0:
                        of.write("3 V("+str(kk+2)+" "+str(kk+1)+" "+str(kk)+")\n")
                    elif rm == 1:
                        of.write("3 V("+str(kk)+" "+str(kk+1)+" "+str(kk+2)+")\n")
                kcount+=vnum

```


alon - you have python installed?
## Post #9
- Username: weling2010
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Feb 10, 2012 3:35 pm
- Post datetime: 2012-07-01T07:25:59+00:00
- Post Title: Black Rock Shooter

syntaxError noesis line 216 brs1 and brs2 line 159 how fix this
