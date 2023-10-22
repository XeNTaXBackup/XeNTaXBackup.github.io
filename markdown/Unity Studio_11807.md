## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-19T00:11:28+00:00
- Post Title: Unity Studio

Unity Studio is a tool for exploring, extracting and exporting assets from Unity games and apps.

It is the continuation of my Unity Importer script for 3ds Max, and comprises all my research and reverse engineering of Unity file formats. It has been thoroughly tested with Unity builds from most platforms, ranging from Web, PC, Linux, MacOS to Xbox360, PS3, Android and iOS, and it is currently maintained to be compatible with Unity builds from 2.5.0 up to the latest version.

Download: app.box.com/UnityStudio
GitHub: https://github.com/RaduMC/UnityStudio

[](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_Kerbal_hierarchy.png.html) [](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_Kerbal_export.png.html) [](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_Kerbal_shader.png.html)
[](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_Hstone_texture.png.html) [](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_Hgo_texture.png.html) [](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_Hgo_audio.png.html)
[](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_Spunch_font.png.html) [](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_Hsniper_text.png.html) [](http://s831.photobucket.com/user/Chipicao/media/Unity%20Studio/UnityStudio_GoH_diagnostics.png.html)

Current features:
Export to FBX, with complete hierarchy, transformations, materials and textures
Geometry is exported with normals, tangents, UV coordinates, vertex colors and deformers.
Skeleton nodes can be exported either as bones or dummy deformers.
Extraction of assets that can be used as standalone resources:
Textures: DDS (Alpha8bpp, ARGB16bpp, RGB24bpp, ARGB32bpp, BGRA32bpp, RGB565, DXT1, DXT5, RGBA16bpp)
PVR (PVRTC_RGB2, PVRTC_RGBA2, PVRTC_RGBA4, PVRTC_RGB4, ETC_RGB4)
Audio clips: mp3, ogg, wav, xbox wav (including streams from .resS files)
Fonts: ttf, otf
Text Assets
Shaders
Real-time preview window for the above-mentioned assets
Diagnostics mode with useful tools for research
UI guide:
Most elements have tooltips or are self-explanatory.
File -> Load file/folder will open Assetfiles and load their assets
Load file can also decompress and load bundle files straight into memory
File -> Extract bundle/folder can extract Assetfiles from bundle files compressed with lzma or l4z
Scene Hierarchy search box - search nodes using * and ? wildcards; press Enter to loop through results or Ctrl+Enter to select all matching nodes
Asset List filter box - enter a keyword to filter the list of available assets; wildcards are added automatically
Diagnostics - press Ctrl+Alt+D to bring up a hidden menu and a new list
Bulid class structures will create human-readable structures for each type of Unity asset; available only in Web builds!
FAQ:
- How can I view the 3D models?
- Export the models you want to FBX and load the file in any compatible app. Examples: 3ds Max, Maya, FBX Review

- Why can't I preview PVR textures? How do I open these?
- PVR is an image format specific to mobile platforms. These cannot be previewed at the moment, you need to extract and use PVRTexTool to open them

- I loaded a game but I can't find all 3D models and assets. Is there something wrong?
- Some games, particularly on mobile platforms, will download additional files after they are installed. You'll need those files in order to access all assets.

- How do I get mobile and Web games on my PC? Where do I find the additional files downloaded by a game?
- Read my downloading guide available here: [viewtopic.php?f=16&t=11154](http://forum.xentax.com/viewtopic.php?f=16&t=11154)

- What are all these file types and how do I open each one?
- Here's a quick summary of unity file types:
Bundles - packages with one or more files inside, compressed or not
- extensions: .unity3d, .assetbundle, .bundle, .bytes
- usually found in web apps or downloadable content
- they contain the actual asset files
- can be extracted with Extract bundle/folder options from Unity Studio, or with quickbms
Assetfiles - contain serialized game resources (assets)
- filename format / extensions: maindata,"level#, *.assets, *.sharedAssets, CustomAssetBundle-*, CAB-*, BuildPlayer-*
- these are the files that you can load/import in Unity Studio
- you can get these files from bundles, ipa/apk mobile app packages, or directly from PC games
unitypackage - asset packages exported from Unity Editor to be transfered from project to project
- you will not find these in published games or apps
- they are basically tar.gz archives and can be extracted if needed
- inside you will find files named "metadata" and "asset"
- metadata is an assetfile - same as no. 2
- asset can be either an assetfile or a "raw" resource (eg. FBX)
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-23T04:16:07+00:00
- Post Title: Unity Studio

Small update:
- considerably better loading time
- bug fixes with extracting certain texture and audio assets
## Post #3
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-08-27T21:58:41+00:00
- Post Title: Unity Studio

Did you make it?
thx. It's cool!
## Post #4
- Username: Cetic
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 28, 2014 8:37 am
- Post datetime: 2014-08-28T02:04:14+00:00
- Post Title: Unity Studio

Hello ! 

Really nice app !! Works like a charm !

 Can you please just add rename function when extracting files ? 

i have like 300 files with the same name in 1 assets file... 
Actually need to extract 1 by 1 and rename before extracting the next file.

if filename exist add a number
Just like filename, filename_0, filename_1 ... 

Thank's for this really awesome app !
## Post #5
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2014-08-28T04:13:45+00:00
- Post Title: Unity Studio

nice work~~,thank for share,i also LIKE you max script~~
## Post #6
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2014-08-28T04:17:18+00:00
- Post Title: Unity Studio

oh , my sysytem is XP, I can't open the exe, i don't know  why~~
## Post #7
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-28T05:35:01+00:00
- Post Title: Unity Studio

@MiRiKan Well yeah, ofc I made it. I wouldn't post someone else's app as my own. D'oh 

@Cetic An option for unique filenames is already added in my current build. I plan to release it soon.

@glcat Make sure you have [.NET Framework 4.0](http://www.microsoft.com/en-in/download/details.aspx?id=17718) installed.


Do you guys find the Size column useful in any way? If not I would rather remove it to make room for longer asset names.
## Post #8
- Username: Cetic
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 28, 2014 8:37 am
- Post datetime: 2014-08-28T15:17:55+00:00
- Post Title: Unity Studio

> Reply from Chipicao
>
> 
@Cetic An option for unique filenames is already added in my current build. I plan to release it soon.

Do you guys find the Size column useful in any way? If not I would rather remove it to make room for longer asset names.

Thank's ! So i will stop now to extract 1 by 1 and wait ^^

The column "size" is really usefull for me !! Because in these 300 files, one with size 8600 are LQ, one with size 33K are MQ and one with size 134K are HQ.

Can you just make columns sortable ? so i can sort by Name or Size ?



Really Thank you !
## Post #9
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-30T08:50:45+00:00
- Post Title: Unity Studio

OK so here's beta 3. Try it and let me know what you think - link in first post.

Changelog:
- moved preview options to menu
- added unique filename option (on by default)
- all user options are remembered for next session
- aligned preview panel with status strip
- asset size column now displays the actual export size
- asset columns are not sortable on click
- implemented a faster method to export filtered assets
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-30T10:49:49+00:00
- Post Title: Unity Studio

What about preview models ?
## Post #11
- Username: Cetic
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 28, 2014 8:37 am
- Post datetime: 2014-08-30T13:36:49+00:00
- Post Title: Unity Studio

AWESOME ! 

SO NICE ! Thank you !!
## Post #12
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-08-30T13:50:15+00:00
- Post Title: Unity Studio

@Chipicao
it's really so cool for me!
Thanks again!
## Post #13
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-30T19:27:18+00:00
- Post Title: Unity Studio

> Reply from Ekey
>
> What about preview models ?
For that I will have to completely re-write the interface in WPF so I can use the Viewport3D class. I don't want to mess around with XNA.

But the priority now ix exporting models to FBX.
## Post #14
- Username: mono24
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-08-30T19:49:55+00:00
- Post Title: Unity Studio

Chipicao
What about import files back in assets and create new assets? =)
## Post #15
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-30T20:27:01+00:00
- Post Title: Unity Studio

I don't know if I will add support for something like that. Maybe after everything else is ready, but that's a big maybe.
## Post #16
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2014-08-31T17:50:39+00:00
- Post Title: Re: Unity Studio beta

Nice, thanks for the tool!
Does it extract/add files not listed above (e.g. data files such as XML or raw binaries)?
## Post #17
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-31T19:14:26+00:00
- Post Title: Re: Unity Studio beta

Only extraction and only files which can be used by themselves - textures, audio clips, fonts and shaders.

If you know any game with xml or other plain-text assets which might be worth extracting, tell me the name and I'll have a look.
## Post #18
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2014-08-31T20:24:07+00:00
- Post Title: Re: Unity Studio beta

[Creeper World 3](http://knucklecracker.com/creeperworld3/redownload.php) for example.
If you don't want to have to purchase it, it also has a [free, browser-based version](http://www.kongregate.com/games/whiteboardwar/creeper-world-3-abraxis) using the Unity3D plugin.
My recollection is that you don't need the key for installation, you need it only for playing. I could be wrong though as I installed it a long time ago.
## Post #19
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-01T00:01:28+00:00
- Post Title: Re: Unity Studio beta

Will release something tomorrow...

[](http://www.imagebam.com/image/ddec77348564703)
## Post #20
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-09-01T01:15:18+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> Will release something tomorrow...

SO COOL! That's TextAsset!
Thanks for lot of!
## Post #21
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2014-09-01T17:21:44+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> Will release something tomorrow...

Yes, maps are XML, hence my original question 
Looking forward to it, thank you in advance!
## Post #22
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-02T11:18:49+00:00
- Post Title: Re: Unity Studio beta

Uploaded new version.

Since I had to implement lzma in order to decompress some of these TextAssets, I decided to also add functions for unpacking bundle files (.unity3d, .assetbundle, .bundle and .bytes) or loading them directly in memory for asset export.
Supports both UnityWeb and UnityRaw types, as well as the special header used in .bytes files.

Unfortunately lzma in C# is slower than old people f***ing, so I suggest you keep to quickbms until I find a faster way.
## Post #23
- Username: weesy91
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 31, 2014 3:39 pm
- Post datetime: 2014-09-05T13:43:25+00:00
- Post Title: Re: Unity Studio beta

Thanks for this awesome program. it works just fine.
but there's a problem which i really want to figure out.
i'm modding an android game and whenever i extract maindata it exports all the assets well except one text assets.
The file has CAB in front of the asset file, and after several reserarch i found out it was custom assets bundle file.
whenever i try to open CAB file with Unity studio, the program call in the data but it doesn't seems it's reading it in right way.
I tried to export the file and it exports, but shows some crashed texts inside which i cannot understand a single word.
Would there be any solutions to this?

[](http://www.imagebam.com/image/f112a7349421489)
## Post #24
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-06T09:14:00+00:00
- Post Title: Re: Unity Studio beta

Firts of all I need that CAB file.

Second, have you tried opening the txt file in wordpad or another text editor such as EditPlus?
## Post #25
- Username: weesy91
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 31, 2014 3:39 pm
- Post datetime: 2014-09-06T09:29:02+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> Firts of all I need that CAB file.

Second, have you tried opening the txt file in wordpad or another text editor such as EditPlus?

I've Tried, NotPad++, EditPlust, normal Notepad and even with Hex Edit and none of those gave me 
a satisfactory result. 

here, i'm posting a link to that cab file.
[http://www.4shared.com/file/VEX-3QZIba/ ... 4b7e0.html](http://www.4shared.com/file/VEX-3QZIba/CAB-1517d855faaa23a46951a4b7e0.html)
## Post #26
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-06T10:42:17+00:00
- Post Title: Re: Unity Studio beta

This TextAsset seems to be using a different compression. but I have no idea what type. I tried running a comtype_scan with quickbms but no luck.
comtype #95 seems to give some fragments of words...

```
00000032 A5A599A5 A5A5A4A5 A5A5A4A5 A6F442A5 807CF5A5 A6F786A5 A5A591A5 F8A5A5AD
00000064 A5F57C80 A5A5A5A5 A5A5A5C2 5B0D4177 FAFDF06F A2228CE9 08BD96B0 F2298B22
00000096 24DEF36F C0D368A5 0C25D43F 5C2131B2 ED63202E 30225161 00DAEE0A 85437F75
00000128 7C6E2C83 2310B11E BC66B4BB F62D1B0B 3A1F6546 3B64AA31 DC822EB9 FD6154D0
00000160 C23C679D 67DD036A 5351ABF7 9F6F9EF9 43FCC878 60B483D5 12D32140 9E1DFC92
00000192 813B48C3 8FD21C99 F7995591 D04342FC AC53F785 0EDF2B5F B03B3133 3E69E5C1
00000224 2510EFD5 86C58CDE 62C7D69A 580B166E B4B9EBD5 704DCF67 5DFABB63 C487E5E0

```


I'll look more into it tomorrow when I get home.
## Post #27
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2014-09-07T05:32:12+00:00
- Post Title: Re: Unity Studio beta

How to edit CAB file ?? Help me, please...
## Post #28
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2014-09-12T03:56:36+00:00
- Post Title: Re: Unity Studio beta

is it possible to export 3D models?
When I click on "Export 3D scene", nothing happens.
## Post #29
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-12T05:38:26+00:00
- Post Title: Re: Unity Studio beta

As mentioned in the first post, that's not ready yet.

I will resume work on this soon. Until then you can use my MAXScript to import models.
## Post #30
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2014-09-14T07:03:37+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> As mentioned in the first post, that's not ready yet.

I will resume work on this soon. Until then you can use my MAXScript to import models.
How to edit CAB file ?? Help me, please...
## Post #31
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-14T07:30:48+00:00
- Post Title: Re: Unity Studio beta

> Reply from hackspeedok
>
> How to edit CAB file ?? Help me, please...
At the moment there is no option to edit unity files, only extraction.

Try Unity Extractor or repacking with aluigi's quickbms script.
## Post #32
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2014-09-22T01:16:40+00:00
- Post Title: Re: Unity Studio beta

Hey Chipicao,

I did test your new tool and I am amazed with the results. Seriously, I can not thank you enough.

I ran into a problem, I'm not sure if it's my issue or something else.

I did some test with [this game](https://itunes.apple.com/ph/app/cupcake-carnival/id899724133?mt=8) and I get the PVR out just fine, however, the dds textures seem to have some problem.

While I see just fine on Unity Studio, after I export, I get problems to see them right.



After exporting, on a Mac using GraphicConverter to see them:



Usually, GraphicConverter works pretty well, I don't understand why this happens.
Any thoughts?

Thanks!
## Post #33
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-24T08:10:29+00:00
- Post Title: Re: Unity Studio beta

Try these 2 textures and let me know if either one works: [http://www.mediafire.com/download/vnw56 ... ceTagB.zip](http://www.mediafire.com/download/vnw56ricmekjrpe/PriceTagB.zip)
## Post #34
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2014-09-26T04:37:48+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> Try these 2 textures and let me know if either one works: http://www.mediafire.com/download/vnw56 ... ceTagB.zip

Both of them are wrong, just like the example I posted.
However, when I convert them to PNG using web or random software, it will work.

Maybe it's just an issue with GraphicConverter?
## Post #35
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-26T07:17:23+00:00
- Post Title: Re: Unity Studio beta

The texture extracted with Unity Studio indeed has a small bug, but it works in Photoshop with nvidia filters.
One of the textures I uploaded is fixed, and the other was re-exported from Photoshop, so it should be 100% good.

So yeah, my guess is there's an issue with GraphicConverter.
## Post #36
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2014-09-28T13:07:47+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> The texture extracted with Unity Studio indeed has a small bug, but it works in Photoshop with nvidia filters.
One of the textures I uploaded is fixed, and the other was re-exported from Photoshop, so it should be 100% good.

So yeah, my guess is there's an issue with GraphicConverter.

Oh! No worries!
GraphicConverter sometimes works, sometimes it does not. I can't really tell why.
I need to use it, since there is no DDS Photoshop plugin for Mac.

But since I got a nice batch converter, it's no pain.   

Thanks for checking it out!
## Post #37
- Username: dongvanhung
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 29, 2014 2:37 pm
- Post datetime: 2014-09-29T06:42:10+00:00
- Post Title: Re: Unity Studio beta

I hope you will make this tool for Mac OSX user . I cant use this tool because i am using Mac OSX
## Post #38
- Username: Elayna
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 08, 2014 6:43 am
- Post datetime: 2014-10-08T08:26:41+00:00
- Post Title: Re: Unity Studio beta

Thank you for building such a useful Unity Software. Now i am able to view more of Samurai Seige files.
## Post #39
- Username: Elayna
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 08, 2014 6:43 am
- Post datetime: 2014-10-08T08:45:41+00:00
- Post Title: Re: Unity Studio beta

I can't open DDS files. Cause i am not using nvidia graphic card. Anyway i can open dds files in other ways?

And how do i export it Scene Hierarchy files? Try using unity assets explorer but it was not able to fully extract the game Temple Run

Thank you
## Post #40
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-10-08T15:00:00+00:00
- Post Title: Re: Unity Studio beta

You don't need an nvidia card to use nvidia filters with photoshop. Any GPU will do. Or any other software that can read DDS files.

Scene Hierarchy? If you mean 3d models, that's not ready yet. But you can use my maxscript for now.
## Post #41
- Username: Elayna
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 08, 2014 6:43 am
- Post datetime: 2014-10-09T04:13:11+00:00
- Post Title: Re: Unity Studio beta

Thanks for the quick respond

As on photo beside Asset list. There is Scene Hierarchy and there is where it MonoScript, Java Script or C sharp script are. I wonder if i can extract those and reuse it back in unity 3d.

I try doing it with Unity Asset Explorer it will indicate the file format on Unity Asset Explorer but when extracted it format is not something which i am sure of or could use in unity
## Post #42
- Username: takatori
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 16, 2014 11:10 pm
- Post datetime: 2014-10-16T15:36:48+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> After about a year and a half of researching and reverse engineering the Unity format, my maxscript importer has has come about as far as it can get. So I decided to make a tool that has the same functionality but offers better performance and isn't attached to a "3rd party" program.

Since this is my first C# project and I'm learning as I go, I'm releasing this beta to get a feel of the interface, featrues and functionality. Many thanks to cra0 for helping me along the way!

Current features:
Compatible with all Unity versions from 2.5.0 to 4.5.3f3
Compatible with Web, PC, iOS, Android, PS3, Xbox 360, OSX and Linux games/apps
Automatically merges .split files from Android games
Able to load audio streams from .resS files
Search filter
Real-time preview window and export function for textures, audio clips, shaders and fonts
Textures: DDS (Alpha8bpp, ARGB16bpp, RGB24bpp, ARGB32bpp, BGRA32bpp, RGB565, DXT1, DXT5, RGBA16bpp)
PVR (PVRTC_RGB2, PVRTC_RGBA2, PVRTC_RGBA4, PVRTC_RGB4, ETC_RGB4)
Audio clips: mp3, ogg, wav, xbox wav
Shader files are exported in plain-text
Fonts: ttf, otf

PVR textures from iOS & Android are not previewed at the moment; use PVRTexTool to open them.

Materials and meshes are useless if exported as standalone files because they need to be linked together with transformation assets (position, rotation scale) and textures in order to get proper 3D models.
Which is why I'm developing a separate function to export 3D content into FBX. Hopefully it will be ready soon.

DOWNLOAD beta 4

Plz update Export 3D/2D Scenes, thank
## Post #43
- Username: Glabrezu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 04, 2014 9:41 pm
- Post datetime: 2014-11-04T13:47:54+00:00
- Post Title: Re: Unity Studio beta

Hi. Really amazed at the tool.

Are you planning on adding the possibility of exporting prefabs (objects of type GameObject) and scenes? 
If not, would you consider making the sources available?
## Post #44
- Username: Kaens
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 10, 2014 12:24 am
- Post datetime: 2014-11-09T16:26:30+00:00
- Post Title: Re: Unity Studio beta

I just signed up to be able to say thanks =) What a nice piece of software.
## Post #45
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2014-11-09T18:34:40+00:00
- Post Title: Re: Unity Studio beta

hi ,Chipicao,well done;thx
## Post #46
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-07T16:59:37+00:00
- Post Title: Re: Unity Studio beta

Hey, please add a function to export meshes.

This is already possible with DisUnity, but it has no preview, it cant just extract everything or nothing.

Thanks in advance!
## Post #47
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-03-10T12:54:08+00:00
- Post Title: Re: Unity Studio beta

Nice work. Can you add extraction by type of file? For example i need only music and it seems there is no option to extraxt only wav/ogg files.
## Post #48
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-03-12T15:04:53+00:00
- Post Title: Re: Unity Studio beta

@Slandey It is planned, unfortunately time is not on my side

@sfc123 You can sort by type and then do a shift+click selection
## Post #49
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-03-13T03:57:25+00:00
- Post Title: Re: Unity Studio beta

Hey,
I think something changed at Unity5
## Post #50
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-13T15:43:34+00:00
- Post Title: Re: Unity Studio beta

> Reply from MiRiKan
>
> Hey,
I think something changed at Unity5

What do you mean? The way the assets are compiled?
## Post #51
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-03-20T03:15:06+00:00
- Post Title: Re: Unity Studio beta

> Reply from Slandey
>
> MiRiKan wrote:Hey,
I think something changed at Unity5 

What do you mean? The way the assets are compiled?

Yes, a little changed at Unity5: [http://aluigi.altervista.org/papers/bms/unity.bms](http://aluigi.altervista.org/papers/bms/unity.bms)
## Post #52
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-04-08T14:57:10+00:00
- Post Title: Re: Unity Studio beta

> Reply from MiRiKan
>
> Hey,
I think something changed at Unity5 

Yes, a little changed at Unity5: http://aluigi.altervista.org/papers/bms/unity.bms

The new version has a name... "Oxe".
The older versions have just numbers:

> #   It supports the following versions and probably others:
>
> #     6 used in Unity ??? (probably 2.x)
>
> #     8 used in Unity 3.x
>
> #     9 used in Unity 4.x
>
> #     0xe used in Unity 5.x
## Post #53
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2015-04-08T16:09:32+00:00
- Post Title: Re: Unity Studio beta

Interesting choice, lol
## Post #54
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-04-15T18:30:07+00:00
- Post Title: Re: Unity Studio beta

0xe is the number 14 so that's not really a change 

I already knew this plus many more complex changes, but unfortunately I have stopped working on this for lack of time.
I hope to resume when Unity 5 final is released.
## Post #55
- Username: D1g1K1d
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 01, 2012 5:33 am
- Post datetime: 2015-05-12T10:31:50+00:00
- Post Title: Re: Unity Studio beta

great job! looks like a fantastic app and i'm excited to play with it,
but i seem to be having the same problem as glcat on the first page-
i'm on XP thru parallels desktop on my mac (the apps on this site are the only thing i use windows for lol),
and the app simply refuses to open. 
i took the advice you gave glcat and double checked .NET 4.0 was installed. 
it was. even removed it, then reinstalled just to be sure. still a no-go :-\
are there any other system dependancies, or thoughts you might have on how to get it to open?
thanks so much in advance for any help you can offer
## Post #56
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-07-17T22:27:08+00:00
- Post Title: Re: Unity Studio beta

Hey! 
I've come across a game that is powered by Unity (I saw this by checking the apk file, it had Unity assets that were openable with Unity Studio), however the main model files are downloaded once the game loads, it's a bit of a pain to find the files and I'm not even sure if I've got the correct ones because these files won't load in Unity Studio. Would anyone take a look and see if these are actually Unity files? I'm not sure if they are encrypted or not.. I'd really love to get the models from the game. (The game is One Piece Dance Battle if you would like to know)
[Resource.rar](https://xentaxbackup.github.io/file/9427_Resource.rar)
## Post #57
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2015-07-22T16:24:16+00:00
- Post Title: Re: Unity Studio beta

he what about unity 5.x ??
I dont work 
And the script with bms dont realy working mean what in the fuckii ng hell extports .script files ???????????
## Post #58
- Username: LinkofHyrule89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 10, 2015 5:19 pm
- Post datetime: 2015-10-10T09:32:58+00:00
- Post Title: Re: Unity Studio beta

I was hoping this would work for opening asset files from [Shroud of the Avatar](https://www.shroudoftheavatar.com) ([download](https://d2sx9mrt4zumaq.cloudfront.net/Installers/SotAInstaller.exe)) but it doesn't seem to want to work when I try to open resources.assets is there anyway you can update it to work with the new unity 5 format? It would be amazing if you could I'm trying to get the images for a wiki. If could open source this project it would make it easier for community members to help fix it when it breaks thanks for your time
## Post #59
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-10-27T21:12:04+00:00
- Post Title: Re: Unity Studio beta

I finally have some free time to get back to this project.
Unity Studio 0.4.6.9 released: [https://app.box.com/UnityStudio](https://app.box.com/UnityStudio)

New features:
- compatibility with Unity up to 4.6.9
- 3D object export to FBX
- minor interface tweaks
- code cleanup and optimization

Planned for next release:
- Unity 5 support
- Collada DAE export
- PVR texture preview and conversion
## Post #60
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2015-10-27T21:18:05+00:00
- Post Title: Re: Unity Studio beta

Yippie, great, thanks!
Looking forward to Unity 5 - not so many stuff comes on Unity 4 anymore.
## Post #61
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-10-28T12:29:03+00:00
- Post Title: Re: Unity Studio beta

Small update:
- fixed an issue that prevented exporting UV coordinates on some unity versions
- removed code that slowed down object selection in the hierarchy
- fixed a problem with sorting filenames
- fixed the Export menu actions
- added material.json parsing for Porsche.com car builder

Download link is the same: [https://app.box.com/UnityStudio](https://app.box.com/UnityStudio)
## Post #62
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2015-10-29T08:59:20+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> Small update:
- fixed an issue that prevented exporting UV coordinates on some unity versions
- removed code that slowed down object selection in the hierarchy
- fixed a problem with sorting filenames
- fixed the Export menu actions
- added material.json parsing for Porsche.com car builder

Download link is the same: https://app.box.com/UnityStudio

when does UnityStudio support importing ??? Thanks so much
## Post #63
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-10-29T20:03:13+00:00
- Post Title: Re: Unity Studio beta

> Reply from Csimbi
>
> Yippie, great, thanks!
Looking forward to Unity 5 - not so many stuff comes on Unity 4 anymore.
Please post any Unity 5 games you know of in this topic [viewtopic.php?p=111709#p111709](http://forum.xentax.com/viewtopic.php?p=111709#p111709) so that I may begin testing


@hackspeedok I might add the option to replace simple assets such as textures or sounds, but I can;t make any promises.
## Post #64
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-10-29T23:47:32+00:00
- Post Title: Re: Unity Studio beta

And we have liftoff! 

[](http://www.imagebam.com/image/ac802b443857059) 

New version will be released after I have a chance to test all Unity 5 versions up to 5.2.2 (about a dozen).
## Post #65
- Username: quadcoremax
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 30, 2011 8:33 pm
- Post datetime: 2015-10-30T07:53:17+00:00
- Post Title: Re: Unity Studio beta

Hi Chipicao,

I saw your topic recently & I was not sure about why having such tool as Unity Studio. I completely forgot that it's by default impossible to extract & export fbx files from Unity Projects.

I downloaded your tool & I'm still kind of not sure, how it works. I first thought, it would load a unitypackage file & then let us decide what to choose to export, probably models, materials, etc.

Sorry for being so noob, but where I do find the files that Unity Studio asks for import ?

Thanks
## Post #66
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2015-10-30T10:10:13+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> Csimbi wrote:Yippie, great, thanks!
Looking forward to Unity 5 - not so many stuff comes on Unity 4 anymore.
Please post any Unity 5 games you know of in this topic viewtopic.php?p=111709#p111709 so that I may begin testing


@hackspeedok I might add the option to replace simple assets such as textures or sounds, but I can;t make any promises.
 hope soon. i always get troubles with bundle files like *.unity3d, *.assetbundle. Thanks so much
## Post #67
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-10-30T10:43:03+00:00
- Post Title: Re: Unity Studio beta

> Reply from quadcoremax
>
> Hi Chipicao,

I saw your topic recently & I was not sure about why having such tool as Unity Studio. I completely forgot that it's by default impossible to extract & export fbx files from Unity Projects.

I downloaded your tool & I'm still kind of not sure, how it works. I first thought, it would load a unitypackage file & then let us decide what to choose to export, probably models, materials, etc.

Sorry for being so noob, but where I do find the files that Unity Studio asks for import ?

Thanks

Well first of all it can't be "impossible if I just did it. And I've been importing Unity 3D models for years with my MAXScript.

Here's a quick summary of unity file types:

1) Bundles - packages with one or more files inside, compressed or not
- extensions: .unity3d, .assetbundle, .bundle, .bytes
- usually found in web apps or downloadable content
- they contain the actual asset files
- can be extracted with Extract bundle/folder options from Unity Studio, or with quickbms

2) Assetfiles - contain serialized game resources (assets)
- filename format / extensions: maindata,"level#, *.assets, *.sharedAssets, CustomAssetBundle-*, CAB-*, BuildPlayer-*
- these are the files that you can load/import in Unity Studio
- you can get these files from bundles, ipa/apk mobile app packages, or directly from PC games

3) unitypackage - asset packages exported from Unity Editor to be transfered from project to project
- you will not find these in published games or apps
- they are basically tar.gz archives and can be extracted if needed
- inside you will find files named "metadata" and "asset"
- metadata is an assetfile - same as no. 2
- asset can be either an assetfile or a "raw" resource (eg. FBX)
## Post #68
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-01T23:51:20+00:00
- Post Title: Re: Unity Studio beta

Unity Studio 0.5 is now available with full support for Unity 5, up to version 5.2.2f1
I haven't been able to find too many Unity 5 games for testing, so if you have any issues please let me know.


I've added a hidden diagnostics feature that will come in handy for anyone who wishes to explore the format and structure of serialized assets. Press Ctrl+Alt+D to reveal a new menu and list.
By default no assets will be loaded and Unity Studio will build human-readable structures for each Unity class.
You can view or export these structures in plain-text format. A folder will be created automatically for each Unity version loaded.
Note that diagnostics only works with games built for the Web platform!
[](http://www.imagebam.com/image/15e6b6444379184)
## Post #69
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-02T04:05:20+00:00
- Post Title: Re: Unity Studio beta

So Star Wars Galaxy Heroes is out on the Google Play store and i noticed it runs on 5.1.3p2 of unity and for some reason this tool doesn't seem to give a Scene hierarchy only a asset list is that cause Unity 5 it's fully supported yet?

Also how do i view models in it unity studio?, cause your 3ds max unity importer doesn't seem to work with the files.
## Post #70
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-02T08:16:58+00:00
- Post Title: Re: Unity Studio beta

> Reply from JakeGreen
>
> So Star Wars Galaxy Heroes is out on the Google Play store and i noticed it runs on 5.1.3p2 of unity and for some reason this tool doesn't seem to give a Scene hierarchy only a asset list is that cause Unity 5 it's fully supported yet?

Also how do i view models in it unity studio?, cause your 3ds max unity importer doesn't seem to work with the files.

When I said "full support for Unity 5" I meant it 
[](http://www.imagebam.com/image/5c4989444425625) [](http://www.imagebam.com/image/0511c2444425628) 

The problem was my TreeView was somehow removed from the final build. So it was only an UI glitch.
Please re-download from the same link and it should work now.


You can't view 3D models in Unity Studio, and you don't need my Maxscript for that. The whole point is to export to FBX and use that however you want.
For those who don't know, FBX is a file format that can be imported directly in Autodesk applications sucha as 3ds Max or Maya, and can also be viewed with FBX Review.
## Post #71
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-02T08:21:35+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> JakeGreen wrote:So Star Wars Galaxy Heroes is out on the Google Play store and i noticed it runs on 5.1.3p2 of unity and for some reason this tool doesn't seem to give a Scene hierarchy only a asset list is that cause Unity 5 it's fully supported yet?

Also how do i view models in it unity studio?, cause your 3ds max unity importer doesn't seem to work with the files.

When I said "full support for Unity 5" I meant it 
  

The problem was my TreeView was somehow removed from the final build. So it was only an UI glitch.
Please re-download from the same link and it should work now.


You can't view 3D models in Unity Studio, and you don't need my Maxscript for that. The whole point is to export to FBX and use that however you want.
For those who don't know, FBX is a file format that can be imported directly in Autodesk applications sucha as 3ds Max or Maya, and can also be viewed with FBX Review.

Ah okay thanks, i tried exporting a few of the models but it keep shooting me a unable to read beyond the end of the stream error.
## Post #72
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-02T08:42:12+00:00
- Post Title: Re: Unity Studio beta

Please let me know if it works now.

It looks like this game, like many others, needs to download additional files after its' installed.
## Post #73
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-02T08:47:39+00:00
- Post Title: Re: Unity Studio beta

> Reply from Chipicao
>
> Please let me know if it works now.

It looks like this game, like many others, needs to download additional files after its' installed.

Yeah i got just about every unity cache file there is for it and i see the model in there along with it's bones but i just keep getting that error when i try to export as fbx with all 3d obejcts or selected 3d objects.
## Post #74
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-02T11:29:36+00:00
- Post Title: Re: Unity Studio beta

Thanks for your feedback.

I was able to find a typo that caused a bug in Unity 5 skinned models.
I also improved the code that links asset files to each-other in order to share assets.

Please re-download Unity Studio, everything should work now. 

[](http://www.imagebam.com/image/5d3d33444449863) [](http://www.imagebam.com/image/190bdd444449867)
## Post #75
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2015-11-02T13:24:48+00:00
- Post Title: Re: Unity Studio beta

That Millenium Falcon has some pretty rugged edges.
Hope it's not that ugly in the game!

Tool looks awesome!
## Post #76
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-02T17:12:28+00:00
- Post Title: Re: Unity Studio

I guess they didn't think a mobile game needs hi-poly models.

New version uploaded:
- fixed an issue with vertex colors in Unity 5
- added support for UV channels 3 & 4 in Unity 5
- fixed a problem with the scene hierarchy search box
## Post #77
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2015-11-02T19:43:48+00:00
- Post Title: Re: Unity Studio

Ah, ok. Thought it was PC 
That's good enough for mobiles.
## Post #78
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-11-03T01:56:53+00:00
- Post Title: Re: Unity Studio

Hi Chipicao,

To be honest, I didn't look for Unity games in a while, but now I'm very happy and excited that you are back! =)

I did a quick testing with Ori and the Blind Forest, I believe it's using Unity 5.0.0.
It reads all the packages and when it starts to build, I get this:



It seems to work with other games, but I'm still testing.

Thank you!
## Post #79
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-03T07:31:27+00:00
- Post Title: Re: Unity Studio

@lolwatt Thanks for the feedback, I'll have a look at Ori.

@notmebug2 I uploaded the current build on GitHub.
## Post #80
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-03T13:09:40+00:00
- Post Title: Re: Unity Studio

New version uploaded
- fixed bug when attempting to preview unsupported fonts
- added failsafe for reading strings that would cause an exception in incompatible games
- added status messages for loading and previewing assets


@lolwatt unfortunately Ori is built with Unity 5 beta, and research for beta builds will require considerable time.
Still, I made some changes that should prevent failures, and as far as I can tell most assets from Ori are loaded fine now.

@notmebug2 good news: I fixed the font error
bad news: that particular type of font wasn't supported anyway (it's a custom format without any ttf or otf included)

I will look into the sorting issue and OLYM this evening.
The error looks like a new audio format that's not supported by my FMOD implementation. I think I need to update that anyway.
## Post #81
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-03T13:57:14+00:00
- Post Title: Re: Unity Studio

Unity 5 introduced FSB audio streams which are causing the error.
fmodex.dll is the latest version, but the API itself is old. I should look into a newer FMOD Studio API.

Texture conversion is already planned, but only after I make sure there are no more errors with Unity 5.

I'll add vertical texture flip to the list, thanks for the suggestion.
IIRC textures are already flipped in Preview mode, but are exported normally.
## Post #82
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-11-03T23:00:11+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> 
@lolwatt unfortunately Ori is built with Unity 5 beta, and research for beta builds will require considerable time.
Still, I made some changes that should prevent failures, and as far as I can tell most assets from Ori are loaded fine now.

Ouch! Didn't think they released that on BETA. :/
I confirm I can check the files. Thank you very much.

I have a question kinda related to Studio; what is the best/fastest way to convert these PVR textures to something more usable?

And thanks once again!
## Post #83
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2015-11-04T05:19:17+00:00
- Post Title: Re: Unity Studio

Any chance that Model Bone Weights will be Supported?
## Post #84
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-04T13:13:29+00:00
- Post Title: Re: Unity Studio

New version with small fix:
- added exception to skip preview of unsupported audio clips
- fixed a feature that automatically resizes list columns by content
- fixed sorting issue when loading a new file/folder
- asset list is now sorted by 2 columns, first by the column you click, then by the column you previously clicked

@lolwatt the fastest way I know is to use [PVRTexTool](http://community.imgtec.com/developers/powervr/tools/pvrtextool/) CLI (command line)
Look for PVRTexToolCLI.exe in \PowerVR_Graphics\PowerVR_Tools\PVRTexTool\CLI\Windows_x86_64
Create a .cmd file in the same folder and paste this inside:

```
set /p dest="Output folder: "

mkdir %dest%
if defined command set "source=%source:"=%"
if defined command set "dest=%dest:"=%"

for %%G in ("%source%\*.pvr") do PVRTexToolCLI -i "%%G" -o "%dest%\%%~nG.dds" -d "%dest%\%%~nG.png" -flip y -f r8g8b8a8

pause
```

Since the tool is meant for converting to PVR or similar, an output compressed format is mandatory. I chose 32-bit DDS for convenience.
Fortunately you can also specify a secondary uncompressed output - in this case PNG, but you can change to JPG or BMP if you'd like.
Unfortunately the -flip switch only affects the DDS output. PNG images will retain original orientation.
But at least this allows you to do a batch conversion with only a few clicks. Good luck!

@Arymond I moved up blend weights and bones on my TODO list. The reason is CSR Racing 2 uses bones to "assemble" car parts in the correct position
[](http://www.imagebam.com/image/b5d6f6444546182)
## Post #85
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-04T22:18:05+00:00
- Post Title: Re: Unity Studio

Another update:
- replaced FMOD Ex with FMOD Studio API
- audio preview code optimization
- added breakpoints for any FMOD errrs; status messages are now generated instead of crashing the app
- fixed a loop in the FMOD code that caused system overflow
- added platform string to app titlebar

Now some of the FSB audio streams are played, but I still have no idea how to handle substreams.
## Post #86
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-05T07:31:31+00:00
- Post Title: Re: Unity Studio

You're right, it looks like they are a PCM format in AIFF container.

I labeled them as FSB because I thought I saw a FSB header in some of them, but I could have been mistaken.
I'll check and update this later. Until then you can simply change the extension to .aif


But I have also failed to use FSBextractor with clips that are indeed FSB, and have a matching FSB5 magic marker.
## Post #87
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2015-11-05T16:16:40+00:00
- Post Title: Re: Unity Studio

when will the Unity Studio support repacker, Chipicao ? Thanks
## Post #88
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-11-10T02:12:11+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> @lolwatt the fastest way I know is to use PVRTexTool CLI (command line)
Look for PVRTexToolCLI.exe in \PowerVR_Graphics\PowerVR_Tools\PVRTexTool\CLI\Windows_x86_64
Create a .cmd file in the same folder and paste this inside:
Code: Select allset /p source="PVR folder: "
set /p dest="Output folder: "

mkdir %dest%
if defined command set "source=%source:"=%"
if defined command set "dest=%dest:"=%"

for %%G in ("%source%\*.pvr") do PVRTexToolCLI -i "%%G" -o "%dest%\%%~nG.dds" -d "%dest%\%%~nG.png" -flip y -f r8g8b8a8

pause
Since the tool is meant for converting to PVR or similar, an output compressed format is mandatory. I chose 32-bit DDS for convenience.
Fortunately you can also specify a secondary uncompressed output - in this case PNG, but you can change to JPG or BMP if you'd like.
Unfortunately the -flip switch only affects the DDS output. PNG images will retain original orientation.
But at least this allows you to do a batch conversion with only a few clicks. Good luck!

Thanks! I modified the batch file a bit to make it mobile and packaged it together with the PVRTexToolCLI.exe

```
https://mega.nz/#!q8EGnKKQ!geMeH8gdRGjP6IoFDL-L7CRJdoUGosB4_iWXOm4Mq5g
```


just copy PVR2PNG.bat and PVRTexToolCLI.exe to the folder with your pvr textures and click the batch file and wait for finish.
Your new png textures will be created in the same folder.
## Post #89
- Username: kenwandou
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 02, 2014 1:08 pm
- Post datetime: 2015-11-11T07:18:39+00:00
- Post Title: Re: Unity Studio

@Chipicao

There is a sample can not open


The actual file contains 2 TEX format images and some text.
(asset format, the suffix name is also the same as assets)
[battleship_001.zip](https://xentaxbackup.github.io/file/9995_battleship_001.zip)
## Post #90
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-11T14:18:06+00:00
- Post Title: Re: Unity Studio

> Reply from notmebug2
>
> When I view fonts, sometime preview window will not be refreshed after I view another font.
It often happen when I switch between two fonts repeatedly.
Sorry, but I'm not able to reproduce the problem. Does it happen in a specific game?

> Reply from kenwandou
>
> There is a sample can not open
https://app.box.com/s/rlu40il1z6fntn342g9kil2r4da6omtv

The actual file contains 2 TEX format images and some text.
(asset format, the suffix name is also the same as assets)
That's a bundle file that needs to be extracted first. Click File -> Extract bundle and select "All files" from the filter list. Then you can import it.

Careful with extensions, .assets is not the same as .asset.
## Post #91
- Username: kenwandou
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 02, 2014 1:08 pm
- Post datetime: 2015-11-11T14:29:35+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> notmebug2 wrote:When I view fonts, sometime preview window will not be refreshed after I view another font.
It often happen when I switch between two fonts repeatedly.
Sorry, but I'm not able to reproduce the problem. Does it happen in a specific game?
kenwandou wrote:There is a sample can not open
https://app.box.com/s/rlu40il1z6fntn342g9kil2r4da6omtv

The actual file contains 2 TEX format images and some text.
(asset format, the suffix name is also the same as assets)
That's a bundle file that needs to be extracted first. Click File -> Extract bundle and select "All files" from the filter list. Then you can import it.

Careful with extensions, .assets is not the same as .asset.

According to you, the problem is solved, ha ha
## Post #92
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-11T18:09:36+00:00
- Post Title: Re: Unity Studio

I've uploaded Unity Studio 0.5.1 with the option to export mesh deformers. You can choose to export skeletons either as dummy deformers or bones.
I know many of you have waited a long time for this, so enjoy. I also know many of you will want animation curves, but that's for another time 

[](http://www.imagebam.com/image/b3de4c446384227) [](http://www.imagebam.com/image/5c44e5446384237)
## Post #93
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-12T02:16:18+00:00
- Post Title: Re: Unity Studio

Hello I really Appreciate the work you do!
So! I only got a minor problem, some of the textures are in strange resulution for instance this one is only 256x256 "[http://prntscr.com/91sjhi](http://prntscr.com/91sjhi)"
And from the same model this one is 1K resulution "[http://prntscr.com/91sjqk](http://prntscr.com/91sjqk)"
And strangly its only on the weapons, head gear and such are just normal.
Am I doing something wrong? everything else works great btw!

and again THANK YOU!
## Post #94
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-12T06:37:27+00:00
- Post Title: Re: Unity Studio

@coolkid What exactly is the issue, the fact that one texture is much larger than the other?
That's just how it is, maybe the developer wanted more detail for that particular spec map. Unity Studio extracts what it sees.
You're welcome 

@notmebug2 I suppose large fonts could be the issue on a very slow HDD.
I designed Unity Studio to keep a low memory profile and load asset data only when you select an item for preview. So every time you select another asset it will read it from the disk.
## Post #95
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-11-12T10:01:26+00:00
- Post Title: Re: Unity Studio

Thank you so much for the update! 
However I tested a few models and they export with their bones and such, but they are exported in a strange pose, not in their default T-Pose/A-Pose. Any way around this?
## Post #96
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-12T14:59:27+00:00
- Post Title: Re: Unity Studio

Hey man! I got an error if I try to export anything of a character mesh.
[http://pastebin.com/pbSTdsSZ](http://pastebin.com/pbSTdsSZ)
## Post #97
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-12T17:21:35+00:00
- Post Title: Re: Unity Studio

Can you tell me which game and which model?
## Post #98
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-12T17:43:26+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> Can you tell me which game and which model?
The game is called Verdun "[http://www.verdungame.com/](http://www.verdungame.com/)" And the error occurs  on every Avatar piece: Hands, Hats, so on "[http://prntscr.com/9203c7](http://prntscr.com/9203c7)"
## Post #99
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-13T12:51:54+00:00
- Post Title: Re: Unity Studio

Thanks for the feedback. Please try the new version and let me know if you find any more issues.

This turned out to be a new feature in Unity 5, but I managed to account for it. The sample I have exports fine now
[](http://www.imagebam.com/image/ccbbb5446758653)
## Post #100
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-13T15:40:00+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> Thanks for the feedback. Please try the new version and let me know if you find any more issues.

This turned out to be a new feature in Unity 5, but I managed to account for it. The sample I have exports fine now

Man IDK, I freaking love you man! Thank you so much!
I still wonder why the weapon textures are so low resolution. 
I guess I'll re-texture them anyway
## Post #101
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-11-13T17:10:47+00:00
- Post Title: Re: Unity Studio

> Reply from TRDaz
>
> Thank you so much for the update! 
However I tested a few models and they export with their bones and such, but they are exported in a strange pose, not in their default T-Pose/A-Pose. Any way around this?
Any help please? Can't seem to figure out why it exports the way it does. I've tested a different game and it works ok on that.
## Post #102
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-13T18:03:14+00:00
- Post Title: Re: Unity Studio

> Reply from TRDaz
>
> TRDaz wrote:Thank you so much for the update! 
However I tested a few models and they export with their bones and such, but they are exported in a strange pose, not in their default T-Pose/A-Pose. Any way around this?
Any help please? Can't seem to figure out why it exports the way it does. I've tested a different game and it works ok on that.

In what Software do you import the models you exported?
In Blender you can select the whole armature and hit Alt|+G and Alt+R to reset the loc and scale parameters.
## Post #103
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-11-13T18:21:18+00:00
- Post Title: Re: Unity Studio

I've tried 3ds max, I don't know how to reset the pose within that. I tried importing it to the latest version of Blender but it gives an error.
## Post #104
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-13T18:30:36+00:00
- Post Title: Re: Unity Studio

> Reply from TRDaz
>
> TRDaz wrote:Thank you so much for the update! 
However I tested a few models and they export with their bones and such, but they are exported in a strange pose, not in their default T-Pose/A-Pose. Any way around this?
Any help please? Can't seem to figure out why it exports the way it does. I've tested a different game and it works ok on that.
Sorry, I didn't see your post.
Define "strange pose". Is it something unnatural, or just not T-pose?
Unity Studio exports bones in whatever position they're stored. If a developer decided to store their models in a specific pose, then that's what you'll get.

AFAIK Blender doesn't support ASCII FBX. If you want to try coolkid's suggestion, you should export from Max to binary FBX and then try Blender.

Mathematically it should be possible to revert the skeleton to the original pose of the mesh, which is usually T-pose or A-pose.
But I'm not that familiar with modeling techniques, so I don't know of any tools.
## Post #105
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2015-11-13T18:34:42+00:00
- Post Title: Re: Unity Studio

I can't import @@ anyone can help me? Thanks
## Post #106
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-13T19:16:37+00:00
- Post Title: Re: Unity Studio

@hackspeedok If you really want help, give me some details: name of the app/game, which model are you trying to export...
## Post #107
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-13T19:55:37+00:00
- Post Title: Re: Unity Studio

For people that are using Blender should use this program "[http://usa.autodesk.com/adsk/servlet/pc ... d=22694909](http://usa.autodesk.com/adsk/servlet/pc/item?siteID=123112&id=22694909)"
You just drag and drop the FBX you exported with Unity studio, select a output folder and select .Obj or any other supported file.
## Post #108
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-11-14T09:19:36+00:00
- Post Title: Re: Unity Studio

I managed to use 3ds to export to a fbx that blender could open. Blender opened the fbx in the same pose and I couldn't use the shortcuts mentioned to remove the pose, but exporting the model to a format I wanted to use made the model return to it's A-Pose. Thanks for the help!
## Post #109
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-11-14T09:42:18+00:00
- Post Title: Re: Unity Studio

to read FBX file i use SAP Visual Enterprise Author .. it can read many formats
## Post #110
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2015-11-14T11:37:40+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> @hackspeedok If you really want help, give me some details: name of the app/game, which model are you trying to export...

I want import text assets or textures to Unity Bundle (like *.unity3d). I work on many Unity games but can't modding *.unity3d files
## Post #111
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-14T16:39:28+00:00
- Post Title: Re: Unity Studio

Unity Studio is meant for exporting, not importing.

Try [Unity Engine Patch And Unpacker](http://forum.xentax.com/viewtopic.php?f=10&t=12837) or [Unity Assets Explorer](http://forum.xentax.com/viewtopic.php?f=10&t=10085)
## Post #112
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-11-15T00:22:12+00:00
- Post Title: Re: Unity Studio

Another Unity 5 game.
ワールド エンド エクリプス - The World End Eclipse
[http://theworldendeclipse.jp/](http://theworldendeclipse.jp/)


```
http://wee-dl.sega-online.jp/asset/15110501/Com/assets_list.bytes
```


just paste the file names in this url and you will get the file

```
http://wee-dl.sega-online.jp/asset/Assets/Ios/ios_tx037.assetbundle
```


```
http://wee-dl.sega-online.jp/asset/Assets/Ios/ios_tt000.assetbundle
```


```
http://wee-dl.sega-online.jp/asset/Assets/Ios/ios_bn001.assetbundle
```


you see the pattern

```
http://wee-dl.sega-online.jp/asset/Assets/Ios/ios_ + FileName + .assetbundle
```
## Post #113
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2015-11-15T07:29:58+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> Unity Studio is meant for exporting, not importing.

Try Unity Engine Patch And Unpacker or Unity Assets Explorer

Only UnityStudio work fine with bundle assets  Hope soon UnityStudio will support importing
## Post #114
- Username: qxoda4
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 31, 2012 7:13 pm
- Post datetime: 2015-11-18T10:32:11+00:00
- Post Title: Re: Unity Studio

When you convert the file to FBX, the texture is not applied correctly .  
I'd appreciate it if you could teach me that.  

[http://storage.game.starlight-stage.jp/ ... nity3d.lz4](http://storage.game.starlight-stage.jp/dl/10010800/High/AssetBundles/Android/3d_chara_head_0272_3004.unity3d.lz4)
## Post #115
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2015-11-19T00:24:38+00:00
- Post Title: Re: Unity Studio

Hey!

When exporting the 3D data from Bakery Story 2, it reports an error, but seems to export without any issues. Just saying!

By the way, is there anyway to kinda filter what is useful 3D and useless 3D data?
Perhaps adding 3D data to the Asset List? If I choose to export all, there is a LOT of useless points coming together.
Maybe there is something already there or planned, but yeah. 
I'm having a lot of fun with this tool.

So, thank you.
## Post #116
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-19T02:32:45+00:00
- Post Title: Re: Unity Studio

Hey!
So the game where I extracted some things form had a update today.
Only one problem, barley anything works now.
It wont open the bundle files anymore, it will try to but than it just says 0 files extarcted.
Also there are a few .asset files but the textures will just show black.
Also I get an error when trying to load folder.
[http://pastebin.com/ekby5ggi](http://pastebin.com/ekby5ggi)
I got some sample files uploaded but I don't know if I am allowed to just post the link here.

Thanks in advance!
## Post #117
- Username: filharvey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 20, 2015 5:48 am
- Post datetime: 2015-11-19T21:49:50+00:00
- Post Title: Re: Unity Studio

Is it possible to save the FBX files into individual files and not one huge fbx? Or is there a good way of seperating them.
## Post #118
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-19T22:25:17+00:00
- Post Title: Re: Unity Studio

> Reply from qxoda4
>
> When you convert the file to FBX, the texture is not applied correctly .  
I'd appreciate it if you could teach me that.  

http://storage.game.starlight-stage.jp/ ... nity3d.lz4
There seems to be an anomaly in the vertex buffer.
I think I know what's going on, but I need to run more tests. Could you paste some more links?

> Reply from lolwatt
>
> When exporting the 3D data from Bakery Story 2, it reports an error, but seems to export without any issues. Just saying!
Same issue as above, I will have a look.

> Reply from lolwatt
>
> By the way, is there anyway to kinda filter what is useful 3D and useless 3D data?
Perhaps adding 3D data to the Asset List? If I choose to export all, there is a LOT of useless points coming together.
Maybe there is something already there or planned, but yeah.
I have something similar planned where the tree hierarchy will display an icon for each node type (Mesh, Camera, Light) and you will be able to select/deselect by type.

> Reply from coolkid
>
> Hey!
So the game where I extracted some things form had a update today.
Only one problem, barley anything works now.
It wont open the bundle files anymore, it will try to but than it just says 0 files extarcted.
Also there are a few .asset files but the textures will just show black.
Also I get an error when trying to load folder.
http://pastebin.com/ekby5ggi
There are two issues here
1. This is an unreleased version of Unity 5.3.0 and it looks like the have a new bundle type called "UnityFS". I will have to investigate and see how it can be extract it.
2. Those textures really are black. They seem to be 120x128 placeholders for the real textures, which could be downloaded after the game is installed

> Reply from filharvey
>
> Is it possible to save the FBX files into individual files and not one huge fbx? Or is there a good way of seperating them.
No. There's no sure way way to tell which mesh objects are part of the same model/scene in order to separate them.
I could make it so that each mesh is exported in a single FBX file ,but that would screw up models made up of several meshes.
It's best to just look for yourself in the hierarchy tree and export models one by one or in groups.
## Post #119
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-19T23:52:09+00:00
- Post Title: Re: Unity Studio

Hey Chipicao!
Thanks for checking it out!
I noticed that there where some new files, there is also a file present called".Manifest" also I found some .low and . high files.
Let me know if you need those in order for your investigation. 
Thanks!
## Post #120
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-20T10:48:07+00:00
- Post Title: Re: Unity Studio

> Reply from chrrox
>
> Another Unity 5 game.
ワールド エンド エクリプス - The World End Eclipse
http://theworldendeclipse.jp/
Thanks, this one seems to work with the current version.
## Post #121
- Username: Maleioch
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 22, 2015 4:31 am
- Post datetime: 2015-11-21T20:46:01+00:00
- Post Title: Re: Unity Studio

Hello,

I'm trying to extract models with animations and textures from a Unity game just released.  It is Sword Coast Legends.  We have been given the okay to mod the game by the developers as long as we don't touch the dll's and exe.

I haved tried numerous programs to extract models and textures with some success here and there.  But none of them will extract the animations, animation controllers, avatars or materials.  Just the model as .obj and textures as .png/.tga.

I just tried your Unity Studio application and was surprised to find that when I extracted the model to fbx and dragged it into unity it had it's material and avatar.  Still no animation controller or animations.  I have to extract the textures still with another program because yours doesn't extract the .tex files.   It also must have the UV Map mixed up because the textures don't apply correctly to the models.  Anyway.  I hope you continue to develop this application because it seems to be a step in the right direction for unity game modding.
## Post #122
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-21T22:41:31+00:00
- Post Title: Re: Unity Studio

New version released
- workaround for Unity 5 vertex buffer anomaly (should fix export errors and UV coordinates)
- re-wrote code for loading and extracting bundle files
- fixed link problem with instances of skinned geometry
- separated normal and bump map texture slots in FBX
- added transparency factor in FBX materials


@Maleioch Thanks for you feedback and appreciation.
Could you please tell me the name of this game so I can test it?
Animation controllers are planned, but still a long way to go.
All textures should be extracted correctly, unless they are not directly linked to materials (for example changeable skins). Even so, you can extract them with Unity Studio from the Assets list, without the need for other programs.
If it's a Unity 5 game, please try the new version I just released, which should fix some issues with UV coordinates.
## Post #123
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2015-11-21T23:38:40+00:00
- Post Title: Re: Unity Studio

hi~Chipicao,thx u tool
get some error Index was outside the bounds of the array
game: Mordheim City of the Damned,resources.assets,resources.resource
## Post #124
- Username: Maleioch
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 22, 2015 4:31 am
- Post datetime: 2015-11-22T04:54:48+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> 
@Maleioch Thanks for you feedback and appreciation.
Could you please tell me the name of this game so I can test it?
Animation controllers are planned, but still a long way to go.
All textures should be extracted correctly, unless they are not directly linked to materials (for example changeable skins). Even so, you can extract them with Unity Studio from the Assets list, without the need for other programs.
If it's a Unity 5 game, please try the new version I just released, which should fix some issues with UV coordinates.

The game I'm attempting to mod is Sword Coast Legends.  Downloading your update now.  Eager to try it out.  Thanks

Update:  I haven't noticed any changes.  I did determine that I have to flip the texture files horizontally in order for them to match the model in the FBX.  I didn't have this issue with other extractors.  Flipping the textures is a workaround for now.
## Post #125
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-22T10:33:57+00:00
- Post Title: Re: Unity Studio

> Reply from Maleioch
>
> The game I'm attempting to mod is Sword Coast Legends.  Downloading your update now.  Eager to try it out.  Thanks

Update:  I haven't noticed any changes.  I did determine that I have to flip the texture files horizontally in order for them to match the model in the FBX.  I didn't have this issue with other extractors.  Flipping the textures is a workaround for now.
OK, I think I know where the issue is.
First of all Unity Studio fails to detect a texture format used in this game. @coolkid I think you had this issue as well but I didn't see it at the time.

Second, you're probably using a different tool to extract textures. And that tool is the one flipping textures in the first place, so you have to flip them back.
Once I add support for this new texture format all should be good.

Expect a new version sometime this evening (EEST).
## Post #126
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-22T14:34:31+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> Maleioch wrote:The game I'm attempting to mod is Sword Coast Legends.  Downloading your update now.  Eager to try it out.  Thanks

Update:  I haven't noticed any changes.  I did determine that I have to flip the texture files horizontally in order for them to match the model in the FBX.  I didn't have this issue with other extractors.  Flipping the textures is a workaround for now.
OK, I think I know where the issue is.
First of all Unity Studio fails to detect a texture format used in this game. @coolkid I think you had this issue as well but I didn't see it at the time.

Second, you're probably using a different tool to extract textures. And that tool is the one flipping textures in the first place, so you have to flip them back.
Once I add support for this new texture format all should be good.

Expect a new version sometime this evening (EEST).

Thanks Chipicao. The textures worked before the game update tho.
Were you able to get any 3D mesh out of the game I was trying to extract it from?
I cant seem to figure it.(Using your updated version)
## Post #127
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-22T18:14:09+00:00
- Post Title: Re: Unity Studio

This new texture type was introduced with a recent Unity 5 version, that's why it worked before.

I haven't been able to figure out those files yet. It's a new type of unity3d format and I'm not even sure it should be extracted or loaded "as is".
I think they call it "AssetBundle Realtime Decompression". I may find more info once Unity 5.3.0 is released to the public.
## Post #128
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-11-22T21:24:07+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> This new texture type was introduced with a recent Unity 5 version, that's why it worked before.

I haven't been able to figure out those files yet. It's a new type of unity3d format and I'm not even sure it should be extracted or loaded "as is".
I think they call it "AssetBundle Realtime Decompression". I may find more info once Unity 5.3.0 is released to the public.

O oke, Good luck man!
## Post #129
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2015-11-23T23:12:08+00:00
- Post Title: Re: Unity Studio

hi
have problem with this 
Its works all good  
But when i export a example a char it export fbx with textures but when i import it in 3d max or unity3d it looks like blurred but the texture is ok ??+

version 5.1.1f1

Also the same bug come on the newst version 5.3x
Thx you 
[3.PNG](https://xentaxbackup.github.io/file/10064_3.PNG)
## Post #130
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-24T10:34:29+00:00
- Post Title: Re: Unity Studio

No, it doesn't look ok.

But if you don't tell me the name of this game I can't look into it.
## Post #131
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2015-11-24T15:15:38+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> No, it doesn't look ok.

But if you don't tell me the name of this game I can't look into it.

here is the game [https://dl.dropboxusercontent.com/u/766 ... ceman.html](https://dl.dropboxusercontent.com/u/76693643/English%20Policeman/English%20Policeman.html)
it using 5.1.1f1
## Post #132
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-24T21:55:32+00:00
- Post Title: Re: Unity Studio

No problems here. Are you sure you're using the latest version of Unity Studio?

[](http://www.imagebam.com/image/a398d0449218947)
## Post #133
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2015-11-25T02:11:40+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> No problems here. Are you sure you're using the latest version of Unity Studio?
hi i use version unity studio 0.5.0.0.

Edit:I dont now why it happend this but i have download now the same programm and now it works 
But hmm im confused .
Only what i make is in the unity studio folder are all my assets maybe this will breaking it ?
## Post #134
- Username: sam319
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 25, 2015 1:45 pm
- Post datetime: 2015-11-25T05:58:57+00:00
- Post Title: Re: Unity Studio

Could you add some console parameters?
Like call "Unity Studio.exe path/font.assetBundle" to run Unity Studio and open asset bundle directly.
Then I can do some method in Unity...

Thank you.
## Post #135
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-25T11:38:16+00:00
- Post Title: Re: Unity Studio

@rayleigh Sorry, I'm not changing the internal version number for every minor update. The box.com link is always the same and I just announce new releases here.
You can see version numbers in the GitHub release page if you're interested.

@sam319 OK, I'll add that.
But what exactly are you looking to achieve? To extract assets and load them back in Unity?
## Post #136
- Username: qxoda4
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 31, 2012 7:13 pm
- Post datetime: 2015-11-25T12:04:58+00:00
- Post Title: Re: Unity Studio

hi

Thank you for the update of the great unity studio    
In the future, do you have any plans to implement a function of extracting a link AssetBundles?
## Post #137
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-11-25T12:36:32+00:00
- Post Title: Re: Unity Studio

> Reply from qxoda4
>
> hi

Thank you for the update of the great unity studio    
In the future, do you have any plans to implement a function of extracting a link AssetBundles?
You're welcome!

What exactly do you mean by "extracting a link AssetBundles"? What link?
## Post #138
- Username: qxoda4
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 31, 2012 7:13 pm
- Post datetime: 2015-11-25T13:08:13+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> What exactly do you mean by "extracting a link AssetBundles"? What link?
wanted to get the manifest list of files in the urls to download the additional files....But it will need to record a log from the proxy server
## Post #139
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2015-11-26T00:04:35+00:00
- Post Title: Re: Unity Studio

he @Chipicao is it possible to export animation in fbx in the future ?
## Post #140
- Username: sam319
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 25, 2015 1:45 pm
- Post datetime: 2015-11-26T01:30:46+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> 
@sam319 OK, I'll add that.
But what exactly are you looking to achieve? To extract assets and load them back in Unity?

I just want to confirm the contents in assetbundle. Thank you very much.
## Post #141
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-28T20:41:39+00:00
- Post Title: Re: Unity Studio

Hi, can anyone help me with a problem I seem to be having?

Trying to export some models from Afro Samurai 2: Revenge of Kuma using Unity Studio and I've run into an issue. When I export to .fbx and import into Max, I end up with models like this.



Then when I export this to .fbx and import in Blender, I get this.



Was just wondering what I'm doing wrong? I think it may be a problem with the models, as some don't even export in t-pose and it seems impossible for them to export them like that. If it isn't an inherent problem with the models, is there anything I can do here? I think I've tried everything in the fbx import options in Max and in the export options for Unity Studio.

Here's some of the FBX files I exported from Unity Studio, if anyone is willing to take a look. Can also try to pull up the raw assets if anyone needs them. Thank you. 

[http://www.mediafire.com/download/5tcqu ... +Files.rar](http://www.mediafire.com/download/5tcquxpj7fdy6rr/Sample+Files.rar)
## Post #142
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-11-28T21:21:26+00:00
- Post Title: Re: Unity Studio

> Reply from DXFan619
>
> Hi, can anyone help me with a problem I seem to be having?

Trying to export some models from Afro Samurai 2: Revenge of Kuma using Unity Studio and I've run into an issue. When I export to .fbx and import into Max, I end up with models like this.



Then when I export this to .fbx and import in Blender, I get this.



Was just wondering what I'm doing wrong? I think it may be a problem with the models, as some don't even export in t-pose and it seems impossible for them to export them like that. If it isn't an inherent problem with the models, is there anything I can do here? I think I've tried everything in the fbx import options in Max and in the export options for Unity Studio.

Here's some of the FBX files I exported from Unity Studio, if anyone is willing to take a look. Can also try to pull up the raw assets if anyone needs them. Thank you. 

http://www.mediafire.com/download/5tcqu ... +Files.rar

Open the fbx in noesis and re-export it to fbx, open it in 3ds max and export to whatever format you want.
## Post #143
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-29T08:32:25+00:00
- Post Title: Re: Unity Studio

> Reply from Darko
>
> Open the fbx in noesis and re-export it to fbx, open it in 3ds max and export to whatever format you want.

Thanks for the help! After messing around with these instructions, I realized that the problem I was having didn't have anything to do with the .fbx format and Max/Blender. It was with Skin Deformers within Unity Studio. The models I initially exported had problems because of their deformers. I tried on some other models and got great results.



^ After exporting that, it works fine in Blender and can be posed without a problem.



The problem now is that some models aren't A-posed, and they look something like this. 



The only way to get them into A-Pose is to turn off skin deformers in the Unity Studio export options, but that leads to this.



No deformers = no bones.

Is there any way in Unity Studio or elsewhere to force A-Pose for these sorts of models so they can properly export with the correct pose and bones? Thanks again for the initial help. Noesis turned out to be a good tool in rooting out this problem, and I had no clue that it also exported in .psk. I'd been looking for a program that could do that.
## Post #144
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-12-01T14:00:08+00:00
- Post Title: Re: Unity Studio

> Reply from DXFan619
>
> After messing around with these instructions, I realized that the problem I was having didn't have anything to do with the .fbx format and Max/Blender. It was with Skin Deformers within Unity Studio. The models I initially exported had problems because of their deformers. I tried on some other models and got great results.
Could you please make a quick list with models that have this problem so I can investigate? I don't need actual files, only their names and location in scene hierarchy.


> Reply from DXFan619
>
> Is there any way in Unity Studio or elsewhere to force A-Pose for these sorts of models so they can properly export with the correct pose and bones?
I'll see if it's possible.
## Post #145
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-12-01T17:07:41+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> DXFan619 wrote:After messing around with these instructions, I realized that the problem I was having didn't have anything to do with the .fbx format and Max/Blender. It was with Skin Deformers within Unity Studio. The models I initially exported had problems because of their deformers. I tried on some other models and got great results.
Could you please make a quick list with models that have this problem so I can investigate? I don't need actual files, only their names and location in scene hierarchy.

DXFan619 wrote:Is there any way in Unity Studio or elsewhere to force A-Pose for these sorts of models so they can properly export with the correct pose and bones?
I'll see if it's possible.

Sure, of course. 

prop_polecat_dj (Located in file "level9" ; scene hierarchy is level9 -> SCENE ROOT -> GAMEPLAY -> PROGRESSION -> GPA 0 -> DYNAMIC PROPS)
archangel (Located in file "level9" ; scene hierarchy is level9 -> SCENE ROOT -> GAMEPLAY -> NPC)
prop_stripper_dance_polecat4 (Located in file "level9" ; scene hierarchy is level9 -> SCENE ROOT -> GAMEPLAY -> PROGRESSION -> GPA 0 -> DYNAMIC PROPS -> Stage_animated)
Old_Bar_Tender relaxed (Located in file "level9" ; scene hierarchy is level9 -> SCENE ROOT -> GAMEPLAY -> NPC)
female_assassin:polecat_03 (Located in file "level9" ; scene hierarchy is level9 -> SCENE ROOT -> GAMEPLAY -> VISUALS -> SCENE VISUALS HOST -> SCENE_VISUALS_ROOT -> Terrain -> Bar Scene -> Dynamic -> Characters -> pole_cat_sitting_ani)

I try and extract from any other level file, and the models load normally. It seems to be contained to this level in specific.
## Post #146
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2015-12-01T22:32:24+00:00
- Post Title: Re: Unity Studio

@CHIPICAO how import mesh from nitro nation and nitro nation stories??
## Post #147
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2015-12-04T00:47:49+00:00
- Post Title: Re: Unity Studio

Hey Chipicao! just checkin.
Got any news on those manifest files yet?
## Post #148
- Username: hackspeedok
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Aug 10, 2014 5:44 am
- Post datetime: 2015-12-09T06:21:47+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> DXFan619 wrote:After messing around with these instructions, I realized that the problem I was having didn't have anything to do with the .fbx format and Max/Blender. It was with Skin Deformers within Unity Studio. The models I initially exported had problems because of their deformers. I tried on some other models and got great results.
Could you please make a quick list with models that have this problem so I can investigate? I don't need actual files, only their names and location in scene hierarchy.

DXFan619 wrote:Is there any way in Unity Studio or elsewhere to force A-Pose for these sorts of models so they can properly export with the correct pose and bones?
I'll see if it's possible.

Can you help me, i have an encrypted image and i can't replace its in the resources.assets

[https://drive.google.com/file/d/0B2fmFY ... sp=sharing](https://drive.google.com/file/d/0B2fmFYUfOr3NUGRzRFBkVmFHUWM/view?usp=sharing)
## Post #149
- Username: Cerophono
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 19, 2014 7:42 am
- Post datetime: 2015-12-09T13:04:16+00:00
- Post Title: Re: Unity Studio

Seems like Unity 5.3 has a new encryption scheme?
I only know about this in a naive sense, but does this mean that Unity Studio needs to be updated to extract a 5.3 build? 
Is this only for WebGL builds or for all builds?

> Data files will now be LZ4 compressed in memory. In WebGL, you don’t have access to a real file system. For this reason, we will keep all your assets in memory all the time. In Unity 5.3, asset data in memory is compressed using LZ4, and will only be decompressed when assets are loaded. This means that your asset data will use less space in memory, and you will be less likely to run out of memory.
[http://blogs.unity3d.com/2015/12/07/uni ... l-updates/](http://blogs.unity3d.com/2015/12/07/unity-5-3-webgl-updates/)
## Post #150
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-11T09:53:23+00:00
- Post Title: Re: Unity Studio

Hello Chipicao!  

I tried interesting feature of Unity Studio - Shader Export, but it might not be working properly...

I took CSR Classics for a test and tried bunch of shaders in different versions of Unity3D but none of them work.
Every shader(even simple ones) tell the same error: It basically won't compile

I will try something simplier to see if it works
[UPD]
Tried a bunch of games,even the newest CSR 2,none of the exported shaders works for some reason (Even in unity 5) But I think It's the issue inside the unity,I'm searching for the way to fix it.

[UPD 2]
I think I found a problem why they can't be used - they are already compiled/precompiled for specific platform,that's why they won't start...I guess

By the way,I wonder if Unity Studio can export actual C#/JavaScripts in the future? That would be really amazing stuff for learning!
## Post #151
- Username: Rancher
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 22, 2015 11:00 am
- Post datetime: 2015-12-12T23:20:29+00:00
- Post Title: Re: Unity Studio

> Reply from Chipicao
>
> 
@lolwatt unfortunately Ori is built with Unity 5 beta, and research for beta builds will require considerable time.
Still, I made some changes that should prevent failures, and as far as I can tell most assets from Ori are loaded fine now.
Yes, Ori is built with Unity 5.0.0b5. Unity Studio can open the textures just fine, I think, but other resources are problematic. It cannot extract most of them. Can you try to support it in the future? Thank you in advance!
## Post #152
- Username: AhrimanSefid
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 07, 2011 4:55 pm
- Post datetime: 2015-12-13T20:36:47+00:00
- Post Title: Re: Unity Studio

Very good software but add item import files.
thank you.
## Post #153
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-12-21T09:55:06+00:00
- Post Title: Re: Unity Studio

I know Unity Studio was updated to work fine with Star Wars Galaxy of Heroes a while back, however the models seem to have no weights when they are exported. Any chance this could be looked at? I uploaded some samples.
[GalaxyOfHeroesSamples.rar](https://xentaxbackup.github.io/file/10179_GalaxyOfHeroesSamples.rar)
## Post #154
- Username: badthug88
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 29, 2015 4:35 pm
- Post datetime: 2015-12-29T09:52:55+00:00
- Post Title: Re: Unity Studio

Thank you so much, i can easy extract sound and all of assets on game!
## Post #155
- Username: nobody231
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 09, 2014 11:59 am
- Post datetime: 2015-12-31T19:24:55+00:00
- Post Title: Re: Unity Studio

I'm trying to rip 3D models from Sonic Runners. However, the only things that pop out are Texture2D files and Shader files. In the Unity Importer script I've seen here, the models and textures come out, but nothing else. Here's a link to the .sharedAssets file: [https://onedrive.live.com/redir?resid=2 ... aredAssets](https://onedrive.live.com/redir?resid=211DFCABF32AFB94!99094&authkey=!AEG1D3sdhzEXBMc&ithint=file%2CsharedAssets)

Could you take a look, and see if there's anything with it that can be done?
## Post #156
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-05T10:49:46+00:00
- Post Title: Re: Unity Studio

> Reply from TRDaz
>
> I know Unity Studio was updated to work fine with Star Wars Galaxy of Heroes a while back, however the models seem to have no weights when they are exported. Any chance this could be looked at? I uploaded some samples.

I'm also starting to see models like echo and fives and tons others (like jedi,pirates,clones,stormtroopers and more) i was able to get out when he first supported this game now not working and it only gets out their weapons when it clearly shows their head,body....ect in the scene hierarchy.
## Post #157
- Username: brokenspicerack
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 09, 2016 1:24 am
- Post datetime: 2016-01-08T17:26:14+00:00
- Post Title: Re: Unity Studio

I was able to extract bundles until 5.3. I think its because of the WebGL lz4 compression that they added.
## Post #158
- Username: SeriousNorbo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 27, 2016 6:24 am
- Post datetime: 2016-01-26T22:33:16+00:00
- Post Title: Re: Unity Studio

I have a small problem...

Tool can't see few models from resources.assets, when i looked in that file with "Unity Assets Explorer" i saw all the .43 meshes, but almost none of them is visible in hierarchy tree through your program.
## Post #159
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2016-01-31T19:57:06+00:00
- Post Title: Re: Unity Studio

Hi  

I was looking trough some assets and noticed that Unity Studio detects cubemaps but doesn't export them
Is that a bug or it's impossible to extract them?
## Post #160
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2016-02-12T20:35:12+00:00
- Post Title: Re: Unity Studio

Aniway to get animation
## Post #161
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2016-02-19T17:42:09+00:00
- Post Title: Re: Unity Studio

Chipicao,

I've been trying to find the models of Saint Seiya Zodiac Battle - Android - APK

I managed to extract the CAB-* files, both from the .APK and on Root/data/data 
I'm able to extract 3D-buildings, 3D-scenery, UI-textures, Audios, etc, but none of the 3D-characters appear...

I've noticed that some CAB just display "__crypto__" on the Assets List and I'm betting those are the 3D-characters.

How can I open those files?

Sample - 547 kb - [http://www.mediafire.com/download/mcdyx ... cc94e2.rar](http://www.mediafire.com/download/mcdyxa023x8obpy/1a3a7d2bac75f5b8f44b917ecff06ef0cdcc94e2.rar)
## Post #162
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-02-23T18:38:37+00:00
- Post Title: Re: Unity Studio

Hello guys, tell me what additional libraries needed to run the program except NetFramework 4.0? I be happening crash when running on WindowsXP.
## Post #163
- Username: 0355
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 24, 2016 4:45 pm
- Post datetime: 2016-02-25T08:01:31+00:00
- Post Title: Re: Unity Studio

Hi Chipicao, as you noted extracting from CSR 2 returns an "exploded" model. Did you manage to find a way to reassemble it using the "bone" structure yet? Or do I have the only option to do it manually?

Thanks
## Post #164
- Username: epfcg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 28, 2016 2:39 pm
- Post datetime: 2016-02-28T23:03:54+00:00
- Post Title: Re: Unity Studio

I get an arithmetic operation overflow from trying to export a simple rigged model which is a tail.  I'd rather not go through and change things to Int64 because It might mess up other things.  Is there any simple fix for this?
See the end of this message for details on invoking 
just in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.OverflowException: Arithmetic operation resulted in an overflow.
   at Unity_Studio.Material..ctor(AssetPreloadData preloadDany a)
   at Unity_Studio.UnityStudioForm.WriteFBX(String FBXfile, Boolean allNodes)
   at Unity_Studio.UnityStudioForm.Export3DObjects_Click(Object sender, EventArgs e)
   at System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   at System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   at System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.ToolStrip.WndProc(Message& m)
   at System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPt
## Post #165
- Username: ab010108
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 13, 2014 3:45 pm
- Post datetime: 2016-03-12T08:45:32+00:00
- Post Title: Re: Unity Studio

How do you find the file filename extension?

Examples of the accompanying 1024 or 2048 size texture.

[https://www.dropbox.com/s/a16u9kpnwcwnk ... 6.tex?dl=0](https://www.dropbox.com/s/a16u9kpnwcwnkij/HanSoYoung%20%2300105_1024x1024.46.tex?dl=0)
[https://www.dropbox.com/s/yl8mj3spqoknq ... 5.tex?dl=0](https://www.dropbox.com/s/yl8mj3spqoknqak/w_school_1%20%2319020_2048x2048.45.tex?dl=0)
## Post #166
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2016-03-18T22:53:00+00:00
- Post Title: Re: Unity Studio

I'm sorry, but at the moment I don't have any time to work on this.
There have been so many new Unity releases since I last investigated... it's like a full time job 

All I know is that starting with Unity 5, they introduced "DXTn Crunched" textures, which are pain to read or convert. But there are tools available to convert such textures to standard DXT, use Google.
## Post #167
- Username: xLumexMoonx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 11, 2016 11:19 pm
- Post datetime: 2016-04-11T17:50:10+00:00
- Post Title: Re: Unity Studio

Srry For Bump...

Games: Atlas Reactor.

Unity Studio can't not open the *.assets.resS  File, there's texture in the *.assets.resS File.

Here sample:

[http://www.mediafire.com/download/khthl ... r_Data.rar](http://www.mediafire.com/download/khthlhrrhh39pat/AtlasReactor_Data.rar)

If U Have Any Time.

Srry For Poor English...
## Post #168
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2016-04-17T00:01:23+00:00
- Post Title: Re: Unity Studio

new update and some games are not possible to open it
## Post #169
- Username: NeonZed
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 09, 2015 11:15 pm
- Post datetime: 2016-04-20T04:15:17+00:00
- Post Title: Re: Unity Studio

Sorry to ask but, I wanted to try the new version of the Unity Studio, but theres no .exe file like the old version in it when I redownload. How to open Unity Studio?
## Post #170
- Username: dzikar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 21, 2016 7:35 pm
- Post datetime: 2016-04-21T11:46:51+00:00
- Post Title: Re: Unity Studio

Do not download [https://app.box.com/v/unitystudio](https://app.box.com/v/unitystudio) 
Do not compiled [https://github.com/RaduMC/UnityStudio](https://github.com/RaduMC/UnityStudio) (1000+ errors)
## Post #171
- Username: s25jin
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2016-04-22T11:33:30+00:00
- Post Title: Re: Unity Studio

dzikar
[https://github.com/RaduMC/UnityStudio/r ... .5.1b3.zip](https://github.com/RaduMC/UnityStudio/releases/download/v0.5.1b3/Unity.Studio.v0.5.1b3.zip)
## Post #172
- Username: angelasvv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 13, 2013 2:22 pm
- Post datetime: 2016-04-28T19:02:22+00:00
- Post Title: Re: Unity Studio

file：[https://onedrive.live.com/redir?resid=3 ... file%2cZIP](https://onedrive.live.com/redir?resid=3830AB84E050FD26!677&authkey=!AE-rWBou5NI3pA8&ithint=file%2CZIP)

how can i export the .ssax files?
## Post #173
- Username: ryuanime
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu May 05, 2016 7:31 pm
- Post datetime: 2016-05-12T19:49:48+00:00
- Post Title: Re: Unity Studio

I'm trying to understand how to extract the models file date or obb the game android bleach brave souls Android.

I am very confused how to proceed.

I already downloaded the apk and has nothing interesting there.

So I downloaded the obb but do not know how to draw, until I see where the characters station.

Extension is * .pb

thanks for the help
## Post #174
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-05-13T13:20:34+00:00
- Post Title: Re: Unity Studio

Anyone got a download link for Unity Studio that works? When I go to [https://app.box.com/v/unitystudio](https://app.box.com/v/unitystudio) and press "download" it does nothing and doesn't give me a download.
Tried with several browsers, no luck.
## Post #175
- Username: Rovaski
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 14, 2016 12:59 am
- Post datetime: 2016-05-13T18:40:48+00:00
- Post Title: Re: Unity Studio

When I "extract all 3d models" It lumps them all into one single file. How can I prevent this and just extract them individually?
## Post #176
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2016-05-26T23:57:21+00:00
- Post Title: Re: Unity Studio

Hi Chipicao, I'm trying to extract the vehicle models and textures from Table Top Racing World Tour using the Unity Studio, the models are extracted well, but the textures have some problem. They are only black, transparents and some textures are blue.
I know this game use Unity 5, probably the version 5.3.4.
Do you know how can I extract then? Some manual way?
I have plans to convert some cars to Burnout Paradise.

Edit: ok, I managed to do this manually, I just found the position of the start and the size of each texture on the resources file. After I save it as a new file and put a "image header" on the begin.
Here is a render from Huuligun:
[http://i.imgur.com/FkS3Og0.jpg](http://i.imgur.com/FkS3Og0.jpg)
## Post #177
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2016-05-29T02:55:59+00:00
- Post Title: Re: Unity Studio

update please no works on  unity 5.3.4
## Post #178
- Username: swtor enthusiast
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 31, 2013 5:23 am
- Post datetime: 2016-06-28T19:05:53+00:00
- Post Title: Re: Unity Studio

I am also having issues with a 5.3.4f1 game:

[http://i.imgur.com/9a6XIM6.png](http://i.imgur.com/9a6XIM6.png)

Older versions of the game from pre-5.3 Unity extracted fine, but now I'm getting blank black images and bugged .dds files.
## Post #179
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2016-06-29T08:28:24+00:00
- Post Title: Re: Unity Studio

Hello Chipicao!

I was looking trough Drift Spirits (Japanese only title) and found that all the UnityCache files look different than in any other game I saw before.

Moreover,they cannot be opened with 3DSMax Scripts or Unity Studio. (Even if you change file name to something silly such as CAB-3UI52LG343252)
I have to mention that just a couple of months ago everything was ok...and it does not really looks like they moved to Unity5 or some sort...

Cache files come in pair and this is definetly the Unity cache file(I checked it by uploading new cars into the memory)
"__info" holds some sort of number/value and "__data" is the file that used to hold everything inside.

Here's an example(folder name unchanged)
[http://www.mediafire.com/download/g4did](http://www.mediafire.com/download/g4did) ... _Files.rar

Maybe it can be fixed?
## Post #180
- Username: kenwandou
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 02, 2014 1:08 pm
- Post datetime: 2016-06-30T08:54:51+00:00
- Post Title: Re: Unity Studio

update please no works on unity 5.3.4
## Post #181
- Username: snappyapple632
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 01, 2016 5:13 am
- Post datetime: 2016-06-30T21:24:16+00:00
- Post Title: Re: Unity Studio

Hi. I have to say this is a very useful program! I am having issues trying to open extracted Texture2D and audio files. After converting an image from .dds to .png by renaming the extension, I get this error trying to open it in another program saying that the file format is not supported, despite already being in a readable format. However I can view the file just fine. Are extracted audio and texture files encrypted? Thanks!
## Post #182
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2016-07-06T17:53:18+00:00
- Post Title: Re: Unity Studio

> Reply from snappyapple632
>
> Hi. I have to say this is a very useful program! I am having issues trying to open extracted Texture2D and audio files. After converting an image from .dds to .png by renaming the extension, I get this error trying to open it in another program saying that the file format is not supported, despite already being in a readable format. However I can view the file just fine. Are extracted audio and texture files encrypted? Thanks!

You should convert .DDS to .PNG , and not just rename the extension of file manually.

Use Paint.NET for example. Open your .DDS image and then save it as .PNG , and everything will be fine
## Post #183
- Username: snappyapple632
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 01, 2016 5:13 am
- Post datetime: 2016-07-06T18:35:13+00:00
- Post Title: Re: Unity Studio

OK, I'll try that. Notably this happens with the raw photo as well.

Update: Still no dice. Opening up the raw .DDS in Photoshop with the read-only completely disabled gives me this: 


Screenshot (17).png (122.57 KiB) Viewed 355 times
## Post #184
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2016-07-07T13:38:49+00:00
- Post Title: Re: Unity Studio

Heya, hoping somebody can help.
So I've exported models from the game Final Fantasy G-bike before using Unity Studio, but I lost them. I tried no again to export the models from the same files I used last time, but now every model always exports to a 2kb file. Im not sure what exactly is going on. Exporting models from other games are still working fine, but for some reason its just this game
## Post #185
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2016-07-11T16:10:01+00:00
- Post Title: Re: Unity Studio

> Reply from jfwfreo
>
> Anyone got a download link for Unity Studio that works? When I go to https://app.box.com/v/unitystudio and press "download" it does nothing and doesn't give me a download.
Tried with several browsers, no luck.
Same here...not able to download
## Post #186
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-11T22:05:08+00:00
- Post Title: Re: Unity Studio

> Reply from jfwfreo
>
> Anyone got a download link for Unity Studio that works?
> Reply from parttimegamer15
>
> Same here...not able to download
[https://github.com/RaduMC/UnityStudio/releases](https://github.com/RaduMC/UnityStudio/releases)
## Post #187
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2016-07-16T21:11:44+00:00
- Post Title: Re: Unity Studio

> Reply from AceWell
>
> jfwfreo wrote:Anyone got a download link for Unity Studio that works?parttimegamer15 wrote:Same here...not able to download
https://github.com/RaduMC/UnityStudio/releases
Thank you!
## Post #188
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2016-07-24T13:02:39+00:00
- Post Title: Re: Unity Studio

Any word on the ".assets.resS" files?
The data is now in .assets.resS files and .assets files probably function as headers.
For example sharedassets1.assets is 175 kB and sharedassets1.assets.resS is 122 MB.
So I think .assets points to .assets.resS for the data instead of contaning the data itself.
## Post #189
- Username: adamodambrosio
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 31, 2016 2:03 am
- Post datetime: 2016-07-30T18:34:33+00:00
- Post Title: Re: Unity Studio

Hey everyone so far this tool is great, it gets the job done well. But I am having a problem with the terrain. Please watch the video below and if you know what I am doing wrong please help me, thanks.   

https://www.youtube.com/watch?v=CGUHdH5dZck
## Post #190
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-08-12T17:16:40+00:00
- Post Title: Re: Unity Studio

> Reply from glcat
>
> oh , my sysytem is XP, I can't open the exe, i don't know  why~~

> Reply from Chipicao
>
> tMake sure you have .NET Framework 4.0 installed.
I also have xp, i have istalled net 4.0, but the .exe still dont' run.
What other things is required?
## Post #191
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-12T20:07:44+00:00
- Post Title: Re: Unity Studio

i'll wager there is something in there that relies on a higher OS   
if i knew how, i would try to compile the source on XP to guarantee it works with it
## Post #192
- Username: pikachuk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 15, 2016 10:46 pm
- Post datetime: 2016-08-15T14:50:58+00:00
- Post Title: Re: Unity Studio

i'd like to modify 3d models of yandere simulator, it's good to extract 3d models but it would be awesome if we could import again, at the moment i make texture and music hacks when i use other softwares it extracts .43 models with your software it's better but it would be good to import again at 43 format
## Post #193
- Username: dragonzh
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Jul 29, 2015 1:23 pm
- Post datetime: 2016-08-20T08:54:45+00:00
- Post Title: Re: Unity Studio

> Reply from Smakkohooves
>
> glcat wrote:oh , my sysytem is XP, I can't open the exe, i don't know  why~~
Chipicao wrote:tMake sure you have .NET Framework 4.0 installed.
I also have xp, i have istalled net 4.0, but the .exe still dont' run.
What other things is required?
Support XP
[https://drive.google.com/open?id=0B1kwx ... jgyUEl0a28](https://drive.google.com/open?id=0B1kwxI2ELDqyUjQ5bjgyUEl0a28)
## Post #194
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2016-09-13T23:49:42+00:00
- Post Title: Re: Unity Studio

mhh looks like 5.3x+ no more support good for me ^^
## Post #195
- Username: RicoKwothe
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 03, 2014 9:47 pm
- Post datetime: 2016-09-17T13:31:33+00:00
- Post Title: Re: Unity Studio

Never Alone (ps3 version) resources.assets, not working. Why?
## Post #196
- Username: Akselier
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 20, 2016 12:37 am
- Post datetime: 2016-09-19T23:41:50+00:00
- Post Title: Re: Unity Studio

Is there a way to convert the FSB files extracted from Unity Studio?
I keep getting Not a valid FSB file format (FileID: 0x00000000) errors. Any help would be greatly appreciated here.
## Post #197
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2016-10-02T19:56:57+00:00
- Post Title: Re: Unity Studio

^^^

the FSB's don't even extract correctly they are all blank when i look at em in a hex editor.

sample:

[https://www.dropbox.com/s/cx3z3y6azeraa ... ssets?dl=0](https://www.dropbox.com/s/cx3z3y6azeraaad/Voice_GST30.tmp.assets?dl=0)
## Post #198
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-10-14T04:43:48+00:00
- Post Title: Re: Unity Studio

Great tool, well done!   

Only thing I miss is vertical UV flip option for exported models.
## Post #199
- Username: flipdark95
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 08, 2016 12:24 pm
- Post datetime: 2016-10-15T12:26:27+00:00
- Post Title: Re: Unity Studio

Just wondering, how do I extract single meshes? I can't find any of them by searching and the only way is to extract all meshes which creates a huge FBX file that I can't open properly.
## Post #200
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-10-16T20:00:42+00:00
- Post Title: Re: Unity Studio

> Reply from flipdark95
>
> Just wondering, how do I extract single meshes? I can't find any of them by searching and the only way is to extract all meshes which creates a huge FBX file that I can't open properly.
Something like that:
[](http://fastpic.ru/view/84/2016/1016/e0c6e43749de90616acfc4459f76531c.png.html)
Five checked meshes (and their textures) will be extracted in this case.

With some loss of assembly and structure:
[](http://fastpic.ru/view/84/2016/1017/db59718826232a884afa2e8233c8755f.png.html)

So, it's better to keep groups and skip only unnecessary meshes for good result, like this:
[](http://fastpic.ru/view/83/2016/1017/6e11238a90c4298496b131682bbc59bd.png.html)
(materials are reworked on this pic)
## Post #201
- Username: GameDragon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 14, 2016 7:54 am
- Post datetime: 2016-10-19T13:24:17+00:00
- Post Title: Re: Unity Studio

I'm getting some inconsistencies when exporting with Unity Studio. A few of the normals on extracted models seem to not be smoothed. When using the Unity Importer 3ds Max script however, the normals import and export just fine.

I'm not sure how I should go about fixing this. I'd much rather use Unity Studio for bone exports, but I don't seem to be getting the results I want.
## Post #202
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-10-20T14:57:44+00:00
- Post Title: Re: Unity Studio

> Reply from GameDragon
>
> A few of the normals on extracted models seem to not be smoothed.
Got similar problems with importing to Deep Exploration directly from FBX, but in 3dsmas2016 smoothing in FBX imports looks good, same as from script importer.
So, I use FBX>Max2016>Deep Exploration pipeline for fine result.
## Post #203
- Username: Vygar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 26, 2016 12:12 am
- Post datetime: 2016-11-11T21:18:37+00:00
- Post Title: Re: Unity Studio

This tool looks extremely handy.  However, the App Box link doesn't appear to be working (the download buttons don't work).  Also, the source code is missing a few reference dlls and can't be built. Anyone have an alternate link?

Edt - Nevermind.  Found the answer a few pages back
## Post #204
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2016-11-23T16:02:20+00:00
- Post Title: Re: Unity Studio

This tool is amazing
But can you make it avable to used on Win XP?
I'm cheap computer user, I can't update my computer to Win 7 or higher ;-;
## Post #205
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-24T20:50:06+00:00
- Post Title: Re: Unity Studio

[viewtopic.php?p=121773#p121773](http://forum.xentax.com/viewtopic.php?p=121773#p121773)
## Post #206
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2016-11-26T11:52:01+00:00
- Post Title: Re: Unity Studio

Curious, has there been any attempt updating the program to support the new unity 5 engine?
## Post #207
- Username: hessam1376
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 19, 2015 2:30 am
- Post datetime: 2016-12-08T16:19:14+00:00
- Post Title: Re: Unity Studio

i have Problem With Shaders i cant use them    . all shaders rip from android game dont work but i use unity 4.6 game rip and import shader in unity 4.6  and i test many games in many version unity   . im sory for my pad english type. plz help me and tanks for Unity Studio
## Post #208
- Username: coolkid
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jul 11, 2015 8:56 pm
- Post datetime: 2016-12-29T18:40:11+00:00
- Post Title: Re: Unity Studio

hmm is this working for newer Unity games? I am having problems exporting models and textures are either really low quality or just shows black.
## Post #209
- Username: duongham2511
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 06, 2017 11:31 pm
- Post datetime: 2017-01-08T17:33:06+00:00
- Post Title: Re: Unity Studio

Well, I was extracting some CGs from a file, then this happened:




I tried every way I could find and it's still not fixed, please tell me what to do.
Thank you
## Post #210
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-01-13T07:45:30+00:00
- Post Title: Re: Unity Studio

> Reply from duongham2511
>
> Well, I was extracting some CGs from a file, then this happened:




I tried every way I could find and it's still not fixed, please tell me what to do.
Thank you
Just click continue!
## Post #211
- Username: Adolfok3
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 11, 2014 2:13 am
- Post datetime: 2017-02-27T04:36:54+00:00
- Post Title: Re: Unity Studio

No news about import files?
## Post #212
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-21T02:54:33+00:00
- Post Title: Re: Unity Studio

I wish someone felt interested with this tool and upgrade it ;w;
Unity Studio now can't work with assets from Unity 5.4 ;w;
## Post #213
- Username: baddis
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 11, 2017 3:25 pm
- Post datetime: 2017-04-11T07:51:09+00:00
- Post Title: Re: Unity Studio

hello all
Sorry for my English

Is reverse engineering possible (scenes, prefabs, etc.) unity of the project?
I liked one game (great top down game S-U-B-T-E-R-R-A-I-N), I want to use the movement of the character in my project. Has pulled out the code and assets, but as all to combine I do not know.

[http://icecream.me/c231a11df6d455f91dfbcbb8bc0f76bf](http://icecream.me/c231a11df6d455f91dfbcbb8bc0f76bf)

The question is how to realize the identical movement in your own scene?

big thx
## Post #214
- Username: nmkd
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 15, 2017 10:59 pm
- Post datetime: 2017-04-15T15:01:40+00:00
- Post Title: Re: Unity Studio

> Reply from ngovandang
>
> I wish someone felt interested with this tool and upgrade it ;w;
Unity Studio now can't work with assets from Unity 5.4 ;w;

Well, the project is open-source, but my coding skills are shit and I'm honestly too lazy to learn it :/
## Post #215
- Username: nathansmash9000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 18, 2017 1:22 pm
- Post datetime: 2017-05-18T05:25:11+00:00
- Post Title: Re: Unity Studio

I'm really new and don't understand most of stuff you talk about. When I exported my project, I got a .txt file. What do I do with that? Help plz
## Post #216
- Username: Aatsra
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 25, 2017 4:11 pm
- Post datetime: 2017-05-25T10:26:51+00:00
- Post Title: Re: Unity Studio

Please pardon me if I have not searched the question/answer well, but I'd like to ask if this tool is supported on macOS? If not, are there alternatives to this that support Mac for Unity-related tools? I did see the tool is .exe which concerns the issue.
## Post #217
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-05-26T08:08:28+00:00
- Post Title: Re: Unity Studio

> Reply from Aatsra
>
> Please pardon me if I have not searched the question/answer well, but I'd like to ask if this tool is supported on macOS? If not, are there alternatives to this that support Mac for Unity-related tools? I did see the tool is .exe which concerns the issue.not sure you can find ANY tool for game unpacking on internet for MAC. Extracting games is the advance thing which can be done only via advance (and flexible) tool such as PC but if you want to send email or type words or play music you use MAC. Damn, MAC doesn't even have much games on it to play.
p.s.: don't wanted to insult MAC users - I am one of MAC and PC users - just clarified things up.
## Post #218
- Username: holyvink
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 02, 2017 1:46 pm
- Post datetime: 2017-06-02T05:52:21+00:00
- Post Title: Re: Unity Studio

Hello everyone,
I have just discovered Unity Studio few days ago and it works like a charm for viewing unity3d files. I can see texture 2d and export 3d files to FBX viewer. However, no textures loaded in the 3d model.

Does Unity Studio able to export 3d model as well as the texture in FBX viewer? or do I need other program to load the 3d model + texture? Thanks.
## Post #219
- Username: MarvelousPotato
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2015 11:17 am
- Post datetime: 2017-06-06T02:05:10+00:00
- Post Title: Re: Unity Studio

Trying to EXPORT a 3D rigged mesh to fbx, (yes I am 100% sure this is a mesh) but when I hit either export all 3d objects or selected 3d objects, I get an error. I have no trouble with loading the assets file, just when I try to export the 3d model. I had no trouble beforehand, but a new update to the game seems to be root of this problem. Any solutions? Below is the error info.

************** Exception Text **************
System.OutOfMemoryException: Exception of type 'System.OutOfMemoryException' was thrown.
   at Unity_Studio.SkinnedMeshRenderer..ctor(AssetPreloadData preloadData)
   at Unity_Studio.UnityStudioForm.WriteFBX(String FBXfile, Boolean allNodes)
   at Unity_Studio.UnityStudioForm.Export3DObjects_Click(Object sender, EventArgs e)
   at System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   at System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   at System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.ToolStrip.WndProc(Message& m)
   at System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework/v4.0.30319/mscorlib.dll
----------------------------------------
Unity Studio
    Assembly Version: 0.5.0.0
    Win32 Version: 0.0.0.0
    CodeBase: file:///C:/Users/Ethan/Desktop/Unity%20Studio/Unity%20Studio.exe
----------------------------------------
System.Core
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1647.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1647.0 built by: NETFXREL3STAGE
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Windows.Forms
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System.Drawing
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
System.Configuration
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Xml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
System.Web.Extensions
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Web.Extensions/v4.0_4.0.0.0__31bf3856ad364e35/System.Web.Extensions.dll
----------------------------------------
System.Web
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.1590.0 built by: NETFXREL2
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_32/System.Web/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Web.dll
----------------------------------------

************** JIT Debugging **************
To enable just-in-time (JIT) debugging, the .config file for this
application or computer (machine.config) must have the
jitDebugging value set in the system.windows.forms section.
The application must also be compiled with debugging
enabled.

For example:

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

When JIT debugging is enabled, any unhandled exception
will be sent to the JIT debugger registered on the computer
rather than be handled by this dialog box.
## Post #220
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-12T04:37:37+00:00
- Post Title: Re: Unity Studio

just adding a link here to the user Perfare on GitHub who forked and updated Unity Studio, version is currently 0.7.0   

[https://github.com/Perfare/UnityStudio/releases](https://github.com/Perfare/UnityStudio/releases)
## Post #221
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-07-28T19:22:31+00:00
- Post Title: Re: Unity Studio

> Reply from AceWell
>
> just adding a link here to the user Perfare on GitHub who forked and updated Unity Studio, version is currently 0.7.0   

https://github.com/Perfare/UnityStudio/releases
OMG OMG
Its 0.7.0 now? I still using 0.5.1b I thought no one had planned on update this tool. OMG
 thank for this info, Acewell
## Post #222
- Username: bokoboko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Feb 07, 2018 1:11 pm
- Post datetime: 2018-02-15T08:58:39+00:00
- Post Title: Re: Unity Studio

Anyone know whether it's possible to export 3D models from several .unity3d files at the same time?

When I try File > Load Folder, the names of the .unity3d files (within that folder) are visible in the Scene Hierarchy but they don't appear to actually be loaded and the status bar reads "Finished loading X files with 0 exportable assets"

If I try File > Load File and select multiple .unity3d files, I get error "X.unity3d is bundle file, please select bundle file type to load this file"

The only way I can get .unity3d files into Unity Studio is by loading 1 at a time, and then Export > 3D Object.. but this is going to take a while with many .unity3d files.

Is there any batch method for exporting models/assets from several .unity3d files?
## Post #223
- Username: Sergie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 01, 2018 10:36 am
- Post datetime: 2018-04-01T02:38:10+00:00
- Post Title: Re: Unity Studio

Is this normal that github.com ain't letting us download the UnityEditor?
