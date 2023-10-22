## Post #1
- Username: HardRain
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2021 12:54 pm
- Post datetime: 2022-02-07T21:34:23+00:00
- Post Title: Van Helsing PS2 .bin models

I am here to ask if someone please can help me exporting the contents of .bin files from Van Helsing PS2 game, it contains 3D models and its textures from characters and missions.



Link for downloads:
Characters
[https://drive.google.com/file/d/1Yzq9Fd ... sp=sharing](https://drive.google.com/file/d/1Yzq9FdqtMxJVdxrey9EPPk9ucctCbNCS/view?usp=sharing)
[https://drive.google.com/file/d/1pTEdag ... sp=sharing](https://drive.google.com/file/d/1pTEdagAcr3_vB__rI_xjYel9FVWGHWJh/view?usp=sharing)

Level
[https://drive.google.com/file/d/145lqwJ ... sp=sharing](https://drive.google.com/file/d/145lqwJ4nS6mqFdmkSnbHv_Hfe973I9eY/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-08T13:07:30+00:00
- Post Title: Van Helsing PS2 .bin models

Didn't bother searching for face indices:
.



VanHelsing-grp-bin.png (27.95 KiB) Viewed 257 times


(Small submeshes of about 137 vertices each need to be assembled.)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-08T19:19:34+00:00
- Post Title: Van Helsing PS2 .bin models

collected some submeshes (vertex count 42 may be too low for some of them since I didn't search for the correct value)
.



VanHelsing-point-cloud.png (40.13 KiB) Viewed 237 times


(In the lower part I chose vcount=79, maybe grabbed some normals thus.)
## Post #4
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-02-09T19:47:29+00:00
- Post Title: Van Helsing PS2 .bin models

So it looks like the sequence is UV, Vertices and then the normals.
You may need to create a .bms script to extract the files,
perhaps the file structure appears to be:

```
long - starting address
long - unknown
long - unknown
long - name address
long - unknown
long - file size
long - unknown
long - unknown
long - unknown
long - FFFFFFFF?

```
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-10T11:22:37+00:00
- Post Title: Van Helsing PS2 .bin models

> Reply from reh ↑Thu Feb 10, 2022 3:47 am at Thu Feb 10, 2022 3:47 am
>
> You may need to create a .bms script to extract the files,bms scripts are used for decompressing, usually. But I didn't see compressed parts in the grp.bin file. Did I miss something?
## Post #6
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-02-10T15:25:51+00:00
- Post Title: Van Helsing PS2 .bin models

Files are concatenated, if you go to offset 0x5DD8 you will see a list of filenames contained in ND_R01.GRP.bin
I believe that for a better handling of these files it would be easier if they were not in a single file.
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-10T17:09:15+00:00
- Post Title: Van Helsing PS2 .bin models

```
int data_offset
int unk //32

for (num_file)
    int  unk0 //always 0
    int  offset_name
    seek (offset_name) >> string name
    int  unk1
    int  size_data
    int  unk2 //always 0
    int  unk3
    int  unk4
    int  unk5//always -1
    int  unk6//always 0
    
seek (data_offset)
    
```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-11T06:07:17+00:00
- Post Title: Van Helsing PS2 .bin models

> Reply from reh ↑Thu Feb 10, 2022 11:25 pm at Thu Feb 10, 2022 11:25 pm
>
> 
Files are concatenated, if you go to offset 0x5DD8 you will see a list of filenames contained in ND_R01.GRP.bin
I believe that for a better handling of these files it would be easier if they were not in a single file.I see the point. Thing is that the character file VANHELSING.GRP.bin contains about 109 small submeshes with 40..80 vertices. Not sure whether dividing up to separate files gives an advantage (maybe some of them are bigger, just used 42 and 79 as quickhack vertex counts for them all, no time to care for it atm). 

Maybe level files contain bigger parts. But usually you'd treat levels "undivided".

btw, there's "Created by: JOF2MDL Ver 1.6" in the .bin file. Anyone knows this tool?

well, this one is dead ugly (some details look correct):
.



VanH_deadUgly.png (253.21 KiB) Viewed 142 times
## Post #9
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-03-27T21:06:14+00:00
- Post Title: Van Helsing PS2 .bin models

Hi, I was doing some research(yes, a year later, lol) but I used XBOX files. I think is more easy to understand, I analyzed an enemy "OWL" (OWL_BASE.GRP.bin) so I cut the mesh part(mdl) and pasted this in a new file("OWL_BASE_model"), this was what I found:


With that info I used model researcher, now we have the complete mesh:



But it looks like a mess.. I guess we need to apply the skeleton but I don't know how to do that. Skeleton in "OWL_BASE.GRP" is at 0x49A80.
Some notes:
-OWL_BASE has one mesh, other characters/enemies have more meshes. For example Van Helsing has more meshes for the head(Face, hat, hair. etc), the rest of the body is in one single mesh. You can find a mesh for the shadow too.
-VANHELSING.GRP.bin has meshes for weapons and effects, the model is in "VANHELSING_BASE.GRP.bin" so models for characters/enemies are in "xxx_BASE.GPR.bin" files.
-Textures are DDS so it is easy to extract those. 
-There is a table about material(?) before each mesh(mdl).

Here are some samples:
[https://www.mediafire.com/file/34hd4fug ... s.rar/file](https://www.mediafire.com/file/34hd4fugbtejs9k/VH_XBOX_samples.rar/file)

OK, that is all. I hope this helps a little bit, Thanks for reading all this crap
