## Post #1
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-09T13:15:45+00:00
- Post Title: Marvel Avengers Alliance II Android

Hi guys, I need help extracting the models from the Marvel Avengers Alliance II game.

[http://www.mediafire.com/file/ep9dbwrjd ... ab.Low.rar](http://www.mediafire.com/file/ep9dbwrjdh17s6w/iron_man03.prefab.Low.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-09T14:48:46+00:00
- Post Title: Marvel Avengers Alliance II Android

To my knowledge "UnityFS" is a bundle type that noone has extracted so  far.
## Post #3
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-09T15:19:26+00:00
- Post Title: Marvel Avengers Alliance II Android

> Reply from shakotay2
>
> To my knowledge "UnityFS" is a bundle type that noone has extracted so  far.

Actually yes, see this post.

[http://deant01.deviantart.com/art/She-H ... -585190833](http://deant01.deviantart.com/art/She-Hulk-Marvel-Avengers-Alliance-2-beta-585190833)

Unfortunately this guy does not respond.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-09T15:36:24+00:00
- Post Title: Marvel Avengers Alliance II Android

what does that mean: "does not respond"? Within the last two hours, or what?  
(my philosophy is to completely ignore guys who do not respond  )

Anyways, admitted, I was wrong. Look here for an extractor; I'm just fiddeling around with the raw files  it produces:
[https://7daystodie.com/forums/showthrea ... -Extractor](https://7daystodie.com/forums/showthread.php?22675-Unity-Assets-Bundle-Extractor)

The authors name is "DerPopo"  - but it works (somehow):



ironman.JPG (17.69 KiB) Viewed 563 times
## Post #5
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-09T15:50:48+00:00
- Post Title: Marvel Avengers Alliance II Android

> Reply from shakotay2
>
> what does that mean: "does not respond"? Within the last two hours, or what?  
(my philosophy is to completely ignore guys who do not respond  )

Anyways, admitted, I was wrong. Look here for an extractor; I'm just fiddeling around with the raw files  it produces:
https://7daystodie.com/forums/showthrea ... -Extractor

The authors name is "DerPopo"  - but it works (somehow):
ironman.JPG

How do I proceed with this extractor?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-09T16:10:31+00:00
- Post Title: Marvel Avengers Alliance II Android

export a Raw file from here:



Assetbundle-extractor.JPG (85.86 KiB) Viewed 561 times


then try to find point clouds using hex2obj (view link in my sig).

Use this H2O file:

0x0 500
Vb1
12 99
0x1384 500
020400
0x0 255

with the noPtC button switched to PtCld.

(don't have the time for further investigations. So you're on your own when searching for face indices, FIs.)

You could do an Export Dump, too.

In View Data there's PackedBitVector Triangles (21084 items). Might be/contain FIs (or not).
## Post #7
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-09T16:36:08+00:00
- Post Title: Marvel Avengers Alliance II Android

> Reply from shakotay2
>
> export a Raw file from here:
Assetbundle-extractor.JPG
then try to find point clouds using hex2obj (view link in my sig).

Use this H2O file:

0x0 500
Vb1
12 99
0x1384 500
020400
0x0 255

with the noPtC button switched to PtCld.

(don't have the time for further investigations. So you're on your own when searching for face indices, FIs.)

You could do an Export Dump, too.

In View Data there's PackedBitVector Triangles (21084 items). Might be/contain FIs (or not).

Thanks for help me.
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-09T17:15:05+00:00
- Post Title: Marvel Avengers Alliance II Android

okay, 
UABE can open the newer unity assets but it doesn't support compressed meshes
Unity Studio is the only tool that supports compressed meshes
UABE is also a package modding tool where you can modify packages 

knowing this, we open iron_man03.prefab.Low.assetbundle with UABE 
and find the mesh then "Export Raw" this will save it as somename.dat
then we open an older unity package with UABE that Unity Studio can open
and we select a file of the same type (mesh) and click "Import Raw" and 
select the somename.dat that you export earlier and click File > Save
now we open that modified Unity package with Unity Studio and export the
compressed mesh as fbx  



ironman.png (103.62 KiB) Viewed 552 times
## Post #9
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-09T17:28:53+00:00
- Post Title: Marvel Avengers Alliance II Android

> Reply from AceWell
>
> okay, 
UABE can open the newer unity assets but it doesn't support compressed meshes
Unity Studio is the only tool that supports compressed meshes
UABE is also a package modding tool where you can modify packages 

knowing this, we open iron_man03.prefab.Low.assetbundle with UABE 
and find the mesh then "Export Raw" this will save it as somename.dat
then we open an older unity package with UABE that Unity Studio can open
and we select a file of the same type (mesh) and click File > Add and 
select the somename.dat that you export earlier and click File > Save
now we open that modified Unity package with Unity Studio and export the
compressed mesh as fbx  
ironman.png

Amazing!!! Thanks.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-09T18:13:10+00:00
- Post Title: Marvel Avengers Alliance II Android

> Reply from AceWell
>
> then we open an older unity package with UABE that Unity Studio can open
and we select a file of the same type (mesh) and click File > Add and 
select the somename.dat that you export earlier and click File > Save
now we open that modified Unity package with Unity Studio and export the
compressed mesh as fbxwell, made my day.

There's nothing more to say than: I'm deeply impressed. 

Ace, just out of curiosity: did you find out this by yourself?

(I've a deja vue that this kind of trick was used years ago with some other game/tools.)
## Post #11
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-09T18:34:52+00:00
- Post Title: Marvel Avengers Alliance II Android

Friends, you are amazing!!! Many thanks for the help, I have tried to unravel this mystery for some time. Thank you.
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-09T19:51:37+00:00
- Post Title: Marvel Avengers Alliance II Android

@dswd2015
thats great man!   

> Reply from shakotay2
>
> Ace, just out of curiosity: did you find out this by yourself?

(I've a deja vue that this kind of trick was used years ago with some other game/tools.)
i have deja vue every day it seems  , this process is just from my experience with those programs
and some bits of info here and there i managed to piece together and fortunately it worked.  

yeah i think this tutorial by dswd2015 where he used UABE to decompress a package for Unity Studio
gave me the idea to try this with compressed meshes.
[viewtopic.php?p=124410#p124410](http://forum.xentax.com/viewtopic.php?p=124410#p124410) 

i am extremely interested in learning how compressed mesh data is restored by Unity Studio
and i eventually want to make a Noesis python script that can open these types of model files.  
i think this has the code in it
[https://github.com/RaduMC/UnityStudio/b ... es/Mesh.cs](https://github.com/RaduMC/UnityStudio/blob/master/Unity%20Studio/Unity%20Classes/Mesh.cs)

i just need to make sense of it
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-09T20:37:16+00:00
- Post Title: Marvel Avengers Alliance II Android

> Reply from AceWell
>
> i just need to make sense of itin my experience (in most cases) it takes more time to understand other people's code than to write it from scratch.  

An intermediate method that would make sense to me:
set 4 or 5 breakpoints (BP) in the C# project where the vertices, normals, uvs and face indices are read.
Then extract a simple model and at each BP do single step debugging to get the idea(s).

That's how I would do it.
## Post #14
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-01-11T01:07:02+00:00
- Post Title: Marvel Avengers Alliance II Android

> Reply from AceWell
>
> @dswd2015
thats great man!
 hi
Thank for all of your helps
Can you teach me how to extract this bundle file?
[http://www.fenglee.com/game/aog/aog.unity3d](http://www.fenglee.com/game/aog/aog.unity3d)
Please check it, I can't open it
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-11T02:13:13+00:00
- Post Title: Marvel Avengers Alliance II Android

UnityEX can open your sample   
[http://www.zoneofgames.ru/forum/index.p ... opic=36240](http://www.zoneofgames.ru/forum/index.php?showtopic=36240)

after you open the package browse through the dropdown menu in the upper right
and select resources.assets, this contains many textures and .43 mesh files.
you can export out the *.mesh files and change the extension to *.43 and use 
finale00's Noesis python script to open those   
[http://himeworks.com/redirect.php?type= ... Unity3D_43](http://himeworks.com/redirect.php?type=noesis&name=Unity3D_43)

edit
just in case you have trouble getting UnityEx i uploaded a copy of the one i used

```
http://www.mediafire.com/file/t65vjhgt50t5g63/UnityEX_1.5.4.7z
```

i think 1.5.7 is the newest version
## Post #16
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-11T09:32:18+00:00
- Post Title: Re: Marvel Avengers Alliance II Android

> Reply from AceWell
>
> @dswd2015
thats great man!   
shakotay2 wrote:Ace, just out of curiosity: did you find out this by yourself?

(I've a deja vue that this kind of trick was used years ago with some other game/tools.)
i have deja vue every day it seems  , this process is just from my experience with those programs
and some bits of info here and there i managed to piece together and fortunately it worked.  

yeah i think this tutorial by dswd2015 where he used UABE to decompress a package for Unity Studio
gave me the idea to try this with compressed meshes.
viewtopic.php?p=124410#p124410 

i am extremely interested in learning how compressed mesh data is restored by Unity Studio
and i eventually want to make a Noesis python script that can open these types of model files.  
i think this has the code in it
https://github.com/RaduMC/UnityStudio/b ... es/Mesh.cs

i just need to make sense of it

Good idea bro, if I can help in anything please contact me. Thanks again for helping me.
## Post #17
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-11T09:43:43+00:00
- Post Title: Re: Marvel Avengers Alliance II Android

> Reply from AceWell
>
> UnityEX can open your sample   
http://www.zoneofgames.ru/forum/index.p ... opic=36240

after you open the package browse through the dropdown menu in the upper right
and select resources.assets, this contains many textures and .43 mesh files.
you can export out the *.mesh files and change the extension to *.43 and use 
finale00's Noesis python script to open those   
http://himeworks.com/redirect.php?type= ... Unity3D_43

edit
just in case you have trouble getting UnityEx i uploaded a copy of the one i used
Code: Select allhttp://www.mediafire.com/file/t65vjhgt50t5g63/UnityEX_1.5.4.7z
i think 1.5.7 is the newest version

Fantastic!!! I will test with some files that I could not extract yet. Thanks for sharing.
## Post #18
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-01-11T20:54:48+00:00
- Post Title: Re: Marvel Avengers Alliance II Android

Sorry if this may a stupid question,but how do you have access to the game files? isn't this game a closed?
## Post #19
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-12T03:39:20+00:00
- Post Title: Re: Marvel Avengers Alliance II Android

> Reply from Rutabaga
>
> Sorry if this may a stupid question,but how do you have access to the game files? isn't this game a closed?

Download Obb:

[http://www.brunoandroid.com/2015/12/mar ... -v100.html](http://www.brunoandroid.com/2015/12/marvel-avengers-alliance-2-apk-v100.html)
## Post #20
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-01-12T09:25:00+00:00
- Post Title: Re: Marvel Avengers Alliance II Android

Thanks a lot guys! i finally understand extraction process,and ripped some models 
[http://i.imgur.com/CHqEdCc.png](http://i.imgur.com/CHqEdCc.png)
[http://i.imgur.com/LQF3XAB.png](http://i.imgur.com/LQF3XAB.png)
But textures looks like a blurred,is there any chance to get hi-res texs?
Maybe anyone here have a files from iOS version?
