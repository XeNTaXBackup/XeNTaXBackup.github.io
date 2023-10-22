## Post #1
- Username: DenniiaLux
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 29, 2021 3:37 am
- Post datetime: 2021-11-06T10:41:18+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

Just wondering if anyone figured out how to rip from GTOG so far as i don't see any forum or anyone really talking about this , and i do wanna get my hands on these models i think they would be great for animations!
## Post #2
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-11-06T14:50:44+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

From what I can see, Marvel's Guardians of the Galaxy is using the Dawn Engine that Deus Ex Mankind Divided used, and a variation of the archive formats that Hitman Absolution used.

Most of the files have the "pc_resourcelib" extention and "BILR" header.
I cannot see any existing tools that are applicable for it.

Samples [https://mega.nz/folder/ySZmhLQZ#SYPlmi42oQL4Mcoxb3W1Xw](https://mega.nz/folder/ySZmhLQZ#SYPlmi42oQL4Mcoxb3W1Xw)
## Post #3
- Username: 4411
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 06, 2019 3:41 pm
- Post datetime: 2021-11-09T17:53:05+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

I see, so from my knowledge point we need to have a tool which can get of the encryption right?
## Post #4
- Username: TheBoq
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 04, 2021 3:58 am
- Post datetime: 2021-11-13T05:04:23+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

Hope to see this developed
## Post #5
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-11-20T18:54:49+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

The game has a few extensions, some files have the extension .pc_headerlib, with a "HLIB" header.
They might be important, there are also some RLIB parts in the HLIB files.

The HLIB files have strings such as:

```
[[assembly:/common/initchunk.streamable.ini].pc_resourcelibdef].pc_headerlib
[assembly:/objects/dxm/interactive_objects/custom/knu/knu_gamora_cut_jump_horizontal_a/knu_gamora_cut_jump_horizontal_a.fbx?/knu_gamora_cut_jump_horizontal_a.prim].pc_prim
[assembly:/sound/wwise/originals/voices/english(us)/game/officialscript/chapter08/9000_mno/c08_9000_os_cnv/c08_9000_os_cnv_a001_gdn_rocket.wav](dialogue_conversion_settings).pc_wem

```


59C94B392FC8A8A354D16F4477D4FA9A.pc_headerlib and 9BEF2077AA4D984AEE24F0F021732317.pc_headerlib contain the majority of paths. Both are around 70 MB large.

Based on the DLC, each pc_headerlib has at least 1 pc_resourcelib and 1 pc_scenemetadata file.

```
88E8BA9946D1EBFF92859CF5C4CE6050.pc_resourcelib =  [[assembly:/scenes/dxm/dlc_scenes/dlc_first_party/dlc_first_party.scene].pc_resourcelibdef](0000).pc_resourcelib
FFD50FC8035B504C1C5C02850A347ACD.pc_headerlib = [[assembly:/scenes/_libs/unlockablecontentkeys_lib/unlockablecontentkeys_lib.scene].pc_resourcelibdef].pc_headerlib

```


these strings are found in the pc_headerlib file.
## Post #6
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2021-11-22T07:44:08+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

This may be of some help: [https://gitlab.com/dvdkon/dxmd_modding](https://gitlab.com/dvdkon/dxmd_modding)

Deus Ex Mankind Divided had .archive files as well though, so we don't need to keep any code related to that. But there is code related to the BILR header and a lot of other things: [https://gitlab.com/dvdkon/dxmd_modding/ ... structs.py](https://gitlab.com/dvdkon/dxmd_modding/-/blob/master/datautils/structs.py)
## Post #7
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-11-25T15:00:10+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

Bump? Anyone made some progress?
## Post #8
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2021-11-25T19:19:20+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

> Reply from Notex ↑Mon Nov 22, 2021 3:44 pm at Mon Nov 22, 2021 3:44 pm
>
> 
This may be of some help: https://gitlab.com/dvdkon/dxmd_modding

Deus Ex Mankind Divided had .archive files as well though, so we don't need to keep any code related to that. But there is code related to the BILR header and a lot of other things: https://gitlab.com/dvdkon/dxmd_modding/ ... structs.py

 this tool not work
## Post #9
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2021-11-25T19:21:44+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

> Reply from lazenes ↑Fri Nov 26, 2021 3:19 am at Fri Nov 26, 2021 3:19 am
>
> 
Notex wrote: ↑Mon Nov 22, 2021 3:44 pm
This may be of some help: https://gitlab.com/dvdkon/dxmd_modding

Deus Ex Mankind Divided had .archive files as well though, so we don't need to keep any code related to that. But there is code related to the BILR header and a lot of other things: https://gitlab.com/dvdkon/dxmd_modding/ ... structs.py


 this tool not work

Well, yeah. I did say it may help. I never said it would work. You would have to modify it so it works.
## Post #10
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2021-12-03T23:08:08+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

I am looking for Programmer Friends to help me I am trying to develop a Tool for this game

[https://github.com/lazenes/PC_Headerlib-Viewer](https://github.com/lazenes/PC_Headerlib-Viewer)
## Post #11
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-04T11:57:24+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

i made an extractor and super basic model import script for blender, as of right now my extractor is broken but i will share it once i fix it, along with the blender script of course, and will post the code on GitHub for both
[Capture.png](https://xentaxbackup.github.io/file/21341_Capture.png)
## Post #12
- Username: elasticheart
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Oct 09, 2021 3:52 am
- Post datetime: 2021-12-04T12:19:19+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sat Dec 04, 2021 7:57 pm at Sat Dec 04, 2021 7:57 pm
>
> 
i made an extractor and super basic model import script for blender, as of right now my extractor is broken but i will share it once i fix it, along with the blender script of course, and will post the code on GitHub for both

This is neat! Does it also extract the textures?
## Post #13
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-12-04T12:59:17+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

Nice!! Awesome job
## Post #14
- Username: giofrida
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 08, 2020 5:14 pm
- Post datetime: 2021-12-04T17:03:28+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

Hey!
Just wanted to contribute to the thread by posting my "unscrambler" tool that you can use to decypher .ini.scrambled configuration files you can find inside the bin folder of the game. Maybe it's not very useful for extracting models, but I don't think it deserves its own thread. 
This tool was made after reverse engineering the part of the code responsible of deciphering these files, and basically it uses a XOR key to (de)cypher the text and a 4 bytes checksum (also computed with a XOR key).

The C source code and the compiled exe of the tool are [available here](https://www.mediafire.com/file/gln0hwwum608qft/gotg-unscrambler.zip/file).
Usage is very simple: 

```
unscrambler <file>.ini.scrambled
```
 to unscramble the file

```
unscrambler <file>.ini
```
 to scramble it again
## Post #15
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-05T07:25:04+00:00
- Post Title: Guardians Of The Galaxy 2021 Ripping?

Im still waiting for tools from KboyKboy.
## Post #16
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2021-12-06T17:34:53+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from giofrida ↑Sun Dec 05, 2021 1:03 am at Sun Dec 05, 2021 1:03 am
>
> 
Hey!
Just wanted to contribute to the thread by posting my "unscrambler" tool that you can use to decypher .ini.scrambled configuration files you can find inside the bin folder of the game. Maybe it's not very useful for extracting models, but I don't think it deserves its own thread. 
This tool was made after reverse engineering the part of the code responsible of deciphering these files, and basically it uses a XOR key to (de)cypher the text and a 4 bytes checksum (also computed with a XOR key).

The C source code and the compiled exe of the tool are available here.
Usage is very simple: 
Code: Select allunscrambler <file>.ini.scrambled to unscramble the file
Code: Select allunscrambler <file>.ini to scramble it again


You can do this with a version of this Tool for hitman absolution.
[HMAScrambler.zip](https://xentaxbackup.github.io/file/21345_HMAScrambler.zip)
## Post #17
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2021-12-07T12:51:19+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sat Dec 04, 2021 7:57 pm at Sat Dec 04, 2021 7:57 pm
>
> 
i made an extractor and super basic model import script for blender, as of right now my extractor is broken but i will share it once i fix it, along with the blender script of course, and will post the code on GitHub for both

Hey that's awesome! By the way, does your extractor handle audio as well ? Was it successful at extracting the music for example ?

Excited to hear more about it
## Post #18
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2021-12-07T19:07:17+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sat Dec 04, 2021 7:57 pm at Sat Dec 04, 2021 7:57 pm
>
> 
i made an extractor and super basic model import script for blender, as of right now my extractor is broken but i will share it once i fix it, along with the blender script of course, and will post the code on GitHub for both

I want to develop a tool where I can access language files, but I couldn't solve it. Is there anyone who can help?
## Post #19
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-09T07:24:58+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from lazenes ↑Wed Dec 08, 2021 3:07 am at Wed Dec 08, 2021 3:07 am
>
> 
I want to develop a tool where I can access language files, but I couldn't solve it. Is there anyone who can help?

what kinda of language files? there is a folder called "localization" and it has stuff for subtitles, that what you are after?
## Post #20
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-09T07:25:58+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from elasticheart ↑Sat Dec 04, 2021 8:19 pm at Sat Dec 04, 2021 8:19 pm
>
> 
This is neat! Does it also extract the textures?
yes but you need a tool to convert them to usable formats
## Post #21
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-09T07:28:18+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Luriam ↑Tue Dec 07, 2021 8:51 pm at Tue Dec 07, 2021 8:51 pm
>
> 
Hey that's awesome! By the way, does your extractor handle audio as well ? Was it successful at extracting the music for example ?

Excited to hear more about it

the audio appears to use a modified version of the WWise .wem format
## Post #22
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-09T07:36:05+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

been kinda busy lately so i haven't been able to work on it too much but i will upload the extractor in 1-2 days, i had it working so it could extract the entire game but it didn't have the file names or paths, i made it so it now reads the paths but right now its having an issue where its only extracting 40gb of the 70gb it should be extracting, so once i find out why its doing that i will upload, and i also plan on eventually making a full gui app for viewing files before extracting and am also gonna work on actually making mod tools
## Post #23
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-09T07:48:22+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Thu Dec 09, 2021 3:28 pm at Thu Dec 09, 2021 3:28 pm
>
> 
Luriam wrote: ↑Tue Dec 07, 2021 8:51 pm
Hey that's awesome! By the way, does your extractor handle audio as well ? Was it successful at extracting the music for example ?

Excited to hear more about it


the audio appears to use a modified version of the WWise .wem format

turns out its a normal .wem with an extra header added to it, if you remove the first 24 bytes it can be opened in foobar
## Post #24
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2021-12-09T09:39:20+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Oh awesome   

Thank you for the update and I'm looking forward to the release of your tool :>
## Post #25
- Username: Carpethop
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Sep 12, 2011 8:02 pm
- Post datetime: 2021-12-09T14:58:19+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Thu Dec 09, 2021 3:36 pm at Thu Dec 09, 2021 3:36 pm
>
> 
been kinda busy lately so i haven't been able to work on it too much but i will upload the extractor in 1-2 days, i had it working so it could extract the entire game but it didn't have the file names or paths, i made it so it now reads the paths but right now its having an issue where its only extracting 40gb of the 70gb it should be extracting, so once i find out why its doing that i will upload, and i also plan on eventually making a full gui app for viewing files before extracting and am also gonna work on actually making mod tools
Does it also extract weights and textures?
## Post #26
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2021-12-10T16:50:10+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Thu Dec 09, 2021 3:24 pm at Thu Dec 09, 2021 3:24 pm
>
> 
lazenes wrote: ↑Wed Dec 08, 2021 3:07 am
I want to develop a tool where I can access language files, but I couldn't solve it. Is there anyone who can help?


what kinda of language files? there is a folder called "localization" and it has stuff for subtitles, that what you are after?

yes i need these files
## Post #27
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-11T06:38:21+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Carpethop ↑Thu Dec 09, 2021 10:58 pm at Thu Dec 09, 2021 10:58 pm
>
> 
Does it also extract weights and textures?
a friend made a tool to convert textures to .dds, he will upload it soon.
as of right now the mesh tool does not do anything with skeletal data, gonna work on that soon
## Post #28
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-11T06:43:47+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

alright here is the extractor, run the exe, copy the path to your runtime folder and paste it into the console, press enter then copy and paste the path to your output folder, press enter again and it will start extracting, it will extract the entire game, the game doesn't use compression so except the extracted size to be the same as the game size, and expect it to take a couple hours to extract everything, texture files have the extension .pc_tex and models are .pc_prim, a friend made a tool to convert textures to .dds and while i was busy he updated my blender mesh plugin, he is busy right now but he will upload both soon



[https://www.mediafire.com/file/vtr2gxnh ... r.exe/file](https://www.mediafire.com/file/vtr2gxnhura65b4/ResourceExtractor.exe/file)
## Post #29
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-11T11:52:32+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Thanks a ton kboykboy
## Post #30
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2021-12-11T12:28:01+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sat Dec 11, 2021 2:43 pm at Sat Dec 11, 2021 2:43 pm
>
> 
alright here is the extractor, run the exe, copy the path to your runtime folder and paste it into the console, press enter then copy and paste the path to your output folder, press enter again and it will start extracting, it will extract the entire game, the game doesn't use compression so except the extracted size to be the same as the game size, and expect it to take a couple hours to extract everything, texture files have the extension .pc_tex and models are .pc_prim, a friend made a tool to convert textures to .dds and while i was busy he updated my blender mesh plugin, he is busy right now but he will upload both soon



https://www.mediafire.com/file/vtr2gxnh ... r.exe/file

Nice work, seems to work perfectly!  Is there any chance of this being open sourced? Someone might be able to help contribute and add repacking into it.
## Post #31
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2021-12-11T17:45:25+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sat Dec 11, 2021 2:43 pm at Sat Dec 11, 2021 2:43 pm
>
> 
alright here is the extractor, run the exe, copy the path to your runtime folder and paste it into the console, press enter then copy and paste the path to your output folder, press enter again and it will start extracting, it will extract the entire game, the game doesn't use compression so except the extracted size to be the same as the game size, and expect it to take a couple hours to extract everything, texture files have the extension .pc_tex and models are .pc_prim, a friend made a tool to convert textures to .dds and while i was busy he updated my blender mesh plugin, he is busy right now but he will upload both soon



https://www.mediafire.com/file/vtr2gxnh ... r.exe/file
How can I open files with this extension?
## Post #32
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-11T20:03:55+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Notex ↑Sat Dec 11, 2021 8:28 pm at Sat Dec 11, 2021 8:28 pm
>
> 
Nice work, seems to work perfectly!  Is there any chance of this being open sourced? Someone might be able to help contribute and add repacking into it.
i plan on making a repacker and i also plan on making it open source, i was going to do that from the beginning but my code is a mess and i am probably gonna redo most of it anyway
## Post #33
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-11T20:04:34+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from lazenes ↑Sun Dec 12, 2021 1:45 am at Sun Dec 12, 2021 1:45 am
>
> 
How can I open files with this extension?
a hex editor, HxD is good
## Post #34
- Username: elasticheart
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Oct 09, 2021 3:52 am
- Post datetime: 2021-12-11T20:08:50+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

I noticed my extractor closed itself while I was gone. I do not know if that's supposed to happen. Since it has extracted 74gb. I assume I should be fine? My only issue if I can find the UI images for each guardian.
## Post #35
- Username: maryrangel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 27, 2019 2:25 am
- Post datetime: 2021-12-11T22:12:21+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sun Dec 12, 2021 4:03 am at Sun Dec 12, 2021 4:03 am
>
> 
Notex wrote: ↑Sat Dec 11, 2021 8:28 pm
Nice work, seems to work perfectly!  Is there any chance of this being open sourced? Someone might be able to help contribute and add repacking into it.

i plan on making a repacker and i also plan on making it open source, i was going to do that from the beginning but my code is a mess and i am probably gonna redo most of it anyway

Bless you! A repacker would be amazing!!! Thank you for the extract tool!
## Post #36
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-11T23:59:22+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from elasticheart ↑Sun Dec 12, 2021 4:08 am at Sun Dec 12, 2021 4:08 am
>
> 
I noticed my extractor closed itself while I was gone. I do not know if that's supposed to happen. Since it has extracted 74gb. I assume I should be fine? My only issue if I can find the UI images for each guardian.
yes it closes itself when its done, not sure where the UI images are, the file structure of this game is very confusing
## Post #37
- Username: Irastris
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 21, 2015 12:28 pm
- Post datetime: 2021-12-12T01:41:52+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Mesh and texture tools based on our early research.

Meshes:

Mesh importing is handled by Blender. v2.93 is the only tested version, but it's likely compatible with anything newer than v2.90. Vertices/faces/UVs are supported with materials/weights/skeletons likely coming later. An LOD toggle is exposed by the importer allowing you to decide whether or not you only want to import the highest detail LOD. Should support most PRIM types other than geomcache, but regardless expect some meshes to fail to import correctly.



Textures:

Texture conversion is handled by a Python script. v3.9 is the only tested version, but again it's likely compatible with others. Requires Click installed through pip. Only textures with a depth of 1 are supported at this time. We have yet to discover a consistent way to detect texture format so for now it must be manually specified, with BC[1/3/7]_UNORM being available in this first release. Use Microsoft's Texconv or some similar application to convert the resulting DDS to TGA/PNG/etc if desired. An example of calling the script would be as follows, along with the result (resized to avoid ruining the thread):

```
text.py extract gamora_head_bc.tif.pc_tex -f BC7_UNORM
```


[gotgTools.zip](https://xentaxbackup.github.io/file/21376_gotgTools.zip)
## Post #38
- Username: elasticheart
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Oct 09, 2021 3:52 am
- Post datetime: 2021-12-12T03:34:25+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Irastris ↑Sun Dec 12, 2021 9:41 am at Sun Dec 12, 2021 9:41 am
>
> 
Mesh and texture tools based on our early research.

Meshes:

Mesh importing is handled by Blender. v2.93 is the only tested version, but it's likely compatible with anything newer than v2.90. Vertices/faces/UVs are supported with materials/weights/skeletons likely coming later. An LOD toggle is exposed by the importer allowing you to decide whether or not you only want to import the highest detail LOD. Should support most PRIM types other than geomcache, but regardless expect some meshes to fail to import correctly.



Textures:

Texture conversion is handled by a Python script. v3.9 is the only tested version, but again it's likely compatible with others. Requires Click installed through pip. Only textures with a depth of 1 are supported at this time. We have yet to discover a consistent way to detect texture format so for now it must be manually specified, with BC[1/3/7]_UNORM being available in this first release. Use Microsoft's Texconv or some similar application to convert the resulting DDS to TGA/PNG/etc if desired. An example of calling the script would be as follows, along with the result (resized to avoid ruining the thread):
Code: Select alltext.py extract gamora_head_bc.tif.pc_tex -f BC7_UNORM

Thank you a lot for this amazing research and tools! Since it's been a while I used Blender. I assume I just install these like an add on right? 
Also I couldn't figure out where the PRIM files are located. I have 3 main folders named, assembly, modules and project.
## Post #39
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-12T12:14:33+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Thanks  here is a Blender batch script for anyone who needs it.  

Just change the input path.
[PRIM2FBX(GOTG).zip](https://xentaxbackup.github.io/file/21382_PRIM2FBX(GOTG).zip)
## Post #40
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2021-12-12T12:51:42+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Irastris ↑Sun Dec 12, 2021 9:41 am at Sun Dec 12, 2021 9:41 am
>
> 

Thanks for this awsome tool!!!!
It works like a charm!  

I just thought that maybe the game use multiple UV layers for texturing? Since I find no right texture that fits gamora's eyelashes  
[](https://ibb.co/k9k8gNq)
## Post #41
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-12T12:54:06+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Textures I batched as well. Placed all files into 1 folder and did this.
[](https://ibb.co/xzkXT83)

pip install click

Then ran this .bat file along with the text.py inside of the folder. Anyone is more than welcome to use.   
[TEX2DDS.zip](https://xentaxbackup.github.io/file/21379_TEX2DDS.zip)
## Post #42
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2021-12-12T13:29:42+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hey guys, very nice work!

I was wondering if I could please get some help extracting the audio. After unpacking the game files I found the sounds, and they're all inside these PC_WEM files. I tried some tools that I usually use on wem files but they didn't work :<

Here's a couple of samples, maybe someone can help me get the wavs out of them: [https://mega.nz/file/kN0HRQTB#DLf6VS17f ... olPc73ij-c](https://mega.nz/file/kN0HRQTB#DLf6VS17f2ma4z8288w1rdqgtb0gUwhs5olPc73ij-c)

Thank you!
## Post #43
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-12T13:50:08+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Luriam ↑Sun Dec 12, 2021 9:29 pm at Sun Dec 12, 2021 9:29 pm
>
> 
Hey guys, very nice work!

I was wondering if I could please get some help extracting the audio. After unpacking the game files I found the sounds, and they're all inside these PC_WEM files. I tried some tools that I usually use on wem files but they didn't work :<

Here's a couple of samples, maybe someone can help me get the wavs out of them: https://mega.nz/file/kN0HRQTB#DLf6VS17f ... olPc73ij-c

Thank you!

Found this.
[](https://ibb.co/NrrtVrp)

I cut the files here, not sure how to process them i seen a post somewhere though.
## Post #44
- Username: elasticheart
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Oct 09, 2021 3:52 am
- Post datetime: 2021-12-12T14:03:55+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Sharppy ↑Sun Dec 12, 2021 8:54 pm at Sun Dec 12, 2021 8:54 pm
>
> 
Textures I batched as well. Placed all files into 1 folder and did this.


pip install click

Then ran this .bat file along with the text.py inside of the folder. Anyone is more than welcome to use.

Thank you! But I think im doing something wrong not sure what though since I have zero knowledge here.
## Post #45
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-12-12T14:09:34+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from elasticheart ↑Sun Dec 12, 2021 10:03 pm at Sun Dec 12, 2021 10:03 pm
>
> 
Sharppy wrote: ↑Sun Dec 12, 2021 8:54 pm
Textures I batched as well. Placed all files into 1 folder and did this.


pip install click

Then ran this .bat file along with the text.py inside of the folder. Anyone is more than welcome to use.   


Thank you! But I think im doing something wrong not sure what though since I have zero knowledge here.

You dont have python installed.
## Post #46
- Username: elasticheart
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Oct 09, 2021 3:52 am
- Post datetime: 2021-12-12T14:19:51+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kotn3l ↑Sun Dec 12, 2021 10:09 pm at Sun Dec 12, 2021 10:09 pm
>
> 
elasticheart wrote: ↑Sun Dec 12, 2021 10:03 pm
Sharppy wrote: ↑Sun Dec 12, 2021 8:54 pm
Textures I batched as well. Placed all files into 1 folder and did this.


pip install click

Then ran this .bat file along with the text.py inside of the folder. Anyone is more than welcome to use.   


Thank you! But I think im doing something wrong not sure what though since I have zero knowledge here.




You dont have python installed.

now it says no module found and something about click
## Post #47
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2021-12-12T14:23:43+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Sharppy ↑Sun Dec 12, 2021 9:50 pm at Sun Dec 12, 2021 9:50 pm
>
> 
Luriam wrote: ↑Sun Dec 12, 2021 9:29 pm
Hey guys, very nice work!

I was wondering if I could please get some help extracting the audio. After unpacking the game files I found the sounds, and they're all inside these PC_WEM files. I tried some tools that I usually use on wem files but they didn't work :<

Here's a couple of samples, maybe someone can help me get the wavs out of them: https://mega.nz/file/kN0HRQTB#DLf6VS17f ... olPc73ij-c

Thank you!  


Found this.


I cut the files here, not sure how to process them i seen a post somewhere though.

Hey sorry no idea what that means or what to do x_x

Could you please explain ? I used HxD yesterday to inspect the files, which is how I learned that there are wave files inside them. But I don't know what to do with that information
## Post #48
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-12T14:40:18+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Seems you don't have the text.py inside the folder too. And you forgot to do 

pip install click   (in CMD)

.bat is designed to process all textures at once "Invalid input" means the texture is not there.   try editing .bat to do recursively if not then just do them 1 by 1 with text.py

And for audio im not sure. No tools yet seems like in the community. Will have to wait   so far i found..
ANIMATIONS : 85,000
MODELS: 20,000
TEXTURES: 40,000
## Post #49
- Username: Exolia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 13, 2021 8:30 pm
- Post datetime: 2021-12-13T12:39:48+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Sharppy ↑Sun Dec 12, 2021 8:54 pm at Sun Dec 12, 2021 8:54 pm
>
> 
Textures I batched as well. Placed all files into 1 folder and did this.


pip install click

Then ran this .bat file along with the text.py inside of the folder. Anyone is more than welcome to use.

i have issue with Click module, even though it is installed (Python version 3.9, also tried different click install commands, but still get same result)
UPD: actually its looks like Python Issue, i updated Python to 3.9.9 (i had 3.9.0) and now its works fine
## Post #50
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2021-12-13T20:31:26+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sun Dec 12, 2021 4:04 am at Sun Dec 12, 2021 4:04 am
>
> 
lazenes wrote: ↑Sun Dec 12, 2021 1:45 am
How can I open files with this extension?

a hex editor, HxD is good

No, how can I decrypt these files?
## Post #51
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-14T02:53:32+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from lazenes ↑Tue Dec 14, 2021 4:31 am at Tue Dec 14, 2021 4:31 am
>
> 
No, how can I decrypt these files?
?? they... they aren't encrypted, its a binary file, it stores information.. in binary, if you want the actual text for the subtitles they are not in the .pc_dialogevent they are in the .pc_timedsubtitles which are also binary files but they do contain the actual text, there is no program to open them (except a hex editor), these files where made for this engine, its not some standard format, so no tools to open them, but again you can use a hex editor
## Post #52
- Username: Crazyike
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 16, 2021 11:43 pm
- Post datetime: 2021-12-17T05:00:17+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Not sure.JPG (177.12 KiB) Viewed 341 times



Not sure what I am doing wrong here, but only a few of the Prims actually work without error and those that do are just random shapes.  This is using the Blender Addon that was shared here.

If anyone has any suggestions on what I could be missing I would certainly appreciate the help.
## Post #53
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-17T20:13:51+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Crazyike ↑Fri Dec 17, 2021 1:00 pm at Fri Dec 17, 2021 1:00 pm
>
> 
Not sure.JPG

Not sure what I am doing wrong here, but only a few of the Prims actually work without error and those that do are just random shapes.  This is using the Blender Addon that was shared here.

If anyone has any suggestions on what I could be missing I would certainly appreciate the help.
the model is incorrect, it should be 4.1 KB not 109, give the entire path to the model so i can confirm i am looking at the same one, and send me the pc_prim so i can look at it
## Post #54
- Username: Crazyike
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 16, 2021 11:43 pm
- Post datetime: 2021-12-17T20:42:32+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Here is my file path for the mesh I was attempting to open.

Guardians of the Galaxy\assembly\characters\dxm\resources\unique\starlord\starlord_mesh.fbx\starlord.prim.pc_prim

Link to the file

[https://www.dropbox.com/s/hml0vhm1hbxb2 ... m.fbx?dl=0](https://www.dropbox.com/s/hml0vhm1hbxb24w/starlord.prim.pc_prim.fbx?dl=0)
## Post #55
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-12-17T23:16:00+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Crazyike ↑Sat Dec 18, 2021 4:42 am at Sat Dec 18, 2021 4:42 am
>
> 
Here is my file path for the mesh I was attempting to open.

Guardians of the Galaxy\assembly\characters\dxm\resources\unique\starlord\starlord_mesh.fbx\starlord.prim.pc_prim

Link to the file

https://www.dropbox.com/s/hml0vhm1hbxb2 ... m.fbx?dl=0
i wanted the .pc_prim not the converted .fbx, but anyway opening that same prim gives me this. so not sure what's up with your stuff, i guess somehow the extractor failed to extract your stuff properly, or somehow the names got mixed up and what it says is starlord is some other random mesh?? no idea, and i don't even really see how that's possible, try opening this prim and show me what it looks like assembly\characters\dxm\resources\unique\starlord\starlord.fbx\starlord.weightedprim.pc_weightedprim
it should actually look identical to this image
[Capture.PNG](https://xentaxbackup.github.io/file/21416_Capture.PNG)
## Post #56
- Username: Crazyike
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 16, 2021 11:43 pm
- Post datetime: 2021-12-17T23:54:11+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sat Dec 18, 2021 7:16 am at Sat Dec 18, 2021 7:16 am
>
> 
Crazyike wrote: ↑Sat Dec 18, 2021 4:42 am
Here is my file path for the mesh I was attempting to open.

Guardians of the Galaxy\assembly\characters\dxm\resources\unique\starlord\starlord_mesh.fbx\starlord.prim.pc_prim

Link to the file

https://www.dropbox.com/s/hml0vhm1hbxb2 ... m.fbx?dl=0

i wanted the .pc_prim not the converted .fbx, but anyway opening that same prim gives me this. so not sure what's up with your stuff, i guess somehow the extractor failed to extract your stuff properly, or somehow the names got mixed up and what it says is starlord is some other random mesh?? no idea, and i don't even really see how that's possible, try opening this prim and show me what it looks like assembly\characters\dxm\resources\unique\starlord\starlord.fbx\starlord.weightedprim.pc_weightedprim
it should actually look identical to this image

Sorry looks like I dragged the wrong file in there.  

If you wanted the correct link its here, sorry again.
[https://www.dropbox.com/s/0goaykh2qaq0j ... _prim?dl=0](https://www.dropbox.com/s/0goaykh2qaq0j78/starlord.prim.pc_prim?dl=0)

I tried opening the file you suggested and nothing gets loaded.  The scene is empty with no new objects.
None of the weightedprim files open anything in blender.  The only files that I was able to get to actually add anything to the scene were a few of the pc_prim extensions that were the odd random parts like I shared.

I can run the extractor again and see if that fixes any of the files.
## Post #57
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2021-12-18T19:47:39+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Will there be a github source?
i just want to edit and repackage .codexlineen.pc localizedtext files
## Post #58
- Username: MOAX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 20, 2021 3:37 am
- Post datetime: 2021-12-23T11:04:39+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hello! Had two questions in regards the tools. I succesfully extracted the game, but i'm having a bit of struggle with the python scripts. Before asking, I did install both Python 3.9.9 and PIP + the Click Module which were mentioned earlier in the thread, and it's not picking the module at all when using the texture batching, it displays the same message of "No Module named:Click", even though I have it installed.

Also, upon running the script of PRIM2FBX on Blender (3.0) Text Console with ALT+P I get this:



Any idea what could be causing either of the problems
## Post #59
- Username: maryrangel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 27, 2019 2:25 am
- Post datetime: 2021-12-23T12:47:11+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hello! Anyone advanced with a repacker?
## Post #60
- Username: komeon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 31, 2020 10:59 am
- Post datetime: 2021-12-25T16:33:41+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hello. Can anyone help me, please, which folder gamora's hair and eye textures?
## Post #61
- Username: lJITimate
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 12, 2021 11:26 pm
- Post datetime: 2021-12-26T01:11:46+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Sharppy ↑Sun Dec 12, 2021 8:54 pm at Sun Dec 12, 2021 8:54 pm
>
> 
Textures I batched as well. Placed all files into 1 folder and did this.


pip install click

Then ran this .bat file along with the text.py inside of the folder. Anyone is more than welcome to use.

I think Ive got it working, and its outputting .dds files but they aren't usable. every software I try fails to open them properly. Any ideas?

Edit: or if anyone has an alternate method of converting texture files Id really appreciate it, even if its just one at a time
## Post #62
- Username: THBlender
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 28, 2021 7:15 am
- Post datetime: 2021-12-29T19:43:51+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Sharppy ↑Sun Dec 12, 2021 8:54 pm at Sun Dec 12, 2021 8:54 pm
>
> 
Textures I batched as well. Placed all files into 1 folder and did this.


pip install click

Then ran this .bat file along with the text.py inside of the folder. Anyone is more than welcome to use.

I'm getting this error every time i open this batch:
[](https://ibb.co/VQHZwLp)
I already have Click installed and i have python 3.9.9, what am i doing wrong?
## Post #63
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-01-02T09:04:19+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Not sure i had no issues in converting textures.  I did py install click in CMD then placed .bat and .py into same folder as textures than then ran the bat. There is nothing else to do here.
## Post #64
- Username: THBlender
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 28, 2021 7:15 am
- Post datetime: 2022-01-02T21:18:57+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Sharppy ↑Sun Jan 02, 2022 5:04 pm at Sun Jan 02, 2022 5:04 pm
>
> 
Not sure i had no issues in converting textures.  I did py install click in CMD then placed .bat and .py into same folder as textures than then ran the bat. There is nothing else to do here.

I already fixed the problem, i used py -m pip install click and it worked, now i've exported several texture files.
However, the dds textures i exported dont work in blender, The dds files are exported in bc7_unorm, and blender does not support that format and shows pink textures instead. 
If i convert the textures to bc3_unorm they will work, however if i export with the py script the images come out bugged and look like [this](https://ibb.co/HGDgkyG), so i have to use visual studio to convert from bc7 to bc3.
sorry if my english is bad i'm not a native speaker.
## Post #65
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-01-02T23:02:31+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

^ That's actually a good question. While I'm not interested in the game, I wonder if there is a blender plugin with support for "modern" texture compressions, like BC7 (it exists for more than 10 years btw). For example, something like [Valkyria Chronicles plugin](https://github.com/gomtuu/import_valkyria) with automatic external convertion through texconv.
## Post #66
- Username: THBlender
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 28, 2021 7:15 am
- Post datetime: 2022-01-03T03:14:45+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Kanbara ↑Sun Dec 12, 2021 8:51 pm at Sun Dec 12, 2021 8:51 pm
>
> 
Irastris wrote: ↑Sun Dec 12, 2021 9:41 am


Thanks for this awsome tool!!!!
It works like a charm!  

I just thought that maybe the game use multiple UV layers for texturing? Since I find no right texture that fits gamora's eyelashes

where did you find the hair and eye texture? i cant find them anywhere
## Post #67
- Username: Galmoth
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 18, 2021 9:05 pm
- Post datetime: 2022-01-06T03:55:47+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hello people!
Anyone know how can I export all Star-Lord Helmets? (skins and the original). I can't find the model of this object.

Thank You!
## Post #68
- Username: Galmoth
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 18, 2021 9:05 pm
- Post datetime: 2022-01-06T08:30:47+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Galmoth ↑Thu Jan 06, 2022 11:55 am at Thu Jan 06, 2022 11:55 am
>
> 
Hello people!
Anyone know how can I export all Star-Lord Helmets? (skins and the original). I can't find the model of this object.

Thank You!

Ok! I Finaly found the files... xD
Just open this folders > "assembly/characters" and type "helmet.prim"
## Post #69
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2022-01-07T19:44:13+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sat Dec 11, 2021 2:43 pm at Sat Dec 11, 2021 2:43 pm
>
> 
alright here is the extractor, run the exe, copy the path to your runtime folder and paste it into the console, press enter then copy and paste the path to your output folder, press enter again and it will start extracting, it will extract the entire game, the game doesn't use compression so except the extracted size to be the same as the game size, and expect it to take a couple hours to extract everything, texture files have the extension .pc_tex and models are .pc_prim, a friend made a tool to convert textures to .dds and while i was busy he updated my blender mesh plugin, he is busy right now but he will upload both soon



https://www.mediafire.com/file/vtr2gxnh ... r.exe/file

Does this only work with PC_ResourceLib files? Sadly I only have the ps4 files, so mine are with PS4_ResourceLib extension. Renaming them does not work, so there must be something different.
## Post #70
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2022-01-28T22:04:30+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sun Dec 12, 2021 4:03 am at Sun Dec 12, 2021 4:03 am
>
> 
i plan on making a repacker and i also plan on making it open source, i was going to do that from the beginning but my code is a mess and i am probably gonna redo most of it anyway

Hey kboykboy, any news on your plan? I am currently looking further into the formats, and any help would come in handy. If you could share what you already have, that would be absolutely amazing! I don't mind if the code is messy, btw. 

Actually I'm quite far already I think, I can get the resource headers from the .pc_headerlib files and the pointers to a pc_resourcelib, but I just don't know where to get the right offsets into the resourcelibs from...
In Deus Ex 4, there were these big .archive files that contained the resourcelibs together with a list of all resource offsets, but in GotG, they are all loose files without indexes... or so it seems.
## Post #71
- Username: player12341
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jan 16, 2022 10:46 pm
- Post datetime: 2022-02-01T23:25:11+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

not any support for modding yet?
## Post #72
- Username: Afonnyboy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 22, 2019 9:13 am
- Post datetime: 2022-02-09T04:21:45+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Any news on an update to support skeletons and or weights?
## Post #73
- Username: lazenes
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 08, 2021 3:57 am
- Post datetime: 2022-02-26T16:15:38+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

I have C++ Code blogs, how can I export game language files with them?
 I don't know c++ I'm looking for a friend who can help me
## Post #74
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2022-02-27T21:44:18+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from kboykboy ↑Sun Dec 12, 2021 4:03 am at Sun Dec 12, 2021 4:03 am
>
> 
Notex wrote: ↑Sat Dec 11, 2021 8:28 pm
Nice work, seems to work perfectly!  Is there any chance of this being open sourced? Someone might be able to help contribute and add repacking into it.

i plan on making a repacker and i also plan on making it open source, i was going to do that from the beginning but my code is a mess and i am probably gonna redo most of it anyway

Are you still working on repacker?
## Post #75
- Username: olvad
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 07, 2022 6:00 am
- Post datetime: 2022-03-07T01:38:58+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

oh man it looks like this is dead! did anyone figure out how to get rigs and weights?
## Post #76
- Username: olvad
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 07, 2022 6:00 am
- Post datetime: 2022-03-07T18:55:50+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Kanbara ↑Sun Dec 12, 2021 8:51 pm at Sun Dec 12, 2021 8:51 pm
>
> 
Irastris wrote: ↑Sun Dec 12, 2021 9:41 am


Thanks for this awsome tool!!!!
It works like a charm!  

I just thought that maybe the game use multiple UV layers for texturing? Since I find no right texture that fits gamora's eyelashes

how did you apply the textures properly? when i do it it looks strange. everything has hardly any color.
## Post #77
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2022-03-20T20:13:25+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Sharppy ↑Sun Jan 02, 2022 5:04 pm at Sun Jan 02, 2022 5:04 pm
>
> 
Not sure i had no issues in converting textures.  I did py install click in CMD then placed .bat and .py into same folder as textures than then ran the bat. There is nothing else to do here.

Did you manage to convert the AO maps for characters? I'm having trouble converting those.
## Post #78
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2022-03-20T22:29:29+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Irastris ↑Sun Dec 12, 2021 9:41 am at Sun Dec 12, 2021 9:41 am
>
> 
Mesh and texture tools based on our early research.

Meshes:

Mesh importing is handled by Blender. v2.93 is the only tested version, but it's likely compatible with anything newer than v2.90. Vertices/faces/UVs are supported with materials/weights/skeletons likely coming later. An LOD toggle is exposed by the importer allowing you to decide whether or not you only want to import the highest detail LOD. Should support most PRIM types other than geomcache, but regardless expect some meshes to fail to import correctly.



Textures:

Texture conversion is handled by a Python script. v3.9 is the only tested version, but again it's likely compatible with others. Requires Click installed through pip. Only textures with a depth of 1 are supported at this time. We have yet to discover a consistent way to detect texture format so for now it must be manually specified, with BC[1/3/7]_UNORM being available in this first release. Use Microsoft's Texconv or some similar application to convert the resulting DDS to TGA/PNG/etc if desired. An example of calling the script would be as follows, along with the result (resized to avoid ruining the thread):
Code: Select alltext.py extract gamora_head_bc.tif.pc_tex -f BC7_UNORM
Thank you for these tools, it's great to have access to them 

I'm having some UVs issues with models imported using the blender script, specifically gamora's eyelashes and Mantis's blades. Also, when importing Mantisis's body, her skirt is missing, leaving a hole in her waist.

Many thanks
gep5
## Post #79
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2022-03-22T02:43:01+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

I read the thread but haven't found an answer since I dont have the game to look at the files (yet).
is static mesh supported? like the random map objects? or is it the .geomcache?
## Post #80
- Username: Doomslayer123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 23, 2022 12:21 am
- Post datetime: 2022-03-22T21:15:09+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

hello , im new here , someone please can explain to me all the steps to extract the models ?
## Post #81
- Username: bigbiggerboy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 24, 2022 9:03 am
- Post datetime: 2022-03-24T01:06:47+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hey guys, is there any way someone could send me the model and stuff for peter quill, I've been looking everywhere to get it and you guys seem to have gotten access to it.
## Post #82
- Username: olvad
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 07, 2022 6:00 am
- Post datetime: 2022-03-28T18:27:32+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from gep55 ↑Mon Mar 21, 2022 4:13 am at Mon Mar 21, 2022 4:13 am
>
> 
Sharppy wrote: ↑Sun Jan 02, 2022 5:04 pm
Not sure i had no issues in converting textures.  I did py install click in CMD then placed .bat and .py into same folder as textures than then ran the bat. There is nothing else to do here.


Did you manage to convert the AO maps for characters? I'm having trouble converting those.

did you figure out the AO maps? mine aren't converting properly either
## Post #83
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2022-03-31T13:28:37+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from olvad ↑Tue Mar 29, 2022 2:27 am at Tue Mar 29, 2022 2:27 am
>
> 
gep55 wrote: ↑Mon Mar 21, 2022 4:13 am
Sharppy wrote: ↑Sun Jan 02, 2022 5:04 pm
Not sure i had no issues in converting textures.  I did py install click in CMD then placed .bat and .py into same folder as textures than then ran the bat. There is nothing else to do here.


Did you manage to convert the AO maps for characters? I'm having trouble converting those.


did you figure out the AO maps? mine aren't converting properly either
The tool doesn't convert them properly, but I managed to use this to get the AO maps working properly.

You have to play around with the settings to get it to convert the image correctly though, so there is some trial and error involved in finding the right settings.

[viewtopic.php?f=18&t=16461](https://forum.xentax.com/viewtopic.php?f=18&t=16461)
## Post #84
- Username: samboychips
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 07, 2020 4:04 pm
- Post datetime: 2022-06-08T05:59:48+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hey guys! Is there a version of GotG at which the extractor compatibility ceases? I'm trying to run the resourcesextractor.exe tool with the complete edition's core runtime files and the app just exits immediately without any extraction happening...
## Post #85
- Username: fpaterson6
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 14, 2022 12:58 am
- Post datetime: 2022-08-13T17:00:27+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Would anyone be able to send me the files for the element guns as I don’t have the game on pc to rip them, any help would be greatly appreciated!!

Edit: I do own the game on Xbox however can’t rip the files from it
## Post #86
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2022-08-17T07:46:32+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hello, tell me where to look models Gamora/Drax
assembly\characters\dxm\resources\unique\gamora and assembly\characters\dxm\resources\unique\drax
dont have .pc_weightedprim, maybe tools extract not all
may parts of the models be on other paths
Thanks
## Post #87
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2022-08-17T09:00:20+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Crazy31139 ↑Wed Aug 17, 2022 3:46 pm at Wed Aug 17, 2022 3:46 pm
>
> 
Hello, tell me where to look models Gamora/Drax
assembly\characters\dxm\resources\unique\gamora and assembly\characters\dxm\resources\unique\drax
dont have .pc_weightedprim, maybe tools extract not all
may parts of the models be on other paths
Thanks

The tool might overwrite a lot of files due to how absurd the path structure is in the engine, unfortunately it's the only tool and the author seems to have disappeared.
## Post #88
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2022-09-12T05:59:36+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hi
Here is a blend file for import models from "pc_weightedprim, pc_prim, pc_bonerig" files.
It requires to install Blender version 249b (32 bit) and Python 2.6.6.(32 bit).
Doubleclick file "Blender249.blend" and in Text Window press alt+p to run script.
Select file  and press import.
Script import geometry, uv , weights and bones.
No names for bones only numbers.

You must have experience in using such an old Blender.

[https://www.mediafire.com/file/atevy3zz ... D.zip/file](https://www.mediafire.com/file/atevy3zzryhtf7x/Blender249%255BMGotG%255D%255BPC%255D%255Bpc_weightedprim%255D%255B2022-09-11%255D.zip/file)
## Post #89
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2022-09-30T11:02:42+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Szkaradek123 ↑Mon Sep 12, 2022 1:59 pm at Mon Sep 12, 2022 1:59 pm
>
> 
Hi
Here is a blend file for import models from "pc_weightedprim, pc_prim, pc_bonerig" files.
It requires to install Blender version 249b (32 bit) and Python 2.6.6.(32 bit).
Doubleclick file "Blender249.blend" and in Text Window press alt+p to run script.
Select file  and press import.
Script import geometry, uv , weights and bones.
No names for bones only numbers.

You must have experience in using such an old Blender.

https://www.mediafire.com/file/atevy3zz ... D.zip/file
hey man, thanks for this, any chance you could explain how to set 2.49b to use python 2.6.6? even though I have it installed, it still uses 2.6.2 according to the console window.
## Post #90
- Username: AttackTheNarwhal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 24, 2022 12:09 am
- Post datetime: 2022-10-03T01:48:43+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Does anyone know the method for opening the LinkedPrim file format? I've tried a few different methods and even when it does insert, it becomes a jumbled mess. I'm trying to export the Milano ship exterior and interior and it looks like the entire ship is a linkedprim file.
## Post #91
- Username: Trinigamer10
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 03, 2022 11:20 pm
- Post datetime: 2022-11-03T15:22:46+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

I hope this isn't a necro, but does anyone have the model of Cosmo the dog? Would really appreciate that
## Post #92
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2022-12-19T11:50:31+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

> Reply from Szkaradek123 ↑Mon Sep 12, 2022 1:59 pm at Mon Sep 12, 2022 1:59 pm
>
> 
Hi
Here is a blend file for import models from "pc_weightedprim, pc_prim, pc_bonerig" files.
It requires to install Blender version 249b (32 bit) and Python 2.6.6.(32 bit).
Doubleclick file "Blender249.blend" and in Text Window press alt+p to run script.
Select file  and press import.
Script import geometry, uv , weights and bones.
No names for bones only numbers.

You must have experience in using such an old Blender.

https://www.mediafire.com/file/atevy3zz ... D.zip/file
Hi, dont load Nikki_cadet body, if you have time can see
path - assembly\characters\dxm\resources\unique\nikki_cadet\nikki_cadet.fbx\nikki_cadet_cloth.weightedprim.pc_weightedprim
Thanks
## Post #93
- Username: CooseyGoosey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 16, 2023 7:52 am
- Post datetime: 2023-06-15T23:57:35+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

I'll pay someone to rip a few models for me. Just looking for Star-Lord's Mask/Visor, Blasters, and maybe Walkman, as well as his character model. I dont even need textures, just models that I can open in blender. Can someone help me out?
## Post #94
- Username: renicito
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 14, 2021 8:12 am
- Post datetime: 2023-09-02T01:59:13+00:00
- Post Title: Re: Guardians Of The Galaxy 2021 Ripping?

Hello, is there any tool that can extract the audio files of the game "Marvel's Guardians of the Galaxy PC".
The audio files are:

32F71247E61BDD3FC443053EA1D1B597.pc_resourcelib
and
227645555CA21C44361D76432590234D.pc_resourcelib

They have a pc_resourcelib format. I would like to be able to extract the audios that are in these files. Please help me if you know of any method or form or tool.

  I am very grateful for your time...
