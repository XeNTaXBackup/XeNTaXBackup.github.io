## Post #1
- Username: PedroSilvaPES14
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 02, 2017 6:38 am
- Post datetime: 2017-09-01T23:55:15+00:00
- Post Title: Help with Script to extract 3D Models from a .bin file PS2

Hello anyone could tell me if this Script works properly.
I was looking for a way to extract 3D models from the PES 2014 PS2 game.
And I found these Scripts for QuickBMS however I'm not sure if they work well.
Scripts: [http://ps23dformat.wikispaces.com/Pro+E ... occer+2013](http://ps23dformat.wikispaces.com/Pro+Evolution+Soccer+2013)
Bin Files PES 14 PS2 Models 3D: [https://www.4shared.com/rar/SjLAH8K0ca/ ... ls_3D.html](https://www.4shared.com/rar/SjLAH8K0ca/Bin_File_PES_14_PS2_Models_3D.html)? 
After extracting the model in .3ds I open it in the blender and it gets half erased.
And also can not import it back to the .bin file
And I was wondering if there is another way to extract 3D models from .bin files.
Like for example via Hexadecimal with Hex Workshop.
And if anyone knows more about these types of models, please I wanted details about them so I could find ways to work with them.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-02T12:01:59+00:00
- Post Title: Help with Script to extract 3D Models from a .bin file PS2

> Reply from PedroSilvaPES14
>
> Hello anyone could tell me if this Script works properly.speaking of PES2013DCMeshBinTo3ds.bms, obviously not.

> And I found these Scripts for QuickBMSwell, that above mentioned script looks like a sibling of world "famous" WildArms3eememoryto3ds.BMS. Variables like snake, dragon and deerdeerfox, no indentations, no comments make it hard to understand. Also those scripts don't provide uvs. 

> After extracting the model in .3ds I open it in the blender and it gets half erased.no, it's just what the scripts extracts. You could patch the script like such to get more vertices:
findloc OFFSET string "\x00\x04\x01\x00\x01" 0 0 ;

```
    GoTo OFFSET 0 ;
    GoTo 0x6 0 SEEK_CUR ;
    Get dummy Byte 0 ;
    Get onetest Byte 0 ;
    Get twotest Byte 0 ;
    SavePos found 0 ;
EndIF ;
```
>>> May add more faults, though, because I made just a quickhack. ### (This script is a waste of time&life, imho.)
Checked with unknow_01192.str_000 only!



PES2013-binTo3ds.JPG (36.31 KiB) Viewed 195 times



> And also can not import it back to the .bin fileha, well, very good joke. Forget that as long as the script doesn't create correct 3ds files.
(Also reversing does only work with simple bms decompression scripts if I understood correctly.)

> And I was wondering if there is another way to extract 3D models from .bin files.not to my knowledge for those specific bin files.
You might read here, though, for some format details: [http://ps23dformat.wikispaces.com/Wild+Arms+3](http://ps23dformat.wikispaces.com/Wild+Arms+3)
Maybe they're similar.
## Post #3
- Username: PedroSilvaPES14
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 02, 2017 6:38 am
- Post datetime: 2017-09-02T16:49:38+00:00
- Post Title: Help with Script to extract 3D Models from a .bin file PS2

The only thing I found out about these PES PS2 models is that one can change parts of the model by other parts of other models.
For example, by copying one part of the model and pasting it over a part of another model.
Part of the 3D model: [https://imgur.com/a/y6pXE](https://imgur.com/a/y6pXE) 500A: It is the byte numbers of that part.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-02T19:25:48+00:00
- Post Title: Help with Script to extract 3D Models from a .bin file PS2

I checked the point cloud of 01190 and it looked ok to me.



PES2013_01190.str_000-1.jpg (26.22 KiB) Viewed 187 times


So it should be a matter of face indices.

Removed duplicate vertices and added autocreated face indices (tris, then strips) but at no avail.
## Post #5
- Username: PedroSilvaPES14
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 02, 2017 6:38 am
- Post datetime: 2017-09-02T20:50:57+00:00
- Post Title: Help with Script to extract 3D Models from a .bin file PS2

This model is a player on top of an ostrich, As you can see in this video here: [https://www.youtube.com/watch?v=8nfhSJDskbM](https://www.youtube.com/watch?v=8nfhSJDskbM)
3D Model Texture: [https://imgur.com/a/SJiwz](https://imgur.com/a/SJiwz)
## Post #6
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-09-03T04:20:58+00:00
- Post Title: Help with Script to extract 3D Models from a .bin file PS2

I haven't had much luck with anything from that link either. The one for the Japanese Transformers game most recently says the files from the game are not files from the game (?).
