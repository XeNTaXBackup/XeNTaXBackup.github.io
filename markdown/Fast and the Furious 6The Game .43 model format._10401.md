## Post #1
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-08T09:44:37+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

Hello all,

 This is my first post and I have tried search everywhere for answers to this. I bought the fast and furious 6 game for ipod touch.
game is fun and all that. I found out, through this wonderful forum, that you can take that .IPA and just rename it as a .zip file. did that and unzipped the game. Turns out it's a Unity 3d engine game. that's the good news.

 Using a tool to extract the resource asset main file I found the car I was looking for. the 1972 ford torino.  she's in many peices not including the texture files which are stored as both .TEX and .mat files. the mesh itself is stored in a ".43" file format.

 the maker is Universal (vevendi I believe) it just hit the market last week to amp people up for the new movie coming out later this month. there is an android version as well. I don't own an android phone but am willing to buy that version if it would be best to work with.

 I can provide one mesh file that is in the ".43" file format if that will help. I am a novice model researcher. I am learning a lot from this forum and hope someone knows how to ultimately get this file converted over to 3d studio max if possible. it's like the model is right there but just out of reach. any help would be greatly appreciated.
## Post #2
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-08T17:23:22+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

well, upon further research I found a plugin for Noesis for Unity 3d .43 format.  yeaaah.

 only Noesis keeps throwing up these errors.

 when I click on the now visible .43 file for the body of the car it tells me this

"Trackback (most recent call last.)
File:"C:\USER\-name omitted-\downloads\fast and furious 6 experiment\noesis40785\plugins\python\fmt_Unity3d_43.py",
line 27, in noepyLoadModel
  Mdl= rapi.rpgConstructModel()
Runtime Error:Failed to Construct Model from rpgeo context."

 I press "Ok" and it informs me that "This model cannot be previewed but may be exportable.would you like to export it? I click "yes"

 The Usual export module appears and it allows me to export to .obj which I need to study the model.
 I leave everything in this module as defult. and press "ok"

it tells me again:

"Trackback (most recent call last.)
File:"C:\USER\-name omitted-\downloads\fast and furious 6 experiment\noesis40785\plugins\python\fmt_Unity3d_43.py",
line 27, in noepyLoadModel
  Mdl= rapi.rpgConstructModel()
Runtime Error:Failed to Construct Model from rpgeo context."

 but then pops up one last message "Export complete" yet when I go to see what file has come out and in what state it is in,there is no file.
Granted given the above the file would probably be useless anyways. but is there something I am not doing here? I exported the model from my game using an unity3d engine asset viewer which has an exporter. I exported not just the mesh but all texture files releated to the mesh.

 Noesis says hey no problem I know that format thanks to this new plugin. and this is the result. I am stumped. has anyone else run into this and if so did you solve it and how? 

 thank you again for any information you can give me.
## Post #3
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-09T00:55:14+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

uploaded two mesh files still in the .43 format. this is unity 3d engine but again I can only extract I cannot phrase the file in a way that would work withoy specific 3d program at this time.

