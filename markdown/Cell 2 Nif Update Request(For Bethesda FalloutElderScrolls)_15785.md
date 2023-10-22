## Post #1
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-01-25T07:56:11+00:00
- Post Title: Cell 2 Nif Update Request(For Bethesda Fallout/ElderScrolls)

CellToNif (by Yacoby) is a program that converts 'Morrowind' Map Mesh Cell Data into a 3D Nif Format
Sources:
[https://github.com/Yacoby/CellToNif](https://github.com/Yacoby/CellToNif)
[http://www.nexusmods.com/morrowind/mods ... w%3D&pUp=1](http://www.nexusmods.com/morrowind/mods/20928/?tab=1&navtag=http%3A%2F%2Fwww.nexusmods.com%2Fmorrowind%2Fajax%2Fmoddescription%2F%3Fid%3D20928%26preview%3D&pUp=1)


Morrowind uses a 64x64 Cell Grid, I am hoping this could be updated to work with Fallout 3, New Vegas, Oblivion, Skyrim Fallout 4. (All of these use a 32x32 Cell Grid)



An Importer/Exporter option would be awesome to create terrain in 3DS max rather than the respective Creation Kits (TESxCK+GECK)

It could also be used to import Cell Data from one game to the next, for example I started making a map in Skyrim but now want to copy that over to Fallout 4
I tried using the respective xxEdits to copy cell vertex data from one 'esp' to the next but it doesnt really work (I assume this is a basic problem with the file offsets)
## Post #2
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-02-02T09:55:44+00:00
- Post Title: Cell 2 Nif Update Request(For Bethesda Fallout/ElderScrolls)

I've created this simple indentifiable untextured landscape within a SKYRIM Cel 0,0


For those who dont have the Creation Kits and would like to have a look I have attached this Esp which contains the model data.

If someone could write a model import/export script It would save me time eternal
[ABCSKY.7z](https://xentaxbackup.github.io/file/12370_ABCSKY.7z)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-02-03T19:09:45+00:00
- Post Title: Cell 2 Nif Update Request(For Bethesda Fallout/ElderScrolls)

There is no subrecord "INTV" for the record "LAND" in Fallout3.esm, in Skyrim.esm it seems to have another meaning.

I don't think that someone will dig into the "LAND" records of FO3 and TESV if you won't do it.

Iirc the landscaping in bethsoft games is based on heightmaps.
Did you take into account to use TESAnnwyn.exe?

(I created a Skyrimp.esp using
TESannwyn -i Skyrim -p 1 -b 16 -d 4096x4096 -s 0.4 -x -64 -y -64 -h -20800 -w Colovia TamBeta03prepped_c_Cl.raw
on a gigantic raw file.

And this is the problem with the exe: to know which params to use)
## Post #4
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2017-02-04T00:22:07+00:00
- Post Title: Cell 2 Nif Update Request(For Bethesda Fallout/ElderScrolls)

[https://github.com/TES5Edit/fopdoc](https://github.com/TES5Edit/fopdoc) has documentation (such as exists) for the Fallout 3/NV/4 esp/esm formats.
[http://www.uesp.net/wiki/Tes4Mod:Mod_File_Format](http://www.uesp.net/wiki/Tes4Mod:Mod_File_Format) has the Oblivion docs.
[http://www.uesp.net/wiki/Tes5Mod:Mod_File_Format](http://www.uesp.net/wiki/Tes5Mod:Mod_File_Format) has the Skyrim docs.

So assuming there are no holes in the documentation, all the needed info should be there.
## Post #5
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-02-04T09:48:29+00:00
- Post Title: Cell 2 Nif Update Request(For Bethesda Fallout/ElderScrolls)

I've never heard of TESAnnwyn but at a glance it just looks like a program to create heightmaps (Creation Kit also has its own built in Paint program for this)  My goal is to get some XYZ Perfect co-ordinatemap placements.

I'm guessing that what this means is that the Creation Kit converts the model data back into a Hightmap format data.



This is all of the VHGT Data for the Centre Cell Shown

```
00 00 80 C3 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 [b]7F 81[/b] 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 [b]7F 81[/b] 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 [b]7F 81[/b] 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 [b]7F 81[/b] 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 18 00
```

Unless Im completely mad 7F 81 represents the hight and location of each 4 points shown in the model

I'm pretty sure that the older Morrowind Cell data also uses this type of cell construction and Yacoby has shown its possible to convert that data to Nif.  It would be great if that process could be reversed , and since each mesh coordinate is based on Hight (z-axis) I really hoped that this would be a pretty simple operation.  Even though Bethesda have used the same method of Landscape construction they seem to purposefully alter it from game to game so they arnt natively compatible.(since I have already tried copy/pasting the Vertex infos in TesEDIT)

Its not the end of the world i do have another method of recreating Cells its just time consuming.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-02-04T10:50:20+00:00
- Post Title: Cell 2 Nif Update Request(For Bethesda Fallout/ElderScrolls)

> Reply from ReeceMix
>
> Unless Im completely mad 7F 81 represents the hight and location of each 4 points shown in the modelif so then I don't understand why you don't change some of the zeroes and watch the results ingame or in the construction set?
After verifying you could create 3D vectors of the data.
(Where I don't know why it should contain the location? Isn't it given by the square map, 32x32, 64x64, whatever)?
So do we have 1024 DWords in that data? Seems it's about 552. Why?

> Its not the end of the world i do have another method of recreating Cells its just time consuming.then you're fine, aren't you?  
I'm too busy with my own projects than to dig into that "INTV" problem; all I can give is some assistance.
## Post #7
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-02-04T10:55:26+00:00
- Post Title: Cell 2 Nif Update Request(For Bethesda Fallout/ElderScrolls)

> Reply from shakotay2
>
> I'm too busy with my own projects than to dig into that "INTV" problem; all I can give is some assistance.

Not a problem Dude , I am just a lowly modder who has been forced to look at Hex from time to time, creating importers/exporters etc, Is out of my current skillset and all I can do is ask.
