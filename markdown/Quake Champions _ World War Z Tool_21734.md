## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-10T20:55:20+00:00
- Post Title: Quake Champions \ World War Z Tool

The format ended up being harder than I thought. So I will start with basic support and improve the tool as I have time to work on it.

UPDATE
The tool now supports skeleton/skinning and type of models that can be loaded increased a lot. It will also work with World War Z models.

Tool overview and example exported model



World War Z Character



How to use

Load

TPL : Loads models in tpl files. tpl_data needs to be in the same folder (if used). 
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
Textures : Select a folder containing pct texture files. They will be exported in PNG format.
Note  : Models and textures will be exported into the folder Export.
Download : [https://www.mediafire.com/file/r8v61kt9 ... 1.rar/file](https://www.mediafire.com/file/r8v61kt9lq9ie0p/QCViewer_U1.rar/file)
## Post #2
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2020-02-10T22:32:49+00:00
- Post Title: Quake Champions \ World War Z Tool

Thats really dope, but how to unpack?
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-10T22:38:28+00:00
- Post Title: Quake Champions \ World War Z Tool

> Reply from georgesears ↑Tue Feb 11, 2020 6:32 am at Tue Feb 11, 2020 6:32 am
>
> 
Thats really dope, but how to unpack?

Use the attached bms script. Tested with the files from Steam (2019 winter update). Might not work with any other versions.
[quake_champions_bms.rar](https://xentaxbackup.github.io/file/17482_quake_champions_bms.rar)
## Post #4
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2020-02-11T11:15:44+00:00
- Post Title: Quake Champions \ World War Z Tool

> Reply from akderebur ↑Tue Feb 11, 2020 6:38 am at Tue Feb 11, 2020 6:38 am
>
> 
Use the attached bms script. Tested with the files from Steam (2019 winter update). Might not work with any other versions.

BMS Script works with current game client
In my case program loads every model of selected character, is that correct?
Also there are some loos vertices or... balls?
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-11T11:27:14+00:00
- Post Title: Quake Champions \ World War Z Tool

> Reply from georgesears ↑Tue Feb 11, 2020 7:15 pm at Tue Feb 11, 2020 7:15 pm
>
> 
In my case program loads every model of selected character, is that correct?
Yes, all of the skins are inside the same file, so all of them will be loaded. Some of the mesh names might be wrong for some characters. Like it says torso, but it is a legs mesh. I will try to fix that. 

> Reply from georgesears ↑Tue Feb 11, 2020 7:15 pm at Tue Feb 11, 2020 7:15 pm
>
> 
Also there are some loos vertices or... balls?
Don't worry about those. They are for representing skeleton/nodes. They won't effect mesh export.
## Post #6
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2020-02-11T11:59:58+00:00
- Post Title: Quake Champions \ World War Z Tool

Should've clarified, tool exports ALL textures in folder)))
Also, after texture export i've tried model export, and it've created Textures.obj and .mtl in export/textures folder. 
Just letting you know.
After that i've tried model export second time and it created correct folder and file names.
Checking obj import

EDIT
Some UV's are broken on Doom Slayer armor (mortal_legs_va/mortal_torso_va)


EDIT 2
Weapon models either won't load or strobes in viewport like crazy
There are also problems with smoothing here and there
I really like where it's going though, those models weren't availible for too long
Can't wait for updates!
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-11T14:30:34+00:00
- Post Title: Quake Champions \ World War Z Tool

Thanks for testing. I will try to fix those problems over time. 

Currently I haven't checked anything other than "cc_" character models, so other stuff might fail like you said. My first priority will be to get character models working with skinning. After that I can take a look and weapons and other props.
## Post #8
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2020-02-20T10:46:18+00:00
- Post Title: Quake Champions \ World War Z Tool

Will there be a plan to support World War Z meshes? I tried WWZ .tpls with your current state of the tool and it only loads bone nodes


I only have the files from early release, and archive extraction works well with 7zip while textures are readable with QCPCT tools. I'd see if I could procure files from latest release, but if anyone has them feel free to post attach some .tpl samples (favorably from latest releases).
## Post #9
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-20T11:08:09+00:00
- Post Title: Quake Champions \ World War Z Tool

> Reply from ventuhr ↑Thu Feb 20, 2020 6:46 pm at Thu Feb 20, 2020 6:46 pm
>
> 
Will there be a plan to support World War Z meshes?
Maybe, at some point. I am working on another tool now. After that I am planning to add skinning support for QC and fix the current issues. Especially with uvs.

I haven't checked the model format of World War Z, but if the bones are getting loaded fine, then it might not be far away from QC. I will take a look some time.
## Post #10
- Username: SinkingSponge
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 19, 2020 1:27 am
- Post datetime: 2020-02-21T02:14:07+00:00
- Post Title: Quake Champions \ World War Z Tool

Been giving this tool a try now for at least 3 days, managed to get some pretty decent results out of it, one thing i noticed last night is that, when using Ninja Ripper to get hold of some the models, Mainly for the weights for references so i can create rigs with them for Blender, the models grabbed by this tool seem to have under half the vertices as if they're LOD versions, Just thought i'd mention it cause i feel like i'm doing something wrong.
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-21T07:50:36+00:00
- Post Title: Quake Champions \ World War Z Tool

> Reply from SinkingSponge ↑Fri Feb 21, 2020 10:14 am at Fri Feb 21, 2020 10:14 am
>
> 
the models grabbed by this tool seem to have under half the vertices as if they're LOD versions
That is weird. Actually there is one high poly mesh and 4 LOD levels in the file. The tool should be exporting the high poly one only, skipping the LODs. Are you also getting separate LOD meshes when using Ninja?

Edit:

I have checked the meshes by also including vertex counts, and I am positive that the one with most vertices is getting exported. The tool won't export those "LODX" meshes.



Dunno how Ninja exports higher poly ones. Maybe the game is loading some meshes from another file, but I would doubt that there would be higher poly ones of each of these skins in some other file. Maybe just the base skin.
## Post #12
- Username: SinkingSponge
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 19, 2020 1:27 am
- Post datetime: 2020-02-21T18:12:08+00:00
- Post Title: Quake Champions \ World War Z Tool

When i'm getting the meshes from Ninja Ripper it gives me 2 meshes of each piece, both identical
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-21T18:19:05+00:00
- Post Title: Quake Champions \ World War Z Tool

> Reply from SinkingSponge ↑Sat Feb 22, 2020 2:12 am at Sat Feb 22, 2020 2:12 am
>
> 
When i'm getting the meshes from Ninja Ripper it gives me 2 meshes of each piece, both identical

Hmm I don't quite know the way NinjaRipper operates, so can't tell much. If you send me an example ripped mesh I can compare it to the data I am getting from the model files. From my side it seems that the tool loads the correct vertex/face data.
## Post #14
- Username: SinkingSponge
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 19, 2020 1:27 am
- Post datetime: 2020-02-21T18:38:56+00:00
- Post Title: Quake Champions \ World War Z Tool

> Reply from akderebur ↑Sat Feb 22, 2020 2:19 am at Sat Feb 22, 2020 2:19 am
>
> 
SinkingSponge wrote: ↑Sat Feb 22, 2020 2:12 am
When i'm getting the meshes from Ninja Ripper it gives me 2 meshes of each piece, both identical


Hmm I don't quite know the way NinjaRipper operates, so can't tell much. If you send me an example ripped mesh I can compare it to the data I am getting from the model files. From my side it seems that the tool loads the correct vertex/face data.

I'll grab you Sorlag's chest piece from my rip archive.

Here you go: [https://drive.google.com/file/d/1k7KuOI ... 5e7_i/view](https://drive.google.com/file/d/1k7KuOIxGJ2vbfguZ3FzxgrElxOk5e7_i/view)

And here's the same chest piece from QCViewer: [https://drive.google.com/open?id=1w_09P ... 9A-fBuUaYG](https://drive.google.com/open?id=1w_09Pf7OMwlxY8LU0nRqIt9A-fBuUaYG)

Edit: Heads up also that the uvs on the meshes from Ninja Ripper are really, really broken.
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-22T09:09:15+00:00
- Post Title: Quake Champions \ World War Z Tool

> Reply from SinkingSponge ↑Sat Feb 22, 2020 2:38 am at Sat Feb 22, 2020 2:38 am
>
> 
I'll grab you Sorlag's chest piece from my rip archive.

Thanks for the sample. Indeed it is higher poly. I have checked the "cc_" files again and it seems that the tool is using ALL possible vertices/indices in the file. So that mesh is not coming from "cc_" files.

I haven't tested but I think you might not see a difference in vertex count with skin parts. My guess is that only the base meshes have a higher poly versions and are being loaded from somewhere else. Maybe the "mm_" files. "cc_" files are probably just meant for skin parts, and contain lower poly base meshes; since they won't be seen under the armor anyway. We will see for sure when the tool supports more tpl files.
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-23T17:00:51+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from SinkingSponge ↑Sat Feb 22, 2020 2:38 am at Sat Feb 22, 2020 2:38 am
>
> 
I'll grab you Sorlag's chest piece from my rip archive.
I have started to update the tool and got the "mm_" files loading. I have found the Sorlag high poly torso there  Same as the vertex count of the NinjaRipper mesh you uploaded.



So it seems like "mm_" is also needed for some stuff. Not all meshes seems to be higher poly than "cc_". Some of them are, some are not. Anyway I will do more tests, do couple fixes and release the newer version some time.
## Post #17
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-28T16:24:37+00:00
- Post Title: Re: Quake Champions Tool [WIP]

NEW UPDATE

- Skeleton / skinning support
- Secondary uv support
- Can load newer model types (mm_ / gore / some weapons)
- World War Z support
- Fixed wrong mesh names

Large models might take some time to load.
## Post #18
- Username: xrevo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 09, 2016 8:56 am
- Post datetime: 2020-02-29T07:25:49+00:00
- Post Title: Re: Quake Champions Tool [WIP]

The tool is nice and im thankful for it, however UVs on some meshes are off either by a bit or completely as well as flipped on the Y axis, some are also scaled incorrectly, typically needing a 2x resize (normally on torso meshes from what ive seen). Most of the weapons ive tried are just floating vertices or whatever in the viewport and export 2kb files of nothing. Glad you got skeletons working though!
## Post #19
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-29T08:27:51+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from xrevo ↑Sat Feb 29, 2020 3:25 pm at Sat Feb 29, 2020 3:25 pm
>
> 
however UVs on some meshes are off either by a bit or completely
If you can tell me the file and mesh name that has this problem I can take a look. Also some meshes have 2 uv sets. Make sure to check both of them.

> Reply from xrevo ↑Sat Feb 29, 2020 3:25 pm at Sat Feb 29, 2020 3:25 pm
>
> 
flipped on the Y axis
That is done on purpose since my tool will also export the textures flipped like that. It shouldn't be a problem really. You can flip the uvs again in Noesis with a single click 

> Reply from xrevo ↑Sat Feb 29, 2020 3:25 pm at Sat Feb 29, 2020 3:25 pm
>
> 
Most of the weapons ive tried are just floating vertices or whatever in the viewport
They are not floating vertices, just nodes/skeleton. My main focus was character models, so weapons might not work so good at the moment.
## Post #20
- Username: xrevo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 09, 2016 8:56 am
- Post datetime: 2020-02-29T09:45:35+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from akderebur ↑Sat Feb 29, 2020 4:27 pm at Sat Feb 29, 2020 4:27 pm
>
> 
If you can tell me the file and mesh name that has this problem I can take a look. Also some meshes have 2 uv sets. Make sure to check both of them.

So far Ranger and BJ are the only meshes ive exported and messed with, the UVs for their heads are off by a little bit which can be fixed by constraining the UV to the image/texture bounds. The other thing I've noticed is the torso UV for BJ's wolf 2 outfit is smaller than it should be and the UV needs to be scaled 2x after centering the primary islands.

Also I exported them as FBX from noesis and they only have one UV set (at least for these that I tried), ticking the flip UV option definitely helped.
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-29T10:05:09+00:00
- Post Title: Re: Quake Champions Tool [WIP]

Thanks for reporting, I will check them out to see the problem.

> Reply from xrevo ↑Sat Feb 29, 2020 5:45 pm at Sat Feb 29, 2020 5:45 pm
>
> 
they only have one UV set (at least for these that I tried)
Not all of them have multiple uvs, so no problem. I mostly encountered that in WWZ models.
## Post #22
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2020-02-29T18:49:14+00:00
- Post Title: Re: Quake Champions Tool [WIP]

Glad to see this tool updated, thank you very much!
The mm_doomslayer loads fine, but cosmetic addons are still have broken UV's
EDIT. Also weapons still won't work, mostly)
## Post #23
- Username: Shokes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 04, 2020 2:12 pm
- Post datetime: 2020-03-04T06:27:33+00:00
- Post Title: Re: Quake Champions Tool [WIP]

Don't know what I'm doing wrong but I can't seem to get anything to export properly. Some meshes import properly (some just outright freeze the program), but I can never see anything besides an armature. Exporting gives a similarly expected result of no actual mesh and occasionally Noesis seems to jumble the skeleton around. Importing whatever Noesis spits out just gives a dummy mesh with a tiny armature.

The TPLs I have were extracted with the BMS script from the most recent non-PTS update. Running QCViewer through wine/Proton 5.0-3 if that makes a difference.
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-04T07:36:22+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from Shokes ↑Wed Mar 04, 2020 2:27 pm at Wed Mar 04, 2020 2:27 pm
>
> 
Running QCViewer through wine/Proton 5.0-3 if that makes a difference.
I don't know myself, maybe it does . Some unity functionality might not be working properly under wine?

If you are trying weapon models it is normal that most of them are not getting loaded. Characters should be fine though. Can you pm me 2-3 of the tpls you are trying to load?
## Post #25
- Username: Shokes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 04, 2020 2:12 pm
- Post datetime: 2020-03-07T03:36:56+00:00
- Post Title: Re: Quake Champions Tool [WIP]

After using this for a bit, I've noticed a few things:
- Both UVs and textures are flipped. Is there a technical reason for this? I see you mentioned it earlier.
- UV maps for heads, the eyeshadow models, and eyelashes are all mangled for several of the champs at least for the mm models
 - - So far affects at least Eisen, Galena, Slash, Keel, Athena and Ranger

- Strogg's mm model doesn't export properly and Noesis crashes when trying to convert it.
- Cubemaps I believe are in BC6 which would need to be exported to something like EXR since that's an HDR format
- Only the first block of the shader textures are exported. Those handful of PCTs have multiple textures in them.
- Athena's lore hair doesn't get ripped, period, unless it's hidden in another TPL

I understand this is a WIP. Just wanted to note my observations for future reference.
## Post #26
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-09T08:42:47+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from Shokes ↑Sat Mar 07, 2020 11:36 am at Sat Mar 07, 2020 11:36 am
>
> 
- UV maps for heads, the eyeshadow models, and eyelashes are all mangled for several of the champs at least for the mm models
Yes, uv maps are the main issue. Some of them has that problem. Maybe I am missing some extra data to load them correctly. Might be a scale value or uv bounds, but I am not sure. So I am aware of the issue, but don't know how to fix it atm 

I will not bother with cubemaps or shader textures. You can try loading them with QPCT.
## Post #27
- Username: Shokes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 04, 2020 2:12 pm
- Post datetime: 2020-03-10T05:47:00+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from akderebur ↑Mon Mar 09, 2020 4:42 pm at Mon Mar 09, 2020 4:42 pm
>
> I will not bother with cubemaps or shader textures. You can try loading them with QPCT.

QPCT doesn't want to work for me, but I've been able to get most of the textures with Rawtex. Cubemaps are another mess that I haven't figured out yet, but my concern at the moment is getting the correct blue channels for the normal maps. I've managed to rebuild them with ImageMagick and the power of math, but your program is giving completely different results so I'm wondering if I slipped and the blue channel is actually in the PCT somewhere.

For instance, this image is the blue channel for the eye normals I get with this program:

[](https://i.imgur.com/V7ynC1N.png)

and this is the one I "rebuilt":

[](https://i.imgur.com/DiNpFsX.png)

This is part of the script I've been using:

```
convert "$f" -channel B -fx "sqrt(1-((2r-1)^2+(2g-1)^2))/2+0.5" normals_fixed/$f
```

I've tested this with other normals and it gives nearly identical results to baked normals, minus a tiny amount of noise at points where the function is discontinuous and the result becomes zero internally.
## Post #28
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2020-04-02T23:27:39+00:00
- Post Title: Re: Quake Champions Tool [WIP]

Are you still giving this tool some updates perhaps? I'm currently found and making a list of quake champions tpls that doesn't work with this tool.
## Post #29
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-03T08:20:08+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from ventuhr ↑Fri Apr 03, 2020 7:27 am at Fri Apr 03, 2020 7:27 am
>
> 
Are you still giving this tool some updates perhaps?

Not working on it actively. Working on other games atm. I might return to this format later.
## Post #30
- Username: Korsakoff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 15, 2020 5:18 pm
- Post datetime: 2020-04-15T09:32:02+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from akderebur ↑Tue Feb 11, 2020 6:38 am at Tue Feb 11, 2020 6:38 am
>
> 
georgesears wrote: ↑Tue Feb 11, 2020 6:32 am
Thats really dope, but how to unpack?


Use the attached bms script. Tested with the files from Steam (2019 winter update). Might not work with any other versions.

im very sorry, but how to use .bms script to convert .pak?
im newbie 

--
i want to rip some architecture models to make same maps for Killing Floor 2 and maybe other UE3-UE4 engine games.
just need to rip 3d models and textures.
## Post #31
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-15T12:09:51+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from Korsakoff ↑Wed Apr 15, 2020 5:32 pm at Wed Apr 15, 2020 5:32 pm
>
> 
how to use .bms script to convert .pak?
Use it with QuickBMS : [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)

> Reply from Korsakoff ↑Wed Apr 15, 2020 5:32 pm at Wed Apr 15, 2020 5:32 pm
>
> 
i want to rip some architecture models
Map models are not supported. You can give it a try, but most probably the tool won't load them properly.
## Post #32
- Username: Korsakoff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 15, 2020 5:18 pm
- Post datetime: 2020-04-15T12:27:11+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from akderebur ↑Wed Apr 15, 2020 8:09 pm at Wed Apr 15, 2020 8:09 pm
>
> 
Korsakoff wrote: ↑Wed Apr 15, 2020 5:32 pm
how to use .bms script to convert .pak?

Use it with QuickBMS : https://aluigi.altervista.org/quickbms.htm
Korsakoff wrote: ↑Wed Apr 15, 2020 5:32 pm
i want to rip some architecture models

Map models are not supported. You can give it a try, but most probably the tool won't load them properly.

thank you a lot, dear
you right, i cant view geometry models 
just not loading
## Post #33
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-09-23T08:52:49+00:00
- Post Title: Re: Quake Champions Tool [WIP]

> Reply from akderebur ↑Fri Apr 03, 2020 4:20 pm at Fri Apr 03, 2020 4:20 pm
>
> 
ventuhr wrote: ↑Fri Apr 03, 2020 7:27 am
Are you still giving this tool some updates perhaps?


Not working on it actively. Working on other games atm. I might return to this format later.

I want to continue developing this World War Z tool and make a blender/Noesis script instead. Is there anyone who could share with a template? It's pain to analyse .tpl file structure.
## Post #34
- Username: Rifat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 28, 2022 3:20 am
- Post datetime: 2022-03-27T19:38:34+00:00
- Post Title: Re: Quake Champions Tool [WIP]

hello pls link give a QCviewer
## Post #35
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2022-06-16T22:57:53+00:00
- Post Title: Re: Quake Champions Tool [WIP]

I can't get any WWZ characters to load at all. I don't think there is a problem with the tool, it's just something I'm doing wrong on my end but I just can't work out what.  

Thanks for the tool though
