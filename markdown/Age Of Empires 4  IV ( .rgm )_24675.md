## Post #1
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-02T03:50:02+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

Its relic chunky
but i dont know any tools to open / convert it

Engine: Essence Engine 5.0

( i also added other files since i dont know if its a model or something )
FIle Samples: [https://drive.google.com/drive/u/3/fold ... 0kyt6-ZinO](https://drive.google.com/drive/u/3/folders/1aD5KWZYSfNxS5sNI8O5vbc0kyt6-ZinO)
## Post #2
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-02T08:56:46+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

RRGeom appears to be the mesh file, appears to have what I can only assume is multiple LODs packed in each file (or maybe different age upgrades from the game when you go to the next age).  

Last LOD I could find starts at offset 107048, 5256 verts, 10 padding - half floats. Vert count is at offset 193299. Faces I can't figure out however for now after a quick look.

Result so far


Faces at 2F324, seems like it's half-float for verts and short faces.
Count 5256 also 


Settings: 

This is pretty much all I can do with my limited knowledge for this file.

EDIT 2: It isn't LODs by the looks of it, just the submeshes split or something of the sort, couldn't combine all of them together with parameter sets on AXE unfortunately.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-02T13:55:37+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

> Reply from dimis9138 ↑Tue Nov 02, 2021 4:56 pm at Tue Nov 02, 2021 4:56 pm
>
> couldn't combine all of them together with parameter sets on AXE unfortunately.
Why? You've made it with the last one.  



chi_archery_range_control_age02.rrgeom.png (163.83 KiB) Viewed 239 times



chi_archery_range_control_age02.rgm contains the same model as the one in chi_archery_range_control_age02.rrgeom BTW. Just without normals and texcoords though.
## Post #4
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-02T14:27:45+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

> Reply from Bigchillghost ↑Tue Nov 02, 2021 9:55 pm at Tue Nov 02, 2021 9:55 pm
>
> 
dimis9138 wrote: ↑Tue Nov 02, 2021 4:56 pmcouldn't combine all of them together with parameter sets on AXE unfortunately.

Why? You've made it with the last one.

My result with the same settings: 



Is it because I haven't done multiple meshes on the parameter list on the top left? And if so how did you use it to separate mesh 0, 1 and 2? Or what am I missing here? 
Although that does make me wonder, are the other meshes in the same file showing anything else that I can't see like I can't see with the last mesh due to something being wrong in my settings?

By the way, quick question - why does AXE convert the 10 for stride to 16?
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-02T15:12:05+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

> Reply from dimis9138 ↑Tue Nov 02, 2021 10:27 pm at Tue Nov 02, 2021 10:27 pm
>
> 
Is it because I haven't done multiple meshes on the parameter list on the top left?
Yes. All params you can see from the panel, except for the endianness and those of the materials and bones, are properties of ONE mesh. To save multiple mesh objects, you must add it to the Prameter List and use the "from/in List" operations for export/preview. Thought I'd already mentioned that:

> Reply from Bigchillghost ↑Sun Oct 31, 2021 2:26 pm at Sun Oct 31, 2021 2:26 pm
>
> 
... So you have to save the existing params of the 1st mesh into the "Paramter List" (by clicking the "Add" button, yes), and start over for the rest "mesh" objects.


> Reply from dimis9138 ↑Tue Nov 02, 2021 10:27 pm at Tue Nov 02, 2021 10:27 pm
>
> 
are the other meshes in the same file showing anything else that I can't see like I can't see with the last mesh due to something being wrong in my settings?
No. Nothing different in particular.

> Reply from dimis9138 ↑Tue Nov 02, 2021 10:27 pm at Tue Nov 02, 2021 10:27 pm
>
> why does AXE convert the 10 for stride to 16?
What's "10" for? The size of each vertex element (including pos, norm & uv) is 16 bytes, that's what the stride stands for.
## Post #6
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-02T15:30:54+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

> Reply from Bigchillghost ↑Tue Nov 02, 2021 11:12 pm at Tue Nov 02, 2021 11:12 pm
>
> 
Yes. All params you can see from the panel, except for the endianness and those of the materials and bones, are properties of ONE mesh. To save multiple mesh objects, you must add it to the Prameter List and use the "from/in List" operations for export/preview. Thought I'd already mentioned that:

That actually worked, nice! I just need to figure out material groups now hah but shouldn't be too hard, just assign a material to each mesh parameter.

Also 10 stood for the padding (the hex length) cause I used MR initially to figure out the mesh before going over to AXE, hence why I was wondering why it converted it to 16 but I was dumb cause I didn't consider that in HxD that it was 16 indeed. You should defo offer tutoring by the way, would definitely pay by the hour!
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-02T16:04:10+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

> Reply from dimis9138 ↑Tue Nov 02, 2021 11:30 pm at Tue Nov 02, 2021 11:30 pm
>
> 
Also 10 stood for the padding (the hex length) cause I used MR initially to figure out the mesh before going over to AXE
If I ever remember correctly the "padding" indicates the number of bytes to skip, after reading the data, not because it's in hex notation.

> Reply from dimis9138 ↑Tue Nov 02, 2021 11:30 pm at Tue Nov 02, 2021 11:30 pm
>
> 
You should defo offer tutoring by the way, would definitely pay by the hour!
That, however, will cost much more hours which I have no intention for. Read the specification of AMR instead for detailed explanation.

> Reply from Bigchillghost ↑Mon Aug 19, 2019 2:27 pm at Mon Aug 19, 2019 2:27 pm
>
>
## Post #8
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-04T13:56:23+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

i tried this method by Bigchillghost

so i downloaded AXE
but it says its missing some ddl
and i cant the view scene

( edit nvm i just noticed the txt file )
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-04T14:00:06+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

The links to the required components are included in the download. Just read the post and follow the instructions.
## Post #10
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-04T14:17:01+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

ye thanks 
I just noticed it
## Post #11
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-05T12:13:14+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

Thanks to DKDave & Joschka I was able to come up with this noesis plugin, this doesn't work with all stuff since it essentially looks for the DATAGEOB header, counts it's verts count and offsets it for the verts buffer, then looks for next DATAGEOB faces count and counts that as faces count and offsets it for the faces buffer, however in some cases it has two DATAGEOB headers for vertices, meaning that it doesn't work in those cases and I don't know how to fix it for that - but it should work with most props. If someone could fix it for that and post their version so I could understand Noesis better I'd really appreciate it!
## Post #12
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-05T13:41:32+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

Example of a file it won't work with:
[dan_tent_control_a.rar](https://xentaxbackup.github.io/file/21149_dan_tent_control_a.rar)
## Post #13
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-05T22:21:16+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

Fixed issue above thanks to DKDave's help, it now grabs the correct stride, should work with most if not all models.
Please use this only to reverse models to fix bugs and such and not commercialized reasons. 


 fmt_aoe4.rar
(691 Bytes) Downloaded 34 times
## Post #14
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-07T10:26:13+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

Damnnnn, Thanks for this plugin

It works on all models i have tested
## Post #15
- Username: Tora
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 02, 2021 7:33 am
- Post datetime: 2021-12-02T01:15:30+00:00
- Post Title: Age Of Empires 4 / IV ( .rgm )

Hey, thank you for the information in this thread. I added initial .rrgeom support to [https://github.com/aoemods/AOEMods.Essence](https://github.com/aoemods/AOEMods.Essence). I noticed some rrgeoms have 28 bytes per vertex and some (like the first one in this thread) have 16, perhaps there are even more. Right now I just read the first two GEOB chunks of each geometry object in the file and assume the first stores positions as halfs (and I skip the rest of the vertex data) and the second stores faces. Hopefully we can figure everything out and also convert the material files (I already have a converter for the textures too).
## Post #16
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-12-02T20:24:28+00:00
- Post Title: Re: Age Of Empires 4 / IV ( .rgm )

> Reply from Tora ↑Thu Dec 02, 2021 9:15 am at Thu Dec 02, 2021 9:15 am
>
> 
Hey, thank you for the information in this thread. I added initial .rrgeom support to https://github.com/aoemods/AOEMods.Essence. I noticed some rrgeoms have 28 bytes per vertex and some (like the first one in this thread) have 16, perhaps there are even more. Right now I just read the first two GEOB chunks of each geometry object in the file and assume the first stores positions as halfs (and I skip the rest of the vertex data) and the second stores faces. Hopefully we can figure everything out and also convert the material files (I already have a converter for the textures too).

Unsure whether you're talking about the stride or not but for my little Noesis plugin I just instead looked for the header, then skipped 0x14 for verts, read the VCount, 0x4 to get the stride, then VCount & VStride and repeat the same technique to get FCount. You can look at my plugin for reference.

For reference also, verts are halfs, normals are bytes, UVs are half floats and faces are unsigned shorts. This is what I was able to pull with my very, very limited skills.
