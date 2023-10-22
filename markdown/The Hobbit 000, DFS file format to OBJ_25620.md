## Post #1
- Username: captaintoasty
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 14, 2022 10:43 am
- Post datetime: 2022-07-14T21:18:41+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

Hi there!

I'm very new to the idea of converting raw binary files to something actually usable (like .obj). I'm a professional 3d modeler/tech artist and so have pretty good knowledge with Python and MAXScript, and some knowledge with C++, openGL, etc. On a technical level I'm fairly familiar with how geometry tends to be structured.

I followed some tutorials on YouTube and here and am still pretty lost. I used QuickBms to extract the .npcgeom, .rgeom, and .xbmp filetypes from the .000/.dfs files found in the game install dir. From here, using the .bms scripts I found on here and also on various sites (aluigi, ps23dformat) I think I got closer? But they still don't quite seem to work.

Any help or a step in the first direction would be appreciated! I'm interested on learning myself how to do this, not really expecting someone to necessarily do it for me.

Here's a public Google Drive link to the .000/.dfs files for one of the levels (Hobbiton), the extracted .rgeom file for the Sting sword, the extracted .xbmp (diffuse texture?) file, and the various .bms scripts I attempted to use.
[https://drive.google.com/file/d/1LWNI__ ... sp=sharing](https://drive.google.com/file/d/1LWNI__5ALZkab5tToPOp8MikJUOGRw_Y/view?usp=sharing)

Thanks!
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-14T22:45:55+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

> Reply from captaintoasty ↑Fri Jul 15, 2022 5:18 am at Fri Jul 15, 2022 5:18 am
>
> 
.rgeom file for the Sting sword.
[sting.rgeom_Fri_Jul_15_01-45-08_2022.png](https://xentaxbackup.github.io/file/22490_sting.rgeom_Fri_Jul_15_01-45-08_2022.png)
## Post #3
- Username: captaintoasty
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 14, 2022 10:43 am
- Post datetime: 2022-07-14T22:49:42+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

That was quick! Sorry, what viewer are you using for that? Also how did you determine the vertex offset, count, padding, and face offset, count and format?
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-14T22:53:07+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

> Reply from captaintoasty ↑Fri Jul 15, 2022 6:49 am at Fri Jul 15, 2022 6:49 am
>
> 
That was quick! Sorry, what viewer are you using for that? Also how did you determine the vertex offset, count, padding, and face offset, count and format?
for PC (Advanced Mesh Reaper, ModelResearcher, Hex2Obj) or Mesh Finder (Android) + HexEditor (HxD)
post more *.rgeom
the format is simple, we can now make a plugin for Noesis  (only mesh)
## Post #5
- Username: captaintoasty
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 14, 2022 10:43 am
- Post datetime: 2022-07-14T23:30:23+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

I've added some more .zips with .rgeom, .npcgeom, .charanim, .anim, .xbmp, .export filetypes.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1N9xmt9N0BC2UeblF8PXg7TFETp4ZdMgH?usp=sharing)

Thanks!
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-15T00:32:31+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

> Reply from captaintoasty ↑Fri Jul 15, 2022 7:30 am at Fri Jul 15, 2022 7:30 am
>
> 
.rgeom
two files are not enough. (not the fact that it will work with everyone)

[fmt_rgeom.zip](https://xentaxbackup.github.io/file/22494_fmt_rgeom.zip)
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-15T01:57:30+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

> Reply from captaintoasty ↑Fri Jul 15, 2022 7:30 am at Fri Jul 15, 2022 7:30 am
>
> 
.npcgeom
[*npcgeom] has several models (lods)
to switch between models press the button:

to export the current model: File>Export from Prewiew

[fmt_npcrgeom.zip](https://xentaxbackup.github.io/file/22503_fmt_npcrgeom.zip)
## Post #8
- Username: captaintoasty
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 14, 2022 10:43 am
- Post datetime: 2022-07-15T18:45:04+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

Sweet, thanks! I noticed when using these plugins in Noesis that there were no UVs obtained. I was playing around with ModelResearcher but was unable to find where exactly the UVs begin/what the proper values are. Any tips on how to figure that out?
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-15T19:36:56+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

> Reply from captaintoasty ↑Sat Jul 16, 2022 2:45 am at Sat Jul 16, 2022 2:45 am
>
> 
UVs
i update plugin npcgeom, plugin rgeom its ok.



uvs.png (116.51 KiB) Viewed 100 times
## Post #10
- Username: captaintoasty
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 14, 2022 10:43 am
- Post datetime: 2022-07-18T18:28:41+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

Hi Durik! Thanks again for the help last week. I've been using Noesis and these scripts work for about half of the models, but the other half don't seem to work. I uploaded 5 of each rgeom and npcgeom.

npcgeom
[https://drive.google.com/file/d/135AmIw ... sp=sharing](https://drive.google.com/file/d/135AmIwqMyBvSji_O_lgk0vW-9mCETKnL/view?usp=sharing)

rgeom
[https://drive.google.com/file/d/1ypsKyg ... sp=sharing](https://drive.google.com/file/d/1ypsKygmOJw2gRH8LaMWjsbh0dAHWp3t8/view?usp=sharing)

As far as I can tell, at least with rgeom, the standard structure for models which work is:

```
facecount

stride
vertexsize
vertexcount

vertices

indexes

```


But there's some .rgeom models (which are in the linked .zip) which really don't seem to follow this format at all. Any help would be appreciated! Thanks!
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-19T14:06:20+00:00
- Post Title: The Hobbit 000, DFS file format to OBJ

> Reply from captaintoasty ↑Tue Jul 19, 2022 2:28 am at Tue Jul 19, 2022 2:28 am
>
> 
Hi Durik! I uploaded 5 of each rgeom and npcgeom.

most likely not properly unpacked
