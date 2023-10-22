## Post #1
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2010-01-18T20:38:20+00:00
- Post Title: Bayonetta XBox360

Here is the file i'm using to try to figure out the file format:

[http://www.sendspace.com/file/52vq2a](http://www.sendspace.com/file/52vq2a)

so, what i have so far:

the first 4 bytes at 0x0 seems to be the idstring '\0BMW' that is 'WMB\0' if we convert to little-endian.

In the hex editor, we can easily spot a 32 bytes pattern at offset 0x80.
The 0x80 value is found a offset 0x18 so it could indicate the begining of a structure.

[](http://img237.imageshack.us/i/hex1d.png/)


if we examine the file, we can see that at offset 0x3D40 the pattern is changing and there's no more the 32 bytes pattern.

[](http://img85.imageshack.us/i/hex2.png/)

The 0x3D40 value can be found at offset 0x1C so that could be the offset of another structure.

I do some math on those offset:  0x3D40 - 0x80 = 0x3CC0 
I divide this result by 0x20 (32 bytes in hex) and I obtain 0x1E6.
This number can be found at offset 0x0C

I think this confirm that at offset 0x80 begin a datablock of 0x1E6 (486) 32bytes structures

let's assume that this is vertices data and render those 486 structures using the first 12 bytes as 3 floats, probably x, y and z coordinates.
[](http://img85.imageshack.us/i/lamp.png/)

It isn't really beautilful on this static image but it looks like a street lamp, so I guess i've found the vertices coordinates in that 32 bytes structures.

That's all i got for the moment, the other fields of the header, vertex structure or other datablock in the file have still no meaning for me.

I checked if there's several time the same vertex coordinates in the vertex list and found that a lot of vertices are duplicated 2, 3 or 4 times. Dunno why, perhaps for degenerate triangles.

I'm now searching how to render the tringles out of this but wasn't able to find anything yet.
Near the end of the file there's several datablock with a lot of numbers under the 486 vertex count so it could be indices.

Any info or hints are welcome 
i'll keep you posted.



ps: redirect me if this is the wrong section for this kind of stuff.
## Post #2
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2010-01-19T18:30:40+00:00
- Post Title: Bayonetta XBox360

Small update

The values at the end of the file are indeed indices.
I found two meshes in the file, one detailed and one really low poly, probably only used for collision detection:

[](http://img29.imageshack.us/i/pylon.png/)

I identified several new values in the header.

Don't mind the funny colors, I haven't found how to read the textures yet.

I'm really having fun :p
## Post #3
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-12T20:15:58+00:00
- Post Title: Bayonetta XBox360

here is the full toolset thanks to chroxx, luigi, fatduck and me (and some others )
[http://www.mediafire.com/?twinmymtndz](http://www.mediafire.com/?twinmymtndz)
## Post #4
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-14T22:45:32+00:00
- Post Title: Bayonetta XBox360

I'm a noobs i follow the step in this thread [viewtopic.php?f=10&t=3773&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=3773&start=15)  i tried to convert in obj in win 32 and in win 64 bit but the tool said "job done" but i don't see any obj file.... 

[](http://imagefra.me/)

I need to do something or install something??, please guys help me
## Post #5
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2010-06-14T23:31:23+00:00
- Post Title: Bayonetta XBox360

the obj file is created automatically into your C:\Documents and Settings\username
And it is the same for textures.
## Post #6
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-15T00:04:12+00:00
- Post Title: Bayonetta XBox360

> Reply from noazett
>
> the obj file is created automatically into your C:\Documents and Settings\username
And it is the same for textures.

Thanks a lot noazett
## Post #7
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-20T11:56:14+00:00
- Post Title: Bayonetta XBox360

yes it seems you just don't have admin rights on your computer so it save the files in the local account in uses folder :p
## Post #8
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2011-01-25T20:09:54+00:00
- Post Title: Bayonetta XBox360

Wow

One year has passed since I started this thread and i'm still nowhere.
Well, probably because I was really busy on other stuffs during most part of that time.

But lets get back to business 

I'm still trying to figure out most of the field in the WMB file.

Here is what I have:

[https://docs.google.com/Doc?docid=0Aaaz ... Z2c1&hl=en](https://docs.google.com/Doc?docid=0AaaziCv2Z7WQZGRuM2pieHZfMmRjd3o2Z2c1&hl=en)

With that i'm able to load a model file in a homemade viewer and display the meshes in the file.
If I load a texture with a mesh, I can sometime see the mesh textured correctly but most of the time it's not the right texture (or the uv seem wrong)

So what I'm trying to figure out now is: "how to know which texture correspond to which mesh in the wmb file?"

Can you give me a hand here ?
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-25T22:56:03+00:00
- Post Title: Bayonetta XBox360

noesis supports this format 100% and he gave the source to that import plugin on his site.
## Post #10
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2011-01-26T11:36:29+00:00
- Post Title: Bayonetta XBox360

Hi chrrox,

Thanks for the answer, i'll have a look.
## Post #11
- Username: davironica
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 23, 2009 4:29 am
- Post datetime: 2011-02-01T14:04:51+00:00
- Post Title: Bayonetta XBox360

I tried using using bayonetta tools on the ps3 version and it worked flawlessly with the models however i get an error with the xpr textures, i can't seemed to extract them with unbundler or xpr express, it would be great if you guys willing to have a look at the original dat file from the ps3 version for comparison. thanks in advance.

[http://www.mediafire.com/?sfyzlev9zzw9wl9](http://www.mediafire.com/?sfyzlev9zzw9wl9)
## Post #12
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:53:48+00:00
- Post Title: Bayonetta XBox360

we can use noesis to extract the model
## Post #13
- Username: davironica
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 23, 2009 4:29 am
- Post datetime: 2011-02-10T17:45:05+00:00
- Post Title: Bayonetta XBox360

True, but still is there a way to extract the texture from the ps3 version, since all the xpr produced got invalid header, my guess is they aren't in the same format as the xbox 360 version, perhaps anyone have this thing figured out.
## Post #14
- Username: jouzumania
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 17, 2010 6:55 am
- Post datetime: 2011-02-24T01:02:05+00:00
- Post Title: Bayonetta XBox360

hello everyone,

all the textures work right except those for the head. i did a screencap collaboration to show you my problem.
The normal texture does not work, but the alpha map is just fine. Can you tell me what i can do?
[problem.png](https://xentaxbackup.github.io/file/3984_problem.png)
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-24T01:09:25+00:00
- Post Title: Bayonetta XBox360

this game has multiple uv layers you are using the wrong one.
## Post #16
- Username: jouzumania
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 17, 2010 6:55 am
- Post datetime: 2011-02-24T01:42:29+00:00
- Post Title: Re: Bayonetta XBox360

ah! ok i got it. i didn't know that there are multiple maps. do you know where to get the right one? i found another post where someone "copied" the wrong uvmap onto the alpha map to make it fit but thats not how it should be done :/
## Post #17
- Username: thegtsolo
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jul 12, 2011 3:18 am
- Post datetime: 2011-07-17T17:17:43+00:00
- Post Title: Re: Bayonetta XBox360

how to extract .aax
Thank
## Post #18
- Username: thegtsolo
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jul 12, 2011 3:18 am
- Post datetime: 2011-07-17T17:30:15+00:00
- Post Title: Re: Bayonetta XBox360

The contents of this post was deleted because of possible forum rules violation.
