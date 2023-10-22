## Post #1
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2012-04-08T10:14:52+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

Looking to extract models (characters, stages) from the following PS2 games:

Avatar: The Last Airbender
Avatar: The Last Airbender - The Burning Earth
Avatar: The Last Airbender - Into the Inferno

All three games are made by THQ, and have appears to be a main data file as "DATA.PAK" (although this just applies to the last two, the first has eight data.pak files).



The data.pak from "Into the Inferno": 
[http://www.mediafire.com/?c5aomif3e1t9dm7](http://www.mediafire.com/?c5aomif3e1t9dm7)
[http://www.mediafire.com/?vdkfe1kxdnma2cr](http://www.mediafire.com/?vdkfe1kxdnma2cr)
[http://www.mediafire.com/?wnxm8wlguktlgl2](http://www.mediafire.com/?wnxm8wlguktlgl2)
## Post #2
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2012-06-23T17:04:20+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

....nothing? Not even a little bit of help, or a nudge in the right direction?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-23T17:07:28+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

Just screenshot the beginning and end of the file or get the first and last MB. I'm not downloading 600 MB to see what it might look like.
## Post #4
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2012-06-24T06:59:55+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

> Reply from finale00
>
> Just screenshot the beginning and end of the file or get the first and last MB. I'm not downloading 600 MB to see what it might look like.

Screenshot as in open with hex-editor and take a screencap of what it displays at the top and bottom?
## Post #5
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-07-07T18:58:05+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

This post refers to Avatar: The Last Airbender (The first PS2 game).

In this game their are several PAK files that contain files for each chapter, aka
their is a file named C5_DATA.PAK

Some of the data in these PAK files are compressed while other data is not compressed. You can decompress the compressed data by using the tool, called "offzip" aluigi.altervista.org/mytoolz.htm

That tool will not give you the file names, however the files names are uncompressed in the beginning and end, of the PAKs.

Format of the PAKs
All Offsets are relative to the start of the PAK (aka right when the header "kcap" begins)

4ByteASCIIHeader: kcap
4ByteUnknownOrConstant: 01 00 01 00
4ByteOffsetToEndOfASCIINameTable
4ByteIntegerSizeofPAKfile
4ByteOffsetToStartOfASCIINameTable
4ByteIntegerNumberofSubFiles
Now Begins the FileLength/SizeTable (if your following we at now at offset 0x18)
Format of the FIleLength/SizeTable
{4ByteUnknownID, 4ByteOffsetOfSubFile, 4ByteSizeOfSubFile, 4ByteUnknown}
FormatOfTheASCIINameTable
{ASCII file Path terminated with the hex byte 00}

PAKS can be nested. Nested paks. Take the same format as the regular PAKs, except, that the subfiles are zlib compressed. In first level PAKs, there are RAD files, which I think never contain models, only data describing how to use the data from second level PAKs.

Can someone make a script to extract PAKs into subfiles? The information above should be enough.

Most if not all models contain the ASCII header enod
Followed by the most of the model data in array format. The funny thing is that while
the models are in tristrips there is zero padding between some vertexes that must be removed. For example say in one model between there is zero padding between the 12th 34th 132nd and 421st vertexes. The padding is of different sizes, and is in every component. Let me see if I can get file names, of the compressed files, and decompress them so they will be much easier too work with.
## Post #6
- Username: triad
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 20, 2012 8:42 pm
- Post datetime: 2012-07-20T12:52:58+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

If you want to extract the audio, use PSound (just google it)
I'm still looking for a utility to extract the files..........

I've used OFFZIP and extracted allot of .gml;.plo;.... files (what is correct;)
.RCB files aren't recognized, searching for a util for that....

use OFFZIP -a DATA.PAK C:\EXISTINGFOLDER 0
to start extracting zlib compression files from the pak file

You'll hear from me soon 
LB
## Post #7
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-07-20T18:07:50+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

The rsc files contain models in at least the original game. And the format of the files is very similar in the original game, as compared to Into the Inferno except in Into the Inferno there is some padding between the headers of each pack or subpack.
## Post #8
- Username: triad
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 20, 2012 8:42 pm
- Post datetime: 2012-07-30T12:15:47+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

I'm busy writing a program; quite some hard work as i am not a pro in those things 
At least ive managed to get the list of all the files in the DATA.PAK file: (Program coming soon) : 

In the beginning of a compressed PAK file, you will see this : Hbilz => turn it around and you will see zlibh 
Heres the list : 
i think that .rcb files contain effects and their resources

[ the list isn't complete as i can't upload .txt files here and i'm only allowed 60000 characters!!!!]
00_worldmap.pak
00_worldmap_en_normal.pak
00_worldmap_en_normal.rad
00_worldmap_musicmanagercs.rad
01_fnship.pak
01_fnship_en_normal.pak
01_fnship_en_normal.rad
01_fnship_musicmanagercs.rad
02_factory.pak
02_factory_en_normal.pak
02_factory_en_normal.rad

08_temple_musicmanagercs.rad
09_combustion.pak
09_combustion_en_normal.pak
09_combustion_en_normal.rad
09_combustion_musicmanagercs.rad
10_airship.pak
10_airship_en_normal.pak
10_airship_en_normal.rad
10_airship_musicmanagercs.rad
11_finale.pak
11_finale_en_normal.pak
11_finale_en_normal.rad
11_finale_musicmanagercs.rad
20_flying.pak
20_flying_en_normal.pak
20_flying_en_normal.rad
20_flying_musicmanagercs.rad
boot.pak
boot_en_normal.pak
boot_en_normal.rad
common_en_normal.rad
mainmenu.pak
mainmenu_en_normal.pak
mainmenu_en_normal.rad
00_worldmap.pak
00_worldmap_en_normal.pak
00_worldmap_en_normal.rad
00_worldmap_musicmanagercs.rad

03_pier_musicmanagercs.rad
04_invasion.pak
04_invasion_en_normal.pak
04_invasion_en_normal.rad
04_invasion_musicmanagercs.rad
05_palace.pak
05_palace_en_normal.pak
05_palace_en_normal.rad
05_palace_musicmanagercs.rad
06_prison.pak
06_prison_en_normal.pak
06_prison_en_normal.rad
06_prison_musicmanagercs.rad
07_gondola.pak
07_gondola_en_normal.pak
07_gondola_en_normal.rad
07_gondola_musicmanagercs.rad
08_temple.pak
08_temple_en_normal.pak
08_temple_en_normal.rad
08_temple_musicmanagercs.rad
09_combustion.pak
09_combustion_en_normal.pak
09_combustion_en_normal.rad
09_combustion_musicmanagercs.rad
10_airship.pak
10_airship_en_normal.pak
10_airship_en_normal.rad
10_airship_musicmanagercs.rad
11_finale.pak
11_finale_en_normal.pak
11_finale_en_normal.rad
11_finale_musicmanagercs.rad
20_flying.pak
20_flying_en_normal.pak
20_flying_en_normal.rad
20_flying_musicmanagercs.rad
boot.pak
boot_en_normal.pak
boot_en_normal.rad
common_en_normal.rad
mainmenu.pak
mainmenu_en_normal.pak
mainmenu_en_normal.rad
00_worldmap.pak
00_worldmap_en_normal.pak
00_worldmap_en_normal.rad
00_worldmap_musicmanagercs.rad
01_fnship.pak
01_fnship_en_normal.pak
01_fnship_en_normal.rad
01_fnship_musicmanagercs.rad
02_factory.pak
02_factory_en_normal.pak
02_factory_en_normal.rad
02_factory_musicmanagercs.rad
03_pier.pak
03_pier_en_normal.pak
03_pier_en_normal.rad
03_pier_musicmanagercs.rad
04_invasion.pak
04_invasion_en_normal.pak
04_invasion_en_normal.rad
04_invasion_musicmanagercs.rad
05_palace.pak
05_palace_en_normal.pak
05_palace_en_normal.rad
05_palace_musicmanagercs.rad
06_prison.pak
06_prison_en_normal.pak
06_prison_en_normal.rad
06_prison_musicmanagercs.rad
07_gondola.pak
07_gondola_en_normal.pak
07_gondola_en_normal.rad
07_gondola_musicmanagercs.rad
08_temple.pak
08_temple_en_normal.pak
08_temple_en_normal.rad
08_temple_musicmanagercs.rad
09_combustion.pak
09_combustion_en_normal.pak
09_combustion_en_normal.rad
09_combustion_musicmanagercs.rad
10_airship.pak
10_airship_en_normal.pak
10_airship_en_normal.rad
10_airship_musicmanagercs.rad
11_finale.pak
11_finale_en_normal.pak
11_finale_en_normal.rad
11_finale_musicmanagercs.rad
20_flying.pak
20_flying_en_normal.pak
20_flying_en_normal.rad
20_flying_musicmanagercs.rad
boot.pak
boot_en_normal.pak
boot_en_normal.rad
common_en_normal.rad
mainmenu.pak
mainmenu_en_normal.pak
mainmenu_en_normal.rad
00_worldmap.pak
00_worldmap_en_normal.pak
00_worldmap_en_normal.rad
00_worldmap_musicmanagercs.rad
01_fnship.pak
01_fnship_en_normal.pak
01_fnship_en_normal.rad
01_fnship_musicmanagercs.rad
02_factory.pak
02_factory_en_normal.pak
02_factory_en_normal.rad
02_factory_musicmanagercs.rad
03_pier.pak
03_pier_en_normal.pak
03_pier_en_normal.rad
03_pier_musicmanagercs.rad
04_invasion.pak
04_invasion_en_normal.pak
04_invasion_en_normal.rad
04_invasion_musicmanagercs.rad
05_palace.pak
05_palace_en_normal.pak
05_palace_en_normal.rad
05_palace_musicmanagercs.rad
06_prison.pak
06_prison_en_normal.pak
06_prison_en_normal.rad
06_prison_musicmanagercs.rad
07_gondola.pak
07_gondola_en_normal.pak
07_gondola_en_normal.rad
07_gondola_musicmanagercs.rad
08_temple.pak
08_temple_en_normal.pak
08_temple_en_normal.rad
08_temple_musicmanagercs.rad

data/ptx_tabledining_01_a.rcb
data/rs_89_prp_tree_39.rsc

ofx_01_fireballs_frontdeck.ofx
ofx_01_fireballs_approach.ofx
vfxa8_blur_01_c.rcb
ofx_fn_soldier.ofx
ofx_00_paper_disturb.ofx
ofx_fn_guardmale.ofx
ofx_fn_bender.ofx
collisionmaterials.xml
gestures.xml
act_momosamurai.rcb
vfx_toph_bendingwhip_projectile.rcb
rs_208_obj_arm.rsc
rs_184_obj_watertrigger.rsc
rs_241_aang air small.rsc
rs01_a.rcb
vfxa8_loadscreencloud_01_b.rcb
rs_21_skysphere.rsc
ltx_misc_whitebox.rcb
rs_16_l1s01zone01.rsc
rs_18_ant_aang_fe.xml.rsc
tx8_ui_frontend_avatarlogo.rcb
tx8_ui_frontend_avatarlogo_black.rcb
gen_108_savegame.str
gen_109_mainmenu.str
gen_115_messages.str
formal_big.rcb
formal.rcb
polo.rcb
## Post #9
- Username: triad
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 20, 2012 8:42 pm
- Post datetime: 2012-07-31T11:50:41+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

Is it possible that you look up how to open .rcb files? and maybe .cr4 files to:)
program is nearly ready!

The CR4 files contain (compressed?) tga files
## Post #10
- Username: triad
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 20, 2012 8:42 pm
- Post datetime: 2012-07-31T13:56:33+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

Oh, i've just found out that the .RAD files is the .PAK give information over the .PAK file with the same name

The CR4 files contain (compressed?) tga files
## Post #11
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-08T16:53:18+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

Here are some QuickBMS scripts to extract the PAK files from "Avatar The Last Airbender" (the first one for the PS2, the other 2 games have a slightly different format). You will need the newest version of "QuickBMS" which can be found here:
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

1. First Script:
[http://ps23dformat.wikispaces.com/file/ ... TA.PAK.bms](http://ps23dformat.wikispaces.com/file/view/avatar_DATA.PAK.bms)

```
ImpType Standard ;
Set F Long 20 ;
GoTo F 0 ;
Get F Long 0 ;
Set JF Long 16 ;
GoTo JF 0 ;
Get JF Long 0 ;
Set D Long 28 ;
GoTo D 0 ;
SavePos D 0 ;
For T = 1 To F ;
GoTO D 0 ;
Get FO Long 0 ;
Get CS Long 0 ;
SavePos H 0 ;
GoTo JF 0 ;
Get FN String 0 ;
SavePos JF 0 ;
GoTo H 0 ;
Get W Long 0 ;
Get W Long 0 ;
SavePos D 0 ;
Log FN FO CS 0 ;
Next T ;
</bms>
```

1. Use the script above called "avatar_DATA.PAK.BMS on the PAK files you see on the Avatar Disc.

2. Second Script:
[http://ps23dformat.wikispaces.com/file/ ... ressed.bms](http://ps23dformat.wikispaces.com/file/view/avatarPAKuncompressed.bms)

```
ImpType Standard ;
Set F Long 20 ;
GoTo F 0 ;
Get F Long 0 ;
Set JF Long 16 ;
GoTo JF 0 ;
Get JF Long 0 ;
Set D Long 28 ;
GoTo D 0 ;
SavePos D 0 ;
For T = 1 To F ;
GoTO D 0 ;
Get FO Long 0 ;
Get CS Long 0 ;
SavePos H 0 ;
GoTo JF 0 ;
Get FN String 0 ;
SavePos JF 0 ;
GoTo H 0 ;
Get W Long 0 ;
Get W Long 0 ;
SavePos D 0 ;
Log FN FO CS 0 ;
Next T ;
</bms>
```

2. Use the script above called "avatarPAKuncompressed.bms" on the PAK files that come out
on from using the first script. Extract them to any folder as an example we will call this "Folder B"

3. Third Script:
[http://ps23dformat.wikispaces.com/file/ ... ressed.bms](http://ps23dformat.wikispaces.com/file/view/avatarPAKcompressed.bms)

```
ImpType Standard ;
ComType zlib_noerror ;
Set F Long 20 ;
GoTo F 0 ;
Get F Long 0 ;
Set JF Long 16 ;
GoTo JF 0 ;
Get JF Long 0 ;
Set D Long 28 ;
GoTo D 0 ;
SavePos D 0 ;
For T = 1 To F ;
GoTO D 0 ;
Get FO Long 0 ;
Get CS Long 0 ;
SavePos H 0 ;
GoTo JF 0 ;
Get FN String 0 ;
SavePos JF 0 ;
GoTo H 0 ;
Get W Long 0 ;
Get W Long 0 ;
SavePos D 0 ;
CLog FN FO CS 90000000 0 ;
Next T ;
</bms>
```

3. Use the script above called "avatarPAKcompressed.bms" to decompress the PAK files that came out from
using the first script, but extract them to a different folder then where you did for the second script. Lets call this
"Folder C"
Now Delete the files in "Folder C" that say the size is 0 bytes.

4. Copy and paste the files/folders from the third step "Folder C", into the place where you extracted in the Second Step, "Folder B" and say Yes when it asks you if you want to override the existing files in "Folder B" with the files from the third step "Folder C".
If everything is done right all of the files in "Folder B" will be decompressed.
Now you can copy over the contents of "Folder B" into "Folder A".

As for the models they have the extension .rsc (but not .xml.rsc)
so rs_5_npc_eo_1_snowwolf.rsc would contain a model
but rs_1_ant_c4q00_wolf.xml.rsc would not contain a model (I think the .xml.rsc is animations).

The rsc model format is tricky but is basically texture/textures near the beginning of the file (BitMaps with the PS2 Texture Filter, but instead of the Color Palate having 256 Colors, is appears to only have 16 Colors (?) Any ways just like how Window Bitmaps can be the 256 color type and some can be other types, this is a variation of the PS2 BitMap.
Next is the mesh itself which has slightly different components (some use Floats, some used 2Byte Signed Integers), but the idea is that all of the model's vertexes appear first, then things like UV's, Normals ect. Except that that there is padding in between some vertexes. You get the padding from bytes in another section of the file, and each byte is the data size. So say you get a data size stream like
8,6,9
Then they might be padding in between the 8th vertex, and the 9th vertex, and in between the 14th vertex and the 15th Vertex.
The padding follows the rule that relative from the very first vertex, each vertex group has to start on a multiple of 16 bytes. And it is more complicated because the vertexes are formed by tristrips, but even more complicated because, there is a mesh component that tells when to terminate tristrips, that also it self has padding.
Here is an example of a wolf mesh I converted:
## Post #12
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2012-08-09T04:00:19+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

I'm highly impressed with all the fantastic work done on this!
## Post #13
- Username: triad
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 20, 2012 8:42 pm
- Post datetime: 2012-08-09T08:44:47+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

Great work! On the ps2disk there were some .bik videos. I've put them all on youtube! Search on youtube :: Avatar IntoTheInferno Official Content
## Post #14
- Username: triad
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 20, 2012 8:42 pm
- Post datetime: 2012-08-22T10:54:41+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

i've tried to extract the data.pak file but when i do so i'm told that i have to enter a new filename and then the program stops

could someone please help me with that?
## Post #15
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-26T22:29:31+00:00
- Post Title: PS2 Avatar The Last Airbender - models?

> Reply from triad
>
> i've tried to extract the data.pak file but when i do so i'm told that i have to enter a new filename and then the program stops

could someone please help me with that?

Send me a screenshot, but note that the scripts, only work for the first avatar game, called Avatar The Last Air Bender.
To use the QuickBMS script, download quickBMS. Then click clickBMS.exe, then select the script, then select the pak file, then select the folder to save the stuff in (sometimes you need to click in a different folder, to get past), then it should extract.

In fact if you could make a quick video using the free program called hypercam, that would let me help you even better.
## Post #16
- Username: triad
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 20, 2012 8:42 pm
- Post datetime: 2012-08-30T12:20:19+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

So it doesn't work for the avatar into the inferno?
## Post #17
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-30T20:37:22+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

> Reply from triad
>
> So it doesn't work for the avatar into the inferno?
No it does not, let me write up different scripts for that game. Also I will write up more scripts, that go more levels deeper, as RCB files contain/are contain in RSC files, and then mesh files can be within sides those
## Post #18
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-09-02T20:48:07+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

I am adding more scripts, for the first avatar game:
The improved PAK script, will extract both compressed and uncompressed PAK files:
[http://ps23dformat.wikispaces.com/file/ ... ps2pak.bms](http://ps23dformat.wikispaces.com/file/view/avatar1ps2pak.bms)

```
ImpType Standard ;
ComType zlib_noerror ;
Set F Long 20 ;
GoTo F 0 ;
Get F Long 0 ;
Set JF Long 16 ;
GoTo JF 0 ;
Get JF Long 0 ;
Set D Long 28 ;
GoTo D 0 ;
SavePos D 0 ;
For T = 1 To F ;
GoTO D 0 ;
Get FO Long 0 ;
Get CS Long 0 ;
SavePos H 0 ;
GoTo JF 0 ;
Get FN String 0 ;
SavePos JF 0 ;
GoTo H 0 ;
Get W Long 0 ;
Get W Long 0 ;
SavePos D 0 ;
GoTo FO 0 ;
Get Test short 0 ;
If Test = 40056 ;
CLog FN FO CS 350687200 0 ;
Else ;
Log FN FO CS 0;
Endif ;
Next T ;
</bms>
```


The script called "avatar1ps2rsc.bms" will extract files from the rsc files (some files from extracted rsc files will be duplicates of existing files, however some files are only found within rsc files, so it is still worth extracting them.
[http://ps23dformat.wikispaces.com/file/ ... ps2rsc.bms](http://ps23dformat.wikispaces.com/file/view/avatar1ps2rsc.bms)

```
Math SIZE -= 8 ;
GoTo 8 0 ;
Get CS Long 0 ;
GoTo 4 0 SEEK_CUR ;
Get namelength Byte 0 ;
GetDString FN namelength 0 ;
Padding 16 ;
SavePos FO 0 ;
Log FN FO CS 0;
GoTo FO 0 ;
GoTo CS 0 SEEK_CUR ;
SavePos i 0 ;
For Q = 0 < SIZE ;
GoTo i 0 ;
GoTo 2 0 SEEK_CUR ;
GoTo 8 0 SEEK_CUR ;
Get CS Long 0 ;
GoTo 4 0 SEEK_CUR ;
Get namelength Byte 0 ;
GetDString FN namelength 0 ;
Padding 16 ;
SavePos FO 0 ;
Log FN FO CS 0;
GoTo FO 0 ;
GoTo CS 0 SEEK_CUR ;
GoTo -1 0 SEEK_CUR ;
SavePos i 0 ;
Math Q = i ;
Math i += 1 ;
Next Q ;
```


The script called "avatar1ps2rcb" will extract RCB files.
[http://ps23dformat.wikispaces.com/file/ ... ps2rcb.bms](http://ps23dformat.wikispaces.com/file/view/avatar1ps2rcb.bms)

```
Math i = 0 ;
For Q = 0 < SIZE ;
GoTo i 0 ;
SavePos FO 0 ;
Get D Long 0 ;
Get ZZ Byte 0 ;
Math FN = FO ;
string FN += "." ;
string FN += ZZ ;
GoTo 7 0 SEEK_CUR ;
Get CS Long 0 ;
Math CS += 16 ;
Log FN FO CS 0 ;
GoTo FO 0 ;
GoTo CS 0 SEEK_CUR ;
GoTo -1 0 SEEK_CUR ;
SavePos i 0 ;
Math Q = i ;
Math i += 1 ;
Next Q ;
```


The extensions I have seen within RCB files have the following uses:
.00 some types of strings
.01 texture related
.03 model
.07 texture
.16 cutscene related
.50 model container (will contain at least one model)
.51 animation
.52 animation related.
## Post #19
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-09-27T22:07:16+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

This script will extract the PAK files from both Avatar 2 and Avatar 3
[http://ps23dformat.wikispaces.com/file/ ... nd3PAK.bms](http://ps23dformat.wikispaces.com/file/view/avatar2and3PAK.bms)

```
ImpType Standard ;
ComType zlib_noerror ;
GoTo 0x8 ;
Get base Long 0 ;
GoTo 0x14 ;
Get filenumber Long 0 ;
GoTo 0x10 ;
Get filenamebase Long 0 ;
Math filenamebase += base ;
GoTo base ;
SavePos werefox 0 ;
For T = 1 To filenumber ;
GoTo werefox 0 ;
Get fileoffset Long 0 ;
Get decompressedsize Long 0 ;
Get compressedsize Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get Type Long 0 ;
SavePos werefox 0 ;
GoTo filenamebase ;
Get filename String 0 ;
SavePos filenamebase 0 ;
If Type = 2053925218 ;
CLog filename fileoffset compressedsize decompressedsize 0 ;
Else ;
Log filename fileoffset decompressedsize 0;
Endif ;
Next T ;
```
## Post #20
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-10-18T23:09:53+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

I have made an early version of a script that will convert the mesh files from the first PS2 avatar game into .3ds files. First to get files to work on you must do the following.

Run this script on pak files from the disc:
[http://ps23dformat.wikispaces.com/file/ ... ps2pak.bms](http://ps23dformat.wikispaces.com/file/view/avatar1ps2pak.bms)

Then run the same script again on the pak files within the pak files
[http://ps23dformat.wikispaces.com/file/ ... ps2pak.bms](http://ps23dformat.wikispaces.com/file/view/avatar1ps2pak.bms)

Then run this script below on rsc files
[http://ps23dformat.wikispaces.com/file/ ... ps2rsc.bms](http://ps23dformat.wikispaces.com/file/view/avatar1ps2rsc.bms)

Then run this script below on rcb files
[http://ps23dformat.wikispaces.com/file/ ... ps2rcb.bms](http://ps23dformat.wikispaces.com/file/view/avatar1ps2rcb.bms)

Then run this script below on the .50 extension files extracted meshes will now have there names back
[http://ps23dformat.wikispaces.com/file/ ... tomesh.bms](http://ps23dformat.wikispaces.com/file/view/avatar50filestomesh.bms)

Then run this script below on the mesh files the script must be run on the windows command prompt with the w option, the w must be lower case and everything should be in your quickbms folder, and the quickbms folder path should have no spaces (ie do not use "program files") and no Asian characters,
[http://ps23dformat.wikispaces.com/file/ ... hto3ds.bms](http://ps23dformat.wikispaces.com/file/view/avatar1meshto3ds.bms)
 for example on my computer I typed in:

```
C:\v\quickbms.exe -w C:\v\avatar1meshto3ds.bms C:\v\act_gener_fn_rhino_ingame___ C:\v
```

then when it says what file to use type in what you want to save the 3ds file as for example rhino.3ds make sure the file does not exist before running it, otherwise it will be overwritten and not work.

Important currently supports only 2byteInt vertexes so if script makes no output file try a different mesh file for now


The script is not perfect yet but I do now how to fix it and will soon, here is a picture of output


I want to add support for ALL avatar games, for all systems.
## Post #21
- Username: flipdark95
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 08, 2016 12:24 pm
- Post datetime: 2017-04-17T07:44:03+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

So I've figured out most of what your method is for extracting the models, but for some reason when I run the script in CMD to convert the mesh file to a .3DS format, it won't work. Am I doing something wrong?

Here's a picture of the QuickBMS script and what I'm doing.



QuickBMS Avatar Model Rip Problem.PNG (103.2 KiB) Viewed 114 times



Edit: Never mind, got everything working. I read the instructions incorrectly and didn't realise is the name of the converted 3DS File.
## Post #22
- Username: flipdark95
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 08, 2016 12:24 pm
- Post datetime: 2017-06-11T13:27:29+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

So, just wondering, anybody know about any scripts out there that can extract the RCB files for the Avatar games after the first one? The QuickBMS scripts can currently only handle the first game's models.
## Post #23
- Username: flipdark95
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 08, 2016 12:24 pm
- Post datetime: 2017-08-02T16:09:22+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

Would really like to know what the status is on ripping models from the later 2 games. I'd love to be able to extract them for use as references and research in my 3D modelling.
## Post #24
- Username: AvatarAang
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 06, 2018 6:13 am
- Post datetime: 2018-07-05T22:17:27+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

> Reply from FurryFan
>
> This script will extract the PAK files from both Avatar 2 and Avatar 3
http://ps23dformat.wikispaces.com/file/ ... nd3PAK.bms
Code: Select all<bms games="'Avatar 2 and Avatar 3'" platforms="'PS2'" ext="PAK">
ImpType Standard ;
ComType zlib_noerror ;
GoTo 0x8 ;
Get base Long 0 ;
GoTo 0x14 ;
Get filenumber Long 0 ;
GoTo 0x10 ;
Get filenamebase Long 0 ;
Math filenamebase += base ;
GoTo base ;
SavePos werefox 0 ;
For T = 1 To filenumber ;
GoTo werefox 0 ;
Get fileoffset Long 0 ;
Get decompressedsize Long 0 ;
Get compressedsize Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get Type Long 0 ;
SavePos werefox 0 ;
GoTo filenamebase ;
Get filename String 0 ;
SavePos filenamebase 0 ;
If Type = 2053925218 ;
CLog filename fileoffset compressedsize decompressedsize 0 ;
Else ;
Log filename fileoffset decompressedsize 0;
Endif ;
Next T ;

Thanks, its working, but what im gonna do with .RCB files? They supposed to be unpackaged, right?

Edit: Its working, but now im stuck with the last part like the flipdark95
## Post #25
- Username: AvatarAang
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 06, 2018 6:13 am
- Post datetime: 2018-07-05T22:52:40+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

> Reply from flipdark95
>
> So I've figured out most of what your method is for extracting the models, but for some reason when I run the script in CMD to convert the mesh file to a .3DS format, it won't work. Am I doing something wrong?

Here's a picture of the QuickBMS script and what I'm doing.
QuickBMS Avatar Model Rip Problem.PNG

Edit: Never mind, got everything working. I read the instructions incorrectly and didn't realise is the name of the converted 3DS File.

Can you explain please, what there is need to do?
## Post #26
- Username: Smolgreen
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 10, 2018 8:19 am
- Post datetime: 2018-12-26T10:15:06+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

Links to scripts seem to be gone,  could someone reupload them?
## Post #27
- Username: MarKreationsStudios
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 03, 2020 5:47 am
- Post datetime: 2021-04-08T16:18:49+00:00
- Post Title: Re: PS2 Avatar The Last Airbender - models?

Can you fix the download links??
