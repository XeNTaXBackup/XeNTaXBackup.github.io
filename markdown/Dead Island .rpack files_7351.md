## Post #1
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-13T10:53:59+00:00
- Post Title: Dead Island .rpack files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-09-13T13:01:16+00:00
- Post Title: Dead Island .rpack files

for example, content of act1a_load_PC.rpack:

header, 9 bytes
Code: Select allRP5L; 36; 2; 147; 5; 26; 410; 26; 2048
magic
version
type of compression (1-zlib, 2-???)
data size
sections count
files count
size of block with filenames
filenames count
block size
sections (lines count == sections count)
Code: Select all32; 512; 4096; 1760; 116; 22; 
33; 768; 6144; 14681120; 2532907; 113; 
48; 768; 2691072; 52032; 9170; 4; 
50; 768; 2707456; 23152; 5668; 4; 
51; 768; 2715648; 1816; 400; 4;
type 1, word
type 2, word
offset, int (absolute value, in .rpack)
unpacked size, int
packed size, int
elements count, int
32; 512 - analog of DDS header
33; 768 - textures mip levels in revese direction
(48; 768), (50; 768), (51; 768) - shaders(???)
files (lines count == data size)
Code: Select all0; 0; 0; 80; 0; 
1; 0; 0; 144; 116; 
1; 0; 2048; 256; 180; 
1; 0; 4096; 1024; 565; 
1; 0; 6144; 4096; 1965; 
1; 0; 8192; 16384; 6735; 
1; 0; 16384; 65536; 23830; 
1; 0; 40960; 262144; 86589; 
1; 0; 129024; 1048576; 360530; 
0; 1; 80; 80; 0; 
1; 1; 491520; 208; 137; 
1; 1; 493568; 512; 183; 
1; 1; 495616; 2048; 442; 
1; 1; 497664; 8192; 1160; 
1; 1; 499712; 32768; 3485; 
1; 1; 503808; 131072; 11286; 
1; 1; 516096; 524288; 39782;
...
section, int
file index, int
offset (relative to section), int
unpacked size, int
packed size, int
unknown section (lines count == files count)
Code: Select all9; 288; 0; 0; 
8; 288; 1; 9; 
9; 288; 2; 17; 
9; 288; 3; 26; 
9; 288; 4; 35; 
2; 288; 5; 44; 
...
type 1, word
type 2, word
file index, ind
unknown, int
filename offsets
Code: Select all0; 14; 28; 42; 56;...
items count = [b]filenames count[/b]
offset of AnsyString (0x00 ending) in next section
filenames (size of this section == size of block with filenames)
Code: Select allact1a_load_00
act1a_load_01
act1a_load_02
act1a_load_03
act1a_load_03l
...

> starting from 0x1000
not always. act1a_PC.rpack have a big header (his size ~480kB).
## Post #3
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-13T14:44:31+00:00
- Post Title: Dead Island .rpack files

what about a tool, is it possible? Seems you find almost everthing.
also you should correct those:
section, int  should be short
file index, int should be short
## Post #4
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-09-14T11:39:31+00:00
- Post Title: Dead Island .rpack files

That's nice! 
Any progress on maps maybe?
## Post #5
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-09-14T23:00:04+00:00
- Post Title: Dead Island .rpack files

> what about a tool, is it possible?
i'm working on it ;) but this is just extract tool and it can convert texture to DDS with mipmaps. other files are unknown format, there are also many obscure fields, so pack back is not yet possible.
## Post #6
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-09-15T07:04:40+00:00
- Post Title: Dead Island .rpack files

little tool for examine (no unpack) structure of rpacks (in attachment)
drag'n'drop one or more archives in program window, after parsing program will create a .txt files in the directory in which it is located.

sample output of menu2_main_PC.rpack:


