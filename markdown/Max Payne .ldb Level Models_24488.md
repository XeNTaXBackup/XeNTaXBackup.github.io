## Post #1
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-09-13T02:30:12+00:00
- Post Title: Max Payne .ldb Level Models

Hey all, been trying to rip levels from the original Max Payne. The atmosphere of this game is something special, and I thought it would be really cool to port some of these maps to other games or do renders of them in modern graphics engines. Unfortunately, the .ldb format is I think the only thing that hasn't been cracked from the original Max Payne, and I couldn't find much of anything about the format online. These files contain pretty much all the level data from what I can tell, including the meshes and textures. 

The textures can be ripped using this program [https://www.moddb.com/games/max-payne/downloads/ldbrip](https://www.moddb.com/games/max-payne/downloads/ldbrip)
However, there is currently no way to rip the actual level mesh from these files. I'm pretty certain they're split up into several submeshes, so far I haven't had much luck. Only able to get some point clouds (probably with junk data)

Car verts from Tutorial.ldb


Verts from end_combat.ldb

Could be wrong, but it kinda resembles this part of the map. If you look on the right side of the above image, that block of verts kinda resembles the desks where the computers are set on.


Any point clouds i'm able to grab are always near the top of the file, but if you look at the bottom of the file, you can see various strings, probably related to the levels scripting but some of these I think are mesh/texture names.


I've also tried the game's modding SDK, which does include a level editor. However, it doesn't include anything for these .ldb files. Ninja ripper also didn't take kindly to this game.

Here's some sample files if you'd like to take a look.
[https://mega.nz/file/Y74QSDjL#YT_Zy8eto ... aVmATG9WCo](https://mega.nz/file/Y74QSDjL#YT_Zy8eto-3cPOZ_-jzjRQc4SLbRsTw9yaVmATG9WCo)

Hope someone with more experience than me can shed some light on this, any help would be appreciated.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-13T11:22:02+00:00
- Post Title: Max Payne .ldb Level Models

Funny format, some small point clouds, yeah. In Tutorial.ldb 30..80 vertices per submesh, but FVFsize is varying from 35 to 36, then 37 bytes. Crazy.
I assume this is worthless as long you don't know where or how to get the face indices.
Maybe a "point cloud skinner" is an option?
.



MP_Tutorial-ldb.png (32.15 KiB) Viewed 466 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-13T13:10:04+00:00
- Post Title: Max Payne .ldb Level Models

funny_tut.png (64.76 KiB) Viewed 464 times



edit: meanwhile I checked some of the face indices "candidates" - always gives me a mess. There must be some trick...
## Post #4
- Username: Nostritius
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 11, 2019 6:18 pm
- Post datetime: 2021-10-31T19:44:04+00:00
- Post Title: Max Payne .ldb Level Models

I have researched the ldb format and can share what I found out. The thing is, that they use a weird serialization format which compresses numbers into up to 3 bytes. Every element is prefixed with a byte determining its type. From what I have read, you probably already know 0x16 for a 3d float vector. I have appended a python script which unpacks the ldb files geometry as obj files. There are still plenty of things to do, for example, the level is build up from multiple sub meshes. While I found an id to separate them they all lay on each other, so they need a kind of offset. Furthermore the extracted stuff is currently only bare geometry, while textures can be extracted I am missing some information where they get attached.
[unldb.zip](https://xentaxbackup.github.io/file/21114_unldb.zip)
## Post #5
- Username: Nostritius
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 11, 2019 6:18 pm
- Post datetime: 2021-10-31T19:45:37+00:00
- Post Title: Max Payne .ldb Level Models

Just a small example of the end combat room as geometry. That thing hanging in the middle is one of those mentioned submeshes
[Bildschirmfoto vom 2021-10-31 20-46-15.png](https://xentaxbackup.github.io/file/21115_Bildschirmfoto vom 2021-10-31 20-46-15.png)
## Post #6
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2022-05-02T23:54:21+00:00
- Post Title: Max Payne .ldb Level Models

how's this comin along? looks like you're makin good progress mango jango!
## Post #7
- Username: Nostritius
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 11, 2019 6:18 pm
- Post datetime: 2022-05-03T10:14:54+00:00
- Post Title: Max Payne .ldb Level Models

> Reply from Reddance ↑Tue May 03, 2022 7:54 am at Tue May 03, 2022 7:54 am
>
> 
how's this comin along? looks like you're makin good progress mango jango!

I made some progress and found a table, describing the material properties. Still, I cannot assign them to a particular face. I should mention that this has a lower priority for me, since I am more interested in the Remedy Games starting from Alan Wake which have a different Engine. I wanted to know, how much these games have in common with the Max Payne Games, that is the reason, why I started reversing them.
[unldb.zip](https://xentaxbackup.github.io/file/22185_unldb.zip)
## Post #8
- Username: m0nstr0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 12, 2022 8:41 pm
- Post datetime: 2022-06-12T13:01:01+00:00
- Post Title: Max Payne .ldb Level Models

I want to port Max Payne to UE5. So I've spent like a week trying to decompile this file format. I've even used IDA to disassemble all the DLLs and the EXE files to figure out how it is processed by the game. I've parsed like 80 percent of file format. The file format is a totally weird. It is the kind of memory dump. The level geometry is duplicated lots of times. I think, it's possible to write Decompiler from LDB to MaxED's LVL format, because LDB contains almost all information that LVL file contains. They use polygons to render geometry not triangles. I'm currently writing Maya script to visualize all of this mess from the LDB.
## Post #9
- Username: m0nstr0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 12, 2022 8:41 pm
- Post datetime: 2022-06-15T01:31:37+00:00
- Post Title: Max Payne .ldb Level Models

I wrote the script for Maya. It allows import Max Payne's levels. 



Screenshot_3.jpg (114.22 KiB) Viewed 203 times
## Post #10
- Username: Nostritius
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 11, 2019 6:18 pm
- Post datetime: 2022-06-16T07:55:43+00:00
- Post Title: Max Payne .ldb Level Models

> Reply from m0nstr0 ↑Wed Jun 15, 2022 9:31 am at Wed Jun 15, 2022 9:31 am
>
> 
I wrote the script for Maya. It allows import Max Payne's levels. 
Screenshot_3.jpg

Nice work, would you be willing to share the code? I would be interested what I missed.
## Post #11
- Username: m0nstr0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 12, 2022 8:41 pm
- Post datetime: 2022-06-24T15:20:34+00:00
- Post Title: Max Payne .ldb Level Models

> Reply from Nostritius ↑Thu Jun 16, 2022 3:55 pm at Thu Jun 16, 2022 3:55 pm
>
> 
m0nstr0 wrote: ↑Wed Jun 15, 2022 9:31 am
I wrote the script for Maya. It allows import Max Payne's levels. 
Screenshot_3.jpg


Nice work, would you be willing to share the code? I would be interested what I missed.

Sure,  [https://github.com/m0nstr0/max_payne_ldb_importer](https://github.com/m0nstr0/max_payne_ldb_importer)

But I'm still working on it. There are some issues with the dynamic mesh transformations in the scene
