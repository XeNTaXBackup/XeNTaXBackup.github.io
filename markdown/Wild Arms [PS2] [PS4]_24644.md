## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-10-27T17:25:12+00:00
- Post Title: Wild Arms [PS2] [PS4]

Wild Arms 3 [PS2] [PS4] tools.

Tested for US game PS2 image SCUS-97203, also included in PS4 release.
Support of all characters/monsters with their textures and animations.
Also extracts stages (levels) with their props, NPCs and cutscenes.




[wa3.rar](https://xentaxbackup.github.io/file/21082_wa3.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-10-27T17:27:17+00:00
- Post Title: Wild Arms [PS2] [PS4]

Usage

First, you need to split BIN archives to individual packages that i called SEG files, like segments.

For this, you need "table" *.T files from the executable (included).
Place them to corresponding folders with BIN files.

Drop .T or .BIN on WildArms3_bin.exe, doesnt matter.

character/monster packs

BTLMON.BIN - all monsters and characters
BTLANM.BIN - horse rides and such

Use wa3_seg_mon.bms to decompress .SEG files. Each will have 1 monster or character.
After you get SEG decompressed, you'll get a set of files, which will be similar for ALL of them.

Use WildArms3_texture.exe to convert textures:

WildArms3_texture  5.dat  6.dat
5 is palette
6 is image
------------

main 3 files you will need for the model are always named  C D E
C is description
D is skeleton
E is model

You have to pass these all to WildArms3_model.exe, and they must be in that order:  C D E
Example:   WildArms3_model.exe 0000000C.dat 0000000D.216 0000000E.dat
you will get same model in SMD and ASCII

------------

All files after those will be animations.
Animations will all be named like  *.213
Remaining small .dat files are not needed, they are animation bounding boxes, or something, useless for us. So you need to process animations to apply to models.

For this, use WildArms3_anm.exe

It needs 2 files: skeleton and animation.
So use like ...  WildArms3_anm.exe 0000000d.216 00000011.213

It will make .smd with extracted animation. Then apply animations to the model in your 3d software.
You can use batch to process all animations at once.

Video for example horse ride animation: [https://youtu.be/CEq0UFCnd4c](https://youtu.be/CEq0UFCnd4c)
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-10-27T17:29:06+00:00
- Post Title: Wild Arms [PS2] [PS4]

Stages:







Split STGMAP.BIN into individual .seg files, then decompress any of them with wa3_seg_stg.bms

each will have 2 map parts: exterior and interior

their files will be same as for models, and have names like:
6 7 8 - exterior
b c d - interior

use them with the model tool and it will export stages

Also stages usually have 2 internal packages:
10 - props and npcs
11 - main character animations for that stage (cutscenes)

Script to unpack them - wa3_seg_int.bms
Before unpacking internal package, rename it and move to another folder, so it will not crash.
Then you will see its all divided into small regions, for one prop or NPC each, and there are 0-sized files between.
Use their content with previous model and animation tools to extracted them.

Here's an example of NPCs and props:







Also main characters with all their animations for that stage (cutscenes):
## Post #4
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-10-27T18:10:01+00:00
- Post Title: Wild Arms [PS2] [PS4]

Here are the .seg filenames of BTLMON.  
[BTLMON.zip](https://xentaxbackup.github.io/file/21083_BTLMON.zip)
## Post #5
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-11-05T15:23:23+00:00
- Post Title: Wild Arms [PS2] [PS4]

[](https://ibb.co/FxHdNsS)
Using TexMod and PCSX2 you can place textures where they need to go. I've done a few now. Many repeating textures so I'm trying to organize them. Also adding missing alpha's. Here is the current BTLSTG.txt id say about 70% coverage.
[BTLSTG.zip](https://xentaxbackup.github.io/file/21150_BTLSTG.zip)
## Post #6
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-11-06T04:09:33+00:00
- Post Title: Wild Arms [PS2] [PS4]

Also here is the new BTLMON.txt with a few adjustments i put the horse rides in the folders below the duplicate ones of characters since there were only 4 files in BTLANM.bin
[BTLMON.zip](https://xentaxbackup.github.io/file/21152_BTLMON.zip)
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-28T17:21:34+00:00
- Post Title: Wild Arms [PS2] [PS4]

Wild Arms alter code F







Usage is the same as WA3, with a few exceptions:
Model files for description, skeleton and model will not always be C D E, you can find them easily anyway.
Files for maps will be
11 12 13 - exterior
16 17 18 - interior
1B - Internal package for props and npcs
[WAaltF.7z](https://xentaxbackup.github.io/file/21692_WAaltF.7z)
## Post #8
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-01-29T04:57:22+00:00
- Post Title: Wild Arms [PS2] [PS4]

Do I need  the game or is it in the files.
## Post #9
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-01-30T09:26:40+00:00
- Post Title: Wild Arms [PS2] [PS4]

A quick way to batch animations.
[](https://ibb.co/cT7F0HD)
Select all the .300 files and use CTRL+Right Click then select "Copy as Path"
[](https://ibb.co/FVx7KR2)
Open a txt document and past in the info copied.
[](https://ibb.co/hyv11tB)
Highlight this part "D:\ now do CTRL+H for rename/replace.
[](https://ibb.co/1nhGgCM)
I renamed tool to ANM.exe for easier batching but in the replace window. Type in the name of the tool. Then leave a space.
[](https://ibb.co/VQ93zzH)
Now paste in the location of the folder you are about to batch. Dont forget to put a " before the folder location.
[](https://ibb.co/rm8v284)
Once location is pasted be sure to put a / on the end. Now go to the .216 file and copy its name. Place this info right after the forward slash.
[](https://ibb.co/phw6ZLk)
Don't forget to put a " at the end of the the .216 file!! Then leave a space.
[](https://ibb.co/phw6ZLk)
Last place in the original location next. Then hit "Replace All".
[](https://ibb.co/b14pC8S)
You should now have a document looking something like this.
[](https://ibb.co/b6RX4xk)
Save the file as a "_.bat" so its at the very top of the folder. (Easier to find)
[](https://ibb.co/txTwZR1)
As long as the data is typed correctly and files are in location. It will process all files and convert the. 
[](https://ibb.co/vw9mmyw)
Open Blender and import the single .SMD. 
[](https://ibb.co/G3mTMsW)
Now import .SMD again and highlight all .SMD files and then click "Import"
[](https://ibb.co/s2qgHNx)
Once complete all tracks will be imported into 1 mesh. Save file as .FBX.
## Post #10
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-02-02T09:43:12+00:00
- Post Title: Wild Arms [PS2] [PS4]

Okay how do I do this.  okay  I have  the wild arms ios  what do I  do next.