```
// int, magic
// int, version (?)
// int, compression (1-zlib, 2-???)
// int, fileparts count
// int, sections count
// int, files count
// int, size of filenames
// int, filenames count
// int, block size
; 
RP5L; 36; 1; 28; 5; 12; 231; 12; 2048; 
; 
// sections:
// byte, type of file
// byte, ??? (0)
// byte, ??? (0)
// byte, ???
// int, offset (absolute)
// int, unpacked size
// int, packed size
// int, parts count
; 
32; 0; 0; 2; 2048; 640; 69; 8; 
33; 0; 0; 3; 4096; 223040; 81575; 8; 
48; 0; 0; 3; 96256; 23744; 5570; 4; 
50; 0; 0; 3; 104448; 8272; 3100; 4; 
51; 0; 0; 3; 112640; 820; 436; 4; 
; 
// fileparts:
// byte, section number
// byte, ??? (0, sometimes 6)
// word, output file index
// int, offset (relative to section)
// int, unpacked size
// int, packed size
; 
0; 0; 0; 0; 80; 0; 
1; 0; 0; 0; 26560; 5704; 
0; 0; 1; 80; 80; 0; 
1; 0; 1; 6144; 33856; 5420; 
0; 0; 2; 160; 80; 0; 
1; 0; 2; 12288; 159488; 69384; 
0; 0; 3; 240; 80; 0; 
1; 0; 3; 81920; 768; 295; 
0; 0; 4; 320; 80; 0; 
1; 0; 4; 83968; 768; 248; 
0; 0; 5; 400; 80; 0; 
1; 0; 5; 86016; 768; 246; 
0; 0; 6; 480; 80; 0; 
1; 0; 6; 88064; 768; 263; 
0; 0; 7; 560; 80; 0; 
1; 0; 7; 90112; 64; 15; 
2; 0; 8; 0; 5936; 1396; 
3; 0; 8; 0; 2068; 775; 
4; 0; 8; 0; 205; 109; 
2; 0; 9; 2048; 5936; 1396; 
3; 0; 9; 2048; 2068; 775; 
4; 0; 9; 2048; 205; 109; 
2; 0; 10; 4096; 5936; 1389; 
3; 0; 10; 4096; 2068; 775; 
4; 0; 10; 4096; 205; 109; 
2; 0; 11; 6144; 5936; 1389; 
3; 0; 11; 6144; 2068; 775; 
4; 0; 11; 6144; 205; 109; 
; 
// filemaps:
// byte, parts count
// byte, ??? (0)
// byte, type of file (32-texture, 48-shader...)
// byte, ??? (1)
// int, file index
// int, first part
; 
2; 0; 32; 1; 0; 0; 
2; 0; 32; 1; 1; 2; 
2; 0; 32; 1; 2; 4; 
2; 0; 32; 1; 3; 6; 
2; 0; 32; 1; 4; 8; 
2; 0; 32; 1; 5; 10; 
2; 0; 32; 1; 6; 12; 
2; 0; 32; 1; 7; 14; 
3; 0; 48; 1; 8; 16; 
3; 0; 48; 1; 9; 19; 
3; 0; 48; 1; 10; 22; 
3; 0; 48; 1; 11; 25; 
; 
// filename pointers:
// int, ptr 
; 
0; 17; 40; 65; 87; 110; 130; 149; 161; 176; 192; 211; 
; 
// filenames:
// string, 0x00 terminator
; 
0; char_menu_splash; 
1; locked_character_stamp; 
2; menu_characters_bio_bckg; 
3; play_menu_ico_chapter; 
4; play_menu_ico_progress; 
5; play_menu_ico_quest; 
6; play_menu_ico_time; 
7; transparent; 
8; DX9_NVidia_LOW; 
9; DX9_NVidia_HIGH; 
10; DX9_AMD_Fetch4_LOW; 
11; DX9_AMD_Fetch4_HIGH; 
; 
```
[/size]
[rp5l_structure_viewer.zip](https://xentaxbackup.github.io/file/4716_rp5l_structure_viewer.zip)
## Post #7
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-15T19:39:50+00:00
- Post Title: Dead Island .rpack files

a tool that can edit dds files  is enough no need to edit other files.
## Post #8
- Username: fabrock
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 16, 2011 8:33 am
- Post datetime: 2011-09-16T01:00:18+00:00
- Post Title: Dead Island .rpack files

hhrhhr if you manage to finish your rp5l unpacker/repacker you will be the hero of the Dead Island modding community.

Check out what we have managed to already accomplish with only having access to the contents of the .pak files.

[http://forums.steampowered.com/forums/s ... ?t=2106453](http://forums.steampowered.com/forums/showthread.php?t=2106453)

Now just imagine what we can do if given access to the other juicy assets located in the .rpack files. 

If you need any help (like identifying all the filetypes by their headers or contents) just let me know or ask in the Steam thread I linked.
## Post #9
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-16T12:42:41+00:00
- Post Title: Dead Island .rpack files

Yeah you are awesome. It will be a great help if you can get your tool to be able to extract those .rpack files. But it is already nice to be able to see what is inside those files.
Will it also be able to inject edited extracted files into the original .rpack files (like packzip). Or even better directly repack those files to a .rpack?

Also sth a bit less important. There are two other filetypes we can't access: .xwb files and .spb files. The .xwb files as one can already guess contain the sound files in .wav format. And i believe the .spb are files that have to do with the gamequests.

We are already able to unpack .wav files from the .xwb with a tool called unxwb. But the extracted .wav files are named by the programm since it can't read the file names. The edited files can be built into a new .xwb file with XACT but you need to convert those extracted .wav files into 16bit PCM .wav first or it won't let you add it into the .xwb. The built .xwb files don't work in game even if you renamed the .wav to the way they are referred to in other game files.
What would be nice is a program that can reinject the edited .wav files to the place it has been extracted from the file (like you can do it with packzip).
here are the two other file types.
[http://www.file-upload.net/download-373 ... ta.7z.html](http://www.file-upload.net/download-3738285/Data.7z.html)

I just wanted to mention this and not distract you from your work on the .rpack files, which are more important to us. But it would be really nice if you could look into this aswell when your work with your tool is done.
And thanks again for doing this. Have I already mentioned that you are awesome?
## Post #10
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-09-17T15:08:00+00:00
- Post Title: Dead Island .rpack files

You guys are amazing 
Is there any possibility to view models? There are no maps for interior rooms so maybe there is a way to view them models. Dev build with no clip is useful, as I saw on youtube, that after we go up everything disappear..
## Post #11
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-09-18T06:49:59+00:00
- Post Title: Dead Island .rpack files

github.com/hhrhhr/rp5l (for Qt 4.7.4) - can unpack all supported rpacks, then convert texture to dds (use only 1-st mip level).

usage:
run the program, if it finds an entry in the registry of the game, it will be used this path. otherwise specify the location of the directory with the packs. then select the directory to unpack.

select the archive, click "scan", then "unpack". there are no indicators of progress, just wait until the selected directory does not see all files. also there are no errors check.

then click the "textures" tab, then select one texture, "scan" and "unpack". or just "unpack all textures".

"unpack all" for rpacks work very very slow.

honestly, do the reverse packer is just lazy ;) maybe it will make someone else?
## Post #12
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-18T14:06:08+00:00
- Post Title: Dead Island .rpack files

Awesome. Works perfectly. 
Now we can at least see the Textures without having to use TexMod, and we get the correct filenames aswell. 
Do you know if the content of the .rpack has a file structure? like Data/Textures or Data/Anim or sth like that?
If yes, than that could perhaps make it possible to use the Modded files without having to put them back into a .rpack.

Thank you so much for your hard work
## Post #13
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-18T14:18:37+00:00
- Post Title: Dead Island .rpack files

just a tool to inject font files (DXT5) will be very good. And how to compile this source?
## Post #14
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-18T16:18:31+00:00
- Post Title: Dead Island .rpack files

> Reply from rengareng
>
> just a tool to inject font files (DXT5) will be very good. And how to compile this source?
Use QT 4.7.4 (like he wrote in his post).
You can run it in there. Was able to compile it, but not run it, even if i put all the needed .dll files in the same folder.

But like I said it runs fine in QT Creator.
## Post #15
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-18T17:12:56+00:00
- Post Title: Dead Island .rpack files

It is very big 1GB, is it possible to compile it with a GNU c++ compiler?
## Post #16
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-09-18T17:29:31+00:00
- Post Title: Re: Dead Island .rpack files

Works great but there is something wrong with act4a_PC.rpack 
Can't unpack and also filenames are messed up..
## Post #17
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-18T17:52:07+00:00
- Post Title: Re: Dead Island .rpack files

yeah i know

i tried it but didn't work for me...so i just downloaded QT
## Post #18
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-18T18:01:24+00:00
- Post Title: Re: Dead Island .rpack files

can you post executable version of program?
## Post #19
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-18T18:04:32+00:00
- Post Title: Re: Dead Island .rpack files

i told you..i wasnt able to get the compiled version to work
## Post #20
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-18T21:19:53+00:00
- Post Title: Re: Dead Island .rpack files

I have asked to author of the source not you  , I know you also could not compile.
## Post #21
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-09-18T23:17:52+00:00
- Post Title: Re: Dead Island .rpack files

The contents of this post was deleted because of possible forum rules violation.
## Post #22
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-19T09:04:06+00:00
- Post Title: Re: Dead Island .rpack files

Would you kindly add support for just change dds files? It should not be hard. Or can you provide a zlib compressor tool, that compress any file just like in rpack files.

I saw pack TAB in the program. Now, I hope you will add at least editing tex files.
## Post #23
- Username: fabrock
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 16, 2011 8:33 am
- Post datetime: 2011-09-22T04:29:37+00:00
- Post Title: Re: Dead Island .rpack files

hhrhhr (or someone else) if you could get the repack function done we would be eternally grateful.  The unpacked rpack contents are relatively useless on their own and unlike the contents of the .pak files, extracted and modified .rpack content does not get recognized by the game.  Without a repack function we cannot actually mod the game using modified textures, meshes and the like.
## Post #24
- Username: Suigintou
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 13, 2011 11:16 pm
- Post datetime: 2011-09-22T07:41:12+00:00
- Post Title: Re: Dead Island .rpack files

how can i open .msh (meshes) files?
## Post #25
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-22T08:53:22+00:00
- Post Title: Re: Dead Island .rpack files

> Reply from Suigintou
>
> how can i open .msh (meshes) files?
Had  no success doing that either....my best bet was this blender script that was made here since call of juarez has the same engine but an older version of it.
But this blender script doesn't even start for me....it probably has to be rewritten...but you could try if it works for you.

[viewtopic.php?f=10&t=3956](http://forum.xentax.com/viewtopic.php?f=10&t=3956)

we either need the  chrome editor...(which only people that have Call of Juarez Bound in Blood can use and it isn 't even sure if you can open those files in it)....or we need a tool that converts these .msh files into another mesh format that blender/maya/3dsmax/.... can use
## Post #26
- Username: Suigintou
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 13, 2011 11:16 pm
- Post datetime: 2011-09-22T09:31:43+00:00
- Post Title: Re: Dead Island .rpack files

it's not working for me too
## Post #27
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-24T13:01:15+00:00
- Post Title: Re: Dead Island .rpack files

I have injected new tex files into menu2_common_pc.rpack 
with that method with minor differences I mentioned in my post in the topic. 
[viewtopic.php?f=21&t=7409](http://forum.xentax.com/viewtopic.php?f=21&t=7409)
## Post #28
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-26T14:05:18+00:00
- Post Title: Re: Dead Island .rpack files

[http://svn.gib.me/public/chrome/trunk/](http://svn.gib.me/public/chrome/trunk/)
> Reply from Revision 5
>
> chrome: rick * r5 /trunk/ (31 files in 8 dirs): 
chrome: - ResourcePackageFile implementation for *.rpack (only supports version 36, Dead Island's)
chrome: - Add Unpack project, *extremely* basic unpacking *.rpack support.Only textures are processed currently, everything else is dumped out raw. There is no packer currently, asking me to create one won't speed things along.

There may be some color issues with some texture formats (L8, L16, R5G6B5, R16F) where I did not directly check if things looked okay.

Binaries can be found here: [http://svn.gib.me/builds/chrome/](http://svn.gib.me/builds/chrome/) (grab the latest revision)
## Post #29
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-26T14:17:50+00:00
- Post Title: Re: Dead Island .rpack files

Oh, there is one issue currently: ResourceUnpack doesn't support LZMA compressed rpacks yet, I'll have that done later today probably.
## Post #30
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-26T14:30:36+00:00
- Post Title: Re: Dead Island .rpack files

While unpacking menu2_ingame_single_PC.rpack, I am getting error when it comes to file "fl pismo reczne 10_16.dds". Probably this rpack doesnt have this file.
## Post #31
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-26T14:39:52+00:00
- Post Title: Re: Dead Island .rpack files

> Reply from rengareng
>
> While unpacking menu2_ingame_single_PC.rpack, I am getting error when it comes to file "fl pismo reczne 10_16.dds". Probably this rpack doesnt have this file.I need an exception traceback or something similar. That file unpacked fine for me.
## Post #32
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-26T17:32:26+00:00
- Post Title: Re: Dead Island .rpack files

Ok, I found my mistake. My file was broken. I copied that file again from installation; now extraction is fine.
## Post #33
- Username: JanoRis
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 16, 2011 7:33 pm
- Post datetime: 2011-09-26T18:43:10+00:00
- Post Title: Re: Dead Island .rpack files

Awesome to see that somebody is working on a tool again.
You also did the unpacker and repacker for  Just Cause 2, didn't you? The Avalanche one^^
I have to admit that every time I wanted to mod a game and couldn't access a compressed file, i tried dragging it on the avalanche unpacker. That was before I discovered this forum   

Keep up the good work.
## Post #34
- Username: fabrock
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 16, 2011 8:33 am
- Post datetime: 2011-10-01T01:44:45+00:00
- Post Title: Re: Dead Island .rpack files

> Reply from Rick
>
> Only textures are processed currently, everything else is dumped out raw. There is no packer currently, asking me to create one won't speed things along.

Hi Rick, I just wanted to thank you for taking on the project.  I am really looking forward to being able to get at the meat of the Dead Island assets so I can mod the hell out of it.  Take your time and thanks again.
## Post #35
- Username: Omnion
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 13, 2013 5:33 pm
- Post datetime: 2013-09-06T10:29:04+00:00
- Post Title: Re: Dead Island .rpack files

1. several questons how does one extract a rpack file
2. what appened to the r5pl. exe
3. and where is the dl for the resourceunpack tool
