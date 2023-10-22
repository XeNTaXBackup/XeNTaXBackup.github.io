## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-04-16T09:33:54+00:00
- Post Title: TitanFall 2 MDL format ( fit faces and vertices )

hello people   

For days I been trying to obtain models from TitanFall 2 but I have lot of problems using decompiler tools or hex2obj.
This game runs under source engine and the formats used for models is MDL but with some differences.

first, all parts that compose a model in original Source Engine (MDL, VVD, VTX, PHY) are composed in a single file where the mdl section has changed in comparison to the vertex and face sections (VVD and VTX respectively), which mantain the original structure, also all addresses respond to a single big file instead a sectioned file.
the decompiler tools doesn't work due this differences and hex2obj can't figure out a correct mesh because the faces don't fit with vertices

in all models the vertex buffer start with the string IDSV and faces (supposedly) start with a pattern 00 00 01 00 02.

so, I want to know if someone with knowledge of this format can take a look or can share some info, specifically how to fit vertices and faces.

here are some samples and thanks.

EDIT: Some samples works under hex2obj perfectly but other no like imc_grunt_smg.mdl

[http://www.mediafire.com/file/ip83mpgig ... humans.rar](http://www.mediafire.com/file/ip83mpgig5lf6wu/humans.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-16T09:53:33+00:00
- Post Title: TitanFall 2 MDL format ( fit faces and vertices )

> Reply from luxox18
>
> hex2obj can't figure out a correct mesh because the faces don't fit with verticesmay depend on the specific model you chose, but for imc_hero_richter.mdl, it's one of the simplest formats I've ever come across.  

It requires some scrolling through the file, of course, and some "feeling of 3D flow" (people might hate it when I write "experience"):
search for 0000 0100 0200 gives 237 finds, or so.
Well, 0xE7C8 is obviously not a good start. Checked some others, finally 0x24932C looked ok to me.
Next find:
0x253154, size 0x9E28 / 2 -> 20244 face indices (dec.)

max. FI is 6048 (lower left listbox), chosen as vertex count

some scrolling for the vertices, 0x2986C8 looks good
FVF size, 48 obviously, floats, 12 bytes position, 12 bytes normals, uvs to follow? yes
so uv pos is 24:



TF2-richter.JPG (92.66 KiB) Viewed 156 times


(in fact it took me more time to write this post than to extract the model, cheers  )
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-04-16T10:10:45+00:00
- Post Title: TitanFall 2 MDL format ( fit faces and vertices )

> Reply from shakotay2
>
> luxox18 wrote:hex2obj can't figure out a correct mesh because the faces don't fit with verticesmay depend on the specific model you chose, but for imc_hero_richter.mdl, it's one of the simplest formats I've ever come across.  

It requires some scrolling through the file, of course, and some "feeling of 3D flow" (people might hate it when I write "experience"):
search for 0000 0100 0200 gives 237 finds, or so.
Well, 0xE7C8 is obviously not a good start. Checked some others, finally 0x24932C looked ok to me.
Next find:
0x253154, size 0x9E28 / 2 -> 20244 face indices (dec.)

max. FI is 6048 (lower left listbox), chosen as vertex count

some scrolling for the vertices, 0x2986C8 looks good
FVF size, 48 obviously, floats, 12 bytes position, 12 bytes normals, uvs to follow? yes
so uv pos is 24:
TF2-richter.JPG
(in fact it took me more time to write this post than to extract the model, cheers  )

hahaha thanks but I forgot to say that this doesn't work in all models, that's why I uploaded some samples that works under hex2obj and other no, like imc_grunt_smg.mdl ( sorry for the incomplete info    (What a shame
   ) )
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-16T11:03:52+00:00
- Post Title: TitanFall 2 MDL format ( fit faces and vertices )

> Reply from luxox18
>
> and other no, like imc_grunt_smg.mdlyeah, that's indeed a little bit strange, since the point cloud looks ok
