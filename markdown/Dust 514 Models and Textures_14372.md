## Post #1
- Username: RvdDragoon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 11, 2015 9:35 am
- Post datetime: 2016-05-20T09:46:01+00:00
- Post Title: Dust 514 Models and Textures

So, don't kill me right off. I know this is sort of an 'again' thread.
I'm trying, as the title suggests, to get the models and textures. The game's shutting down on the 30th, and I want to try and save some of it. I don't trust Project Nova to come to fruition, unfortunately.

Anyway. I've managed to get to the mesh files and the textures stored in the .upk with the models, mostly. It was the easy bit. The mesh files I think are Edge compressed, from other conversations I've read. UEViewer can open the .upk once it's out of the .psarc and says it's version 708/35, engine 6699, game 8043. UEViewer crashes on loading skeletal models, and the textures load but are corrupted.  Chrrox suggest two python files for Noesis, psa.py and bitloader.py, and either I don't know how to make them work or they don't work on these files. 
These posts [viewtopic.php?f=16&t=13057](http://forum.xentax.com/viewtopic.php?f=16&t=13057) and [viewtopic.php?f=10&t=11530](http://forum.xentax.com/viewtopic.php?f=10&t=11530) have everything I've been using, with the exception of the latest DLC file, which would be A0515. All the unlabeled .upk character model files I know of that ar'n't levels are contained in the CATMA.psarc. I have yet to give a crack at the .tfc files, but I'll give that a shot next.

I'd like to get something working to extract the models and textures, but I don't have the knowledge of where to go next to do it.

One of the two constants near the header in four mesh files I checked is at 0x8D, 8E, 8F and that's 3C A3 07. A little further down the files is a second constant feature of a very long string of 00 00 00 00 00 00 00 FF 00, sometimes interspersed with FF 01 or FF 02 instead of FF 00. Other bits in the header are consistent in location, but not content. I'm sure this means something, but I don't know what.

I'm pretty sure I shouldn't upload the model files, and they're easy to get. You want the A508 file, it'll contain most everything as that's the core file.

Edit: Following [viewtopic.php?f=16&t=9263](http://forum.xentax.com/viewtopic.php?f=16&t=9263) to get the textures, using -export -uncook -nomesh -noanim -nostat -all, the textures still come out corrupt, and it crashes while trying to load from a linked .tfc. Unable to serialize 1 byte.
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-20T10:33:48+00:00
- Post Title: Dust 514 Models and Textures

I extracted all characters from DUST 514 (male/female), by request from xentax's user, it's using edge compression, though vertices are packed too, format is complex. Also, I started to work on weapons, vehicles, though don't know when I will finish it
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-20T10:56:31+00:00
- Post Title: Dust 514 Models and Textures

> Reply from zaramot
>
> it's using edge compression,for the face indices, I guess? How did you get them?

Noesis is the only tool I know which handles edge compression:

```
edgeDecomp = rapi.decompressEdgeIndices(edgeData, indexCount)
```


(flatz wrote an edge decompressor but didn't release it, afaik)
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-20T14:36:47+00:00
- Post Title: Dust 514 Models and Textures

3ds max handles edge too, maybe not some custom versions but native sony sdk compression yes
## Post #5
- Username: RvdDragoon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 11, 2015 9:35 am
- Post datetime: 2016-05-20T19:42:37+00:00
- Post Title: Dust 514 Models and Textures

That's really a much more positive response than I had hoped for. Not that my thanks are worth much, know that you have my sincere heartfelt thanks for working on the model files. They're something a little bit special. If Max can handle the standard edge compression natively, did you write a custom importer or script for Max to handle the vertices? I know it'd probably be uncouth (and against the rules) to ask for the models themselves, so I wont. But I don't know how asking for the tools would be. 

Did you manage to get the texture files, or were you only working on the models? I'm not sure where I'm going wrong with them, or what sort of realignment I'd have to put them through to get them to come out clean. They seem to be the right data, just assembled wrong.

Thank you, though. That was great news, and a real big bunch of hope.
## Post #6
- Username: ljkvfd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 01, 2017 1:50 pm
- Post datetime: 2017-04-01T05:52:13+00:00
- Post Title: Dust 514 Models and Textures

Hello, any updates on this? are there any mesh files to download?
## Post #7
- Username: SamsonYo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 06, 2018 8:36 pm
- Post datetime: 2021-01-04T11:15:27+00:00
- Post Title: Dust 514 Models and Textures

Hey, I've tried to open the .pkg with a Playstation file unpacker, getting to the files. 
As show here:
[https://cdn.discordapp.com/attachments/ ... nknown.png](https://cdn.discordapp.com/attachments/246372917695217664/795610278192087060/unknown.png)

But i'm not sure how to access the files here, because of the format, they are in .TFC and .XXX format.
Also, i might be doing everything here wrong, and a point in a better direction, like other tools ect would also be appreciated
## Post #8
- Username: stalker0912
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 18, 2017 10:24 pm
- Post datetime: 2021-06-29T07:33:22+00:00
- Post Title: Dust 514 Models and Textures

> Reply from SamsonYo ↑Mon Jan 04, 2021 7:15 pm at Mon Jan 04, 2021 7:15 pm
>
> 
Hey, I've tried to open the .pkg with a Playstation file unpacker, getting to the files. 
As show here:
https://cdn.discordapp.com/attachments/ ... nknown.png

But i'm not sure how to access the files here, because of the format, they are in .TFC and .XXX format.
Also, i might be doing everything here wrong, and a point in a better direction, like other tools ect would also be appreciated

You can use uModel for the .XXX files, which are .UPK files. Best to rename 'em to .UPK. The PSARCs in the DLC_PS3 dir contain more of em, so what I usually did was extract PSARCs with Total Commander with the PSARC plugin, rename .XXX to .UPK and view .UPKs with uModel.

Most of models will export just fine, except for skeletal meshes, i.e. any LAV, HAV, dropsuit, and weapon. MCCs and the RDV will export just fine, and so will game objectives (the consoles and turrets). Rest is compressed with Edge compression and won't export out, a fellow above posted an image of models exported out but I never got there myself.
## Post #9
- Username: stalker0912
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 18, 2017 10:24 pm
- Post datetime: 2023-08-06T10:17:27+00:00
- Post Title: Dust 514 Models and Textures

> Reply from zaramot ↑Fri May 20, 2016 6:33 pm at Fri May 20, 2016 6:33 pm
>
> 
I extracted all characters from DUST 514 (male/female), by request from xentax's user, it's using edge compression, though vertices are packed too, format is complex. Also, I started to work on weapons, vehicles, though don't know when I will finish it

Could you possibly share the tools/scripts you used? It's been quite a while, Noesis can handle edge compression from what I read  - but not in this case, it throws the "Failure to acquire buffer bytes" error.
