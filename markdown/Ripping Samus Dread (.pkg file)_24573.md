## Post #1
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-05T15:28:00+00:00
- Post Title: Ripping Samus Dread (.pkg file)

Hi everyone I extracted the .NCA from the .NSP of Metroid Dread and now I'm trying to open the Samus.pkg file but I can't seem to remember how to do it    
Anyone can help me with it?
## Post #2
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-05T18:10:49+00:00
- Post Title: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Tue Oct 05, 2021 11:28 pm at Tue Oct 05, 2021 11:28 pm
>
> 
Hi everyone I extracted the .NCA from the .NSP of Metroid Dread and now I'm trying to open the Samus.pkg file but I can't seem to remember how to do it    
Anyone can help me with it?

it meight help posting a pkg file really. im uploading some stuff aswell so ill do it too
## Post #3
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-05T18:19:17+00:00
- Post Title: Ripping Samus Dread (.pkg file)

well here is the player one. at least the pkg extracter i had didnt do squad but need to do more poking around.

**edit** removed drive link email got spammed to snot with requests
## Post #4
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-05T18:57:32+00:00
- Post Title: Ripping Samus Dread (.pkg file)

> Reply from kees ↑Wed Oct 06, 2021 2:19 am at Wed Oct 06, 2021 2:19 am
>
> 
well here is the player one. at least the pkg extracter i had didnt do squad but need to do more poking around.

https://drive.google.com/file/d/15lKGiY ... sp=sharing

Sorry, yes, thats the file I go too. I tried many bms files for quickbms that I found on github, including metroid_sr_3ds.bmd but didin´t work either...
## Post #5
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-05T19:03:20+00:00
- Post Title: Ripping Samus Dread (.pkg file)

