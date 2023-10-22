## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-05-18T13:41:10+00:00
- Post Title: The Matrix / UE5 tech demo tool

As we all know, most assets from Matrix demo were published, but i decided to research PS5 dump as an example of future UE5 games, with its many new tech needed to be extracted.

Tool currently supports all models (with nanites), textures and map composing.

For example its Neo's room:


You may notice that in the movie it was a little different (half of the objects moved or rotated):


but after applying scene setup data, its now correct:


Neo's head has 900 bones:




and here's mesh topology:


also we can get virtual (PS5 swizzled) textures:


full models of Neo & Trinity (only hair cards now supported)




models use 12IPV weights:

[UE_matrix.7z](https://xentaxbackup.github.io/file/23836_UE_matrix.7z)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-05-18T13:43:00+00:00
- Post Title: The Matrix / UE5 tech demo tool

Now here how nanites look in compare to usual (fallback) meshes from Neo's room:




Nanite bus (2 million faces):




and also neo's nanite bed (1 million faces):


big (tiled) textures are exported as standard UDIMs:


corresponding to nanite car UVs


here's the bus which has the biggest texture (7x25 tiles)
## Post #3
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-05-20T03:09:39+00:00
- Post Title: The Matrix / UE5 tech demo tool

Oh my god this is insane, I've been waiting for these models for ages, thank you so much! When can we expect the tool to release and the instructions on how to use it? Also, do we need a PS5 build of the game or the PC version? I don't think the version on PC comes with the character models
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-20T13:43:52+00:00
- Post Title: The Matrix / UE5 tech demo tool

> Reply from AxelNoir ↑Sat May 20, 2023 11:09 am at Sat May 20, 2023 11:09 am
>
> 
Oh my god this is insane, I've been waiting for these models for ages, thank you so much! When can we expect the tool to release and the instructions on how to use it? Also, do we need a PS5 build of the game or the PC version? I don't think the version on PC comes with the character models
Why everyone keeps confusing the CitySample project with the Matrix Awakens Tech Demo on PS5? Only PS5 Tech Demo has the IP Matrix content. This has never been a secret there are two different projects, and there is no game.
No, this has nothing to do with the PC project.
## Post #5
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2023-05-20T22:45:02+00:00
- Post Title: The Matrix / UE5 tech demo tool

> Reply from daemon1 ↑Thu May 18, 2023 9:41 pm at Thu May 18, 2023 9:41 pm
>
> 
As we all know, most assets from Matrix demo were published, but i decided to research PS5 dump as an example of future UE5 games, with its many new tech needed to be extracted.

Tool will be published soon, and it currently supports all models (with nanites), textures and map composing.

You have outdone yourself yet again. I'm guessing since we have UE5 source code getting the animations aswell from UE5 games should be a walk in the park?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-05-21T08:18:53+00:00
- Post Title: The Matrix / UE5 tech demo tool

> Reply from AxelNoir ↑Sat May 20, 2023 11:09 am at Sat May 20, 2023 11:09 am
>
> 
When can we expect the tool to release and the instructions on how to use it?
It will be released soon, after some testing. And yes, it will require PS5 files.

> Reply from Bladers ↑Sun May 21, 2023 6:45 am at Sun May 21, 2023 6:45 am
>
> 
I'm guessing since we have UE5 source code getting the animations aswell from UE5 games should be a walk in the park?
Nothing is a walk in the park in UE5. It could be simple or not, you never know. At least i'm not going to look into that yet.
## Post #7
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-21T13:51:38+00:00
- Post Title: The Matrix / UE5 tech demo tool

> Reply from Bladers ↑Sun May 21, 2023 6:45 am at Sun May 21, 2023 6:45 am
>
> ...I'm guessing since we have UE5 source code getting the animations aswell from UE5 games should be a walk in the park?
Aren't those already supported by Spiritovod's custom builds of umodel for specific games that are built on UE5?
## Post #8
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2023-05-25T00:31:37+00:00
- Post Title: The Matrix / UE5 tech demo tool

> Reply from daemon1 ↑Thu May 18, 2023 9:41 pm at Thu May 18, 2023 9:41 pm
>
> research PS5 dump
Very cool to see! So I have the demo on Xbox X and PS5... But I am interested in the original movie files from the demo, because they weren't published from Unreal AFAIK, although I didn't download the assets from Unreal. Just curious if anyone knows if the video files are available out there somewhere. Then I guess I have to go looking
## Post #9
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2023-05-25T02:21:22+00:00
- Post Title: The Matrix / UE5 tech demo tool

Same here, would love to get my hands on the ps5 pkg. I wouldn't mind in anyone shared it with me in the PM. Seeing that its a free demo.
I have searched the interwebs and came up empty. I don't have the expertise to dump it myself.
## Post #10
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-25T04:06:21+00:00
- Post Title: The Matrix / UE5 tech demo tool

> Reply from relight ↑Thu May 25, 2023 8:31 am at Thu May 25, 2023 8:31 am
>
> ...anyone knows if the video files are available out there somewhere...
Out of curiosity, what kind of videos are you hoping to find? The demo is real time.
## Post #11
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2023-05-25T14:16:28+00:00
- Post Title: The Matrix / UE5 tech demo tool

> Reply from mono24 ↑Thu May 25, 2023 12:06 pm at Thu May 25, 2023 12:06 pm
>
> 
relight wrote: ↑Thu May 25, 2023 8:31 am...anyone knows if the video files are available out there somewhere...
Out of curiosity, what kind of videos are you hoping to find? The demo is real time.
For some reason I thought that the first 2:45 or so of the demo was a video file, pre-rendered (but still featuring the digital versions of Neo and Trinity), and that the "captured realtime" message at the beginning of the demo just meant captured in realtime from a console, not necessarily that none of it was prerendered. But maybe I just misread what they wrote that the demo "starts out with a cinematic that features exceptionally realistic digital humans, before morphing into a fast-paced interactive experience." I'd have to watch the demo again with the commentary and see if they say anything else, but perhaps daemon1 can clear this up. Either way, I would still be very interested in a pkg/dump for my personal archive.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-05-26T17:17:05+00:00
- Post Title: The Matrix / UE5 tech demo tool

> Reply from relight ↑Thu May 25, 2023 8:31 am at Thu May 25, 2023 8:31 am
>
> 
I am interested in the original movie files from the demo
Even though most of the demo is realtime, there are several video files in it.
## Post #13
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-05-26T17:55:30+00:00
- Post Title: The Matrix / UE5 tech demo tool

You are freaking AMAZING! I wish I was as wicked as you!
## Post #14
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2023-05-29T19:13:23+00:00
- Post Title: The Matrix / UE5 tech demo tool

@daemon1 great job completing the tool, unfortunately no one i know has the files nor is it available anywhere.
Would you care to upload the files seeing as its a free game?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-06-01T18:28:39+00:00
- Post Title: The Matrix / UE5 tech demo tool

Tool posted. It requires 2 files to work (these files must be in same folder as the tool):
- global.ucas from game dump
- data.bin

You need to extract assets from PAK file with a special UModel build for UE5 by Spiritovod.
Then you can use the tool to convert individual assets, or all assets in a folder.

1. To convert one asset, drop asset file onto the tool, or run the tool from command line with asset filename as parameter.

If asset file contains a texture, in will be exported to "textures" subfolder in Directx10 DDS format. After that you can convert them to the format you like.

If asset file contains static or skeletal mesh, in will be exported to ASCII. Raw data will also be saved in "staticmesh.raw" & "skeletalmesh.raw" folders for later use in map extraction. If static mesh contains nanite data, it will also be exported to "nanite" folder.

If asset file contains a material, it will create "material.db" file with information for later use in map extraction. If "material.db" file already exists next to the tool, it will be updated with newly found materials.

2. To convert all assets in a folder, place the tool in that folder and run it. Tool will search that folder and all subfolders for .uasset files and try converting them all. When prompted "are you sure?" you can press "enter" to confirm or Ctrl-C to cancel.

3. To convert maps, drop .umap file onto the tool, or run the tool from command line with umap filename as parameter. Current version will extract only static meshes from a map.

For map extraction to work, "staticmesh.raw" folder with previously extracted data must be in the same folder with the tool. If some models will be missing, tool will give messages.

If "material.db" file will be next to the tool, material information from that file will be used to place texture names in the output ASCII file, so when loaded, all textures will be applied automatically. 

If there will be no "material.db" file, or some materials will be missing in that file, tool will give error messages. In that case you can search and apply them manually.
## Post #16
- Username: cbflex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 21, 2023 1:25 pm
- Post datetime: 2023-09-21T05:27:50+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

Hey can you post the models of Neo and Trinity?
Im working on a Matrix Mod for Half Life Alyx, where i recreate the 1st films action scenes, and i could really use their models... Otherwise ill have to sculpt them from scratch
## Post #17
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-09-22T15:46:11+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

> Reply from cbflex ↑Thu Sep 21, 2023 1:27 pm at Thu Sep 21, 2023 1:27 pm
>
> 
Hey can you post the models of Neo and Trinity?
Im working on a Matrix Mod for Half Life Alyx, where i recreate the 1st films action scenes, and i could really use their models... Otherwise ill have to sculpt them from scratch

I can Dm you a link I have to them but be warned, they're over 1 million polygons and comprised of over 800-900 bones each. I'd be interested in seeing how you optimise the models to work in HL:A
## Post #18
- Username: Banner2020
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 23, 2020 6:54 pm
- Post datetime: 2023-09-23T01:36:54+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

> Reply from AxelNoir ↑Fri Sep 22, 2023 11:46 pm at Fri Sep 22, 2023 11:46 pm
>
> 
cbflex wrote: ↑Thu Sep 21, 2023 1:27 pm
Hey can you post the models of Neo and Trinity?
Im working on a Matrix Mod for Half Life Alyx, where i recreate the 1st films action scenes, and i could really use their models... Otherwise ill have to sculpt them from scratch


I can Dm you a link I have to them but be warned, they're over 1 million polygons and comprised of over 800-900 bones each. I'd be interested in seeing how you optimise the models to work in HL:A
May I also have one?
## Post #19
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2023-09-23T13:05:51+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

Me too
## Post #20
- Username: mpisc192
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 02, 2018 5:03 am
- Post datetime: 2023-09-27T23:44:46+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

Also interested!
## Post #21
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2023-10-01T06:38:42+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

> Reply from mono24 ↑Sun May 21, 2023 9:51 pm at Sun May 21, 2023 9:51 pm
>
> 
Bladers wrote: ↑Sun May 21, 2023 6:45 am...I'm guessing since we have UE5 source code getting the animations aswell from UE5 games should be a walk in the park?
Aren't those already supported by Spiritovod's custom builds of umodel for specific games that are built on UE5?

unfortunately, there is a tag/encryption error when attempting to export the animation using the custom umodel tool.
## Post #22
- Username: darkssektor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 29, 2019 10:54 pm
- Post datetime: 2023-10-18T11:07:38+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

> Reply from Banner2020 ↑Sat Sep 23, 2023 9:36 am at Sat Sep 23, 2023 9:36 am
>
> 
AxelNoir wrote: ↑Fri Sep 22, 2023 11:46 pm
cbflex wrote: ↑Thu Sep 21, 2023 1:27 pm
Hey can you post the models of Neo and Trinity?
Im working on a Matrix Mod for Half Life Alyx, where i recreate the 1st films action scenes, and i could really use their models... Otherwise ill have to sculpt them from scratch


I can Dm you a link I have to them but be warned, they're over 1 million polygons and comprised of over 800-900 bones each. I'd be interested in seeing how you optimise the models to work in HL:A

May I also have one?

Good afternoon, can I get these models? And if possible the Agents' models.
## Post #23
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-18T12:52:29+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

Ok I'm a little tired of constantly receiving PMs about this and seeing that this site is gonna get nuked pretty soon, I might as well just leave the link here for anyone coming across this:

[https://mega.nz/folder/qOIGBDrR#D90yv3W8-Idmo1suhl0fVA](https://mega.nz/folder/qOIGBDrR#D90yv3W8-Idmo1suhl0fVA)

I didn't rip these models just FYI so I don't really know what's what in them and don't ask me about that either, use at your own discretion.
## Post #24
- Username: darkssektor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 29, 2019 10:54 pm
- Post datetime: 2023-10-20T07:39:35+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

> Reply from relight ↑Thu May 25, 2023 8:31 am at Thu May 25, 2023 8:31 am
>
> 
daemon1 wrote: ↑Thu May 18, 2023 9:41 pmresearch PS5 dump
Very cool to see! So I have the demo on Xbox X and PS5... But I am interested in the original movie files from the demo, because they weren't published from Unreal AFAIK, although I didn't download the assets from Unreal. Just curious if anyone knows if the video files are available out there somewhere. Then I guess I have to go looking
can I ask you to send the demo files of Xbox X and PS5 versions?
## Post #25
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-10-20T21:19:34+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

> Reply from darkssektor ↑Fri Oct 20, 2023 3:39 pm at Fri Oct 20, 2023 3:39 pm
>
> ...send the demo files of Xbox X...
Xbox, after x360, is pretty much unhackable, i doubt there will ever be a hacked console version to extract assets from games since most are on PC already, PS5 version of the demo is already all over internet easy to get.
## Post #26
- Username: darkssektor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 29, 2019 10:54 pm
- Post datetime: 2023-10-21T03:58:12+00:00
- Post Title: Re: The Matrix / UE5 tech demo tool

> Reply from mono24 ↑Sat Oct 21, 2023 5:19 am at Sat Oct 21, 2023 5:19 am
>
> 
darkssektor wrote: ↑Fri Oct 20, 2023 3:39 pm...send the demo files of Xbox X...
Xbox, after x360, is pretty much unhackable, i doubt there will ever be a hacked console version to extract assets from games since most are on PC already, PS5 version of the demo is already all over internet easy to get.
I can't find anything to download the original ps5 demo, only reviews, speculation and such, can I ask you to send a site in private messages where exactly the original demo is.
