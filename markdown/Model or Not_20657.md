## Post #1
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-13T03:20:28+00:00
- Post Title: Model or Not?

So, I've been trying to figure out Tomb Raider Anniversary's models, which has proven to be a very frustrating endeavor.  I've been told unequivocally that this .gnc file is a model file, but I haven't been able to successfully get a full model using hex2obj.  I've determined there are multiple vertex indices, but when I hex2obj them, The model elements (belts, holsters, etc...) all seem to be centered together, rather than in their proper positions.  I'm including a link to the gnc file, if anyone wants to look.

[Lara](https://drive.google.com/open?id=1OZdmW8GfK4Ckkcx5WGqMOKouILMpGNax)
[AnniversaryBeltModel.jpg](https://xentaxbackup.github.io/file/16344_AnniversaryBeltModel.jpg)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-13T09:54:19+00:00
- Post Title: Model or Not?

> Reply from nightwolf1982 ↑Thu Jun 13, 2019 11:20 am at Thu Jun 13, 2019 11:20 am
>
> but I haven't been able to successfully get a full model using hex2obj.the tool was never intended to get full models (other than simple models)
I try to get the parameters for a first submesh then usually do some coding ([https://forum.xentax.com/viewtopic.php?f=29&t=15955](https://forum.xentax.com/viewtopic.php?f=29&t=15955))

> I've determined there are multiple vertex indices, but when I hex2obj them, The model elements (belts, holsters, etc...) all seem to be centered together, rather than in their proper positions.That's not a matter of hex2obj. It's how the gnc creators built their meshes.

Usually you need to find the offsets for the different submeshes but you need to get properly separated submeshes before.

Which is not easy here, as an example

0x1F6BC 3315
Vb1
16 99
0x3E00 6679
020400
0x0 255

Might become tricky to get proper submeshes:



lara_part.png (165.07 KiB) Viewed 105 times



(I'd start getting all the FI blocks which are separated by FFFF (and 000000000000000000 / 0000) as it seems.)
## Post #3
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-13T14:56:41+00:00
- Post Title: Model or Not?

That's one of the reasons I'm not sure this is supposed to be the model.  I've never seen a game that stored the character models in such a jumbled state; usually the models are in the standard T or A pose.  There's also the fact that, similar to TR Legend, the gnc files appear to store skeleton and rigging data.  I would have thought the mesh sections would be properly positioned for the rigging.
## Post #4
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-13T18:53:55+00:00
- Post Title: Model or Not?

OK, these are the offsets for all of the Face Indices, as far as I can tell.  Looking at the resulting meshes though, I can't see this being the actual model for the game.  All of the model parts seem to be collapsed down or overlapping to the point of being non-sensical.  It would take months to reposition everything into just the basic t-pose.

```
0x1E10C
0x1E3A8
0x1F3B8
0x1F6BC
0x210B0
0x22918
0x24336
0x24794
0x24880
0x24A5C
0x24C44
0x24D84
0x24F0C
0x25094
0x27C30
0x28AB0
0x28CE0
0x292B8
0x29734
0x299D0
```
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-13T20:59:31+00:00
- Post Title: Model or Not?

> Reply from nightwolf1982 ↑Fri Jun 14, 2019 2:53 am at Fri Jun 14, 2019 2:53 am
>
> All of the model parts seem to be collapsed down or overlapping to the point of being non-sensical.wouldn't it be funny to solve this riddle? Not to get correct positions, just understand what this gnc is good for  



bodyparts.png (137.19 KiB) Viewed 82 times



(There's some floating point tables from  0x1A0 to 0x3950. Might be matrices -> 222 x 64 bytes.)
Maybe try out floats at 0x1C0, 0x200, ... (step 0x40) as positions?
## Post #6
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-13T21:27:59+00:00
- Post Title: Model or Not?

Consider the riddle solved, then.  TR Legend has the same "gnc" files, which contain the same type of vertex and index information.  When you hex2obj the Legend Lara file, you get the same type of screwed up model.  I'm now convinced these files are just skeleton or rigging files, and that the Anniversary models are stored somewhere other than the drms.  Just can't seem to figure out where.
[LegendLara_gnc.jpg](https://xentaxbackup.github.io/file/16349_LegendLara_gnc.jpg)
## Post #7
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-14T02:09:19+00:00
- Post Title: Model or Not?

Reposting the link to the drm file, in case anyone wants to take a look at it:

[Lara](https://drive.google.com/open?id=1L0ZoiEiRaV7J4tSqEDM3XSo7o1kXcXHE)
## Post #8
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-14T20:15:40+00:00
- Post Title: Model or Not?

So the question now is where are the models?  Are they in separate file?  Hardcoded in the exe?  Or are these "gnc" files really supposed to be the model files?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-06-17T17:12:14+00:00
- Post Title: Model or Not?

> Reply from nightwolf1982 ↑Sat Jun 15, 2019 4:15 am at Sat Jun 15, 2019 4:15 am
>
> 
So the question now is where are the models?  Are they in separate file?possible

> Hardcoded in the exe?I've never come across a game that stored model data (vertices) in its exe.

> Or are these "gnc" files really supposed to be the model files?You might try out some simple static meshes (such as a book, a chest, a table, a plank or something like that) to decide this.

btw: you could try out byte 8 or byte 10 (of the FVF block, starts with byte 0) as a vertex group number for separating meshes (just a wild guess).
