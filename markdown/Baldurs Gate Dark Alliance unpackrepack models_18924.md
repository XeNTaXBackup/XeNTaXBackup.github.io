## Post #1
- Username: bgdaNerd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2018 2:25 am
- Post datetime: 2018-10-12T18:34:25+00:00
- Post Title: Baldurs Gate Dark Alliance unpack/repack models

One of my favorite games for PS2. Saw that there is a tool that can extract model data from the game files: [https://github.com/bigianb/bgda-explorer](https://github.com/bigianb/bgda-explorer) 

This tool works great for getting data off the game but I was wondering if it is possible to modify the models/textures etc. then repack them into the LMP file. This would allow for some cool mods for snowblind engine games.

Anyone have any ideas/ resources I can check out to better understand how to do this?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-12T19:59:39+00:00
- Post Title: Baldurs Gate Dark Alliance unpack/repack models

We'd need an .LMP file to tell more.
## Post #3
- Username: bgdaNerd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2018 2:25 am
- Post datetime: 2018-10-12T21:59:25+00:00
- Post Title: Baldurs Gate Dark Alliance unpack/repack models

Here is the lmp file for the dwarf character (bgda2): [https://ufile.io/7qoua](https://ufile.io/7qoua)

Here is that file open in the explorer (as you can see contains all animations and the base model for the character): [https://imgur.com/a/wJc1cbh](https://imgur.com/a/wJc1cbh)

There is also lmp files for all other game assets (armor weapons scenery).
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-12T23:16:15+00:00
- Post Title: Baldurs Gate Dark Alliance unpack/repack models

thanks! Tomorrow I'll see whether I can add some debug/loggging lines to the C# code (not my preferred language, though) so that some format specs can be generated (where is the vif in the .lmp for example).
(not sure whether you have the .vif specs already?)
In fact you need a full format analysis before you can create a vif from an obj file.

The exporter seems to work, as you stated:



dwarf.png (163.86 KiB) Viewed 232 times
## Post #5
- Username: bgdaNerd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2018 2:25 am
- Post datetime: 2018-10-13T01:36:34+00:00
- Post Title: Baldurs Gate Dark Alliance unpack/repack models

So I figured out how to repack the LMP file. Someone has already made a BMS script for baldurs gate: [viewtopic.php?f=13&p=86343](http://forum.xentax.com/viewtopic.php?f=13&p=86343)

> Reply from AlphaTwentyThree
>
> Baldur's Gate: Dark Alliance (PS2) - *.GOB/*.LMP
Code: Select all# extracts *.GOB archives from "Baldur's Gate: Dark Alliance" (PS2)
# (c) 2013-06-28 by AlphaTwentyThree of XeNTaX

for
	getDstring NAME 0x20
	get OFFSET long
	get SIZE long
	if NAME == ""
		cleanexit
	endif
	log NAME OFFSET SIZE
next
Code: Select all# extracts *.LMP archives from "Baldur's Gate: Dark Alliance" (PS2)
# (c) 2013-06-28 by AlphaTwentyThree of XeNTaX

get FILES long
for i = 1 <= FILES
	getDstring NAME 0x38
	get OFFSET long
	get SIZE long
	log NAME OFFSET SIZE
next i

So using quickbms you can easily pack and unpack the archive. Now just to figure out how the textures(tex) and models(vif) are encoded (should be able to reverse however they are decoded in the explorer). 

On a little off topic note, there is a bunch of script files and audio files present in the lmp and GOB(level) files. The audio files are easy (VAG) but the script files idk how to open them... There is also an OB file in the GOB archive that contains coordinates for all objects in each level.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-13T12:34:29+00:00
- Post Title: Baldurs Gate Dark Alliance unpack/repack models

Unpacking the dwarf.lmb results in 90 files, here's two of them:

00044e00 69024 dwarf.tex
00055c00 112784 dwarf.vif (mesh)

So 0x55C00 is the offset into dwarf.lmb where the vif resides.
When trying to create a vif from obj we need to understand the vif format and it appears to be a very time consuming task. I put some more log lines to the log window of the WorldExplorer (which unpacks the vif from lmb automatically)
and as you may see, it's not "funny" (RV means ReadVerts() function):
First mesh starts at 0xC08 (offset into .vif; you need to add 0x55C00 for the dwarf to find the data in the lmb file).

RV: 0x00000c00
0x00000c03: 0x00000004
0x00000c07: 0x00000069
0x00000c08: v-16 -> vertices
0x00000cf7: 0x0000006a
0x00000cf8: v-8 -> vertices
0x00000d73: 0x00000069
0x00000d74: v-16 -> vertices
0x00000e6f: 0x0000006e
0x00000e70: weights
0x00000e77: 0x0000006d
0x00000e78: ?
v4-16 data, 4 entries, addr=120
0x00000e9b: 0x0000006c
0x00000e9c: GifTags?
v4-32 data, 1 entry, addr=124
0x00000eaf: 0x00000014
0x00000eb3: 0x00000001
0x00000eb7: 0x00000065
0x00000eb8: uv-16
0x00001007: 0x00000001
0x0000100b: 0x00000000
0x0000100f: 0x00000000
0x00001013: 0x00000004
0x00001017: 0x00000069
0x00001018: v-16
0x00001113: 0x0000006a
0x00001114: v-8
0x00001193: 0x00000069
0x00001194: v-16
0x0000129b: 0x0000006e
0x0000129c: weights
0x000012a3: 0x0000006d
0x000012a4: ?



bgda - dwarf-vif.png (60.35 KiB) Viewed 213 times