[http://www.mediafire.com/?mcbn5d4kzgur5m4](http://www.mediafire.com/?mcbn5d4kzgur5m4)

 any help would be greatly appreciated.
## Post #4
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-18T07:51:04+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

I've hit a deadend in my research on this type of archive. sadly Noesis has a unity3d.43 filter but even it cannot seem to open or translate this archive into a useable mesh. which is sad. but okay if I but the cars entire mesh up along with the texture files might that help some of you out there? I did see that the file I posted previously was downloaded at least twice.

 I don't mean to bump this I just wishing to know if anyone knows anything. thank you all for your time.
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-18T09:45:47+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

Format is pretty understandable. I tried model you provided, no wheel just body and the hood.
[car.jpg](https://xentaxbackup.github.io/file/6405_car.jpg)
## Post #6
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-18T10:16:27+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

may I ask what tools you used or can you point me into the right direction for the model format because I've been burning through google and forums like this trying to figure out how to unlock this format to research this exact mesh and had no luck.
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-18T10:23:22+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

Well, I wrote simple script to import model directly in 3ds max. If you need info about format I can tell you what I know.
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-19T10:17:10+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

Here's simple maxscript to import models from this game (geometry and uv's).


[Fast_Furious_a.43.7z](https://xentaxbackup.github.io/file/6408_Fast_Furious_a.43.7z)
## Post #9
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-19T17:43:34+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

I want to thank zaramot personally for his work on this script. this game features a car that is very near and dear to my heart for reasons I won't bore you with. thanks to the efforts of zaramot. I can now study this model and recreate a car that has meaning to me and one that I have not seen in games in a good long time. for me this script will allow me to honor someones memory and also let a legendary vehicle live on.

 I have much work to do but I appreciate the efforts of zaramot, as well as this forum. without you all so much wouldn't be possible. thank you all so much.
## Post #10
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-05-28T14:35:06+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

> Reply from octaviousrex
>
> uploaded two mesh files still in the .43 format. this is unity 3d engine but again I can only extract I cannot phrase the file in a way that would work withoy specific 3d program at this time.

http://www.mediafire.com/?mcbn5d4kzgur5m4

 any help would be greatly appreciated.

Umm, excuse me octaviousrex, may i ask you from which file of the game contains those .43 files for cars? And what program did you use to extract those cars .43 file from the assets file?
I seemed to be unable to find the car files.
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-05-28T15:45:05+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

You should use Unity Assets Explorer [v 1.2] in order to open and extract content from Unity bundle files.
[viewtopic.php?f=10&t=10085](http://forum.xentax.com/viewtopic.php?f=10&t=10085)
## Post #12
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-05-28T16:03:40+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

I have used that program. Problem is, it seems that i cannot find any .43 file(s) with any name of cars on it. I have searched through "resources.assets" until "sharedassets23.assets" , but i only see map/level files of it. I went inside to ios>cars and found this file "bundle_cars.assetbundle" file, which had the size of 89,1 MB. I believe it is where the car files are stored? But the format is different. And when i rename the format into .assets, Assets Explorer just stopped responding. It does list something like the assets contains 8 million files inside.
## Post #13
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-28T18:31:12+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

resources.assets

 I found the car files but yes,you are right, no .43 format seems to show up in the directory when using the tool. what I did was find all
the files withe the cars name. If I rememeber correctly you can click for the asset viewer to pair all files by name. then I simply higlighted all the
files for one car and clicked extract. when I went the to newlyformed "recources" folder there were .43 format mesh files.

that's how I got the files out out. somewhere in the vehicle specific files in Rexoures.assets is the files that get extracted out when you extract a speciifc asset. if that makes sense. it seems like it's warlock magic but it's not. and I have gotten the meshes I needed for some much needed research. but be aware the models are hallow and and do lack an underside model. so if you want to research them for their bodies that is fine. but any other the main guts of the car's themselves well you'll have to make them from scratch if you want to use for other games.

 it's not bad I mean the gran torino at least looks very detailed when fully extracted but it's not usefull for say a game you ref modeling for like grand theft auto where the bottom of the car could be seen.

 hope that helps if not I'll do a step by step tutorial on how I got the files out. they don't seem to be there but trust me they are there.
if all else fails. open up the recources.asset file and press "extract all" there is a lot to sort through but it will extract everything including the seemingly unseen .43 format files.
## Post #14
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2013-05-29T10:47:54+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

How much is the poly count for the cars? They look high-poly for a mobile game.
## Post #15
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-05-29T16:28:58+00:00
- Post Title: Fast and the Furious 6:The Game .43 model format.

Guess i still can't find any. I tried extracting all files in resources.assets (File Size: 51885032), but these were the only .43 file i found:
1_left_pause_bg.43
3_stage_time.43
4_time_countdown_right.43
flag.43
flag_glow.43
mapUI_bggrid_01.43
mapUI_keyline_01.43
mapUI_randomicon_02.43
mapUI_ring_01.43
pPlane1.43
top_bar_bg_geo.43

The rest are .-43 files with numbers as their names, and the only files i found which had car manufacturers names on it, were mainly their logos texture (which appear above cars on race start). I've been stuck on this progress as of now.
## Post #16
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-05-29T16:31:30+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

> Reply from huckleberrypie
>
> How much is the poly count for the cars? They look high-poly for a mobile game.
Imo, cars are not that high poly. Textures are the ones that made the car look highly detailed. The only game which contains high poly car models for a mobile game should be Real Racing 3. They mostly convert cars from NFS: SHIFT 2 Unleashed into the game. The rest are The RUN and newly made cars for the game.
## Post #17
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-30T01:20:09+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

tell you what. I still have all the cars plus wheels extracted on my hard drive pm me the files you want and I'll send them to you if you'd like.
## Post #18
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-05-30T03:45:30+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

> Reply from octaviousrex
>
> tell you what. I still have all the cars plus wheels extracted on my hard drive pm me the files you want and I'll send them to you if you'd like.

Problem is... I need all of the car files (tires included). I'm planning to do a render out of every one of them, and convert few to SA. But i do appreciate your request of sending me the files though.
## Post #19
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-30T19:34:27+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

> Reply from huckleberrypie
>
> How much is the poly count for the cars? They look high-poly for a mobile game.

 at this point I don't recall I have only just started in on delving into the meshes myself. that said,on the outside they are rather nicely 
poly but the odd thing is they have only half interriors. what I mean is when you get the mesh in a 3d modeler like 3d max you find out that there
is only have a steering wheel or a half a seat. so anything below the window is pretty much non existant. they also have nearly no bottom. it's
a flat surface with false geomtry skinned on since you generally not going to see the bottom of the car.

 to make them into a useable game model you have to basically enjoy the hallow model as it makes eyeing the verts of the body so much easier. but then you have to go and find a decent refs for the engine,trunk,interrior and if the car you are using is to be a game model in a game that
allows you to see the bottom then you also need to create your own bottom which adds a ton more poly. I'll try to get a count when I have
time to work with the mesh again. but yeah for a mobile game I was surprised at the detail myself.

 it's partly I guessing cause you do get to see the cars upclose when you select them so they probably figured that one model would be best for
the game rather then having the usual one model for show and one model for play. but again having a mostly hallow mesh does help with the
poly count.
## Post #20
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-30T19:54:54+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

> Reply from REDZOEU
>
> octaviousrex wrote:tell you what. I still have all the cars plus wheels extracted on my hard drive pm me the files you want and I'll send them to you if you'd like.

Problem is... I need all of the car files (tires included). I'm planning to do a render out of every one of them, and convert few to SA. But i do appreciate your request of sending me the files though.

 well the resource folder is the only one I found with actual mesh files for the cars in it. I am not sure why the unity asset manager isn't finding
the mesh files but I have the .43 files for all cars with tires. the cars share one tire file that comes in two sizes. I know this cause I found the
tire file when resorting out the resources folder for the cars. so I know what the files are and where they are I am just curious as to why you yourself cannot find them.

 I used "UnityAssetsExplorer-1.2"  to open up "resources.assets"

 one of the first cars you'll bump into is :
"bmw_1m_coupe_body_a.43"

 from there I tended to find the other makes and models.

the first tire file is names this
"tire_muscle_25_16_a.43"

 and there are two of these files as said they have two sizes for the tires. there are also spoiler mesh files but I haven't messed with those much.

 as to converting to say. here what I know from my research on the 1972 gran torino:  that's possible but you need more then just these mesh files to work with. for one thing they have no real undercarriage. I mean a good skin can take of that but really you will likely want to model a bottom for the car. you'll also have to cut poly for  the doors and trunk since the only thing detached as a seperate mesh is the hood. the windows can be easily detatched but the side windows are one solid plane.so you'd have to cut poly for the door windows for instance.

 you'd need model an entirely no interrior,trunk space and engine with engine bay as all this is abscent from the hallow mesh and what interrior does exist is only a partial thing. nothing below the car door windows exists to say poly in the mobile game.

 so if you looking for a quick and easy conversion job (cause I know gta modding well been doing it for years) then these cars are not it. but
if you looking for fun project cars to put hard work into then these cars are magnificent for that. I am currently remaking the torino from the ground up using the mesh as a guide because it was a car my father,who recently passed,loved and I want to pay tribute to him
through gta. this is a labor of love for me and so the extra work is worth it for me. 

 these cars are nicely detailed and are a great shell. but you need more then a shell in gta. thought to be honest the stock body makes for a 
great collision file or chassis_vlo file without needing to touch a thing.

 if you still cannot find the files I have all the cars,car textures and yes even the tires in their original .43 format on my hard drive and am willing to host the files and send a link in a pm if you are still willing to put in the work on the files that these cars would deserve.
## Post #21
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-06-01T16:07:15+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Whoa, now this is funny. I downloaded FF6 version 1.0.2 and found out the resource.assets file are 50 MB bigger. And i found the car files like blur wheel, brakedisc, licenseplatelondon, etc. Guess problem's solved. My game is version 1.0.3 so ye. They probably moved the files on this version.
## Post #22
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-06-01T20:07:06+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

aww I should have asked which version you had. interesting. well happy converting. if you convert them successfully please pm me to where you are hosting them.
## Post #23
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-06-02T06:34:34+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Well, guess i stumbled on another problem. Texture files which were automatically converted into .dds on extraction were broken. They look like grids of rainbows and some empty spaces. More like a broken TV screen. Any idea why this is happening? I used Paint.NET to open the converted .tex files on .dds format.

Below is the converted "bmw_1m_coupe_rim_blur.tex" file.

Texture resolution is 512x512, and the blank spaces are actually alpha image.
## Post #24
- Username: khm666
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 24, 2011 9:18 pm
- Post datetime: 2013-06-04T06:44:48+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Can anyone please help with .tex formt and how we can convert it to TGA , i've tried changing the headers but its not working for me , any tips ?
## Post #25
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-06-04T11:35:09+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Those textures are in PVRTC format, so they need a different header.

Here's the format specification where you will find the header structure: [http://www.imgtec.com/powervr/insider/d ... ternal.pdf](http://www.imgtec.com/powervr/insider/docs/PVR%20File%20Format.Specification.1.0.11.External.pdf)
It should be easy to build, I did it in maxscript a while ago.

The problem is that even if you use the right header, PVR textures are specific to mobile platforms, so you'll have to convert them to something else in order to use them in other games.
The tool for this job would be [PVRTexTool](http://www.imgtec.com/powervr/insider/powervr-pvrtextool.asp)
## Post #26
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-06-05T02:50:07+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

thanks so much Chipicao. I myself am a good modeler but a lousy skinner so I am not the one who could have answered this. I think Chipicao's solution works for you all. myself I'll have a good friend skin my torino when it's done.
## Post #27
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-06-05T03:56:32+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Well chipicao, i'm quite lost on how to open or convert the tex file. I downloaded PVRTexTool (on installer, i untick everything except PVRTexTool), and tried to drag and drop the .tex file or open it. It says that it's not recognized.
Sorry, i'm not that familiar with file headers or complex texture compression format. All i do is convert cars to other games so, yeah. :\
## Post #28
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-06-08T16:53:34+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

I tried to come up with a simple guide but I can't. Not because it's difficult, but because you need some information from the unity image header in order to find the right texture format.

So instead I'm uploading all textures from the game here: [http://www.mediafire.com/download/c00jh ... w/maps.rar](http://www.mediafire.com/download/c00jhxh6gg95z8w/maps.rar)
Let me know if you have any trouble with them.
## Post #29
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-06-09T10:53:49+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

> Reply from Chipicao
>
> I tried to come up with a simple guide but I can't. Not because it's difficult, but because you need some information from the unity image header in order to find the right texture format.

So instead I'm uploading all textures from the game here: http://www.mediafire.com/download/c00jh ... w/maps.rar
Let me know if you have any trouble with them.

Whoa bro, can't believe you went through all that trouble to get the textures of the game for the community. Your work will be very much appreciated. Thanks
## Post #30
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2013-06-13T03:18:18+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

> Reply from Chipicao
>
> I tried to come up with a simple guide but I can't. Not because it's difficult, but because you need some information from the unity image header in order to find the right texture format.

So instead I'm uploading all textures from the game here: http://www.mediafire.com/download/c00jh ... w/maps.rar
Let me know if you have any trouble with them.

bro，that is allsome，thank you very~~~~veyr~~~~~much , it works good for me,
## Post #31
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-06-13T09:23:45+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

If you guys are interested, I have released a Unity maxscript importer [here](http://kotschopshop.com/topic/5134976/1).
It works directly with level# and .assets files, because that's how unity files are meant to be loaded. "Extracting" them is a waste of time, because you lose important data such as mesh transformations, hierarchy or material linking.

[](http://www.imagebam.com/image/cad64d260008269)
## Post #32
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-06-13T10:14:40+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

fantastic work man. truly.
## Post #33
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2013-06-13T13:17:00+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

You deserved a medal. Truly credit to team!
## Post #34
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2014-03-12T12:40:34+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

How to decompress "bundle_cars.assetsbundle"?   
Probably, It contains car data. Because "resource.assets" and so on contains no car data.

I Want to extract Honda Prelude Type-S(3D Model)!!!
## Post #35
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-12T13:42:41+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Use barracuda's modified quickbms script to extract it: [viewtopic.php?p=86592#p86592](http://forum.xentax.com/viewtopic.php?p=86592#p86592)

You'll get a CAB file that can be imported with my script.
## Post #36
- Username: bushey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 22, 2014 6:15 am
- Post datetime: 2014-11-22T18:41:11+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

> Reply from zaramot
>
> Format is pretty understandable. I tried model you provided, no wheel just body and the hood.

Hi folks, im also having the same issues with converting .43 format unity mesh files into something more useful. Zaramot, have you released your conversion script for public use? If not would you mind converting a couple of meshes for me. 
Failing that, what software is able to extract and convert the .43 mesh files to obj. I tried disunity but I keep getting errors saying that it's not working. 

Any help would be appreciated. 

Cheers!
## Post #37
- Username: bertan06
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 26, 2014 10:31 pm
- Post datetime: 2014-11-26T16:10:56+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Hi!

I have ".43" format files. How do i open it?

---------------------------------------------------------------------------------

Edit: No problem, i solved
## Post #38
- Username: dongvanhung
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 29, 2014 2:37 pm
- Post datetime: 2015-04-01T06:19:45+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Could someone post all of car models download link to here ?

Many Thanks
## Post #39
- Username: 3080
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 27, 2014 11:49 am
- Post datetime: 2015-06-12T16:56:54+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

I also have a ".43 " file that came from my daughters "Monster High - Monster Maker" Toys software program. The file is called "TorsoMesh.43" If you need the file you the original program you can download the program for free for the Monster High web sit. See this link:
[http://www.monsterhigh.com/en-us/monste ... maker.html](http://www.monsterhigh.com/en-us/monstermaker/monster-maker.html)#
I'm very new at this, and I would like some help. Please. I can't seem to get the "Fast_Furious_a.43.ms" to work with this file on Autodesk 3ds Max 2010. I used "UnityAssetsExplorer.exe (v1.2)" to extract the file from the " sharedassets0.assets " file after it was installed the toys software program.

Will any one please help me with this?  
[TorsoMesh.rar](https://xentaxbackup.github.io/file/9300_TorsoMesh.rar)
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-12T19:26:17+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

using hex2obj (view link in my sig):



TorsoMesh.JPG (53.71 KiB) Viewed 95 times

(unsure about uv pos)
## Post #41
- Username: sunrise
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 14, 2016 1:09 am
- Post datetime: 2016-12-13T17:23:00+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

Hi all, how can open this one's object. I tried to open the assets file with the asset unity importer by Chipicao. But the importer did not find the file to import. Opening the file with the asset UnityAssetsExplorer. I was able to get a few files .43. Tell me if there is a 3d model and how to get it?
[Outlander_MK3_l_FrontDoor.rar](https://xentaxbackup.github.io/file/12042_Outlander_MK3_l_FrontDoor.rar)
## Post #42
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-14T03:15:34+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

MK3_I_Frontdoor.JPG (39.4 KiB) Viewed 44 times


uvs not found; maybe uvpos 24 and 32? (hex2obj uses uvpos, uvpos+4 for floats).
## Post #43
- Username: sunrise
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 14, 2016 1:09 am
- Post datetime: 2016-12-14T10:27:46+00:00
- Post Title: Re: Fast and the Furious 6:The Game .43 model format.

> Reply from shakotay2
>
> MK3_I_Frontdoor.JPG
uvs not found; maybe uvpos 24 and 32? (hex2obj uses uvpos, uvpos+4 for floats).
Thanks for the answer. Yes maybe uvpos 24 and 32. It turns out I could via hex2obj try to get this model?
