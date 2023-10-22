## Post #1
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-08-28T12:01:21+00:00
- Post Title: Astral Chain package

I've got the container pretty much all figured out, but I have 0 clue on how to make a script, so I've [uploaded some samples](https://mega.nz/#F!w1lmAALC!8qwCER-YfsLezZg8rC6BPA) from the game for anyone to make a BMS script for

> 0x00 - magic [pkzl]
>
> 0x04 - unk
>
> 0x08 - package size
>
> 0x10 - files in package
>
> 0x14 - table offset location
>
> 0x18 - length of filename table
>
> 
>
> table:
>
> -Filename Location (at ZStandard)
>
> -Decompressed Size [this can be skipped]
>
> -Offset location of said compressed file
>
> -Compressed file length

No need to extract files to their decompressed files since it's all zstandard/zstd compression, I can just decompress them via smash ultimate tools, which is what I did for the model, when I was extracting files 1 at a time without proper filenames.
## Post #2
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-08-30T14:19:17+00:00
- Post Title: Astral Chain package

> Reply from demonslayerx8 ↑Wed Aug 28, 2019 8:01 pm at Wed Aug 28, 2019 8:01 pm
>
> 
No need to extract files to their decompressed files since it's all zstandard/zstd compression, I can just decompress them via smash ultimate tools, which is what I did for the model, when I was extracting files 1 at a time without proper filenames.
So which tools did you used?
## Post #3
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-08-30T14:58:13+00:00
- Post Title: Astral Chain package

> Reply from andree ↑Fri Aug 30, 2019 10:19 pm at Fri Aug 30, 2019 10:19 pm
>
> 
demonslayerx8 wrote: ↑Wed Aug 28, 2019 8:01 pm
No need to extract files to their decompressed files since it's all zstandard/zstd compression, I can just decompress them via smash ultimate tools, which is what I did for the model, when I was extracting files 1 at a time without proper filenames.

So which tools did you used?
Extracted the compressed files via hex 1 at a time, then I used zstd (via cmd prompt) to decompress the files.

Atm just waiting for a proper script to be made that'll extract all the files with their proper names in their compressed forms.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-30T16:11:05+00:00
- Post Title: Astral Chain package

This QuickBMS script should extract and decompress the files.


# Astral Chain . pkz extract
# By Dave, 2019

IDString "pkzl"

ComType ZSTD

Goto 0x10
Get ITEMS Long
Get FILE_ENTRY Long

XMath NAME_TABLE "FILE_ENTRY + (ITEMS * 0x20)"

For A = 1 to ITEMS

	Goto FILE_ENTRY
	Get NAME_OFFSET Long
	Get JUNK Long
	Get SIZE Long
	Get JUNK Long
	Get OFFSET Long
	Get JUNK Long
	Get ZSIZE Long
	Math NAME_OFFSET + NAME_TABLE
	Goto NAME_OFFSET
	GetDSTring FILENAME 0x10

	Clog FILENAME OFFSET ZSIZE SIZE
#	Log FILENAME OFFSET ZSIZE				# Use this line to get compressed output instead

	Math FILE_ENTRY + 0x20

Next A
## Post #5
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-08-30T22:31:59+00:00
- Post Title: Astral Chain package

ooohh thanks!! Works on all the files so far!
## Post #6
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-08-31T07:49:35+00:00
- Post Title: Astral Chain package

The model/animation format is identical to Nier's. Texture format is unknown to me.
I added support for Astral Chain to my noesis plugin. If someone can help me with the texture format (FOURCC is "XT1\x00") I should be able to add it to the plugin.
[https://github.com/Kerilk/noesis_bayonetta_pc/](https://github.com/Kerilk/noesis_bayonetta_pc/)
Note that you need to unpack the pkz files by yourself.



Astral Chain.png (118.83 KiB) Viewed 694 times
## Post #7
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-08-31T09:08:27+00:00
- Post Title: Astral Chain package

> Reply from Kerilk ↑Sat Aug 31, 2019 3:49 pm at Sat Aug 31, 2019 3:49 pm
>
> 
The model/animation format is identical to Nier's. Texture format is unknown to me.
I added support for Astral Chain to my noesis plugin. If someone can help me with the texture format (FOURCC is "XT1\x00") I should be able to add it to the plugin.
https://github.com/Kerilk/noesis_bayonetta_pc/
Note that you need to unpack the pkz files by yourself.

the texture format is ASTC_10x10_UNORM and uses switch's swizzle algorithm. Still working on it.


> WTA :
>
> magic
>
> unk [possibly file version?]
>
> file total
>
> table1 offset
>
> table2 offset
>
> table3 offset
>
> table4 offset
>
> table5 offset
>
> 
>
> table1 - texture offset locations in wtp
>
> table2 - texture filesize in wtp
>
> table3 - unk
>
> table4 - unk
>
> table5 - texture header info
>
> 
>
> Texture header
>
> magic
>
> unk
>
> texture filesize
>
> unk
>
> unk
>
> mipmap count
>
> unk
>
> unk
>
> width
>
> height
>
> depth
>
> unk
>
> unk
>
> unk

Edit:
Also, is there a reason why there's no facial bones for the 2 main chars? Or do they use vertex morph sets?
## Post #8
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2019-08-31T10:57:21+00:00
- Post Title: Astral Chain package

> Reply from demonslayerx8
>
> 
Edit:
Also, is there a reason why there's no facial bones for the 2 main chars? Or do they use vertex morph sets?

In other platinum games there are seperate head models elsewhere (sometimes even other package) that have full rig. Probably the same here.
## Post #9
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-08-31T16:20:18+00:00
- Post Title: Astral Chain package

WTA
Table 3 are flags for the game
Table 4 are hashes to reference textures in materials
## Post #10
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-08-31T17:44:15+00:00
- Post Title: Astral Chain package

> Reply from HeliosAI ↑Sat Aug 31, 2019 6:57 pm at Sat Aug 31, 2019 6:57 pm
>
> 
demonslayerx8 wrote:
Edit:
Also, is there a reason why there's no facial bones for the 2 main chars? Or do they use vertex morph sets?


In other platinum games there are seperate head models elsewhere (sometimes even other package) that have full rig. Probably the same here.

ah gotcha

> Reply from Kerilk ↑Sun Sep 01, 2019 12:20 am at Sun Sep 01, 2019 12:20 am
>
> 
WTA
Table 3 are flags for the game
Table 4 are hashes to reference textures in materials
ohh, didn't know that, thanks for the tip.

Edit:
Well so far I have no luck with getting these textures properly, it's close but I don't know much about swizzling.
## Post #11
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-08-31T18:10:56+00:00
- Post Title: Astral Chain package

There are volume textures in sta/ra_00.dtt, maybe they can give you some insight about the unknown texture info fields. I am trying to match them to [https://github.com/aboood40091/BNTX-Inj ... globals.py](https://github.com/aboood40091/BNTX-Injector/blob/master/globals.py) but for now I am rather unsuccessful. I was hoping it was some kind of BNTX that had been stripped.
The texture archive is in wtb format (meaning the texture data is inside the file rather than in an accompanying wtp).
## Post #12
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-08-31T19:13:05+00:00
- Post Title: Astral Chain package

> Reply from Kerilk ↑Sun Sep 01, 2019 2:10 am at Sun Sep 01, 2019 2:10 am
>
> 
There are volume textures in sta/ra_00.dtt, maybe they can give you some insight about the unknown texture info fields. I am trying to match them to https://github.com/aboood40091/BNTX-Inj ... globals.py but for now I am rather unsuccessful. I was hoping it was some kind of BNTX that had been stripped.
The texture archive is in wtb format (meaning the texture data is inside the file rather than in an accompanying wtp).
I took a look, and they're about the same as the regular texture

the flags however, makes a bit more sense to me now
20000060 - normal/pbr/special maps
20000064 - diffuse/cube

Did notice that the cubemap and FogLUT has unk4 set as 8 tho... as far as I know, cubemaps have 6 layers, not 8...   


edit:
if u wanna see/take a look at the coding for these textures in [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/blob/ca1b62e45efe5ea6ca15d3a34726e09d91522c2d/File_Format_Library/FileFormats/Texture/WTB.cs)
## Post #13
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-08-31T19:56:00+00:00
- Post Title: Astral Chain package

unk4 could be:
typedef enum {
    T_1D,
    T_2D,
    T_3D,
    T_Cube,
    T_1D_Array,
    T_2D_Array,
    T_2D_Mulitsample,
    T_2D_Multisample_Array,
    T_Cube_Array
} texture_type_t;

so 8 would be T_Cube_Array
But that could be completely wrong.
Also the textures from CubeMap have 7 mip map, while those from FogLUT have 1, but sizes don't seem to coincide:



Astral Chain textures.png (113.96 KiB) Viewed 642 times



Edit: if you are looking for PlatinumGames related binary templates you may find something interesting here:
[https://github.com/Kerilk/bayonetta_too ... _templates](https://github.com/Kerilk/bayonetta_tools/tree/master/binary_templates)
## Post #14
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-09-01T05:40:07+00:00
- Post Title: Astral Chain package

Well so far, no luck on getting these textures properly.. I've tried contacting RTB, but no response yet.

Edit:
Could the 2nd unknown after depth be bytes per pixel?
## Post #15
- Username: gren
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 19, 2019 7:41 am
- Post datetime: 2019-09-10T22:22:56+00:00
- Post Title: Astral Chain package

I was working through the file format on my own and worked out all of pkz and most of DAT file structure but I couldn't figure out what the 5th table was for in DAT files and it seems maybe unneeded? The first 4 were for offsets, file type, file name, and size, but I couldn't for the life of me figure out what the 5th was. Any one got any ideas?

Also I have 010 templates for pkz dat, and wip templates for the texture ones as well but don't have too much on textures yet. Will post when I get home later
## Post #16
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-09-10T22:43:44+00:00
- Post Title: Re: Astral Chain package

> Reply from gren ↑Wed Sep 11, 2019 6:22 am at Wed Sep 11, 2019 6:22 am
>
> 
I was working through the file format on my own and worked out all of pkz and most of DAT file structure but I couldn't figure out what the 5th table was for in DAT files and it seems maybe unneeded? The first 4 were for offsets, file type, file name, and size, but I couldn't for the life of me figure out what the 5th was. Any one got any ideas?

Also I have 010 templates for pkz dat, and wip templates for the texture ones as well but don't have too much on textures yet. Will post when I get home later
read above
table1 - texture offset locations in wtp
table2 - texture filesize in wtp
table3 - flags for the game
table4 - hashes to reference textures in materials
table5 - texture header info
## Post #17
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-09-11T01:04:48+00:00
- Post Title: Re: Astral Chain package

> Reply from gren ↑Wed Sep 11, 2019 6:22 am at Wed Sep 11, 2019 6:22 am
>
> 
I was working through the file format on my own and worked out all of pkz and most of DAT file structure but I couldn't figure out what the 5th table was for in DAT files and it seems maybe unneeded? The first 4 were for offsets, file type, file name, and size, but I couldn't for the life of me figure out what the 5th was. Any one got any ideas?

Also I have 010 templates for pkz dat, and wip templates for the texture ones as well but don't have too much on textures yet. Will post when I get home later

Nice catch! I hadn't seen it. It exists in Nier also, and I hadn't noticed. I can tell you that ignoring it in Nier is not showing much impact. This looks like some metadata. Some of it are hash for files, and the rest looks like priority class for data streaming? I'll commit an update binary template in once I am done with it.

Edit: Okay I understand what it is, it is a hash map of hashes, so hashes can be retrieved faster.

Edit 2: Here is a corrected binary template: [https://github.com/Kerilk/bayonetta_too ... %20base.bt](https://github.com/Kerilk/bayonetta_tools/blob/master/binary_templates/Bayonetta%20dat%20base.bt)
## Post #18
- Username: gren
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 19, 2019 7:41 am
- Post datetime: 2019-09-11T03:46:12+00:00
- Post Title: Re: Astral Chain package

> Reply from demonslayerx8 ↑Wed Sep 11, 2019 6:43 am at Wed Sep 11, 2019 6:43 am
>
> 
gren wrote: ↑Wed Sep 11, 2019 6:22 am
I was working through the file format on my own and worked out all of pkz and most of DAT file structure but I couldn't figure out what the 5th table was for in DAT files and it seems maybe unneeded? The first 4 were for offsets, file type, file name, and size, but I couldn't for the life of me figure out what the 5th was. Any one got any ideas?

Also I have 010 templates for pkz dat, and wip templates for the texture ones as well but don't have too much on textures yet. Will post when I get home later

read above
table1 - texture offset locations in wtp
table2 - texture filesize in wtp
table3 - flags for the game
table4 - hashes to reference textures in materials
table5 - texture header info
No. I am talking about the DAT files. These are containers for more files - much like the pkz but the DAT files are contained within pkz files. 

> Reply from Kerilk ↑Wed Sep 11, 2019 9:04 am at Wed Sep 11, 2019 9:04 am
>
> 
gren wrote: ↑Wed Sep 11, 2019 6:22 am
I was working through the file format on my own and worked out all of pkz and most of DAT file structure but I couldn't figure out what the 5th table was for in DAT files and it seems maybe unneeded? The first 4 were for offsets, file type, file name, and size, but I couldn't for the life of me figure out what the 5th was. Any one got any ideas?

Also I have 010 templates for pkz dat, and wip templates for the texture ones as well but don't have too much on textures yet. Will post when I get home later


Nice catch! I hadn't seen it. It exists in Nier also, and I hadn't noticed. I can tell you that ignoring it in Nier is not showing much impact. This looks like some metadata. Some of it are hash for files, and the rest looks like priority class for data streaming? I'll commit an update binary template in once I am done with it.

Edit: Okay I understand what it is, it is a hash map of hashes, so hashes can be retrieved faster.

Edit 2: Here is a corrected binary template: https://github.com/Kerilk/bayonetta_too ... %20base.bt
Awesome! Hashes make a lot of sense for that. Makes sense they reused stuff from bayonetta/nier I guess. Will probably be a good resource to look at for other stuff.
## Post #19
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-09-11T04:40:45+00:00
- Post Title: Re: Astral Chain package

Well there are other binary templates for Astral chain wmb files in the same directory. You can also decode bxm files (which are binary xml files) using the Bayonetta 2 bxm.bt (mind the byte ordering though). Motion formats are also known.
## Post #20
- Username: gren
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 19, 2019 7:41 am
- Post datetime: 2019-09-11T18:45:46+00:00
- Post Title: Re: Astral Chain package

In the wta binary template, is textureInfo.format supposed to be of the texture_format_t type? I ran a script to parse every WTA in the romfs and there a handful of format codes that aren't listed in the comment for that entry (0x38, 0x25, 0x29, 0x01) which can be found in files like ui/core.wta, core/pre_texture.wta, and a few other loose files
## Post #21
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-09-11T19:06:45+00:00
- Post Title: Re: Astral Chain package

No this is still wip and the enum is not used.
See discussion there:
[https://github.com/Kerilk/noesis_bayonetta_pc/issues/11](https://github.com/Kerilk/noesis_bayonetta_pc/issues/11)
## Post #22
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-09-20T05:53:03+00:00
- Post Title: Re: Astral Chain package

The plugin has been updated with texture support.
Thanks for all the help!



Astral Chain with textures.png (148.51 KiB) Viewed 327 times
## Post #23
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-22T21:47:22+00:00
- Post Title: Re: Astral Chain package

> Reply from Kerilk ↑Fri Sep 20, 2019 1:53 pm at Fri Sep 20, 2019 1:53 pm
>
> 
The plugin has been updated with texture support.
Although I'm using latest version of Noesis and made sure to delete original bayonetta.dll from plugins directory and added the new bayonetta_pc.dll, and having the DAT/DTT pairs still wont work, what else am I missing?   



Capture.jpg (72.82 KiB) Viewed 300 times


EDIT:
looks like it was in conflict with another plug-in/script so deleting the entire python folder solved the import
the other issue with it was a continuous loop mode for animations, no matter how many times I'd hit cancel animation wont load, or to type the animation, then hit ok, will open up another window to select the model, once you select the model it loops back to select animation, or if you click cancel nothing happens, continuous loop, very annoying, and still no animations imported, oh well, time to move on, thank you though
## Post #24
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-09-23T00:05:43+00:00
- Post Title: Re: Astral Chain package

To load animations you have to select the file containing the animations. In platinum games, the animation for the main character are usually in different files, that is why you are offered the opportunity to load several (until you click cancel). The main animations for pl0000 are in pl000f.dat.
So if you want to load the animations for the male character, after loading pl0000.dat, you need to select pl000f.dat to load the animations.

If you want to load the animation for the girl (pl0001 for instance), and select pl000f.dat, nothing will happen because the name prefix of the animation are those of the male character (pl0000). In this case, before clicking Ok, you need to write pl0000 inside the field so that pl0000 anims will be loaded.
## Post #25
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2019-09-30T16:48:04+00:00
- Post Title: Re: Astral Chain package

> Reply from Kerilk ↑Fri Sep 20, 2019 1:53 pm at Fri Sep 20, 2019 1:53 pm
>
> 
The plugin has been updated with texture support.
Thanks for all the help!

Astral Chain with textures.png

Is there anywhere I could download those 3d model files to open in 3dsMax?
## Post #26
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2019-09-30T17:44:02+00:00
- Post Title: Re: Astral Chain package

I ran the script DKDave made for QuickBMS and get some .dat files but I can´t open them with Noesis. Am I missing something?
[qqqqqaszz.png](https://xentaxbackup.github.io/file/16833_qqqqqaszz.png)
## Post #27
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-04T02:04:10+00:00
- Post Title: Re: Astral Chain package

> Reply from Enderfacio ↑Tue Oct 01, 2019 1:44 am at Tue Oct 01, 2019 1:44 am
>
> 
I ran the script DKDave made for QuickBMS and get some .dat files but I can´t open them with Noesis. Am I missing something?
Now if you would have paid attention above you have same error as mine, meaning there's a conflict between the scripts, its trying to load them with a wrong script, remove them one at a time and find which is the culprit, then you'll be good to go.
## Post #28
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2019-10-04T03:41:03+00:00
- Post Title: Re: Astral Chain package

> Reply from mono24 ↑Fri Oct 04, 2019 10:04 am at Fri Oct 04, 2019 10:04 am
>
> 
Enderfacio wrote: ↑Tue Oct 01, 2019 1:44 am
I ran the script DKDave made for QuickBMS and get some .dat files but I can´t open them with Noesis. Am I missing something?

Now if you would have paid attention above you have same error as mine, meaning there's a conflict between the scripts, its trying to load them with a wrong script, remove them one at a time and find which is the culprit, then you'll be good to go.

I notice that, but I didin´t understand wich folder is it. I deleted the entire Python folder as you said but Noesis starts with an error message. Wich folder is the one with the scripts I have to delete?
## Post #29
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2019-10-04T13:26:26+00:00
- Post Title: Re: Astral Chain package

SOLVED IT! Thanks for reply
## Post #30
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2019-10-19T03:49:05+00:00
- Post Title: Re: Astral Chain package

> Reply from Kerilk ↑Fri Sep 20, 2019 1:53 pm at Fri Sep 20, 2019 1:53 pm
>
> 
The plugin has been updated with texture support.
Thanks for all the help!

Astral Chain with textures.png
there is one thing i dont understand yet from taking the models appart. where are the facial textures being stored. i looked in the files and havent been able to locate it. is there a place where its stored and so how to get to it?
## Post #31
- Username: jjjung
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 01, 2019 9:05 pm
- Post datetime: 2019-10-31T06:05:16+00:00
- Post Title: Re: Astral Chain package

Hello I'm a noob here,
I've tried extracting the effect texture files, and i got a bunch of .wta and .wtp files.
I searched google, and I tried the bayonetta wtp quick bms script to convert them to .dds, but it couldn't read anything.
Is there a way to convert .wtp texture files to viewable image files?
Thank you.
## Post #32
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-10-31T07:18:06+00:00
- Post Title: Re: Astral Chain package

use Switch Toolbox, or the latest noesis script/plugin for Platinum games models.
## Post #33
- Username: jjjung
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 01, 2019 9:05 pm
- Post datetime: 2019-10-31T07:30:33+00:00
- Post Title: Re: Astral Chain package

> Reply from demonslayerx8 ↑Thu Oct 31, 2019 3:18 pm at Thu Oct 31, 2019 3:18 pm
>
> 
use Switch Toolbox, or the latest noesis script/plugin for Platinum games models.

On noesis, it was unable to open or export .dat files
So I downloaded switch toolbox now, but there is nothing happening when I opened .wtp or .wta files
Is there a plugin I should download for toolbox?
The .wtp files are from the Effect/Texture folder
[image.PNG](https://xentaxbackup.github.io/file/16976_image.PNG)
## Post #34
- Username: zzio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 22, 2019 1:51 am
- Post datetime: 2019-11-01T11:53:26+00:00
- Post Title: Re: Astral Chain package

sorry, for my bad english first.

I got stage mesh and textures from noesis tool ( I've had a crack issue on noesis, so I unpacked & repacked .dat file )

but I can't do mapping textures on mesh  

as you guys can see,  textures only have indexed name not proper material name.

the only thing I tried to fix it is wmb_find_textures.rb on bayonetta_tools but It's no hope ( I have no ideas how to deal with ruby script )

plz help me
[issue_on_astralchain-min.png](https://xentaxbackup.github.io/file/16983_issue_on_astralchain-min.png)
## Post #35
- Username: kakifloss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 16, 2017 5:41 am
- Post datetime: 2020-01-28T20:59:17+00:00
- Post Title: Re: Astral Chain package

Hello,

I'm having an issue when exporting the animations, noesis just crash. That is I think due to the large amount of data one .dat file can contain.

I was wondering if someone knew a tool that could allows me to unpack and repack the .dat file so I can remove some .mot files (animation) to make the final .dat file much smaller and allow noesis to export the animations without crashing.

Thanks for the help, (and sorry for my english)
## Post #36
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2020-01-28T22:14:04+00:00
- Post Title: Re: Astral Chain package

Look at the issue here:

[https://github.com/Kerilk/noesis_bayonetta_pc/issues/9](https://github.com/Kerilk/noesis_bayonetta_pc/issues/9)
## Post #37
- Username: kakifloss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 16, 2017 5:41 am
- Post datetime: 2020-01-28T22:33:35+00:00
- Post Title: Re: Astral Chain package

Thank you very much!
## Post #38
- Username: G1fan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 23, 2018 3:03 pm
- Post datetime: 2020-01-31T20:48:23+00:00
- Post Title: Re: Astral Chain package

Hey folks

I'm currently trying to hunt down the high poly hair textures by comparing their texture ids to the texture ids present in other objects materials but so far no luck.
Was wondering if anyone else had managed to find them already, and if so where.

Cheers
## Post #39
- Username: greenteasan1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 24, 2020 10:44 am
- Post datetime: 2020-04-24T02:03:15+00:00
- Post Title: Re: Astral Chain package

Does anyone know where the npcs are located?(i mean  which file it's located in) Sorry I'm a beginner at this
## Post #40
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2021-06-14T21:26:57+00:00
- Post Title: Re: Astral Chain package

Hate to ask, but has anyone located the hi-rez textures for the female main character/Akira? I can only find low resolution textures.

Also maybe it's just me, but most files work, but not pl0000 and a few others.
## Post #41
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2021-06-15T02:22:14+00:00
- Post Title: Re: Astral Chain package

> Reply from Andelx ↑Tue Jun 15, 2021 5:26 am at Tue Jun 15, 2021 5:26 am
>
> 
Hate to ask, but has anyone located the hi-rez textures for the female main character/Akira? I can only find low resolution textures.

Also maybe it's just me, but most files work, but not pl0000 and a few others.
High-res textures are stored in a 4k texture located in pl0000, which has both male and female on 1 texture sheet for their outfit.
## Post #42
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2021-06-16T20:20:05+00:00
- Post Title: Re: Astral Chain package

> Reply from demonslayerx8 ↑Tue Jun 15, 2021 10:22 am at Tue Jun 15, 2021 10:22 am
>
> 
Andelx wrote: ↑Tue Jun 15, 2021 5:26 am
Hate to ask, but has anyone located the hi-rez textures for the female main character/Akira? I can only find low resolution textures.

Also maybe it's just me, but most files work, but not pl0000 and a few others.

High-res textures are stored in a 4k texture located in pl0000, which has both male and female on 1 texture sheet for their outfit.

Appreciate it, what's the best way to get them? Since exporting via the usual tools gives subpar textures and only for the male character. Thank you.
## Post #43
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2021-06-20T20:39:24+00:00
- Post Title: Re: Astral Chain package

Hey there, I always hate to ask for this, but can anyone export the HD textures for the two main characters for me please? I tried for a while on my end but no luck. Any help would be appreciated, thank you.
## Post #44
- Username: Dakotaraptorsaurus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 11, 2022 1:26 am
- Post datetime: 2022-04-10T17:32:46+00:00
- Post Title: Re: Astral Chain package

I just extracted the game and I'm a little lost. Does Any know the location of the models for the protagonists? and is it possible to perhaps replace them with 3DS Max?
## Post #45
- Username: shaunanthonywheeldon
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 28, 2018 3:27 am
- Post datetime: 2022-08-12T21:38:15+00:00
- Post Title: Re: Astral Chain package

> Reply from DKDave ↑Sat Aug 31, 2019 12:11 am at Sat Aug 31, 2019 12:11 am
>
> 
This QuickBMS script should extract and decompress the files.

Hello, I am trying to extract the models and textures from Astral Chain, it may sound like madness, but I can't see the .pnz archives; are they in the .bins or am I missing something?
