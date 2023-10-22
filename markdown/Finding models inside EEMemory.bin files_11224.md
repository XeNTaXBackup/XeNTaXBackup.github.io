## Post #1
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-02-19T22:17:39+00:00
- Post Title: Finding models inside EEMemory.bin files?

Hello, all. Lately, I've been seeking to get 3D models of characters and monsters in Wild Arms 3 on the PS2, and I was able to find out the 3D data is stored in the EEMemory.bin file extracted from a savestate on PCSX2. I wanna learn how to use shakotay's 3D model extraction guide, but I am uncertain of how to actually locate in hex editors. Can someone please help me? If anyone is interested, I will supply them with the EEMemory.bin from a savestate during the battle with Janus Cascade's demon form.
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-20T13:32:10+00:00
- Post Title: Finding models inside EEMemory.bin files?

[http://ps23dformat.wikispaces.com/Wild+Arms+3](http://ps23dformat.wikispaces.com/Wild+Arms+3)
This website might be quite useful for you.
## Post #3
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-02-20T14:31:46+00:00
- Post Title: Finding models inside EEMemory.bin files?

> Reply from barti
>
> http://ps23dformat.wikispaces.com/Wild+Arms+3
This website might be quite useful for you.
Well, I have the textures for said character. The problem is finding some way to get the UVs to fit onto them, to help with disassembling model parts.
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-20T14:35:35+00:00
- Post Title: Finding models inside EEMemory.bin files?

Have you tried using the WildArms3eememoryto3ds.BMS script? The format specification below seems to mention UVs so they should load.
## Post #5
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-02-20T15:07:09+00:00
- Post Title: Finding models inside EEMemory.bin files?

> Reply from barti
>
> Have you tried using the WildArms3eememoryto3ds.BMS script? The format specification below seems to mention UVs so they should load.
Of course. I try unwrapping UVs via Blender, but it's in every tri being separated.
## Post #6
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-20T15:29:11+00:00
- Post Title: Finding models inside EEMemory.bin files?

Can you send me the file EEMemory.bin file so that I can have a look at it?
## Post #7
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-02-20T16:02:01+00:00
- Post Title: Finding models inside EEMemory.bin files?

> Reply from barti
>
> Can you send me the file EEMemory.bin file so that I can have a look at it?
[Here you go, good sir.](http://www.mediafire.com/download/8atec7t8eqdphi1/eeMemory.bin)
## Post #8
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-02-20T18:00:30+00:00
- Post Title: Finding models inside EEMemory.bin files?

Why are you trying to obtain them from a ram dump, what's up with the raw files?
## Post #9
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-20T18:31:25+00:00
- Post Title: Finding models inside EEMemory.bin files?

> Reply from Gh0stBlade
>
> Why are you trying to obtain them from a ram dump, what's up with the raw files?
Supposedly files on the disc use some unknown compression and it's easier to extract data from a PCSX2 savestate.
## Post #10
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-02-21T22:21:49+00:00
- Post Title: Finding models inside EEMemory.bin files?

I really don't intend to put pressure on anybody with this post.

Has there been an update to the situation?
## Post #11
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-21T22:25:07+00:00
- Post Title: Finding models inside EEMemory.bin files?

I tried to look at the BMS script to see how it loads the models but it's quite hard to read   I need to look into it later.
## Post #12
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-02-22T21:18:49+00:00
- Post Title: Finding models inside EEMemory.bin files?

No worries. I can wait.
## Post #13
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-02-27T22:38:51+00:00
- Post Title: Finding models inside EEMemory.bin files?

My sincere apologies for the bump, but I have recently learned all models in the game use backface culling. Not sure if this will help, but felt like informing.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-24T14:44:32+00:00
- Post Title: Finding models inside EEMemory.bin files?

Due to your question in the tutorials thread concerning another game I restarted viewing the problem here and found it not too hard:
[](http://www.pic-upload.de/view-22653872/1_3ds_as_obj.jpg.html)

But I have no time to update the bms script so that the uvs are automatically written into the 3ds files in
a 4140 chunk (Mapping coordinates).
(wonder why the author of the script didn't do it. I'm sure he knew how to but maybe he wasn't interested in uvs and normals).

I just made a workaround using a 3ds lib from the web to extract the face indices, and using the bms to dump the uvs.

So I've no one-in-all solution but I could provide the 8 3ds files as objs (including uvs).
## Post #15
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-03-24T18:20:11+00:00
- Post Title: Finding models inside EEMemory.bin files?

> Reply from shakotay2
>
> Due to your question in the tutorials thread concerning another game I restarted viewing the problem here and found it not too hard:


But I have no time to update the bms script so that the uvs are automatically written into the 3ds files in
a 4140 chunk (Mapping coordinates).
(wonder why the author of the script didn't do it. I'm sure he knew how to but maybe he wasn't interested in uvs and normals).

I just made a workaround using a 3ds lib from the web to extract the face indices, and using the bms to dump the uvs.

So I've no one-in-all solution but I could provide the 8 3ds files as objs (including uvs).
Yes, please. 

It would be appreciated!
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-24T21:12:03+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

here you go:
[WA3_3ds_as_obj.zip](http://www.uploadmb.com/dw.php?id=1395695458)
It's 1, 2 and 5.3ds as obj. Will provide the rest as soon as you confirm that they are as you expected them to be.

For 5.3ds I had to cut the face indices from 1758 to 10961 since the vertices built a flat useless mesh.
So the uv map is not complete.

(Guess the errorness 5.3ds is caused by the bms script. Don't know the reason - maybe a submesh problem.)
Leaving the face indices uncut is no solution.
## Post #17
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-03-24T22:26:59+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

> Reply from shakotay2
>
> here you go:
WA3_3ds_as_obj.zip
It's 1, 2 and 5.3ds as obj. Will provide the rest as soon as you confirm that they are as you expected them to be.

For 5.3ds I had to cut the face indices from 1758 to 10961 since the vertices built a flat useless mesh.
So the uv map is not complete.

(Guess the errorness 5.3ds is caused by the bms script. Don't know the reason - maybe a submesh problem.)
Leaving the face indices uncut is no solution.
Yes, they are what I expected them to be.

The problem in separating meshes by loose parts is that the main body other than the head is in a single mesh when it is not supposed to be. This could make things more difficult when reorganizing different parts of the model.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-25T07:00:37+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

So here's the rest:
[WA3_Part2_3ds_as_obj.zip](http://www.uploadmb.com/dw.php?id=1395730592)

(Face winding is reverse to the one of the 3ds models.)

Model 8's mesh is a complete mess. The vertices are near 0.0 0.0 0.0 and some texture coords are out of bounds/wrong.
## Post #19
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-03-25T08:34:40+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

> Reply from shakotay2
>
> So here's the rest:
WA3_Part2_3ds_as_obj.zip

(Face winding is reverse to the one of the 3ds models.)

Model 8's mesh is a complete mess. The vertices are near 0.0 0.0 0.0 and some texture coords are out of bounds/wrong.
Thanks! 

I have been wanting to find a way to fix the mesh in model 7. Do you have any tips to make it easier?
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-03-25T09:11:23+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

Model 7 looks o.k. to me. You mean model 8?

Well, you'd to go through the bms script inserting print commands as a debug help.
for example:
print "nuv: %nuv%"
For cvb = 1 To nuv ;
 print "nuv-addr: %werefox%"
 GoTo werefox 0 ;
(nuv is number of vertices, but not max vertex count)

As you know the structure of the basic data blocks is rather simple:

4ByteNumberofVertexes ORunknown
00 40 1E 31
12 04 00 00
4ByteFloatingPointWeight
{3x 4ByteFloatingPointVertexes(X,Y,Z), 4ByteFloatingPointWeight, 3x 4ByteFloatingPointNormalMappings(X,Y,Z), 
4ByteFloatingPointWeight, 2x 4ByteFloatingPointTextureUVCoords(U,V), 4ByteFloatPointWeight, 4ByteUnknownInteger}

where the first 12 bytes are some kind of header (the 00 40 1E 31... sequence is used by the bms script to find the blocks) and the following 48 bytes block is present nuv times (nuv=3..21 for the first mesh).

You might use the addresses of your debug output to look into the eeMemory.bin file to understand what goes wrong with model 8 (and 5).

This tends to be a little bit time consuming (while finding how to get the uvs was not).
Since the models are not of vast interest for me I don't think I'll dig deeper into this.

btw: to get all the debug output you'll have to enlarge the command window or redirect the output into a file like this:
quickbms WildArms3\WildArms3eememoryto3ds.BMS WildArms3\eeMemory.bin > logme.txt

(Be sure to delete the 3ds files before a second run otherwise you'll find this "batch session" blocked.)
## Post #21
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-04-19T02:22:46+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

> Reply from shakotay2
>
> Model 7 looks o.k. to me. You mean model 8?

Well, you'd to go through the bms script inserting print commands as a debug help.
for example:
print "nuv: %nuv%"
For cvb = 1 To nuv ;
 print "nuv-addr: %werefox%"
 GoTo werefox 0 ;
(nuv is number of vertices, but not max vertex count)

As you know the structure of the basic data blocks is rather simple:

4ByteNumberofVertexes ORunknown
00 40 1E 31
12 04 00 00
4ByteFloatingPointWeight
{3x 4ByteFloatingPointVertexes(X,Y,Z), 4ByteFloatingPointWeight, 3x 4ByteFloatingPointNormalMappings(X,Y,Z), 
4ByteFloatingPointWeight, 2x 4ByteFloatingPointTextureUVCoords(U,V), 4ByteFloatPointWeight, 4ByteUnknownInteger}

where the first 12 bytes are some kind of header (the 00 40 1E 31... sequence is used by the bms script to find the blocks) and the following 48 bytes block is present nuv times (nuv=3..21 for the first mesh).

You might use the addresses of your debug output to look into the eeMemory.bin file to understand what goes wrong with model 8 (and 5).

This tends to be a little bit time consuming (while finding how to get the uvs was not).
Since the models are not of vast interest for me I don't think I'll dig deeper into this.

btw: to get all the debug output you'll have to enlarge the command window or redirect the output into a file like this:
quickbms WildArms3\WildArms3eememoryto3ds.BMS WildArms3\eeMemory.bin > logme.txt

(Be sure to delete the 3ds files before a second run otherwise you'll find this "batch session" blocked.)
Actually, I meant removing the double vertices and separating by loose parts in Blender separates the head and weapon, but the main body is still a mess in a single piece. I was hoping if it were possible to make the task a lot easier. Thanks anyway.

EDIT:



Here, after, using applying textures that I ripped, I removed double vertices in Edit Mode, then proceeded to separate the objects by loose parts. However, the main body without the head and weapon is a mess. I dunno if this has something to do with the way the script extracted the model. Is there anywhere to fix it to resemble how it appears in-game?
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-19T07:16:26+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

> Reply from SmashFan127
>
> [...]I dunno if this has something to do with the way the script extracted the model.It obviously has since the script doesn't care for submeshes.

You could try to insert "g lines" into the objs I provided to create submeshes
such as
g sm0
f 1/1 2/2 3/3
...
f 998/998 999/999 1000/1000
g sm2
...
f 1997/1997 1998/1998 1999/1999
g sm3
...

These were just for a quick test You'll have to find the correct positions of the lines by trial'n error.

Importing the 3_3ds_as_obj.obj into blender with the group button selected shows this:



3ds_as_obj_groups.JPG (57.47 KiB) Viewed 313 times
## Post #23
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-04-23T06:10:36+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

> Reply from shakotay2
>
> SmashFan127 wrote:[...]I dunno if this has something to do with the way the script extracted the model.It obviously has since the script doesn't care for submeshes.

You could try to insert "g lines" into the objs I provided to create submeshes
such as
g sm0
f 1/1 2/2 3/3
...
f 998/998 999/999 1000/1000
g sm2
...
f 1997/1997 1998/1998 1999/1999
g sm3
...

These were just for a quick test You'll have to find the correct positions of the lines by trial'n error.

Importing the 3_3ds_as_obj.obj into blender with the group button selected shows this:
3ds_as_obj_groups.JPG
I see... and what about fixing the mesh to make it closely resemble its in-game appearance instead of a pile of ruined mesh?
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-23T08:49:36+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

I don't owe the game so I don't know how the meshes look like ingame.
All I got is a script that extracts them as 3ds from the EEMemory.bin file without UVs.

I cared for the UVs but now I'm sorry - all I can do is to quote myself:

> Since the models are not of vast interest for me I don't think I'll dig deeper into this.
## Post #25
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-04-23T12:27:17+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

nice thread!
I was interested with textures extraction from "Plugin GS.dat" and "eeMemory.bin" of pcsx2 unpacked saveState files, here is some help:
[http://forums.pcsx2.net/Thread-PCSX2-ss ... ure-viewer](http://forums.pcsx2.net/Thread-PCSX2-sstates-VRAM-texture-viewer)
## Post #26
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-05-24T06:01:56+00:00
- Post Title: Re: Finding models inside EEMemory.bin files?

> Reply from SILENTpavel
>
> nice thread!
I was interested with textures extraction from "Plugin GS.dat" and "eeMemory.bin" of pcsx2 unpacked saveState files, here is some help:
http://forums.pcsx2.net/Thread-PCSX2-ss ... ure-viewer
I can certainly agree that textures are an important thing to a model. However, I am not good at finding textures inside the savestate. My biggest concern right now is trying to fix the mesh to resemble how it looks in-game while having proper UVs to fit onto the textures I have. Thanks for letting me know about the textures, though.

EDIT:

Is there anyway that the models inside eeMemory.bin can be extracted and not put in a mess while keeping the UV coordinates?
