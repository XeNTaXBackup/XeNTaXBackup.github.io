## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-06T16:18:07+00:00
- Post Title: Injustice 2 (PC)

Injustice 2 (PC) tool





Tool must work with all game packages (including full map export). Usage:

1. Unpack .XXX package with ue3_oodle.bms
2. Drop created .unp file onto the tool. Corresponding .TFC file must be in the same folder
3. Models will be exported in ASCII & SMD formats as usual. ASCII skeletons will be broken, use SMD skeletons. ASCII will have all extra UV pairs.
4. Textures will be exported as DDS and OODLE. You need to unpack OODLE ones with ue3_oodle_dds.bms
Example .bat file to unpack all oodle textures:

```
for %%a in (*.oodle) do quickbms.exe ue3_oodle_dds.bms "%%a"
```

Notes:
- Models are split into many exchangeable parts. They will all have their own skeletons, bone names will be compatible. Example:
- Map export support (instructions are in this post - [viewtopic.php?p=138619#p138619](http://forum.xentax.com/viewtopic.php?p=138619#p138619) )


[Injustice2_model.rar](https://xentaxbackup.github.io/file/14180_Injustice2_model.rar)
## Post #2
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-07T01:12:36+00:00
- Post Title: Injustice 2 (PC)

the textures are very bright (white). The textures converted from the .oodle seem to be have a heavy transparency and washed out colours (very white) but the few dds that were extracted were perfect.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-07T15:14:10+00:00
- Post Title: Injustice 2 (PC)

> Reply from AstroStormz
>
> the textures are very bright

All textures are correct BC7. I dont have time to explain how to apply them. Ask someone else.
## Post #4
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-07T20:19:27+00:00
- Post Title: Injustice 2 (PC)

> Reply from daemon1
>
> AstroStormz wrote:the textures are very bright

All textures are correct BC7. I dont have time to explain how to apply them. Ask someone else.

even in the picture you provided the batman textures are white. Noone else knows how to get textures working properly. Only premier skins have working textures.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-07T20:29:45+00:00
- Post Title: Injustice 2 (PC)

> Reply from AstroStormz
>
> even in the picture you provided the batman textures are white.
they are not white. they are grey, supposed to be painted using masks in the other textures.
## Post #6
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-08T02:54:29+00:00
- Post Title: Injustice 2 (PC)

> Reply from daemon1
>
> AstroStormz wrote:even in the picture you provided the batman textures are white.
they are not white. they are grey, supposed to be painted using masks in the other textures.

each character file has a shader.tfc tho......i thought maybe how the game uses shaders maybe each of the shader overlay the (grey) textures to form the colour but there is no way for me to open the tfc to see
## Post #7
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2017-12-08T03:15:36+00:00
- Post Title: Injustice 2 (PC)

Eye texture is stored in the startup.xxx file
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-08T15:24:07+00:00
- Post Title: Injustice 2 (PC)

> Reply from AstroStormz
>
> shader.tfc

ok i'll check whats inside of these

p.s. ok they are exactly what i expected: directX compiled shaders
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-08T16:26:09+00:00
- Post Title: Injustice 2 (PC)

fixed a bug that caused SubZero to crash
## Post #10
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-08T18:24:26+00:00
- Post Title: Injustice 2 (PC)

> Reply from daemon1
>
> fixed a bug that caused SubZero to crash
 you have a tool to open/extract individual .tfc files?
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-08T18:49:15+00:00
- Post Title: Injustice 2 (PC)

> Reply from AstroStormz
>
> daemon1 wrote:fixed a bug that caused SubZero to crash
 you have a tool to open/extract individual .tfc files?
no, TFC are accessed (linked) from XXX
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-08T19:24:13+00:00
- Post Title: Injustice 2 (PC)

here's an example of a character extracted with this tool:
[https://sticklove.deviantart.com/art/Bl ... -718933170](https://sticklove.deviantart.com/art/Black-Canary-718933170)
## Post #13
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-08T20:30:25+00:00
- Post Title: Injustice 2 (PC)

> Reply from daemon1
>
> here's an example of a character extracted with this tool:
https://sticklove.deviantart.com/art/Bl ... -718933170
 yes and i spoke to him. He coloured textures manually. Its a shame but nothing can be done about that since the game has character customization
## Post #14
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-12-08T22:51:06+00:00
- Post Title: Injustice 2 (PC)

Great work. Is it possible to have your tool support Animation or Sound?

Thanks for letting us know.
## Post #15
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-09T01:58:48+00:00
- Post Title: Injustice 2 (PC)

[quote="daemon1"]here's an example of a character extracted with this tool:

im sorry that this is outta topic but by chance do you know how to get models from ps1 games? im trying to get the batmobile from the batman and robin game from the playstation 1 but no ripper is working with it
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-09T06:46:42+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from AstroStormz
>
> daemon1 wrote:here's an example of a character extracted with this tool:

im sorry that this is outta topic but by chance do you know how to get models from ps1 games? im trying to get the batmobile from the batman and robin game from the playstation 1 but no ripper is working with it
yes i got some models from ps1, its a lot different and i'm not sure i'll have time for it
## Post #17
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-09T11:14:52+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> AstroStormz wrote:daemon1 wrote:here's an example of a character extracted with this tool:

im sorry that this is outta topic but by chance do you know how to get models from ps1 games? im trying to get the batmobile from the batman and robin game from the playstation 1 but no ripper is working with it
yes i got some models from ps1, its a lot different and i'm not sure i'll have time for it

oh well i make mods for san andreas and im tryna get the diff batmobiles. Here is the ps1 game [https://drive.google.com/open?id=1C_mu8 ... ktw30dyHe3](https://drive.google.com/open?id=1C_mu8rWgp3sqJN3zvD6D0Vktw30dyHe3) i know you are very busy but if you do have time any help with this is appreciated. Thanks for all your hard work man!
## Post #18
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2017-12-09T16:34:32+00:00
- Post Title: Re: Injustice 2 (PC)

Where I can get bms scripts? Look like it missing after update.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-09T16:45:34+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from m0xf
>
> Where I can get bms scripts? Look like it missing after update.
oh.

added them
## Post #20
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2017-12-09T17:10:47+00:00
- Post Title: Re: Injustice 2 (PC)


## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-14T20:26:55+00:00
- Post Title: Re: Injustice 2 (PC)

Working on maps export. Its not fully working yet, but most of the object export fine.
## Post #22
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-15T12:34:39+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Working on maps export. Its not fully working yet, but most of the object export fine.

by chance do you know what file the batmobile with interior is? i got the batmobile from vehiclecave but the textures are weird and there is no interior like from the cutscene
## Post #23
- Username: killonious
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 18, 2017 2:23 am
- Post datetime: 2017-12-17T18:28:11+00:00
- Post Title: Re: Injustice 2 (PC)

Is there a guide for noobie on how to rip these models from Injustice 2 I don't quite understand these dirctions.

1. Unpack .XXX package with ue3_oodle.bms
2. Drop created .unp file onto the tool. Corresponding .TFC file must be in the same folder
3. Models will be exported in ASCII & SMD formats as usual. ASCII skeletons will be broken, use SMD skeletons. ASCII will have all extra UV pairs.
4. Textures will be exported as DDS and OODLE. You need to unpack OODLE ones with ue3_oodle_dds.bms
Example .bat file to unpack all oodle textures:

I have downloaded the files and unzipped that's as far as i gotten.

Thanks
## Post #24
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-18T01:51:18+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from killonious
>
> Is there a guide for noobie on how to rip these models from Injustice 2 I don't quite understand these dirctions.

1. Unpack .XXX package with ue3_oodle.bms
2. Drop created .unp file onto the tool. Corresponding .TFC file must be in the same folder
3. Models will be exported in ASCII & SMD formats as usual. ASCII skeletons will be broken, use SMD skeletons. ASCII will have all extra UV pairs.
4. Textures will be exported as DDS and OODLE. You need to unpack OODLE ones with ue3_oodle_dds.bms
Example .bat file to unpack all oodle textures:

I have downloaded the files and unzipped that's as far as i gotten.

Thanks

to follow these instructions u need quickbms and the tool daemon provided
## Post #25
- Username: killonious
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 18, 2017 2:23 am
- Post datetime: 2017-12-21T03:50:00+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from AstroStormz
>
> killonious wrote:Is there a guide for noobie on how to rip these models from Injustice 2 I don't quite understand these dirctions.

1. Unpack .XXX package with ue3_oodle.bms
2. Drop created .unp file onto the tool. Corresponding .TFC file must be in the same folder
3. Models will be exported in ASCII & SMD formats as usual. ASCII skeletons will be broken, use SMD skeletons. ASCII will have all extra UV pairs.
4. Textures will be exported as DDS and OODLE. You need to unpack OODLE ones with ue3_oodle_dds.bms
Example .bat file to unpack all oodle textures:

I have downloaded the files and unzipped that's as far as i gotten.

Thanks

to follow these instructions u need quickbms and the tool daemon provided

Thank you for the reply I downloaded quickbms watch some video on how it works and still can't figure it out.  I guess I'm too much of a noob to figure this one out.  I can even unlock my injustice 2.exe file i download from Microsoft.
## Post #26
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-12-25T00:32:10+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from killonious
>
> AstroStormz wrote:killonious wrote:Is there a guide for noobie on how to rip these models from Injustice 2 I don't quite understand these dirctions.

1. Unpack .XXX package with ue3_oodle.bms
2. Drop created .unp file onto the tool. Corresponding .TFC file must be in the same folder
3. Models will be exported in ASCII & SMD formats as usual. ASCII skeletons will be broken, use SMD skeletons. ASCII will have all extra UV pairs.
4. Textures will be exported as DDS and OODLE. You need to unpack OODLE ones with ue3_oodle_dds.bms
Example .bat file to unpack all oodle textures:

I have downloaded the files and unzipped that's as far as i gotten.

Thanks

to follow these instructions u need quickbms and the tool daemon provided

Thank you for the reply I downloaded quickbms watch some video on how it works and still can't figure it out.  I guess I'm too much of a noob to figure this one out.  I can even unlock my injustice 2.exe file i download from Microsoft.

quickbms is as simple as it gets....there are bms files included in what daemon provided just open quickbms load script (bms files) and follow his instructions
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-31T15:18:04+00:00
- Post Title: Re: Injustice 2 (PC)

Tool updated to support "cutscene" versions of heads, which have no facial weights (because morphs used for anims) but they do have eyelashes.
## Post #28
- Username: Nihyaku
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 08, 2017 7:06 pm
- Post datetime: 2018-01-04T22:24:25+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Tool updated to support "cutscene" versions of heads, which have no facial weights (because morphs used for anims) but they do have eyelashes.
Hi! I just wanted to thank you for this tool. Your work is truly appreciated!   
I have a question: I can't seem to find these "cutscenes" versions of heads (I've unpacked almost every package, without success). In which package are they stored? I am particularly interested in Wonder Woman's eyelashes.
Thank you.
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-05T06:56:01+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Nihyaku
>
> daemon1 wrote:Tool updated to support "cutscene" versions of heads, which have no facial weights (because morphs used for anims) but they do have eyelashes.
Hi! I just wanted to thank you for this tool. Your work is truly appreciated!   
I have a question: I can't seem to find these "cutscenes" versions of heads (I've unpacked almost every package, without success). In which package are they stored? I am particularly interested in Wonder Woman's eyelashes.
Thank you.
in the same packages. Just now they will have 2 head meshes extracted into the same file.
## Post #30
- Username: Nihyaku
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 08, 2017 7:06 pm
- Post datetime: 2018-01-05T14:41:15+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Nihyaku wrote:daemon1 wrote:Tool updated to support "cutscene" versions of heads, which have no facial weights (because morphs used for anims) but they do have eyelashes.
Hi! I just wanted to thank you for this tool. Your work is truly appreciated!   
I have a question: I can't seem to find these "cutscenes" versions of heads (I've unpacked almost every package, without success). In which package are they stored? I am particularly interested in Wonder Woman's eyelashes.
Thank you.
in the same packages. Just now they will have 2 head meshes extracted into the same file.
Many thanks for your prompt reply! 
My bad I didn't check the same packages before asking. Thank you for the information!
## Post #31
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2018-01-07T09:37:07+00:00
- Post Title: Re: Injustice 2 (PC)

Can anyone explain how to correct the mesh UVs after importing the smds into blender? They don't match up with the textures. I tried all the variant textures to the arms, legs and torso, even the face and its the same issue. Do the uvs all need to be manually realigned? Is the problem only common with blender and not MAX?
## Post #32
- Username: Flandyn
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 12, 2015 9:06 pm
- Post datetime: 2018-01-10T16:31:19+00:00
- Post Title: Re: Injustice 2 (PC)

[deleted]
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-10T17:26:43+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Flandyn
>
> PPS: The importing of models requires a rotation of 270 on the X axis to get the models upright. Rotating every single object one by one manually is very frustrating and time-wasting. Please fix this.
I have no idea what do you mean by this. All objects are extracted as they are in the game.

p.s. I did not yet published any tool version for map exports. Those pictures were only examples of the tool develop progress.
## Post #34
- Username: Flandyn
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 12, 2015 9:06 pm
- Post datetime: 2018-01-11T08:18:28+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Flandyn wrote:PPS: The importing of models requires a rotation of 270 on the X axis to get the models upright. Rotating every single object one by one manually is very frustrating and time-wasting. Please fix this.
I have no idea what do you mean by this. All objects are extracted as they are in the game.
Whenever I try to import the .obj files into Marmoset Toolbag or the .smd files into Blender they always look like this:



Also, when is the map export update going to be released?

EDIT: It also appears the models are flipped for some reason:
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-13T07:59:32+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Flandyn
>
> Also, when is the map export update going to be released?
no estimate time. After I finish other urgent tasks.

UE3 has coordinate system different from blender: its Y-up and left-handed. This is why models look like this.
## Post #36
- Username: Flandyn
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 12, 2015 9:06 pm
- Post datetime: 2018-01-13T13:04:27+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> 
UE3 has coordinate system different from blender: its Y-up and left-handed. This is why models look like this.
Is there any way to fix this?
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-13T15:07:23+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Flandyn
>
> Is there any way to fix this?
Load all parts and rotate them together. You dont have to do it for each model.
## Post #38
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2018-01-14T02:23:00+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Flandyn wrote:Is there any way to fix this?
Load all parts and rotate them together. You dont have to do it for each model.
daemon, can you offer any advice on fixing the UVs in blender? do they need to be manually realigned? Or also flipped?
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-14T07:17:07+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Straight Edge
>
> do they need to be manually realigned? Or also flipped?

no, nothing needs to be manually realigned. Just change vertical scale from 1 to -1.
## Post #40
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-01-15T12:53:47+00:00
- Post Title: Re: Injustice 2 (PC)

Is anyone planning on or already have the Wonder Woman, Starfire and Harley Quinn models, including their respective gear sets?  Barring that, would anyone be willing to share the appropriate files so I can try to rip them myself?
## Post #41
- Username: Kabalstein03
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 9:36 am
- Post datetime: 2018-01-21T20:43:50+00:00
- Post Title: Re: Injustice 2 (PC)

Um, hello, i'm Kabalstein03, or OGLoc069 from DeviantArt.
I'm not sure if someone else has stated this earlier, but it seems that some character files still give errors while extracting. It usted to be Scarecrow and Sub-Zero, even though those 2 are now fixed, i'm recently experiencing errors with Brainiac's Files (BR_... / CHAR_Brainiac...) and also Black Lighting (Raiden_A...). I'm not sure if there are other characters who experience this as well, i'm willing to check every file of those i haven't seen to spread the word.
## Post #42
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-01-28T00:07:19+00:00
- Post Title: Re: Injustice 2 (PC)

OK, manage to find most of the character files, only thing I can't find at this point is Enchantress.  Anyone have her and is willing to share?
## Post #43
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2018-02-17T23:58:42+00:00
- Post Title: Re: Injustice 2 (PC)

Any updates, daemon? Would like to try out that map exporter with the tool, results looks amazing.
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-18T06:33:27+00:00
- Post Title: Re: Injustice 2 (PC)

no, i'm busy with other games
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-15T08:37:55+00:00
- Post Title: Re: Injustice 2 (PC)

Experimental version with map export support



This version is fully functional: it exports models and textures (like before), and also maps.
Maps are only exported as ascii. Skeletal mesh instances will be exported as static models. Only one UV pair is exported into map.

Usage:

1. Run the tool on ...._MapAssets file
In addition to usual export, it will creare 2 folders: skeletalmesh.raw & staticmesh.raw, which will be needed for map export.

2. Run the tool on small main map files, such as MET_Exterior
This will read information about all mesh instances on a map, search for them in above mentioned folders, and export 2 map files, separate for static & skeletal meshes. If some meshes will be missing, it will give warning messages. Some meshes may be in other packages. If you need them, extract them and put in the same folder
## Post #46
- Username: zeejeez
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 16, 2018 9:00 am
- Post datetime: 2018-03-16T01:45:19+00:00
- Post Title: Re: Injustice 2 (PC)

Thank you SO much for your work on this tool. I have been excited to get these models ever since I saw the announcement trailer... It was a long wait for the PC version.

I'm curious if anyone has had any luck with Wonder Woman? I can't find the correct CHAR .xxx and .tfc files for her in the Assets folder. I was able to get Supergirl into Blender so I know how to get that far, but I am unable to find the right files for Wonder Woman. Maybe they're named differently?

EDIT: Can't believe how often this happens... Right after I posted I figured it out. The files are "WW_MSTR.xxx" and "WW_MSTR.tfc" for anyone who was wondering!
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-17T15:31:31+00:00
- Post Title: Re: Injustice 2 (PC)

Tool updated:

- RGBA textures support
- support for some more skaletal mesh formats, so all packages will work (not crash)
## Post #48
- Username: hydin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 02, 2016 1:48 pm
- Post datetime: 2018-03-25T16:44:27+00:00
- Post Title: Re: Injustice 2 (PC)

Turns out it was a dumb question. Got the map unpacked and found the statue I was after!

Awesome! Thanks again for the tool
## Post #49
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2018-03-28T17:06:56+00:00
- Post Title: Re: Injustice 2 (PC)

Hello.


I don't find starfire and Darkseid TFC file.

Where are they?



Edite: The files are "SF_MSTR.xxx", "SF_MSTR.tfc" and "DS_MSTR.xxx", "DS_MSTR.tfc"
## Post #50
- Username: Armitag123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 29, 2018 8:30 pm
- Post datetime: 2018-03-29T20:19:10+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Injustice 2 (PC) tool





Tool currently tested to work with character packages only. Usage:

1. Unpack .XXX package with ue3_oodle.bms
2. Drop created .unp file onto the tool. Corresponding .TFC file must be in the same folder
3. Models will be exported in ASCII & SMD formats as usual. ASCII skeletons will be broken, use SMD skeletons. ASCII will have all extra UV pairs.
4. Textures will be exported as DDS and OODLE. You need to unpack OODLE ones with ue3_oodle_dds.bms
Example .bat file to unpack all oodle textures:
Code: Select allfor %%a in (*.oodle) do quickbms.exe ue3_oodle_dds.bms "%%a"
Notes:
- All of the textures I've seen in this game were BC7, so if any other format will be encountered, it will fail.
- Models are split into many exchangeable parts. They will all have their own skeletons, bone names will be compatible. Example:
Видит бог я пытался незная инглиша понять как вашим чудом воспользоваться, но так и не понял
можете в личку написать как ею пользоваться 
очень хочется черепах выдернуть
пока я получаю только пустые текстовые файлы
я как понял русиком вы владеете так как я через сайт гилдора сюда вышел
[Снимок.PNG](https://xentaxbackup.github.io/file/14136_Снимок.PNG)
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-08T07:21:12+00:00
- Post Title: Re: Injustice 2 (PC)

New version (at first post). Fixed the problem with IJ2 tool that caused to only extract models having 0..9 as their number. This new version should extract them all.
## Post #52
- Username: Silante
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 12, 2017 2:55 pm
- Post datetime: 2018-05-22T06:18:40+00:00
- Post Title: Re: Injustice 2 (PC)

So I feel kinda stupid for asking but I'm having some trouble after I use the .bms file. I'm able to unpack the .xxx and turn it into a TFC but when I try to run it through the model.exe program nothing happens. a command prompt shows up like its attempting to convert but no folder is created or anything, I've tried this with multiple characters with no such luck, does anyone have a suggestion?
## Post #53
- Username: amestrisx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 09, 2015 3:27 am
- Post datetime: 2018-07-09T03:56:02+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Silante
>
> So I feel kinda stupid for asking but I'm having some trouble after I use the .bms file. I'm able to unpack the .xxx and turn it into a TFC but when I try to run it through the model.exe program nothing happens. a command prompt shows up like its attempting to convert but no folder is created or anything, I've tried this with multiple characters with no such luck, does anyone have a suggestion?

same for me :/
## Post #54
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-07-16T06:58:34+00:00
- Post Title: Re: Injustice 2 (PC)

Do you have any plans to add animation support?
## Post #55
- Username: ebross67
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 04, 2016 1:42 am
- Post datetime: 2018-07-26T19:28:18+00:00
- Post Title: Re: Injustice 2 (PC)

How do you view .ascii files? I noticed some come in .smd and .ascii. Thanks.
## Post #56
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-07-29T18:27:18+00:00
- Post Title: Re: Injustice 2 (PC)

Any plans for animation support?
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-29T18:32:52+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from TrumpetPro
>
> Any plans for animation support?
no
## Post #58
- Username: virus252525
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 11, 2018 10:21 pm
- Post datetime: 2018-08-11T15:48:13+00:00
- Post Title: Re: Injustice 2 (PC)

Please help, I can't open any of Harley Quinn textures (.dds format), don't try other character textures yet, but I can't open her textures, I try Photoshop, DDS converter tool, online converters, try to open it with Blender (usually Blender can read DDS textures), but no, they are just don't openable, may I'm missing something, maybe there are tools to convert DDS into other image formats, that meant to be used?

Thank you in advance!
## Post #59
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-08-11T16:08:08+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from virus252525
>
> Please help, I can't open any of Harley Quinn textures (.dds format), don't try other character textures yet, but I can't open her textures, I try Photoshop, DDS converter tool, online converters, try to open it with Blender (usually Blender can read DDS textures), but no, they are just don't openable, may I'm missing something, maybe there are tools to convert DDS into other image formats, that meant to be used?

Thank you in advance!
Use Noesis or Intel dds plugin for photoshop (not nvidia one). Injustice 2 along with many other new games use newer dds types which are not supported by most old tools.
## Post #60
- Username: virus252525
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 11, 2018 10:21 pm
- Post datetime: 2018-08-11T16:15:32+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from o0Crofty0o
>
> virus252525 wrote:Please help, I can't open any of Harley Quinn textures (.dds format), don't try other character textures yet, but I can't open her textures, I try Photoshop, DDS converter tool, online converters, try to open it with Blender (usually Blender can read DDS textures), but no, they are just don't openable, may I'm missing something, maybe there are tools to convert DDS into other image formats, that meant to be used?

Thank you in advance!
Use Noesis or Intel dds plugin for photoshop (not nvidia one). Injustice 2 along with many other new games use newer dds types which are not supported by most old tools.

I use Intel's DDS plugin, but opened images are totally black, but I don't try Noesis, thanks for replying and giving information.
## Post #61
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2018-08-16T15:08:18+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Experimental version with map export support



This version is fully functional: it exports models and textures (like before), and also maps.
Maps are only exported as ascii. Skeletal mesh instances will be exported as static models. Only one UV pair is exported into map.

Usage:

1. Run the tool on ...._MapAssets file
In addition to usual export, it will creare 2 folders: skeletalmesh.raw & staticmesh.raw, which will be needed for map export.

2. Run the tool on small main map files, such as MET_Exterior
This will read information about all mesh instances on a map, search for them in above mentioned folders, and export 2 map files, separate for static & skeletal meshes. If some meshes will be missing, it will give warning messages. Some meshes may be in other packages. If you need them, extract them and put in the same folder

Ok so when it tells me a file is missing and I find the missing file. Should i run the file that told me a file was missing again?
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-16T15:56:17+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Lord Kiri
>
> Ok so when it tells me a file is missing and I find the missing file. Should i run the file that told me a file was missing again?
if you want the missing meshes, then yes, run it again
## Post #63
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2018-08-16T16:46:03+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Lord Kiri wrote:Ok so when it tells me a file is missing and I find the missing file. Should i run the file that told me a file was missing again?
if you want the missing meshes, then yes, run it again

Is there an easier way to find missing files? Cause right now i have all .xxx files .unp format and thinking about just extracting all which will take a while because to get missing files i will need to run it about 3 times for each files. So for example there are 3 files (a, b, c) I would need to extract a then b then c and then start over. But injustice 2 has a lot of files. I deleted all the ClothAnims.xxx and Shader files cause i dont believe they would have anything in them that i need.
## Post #64
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2018-08-16T23:24:21+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Lord Kiri
>
> daemon1 wrote:Lord Kiri wrote:Ok so when it tells me a file is missing and I find the missing file. Should i run the file that told me a file was missing again?
if you want the missing meshes, then yes, run it again

Is there an easier way to find missing files? Cause right now i have all .xxx files .unp format and thinking about just extracting all which will take a while because to get missing files i will need to run it about 3 times for each files. So for example there are 3 files (a, b, c) I would need to extract a then b then c and then start over. But injustice 2 has a lot of files. I deleted all the ClothAnims.xxx and Shader files cause i dont believe they would have anything in them that i need.

So i extracted every single UNP file 3 times and i still getting missing files. Im trying to get files from BTC_VehicleCave.unp and BTC_VehicleCave_MapAssets.unp. In the map asset files i got the batmobile model but the textures for the wheels are missing. Also the Batbike has no textures which i can find.
## Post #65
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-17T05:47:44+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Lord Kiri
>
> So i extracted every single UNP file 3 times
why do you extract every file 3 times? i don't understand

i dont remember is there easy way to find missing meshes, also i never had the full game
i hope you can solve this
## Post #66
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2018-08-17T16:01:18+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Lord Kiri wrote:So i extracted every single UNP file 3 times
why do you extract every file 3 times? i don't understand

i dont remember is there easy way to find missing meshes, also i never had the full game
i hope you can solve this

Mr daemon sir. Im uploading the files which are about 600mb to send to you to take a look in .xxx format. However when i extract the unp using the tool. The name list generated shows a bunch of names (things that are in the files im guessing) and it said BTC_VC_Batmobile_Wheels_Color but in the extracted files there is nothing with that name. Also when extracting BTC_VehicleCave it says that its missing BTC_VC_Batmobile_TireA_Sk. I did run into a texture error saying Unsupported Format 3 with other files or something along the lines of this but I dont think thats the problem with extracting the textures. Is it?

Ive also downloaded the game 3 times which takes 2 hours and it takes 8 hours to set up. Cause i thought i was missing files which i was not.
## Post #67
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-17T16:41:43+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Lord Kiri
>
> Im uploading the files which are about 600mb to send to you
sorry i dont have time to look into them now
maybe 1 week or 2 weeks later

so i really hope someone else can help you
## Post #68
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2018-08-17T19:53:47+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Lord Kiri wrote:Im uploading the files which are about 600mb to send to you
sorry i dont have time to look into them now
maybe 1 week or 2 weeks later

so i really hope someone else can help you

These are the files [https://drive.google.com/file/d/1lNZ4YC ... sp=sharing](https://drive.google.com/file/d/1lNZ4YCSc1d_Y1kH8HEhZJt9ZLMLrjK5R/view?usp=sharing)

A lot of textures are missing and i believe only BTC_VC_BatmobileTireA_Sk is the only mesh missing. If you have 25gb available i can send you all the .xxx files (the ones with models and textures) for you

Im only 17 and school is starting back on the 3rd of september for me but I understand that you are busy and I can wait 1 to 2 weeks

108	BTC_VC_Batbike_Body_Color
109	BTC_VC_Batbike_Body_Norm
10A	BTC_VC_Batbike_Body_RMA
10B	BTC_VC_Batbike_Body_Sk_Intrct_Mic
10C	BTC_VC_Batbike_Emis
10D	BTC_VC_Batbike_Emis_Color
10E	BTC_VC_Batbike_Emis_Norm
10F	BTC_VC_Batbike_Emis_RMA
110	BTC_VC_Batbike_Emis_Sk_Mic
111	BTC_VC_Batbike_Parts_Color
112	BTC_VC_Batbike_Parts_Norm
113	BTC_VC_Batbike_Parts_RMA
114	BTC_VC_Batbike_Parts_Sk_Intrct_Mic
115	BTC_VC_Batbike_Parts_Sk_Mic
119	BTC_VC_Batboat_Emis_Color
11A	BTC_VC_Batboat_Emis_Mic
11B	BTC_VC_Batboat_Emis_Norm
11C	BTC_VC_Batboat_Emis_RMA
135	BTC_VC_Batmobile_Bounce
136	BTC_VC_Batmobile_Emis
137	BTC_VC_Batmobile_Emis_Color
138	BTC_VC_Batmobile_Emis_Norm
139	BTC_VC_Batmobile_Emis_RMA
13A	BTC_VC_Batmobile_Emis_Sk_Mic
142	BTC_VC_Batmobile_Tire_St
145	BTC_VC_Batmobile_Wheels
146	BTC_VC_Batmobile_Wheels_Color
147	BTC_VC_Batmobile_Wheels_Mic
148	BTC_VC_Batmobile_Wheels_Norm
149	BTC_VC_Batmobile_Wheels_RMA
14A	BTC_VC_Batmobile_Wheels_Sk_Mic

these are the files that are missing for me that im interested in
## Post #69
- Username: Silante
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 12, 2017 2:55 pm
- Post datetime: 2018-08-17T23:15:27+00:00
- Post Title: Re: Injustice 2 (PC)

So I feel like this might be just an idiot move and i'm just missing the obvious answer. So I've been trying to export the models recently, and I can get the SMD files perfectly fine. Though textures are being exported in the oodle file format. When using the B<S script the files do get converted to DDS file format, and even have size to them but when trying to open them they always show up as full white screens and cant open at all. 

This is not just the effect of DLC outfits (Currently attempting to get the Justice League Aquaman : AQ_DLCHB) Can anyone think of a reason why the textures wont export right, or have any advice.
## Post #70
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2018-08-18T00:13:34+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Silante
>
> So I feel like this might be just an idiot move and i'm just missing the obvious answer. So I've been trying to export the models recently, and I can get the SMD files perfectly fine. Though textures are being exported in the oodle file format. When using the B<S script the files do get converted to DDS file format, and even have size to them but when trying to open them they always show up as full white screens and cant open at all. 

This is not just the effect of DLC outfits (Currently attempting to get the Justice League Aquaman : AQ_DLCHB) Can anyone think of a reason why the textures wont export right, or have any advice.

Make sure you have photoshop installed and also download and install Intel's dds plugin and open the dds textures with photoshop. You can also use noesis and export the textures as a png or other file format and it will work
## Post #71
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-18T05:59:16+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Lord Kiri
>
> only BTC_VC_BatmobileTireA_Sk is the only mesh missing
are you sure this model is in the game? maybe its just an unfinished part
## Post #72
- Username: Silante
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 12, 2017 2:55 pm
- Post datetime: 2018-08-18T06:56:36+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Lord Kiri
>
> Silante wrote:So I feel like this might be just an idiot move and i'm just missing the obvious answer. So I've been trying to export the models recently, and I can get the SMD files perfectly fine. Though textures are being exported in the oodle file format. When using the B<S script the files do get converted to DDS file format, and even have size to them but when trying to open them they always show up as full white screens and cant open at all. 

This is not just the effect of DLC outfits (Currently attempting to get the Justice League Aquaman : AQ_DLCHB) Can anyone think of a reason why the textures wont export right, or have any advice.

Make sure you have photoshop installed and also download and install Intel's dds plugin and open the dds textures with photoshop. You can also use noesis and export the textures as a png or other file format and it will work

I tried that, even attempted opening in other programs to such as pain.net with a .DDS plug in, and it still shows up the same, unknown file format. I'm attempting to redownload, thinking maybe the files got corrupted, Was wondering if I cant get it figured out if anyone would be able to help in getting the textures.
## Post #73
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2018-08-18T14:22:41+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from daemon1
>
> Lord Kiri wrote:only BTC_VC_BatmobileTireA_Sk is the only mesh missing
are you sure this model is in the game? maybe its just an unfinished part

Well I don't really care about the model. Its the missing textures that I really want.
## Post #74
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2018-08-18T14:23:36+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Silante
>
> Lord Kiri wrote:Silante wrote:So I feel like this might be just an idiot move and i'm just missing the obvious answer. So I've been trying to export the models recently, and I can get the SMD files perfectly fine. Though textures are being exported in the oodle file format. When using the B<S script the files do get converted to DDS file format, and even have size to them but when trying to open them they always show up as full white screens and cant open at all. 

This is not just the effect of DLC outfits (Currently attempting to get the Justice League Aquaman : AQ_DLCHB) Can anyone think of a reason why the textures wont export right, or have any advice.

Make sure you have photoshop installed and also download and install Intel's dds plugin and open the dds textures with photoshop. You can also use noesis and export the textures as a png or other file format and it will work

I tried that, even attempted opening in other programs to such as pain.net with a .DDS plug in, and it still shows up the same, unknown file format. I'm attempting to redownload, thinking maybe the files got corrupted, Was wondering if I cant get it figured out if anyone would be able to help in getting the textures.

make sure you are using INTEL DDS PLUGIN and not NVIDIA DDS PLUGIN
## Post #75
- Username: 73lac
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 04, 2017 1:23 pm
- Post datetime: 2018-09-20T09:43:38+00:00
- Post Title: Re: Injustice 2 (PC)

Problem with the bones / bone weights for facial expressions and animation?

Im trying out the extraction tool for the very first time and here is where im at. I was able to extract the game assets to produce .smd and .ascii file formats for the character from the xxx unp and tfc. I also converted the intel dds file format into the nvidia  dds format so my textures would be read by 3ds max. There were a ton of meshes so I matched the based look as close as possible. When I went to go test the facial bones for the characters expressions, while the weights look like they are in the correct positions and weights the entire head of the character moves when moving something simple like the tip of the nose ex. From what I can guess the weights for the face must be messed up or something. Did I do something wrong with the .smd file or should I trying using another program to load the .smd files?
## Post #76
- Username: abstrait
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Dec 05, 2016 12:33 am
- Post datetime: 2018-10-28T19:39:45+00:00
- Post Title: Re: Injustice 2 (PC)

Any idea how this guy managed to add the animations to the rigged models ?
[https://www.youtube.com/watch?v=Avr3J6zIz_M&t=742s](https://www.youtube.com/watch?v=Avr3J6zIz_M&t=742s)
## Post #77
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2018-10-28T22:56:16+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from abstrait
>
> Any idea how this guy managed to add the animations to the rigged models ?
https://www.youtube.com/watch?v=Avr3J6zIz_M&t=742s

Thats from the mobile game.
## Post #78
- Username: abstrait
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Dec 05, 2016 12:33 am
- Post datetime: 2018-10-29T11:20:18+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from LordKiriYT
>
> abstrait wrote:Any idea how this guy managed to add the animations to the rigged models ?
https://www.youtube.com/watch?v=Avr3J6zIz_M&t=742s

Thats from the mobile game.

Oh i see, thanks.
## Post #79
- Username: cruizeez96
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 05, 2018 11:46 pm
- Post datetime: 2018-11-13T22:28:22+00:00
- Post Title: Re: Injustice 2 (PC)

Does anyone know where to find the eyeball/mouth textures for each character? I can find pretty much everything but those textures for the character models.
## Post #80
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2018-11-24T12:46:51+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from cruizeez96
>
> Does anyone know where to find the eyeball/mouth textures for each character? I can find pretty much everything but those textures for the character models.
They're in the startup.xxx container.
## Post #81
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2018-12-06T00:39:38+00:00
- Post Title: Re: Injustice 2 (PC)

Is there any tutorial on how to paint the textures? I figured out how to extract everything, but cannot find anything on painting the textures. I know it has been asked before, and the OP is too lazy to answer, but is there somewhere that I can find the information needed?
## Post #82
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2018-12-07T01:31:42+00:00
- Post Title: Re: Injustice 2 (PC)

I wouldn't say daemon1 is lazy, after all, he created the tools to extract IJ2 models.
## Post #83
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-07T15:58:34+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Shinteo
>
> Is there any tutorial on how to paint the textures? I figured out how to extract everything, but cannot find anything on painting the textures. I know it has been asked before, and the OP is too lazy to answer, but is there somewhere that I can find the information needed?
i have no idea how to paint them thats why i didnt answer
## Post #84
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2019-01-05T02:08:02+00:00
- Post Title: Re: Injustice 2 (PC)

Hey guys,



I'm currently trying to convert some models and textures.

The models themselves went alright but when it comes to the textures the DDS ones are messed up.



they all come out like this: 



This is the only thing that comes out with Photoshop, when I try to open it with Irfan, then it just tells me it's an incorrect DDS file.

I tried using the ue3_oodle_dds.bms file but to no luck.

Am I doing something wrong or am I just missing something?



Edit I'm looking for the BM_DLCHB specificly, so if anyone can help me get these out in high res I'd be ever so thankfull
## Post #85
- Username: dtboost
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 05, 2019 11:33 am
- Post datetime: 2019-04-05T03:38:13+00:00
- Post Title: Re: Injustice 2 (PC)

ok i feel like an absolute idiot asking this and I've spent hours on other forums trying to find the answer.

im trying to get .obj files of red hoods helmets to print miniature versions to display on a shelf

can someone please explain how i go about this with these files.
im using osx and have maya, zbrush, blender, and makehuman

thank you so much to who ever has an answer
## Post #86
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-04-24T22:58:46+00:00
- Post Title: Re: Injustice 2 (PC)

Do you think you can add support for Little Endian? Mortal Kombat 11 uses the same engine as Injustice 2, altho switch version is Little Endian, so would be nice to have support.

[Character Example](https://mega.nz/#!VgUQTKLb!oBZKzGhoOF33m_ltb9XFzpTArerTWV3IvgTDoixszHc)
## Post #87
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-25T04:17:32+00:00
- Post Title: Re: Injustice 2 (PC)

This tool was always little endian. Because its PC.
## Post #88
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-04-25T06:43:35+00:00
- Post Title: Re: Injustice 2 (PC)

Oh, didn't know that.. well seems like the tool doesn't support MK11 [Switch] then, think u can look into that?

Update:
Apparently PC version is the same style also according to a user on Gildor's forums.
## Post #89
- Username: xentaxdork
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 09, 2019 5:36 pm
- Post datetime: 2019-04-25T07:15:48+00:00
- Post Title: Re: Injustice 2 (PC)

daemon1, I can provide game files, if you're willing to look into them.
## Post #90
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-25T18:00:12+00:00
- Post Title: Re: Injustice 2 (PC)


## Post #91
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-04-25T18:15:32+00:00
- Post Title: Re: Injustice 2 (PC)

MK11?
## Post #92
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-04-27T17:19:11+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Faithfullfaun ↑Fri Apr 26, 2019 2:15 am at Fri Apr 26, 2019 2:15 am
>
> MK11?
what else?
## Post #93
- Username: chaeldyo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 28, 2019 10:12 pm
- Post datetime: 2019-04-28T14:14:56+00:00
- Post Title: Re: Injustice 2 (PC)

@daemon
Thank you so much, you have no idea how hard I've been looking for ripped MK11 models :')
Looking forward to the rips, appreciate your hard work very much! 

p.s and thanks too for the injustice 2 models!
## Post #94
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2019-05-01T20:23:19+00:00
- Post Title: Re: Injustice 2 (PC)

If the Process is the same as IJ2 I can start on MK11, I have ripped most of the IJ2 characters with their gears.
## Post #95
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2019-05-01T23:56:44+00:00
- Post Title: Re: Injustice 2 (PC)

Hello, I need help with the game "injustice 2" .
I can't figure out which file (.xxx) is the actual 3D model, (and equipment ) of the character I need .
[https://pp.userapi.com/c855220/v8552201 ... qt74J4.jpg](https://pp.userapi.com/c855220/v855220162/349b3/agOGJqt74J4.jpg)
## Post #96
- Username: askB
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Feb 06, 2012 10:52 am
- Post datetime: 2019-05-02T14:14:12+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Sinnery32 ↑Thu May 02, 2019 7:56 am at Thu May 02, 2019 7:56 am
>
> 
Hello, I need help with the game "injustice 2" .
I can't figure out which file (.xxx) is the actual 3D model, (and equipment ) of the character I need .
https://pp.userapi.com/c855220/v8552201 ... qt74J4.jpg

Which character are you looking for? The model data is stored in a file that looks like this "SZ_MSTR.xxx". That's Sub-Zero's model, and if you wanted Batman, it would be "BM_MSTR.xxx".
## Post #97
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2019-05-02T19:21:14+00:00
- Post Title: Re: Injustice 2 (PC)

dude, thank you so much.
## Post #98
- Username: BlackKaos
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 10, 2016 7:53 am
- Post datetime: 2019-05-10T14:47:35+00:00
- Post Title: Re: Injustice 2 (PC)

Can anyone post the link to the game files again?
## Post #99
- Username: 41cent
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 19, 2017 10:55 am
- Post datetime: 2019-05-25T14:55:56+00:00
- Post Title: Re: Injustice 2 (PC)

Thanks for your great works!
## Post #100
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-27T09:11:34+00:00
- Post Title: Re: Injustice 2 (PC)

New test version with options recently developed for MK11:

- face morph export
- skeletal models mirrored (from left to right)
- proper ASCII skeleton with bone rotations


[Injustice2_model_morph.rar](https://xentaxbackup.github.io/file/16295_Injustice2_model_morph.rar)
## Post #101
- Username: BlackKaos
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 10, 2016 7:53 am
- Post datetime: 2019-05-27T20:13:34+00:00
- Post Title: Re: Injustice 2 (PC)

Can anyone post the link to download the game files please?
## Post #102
- Username: kellernastya
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 20, 2019 12:16 am
- Post datetime: 2019-06-19T17:28:57+00:00
- Post Title: Re: Injustice 2 (PC)

Hey! Guys, who can share game files for noesis? Please, I beg you, I really want to try to work with these models.
## Post #103
- Username: ARRadiation
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 18, 2018 5:11 am
- Post datetime: 2019-08-29T20:43:26+00:00
- Post Title: Re: Injustice 2 (PC)

Has anyone found any way to colour the textures, there are some textures that have detail and painting over it manually would mean losing that detail?

> Reply from kellernastya ↑Thu Jun 20, 2019 1:28 am at Thu Jun 20, 2019 1:28 am
>
> 
Hey! Guys, who can share game files for noesis? Please, I beg you, I really want to try to work with these models.

What files do you need? Are we allowed to share them?
## Post #104
- Username: FredBob12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 06, 2020 6:22 am
- Post datetime: 2020-02-07T00:33:23+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from ARRadiation ↑Fri Aug 30, 2019 4:43 am at Fri Aug 30, 2019 4:43 am
>
> 
Has anyone found any way to colour the textures, there are some textures that have detail and painting over it manually would mean losing that detail?
kellernastya wrote: ↑Thu Jun 20, 2019 1:28 am
Hey! Guys, who can share game files for noesis? Please, I beg you, I really want to try to work with these models.


What files do you need? Are we allowed to share them?

After hourss of torment I finally found the solution. NinjaRipper is great at ripping ALL the textures that the game generates in real-time. All baked up and ready to import. This applies to ALL costumes, combinations and colour schemes. You don't have to draw anything manually. Just re-align them a little in PS to fit the uvs and voila.
 Use the program in the topic to rip the models, then rip just the textures with Ninja.
Really hope this helps everyone.
## Post #105
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-04-22T01:39:45+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from FredBob12 ↑Fri Feb 07, 2020 8:33 am at Fri Feb 07, 2020 8:33 am
>
> 
ARRadiation wrote: ↑Fri Aug 30, 2019 4:43 am
Has anyone found any way to colour the textures, there are some textures that have detail and painting over it manually would mean losing that detail?
kellernastya wrote: ↑Thu Jun 20, 2019 1:28 am
Hey! Guys, who can share game files for noesis? Please, I beg you, I really want to try to work with these models.


What files do you need? Are we allowed to share them?


After hourss of torment I finally found the solution. NinjaRipper is great at ripping ALL the textures that the game generates in real-time. All baked up and ready to import. This applies to ALL costumes, combinations and colour schemes. You don't have to draw anything manually. Just re-align them a little in PS to fit the uvs and voila.
 Use the program in the topic to rip the models, then rip just the textures with Ninja.
Really hope this helps everyone.

For the most part this solution actually does work, kudos however the diffuse or albedo textures are unusually dark for some reason. If I want to port these models to the source engine for sfm or such it won't look good. Any workaround?
## Post #106
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-04-22T03:32:29+00:00
- Post Title: Re: Injustice 2 (PC)

One other thing, the UVs seemed to be messed up on some meshes or incorrect, I'm not sure.



For example this pant texture for Harley simply isn't lining up right no matter what I do, flipping it or scaling it it just doesn't fit. Using normal for reference.
## Post #107
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-04-27T04:02:24+00:00
- Post Title: Re: Injustice 2 (PC)

Has anyone had more luck painting textures?
## Post #108
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-04-27T04:02:50+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from Assasinge ↑Wed Apr 22, 2020 9:39 am at Wed Apr 22, 2020 9:39 am
>
> 
FredBob12 wrote: ↑Fri Feb 07, 2020 8:33 am
ARRadiation wrote: ↑Fri Aug 30, 2019 4:43 am
Has anyone found any way to colour the textures, there are some textures that have detail and painting over it manually would mean losing that detail?



What files do you need? Are we allowed to share them?


After hourss of torment I finally found the solution. NinjaRipper is great at ripping ALL the textures that the game generates in real-time. All baked up and ready to import. This applies to ALL costumes, combinations and colour schemes. You don't have to draw anything manually. Just re-align them a little in PS to fit the uvs and voila.
 Use the program in the topic to rip the models, then rip just the textures with Ninja.
Really hope this helps everyone.


For the most part this solution actually does work, kudos however the diffuse or albedo textures are unusually dark for some reason. If I want to port these models to the source engine for sfm or such it won't look good. Any workaround?

This is the method i been using you can just brighten the exposure in PS.
## Post #109
- Username: cobaltbluebengal
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 04, 2016 12:15 am
- Post datetime: 2021-03-29T11:44:05+00:00
- Post Title: Re: Injustice 2 (PC)

Hi,

Sorry to drag up an old thread, but I've been trying with the tools provided on page one, but I'm having difficulty. Just to clarify incase I'm missing something:

1) Open QuickBMS and use the "ue3_oodle.BMS" plug in
2) Select the XXX for example I'll just say "AA_Exterior_MapAssets.xxx" as it is the first file in the Assets folder
3) Select a location to extract the contents too.
4) Now it starts doing it's thing, but all I get is a black screen with "oodle error : LZ corruption : bad decode len" numerous times with a closing value of 7876 files detected in 31 seconds, 99% press Enter to close the window

5) In the directory selected to extract to, I then have a unp file as described in the instructions, which is around a 10th of the file size of the xxx file, to which I put on the Injustice2_model.exe program. I then get three txt files and a log file, all of which are 0kb with no data inside...


What am I doing wrong for someone who has only really dabbled with umodel before rather than BMS script?
## Post #110
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-29T11:56:39+00:00
- Post Title: Re: Injustice 2 (PC)

old or broken QuickBMS version
## Post #111
- Username: cobaltbluebengal
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 04, 2016 12:15 am
- Post datetime: 2021-03-29T12:33:12+00:00
- Post Title: Re: Injustice 2 (PC)

Got it,  just updated from a mirror site as for some reason my firewall was going nuts on their website. Managed to export okay, just need to use Neosis and follow the next steps
## Post #112
- Username: Zodmcfly
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 07, 2021 8:41 am
- Post datetime: 2021-08-07T00:44:55+00:00
- Post Title: Re: Injustice 2 (PC)

Does anyone have the gear files for the justice league batman gear set?
Thanks in advance
## Post #113
- Username: tsfgsg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 06, 2021 11:58 pm
- Post datetime: 2021-09-18T06:51:31+00:00
- Post Title: Re: Injustice 2 (PC)

Hey all! I've tried to open several .xxx files using QuickBMS and the "ue3_oodle.bms". Each time, it scans through tons of files and when finished it says 0 files were found but a ton of logs. Pressing Enter then creates a .unp file with a large file size, but dragging that .unp onto the tool only yields a windows batch file and a bunch of TXT log files, all under 10kb... Any idea why no files are being found? I've tried with multiple characters as well as the AA_Exterior_MapAssets.xxx file which is the first huge file in the assets folder. Thanks in advance!




cap 1.PNG (41.69 KiB) Viewed 290 times
## Post #114
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2021-09-20T00:15:42+00:00
- Post Title: Re: Injustice 2 (PC)

Just tried out AA_Exterior_MapAssets.xxx, and everything works fine.  I used quickbms_4gb_files.exe with ue3_oodle.bms to unpack the xxx file, then dragged the resulting unp file onto Injustice2_model_morph.exe (the last release of the IJ2 tool).
## Post #115
- Username: tsfgsg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 06, 2021 11:58 pm
- Post datetime: 2021-09-20T05:47:59+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from nightwolf1982 ↑Mon Sep 20, 2021 8:15 am at Mon Sep 20, 2021 8:15 am
>
> 
Just tried out AA_Exterior_MapAssets.xxx, and everything works fine.  I used quickbms_4gb_files.exe with ue3_oodle.bms to unpack the xxx file, then dragged the resulting unp file onto Injustice2_model_morph.exe (the last release of the IJ2 tool).

AHA! Thanks so much, I was using the original release of the IJ2 tool, didn't realize another version had been released elsewhere in this thread. Just tested with that file as well as Wonder Woman and was able to extract everything. I appreciate the help!
## Post #116
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2021-09-22T20:59:02+00:00
- Post Title: Re: Injustice 2 (PC)

Could anyone who has the game files pleeeease extract & send me the FBX file of Hal Jordan? Been waiting for someone to extract him for years and all I can find is some of the shitty phone game models, not the actual PC/Console ones.
## Post #117
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2022-01-12T16:13:48+00:00
- Post Title: Re: Injustice 2 (PC)

This is ancient stuff...

I am trying to convert the Harley Quinn DLC textures from Oodle to DDS.

the resulting DDS file is unreadable by everything I try.

Could it be the Legendary edition have changed the encoding?
## Post #118
- Username: BeltwayEX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 13, 2019 7:27 am
- Post datetime: 2022-01-27T06:43:22+00:00
- Post Title: Re: Injustice 2 (PC)

Its been so many years and I returned here, since i tought was gonna work

How do you end making the textures work properly?
Do you need to paint them manually or what?

I was able to etract the models, the oodle and all that thing, models work fine, but all the textures are either washed or grey

I tought that was just a mere problem with using alpha (as it worked with a recently extracted model) but seems not
## Post #119
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-06-09T04:05:35+00:00
- Post Title: Re: Injustice 2 (PC)

Well, here's a weird issue.  I'm trying to extract character models from IJ2 PC, but I can't find the Eye/Mouth textures anywhere.  I know they used to be in the startup.xxx container, but when I export that container there are no eye/mouth textures.
## Post #120
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-06-10T02:25:09+00:00
- Post Title: Re: Injustice 2 (PC)

OK, more weirdness...  So, I saw on another forum (Gildor's, I believe) that with Injustice 1, people were sometimes having to rerun the tool for that game two or three times to get files to extract.  That got me wondering, so I tried it with daemon1's tool and Lo and Behold, it worked!!  I was finally able to extract the textures from startup.xxx!

The weird part is, though, I don't remember ever having to do this in the past.  Has anyone else encountered this?
## Post #121
- Username: rinsnap
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 11, 2022 12:56 pm
- Post datetime: 2022-08-11T05:13:29+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from nightwolf1982 ↑Fri Jun 10, 2022 10:25 am at Fri Jun 10, 2022 10:25 am
>
> 
OK, more weirdness...  So, I saw on another forum (Gildor's, I believe) that with Injustice 1, people were sometimes having to rerun the tool for that game two or three times to get files to extract.  That got me wondering, so I tried it with daemon1's tool and Lo and Behold, it worked!!  I was finally able to extract the textures from startup.xxx!

The weird part is, though, I don't remember ever having to do this in the past.  Has anyone else encountered this?

How exactly did you find the eye and mouth textures? I tried running the tool around 3 times and still couldn't find the textures.
## Post #122
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-08-12T23:08:11+00:00
- Post Title: Re: Injustice 2 (PC)

I knew from previous attempts where the eye and mouth textures were stored
## Post #123
- Username: rinsnap
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 11, 2022 12:56 pm
- Post datetime: 2022-08-13T04:24:55+00:00
- Post Title: Re: Injustice 2 (PC)

Would you be able to share where that is? I feel like I've checked everywhere...
## Post #124
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-08-14T04:14:27+00:00
- Post Title: Re: Injustice 2 (PC)

It's in the startup.xxx
## Post #125
- Username: DR43
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 16, 2022 5:34 am
- Post datetime: 2022-08-15T21:40:41+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from askB ↑Thu May 02, 2019 10:14 pm at Thu May 02, 2019 10:14 pm
>
> 
Sinnery32 wrote: ↑Thu May 02, 2019 7:56 am
Hello, I need help with the game "injustice 2" .
I can't figure out which file (.xxx) is the actual 3D model, (and equipment ) of the character I need .
https://pp.userapi.com/c855220/v8552201 ... qt74J4.jpg


Which character are you looking for? The model data is stored in a file that looks like this "SZ_MSTR.xxx". That's Sub-Zero's model, and if you wanted Batman, it would be "BM_MSTR.xxx".

Supergirl files are in SG_MSTR.xxx, but where are the skin files like powergirl?
## Post #126
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-08-16T04:55:30+00:00
- Post Title: Re: Injustice 2 (PC)

Skin files like Powergirl are stored in the CHAR_HeroName_X.xxx files, so Powergirl is in CHAR_Supergirl_A.xxx
## Post #127
- Username: DR43
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 16, 2022 5:34 am
- Post datetime: 2022-08-17T03:13:33+00:00
- Post Title: Re: Injustice 2 (PC)

Much appreciated.
## Post #128
- Username: DR43
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 16, 2022 5:34 am
- Post datetime: 2022-08-21T01:15:53+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from nightwolf1982 ↑Fri Jun 10, 2022 10:25 am at Fri Jun 10, 2022 10:25 am
>
> 
OK, more weirdness...  So, I saw on another forum (Gildor's, I believe) that with Injustice 1, people were sometimes having to rerun the tool for that game two or three times to get files to extract.  That got me wondering, so I tried it with daemon1's tool and Lo and Behold, it worked!!  I was finally able to extract the textures from startup.xxx!

The weird part is, though, I don't remember ever having to do this in the past.  Has anyone else encountered this?

I'm having the same problem, I can't find the eye mouth texture from startup.xxx
## Post #129
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-08-21T05:11:59+00:00
- Post Title: Re: Injustice 2 (PC)

You have to extract 3 or 4 times
## Post #130
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-08-21T05:17:21+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from nightwolf1982 ↑Fri Jun 10, 2022 10:25 am at Fri Jun 10, 2022 10:25 am
>
> 
The weird part is, though, I don't remember ever having to do this in the past.  Has anyone else encountered this?
Thats windows 10/11. It just breaks any tool execution in random moments. I dont know if its windows bug or "defender" feature, but thats it.
## Post #131
- Username: Premium8348
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 06, 2022 2:53 am
- Post datetime: 2022-12-23T20:33:48+00:00
- Post Title: Re: Injustice 2 (PC)

This seems great!! I am having issues with the bat code though, with it running but not exporting any files. If anyone could help that would be wonderful, thanks

Never mind I'm just stupid, it works absolutely brilliantly, and this tool is brilliant, and so easy to use lol
## Post #132
- Username: DR43
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 16, 2022 5:34 am
- Post datetime: 2023-01-09T13:34:11+00:00
- Post Title: Re: Injustice 2 (PC)

Hi guys, happy new year, do u know if there's a way to import lot of mesh.ascii files at once to blender?
It would save a lot of time.
## Post #133
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-09T20:48:20+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from DR43 ↑Mon Jan 09, 2023 9:34 pm at Mon Jan 09, 2023 9:34 pm
>
> ...do u know if there's a way to import lot of mesh.ascii files at once to blender?...
The only way is if the author of the original python script adds support in the python code, other wise your stuck importing one at a time.
## Post #134
- Username: Premium8348
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 06, 2022 2:53 am
- Post datetime: 2023-01-22T20:38:38+00:00
- Post Title: Re: Injustice 2 (PC)

I'm having some issues with opening some .tfc files, with it saying that it is a ridiculous file size, which I think is a script error, though i'm not sure. Any help would be fantastic, thanks
## Post #135
- Username: gnilrad
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Sep 09, 2020 4:48 am
- Post datetime: 2023-03-05T00:02:25+00:00
- Post Title: Re: Injustice 2 (PC)

> Reply from tsfgsg ↑Sat Sep 18, 2021 2:51 pm at Sat Sep 18, 2021 2:51 pm
>
> 
Hey all! I've tried to open several .xxx files using QuickBMS and the "ue3_oodle.bms". Each time, it scans through tons of files and when finished it says 0 files were found but a ton of logs. Pressing Enter then creates a .unp file with a large file size, but dragging that .unp onto the tool only yields a windows batch file and a bunch of TXT log files, all under 10kb... Any idea why no files are being found? I've tried with multiple characters as well as the AA_Exterior_MapAssets.xxx file which is the first huge file in the assets folder. Thanks in advance!


cap 1.PNG

I'm having this same problem except only with map files. I can extract characters fine but once I try the tools on the maps, it gives me a big .unp that spits out a few TXT files that are like no size with nothing in them and like 10 textures. The QuickBMS says 0 files found but like thousands of logs, I am trying to do BGND_FortressOfSolitude_MapAssets.xxx
Thanks in advance
