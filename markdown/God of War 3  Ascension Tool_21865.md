## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-11T16:39:48+00:00
- Post Title: God of War 3 / Ascension Tool

Tool for viewing/extracting skinned models from God of War: Ascension and God of War III Remastered. Supports geometry/skeleton/skinning and texture export.

(NEW) GOW 3 Animation Tool
viewtopic.php?p=169752#p169752

God of War: Ascension (PS3)

Tool overview and example exported model



Alecto textured



How to use

Load

WAD: Loads models (skinned) in WAD  files. RESOURCES.PSARC contains single character WADs, others have map files. You can also find some character models in map files. Especially the ones ending with "IGC".

Export

NEXG : Exports the model in custom binary format (.nexg), intended to be loaded by Noesis. Noesis script for this format : Nexg Script
Textures : Exports textures in DDS format. TS file needs to be in the same folder as WAD file. You can use GIMP for loading normal maps.
Note  : Models and textures will be exported into the folder Export.


Download : https://www.mediafire.com/file/9sdg2133 ... 2.rar/file

God of War III Remastered (PS4)

Same usage as the Ascension tool. No need for the TS  file for textures. Everything is inside the WAD.

Download : https://www.mediafire.com/file/jp5296ae ... r.rar/file

NOTE  : If the tool doesn't work make sure you have these installed on your computer
- VC++ Redistributable 2019
- VC++ Redistributable 2012

Credits
- Noesis - EDGE index decompression
## Post #2
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-03-12T14:51:40+00:00
- Post Title: God of War 3 / Ascension Tool