I ran Quickbms from the cmd and got this error message. The script metroid_sr_3ds.bms did work for Samus Returns files but they wheren't .dat so I can't open those...  I can't find a good pkg script that work with Metroid Dread
[quikcbms metroid.png](https://xentaxbackup.github.io/file/20950_quikcbms metroid.png)
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-05T22:44:56+00:00
- Post Title: Ripping Samus Dread (.pkg file)

Here is simple script for Metroid Dread pkgs, it's almost a copy of Samus Returns script with a few adjustments. 

Update: Script for bctex decompression added.

Update 2: Script for bctex now extracts first mip as "raw" file. You can convert it with tools like Rawtex and provided in the filename parameters + switch swizzle. If you want to simply decompress the texture, edit first line in the script accordingly.



 metroid_dread_scripts.zip
(1.12 KiB) Downloaded 170 times
## Post #7
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-05T23:51:23+00:00
- Post Title: Ripping Samus Dread (.pkg file)

> Reply from Spiritovod ↑Wed Oct 06, 2021 6:44 am at Wed Oct 06, 2021 6:44 am
>
> 
Here is simple script for Metroid Dread pkgs, it's almost a copy of Samus Returns script with a few adjustments. 


metroid_dread_pkg.zip

Thank you very much!!! It works!! I still can't open the files... but is progress   
This is the file with the results but they are all .MSAS .MMDL .MANM .MCAN .MSUR .MPSY and some .dat that i though i can open with Noesis but nope..

[https://drive.google.com/file/d/11VTehc ... sp=sharing](https://drive.google.com/file/d/11VTehcwXimm7fvFirpuBW-0Pi1SZNx2g/view?usp=sharing)
## Post #8
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-06T14:35:54+00:00
- Post Title: Ripping Samus Dread (.pkg file)

> Reply from Spiritovod ↑Wed Oct 06, 2021 6:44 am at Wed Oct 06, 2021 6:44 am
>
> 
Here is simple script for Metroid Dread pkgs, it's almost a copy of Samus Returns script with a few adjustments. 


metroid_dread_pkg.zip

thanks so much for that! serieusly. meight be the same as the standard filesystem for samus returns aswell? at least am hoping so since then the older tools meight be able to be ajusted too somewhat. but am fearing thats a lot harder tho
## Post #9
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-08T15:05:46+00:00
- Post Title: Ripping Samus Dread (.pkg file)

been looking into mmdl files seeing if there has been an existing way to rip em compleetly but so far have not gone that far really. there has been some info what came to samus returns but even that it seems hasnt been researched enough or even ripped at all. furthest ive found is that someone was hinting at specific locations in hex where to find the model data. but no tools at all yet 
[viewtopic.php?f=16&t=17939&p=139514&hil ... ns#p139514](https://forum.xentax.com/viewtopic.php?f=16&t=17939&p=139514&hilit=samus+returns#p139514)

09williamsad found out some info pertaining to texture formats but sadly the tools didnt work. but thought should mention the info regardless view
[viewtopic.php?f=16&t=24585&p=178689&hilit=mmdl#p178689](https://forum.xentax.com/viewtopic.php?f=16&t=24585&p=178689&hilit=mmdl#p178689)
## Post #10
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-08T16:22:20+00:00
- Post Title: Ripping Samus Dread (.pkg file)

> Reply from kees ↑Fri Oct 08, 2021 11:05 pm at Fri Oct 08, 2021 11:05 pm
>
> 
been looking into mmdl files seeing if there has been an existing way to rip em compleetly but so far have not gone that far really. there has been some info what came to samus returns but even that it seems hasnt been researched enough or even ripped at all. furthest ive found is that someone was hinting at specific locations in hex where to find the model data. but no tools at all yet 
viewtopic.php?f=16&t=17939&p=139514&hil ... ns#p139514

09williamsad found out some info pertaining to texture formats but sadly the tools didnt work. but thought should mention the info regardless view
viewtopic.php?f=16&t=24585&p=178689&hilit=mmdl#p178689

Yes i've seen those... I figured that since nobody was abble to extract the Samus Returns 3d models it would happen the same with Dread... I've got the same files ( I shared them above) but can't find a way to open them
## Post #11
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-08T16:48:24+00:00
- Post Title: Ripping Samus Dread (.pkg file)

Script for bctex decompression added to my post above. I didn't bother with it much, but those are mipped textures, compressed with gzip - they're also using switch swizzling and most of them are DXT5. In decompressed textures first 0x78 bytes are base header, then there is 0xAC bytes of probably mips data, then at 0x124 there is additional header with total texture size and header size, then at 0x278 actual texture data. Probably format around the same as previous bctex, except for a few additional fields / magics.

Here is sample, converted with rawtex:  [https://drive.google.com/file/d/1TofvOA ... sp=sharing](https://drive.google.com/file/d/1TofvOAT_RblgmLBbzU6YuX4TxoBxc5iO/view?usp=sharing)
## Post #12
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2021-10-08T16:51:32+00:00
- Post Title: Ripping Samus Dread (.pkg file)

I worked a bit on samus returns a while back but stopped when i noticed someone else had already extracted meshes from it. I poked around dread files and the system is mostly the same but with some tweaks. Their engine does so many stupid things. I've poked around it mostly for the last few days and got something mostly working but with some bugs i need to work out some. 

An example of the stupid things being done: Only the vert and indice data is compressed. They have tables that point to ever vert info and face info but have a table full of mesh info that then points to the vert and indice data anyway. Have a table of bone indexes used for the mesh as reference with the the weights referencing the index of that table instead of just the bone index directly. Lastly they have some meshes that have a normal placement value and other meshes that require the being attached to the skeleton before it's placed to get junk placed. Her cannon took me so long to get right.

I planned on tweaking my code a bit more after work to fix a few things, granted i dont get distracted by playing the game itself 

edit: If spirit or someone else doesnt beat me to it, i can try making a noesis script for the textures. I haven't fiddled with noesis's api yet but it's something i've been meaning to do for a while now so i'm not always making scripts directly for blender.
## Post #13
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-08T18:10:09+00:00
- Post Title: Ripping Samus Dread (.pkg file)

Here's a Noesis script to load the mmdl/bcmdl files, supports mesh names, uvs, normals, skeleton with joint names and skinning. Many thanks to M-1 for the help with his samus returns research. Dread's format is basically an "upgrade" of that one, with a bunch of changes in the layout and some buffers being compressed.

It should work on environmental and skeleton meshes, at least all the samples I checked work fine.

[https://github.com/Joschuka/fmt_mmdl](https://github.com/Joschuka/fmt_mmdl)

Update 1 : More semantics added, preliminary texture support

Update 2 : Material auto assigning (kind of...)

Update 3 : The script now supports animations. It's recommended to extract the pkg files using the Switch Toolbox to have filenames.




> Reply from pox911 ↑Sat Oct 09, 2021 12:51 am at Sat Oct 09, 2021 12:51 am
>
> 
Lastly they have some meshes that have a normal placement value and other meshes that require the being attached to the skeleton before it's placed to get junk placed. Her cannon took me so long to get right.

This part actually annoyed me a lot, I had the exact same issue. Meshes with rigid skinning needed their vertices to be transformed by their associated joint. 
Also I wasn't aware that someone else was planning to release a model plugin for this game, at least it'll help double checking the research done heh

> Reply from Spiritovod ↑Sat Oct 09, 2021 12:48 am at Sat Oct 09, 2021 12:48 am
>
> 
Script for bctex decompression added to my post above. I didn't bother with it much, but those are mipped textures, compressed with gzip - they're also using switch swizzling and most of them are DXT5. In decompressed textures first 0x78 bytes are base header, then there is 0xAC bytes of probably mips data, then at 0x124 there is additional header with total texture size and header size, then at 0x278 actual texture data. Probably format around the same as previous bctex, except for a few additional fields / magics.

Here is sample, converted with rawtex:  https://drive.google.com/file/d/1-iUAAk ... sp=sharing

Neat, I don't like working on textures so that's helpful. I'll add bctex support to the plugin later if it's straighforward enough
## Post #14
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-08T18:47:58+00:00
- Post Title: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 2:10 am at Sat Oct 09, 2021 2:10 am
>
> 
Neat, I don't like working on textures so that's helpful. I'll add bctex support to the plugin later if it's straighforward enough
It's pretty much straightforward, if you need only the first mip. In decompressed texture:
-> 0x8 (and at 0xB8): int height, int width 
-> 0xCC: int mip_count
if mip_count = 1:  int mip_size
else   int texture_size, int mip_offset, next_mip_offset, ... (offset is calculated starting from 0x278)

They're using padding for headers, so offsets for those values are hardcoded - at least for models textures.
## Post #15
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-08T18:50:43+00:00
- Post Title: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 2:10 am at Sat Oct 09, 2021 2:10 am
>
> 
Here's a Noesis script to load the mmdl files, supports mesh names, uvs, normals, skeleton with joint names and skinning. Many thanks to M-1 for the help with his samus returns research. Dread's format is basically an "upgrade" of that one, with a bunch of changes in the layout and some buffers being compressed.

It should work on environmental and skeleton meshes, at least all the samples I checked work fine.

https://github.com/Joschuka/fmt_mmdl

Thank you for the Noesis script.

I ran it in batch on all the MMDL models to see the results.
Out of 8333 models, only 182 did not convert, list attached.
[MDNoConvert.zip](https://xentaxbackup.github.io/file/20973_MDNoConvert.zip)
## Post #16
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-08T20:22:44+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Spiritovod ↑Sat Oct 09, 2021 12:48 am at Sat Oct 09, 2021 12:48 am
>
> 
Script for bctex decompression added to my post above. I didn't bother with it much, but those are mipped textures, compressed with gzip - they're also using switch swizzling and most of them are DXT5. In decompressed textures first 0x78 bytes are base header, then there is 0xAC bytes of probably mips data, then at 0x124 there is additional header with total texture size and header size, then at 0x278 actual texture data. Probably format around the same as previous bctex, except for a few additional fields / magics.

Here is sample, converted with rawtex:  https://drive.google.com/file/d/1TofvOA ... sp=sharing

i was trying to use the script for the bctx and i tried using it in a couple ways and only got errors. i dont know if you can leave a bit more detailed info on what to use that on and how to get to that stage to put it in rawtex. the rawtex stuff is understandable. switch swizzle and mostly DXT5 Texture Formats for cookin them up. just having a wee bit throuble so sorry about the throuble asking for clearification.. 

****EDIT**** im a dumbich didnt know it was stored elsewere. been doing so much at once i didnt notice it. fuck
so am trying to get it to work now with plugging decompressed bctex into rawtex
## Post #17
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-08T20:45:57+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 2:10 am at Sat Oct 09, 2021 2:10 am
>
> 
Here's a Noesis script to load the mmdl files, supports mesh names, uvs, normals, skeleton with joint names and skinning. Many thanks to M-1 for the help with his samus returns research. Dread's format is basically an "upgrade" of that one, with a bunch of changes in the layout and some buffers being compressed.

It should work on environmental and skeleton meshes, at least all the samples I checked work fine.

https://github.com/Joschuka/fmt_mmdl


pox911 wrote: ↑Sat Oct 09, 2021 12:51 am
Lastly they have some meshes that have a normal placement value and other meshes that require the being attached to the skeleton before it's placed to get junk placed. Her cannon took me so long to get right.


This part actually annoyed me a lot, I had the exact same issue. Meshes with rigid skinning needed their vertices to be transformed by their associated joint. 
Also I wasn't aware that someone else was planning to release a model plugin for this game, at least it'll help double checking the research done heh
Spiritovod wrote: ↑Sat Oct 09, 2021 12:48 am
Script for bctex decompression added to my post above. I didn't bother with it much, but those are mipped textures, compressed with gzip - they're also using switch swizzling and most of them are DXT5. In decompressed textures first 0x78 bytes are base header, then there is 0xAC bytes of probably mips data, then at 0x124 there is additional header with total texture size and header size, then at 0x278 actual texture data. Probably format around the same as previous bctex, except for a few additional fields / magics.

Here is sample, converted with rawtex:  https://drive.google.com/file/d/1-iUAAk ... sp=sharing


Neat, I don't like working on textures so that's helpful. I'll add bctex support to the plugin later if it's straighforward enough

 First of all, thank you so much for the help!!!!! but I have a problem with the plugin, this error message show up:
[mmdl error message.png](https://xentaxbackup.github.io/file/20974_mmdl error message.png)
## Post #18
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-08T20:49:18+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sat Oct 09, 2021 4:45 am at Sat Oct 09, 2021 4:45 am
>
> 
 First of all, thank you so much for the help!!!!! but I have a problem with the plugin, this error message show up:

Is that on opening a file or launching noesis?

If the latter then you may want to update noesis, I did not have any launch issues on 4.456.
## Post #19
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-08T20:56:19+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from 09williamsad ↑Sat Oct 09, 2021 4:49 am at Sat Oct 09, 2021 4:49 am
>
> 
Enderfacio wrote: ↑Sat Oct 09, 2021 4:45 am
 First of all, thank you so much for the help!!!!! but I have a problem with the plugin, this error message show up:


Is that on opening a file or launching noesis?

If the latter then you may want to update noesis, I did not have any launch issues on 4.456.

When I try to open Noesis. I just downloaded v4458 and same thing happens =/
## Post #20
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-08T21:08:28+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sat Oct 09, 2021 4:56 am at Sat Oct 09, 2021 4:56 am
>
> 
When I try to open Noesis. I just downloaded v4458 and same thing happens =/

I think you may have downloaded the webpage instead of the py script.
The error has a HTML doctype, which is not in the python script.
## Post #21
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-08T21:09:10+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sat Oct 09, 2021 4:56 am at Sat Oct 09, 2021 4:56 am
>
> 
09williamsad wrote: ↑Sat Oct 09, 2021 4:49 am
Enderfacio wrote: ↑Sat Oct 09, 2021 4:45 am
 First of all, thank you so much for the help!!!!! but I have a problem with the plugin, this error message show up:


Is that on opening a file or launching noesis?

If the latter then you may want to update noesis, I did not have any launch issues on 4.456.


When I try to open Noesis. I just downloaded v4458 and same thing happens =/

wierd cause v4433 works fine on my end. really wierd. lemme send a package version with the updated plugin in there that he posted

[https://www.filemail.com/d/uibvpdchcgarsnj](https://www.filemail.com/d/uibvpdchcgarsnj)
## Post #22
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-08T21:43:39+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from kees ↑Sat Oct 09, 2021 5:09 am at Sat Oct 09, 2021 5:09 am
>
> 
Enderfacio wrote: ↑Sat Oct 09, 2021 4:56 am
09williamsad wrote: ↑Sat Oct 09, 2021 4:49 am


Is that on opening a file or launching noesis?

If the latter then you may want to update noesis, I did not have any launch issues on 4.456.


When I try to open Noesis. I just downloaded v4458 and same thing happens =/


wierd cause v4433 works fine on my end. really wierd. lemme send a package version with the updated plugin in there that he posted

https://www.filemail.com/d/uibvpdchcgarsnj

YeeeeaahhH!!! I don't know why but that seems to work hahaha Thank you very much dude!!!
[YeasssFinally.png](https://xentaxbackup.github.io/file/20975_YeasssFinally.png)
## Post #23
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-08T23:11:22+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

I've updated script for bctex in the package - it now extracts first mip from decompressed texture as "raw" file. You can convert it with Rawtex and provided in the filename parameters + switch swizzle (quickbms obviously doesn't support swizzling, so you can't directly convert to dds with it). Script still supports decompression only, for that simply edit the first line.
## Post #24
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-08T23:29:49+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Spiritovod ↑Sat Oct 09, 2021 12:48 am at Sat Oct 09, 2021 12:48 am
>
> 
Script for bctex decompression added to my post above. I didn't bother with it much, but those are mipped textures, compressed with gzip - they're also using switch swizzling and most of them are DXT5. In decompressed textures first 0x78 bytes are base header, then there is 0xAC bytes of probably mips data, then at 0x124 there is additional header with total texture size and header size, then at 0x278 actual texture data. Probably format around the same as previous bctex, except for a few additional fields / magics.

Here is sample, converted with rawtex:  https://drive.google.com/file/d/1TofvOA ... sp=sharing

alright i got it to work for the normal standard textures. basically after decompressing run it through rawtex with 0xoffset 0x278 gives the standard texture. meanwhile now im trying to fath around with the normal maps but it is a difrent format. am trying to trial and error see if i can find wich format it is cause it doesnt seem to be DXT5 or its close relatives (BC3).

as soon as i was done writing it just submitted. found the format for normals.its BC5U (ATI2) for the ones ive tested. but the same happend as with DE ones. photoshop acts wierd with it. and paint .net craps its pants. luckally we already use noesis and its able to read the muppet. so just open that file in noesis and export. and that should do it. imma do the rest of em and post a complete build soonish of it all together. there are som mappings happening witht the funny alpha layer but that hopefully with a bit of editing wont be an issue
[Dread Normals Edit.jpg](https://xentaxbackup.github.io/file/20977_Dread Normals Edit.jpg)
## Post #25
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-08T23:31:47+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Spiritovod ↑Sat Oct 09, 2021 7:11 am at Sat Oct 09, 2021 7:11 am
>
> 
I've updated script for bctex in the package - it now extracts first mip from decompressed texture as "raw" file. You can convert it with Rawtex and provided in the filename parameters + switch swizzle (quickbms obviously doesn't support swizzling, so you can't directly convert to dds with it). Script still supports decompression only, for that simply edit the first line.

right when i just got it working and figured out normals somewhat XD. imma try the new script edit of yours and see how it goes.

***edit*** just tried the V2 script and it does works yaye. still need to re export normals via noesis but at least the raws tell you what format it is now so its less confusing. and not to mention eliminating the 0xoffset
## Post #26
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-09T00:30:55+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 2:10 am at Sat Oct 09, 2021 2:10 am
>
> 
Here's a Noesis script to load the mmdl files, supports mesh names, uvs, normals, skeleton with joint names and skinning. Many thanks to M-1 for the help with his samus returns research. Dread's format is basically an "upgrade" of that one, with a bunch of changes in the layout and some buffers being compressed.

It should work on environmental and skeleton meshes, at least all the samples I checked work fine.

https://github.com/Joschuka/fmt_mmdl


pox911 wrote: ↑Sat Oct 09, 2021 12:51 am
Lastly they have some meshes that have a normal placement value and other meshes that require the being attached to the skeleton before it's placed to get junk placed. Her cannon took me so long to get right.


This part actually annoyed me a lot, I had the exact same issue. Meshes with rigid skinning needed their vertices to be transformed by their associated joint. 
Also I wasn't aware that someone else was planning to release a model plugin for this game, at least it'll help double checking the research done heh
Spiritovod wrote: ↑Sat Oct 09, 2021 12:48 am
Script for bctex decompression added to my post above. I didn't bother with it much, but those are mipped textures, compressed with gzip - they're also using switch swizzling and most of them are DXT5. In decompressed textures first 0x78 bytes are base header, then there is 0xAC bytes of probably mips data, then at 0x124 there is additional header with total texture size and header size, then at 0x278 actual texture data. Probably format around the same as previous bctex, except for a few additional fields / magics.

Here is sample, converted with rawtex:  https://drive.google.com/file/d/1-iUAAk ... sp=sharing


Neat, I don't like working on textures so that's helpful. I'll add bctex support to the plugin later if it's straighforward enough


we got an issue with the mapping of the materials. i dont know how your script works joshka but there are more than 1 material assigned to a mesh. i assigned the body texture and noticed the shoulders were off. i overlayed the UVmap over the head one for the shoulders. and it seems to fit right.  when earlier tried the varia suit i noticed some funkyness with the textures in some places being off. could this be the culpred? 

in the meantime im gonna collect all the textures base ones i can and make a zip file to put in here and report an issue on the github.

***edit*** here is the link with the file. it should have the material ajusted for it (only included the ones i showed the issue with to keep size down and it shows enough anyway). not sure if it will be any help but here it is. also ill refrain from sending it on the github since i see youre still updating it so im not posting issues when youre already at it probably fixing it 
[https://www.filemail.com/d/rrrbaphcweqbjyz](https://www.filemail.com/d/rrrbaphcweqbjyz)

***edit2*** the new script for noesis works good and the vertex colors are getting picked up so! the only thing is that material issue but i know that happend right before i posted that.
[Dread Multi Materials Assigned.jpg](https://xentaxbackup.github.io/file/20978_Dread Multi Materials Assigned.jpg)
## Post #27
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-09T02:19:33+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from kees ↑Sat Oct 09, 2021 7:31 am at Sat Oct 09, 2021 7:31 am
>
> 
Spiritovod wrote: ↑Sat Oct 09, 2021 7:11 am
I've updated script for bctex in the package - it now extracts first mip from decompressed texture as "raw" file. You can convert it with Rawtex and provided in the filename parameters + switch swizzle (quickbms obviously doesn't support swizzling, so you can't directly convert to dds with it). Script still supports decompression only, for that simply edit the first line.


right when i just got it working and figured out normals somewhat XD. imma try the new script edit of yours and see how it goes.

***edit*** just tried the V2 script and it does works yaye. still need to re export normals via noesis but at least the raws tell you what format it is now so its less confusing. and not to mention eliminating the 0xoffset

The textures you shared worked fine. The body used one and the head, arms and shoulders used the other. The only one missing is the arm cannon
[Samus_test01.jpg](https://xentaxbackup.github.io/file/20980_Samus_test01.jpg)
## Post #28
- Username: ryburgers
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 09, 2021 6:39 am
- Post datetime: 2021-10-09T06:36:49+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Very cool. With the .bctex files, are there any r/g/b channel swaps or inverts necessary after using rawtex? I seem to be getting overly blue .dds image output from rawtex. I've tried both the original and v2 bms scripts, but the result is the same. Looking at powerbody and powerhead textures shared above for example, I'm not getting the red in the breastplate.

I don't often deal with texture encoding, so I'm just curious what's happening here. Or if maybe there are some in-between steps I'm not understanding. I'm getting the normals output in good shape though.

Lastly, the powerbody_bc in the sample texture download looks more like my powerbody_at. What's up with that? Do the two textures need to be combined somehow? My powerbody_bc is mostly blank with green accents.
[rawtex_output_example.JPG](https://xentaxbackup.github.io/file/20982_rawtex_output_example.JPG)
## Post #29
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-09T07:46:22+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Ok so

SCRIPT UPDATED
-New semantics added (tangents, secondary, 3rd UV channels, colors)
-A few fixes on models not loading
-Preliminary texture support, you can now load the bctex directly in Noesis. I only added the BC5 and DXT5 types for now, if you encounter more report it here or on the git repo and I'll add them.

> Reply from 09williamsad ↑Sat Oct 09, 2021 2:50 am at Sat Oct 09, 2021 2:50 am
>
> 
Thank you for the Noesis script.
I ran it in batch on all the MMDL models to see the results.
Out of 8333 models, only 182 did not convert, list attached.

Cool thanks, some of them may have been fixed by M-1's last additions. I'd suggest giving another try with the latest version, I'll check the remaining non working files.

> Reply from Enderfacio ↑Sat Oct 09, 2021 4:45 am at Sat Oct 09, 2021 4:45 am
>
> 
 First of all, thank you so much for the help!!!!! but I have a problem with the plugin, this error message show up:

Np, glad you like it . This happened because you saved the html page instead of the actual script.

> Reply from kees ↑Sat Oct 09, 2021 8:30 am at Sat Oct 09, 2021 8:30 am
>
> 
we got an issue with the mapping of the materials. i dont know how your script works joshka but there are more than 1 material assigned to a mesh. i assigned the body texture and noticed the shoulders were off. i overlayed the UVmap over the head one for the shoulders. and it seems to fit right.  when earlier tried the varia suit i noticed some funkyness with the textures in some places being off. could this be the culpred? 

in the meantime im gonna collect all the textures base ones i can and make a zip file to put in here and report an issue on the github.

***edit*** here is the link with the file. it should have the material ajusted for it (only included the ones i showed the issue with to keep size down and it shows enough anyway). not sure if it will be any help but here it is. also ill refrain from sending it on the github since i see youre still updating it so im not posting issues when youre already at it probably fixing it 
https://www.filemail.com/d/rrrbaphcweqbjyz

***edit2*** the new script for noesis works good and the vertex colors are getting picked up so! the only thing is that material issue but i know that happend right before i posted that.

The meshes are put together based on their original names, I didn't try to assign textures so far but it should work correctly. Enderfacio managed to get it right it seems.

> Reply from Enderfacio ↑Sat Oct 09, 2021 10:19 am at Sat Oct 09, 2021 10:19 am
>
> 
The textures you shared worked fine. The body used one and the head, arms and shoulders used the other. The only one missing is the arm cannon

The way this game assigns materials is based on paths but most of them are hashed, so auto texture assignment is going to be tricky. What I'll be able to do at least is to dump the names of textures supposed to be assigned to each mesh, but then the user would have to find it manually. I'll see what I can do for this, barely looked into the material/meshes relation tbh

> Reply from rdaugherty3 ↑Sat Oct 09, 2021 2:36 pm at Sat Oct 09, 2021 2:36 pm
>
> 
Very cool. With the .bctex files, are there any r/g/b channel swaps or inverts necessary after using rawtex? I seem to be getting overly blue .dds image output from rawtex. I've tried both the original and v2 bms scripts, but the result is the same. Looking at powerbody and powerhead textures shared above for example, I'm not getting the red in the breastplate.

I don't often deal with texture encoding, so I'm just curious what's happening here. Or if maybe there are some in-between steps I'm not understanding. I'm getting the normals output in good shape though.

Lastly, the powerbody_bc in the sample texture download looks more like my powerbody_at. What's up with that? Do the two textures need to be combined somehow? My powerbody_bc is mostly blank with green accents.

In Noesis you can press the cycle blend button to make the diffuse texture appear "correctly", it's the second one on your screen. As for how the to get it right on Blender I think you just need to ignore the alpha channel or something like this.
## Post #30
- Username: samboychips
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 07, 2020 4:04 pm
- Post datetime: 2021-10-09T08:55:55+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

I'm trying to extract the NCA for this but it's asking me for the titlekey. Does anyone happen to know where I can find this or can someone possibly send it/post it here?
## Post #31
- Username: ShadowOfMagnus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 09, 2021 6:48 pm
- Post datetime: 2021-10-09T10:49:34+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Were the files for the ship found yet?
## Post #32
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-09T11:21:50+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from samboychips ↑Sat Oct 09, 2021 4:55 pm at Sat Oct 09, 2021 4:55 pm
>
> 
I'm trying to extract the NCA for this but it's asking me for the titlekey. Does anyone happen to know where I can find this or can someone possibly send it/post it here?

Drag and drop the games .tik file from the NSP/XCI onto GetTitlekey.exe to get the key.
The tik is with the NCA.
If there is no tik then the archive you have may not need a key.
[GetTitlekey.zip](https://xentaxbackup.github.io/file/20984_GetTitlekey.zip)
## Post #33
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-09T12:18:33+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 3:46 pm at Sat Oct 09, 2021 3:46 pm
>
> 
Cool thanks, some of them may have been fixed by M-1's last additions. I'd suggest giving another try with the latest version, I'll check the remaining non working files.

5700 textures, from looking around 2106 did not convert, most of them are all white with some being another colour, list attached.

Models reconverted with the new script, 8333 total with 40 that did not convert, list attached.
[NoConvertModelsAndTextures.zip](https://xentaxbackup.github.io/file/20986_NoConvertModelsAndTextures.zip)
## Post #34
- Username: Esbeckett
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 17, 2014 1:12 pm
- Post datetime: 2021-10-09T13:18:34+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Is there any information on finding the monster models? Are they in the map files or should they have been in the characters subfolder?

I'm wondering if I used the wrong method to extract assets from the cart, honestly. I only found Samus and so far everything's worked great, including removing the alpha with a combination of imagemagick and rawtex. I used 

```
    echo %%~nf
    magick convert %%f -alpha off %%f_noalpha.png
)
```

and dragged and dropped the entirety of the DDS files on the batch, but I also made a second pack and used something to separate the RGB channels, since anything labelled _bc just needed the alpha gone, but some of the others are layered maps that really needed to be split into RGB, the AT ones.

Edit: I should declare I converted them to PNG with noesis first. 
Anything with _bc you remove the alpha channel for, and the _at ones contain the maps like metallic maps which means separating the R, G, and B into separate things. Which isn't necessary for every use, just some. It should also fix the transparency issue some people would have. The _nm is just a normalmap and you don't need to mess with it much.
## Post #35
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-09T14:30:47+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

This new update adds basic auto texture assigning. When working, if you load a model the script will load the associated textures and apply them directly (don't forget to cycle blend if you don't see anything in the preview) :



Make sure to have the new associated .txt file next to the script. It's basically used as a dictionnary to grab the full paths of the textures since the mmdl only have their names. The game seems to do everything with hashes so I can't do better without knowing the hash function, unless I'm missing something.

Anyways, to make it work :
-set your dump path at the top of the .py file
-set the scanning option to True
-vertex colors screw up some of the models since they're probably not meant to be used during rendering, set the option to load them to false to make sure you have a correct preview (especially for environment models)

That's it, you just have to set it once, then you can just load the models as usual, the script will do the rest.

> Reply from 09williamsad ↑Sat Oct 09, 2021 8:18 pm at Sat Oct 09, 2021 8:18 pm
>
> 
Joschka wrote: ↑Sat Oct 09, 2021 3:46 pm
Cool thanks, some of them may have been fixed by M-1's last additions. I'd suggest giving another try with the latest version, I'll check the remaining non working files.


5700 textures, from looking around 2106 did not convert, most of them are all white with some being another colour, list attached.

Models reconverted with the new script, 8333 total with 40 that did not convert, list attached.

Cool thanks, I'll take a look later

> Reply from Esbeckett ↑Sat Oct 09, 2021 9:18 pm at Sat Oct 09, 2021 9:18 pm
>
> 
Is there any information on finding the monster models? Are they in the map files or should they have been in the characters subfolder?

I saw some enemy models in places like packs\maps\s010_cave\subareas
## Post #36
- Username: Esbeckett
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 17, 2014 1:12 pm
- Post datetime: 2021-10-09T14:48:58+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 10:30 pm at Sat Oct 09, 2021 10:30 pm
>
> I saw some enemy models in places like packs\maps\s010_cave\subareas
Excellent, thanks for confirming! It should be easy enough to just swap the python script, so I'll do that. It seems a bit weird on their part to have Samus alone in the characters subfolder and then shove everything else into the respective maps.
## Post #37
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-09T18:33:05+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 10:30 pm at Sat Oct 09, 2021 10:30 pm
>
> 
This new update adds basic auto texture assigning. When working, if you load a model the script will load the associated textures and apply them directly (don't forget to cycle blend if you don't see anything in the preview) :
I saw some enemy models in places like packs\maps\s010_cave\subareas

Thanks, I am testing the new version now.
It seems that the texture assignment only works on some models.
00000003.MMDL in the players\Samus pkg/folder works fine, but 00000142.MMDL in the same place does not.
Alot of map/level chunks seem to be fine.

The Noesis debug log has alot of this:

```
-texnorepfn parameter accepted.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_0_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_1_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_2_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_3_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_4_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_5_material'...Failed.

```
## Post #38
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-09T19:12:29+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from 09williamsad ↑Sun Oct 10, 2021 2:33 am at Sun Oct 10, 2021 2:33 am
>
> 
Thanks, I am testing the new version now.
It seems that the texture assignment only works on some models.
00000003.MMDL in the players\Samus pkg/folder works fine, but 00000142.MMDL in the same place does not.
Alot of map/level chunks seem to be fine.

Yeah the texture assignment will currently fail in two cases :
-the mesh doesn't have a material chunk mentionning textures. This is the case of this 142 file and other meshes used for vfx and such. My guess is that they uses some shaders that don't make use of textures or vertex colors and other things to make them look the way they do ingame. If you find a texture whose name would suggest that it should be used by this 142 model though let me know but I don't think there would be.
-the texture fails to load due to the format not being implemented yet, and end up displaying a white placeholder, this will progressively get solved as more formats are added for textures. I can't really give an ETA for more texture support though, I find working on these to be very boring...

> Reply from 09williamsad ↑Sun Oct 10, 2021 2:33 am at Sun Oct 10, 2021 2:33 am
>
> 
The Noesis debug log has alot of this:
Code: Select allDetected file type: Metroid dread
-texnorepfn parameter accepted.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_0_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_1_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_2_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_3_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_4_material'...Failed.
Reading 'C:\Users\Adam\Downloads\Metroid Dread\players\samus\\mesh_5_material'...Failed.

Yeah you can safely ignore these, it just happens when the material is "empty", so in the cases above.

But yeah keep in mind that material support is hacky since I can't do much better than this (unless I'm missing something) due to the way they're referenced, we'd need to know the actual filenames of the file extracted by the pkg so that would imply getting their hash function/making a hook to grab them.
This is also the reason why I can't add animation support : I have the format completely figured out but the joints are referenced by hashes of their names it seems, which aren't present in the model file. So without the hash function I can't add it.
## Post #39
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-09T19:17:29+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 10:30 pm at Sat Oct 09, 2021 10:30 pm
>
> 
This new update adds basic auto texture assigning. When working, if you load a model the script will load the associated textures and apply them directly (don't forget to cycle blend if you don't see anything in the preview) :

Make sure to have the new associated .txt file next to the script. It's basically used as a dictionnary to grab the full paths of the textures since the mmdl only have their names. The game seems to do everything with hashes so I can't do better without knowing the hash function, unless I'm missing something.

Anyways, to make it work :
-set your dump path at the top of the .py file
-set the scanning option to True
-vertex colors screw up some of the models since they're probably not meant to be used during rendering, set the option to load them to false to make sure you have a correct preview (especially for environment models)

That's it, you just have to set it once, then you can just load the models as usual, the script will do the rest.

I can't get it to work... I set the address were I have the .bctex files but nothing happens.. Do I need to move them to the same folder as the .mmdl files?
## Post #40
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-09T19:24:30+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sun Oct 10, 2021 3:17 am at Sun Oct 10, 2021 3:17 am
>
> 
I can't get it to work... I set the address were I have the .bctex files but nothing happens.. Do I need to move them to the same folder as the .mmdl files?

You need to give the path where the "textures" folder is located (next to "gui", "packs" etc) after you dumped the game. It won't work if you moved the .bctex files if that's what you mean since their path is hardcoded in the files.
## Post #41
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2021-10-09T19:25:30+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Does anyone know if the textures at textures\actors\characters\samus_facial\models\textures are used?
i can't find the meshes for them in the samus pkg.
## Post #42
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-09T19:33:44+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sun Oct 10, 2021 3:24 am at Sun Oct 10, 2021 3:24 am
>
> 
Enderfacio wrote: ↑Sun Oct 10, 2021 3:17 am
I can't get it to work... I set the address were I have the .bctex files but nothing happens.. Do I need to move them to the same folder as the .mmdl files?


You need to give the path where the "textures" folder is located (next to "gui", "packs" etc) after you dumped the game. It won't work if you moved the .bctex files if that's what you mean since their path is hardcoded in the files.

Yes this is were I have the dumped files: 
dumpPath = r"H:\Metroid\Extracted_NCA\romfs"

And I'm loading the .mmdl files from the same dumped location:
H:\Metroid\Extracted_NCA\romfs\packs\players
But I don't know why is not working
## Post #43
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-09T19:35:26+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from CosmicDreams ↑Sun Oct 10, 2021 3:25 am at Sun Oct 10, 2021 3:25 am
>
> 
Does anyone know if the textures at textures\actors\characters\samus_facial\models\textures are used?
i can't find the meshes for them in the samus pkg.

The meshes do not have useful names, just number IDs.
## Post #44
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-09T19:40:09+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sun Oct 10, 2021 3:33 am at Sun Oct 10, 2021 3:33 am
>
> 
Yes this is were I have the dumped files: 
dumpPath = r"H:\Metroid\Extracted_NCA\romfs"

And I'm loading the .mmdl files from the same dumped location:
H:\Metroid\Extracted_NCA\romfs\packs\players
But I don't know why is not working

That looks correct, did you also set the option below to True ? After you did this did you save the file then close/reopen Noesis or reloaded the plugins (Tools -> Reload) for the changes to be applied ?
## Post #45
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2021-10-09T19:40:38+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from 09williamsad ↑Sun Oct 10, 2021 3:35 am at Sun Oct 10, 2021 3:35 am
>
> 
CosmicDreams wrote: ↑Sun Oct 10, 2021 3:25 am
Does anyone know if the textures at textures\actors\characters\samus_facial\models\textures are used?
i can't find the meshes for them in the samus pkg.


The meshes do not have useful names, just number IDs.

Yeah i noticed they don't. I went through all the ones in the samus pkg and none had meshes that looked like they used the textures in that folder. 
If there is a mesh that uses them somewhere i want it because it seems like they're textures for her helmet but with transparent glass to see her face.
## Post #46
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2021-10-09T19:58:12+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Okay i found it in s090_skybase.pkg as 00000012.MMDL
## Post #47
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-09T20:01:13+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sun Oct 10, 2021 3:40 am at Sun Oct 10, 2021 3:40 am
>
> 
Enderfacio wrote: ↑Sun Oct 10, 2021 3:33 am
Yes this is were I have the dumped files: 
dumpPath = r"H:\Metroid\Extracted_NCA\romfs"

And I'm loading the .mmdl files from the same dumped location:
H:\Metroid\Extracted_NCA\romfs\packs\players
But I don't know why is not working  


That looks correct, did you also set the option below to True ? After you did this did you save the file then close/reopen Noesis or reloaded the plugins (Tools -> Reload) for the changes to be applied ?

Yes is set to True. I'm sharing my file in case there is something wrong with it:
[https://drive.google.com/file/d/1UtgjDl ... sp=sharing](https://drive.google.com/file/d/1UtgjDlUv9E8NBHHFKHDxWkuOHMxSgWsb/view?usp=sharing)
## Post #48
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-09T20:16:49+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sun Oct 10, 2021 4:01 am at Sun Oct 10, 2021 4:01 am
>
> 
Yes is set to True. I'm sharing my file in case there is something wrong with it:
https://drive.google.com/file/d/1UtgjDl ... sp=sharing

That should work, did you put your the .py file in the plugins/python folder in Noesis ? And the dreadMap.txt there too ?
## Post #49
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-09T20:25:09+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sat Oct 09, 2021 3:46 pm at Sat Oct 09, 2021 3:46 pm
>
> 
kees wrote: ↑Sat Oct 09, 2021 8:30 am
we got an issue with the mapping of the materials. i dont know how your script works joshka but there are more than 1 material assigned to a mesh. i assigned the body texture and noticed the shoulders were off. i overlayed the UVmap over the head one for the shoulders. and it seems to fit right.  when earlier tried the varia suit i noticed some funkyness with the textures in some places being off. could this be the culpred? 

in the meantime im gonna collect all the textures base ones i can and make a zip file to put in here and report an issue on the github.

***edit*** here is the link with the file. it should have the material ajusted for it (only included the ones i showed the issue with to keep size down and it shows enough anyway). not sure if it will be any help but here it is. also ill refrain from sending it on the github since i see youre still updating it so im not posting issues when youre already at it probably fixing it 
https://www.filemail.com/d/rrrbaphcweqbjyz

***edit2*** the new script for noesis works good and the vertex colors are getting picked up so! the only thing is that material issue but i know that happend right before i posted that.


The meshes are put together based on their original names, I didn't try to assign textures so far but it should work correctly. Enderfacio managed to get it right it seems.

cause i did include a file that had to do with the shoulders applied with the difrent material to show it would be the difrent texture all together. but the script back then didnt load a second material on the body for it. ive yet to redo the rip and testing of it but am struggling to get the textures up and running with the new version of the script. am probably missing something

***edit*** got it it was just a bit wierd before cause my dump doesnt come in a Romfs folder but after a couple tries got the routhe right

***edit2*** forgot to say it now links the material to a seperate node but correctly so that is fixed now thanks so much joshka and m1 !
## Post #50
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-09T20:48:36+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sun Oct 10, 2021 4:16 am at Sun Oct 10, 2021 4:16 am
>
> 
Enderfacio wrote: ↑Sun Oct 10, 2021 4:01 am
Yes is set to True. I'm sharing my file in case there is something wrong with it:
https://drive.google.com/file/d/1UtgjDl ... sp=sharing


That should work, did you put your the .py file in the plugins/python folder in Noesis ? And the dreadMap.txt there too ?

Yes, I can load the .mmdl models thanks to the fmt_mmdl.py file you made, but somehow it doesn't link the 3d models with the textures. I don't know what else to try
## Post #51
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-09T21:00:36+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sun Oct 10, 2021 4:48 am at Sun Oct 10, 2021 4:48 am
>
> 
Yes, I can load the .mmdl models thanks to the fmt_mmdl.py file you made, but somehow it doesn't link the 3d models with the textures. I don't know what else to try

You saved this file and put it next to fmt_mmdl.py right ? [https://raw.githubusercontent.com/Josch ... eadMap.txt](https://raw.githubusercontent.com/Joschuka/fmt_mmdl/main/dreadMap.txt) 
If so grab this version, replace your previous file, reload Noesis and then send me a screenshot of the debug log after you load a model :


 fmt_mmdl.zip
(5.18 KiB) Downloaded 30 times
## Post #52
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-09T21:23:44+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sun Oct 10, 2021 4:48 am at Sun Oct 10, 2021 4:48 am
>
> 
Joschka wrote: ↑Sun Oct 10, 2021 4:16 am
Enderfacio wrote: ↑Sun Oct 10, 2021 4:01 am
Yes is set to True. I'm sharing my file in case there is something wrong with it:
https://drive.google.com/file/d/1UtgjDl ... sp=sharing


That should work, did you put your the .py file in the plugins/python folder in Noesis ? And the dreadMap.txt there too ?


Yes, I can load the .mmdl models thanks to the fmt_mmdl.py file you made, but somehow it doesn't link the 3d models with the textures. I don't know what else to try

if need be just copy over the folder location when yorue in the root of your gamedump like this. just copy that adress and just post that. and ill make another package for you. but at least how i got it to work is that python plugin and the text file in that plugin location on noesis like before. then go into edit mode on notepad in the python file and paste taht adress there in between the brackets. at least thats how i got it to work so i think that explains that joshka? forgot to add picture of the brackets oops but it should be row 9 in notepad ++

***edit *** got it to work but there is an issue it doesnt grab some of the normals from samus's cannon (samuscannon_nm) but ill rip those manually for right now.

oh also joshka when put into blender it links the file to a location in the noesis dump and not where it has exported originally. and if you export it as png it still does .dds aswell. just a nitpick but thought id mention.
[Location Raws.jpg](https://xentaxbackup.github.io/file/20993_Location Raws.jpg)
## Post #53
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-09T22:45:55+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sun Oct 10, 2021 5:00 am at Sun Oct 10, 2021 5:00 am
>
> 
Enderfacio wrote: ↑Sun Oct 10, 2021 4:48 am
Yes, I can load the .mmdl models thanks to the fmt_mmdl.py file you made, but somehow it doesn't link the 3d models with the textures. I don't know what else to try


You saved this file and put it next to fmt_mmdl.py right ? https://raw.githubusercontent.com/Josch ... eadMap.txt 
If so grab this version, replace your previous file, reload Noesis and then send me a screenshot of the debug log after you load a model :
fmt_mmdl.zip

I did it like 20 times or more and then the debug log screen show up again, so now I can send this screenshot of the error (got to say now some textures appear)
[DebugLog.png](https://xentaxbackup.github.io/file/20994_DebugLog.png)
## Post #54
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-09T22:53:41+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Ok it kinda works now. I just hit the Cycle bend button a lot of times and this results shows up. Some textures ares still missing
[results.png](https://xentaxbackup.github.io/file/20999_results.png)
## Post #55
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-09T22:54:56+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Turns out that exporting the textures in .jpg is the best option. i made some renders with Keyshot:
[Prueba_MetroidDread.848.jpg](https://xentaxbackup.github.io/file/21001_Prueba_MetroidDread.848.jpg)
## Post #56
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-09T23:39:37+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Enderfacio ↑Sun Oct 10, 2021 6:54 am at Sun Oct 10, 2021 6:54 am
>
> 
Turns out that exporting the textures in .jpg is the best option. i made some renders with Keyshot:

its cause the alpha map is there it acts like that since they probably use that as an emission map. i just go in gimp and edit that map out. so the bc map is also the albedo aswell as the emission mapping

***Edit*** tested it out yes it is the Emission map
## Post #57
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-10T03:50:45+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

there seem to be more texture formats. earlier went through the gui textures for the menus and there are some being borked. aswell as the power suits lockonmissile textures they seem to be compleetly white aswell as some of the gui ones (and some other model ones too). thought before it was a co incidence but it doesnt seem to be that anymore right now appart from some textures not being nabbed at all. the texture grabbing at least in testing. 00000003 in samus's file refused to get the icemissles and some of the other AT textures. and then some samples of the menu and the lockonmissile file.

ill do the old bms testing to see if i can find out a format in the meantime

***edit*** im doing it with V2 since it just gives me smoll info but am doing the recommended format first thought nothing. then toggled the alpha and i see corrupted texture as its a wrong format like normally expected. no wonder noesis earlier was spitting errors. so imma keep searching and trying to find but thats 1 awnser

***edit*** nope i just had swizzle off. idiot. but still its wierd how it was a complete white from exporting beforehand. the format is right. but decompressing meight be difrent. i got a right texture out of the file with decompressing it with dds and then running it through rawtex lemme make a new post and post some files to show what i mean (im having throuble posting more than 1 file per post)
[lockonmissile textures bctex.zip](https://xentaxbackup.github.io/file/21004_lockonmissile textures bctex.zip)
## Post #58
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-10T04:25:25+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

here are the new ones. formats work fine on rawtex when decompressed somehow. just thought it shouldt be difrent out of noesis but it somehow is??? im so confused. i used v2 bms script just for clearification with same settings on rawtex. BC3 for BC and AT and BC5U for the nm textures (with switch swizzle). only sending BC cause upload limit
[lockonmissle Noesis VS BMS Rawtex.zip](https://xentaxbackup.github.io/file/21005_lockonmissle Noesis VS BMS Rawtex.zip)
## Post #59
- Username: ByStander23
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 08, 2016 2:31 pm
- Post datetime: 2021-10-10T07:45:56+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Little off-topic:
Joschka, Will you add support for Metroid:SR in the near future?
## Post #60
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-10T07:59:22+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Metroid Dread FBX models, dds textures and ogg audio has been added to my archive.
Some of the textures are broken, I will reconvert once the script is updates.

I cannot post the link here due to site policy, but if you google my username you should be able to find it.
## Post #61
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-10T09:53:14+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from kees ↑Sun Oct 10, 2021 5:23 am at Sun Oct 10, 2021 5:23 am
>
> 
***edit *** got it to work but there is an issue it doesnt grab some of the normals from samus's cannon (samuscannon_nm) but ill rip those manually for right now.

Ah yes it seems to grab the _at texture instead, I guess the material chunk doesn't have a consistent layout...

> Reply from kees ↑Sun Oct 10, 2021 5:23 am at Sun Oct 10, 2021 5:23 am
>
> 
oh also joshka when put into blender it links the file to a location in the noesis dump and not where it has exported originally. and if you export it as png it still does .dds aswell. just a nitpick but thought id mention.

Yeah that's the expected behaviour, this way you get a self contained asset if that makes sense. And yeah the additionnal PNG export will have dds + PNG, since it's a built-in Noesis feature I can't prevent that I think. However if you load textures individually and export or use the batch export feature you'll be able to export as PNG only if you want.

> Reply from Enderfacio ↑Sun Oct 10, 2021 6:54 am at Sun Oct 10, 2021 6:54 am
>
> 
Turns out that exporting the textures in .jpg is the best option. i made some renders with Keyshot:

Looking good !

> Reply from kees ↑Sun Oct 10, 2021 11:50 am at Sun Oct 10, 2021 11:50 am
>
> 
there seem to be more texture formats. earlier went through the gui textures for the menus and there are some being borked. aswell as the power suits lockonmissile textures they seem to be compleetly white aswell as some of the gui ones (and some other model ones too).

Yes there are buggy/unsupportd texture formats, that will end up white. Support for these would have to be added to the plugin.

> Reply from ByStander23 ↑Sun Oct 10, 2021 3:45 pm at Sun Oct 10, 2021 3:45 pm
>
> 
Little off-topic:
Joschka, Will you add support for Metroid:SR in the near future?

I don't have a particular interest for this game so most likely not, M-1 may do it though maybe (or someone else, the formats are close so you can follow the code and adapt it). 

Talking about this, I'd just like to mention a few things : 
-I don't have interest in digging much more into Dread, I only reversed the model format "for fun" and decided to make a quick and dirty script for it so people interested in this game could study/check the assets. So aside from a few more hypothetical fixes don't expect much more from me at least, I'm busy with other projects and will probably get back to them soon.
-KillZ already supported the embedded xtx format in the bctex files, so he added support for the Dread texture format in the Switch Toolbox. So if some textures fail in Noesis, you can use the [https://github.com/KillzXGaming/Switch-Toolbox](https://github.com/KillzXGaming/Switch-Toolbox) to grab them. Considering this is a thing I'll probably won't bother with adding more formats myself. 
-Contributions/PRs are welcome if you want to fix/improve the script, that's why I put it on github [https://github.com/Joschuka/fmt_mmdl](https://github.com/Joschuka/fmt_mmdl) . In particular if you want to add more texture formats, this is the section that will interest you : [https://github.com/Joschuka/fmt_mmdl/bl ... #L162-L193](https://github.com/Joschuka/fmt_mmdl/blob/main/fmt_mmdl.py#L162-L193)

That's pretty much it, I hope the script was somewhat useful to you. I'll probably try to fix the few remaining models not loading and then I'll move on.
## Post #62
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-10T13:07:18+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sun Oct 10, 2021 5:53 pm at Sun Oct 10, 2021 5:53 pm
>
> 


Talking about this, I'd just like to mention a few things : 
-I don't have interest in digging much more into Dread, I only reversed the model format "for fun" and decided to make a quick and dirty script for it so people interested in this game could study/check the assets. So aside from a few more hypothetical fixes don't expect much more from me at least, I'm busy with other projects and will probably get back to them soon.
-KillZ already supported the embedded xtx format in the bctex files, so he added support for the Dread texture format in the Switch Toolbox. So if some textures fail in Noesis, you can use the https://github.com/KillzXGaming/Switch-Toolbox to grab them. Considering this is a thing I'll probably won't bother with adding more formats myself. 
-Contributions/PRs are welcome if you want to fix/improve the script, that's why I put it on github https://github.com/Joschuka/fmt_mmdl . In particular if you want to add more texture formats, this is the section that will interest you : https://github.com/Joschuka/fmt_mmdl/bl ... #L162-L193

That's pretty much it, I hope the script was somewhat useful to you. I'll probably try to fix the few remaining models not loading and then I'll move on.

Dude thank you so much for all your help!! Since I don't recieve my copy of Metroid Dread yet I don't want to spoiler the game by checking the assets but all I wanted it for now is the Samus suit 3d model so thank you for your files and the patience to help us
## Post #63
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-11T04:00:05+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Sun Oct 10, 2021 5:53 pm at Sun Oct 10, 2021 5:53 pm
>
> 

Talking about this, I'd just like to mention a few things : 
-I don't have interest in digging much more into Dread, I only reversed the model format "for fun" and decided to make a quick and dirty script for it so people interested in this game could study/check the assets. So aside from a few more hypothetical fixes don't expect much more from me at least, I'm busy with other projects and will probably get back to them soon.
-KillZ already supported the embedded xtx format in the bctex files, so he added support for the Dread texture format in the Switch Toolbox. So if some textures fail in Noesis, you can use the https://github.com/KillzXGaming/Switch-Toolbox to grab them. Considering this is a thing I'll probably won't bother with adding more formats myself. 
-Contributions/PRs are welcome if you want to fix/improve the script, that's why I put it on github https://github.com/Joschuka/fmt_mmdl . In particular if you want to add more texture formats, this is the section that will interest you : https://github.com/Joschuka/fmt_mmdl/bl ... #L162-L193

That's pretty much it, I hope the script was somewhat useful to you. I'll probably try to fix the few remaining models not loading and then I'll move on.

serieusly. so far ive been able to get the dread suit. emmy and some other things. its workable mostly appart from some small things. but its compleetly understandable. and i want to say aswell serieusly thank you and m1 for doing so much already! sorry if i ever seemed a bit nitpicky or a biut rude in my words. just wanted to give as much feedback as possible with it so i apologise if that was ever the case.  doing game ripping/modding should always be about fun so all your points are valid and compleetly understandable! there is a lot we can do already and the groundwork should be there for others to continue afterward. so once again serieusly thank you so much for all the work you 2 have done it shouldn't go underappreciated. 

and serieusly thank you everyone from the bottom of my heart that worked on this and tried to help how they could to figure this out. its been a while since ive seen a community come together to work on a game to pull it appart.
## Post #64
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-11T11:15:42+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from 09williamsad ↑Sat Oct 09, 2021 8:18 pm at Sat Oct 09, 2021 8:18 pm
>
> 
Models reconverted with the new script, 8333 total with 40 that did not convert, list attached.

Version 0.5 has some workaround to load the remaining 40 models, there's some weird issue with the joint indices exceeding the joint maps length for some meshes that I'm confused about but now they'll load at least.
Aside from a few meshes being misplaced all models should now load hopefully.

> Reply from kees ↑Mon Oct 11, 2021 12:00 pm at Mon Oct 11, 2021 12:00 pm
>
> 
sorry if i ever seemed a bit nitpicky or a biut rude in my words. just wanted to give as much feedback as possible with it so i apologise if that was ever the case.

Don't worry I never read your messages as rude or anything, I understood you genuinely wanted to help with bug reporting and making the script better, I appreciate it a lot.

> Reply from Enderfacio ↑Sun Oct 10, 2021 9:07 pm at Sun Oct 10, 2021 9:07 pm
>
> 
Dude thank you so much for all your help!! Since I don't recieve my copy of Metroid Dread yet I don't want to spoiler the game by checking the assets but all I wanted it for now is the Samus suit 3d model so thank you for your files and the patience to help us

> Reply from kees ↑Mon Oct 11, 2021 12:00 pm at Mon Oct 11, 2021 12:00 pm
>
> 
serieusly. so far ive been able to get the dread suit. emmy and some other things. its workable mostly appart from some small things. but its compleetly understandable. and i want to say aswell serieusly thank you and m1 for doing so much already!   doing game ripping/modding should always be about fun so all your points are valid and compleetly understandable! there is a lot we can do already and the groundwork should be there for others to continue afterward. so once again serieusly thank you so much for all the work you 2 have done it shouldn't go underappreciated. 

and serieusly thank you everyone from the bottom of my heart that worked on this and tried to help how they could to figure this out. its been a while since ive seen a community come together to work on a game to pull it appart.

Thank you, I'm glad that this noesis script was helpful to you guys, I'd also like to thank you all for the bug reporting and feedback. Also thanks a lot to spiritovod and KillZ for their research help to get some basic texture support quickly.
Hopefully someone can pick up the torch later, unless I broke something with version 0.5 this will probably be my last update. Time for me to actually play the game now instead of reversing it !
## Post #65
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-11T11:57:13+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Ok I lied, version 0.6 will actually be my last heh

This new version automatically takes the rgb data to make the actual diffuse texture and the alpha channel to make the emissive one. No need for you to cycle blend anymore in the preview and the maps will be exported already processed accordingly.
The diffuse texture name will still be texName_bc.dds, the created emissive texture name will be named texName_emi.dds. That should speed up the workflow instead of having to split channels everytime, on Blender, photoshop or whatever.

EDIT : Well I pushed a bunch of additionnal texture formats and fixes, version 0.7 now loads a lot of the bctex without problem now. For the last that don't work you can use the Switch toolbox or maybe I'll poke at it more later
## Post #66
- Username: Jhyrachy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 29, 2018 12:00 am
- Post datetime: 2021-10-12T23:19:55+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Hello everyone!

Does anyone managed to make some use of the .manm files?

I'm trying to pose the model for 3d printing (after applying a displacement map to increase details) and would be cool to use a game pose.

Thanks!
## Post #67
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2021-10-13T07:17:55+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Jhyrachy ↑Wed Oct 13, 2021 7:19 am at Wed Oct 13, 2021 7:19 am
>
> 
Hello everyone!

Does anyone managed to make some use of the .manm files?

I'm trying to pose the model for 3d printing (after applying a displacement map to increase details) and would be cool to use a game pose.

Thanks!

think its better to go with posing manually cause of how the anims are made i fear they wont be ripped soon. also they meight not be exactly the poses you want. plus its good practice to not limit yourself with only premade poses. have some fun with it and see what you can do
## Post #68
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-13T08:08:02+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Jhyrachy ↑Wed Oct 13, 2021 7:19 am at Wed Oct 13, 2021 7:19 am
>
> 
Hello everyone!

Does anyone managed to make some use of the .manm files?

I'm trying to pose the model for 3d printing (after applying a displacement map to increase details) and would be cool to use a game pose.

Thanks!

I figured out the manm files at 99%, the problem is that the joints are referenced by name hashes, which are not present in the model file. So basically I have the keyframe data but have no clue to which joint it belongs due to this.
I'd need someone to decompile/debug the game and give me the hash function, otherwise animation support can't be added.
## Post #69
- Username: Jhyrachy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 29, 2018 12:00 am
- Post datetime: 2021-10-13T08:21:01+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Wed Oct 13, 2021 4:08 pm at Wed Oct 13, 2021 4:08 pm
>
> 
I figured out the manm files at 99%, the problem is that the joints are referenced by name hashes, which are not present in the model file. So basically I have the keyframe data but have no clue to which joint it belongs due to this.
I'd need someone to decompile/debug the game and give me the hash function, otherwise animation support can't be added.

How many joints are there?

It could be painfull, but  we could map them by hand.

> Reply from kees ↑Wed Oct 13, 2021 3:17 pm at Wed Oct 13, 2021 3:17 pm
>
> 
think its better to go with posing manually cause of how the anims are made i fear they wont be ripped soon. also they meight not be exactly the poses you want. plus its good practice to not limit yourself with only premade poses. have some fun with it and see what you can do

Ye, I know, but I can do as I made with pokémon, starting with a premade pose and then modify it
## Post #70
- Username: Xenphex
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 02, 2021 10:47 am
- Post datetime: 2021-10-13T16:31:43+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Hi, i can't get it Noesis to load the textures, i have fmt_mmdl.py and dreadMap.txt and the same folder, i did the setup for the path dumpPath = r"" where all the .MMDL and .bctex are, and tried changing cycle blend but the model still doesn't show the textures.

Any ideas on what can i try? Noesis version 4.458


Thanks in advance and thank you so much for all the work on the scrips / plugins. Greetings.
## Post #71
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-10-13T17:00:29+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Xenphex ↑Thu Oct 14, 2021 12:31 am at Thu Oct 14, 2021 12:31 am
>
> 
Hi, i can't get it Noesis to load the textures, i have fmt_mmdl.py and dreadMap.txt and the same folder, i did the setup for the path dumpPath = r"" where all the .MMDL and .bctex are, and tried changing cycle blend but the model still doesn't show the textures.

Any ideas on what can i try? Noesis version 4.458


Thanks in advance and thank you so much for all the work on the scrips / plugins. Greetings.

In the Noesis python script, set bTextureScanning = True
If there is still no texture then that model may not work with the scripts material/texture function.
## Post #72
- Username: Xenphex
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 02, 2021 10:47 am
- Post datetime: 2021-10-13T17:51:47+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from 09williamsad ↑Thu Oct 14, 2021 1:00 am at Thu Oct 14, 2021 1:00 am
>
> 
Xenphex wrote: ↑Thu Oct 14, 2021 12:31 am
Hi, i can't get it Noesis to load the textures, i have fmt_mmdl.py and dreadMap.txt and the same folder, i did the setup for the path dumpPath = r"" where all the .MMDL and .bctex are, and tried changing cycle blend but the model still doesn't show the textures.

Any ideas on what can i try? Noesis version 4.458


Thanks in advance and thank you so much for all the work on the scrips / plugins. Greetings.


In the Noesis python script, set bTextureScanning = True
If there is still no texture then that model may not work with the scripts material/texture function.

I tried that but i got an error, but that was before i had all the textures in the same folder and i forgot to try again, let me try.

Yeah, tried and i keep getting the same error.



Noesis tracebak.jpg (28.92 KiB) Viewed 153 times



Also, i'm trying in Blender and when i try yo apply the textures all looks wrong, i exported as .jpg and tried Flip UV too, but nothing, keep looking like it has a wrong UV.
## Post #73
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-15T07:43:01+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Jhyrachy ↑Wed Oct 13, 2021 4:21 pm at Wed Oct 13, 2021 4:21 pm
>
> 
How many joints are there?

It could be painfull, but  we could map them by hand.

I don't remember but I think Samus had like 130 or so. Yeah it's possible but honestly I'm not interested in implementing hacky anim support with a whole hash to name map just for Samus, especially since I had to make an external file for materials already. Once the hash function is figured out full anim support for everything will be possible hopefully.

> Reply from Xenphex ↑Thu Oct 14, 2021 1:51 am at Thu Oct 14, 2021 1:51 am
>
> 
Noesis tracebak.jpg

Also, i'm trying in Blender and when i try yo apply the textures all looks wrong, i exported as .jpg and tried Flip UV too, but nothing, keep looking like it has a wrong UV.

This error message means that your path is incorrect. The plugin expects the path where the romfs has been dumped, so the one with "textures" etc folders, make sure that's the case, not something like putting bctex and mmdl in arbitrary folders.
For UVs not sure, it works for a lot of people so maybe you didn't use the correct textures
## Post #74
- Username: Azarae
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 16, 2021 9:35 pm
- Post datetime: 2021-10-16T13:40:45+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

I'm having the same issue with the textures not loading. Unsure why. Folder names have not been changed. Can you assign textures manually in Noesis?

Also tried in blender, but manually assigning textures is 100% off, with no combination working correctly. Will it be possible to get these models already set up with Blender?

I'm mostly wanting to get this working so some art can be done from a specific perspective, but without the textures it just isn't going to work.

Side note: how does one go about posing the skeleton?
## Post #75
- Username: rainmanbk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 13, 2021 6:09 am
- Post datetime: 2021-10-16T16:39:14+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

I had a question, does anyone know what channel the _at texture fills? I can't seem to figure it out. For example the powerbody_at.dds texture. Attached is a screenshot of it.



Screenshot_3.png (165.01 KiB) Viewed 87 times
## Post #76
- Username: thehypetrain899
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 17, 2021 12:07 pm
- Post datetime: 2021-10-17T04:31:20+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Hey 

I'm quite new to this stuff and I really want to animate these models

Would It Be ok for someone to give me a quick rundown on how you have done it?
Thanks in Advance.
## Post #77
- Username: velencourte
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 12, 2021 7:35 pm
- Post datetime: 2021-10-17T12:40:16+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from rainmanbk ↑Sun Oct 17, 2021 12:39 am at Sun Oct 17, 2021 12:39 am
>
> 
I had a question, does anyone know what channel the _at texture fills? I can't seem to figure it out. For example the powerbody_at.dds texture. Attached is a screenshot of it.
Screenshot_3.png

I'm not sure about the red channel, but the green is roughness and blue is metallic.
## Post #78
- Username: EIA86
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 17, 2021 2:13 pm
- Post datetime: 2021-10-17T21:00:27+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Hello All,

This is a bit off topic but I am trying to make a randomizer for this game and am running into some issues with the PKG file format. So far I was able to successfully swap one Emmy item with another but it only worked because the item names shared the same size. If the size of the file changes at all it crashes the game when the area loads.

The Emmy items are within the subareapack_global.pkg files within each map and start with "ITEM_" in their names. I tried to use the PKG tool to unpack the Cave map's file then searched within them and found the ITEM code within 00001228.MSAD but when I change it then try to follow the steps in the QuickBMS guide to repackage it seems to ignore the changed file and does nothing when using the -w -r option.

I am fairly new to using QuickBMS to repackage things so any alternatives, guides, or help would be wonderful.
## Post #79
- Username: Enderfacio
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 01, 2019 12:35 am
- Post datetime: 2021-10-18T00:16:17+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Xenphex ↑Thu Oct 14, 2021 1:51 am at Thu Oct 14, 2021 1:51 am
>
> 


Also, i'm trying in Blender and when i try yo apply the textures all looks wrong, i exported as .jpg and tried Flip UV too, but nothing, keep looking like it has a wrong UV.

No need for flip the UV, the textures are exported exaclty as they go on the model. Try applying the right texture to the right body part, there is one for the body and head, other for the arms an another for the arm cannon. Maybe you are switching them and that's why the look wrong.
## Post #80
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-18T13:04:29+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from thehypetrain899 ↑Sun Oct 17, 2021 12:31 pm at Sun Oct 17, 2021 12:31 pm
>
> 
Hey 

I'm quite new to this stuff and I really want to animate these models

Would It Be ok for someone to give me a quick rundown on how you have done it?
Thanks in Advance.

Dump the nsp from your switch, dump the romfs from it using Yuzu (the easiest way if you're not familiar with the process). Then unpack the pkg using the switch toolbox or spiritovod's bms script. Finally open the models/textures with the Noesis script.

> Reply from EIA86 ↑Mon Oct 18, 2021 5:00 am at Mon Oct 18, 2021 5:00 am
>
> 
Hello All,

This is a bit off topic but I am trying to make a randomizer for this game and am running into some issues with the PKG file format. So far I was able to successfully swap one Emmy item with another but it only worked because the item names shared the same size. If the size of the file changes at all it crashes the game when the area loads.

The Emmy items are within the subareapack_global.pkg files within each map and start with "ITEM_" in their names. I tried to use the PKG tool to unpack the Cave map's file then searched within them and found the ITEM code within 00001228.MSAD but when I change it then try to follow the steps in the QuickBMS guide to repackage it seems to ignore the changed file and does nothing when using the -w -r option.

I am fairly new to using QuickBMS to repackage things so any alternatives, guides, or help would be wonderful.

Hi, you can probably use the following unpacker/repacker [https://github.com/UltiNaruto/PKGTool](https://github.com/UltiNaruto/PKGTool) didn't try it myself though

Other than that great news : the hash function has been figured out and posted by someone ([https://twitter.com/MrCheeze_/status/14 ... 3794457600](https://twitter.com/MrCheeze_/status/1448360873794457600))

So that means that some filenames will be obtainable instead of having numbers for the pkg. And also it was the only thing I was missing for animation support : 

Expect an update adding it during the week
## Post #81
- Username: EIA86
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 17, 2021 2:13 pm
- Post datetime: 2021-10-19T04:52:28+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Thanks for the suggestion Joschka.

The -o option doesn't seem to be working as intended on that tool. It is ignoring the line after it and just placing all output in either a folder named -o or a -o.pkg file.

That aside altering one of the .bmsad files then repackaging still results in a crash. Are there offsets or field length parameters within the bmsad files I need to be changing?

The smallest one to goof around with is within the Shipyard map area's subareapack_global.pkg and is called F425A8B81D1BBC83.bmsad when extracted. If I change the ITEM_WEAPON_POWER_BOMB to ITEM_SPACE_JUMP then repackage the game will crash while attempting to load the save file.
## Post #82
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-21T18:57:05+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from EIA86 ↑Tue Oct 19, 2021 12:52 pm at Tue Oct 19, 2021 12:52 pm
>
> 
Thanks for the suggestion Joschka.

The -o option doesn't seem to be working as intended on that tool. It is ignoring the line after it and just placing all output in either a folder named -o or a -o.pkg file.

That aside altering one of the .bmsad files then repackaging still results in a crash. Are there offsets or field length parameters within the bmsad files I need to be changing?

The smallest one to goof around with is within the Shipyard map area's subareapack_global.pkg and is called F425A8B81D1BBC83.bmsad when extracted. If I change the ITEM_WEAPON_POWER_BOMB to ITEM_SPACE_JUMP then repackage the game will crash while attempting to load the save file.

Ah sorry I can't help with the tool, I didn't try to do any repacking myself... Maybe you could ask on the Metroid Dread modding discord ?

In other news animation support has been added to the new version 
Simply put the animations you want to extract in a folder and give it to the plugin when asked (can be disabled by the option at the top)

It's recommend to use the switch toolbox to extract the assets now, you'll get a ton of filenames, since the hash function has been figured out some matches have been found. Cheers.
## Post #83
- Username: Gagnetar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 04, 2018 7:20 am
- Post datetime: 2021-10-22T20:32:38+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Wow! this is awesome! I'm so glad that we can look into Dread's assets, I figured after SR not getting really anything that dread would suffer the same fate. The auto texture seems to work great but it seems like it doesn't work on the X Parasites, including the regular X and the Core-X. Is there any chance of adding support for them? I'm not sure if I should add the model here exactly but you can find the X parasite inside the player samus pkg
## Post #84
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-25T11:44:59+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Gagnetar ↑Sat Oct 23, 2021 4:32 am at Sat Oct 23, 2021 4:32 am
>
> 
Wow! this is awesome! I'm so glad that we can look into Dread's assets, I figured after SR not getting really anything that dread would suffer the same fate. The auto texture seems to work great but it seems like it doesn't work on the X Parasites, including the regular X and the Core-X. Is there any chance of adding support for them? I'm not sure if I should add the model here exactly but you can find the X parasite inside the player samus pkg

Now that we have enough filenames I'm probably going to rewrite the material support at some point to make it less hacky so it'll hopefully work then. The temporary solution used right now was implemented because the hash function was unknown.
Taking a few days break from Dread and I'll look into it.
## Post #85
- Username: Gagnetar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 04, 2018 7:20 am
- Post datetime: 2021-10-26T01:14:01+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Excellent, thank you! I'm glad they're actually 3d models. I was scared they were complicated particle effects.
## Post #86
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-10-27T18:51:43+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Here my extractor repo. Files can be extracted with names 

Binary: [here](https://github.com/Ekey/MD.PKG.Tool/releases)
Source: [here](https://github.com/Ekey/MD.PKG.Tool)
## Post #87
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-28T05:17:03+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Ekey ↑Thu Oct 28, 2021 2:51 am at Thu Oct 28, 2021 2:51 am
>
> 
Here my extractor repo. Files can be extracted with names 

Binary: here
Source: here

Thank you ! I think this is the first game for which I see so many extractors, usually people don't like to make these heh
## Post #88
- Username: Unknowni
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 12, 2021 11:21 pm
- Post datetime: 2021-10-30T04:02:41+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Ekey ↑Thu Oct 28, 2021 2:51 am at Thu Oct 28, 2021 2:51 am
>
> 
Here my extractor repo. Files can be extracted with names 

Binary: here
Source: here

Hey there Ekey. I'm really excited to use this. I did have a bit of trouble running it (forgot to command MD.Unpacker with .exe at the end after running the file lol, maybe include that in your example for idiots like me).

But my main question is about the sound effects, which I realize is a bit out of the scope of this thread. I noticed in the Filenames.list file you have all the .wav filenames, but I can't seem to figure out how this would work. The sound effects are stored elsewhere in .bfgrp files. Interestingly they DO have the word "pkg" at the end of each name, but they're .bfgrp files through and through (ex. "_packs_maps_s000_mainmenu_s000_mainmenu_pkg.bfgrp"). I've ripped them myself, all I need is the filenames accurately applied to each individual sound. So is there a function in this program that puts filenames to .bfgrp files yet?

Sorry for being bothersome about something that may be out of the scope of what you're trying to accomplish.
## Post #89
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-10-30T11:57:21+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Unknowni ↑Sat Oct 30, 2021 12:02 pm at Sat Oct 30, 2021 12:02 pm
>
> 
 So is there a function in this program that puts filenames to .bfgrp files yet?

No, there is no such function. I created a list based on manual research files , so it may contain names that are not in the PKG archives.
## Post #90
- Username: Unknowni
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 12, 2021 11:21 pm
- Post datetime: 2021-10-30T16:12:54+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Ekey ↑Sat Oct 30, 2021 7:57 pm at Sat Oct 30, 2021 7:57 pm
>
> 

No, there is no such function. I created a list based on manual research files , so it may contain names that are not in the PKG archives.

 I see. I'll do some more research. Thanks for helping get all the models anyways!
## Post #91
- Username: 8Yaron8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 08, 2018 11:32 pm
- Post datetime: 2021-10-31T14:15:52+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Ekey ↑Thu Oct 28, 2021 2:51 am at Thu Oct 28, 2021 2:51 am
>
> 
Here my extractor repo. Files can be extracted with names 

Binary: here
Source: here

A strange situation in my case, I created a bat file, put this command, entered the path of the archive and where to extract it, but most of the files are sent to the unknown category, and from the extracted ones - small text files and effect models. Could this be due to the fact that in my system the main language is not English? I have previously tried to use the other pkg extractor, which I found earlier in this thread, but it also doesn’t extract all files.
## Post #92
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-31T14:40:54+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from 8Yaron8 ↑Sun Oct 31, 2021 10:15 pm at Sun Oct 31, 2021 10:15 pm
>
> 
Ekey wrote: ↑Thu Oct 28, 2021 2:51 am
Here my extractor repo. Files can be extracted with names 

Binary: here
Source: here


A strange situation in my case, I created a bat file, put this command, entered the path of the archive and where to extract it, but most of the files are sent to the unknown category, and from the extracted ones - small text files and effect models. Could this be due to the fact that in my system the main language is not English? I have previously tried to use the other pkg extractor, which I found earlier in this thread, but it also doesn’t extract all files.

I didn't try Ekey's extractor myself but if you didn't make any mistake then that means that there are missing hashes. Provided you're interested in meshes/textures/anims then you should try this one [https://github.com/UltiNaruto/PKGTool](https://github.com/UltiNaruto/PKGTool) or the STB  [https://github.com/KillzXGaming/Switch-Toolbox](https://github.com/KillzXGaming/Switch-Toolbox) , I know that both of these name a bunch of the graphic assets
## Post #93
- Username: 8Yaron8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 08, 2018 11:32 pm
- Post datetime: 2021-10-31T16:03:43+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Yes, it extracted more files, but there is no single model files.
## Post #94
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-31T17:02:27+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Models are bcmdl.
## Post #95
- Username: 8Yaron8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 08, 2018 11:32 pm
- Post datetime: 2021-10-31T20:28:06+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Alright, I already figured out, subareas packages that I extracted was "additional", they contain animations and particles, the main models of bosses are in the main archive.
## Post #96
- Username: Azarae
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 16, 2021 9:35 pm
- Post datetime: 2021-11-11T23:26:47+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

So are models easily able to be viewed in a 3D program like Blender yet? there's quite a few different zips and archives around; unsure which ones are needed, what is outdated, and what the current progress is.
## Post #97
- Username: velencourte
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 12, 2021 7:35 pm
- Post datetime: 2021-11-12T23:44:03+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Azarae ↑Fri Nov 12, 2021 7:26 am at Fri Nov 12, 2021 7:26 am
>
> 
So are models easily able to be viewed in a 3D program like Blender yet? there's quite a few different zips and archives around; unsure which ones are needed, what is outdated, and what the current progress is.

We've got animation, model, and texture support! You'll need:
A dump of Metroid Dread
A way to extract the .pkg files to get .mmdl files (I like PKGTool: [https://github.com/UltiNaruto/PKGTool](https://github.com/UltiNaruto/PKGTool))
Joschuka's fmt_mmdl plugin for Noesis (found in this thread)
Noesis: [https://richwhitehouse.com/index.php?co ... project=91](https://richwhitehouse.com/index.php?content=inc_projects.php&showproject=91)
A way to export the textures from their .bctex format (Noesis can do this but I highly advise Switch-Toolbox, as Noesis tends to miss the _at textures used for metallic/roughness: [https://github.com/KillzXGaming/Switch-Toolbox/releases](https://github.com/KillzXGaming/Switch-Toolbox/releases))

Unpack the .pkg files, then use the Noesis plugin to open up the assets you want to extract. Export to whatever format you like, and feel free to do whatever you do with them.
## Post #98
- Username: dalekolt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 02, 2021 6:29 am
- Post datetime: 2021-11-23T00:46:47+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

I'm trying to rip the Chozo robot model, but I can only find the regular variation, no gold textures. Is there some kind of color overlay going on, or are the textures hidden somehow?
## Post #99
- Username: TheTitaniumTAC0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 02, 2021 10:02 am
- Post datetime: 2021-12-20T21:37:58+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Hi, Im trying to get a 3D model for the omega cannon but I cant seem to find it in the game files its not listed under any of the weapons or player models that I have seen. Has anybody been able to get the a model of the omega cannon or anyone who would be willing to help find it? Thank you
## Post #100
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-21T06:33:01+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from TheTitaniumTAC0 ↑Tue Dec 21, 2021 5:37 am at Tue Dec 21, 2021 5:37 am
>
> 
Hi, Im trying to get a 3D model for the omega cannon but I cant seem to find it in the game files its not listed under any of the weapons or player models that I have seen. Has anybody been able to get the a model of the omega cannon or anyone who would be willing to help find it? Thank you

From what I recall the omega cannon is hidden by default, set the "showallmeshes" option at the top to true then load up the Samus model.
## Post #101
- Username: TheTitaniumTAC0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 02, 2021 10:02 am
- Post datetime: 2021-12-21T10:33:48+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Thank you! I will give that a shot when I get home. Do I not need to extract any new files for the omega cannon? The only files I found in samus’ textures were her regular cannon. How will Noeisis know which to load?
## Post #102
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-21T10:43:32+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from TheTitaniumTAC0 ↑Tue Dec 21, 2021 6:33 pm at Tue Dec 21, 2021 6:33 pm
>
> 
Thank you! I will give that a shot when I get home. Do I not need to extract any new files for the omega cannon? The only files I found in samus’ textures were her regular cannon. How will Noeisis know which to load?

As long as you have the dump path set correctly (if textures are already loading then you're good), you'll just have to switch the option to True at the top of the script and you'll end up with the omega cannon textured accordingly, on top of the base cannon . 

The extra meshes are used for vfx.
## Post #103
- Username: TheTitaniumTAC0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 02, 2021 10:02 am
- Post datetime: 2021-12-21T21:46:37+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from Joschka ↑Tue Dec 21, 2021 6:43 pm at Tue Dec 21, 2021 6:43 pm
>
> 
TheTitaniumTAC0 wrote: ↑Tue Dec 21, 2021 6:33 pm
Thank you! I will give that a shot when I get home. Do I not need to extract any new files for the omega cannon? The only files I found in samus’ textures were her regular cannon. How will Noeisis know which to load?


As long as you have the dump path set correctly (if textures are already loading then you're good), you'll just have to switch the option to True at the top of the script and you'll end up with the omega cannon textured accordingly, on top of the base cannon . 

The extra meshes are used for vfx.

Okay, So ive gotten the omega cannon to show much like in your screenshot. Is there any way to hide the original cannon? I can see it poking through the bottom of the omega cannon like in your screenshot. coincidentally that's The part I need to see most for what I am trying to do lol. Thanks!
## Post #104
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-12-22T09:28:59+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

> Reply from TheTitaniumTAC0 ↑Wed Dec 22, 2021 5:46 am at Wed Dec 22, 2021 5:46 am
>
> 

Okay, So ive gotten the omega cannon to show much like in your screenshot. Is there any way to hide the original cannon? I can see it poking through the bottom of the omega cannon like in your screenshot. coincidentally that's The part I need to see most for what I am trying to do lol. Thanks!

You can hide the meshes using the Data viewer (Tools -> Data viewer -> Meshes -> whatever mesh -> skip render). Or just export to whatever 3D software and hide it there for a render.
## Post #105
- Username: SneezyWeavile
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 01, 2022 4:45 am
- Post datetime: 2021-12-31T20:50:28+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

How exactly do you use PKGTool? There's no documentation on the Github on how to actually use the program, and I'm a bit lost.
## Post #106
- Username: UltiNaruto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 01, 2022 10:52 pm
- Post datetime: 2022-01-01T14:56:40+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

If you execute PKGTool without any arguments in the command line you get this :

```
-----------------------

Extract : PKGTool -x <input path> [-o <output path>] [-i]
Create : PKGTool -c <input path> [-o <output path>]
```


But yeah I should add that in the readme on github
## Post #107
- Username: SneezyWeavile
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 01, 2022 4:45 am
- Post datetime: 2022-01-17T23:07:39+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

If I run PKGTool.exe, it brings up command prompt and then immediately closes it. Not sure what to do about that.
## Post #108
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2022-01-17T23:26:23+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

You have to run it from the command line. See e.g. [https://www.wikihow.com/Run-an-EXE-File ... and-Prompt](https://www.wikihow.com/Run-an-EXE-File-From-Command-Prompt).
## Post #109
- Username: ramsay6
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 18, 2023 2:28 pm
- Post datetime: 2023-02-18T06:33:54+00:00
- Post Title: Re: Ripping Samus Dread (.pkg file)

Hey guys I know this forum is old, but im wondering if anyone had anyluck exporting the animations as fbx? Im trying to get them ripped myself  but im having difficulties extracting the pkg files. theres something wrong with my pc and I cant run the programs used to extract them.
