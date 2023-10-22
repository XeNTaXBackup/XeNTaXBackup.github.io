## Post #1
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-05-08T12:48:03+00:00
- Post Title: Ghost Recon Breakpoint and NinjaRipper

Been interested in ripping from GR: Breakpoint since there really hasn't been any coverage on it. I managed to rip something from the main menu with the Force Rip function of NinjaRipper and it indeed ripped almost 10 000 files, most seem to be duplicates. Noesis is able to successfully open up two files that are a character's head put into two pieces with intact UV maps, but anything else shows up empty, or at least in Noesis. 3D Max imports the smallest files as 2D quads, which I presume are the menu icons. Some of the other larger files Max can import as vertices, one of which had, if I recall correctly, over 90k vertices, which I'm presuming is the character's lower body. But it's just a mess and can't be used. I'll post the rip file of what I suspect is that of a lower body (there are multiple files which Max imported with many vertices). Just want to know if these can be even used or if they're just an unusable assortment of faces and vertices.

Edit: Yes, Mesh_0322 has 98304 vertices according to 3D Max.

Edit 2: Here's more samples, including the ones that could be opened with Noesis. I'm not sure if the smaller ones are anything useful though.
[https://www.mediafire.com/file/6a4k92a4 ... 6.zip/file](https://www.mediafire.com/file/6a4k92a49ki59ba/Mesh_0556.zip/file)
[Mesh_0322.zip](https://xentaxbackup.github.io/file/22201_Mesh_0322.zip)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-09T14:22:02+00:00
- Post Title: Ghost Recon Breakpoint and NinjaRipper

> Reply from MaZTeR ↑Sun May 08, 2022 8:48 pm at Sun May 08, 2022 8:48 pm
>
> 
Mesh_0322 has 98304 vertices according to 3D Max.
if you open it in hexeditor you will see that there are no vertices there. only faces. and at the beginning it says that stride 0.
(since there are none, then when importing / exporting, all vertices will be as zero)
[Mesh_0322.png](https://xentaxbackup.github.io/file/22203_Mesh_0322.png)
## Post #3
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-05-09T18:00:29+00:00
- Post Title: Ghost Recon Breakpoint and NinjaRipper

> Reply from Durik256 ↑Mon May 09, 2022 10:22 pm at Mon May 09, 2022 10:22 pm
>
> 
MaZTeR wrote: ↑Sun May 08, 2022 8:48 pm
Mesh_0322 has 98304 vertices according to 3D Max.

if you open it in hexeditor you will see that there are no vertices there. only faces. and at the beginning it says that stride 0.
(since there are none, then when importing / exporting, all vertices will be as zero)

Ah damn. I wonder why it successfully is able to rip the head object but nothing else.