thank you for this tool, I try import kratos, the model is stretched, the teeth are out of the head and on the right,and the skeleton is not fitted to the model and is bigger. can you fix please?
tested many models, and only a few works
[](https://ibb.co/BKds6zb)
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-12T15:47:12+00:00
- Post Title: God of War 3 / Ascension Tool

> Reply from fil1969 ↑Thu Mar 12, 2020 10:51 pm at Thu Mar 12, 2020 10:51 pm
>
> 
I try import kratos, the model is stretched
Yes I am aware that some meshes are like that. I will see what I can do. Thanks for reporting.

Edit : 

It seems like it was an easy fix actually. Also fix some other chars with similar problem. I will do some more tests and do an update.



> Reply from fil1969 ↑Thu Mar 12, 2020 10:51 pm at Thu Mar 12, 2020 10:51 pm
>
> 
tested many models, and only a few works
Really? It seemed to work for good amount of main chars / monsters for me. Sometimes the proper model is under broken meshes. You can try exporting and checking.

Also some files are empty for some reason. Like there is athena wad file but no meshes.
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-12T23:33:45+00:00
- Post Title: God of War 3 / Ascension Tool

UPDATE

Looks like there was something wrong with vertex buffer strides. I fixed it now. Kratos is fixed and it should also support some more models. Link in first post updated.

There are still some models that need transformation to be loaded properly. They are not many, so don't think I will bother with them.
## Post #5
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-03-13T04:25:51+00:00
- Post Title: God of War 3 / Ascension Tool

Thank you very much! yes, I tested other models and were hidden under broken parts! Thank you very much!

[https://www.deviantart.com/oo-fil-oo/ar ... -833578944](https://www.deviantart.com/oo-fil-oo/art/GOW-ASCENSION-KRATOS-833578944)
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-03-13T05:28:08+00:00
- Post Title: God of War 3 / Ascension Tool

Nice to see finally a very first ever tool for one of the PS3 GOW games, it was always thought to be impossible.
And I had a chance to test it.
Unfortunately more than 90% of characters are just a mess, geometry scrambled, or it crashes during texture extraction, and it will be a pity if the entire game is not supported, what about static geometry/map geometry, will there be a chance for other GOW games support?
I do hope you consider a better support at least this game fully if nothing else
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-13T05:48:21+00:00
- Post Title: God of War 3 / Ascension Tool

> Reply from mono24 ↑Fri Mar 13, 2020 1:28 pm at Fri Mar 13, 2020 1:28 pm
>
> 
Unfortunately more than 90% of characters are just a mess, geometry scrambled,
Can you try the new update? It should have fixed some issues.

It is weird that you are getting very few models loaded though. Are you using wads in RESOURCES psarc? It should definitely be loading more than 10% . Especially after the update.

> Reply from mono24 ↑Fri Mar 13, 2020 1:28 pm at Fri Mar 13, 2020 1:28 pm
>
> 
supported, what about static geometry/map geometry, will there be a chance for other GOW games support?
It might already be working for GoW 3, because I think that the formats were almost identical. Or at least it might work with a slight change. I haven't tested it though. Need to get the files first.

I will take a look at maps, but I don't think they will be easy to do. Nothing seems easy with this game  I will consider but can't promise anything.

Edit : 

Seems like there are just few changes for GoW 3. I might release it as a separate tool though, to not overcomplicate the code.

Here is GoW 3 Athena



Edit 2 :

Actually started to get some map meshes loaded from Ascension. It also looks like some chars are hidden inside map files too.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-19T09:50:52+00:00
- Post Title: God of War 3 / Ascension Tool

UPDATE

- GoW 3 Remastered tool (PS4)
- Support for map wads for getting map specific npcs
- Fix for some misplaced mesh parts
- Separate skeleton export (needed this because of map characters)
- Improved texture export

New info and download links in the first post.

NOTE :  No static objects support yet. Map support is only for getting skinned meshes in maps. I will release static mesh support later.

GoW 3 Tool
## Post #9
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2020-03-24T01:08:26+00:00
- Post Title: God of War 3 / Ascension Tool

GOW3 ps3 version can use this tool?
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-24T09:19:29+00:00
- Post Title: God of War 3 / Ascension Tool

> Reply from phay008 ↑Tue Mar 24, 2020 9:08 am at Tue Mar 24, 2020 9:08 am
>
> 
GOW3 ps3 version can use this tool?

No, it is for the ps4 version. I was making one for ps3, but switched to ps4 later.
## Post #11
- Username: redman4356
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 27, 2019 4:10 am
- Post datetime: 2020-03-28T07:08:36+00:00
- Post Title: God of War 3 / Ascension Tool

ah why yes thank you,
am gonna check it out when I download gow ascension and do the whole thing
## Post #12
- Username: donovan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 17, 2016 4:58 pm
- Post datetime: 2020-04-01T00:54:17+00:00
- Post Title: God of War 3 / Ascension Tool

I have successfully extract GOW III remaster models (wad files) but for Gow Ascension, there is only PSARC files and gowa viewer seems to be unable to read this format.

What is the process please ?
## Post #13
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-04-01T01:09:46+00:00
- Post Title: God of War 3 / Ascension Tool

> Reply from donovan ↑Wed Apr 01, 2020 8:54 am at Wed Apr 01, 2020 8:54 am
>
> What is the process please ?
You drag and drop them in Noesis preview window and it will tell you where it extracts, select other location or select ok, and it will extract them for you
## Post #14
- Username: donovan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 17, 2016 4:58 pm
- Post datetime: 2020-04-01T08:54:48+00:00
- Post Title: God of War 3 / Ascension Tool

Thanks a lot for your answer, but maybe something is missing because when I put psarc files in nosesis window, nothing happens.
## Post #15
- Username: redman4356
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 27, 2019 4:10 am
- Post datetime: 2020-04-01T12:31:22+00:00
- Post Title: God of War 3 / Ascension Tool

thank you akderebur for the tools, they are pretty helpful, just one more thing
Gow ascension for some reason has some of gow 3's models, some load fine and some just load like (currently this is R_PANDORA00)
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-01T13:13:28+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from redman4356 ↑Wed Apr 01, 2020 8:31 pm at Wed Apr 01, 2020 8:31 pm
>
> 
Gow ascension for some reason has some of gow 3's models, some load fine and some just load like (currently this is R_PANDORA00)
Yes, some are like that. No fix currently. Only minor stuff so I didn't bother too much. You can get Pandora from GoW 3.
## Post #17
- Username: donovan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 17, 2016 4:58 pm
- Post datetime: 2020-04-01T16:36:51+00:00
- Post Title: Re: God of War 3 / Ascension Tool

I've finally found the problem by myself..
You didn't mention that the psarc files must be extract with "psarc extractor" before using gowaviewer for wad files..

Thanks anyway.
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-01T17:30:27+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from donovan ↑Thu Apr 02, 2020 12:36 am at Thu Apr 02, 2020 12:36 am
>
> 
You didn't mention that the psarc files must be extract with "psarc extractor" before using gowaviewer for wad files..
Sorry, but my tool is related to GoW, so I won't explain how to unpack a general ps3 archive format. A quick google search should give bunch of info and multiple extractors.

Also I didn't answer your question because mono already did and I thought you got it working. Just noticed your second post. I don't know why you couldn't extract them with Noesis. It should work, but anyway you extracted them in the end.
## Post #19
- Username: redman4356
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 27, 2019 4:10 am
- Post datetime: 2020-04-01T23:39:48+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Ah well I guess I’ll have to wait for next month to download gow 3, already destroyed my internet today by downloading many things
## Post #20
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2020-04-02T09:45:30+00:00
- Post Title: Re: God of War 3 / Ascension Tool

nice app you got there , sad you don't asked for help i got noesis working scipts for both gow3 and ascencion since 2017 ^^
pm me akderebur
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-02T10:13:57+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from shadowmoy ↑Thu Apr 02, 2020 5:45 pm at Thu Apr 02, 2020 5:45 pm
>
> 
nice app you got there , sad you don't asked for help i got noesis working scipts for both gow3 and ascencion since 2017 ^^
pm me akderebur

How could I know that you had a script for it?  I found one on facepunch, but it was lacking a lot. No proper use of bounding boxes, and mostly pattern search to parse the file. Other than that I haven't seen any work done for this game. Maybe I haven't searched enough, I don't know. Also replied your pm.
## Post #22
- Username: vigneshvampire
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 29, 2019 8:50 pm
- Post datetime: 2020-04-03T09:31:22+00:00
- Post Title: Re: God of War 3 / Ascension Tool

[](https://ibb.co/xLg3wwf)
[](https://ibb.co/XpGnVKb)

ok Fine it's working but to open it blender ..?? i am using your  Nexg Script.py but it not working ...please explain how to open 3d model and textures in blender
## Post #23
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-03T09:37:14+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from vigneshvampire ↑Fri Apr 03, 2020 5:31 pm at Fri Apr 03, 2020 5:31 pm
>
> 
i am using your  Nexg Script.py but it not working ...please explain how to open 3d model and textures in blender

I have explicitly stated that it is a script for Noesis, not Blender. Search for Noesis on xentax or google to see how you can use it. Then use that Noesis plugin to load the nexg models.
## Post #24
- Username: vigneshvampire
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 29, 2019 8:50 pm
- Post datetime: 2020-04-03T15:40:00+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Fri Apr 03, 2020 5:37 pm at Fri Apr 03, 2020 5:37 pm
>
> 
vigneshvampire wrote: ↑Fri Apr 03, 2020 5:31 pm
i am using your  Nexg Script.py but it not working ...please explain how to open 3d model and textures in blender


I have explicitly stated that it is a script for Noesis, not Blender. Search for Noesis on xentax or google to see how you can use it. Then use that Noesis plugin to load the nexg models.

Ok Fine finally i got that Noesis Script  and putting your Nexg Script.py also but i cant merge 3d model and texture can you explain how i to do that..

[](https://ibb.co/wg1X5nD)

[](https://ibb.co/frfwFWq)
## Post #25
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-03T15:53:05+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from vigneshvampire ↑Fri Apr 03, 2020 11:40 pm at Fri Apr 03, 2020 11:40 pm
>
> 
i cant merge 3d model and texture can you explain how i to do that..

Using Noesis, export the model to a desired format (FBX, OBJ etc.). Load it in your favorite 3d software and apply textures. There is no automatic texturing.
## Post #26
- Username: td973
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 18, 2019 3:26 am
- Post datetime: 2020-04-12T07:08:51+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Thanks for this tool, would this work for GoW4 on ps4?
-edit- I just tried but sadly it did not work. here is a sample WAD if interested
[https://mega.nz/file/OqwknYZI#nQ_GWpqdR ... prUUE1hP1M](https://mega.nz/file/OqwknYZI#nQ_GWpqdRcqAH_xzO8S58dYRuU_HMGJbsprUUE1hP1M)
## Post #27
- Username: irmak88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 26, 2019 1:05 am
- Post datetime: 2020-05-21T20:48:34+00:00
- Post Title: Re: God of War 3 / Ascension Tool

I'm having a problem with the Ascension tool. When I try to upload a model, nothing happens and it stays on grey screen. I have installed both of the redist components on my computer but still I cant figure it out.
## Post #28
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-22T07:52:28+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from irmak88 ↑Fri May 22, 2020 4:48 am at Fri May 22, 2020 4:48 am
>
> 
When I try to upload a model, nothing happens
What is the name of the file that you are trying to load?
## Post #29
- Username: irmak88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 26, 2019 1:05 am
- Post datetime: 2020-05-22T13:01:21+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Fri May 22, 2020 3:52 pm at Fri May 22, 2020 3:52 pm
>
> 
What is the name of the file that you are trying to load?
I tried a couple of different files from different psarc files, every one of them has the same issue. Here's the list of files that I tried.
## Post #30
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-22T13:20:21+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Weird. Maybe one of the dlls are blocked. You might need to do right-click -> properties and select "unblock". Other than that I can't think of a reason.

Maybe another redistributable is required, but not very likely. I will double check to make sure, when I have the time.
## Post #31
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2020-05-22T14:11:55+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Can this tool work with the God of War 4 ？If not, can you tell me how to extract the fx textures ?
## Post #32
- Username: irmak88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 26, 2019 1:05 am
- Post datetime: 2020-05-22T14:24:12+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Fri May 22, 2020 9:20 pm at Fri May 22, 2020 9:20 pm
>
> 
Weird. Maybe one of the dlls are blocked. You might need to do right-click -> properties and select "unblock". Other than that I can't think of a reason.
Nope, it didn't work. Also, I checked my redistributables again.
## Post #33
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-22T14:50:21+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from cjdung ↑Fri May 22, 2020 10:11 pm at Fri May 22, 2020 10:11 pm
>
> 
Can this tool work with the God of War 4 ？If not, can you tell me how to extract the fx textures ?
Nope, only gow 3 and ascension.
## Post #34
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-11T14:42:42+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Working on animation and material support for GoW 3. I will release it after doing some more tests. Also planning to release map tools when I have the time to finalize them.
## Post #35
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2020-06-16T06:39:17+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Thu Jun 11, 2020 10:42 pm at Thu Jun 11, 2020 10:42 pm
>
> 
Working on animation and material support for GoW 3. I will release it after doing some more tests. Also planning to release map tools when I have the time to finalize them.

That's a good new! By the way,can you work with the tool for lost ark client? The model inside the package is really god damn good.But it is a encrypted ue3 game which no one can perfectly along the forum.It will be great if you can work with that.
Here is the link for all client:[https://drive.google.com/drive/folders/ ... Eo2MjdmUTg](https://drive.google.com/drive/folders/0B7yj3HHOQvx4YmdCZEo2MjdmUTg)
The offcial web(Ru):[https://la.mail.ru/](https://la.mail.ru/)
## Post #36
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-16T07:58:09+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from cjdung ↑Tue Jun 16, 2020 2:39 pm at Tue Jun 16, 2020 2:39 pm
>
> 
can you work with the tool for lost ark client?
No plans for lost ark. Also better use pm for this kind of questions. It isn't related to GoW
## Post #37
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2020-07-24T04:18:00+00:00
- Post Title: Re: God of War 3 / Ascension Tool

WOW! This is truly amazing! Over three years of searching and finally something works! Akderebur, I cannot thank you enough; I have looked far and wide for tools to export God of War assets. The closest I ever got was the work that HaCKer7UTD and some other people in XeNTaX did back in the day but like you said in an earlier post, it was incomplete.
I really want to thank you for putting these tools together! They have worked fast and flawlessly like a charm! Everything loads correctly in your viewer, exports and imports good in Noesis, and functions perfectly in Maya with working textures, rig, and skin.

Now, I am curious about the animation support that you were working on. *That* has been something I have been very invested in for a long time! I study the animation of God of War because I am a character animator and I love the way Santa Monica handles the animations in the God of War series. The force and the weight and the motion of the actions that they are able to convey is candy for the eyes and saturated in so much raw energy. I love it to bits.
But it was always been a pain to study because of the locked camera, quick time events and such, plus the only assets that were ripped were only the models and textures. I am really hopeful that you can get the animation support for your tools to work since this is the only chance at getting to observe, study, and admire the animations at whatever angle.
I would absolutely LOVE if you were to get that to work as they would be a huge asset and game-changer! Hope to see more progress when you get the chance.

All the best and good luck!
## Post #38
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-07-24T13:12:24+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from voyennyy ↑Fri Jul 24, 2020 12:18 pm at Fri Jul 24, 2020 12:18 pm
>
> 
I would absolutely LOVE if you were to get that to work
I got good amount of animations working actually, minus the cloth physics. Even some longer cutscene sequences. I didn't have the time to release an updated tool though. I will release it some time, eventually, hopefully...
## Post #39
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2020-07-24T17:47:31+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Fri Jul 24, 2020 9:12 pm at Fri Jul 24, 2020 9:12 pm
>
> 
I got good amount of animations working actually, minus the cloth physics. Even some longer cutscene sequences. I didn't have the time to release an updated tool though. I will release it some time, eventually, hopefully... 
[/quote]

Hey man, that’s all good! Honestly you having the animations work and function properly in the first place is very promising. I am bursting at the seams currently with the tools as they are and testing them on numerous WADs.
I will mention that some of the models have broken geometry when loaded in your viewer similar to what other people were experiencing, like goat90 and both harpy models. Another issue was that it seems some textures might be either missing or in a different container, like the chimera was missing some fur transparency textures in its WAD/TS container. But that’s relatively minor; I’m still very grateful for the tools as you’ve made them.
So yeah bud, do what you can for animation stuff, I understand it is the most difficult part of model extraction. Nevertheless, I eagerly await!

All the best!
## Post #40
- Username: vigneshvampire
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 29, 2019 8:50 pm
- Post datetime: 2020-08-01T07:56:38+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Thu Jun 11, 2020 10:42 pm at Thu Jun 11, 2020 10:42 pm
>
> 
Working on animation and material support for GoW 3. I will release it after doing some more tests. Also planning to release map tools when I have the time to finalize them.
Excellent work ... when you release this tool ..?
## Post #41
- Username: netbeans69
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 16, 2020 9:56 am
- Post datetime: 2020-08-16T21:21:30+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Pandora's model seems to be working just fine
[1.jpg](https://xentaxbackup.github.io/file/18621_1.jpg)
## Post #42
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2020-08-23T01:52:27+00:00
- Post Title: Re: God of War 3 / Ascension Tool

I was doing an experiment to see how well the models and skeleton worked in Arnold and it came out quite nice.
Thanks again for the fantastic tools akderebur! Looking forward to future developments!
[centaurPose_betterlighting_04.jpg](https://xentaxbackup.github.io/file/18637_centaurPose_betterlighting_04.jpg)
## Post #43
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-23T09:08:34+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from voyennyy ↑Sun Aug 23, 2020 9:52 am at Sun Aug 23, 2020 9:52 am
>
> 
Looking forward to future developments!
Good to hear that you find it useful. I had some work that I needed to prioritize, so couldn't find the time to develop the GoW tools. Hopefully it will be over soon and I will get back to working on this.
## Post #44
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-08-25T21:35:18+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Fri May 22, 2020 10:50 pm at Fri May 22, 2020 10:50 pm
>
> 
cjdung wrote: ↑Fri May 22, 2020 10:11 pm
Can this tool work with the God of War 4 ？If not, can you tell me how to extract the fx textures ?

Nope, only gow 3 and ascension.

If a tool to extract GOW 4 character models and textures isn't an option, is there any possibility I could commission someone to port a specific model with its textures from the game. I've seen some people port models using Hex2Obj so I was wondering if this would be a possibility?
## Post #45
- Username: dezastrunatural
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 16, 2020 1:55 pm
- Post datetime: 2020-08-28T11:19:47+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Can someone help me with baldur and atreus please from the bottom of my heart I kept trying but I still can't extract Kratos I couldn't extract it please please if someone can help me
## Post #46
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-08-28T14:33:54+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from dezastrunatural ↑Fri Aug 28, 2020 7:19 pm at Fri Aug 28, 2020 7:19 pm
>
> 
Can someone help me with baldur and atreus...
Um, as title suggests, ONLY GOW3/Ascension is supported.
## Post #47
- Username: EgasAmuuFeht
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 22, 2015 5:29 am
- Post datetime: 2020-08-31T01:38:26+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Hmm...
## Post #48
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-31T20:32:10+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from EgasAmuuFeht ↑Mon Aug 31, 2020 9:38 am at Mon Aug 31, 2020 9:38 am
>
> 
I suppose I've somehow completely forgotten the keyboard hotkeys for moving to the next model while in the Viewer window.

The gow tools don't have any hotkeys. You might be mistaking it for some of my other tools, since they all look the same  I think only my TLOU and Bleach tools have arrow hotkeys and they are for animations.
## Post #49
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2020-10-20T03:49:38+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Hey man! Was wondering if there's any update to the tool in regards to getting animations to function?
I hope I'm not coming off as annoying, curiosity gets the best of me.

Thanks in advance!
## Post #50
- Username: blahla123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 09, 2020 7:05 am
- Post datetime: 2020-11-08T23:17:25+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Hey guys, noob here, I am looking for the models/textures from the women in the Bliss scene and the female slave at the Delphi Oracle from Ascension and I can't find them. Using the tool I can only find a few WADs that load. Mostly in RESOURCES.PSARC. Most of the other psarc wads don't seem to show anything at all. Can someone help me find and extract these particular models and correct any errors that might be in them? Thanks.
## Post #51
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2020-11-27T03:08:46+00:00
- Post Title: Re: God of War 3 / Ascension Tool

i want extyract ascension levels.
Is possible?
If yes, what  .psarc file I have to see?
Thanks!
## Post #52
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-11-27T10:21:40+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from grotesque ↑Fri Nov 27, 2020 11:08 am at Fri Nov 27, 2020 11:08 am
>
> 
i want extyract ascension levels.
Is possible?
Unfortunately not at the moment, as I seem to have a tendency for abandoning my projects at their peak 

I have 2 games I am working on currently, planning to get back to GoW after them. I will release the map and animation support, but for GoW 3 first. For Ascension I can possibly release a map tool and don't bother with animations.
## Post #53
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2020-12-05T01:19:52+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Fri Nov 27, 2020 6:21 pm at Fri Nov 27, 2020 6:21 pm
>
> 
grotesque wrote: ↑Fri Nov 27, 2020 11:08 am
i want extyract ascension levels.
Is possible?

Unfortunately not at the moment, as I seem to have a tendency for abandoning my projects at their peak 

I have 2 games I am working on currently, planning to get back to GoW after them. I will release the map and animation support, but for GoW 3 first. For Ascension I can possibly release a map tool and don't bother with animations.

Map without animation is ok   
For GOW 3 you mean the remastered version or original ps3?
## Post #54
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2020-12-05T01:22:25+00:00
- Post Title: Re: God of War 3 / Ascension Tool

I'm looking very forward to whenever you have time to release animation support for GoW 3 Remastered! That'll be awesome!
## Post #55
- Username: vigneshvampire
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 29, 2019 8:50 pm
- Post datetime: 2020-12-18T09:35:07+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Thu Jun 11, 2020 10:42 pm at Thu Jun 11, 2020 10:42 pm
>
> 
Working on animation and material support for GoW 3. I will release it after doing some more tests. Also planning to release map tools when I have the time to finalize them.
Hi i am waiting for this tool more than 6months any update for this tool..??
## Post #56
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-18T10:18:02+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from vigneshvampire ↑Fri Dec 18, 2020 5:35 pm at Fri Dec 18, 2020 5:35 pm
>
> 
Hi i am waiting for this tool more than 6months any update for this tool..??
Wow has it been that long. I will release a tool this weekend then. I am not sure if it will work with everything (kinda forgot my progress actually), but still better than never releasing  I can fix it later if there are problems.
## Post #57
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-20T13:40:22+00:00
- Post Title: Re: God of War 3 / Ascension Tool

GOW 3 Remaster Animation/Material Support

I am releasing this as a separate tool because I haven't tested it much. Might break for some models.

Download: [https://www.mediafire.com/file/owavat4v ... 1.rar/file](https://www.mediafire.com/file/owavat4v56a1hnz/GOW3R_Anim_U1.rar/file)

Usage
- Load the WAD file
- Cycle through animations with the arrow keys (left/right)
- Export to NEW nexg format
- There is also an option to export all animations
- Use the included script to load exported files in Noesis. Remove any other nexg scripts if you had before.

Note: Textures need to be in the same folder as nexg to be loaded. So make sure to copy them after export, if you want textures in Noesis preview.

Example Hades animation loaded in Noesis
## Post #58
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2020-12-20T15:11:02+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Hey man! Just wanted to confirm that the tool is working perfectly! Like you mentioned, a few models are a bit buggy like Medusa10's model is missing some pieces and Skorpius' anims sadly doesn't load at all! But it does work on other models. Thank you so much for uploading the tool! A thousand praises to you!
## Post #59
- Username: Jaimito
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 22, 2020 7:01 am
- Post datetime: 2020-12-21T23:25:02+00:00
- Post Title: Re: God of War 3 / Ascension Tool

hello friends, i'm making a god of war 3 fangame for mobile devices. It would be helpful if you could pass me the maps and animations for project. I tried to do the animations manually, because I couldn't figure out how to extract them from the original game; until I found this forum. But also this method only works for ps4 game
## Post #60
- Username: Hitmanhimself
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Aug 08, 2020 12:43 am
- Post datetime: 2020-12-22T02:41:06+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Sun Dec 20, 2020 9:40 pm at Sun Dec 20, 2020 9:40 pm
>
> 
GOW 3 Remaster Animation/Material Support

What about the map/level static meshes man? when we will see that?
## Post #61
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-22T04:13:47+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from Hitmanhimself ↑Tue Dec 22, 2020 10:41 am at Tue Dec 22, 2020 10:41 am
>
> 
What about the map/level static meshes man?

It shouldn't be too hard at this point. I have an old test build that works with static meshes. Just need to add materials to that.

I am planning to release separate map tools for both games. Makes the code management easier for me. Probably some time this weekend or maybe sooner if I have time.
## Post #62
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-12-28T02:43:49+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Thanks
## Post #63
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-04T21:04:39+00:00
- Post Title: Re: God of War 3 / Ascension Tool

This is a game research forum, enough is enough about asking actual game assets, come on guys you where raised better than that.
## Post #64
- Username: Name
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 31, 2019 9:16 pm
- Post datetime: 2021-01-06T19:33:30+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from mono24 ↑Tue Jan 05, 2021 5:04 am at Tue Jan 05, 2021 5:04 am
>
> 
This is a game research forum, enough is enough about asking actual game assets, come on guys you where raised better than that.

why the hell did you delete the links? You could write this comment, but why the hell was it necessary to delete posts?
## Post #65
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-06T20:21:57+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from Name ↑Thu Jan 07, 2021 3:33 am at Thu Jan 07, 2021 3:33 am
>
> why the hell did you delete the links? You could write this comment, but why the hell was it necessary to delete posts?
Um, take a deep breath, i think you some how got lost with your first comment being here for this long, I'm assuming you have no idea how things are around here, first of all i am NOT a moderator, in case its not clear for you. Having links with game assets in that manner is illegal in here and they get deleted by the administration/moderators at their decision NOT mine, unless the actual author of the post did then good for him/her, keep that transaction for PM use.
## Post #66
- Username: Jaimito
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 22, 2020 7:01 am
- Post datetime: 2021-01-08T13:49:20+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from mono24 ↑Thu Jan 07, 2021 4:21 am at Thu Jan 07, 2021 4:21 am
>
> 
Name wrote: ↑Thu Jan 07, 2021 3:33 amwhy the hell did you delete the links? You could write this comment, but why the hell was it necessary to delete posts?
Um, take a deep breath, i think you some how got lost with your first comment being here for this long, I'm assuming you have no idea how things are around here, first of all i am NOT a moderator, in case its not clear for you. Having links with game assets in that manner is illegal in here and they get deleted by the administration/moderators at their decision NOT mine, unless the actual author of the post did then good for him/her, keep that transaction for PM use.

so bad
## Post #67
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2021-03-05T21:29:42+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Tue Dec 22, 2020 12:13 pm at Tue Dec 22, 2020 12:13 pm
>
> 


It shouldn't be too hard at this point. I have an old test build that works with static meshes. Just need to add materials to that.

I am planning to release separate map tools for both games. Makes the code management easier for me. Probably some time this weekend or maybe sooner if I have time.
So does the tool allow to rip static meshes now or only rigged ?
For example I would like to find the Blades of Exile (yellow glowing blades given by Athena) but I don't know if they are in the files that this tool could process.
## Post #68
- Username: AnisZeus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 02, 2019 5:46 am
- Post datetime: 2021-03-21T17:02:46+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Sun Dec 20, 2020 9:40 pm at Sun Dec 20, 2020 9:40 pm
>
> 
GOW 3 Remaster Animation/Material Support

I am releasing this as a separate tool because I haven't tested it much. Might break for some models.

Download: https://www.mediafire.com/file/u3e5k7i5 ... m.rar/file

Usage
- Load the WAD file
- Cycle through animations with the arrow keys (left/right)
- Export to NEW nexg format
- There is also an option to export all animations
- Use the included script to load exported files in Noesis. Remove any other nexg scripts if you had before.

Note: Textures need to be in the same folder as nexg to be loaded. So make sure to copy them after export, if you want textures in Noesis preview.

Example Hades animation loaded in Noesis
Umm Hades,Poseidon and Zeus animations are kinda broken ,Can you fix them ?
## Post #69
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-03-28T17:02:13+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from AnisZeus ↑Mon Mar 22, 2021 1:02 am at Mon Mar 22, 2021 1:02 am
>
> 
Umm Hades,Poseidon and Zeus animations are kinda broken ,Can you fix them ?

It seems to be due to the rotation mostly. I will release an update for this after some testing. I don't know if it will solve all the issues, but some animations should work better at least. You can see the comparison below.

New update vs current version leg movement
## Post #70
- Username: AnisZeus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 02, 2019 5:46 am
- Post datetime: 2021-03-30T12:23:32+00:00
- Post Title: Re: God of War 3 / Ascension Tool

WOOW thank you very much
## Post #71
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-05T13:31:14+00:00
- Post Title: Re: God of War 3 / Ascension Tool

I have released an update for the GoW 3 animation tool. You can get it here: [viewtopic.php?p=169752#p169752](https://forum.xentax.com/viewtopic.php?p=169752#p169752)

Issues related to wrong rotations should be mostly fixed now. I have also tried to update the camera to follow the model better, but some animations still make the character disappear in the preview. Especially couple of Hermes animations. Just export and preview in Noesis.
## Post #72
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2021-06-23T21:01:01+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Hey! Could you fix Medusa's animations and Skorpius' animations and textures? For Medusa, most of her animations have her arms waving erratically and tail broken. As for Skorpius, her textures are broken and none of her animations load into your tool, except for a broken pose and one moving leg.



Medusa10_BrokenAnim.gif (254.79 KiB) Viewed 127 times
## Post #73
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-06-23T21:48:59+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from voyennyy ↑Thu Jun 24, 2021 5:01 am at Thu Jun 24, 2021 5:01 am
>
> 
Could fix Medusa's animations and Skorpius' animations and textures?

It isn't likely that I will return to this format any time soon. If I ever return to it for Ascension animations or something else I will see what I can do about broken animations/textures.
## Post #74
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2021-06-23T23:09:33+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> It isn't likely that I will return to this format any time soon. If I ever return to it for Ascension animations or something else I will see what I can do about broken animations/textures.

All good, Ascension animations would be awesome! Looking forward to it!
## Post #75
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2021-07-12T22:45:10+00:00
- Post Title: Re: God of War 3 / Ascension Tool

when I try to import nothing happens and I've already tested it, nothing is missing -VC ++
## Post #76
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-13T00:21:33+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from LeoFeroz ↑Tue Jul 13, 2021 6:45 am at Tue Jul 13, 2021 6:45 am
>
> 
when I try to import nothing happens and I've already tested it, nothing is missing -VC ++

I had one other user had that problem. In the end they opened the program inside the rar file without extracting and it worked. You can try the same. Also make sure windows is not blocking the file or something.
## Post #77
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2021-07-15T05:33:08+00:00
- Post Title: Re: God of War 3 / Ascension Tool

you intend to create an extractable version of the game maps ?
## Post #78
- Username: blahla123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 09, 2020 7:05 am
- Post datetime: 2021-08-01T07:09:14+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Hello I'm extracting some character model textures and I'm having trouble identifying what is what. In the image below I've labeled what I think are Diffuse, normal, and specular textures. But its really hard to tell whether something is indeed a specular texture or for glow or shininess or whatever. And then there are some textures I have no idea what type they are supposed to be. I was hoping someone could take a look and identify some of the question marks or if I got my classification wrong. 

[https://ibb.co/rQqDWB3](https://ibb.co/rQqDWB3)

Also I am looking for the model for the lady character in this picture below for GOW ascension during the confrontation with castor at delphi. I've extracted many files to no avail. I've found a similar model in temp.psarc in the tem759igc.wad but its doesn't appear to be the same and the proper textures seem to be missing. Does someone have an idea where I can find it? Thanks. 



missingmodelstrip.jpg (193.22 KiB) Viewed 342 times
## Post #79
- Username: Kabalstein03
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 9:36 am
- Post datetime: 2022-04-18T02:27:31+00:00
- Post Title: Re: God of War 3 / Ascension Tool

The God of War Ascension tools are gone, the link got a DMCA strike, does anyone have an alternate link?
## Post #80
- Username: dark9090
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 09, 2021 4:55 pm
- Post datetime: 2022-04-25T13:13:29+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Excuse me, could you reupload the tool for ascension, I'm reacting to kratos in zbrush   but I would like to be able to extract them to make other pj, thanks
## Post #81
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2022-05-17T13:36:22+00:00
- Post Title: Re: God of War 3 / Ascension Tool

So, I extracted god of war ascension RESOURCES.PSARC with PSARCTool.exe and I tried the tool to load WAD and animations.

However, it seems that it does not want to load the model at all. Still Blank. Am I doing something wrong?
[Untitled.png](https://xentaxbackup.github.io/file/22236_Untitled.png)
## Post #82
- Username: AnisZeus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 02, 2019 5:46 am
- Post datetime: 2022-06-24T11:39:22+00:00
- Post Title: Re: God of War 3 / Ascension Tool

I don't know if you gave up on this , but some of Zeus animations are messed up like this one
[6FDQDX_988bc8c5d824e056a78937b40389e819_00-00-00_00-00-02_2.gif](https://xentaxbackup.github.io/file/22419_6FDQDX_988bc8c5d824e056a78937b40389e819_00-00-00_00-00-02_2.gif)
## Post #83
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2022-08-18T18:25:45+00:00
- Post Title: Re: God of War 3 / Ascension Tool

Hopefully this thread isn't dead, but is it possible to find any documentation on the models format in God of War 3 PS4? Any help would be appreciated.
## Post #84
- Username: mjoern
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 03, 2022 2:30 pm
- Post datetime: 2022-12-03T06:57:48+00:00
- Post Title: Re: God of War 3 / Ascension Tool

> Reply from akderebur ↑Thu Mar 12, 2020 12:39 am at Thu Mar 12, 2020 12:39 am
>
> 
Tool for viewing/extracting skinned models from God of War: Ascension and God of War III Remastered. Supports geometry/skeleton/skinning and texture export.

(NEW) GOW 3 Animation Tool
viewtopic.php?p=169752#p169752

God of War: Ascension (PS3)

Tool overview and example exported model



Alecto textured



How to use

Load

WAD: Loads models (skinned) in WAD  files. RESOURCES.PSARC contains single character WADs, others have map files. You can also find some character models in map files. Especially the ones ending with "IGC".

Export

NEXG : Exports the model in custom binary format (.nexg), intended to be loaded by Noesis. Noesis script for this format : Nexg Script
Textures : Exports textures in DDS format. TS file needs to be in the same folder as WAD file. You can use GIMP for loading normal maps.
Note  : Models and textures will be exported into the folder Export.


Download : https://www.mediafire.com/file/9sdg2133 ... 2.rar/file

God of War III Remastered (PS4)

Same usage as the Ascension tool. No need for the TS  file for textures. Everything is inside the WAD.

Download : https://www.mediafire.com/file/jp5296ae ... r.rar/file

NOTE  : If the tool doesn't work make sure you have these installed on your computer
- VC++ Redistributable 2019
- VC++ Redistributable 2012

Credits
- Noesis - EDGE index decompression

hi, I dowloaded the script for .genx compatibility with noesis and put it in plugin/python, I opened noesis, reloaded the scripts but still none of the files i extracted from gow3rviewer show up..
any idea?

UPDATE :

the files shows up now but I get this error message



anyone knows what's up?
