## Post #1
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-20T20:34:23+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

extractor is here
[viewtopic.php?f=10&t=16027](http://forum.xentax.com/viewtopic.php?f=10&t=16027)
Here is a noesis script to open the model files with bones and weights.
-to do
load the mesh shell so its like the original toon shading.


[fmt_tlru_bum.zip](https://xentaxbackup.github.io/file/12665_fmt_tlru_bum.zip)
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-20T23:40:18+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

It was hard but good to learn. thanks, chrrox!
I assumed this works for android, does it work for ios?
[co01_ssr.jpg](https://xentaxbackup.github.io/file/12666_co01_ssr.jpg)
## Post #3
- Username: kayaha
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 09, 2017 11:15 pm
- Post datetime: 2017-03-22T06:36:56+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

Hello chrrox, I respect your work.  
I opened the .bum file with noesis, but the body and texture are not displayed with only the head mesh and bone
Does noesis need to plugin something other than .bum noesis script?
Would you please tell me a tutorial if you like it?
[noesis.png](https://xentaxbackup.github.io/file/12670_noesis.png)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-22T09:01:33+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

make sure you have the newest noesis.
Also make sure you download your newest gpu drivers.
## Post #5
- Username: Nathanzica
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 15, 2017 8:16 am
- Post datetime: 2017-07-17T18:10:36+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

I do not find the files in /data/data/jp.furyu.tologra ;-;
## Post #6
- Username: Nathanzica
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 15, 2017 8:16 am
- Post datetime: 2017-07-17T20:17:30+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

I got thank you very much: D


I'm very dumb

Then I realized what I had to do.
## Post #7
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-12-18T15:07:58+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

Excuse me chrrox, this is .bum file from Senran Kagura: New Link. Can you check it? Tks you.
[pl19_model.7z](https://xentaxbackup.github.io/file/13704_pl19_model.7z)
## Post #8
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2018-04-10T16:11:29+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

thk for the work.but the shell will run in error with the other .bum  files just like "ch01_cut00.bum",is it rugular?



TIM截图20180411000747.png (25.92 KiB) Viewed 1279 times


and anyone can tell me how to combination the body model with the head? tks a lot
## Post #9
- Username: xele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 15, 2018 2:19 am
- Post datetime: 2018-04-16T17:43:30+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

> Reply from azbycx
>
> thk for the work.but the shell will run in error with the other .bum  files just like "ch01_cut00.bum",is it rugular?
and anyone can tell me how to combination the body model with the head? tks a lot

Started to look at the file of this game some times ago. Only the chXX.bum file have a mesh data, and contain only the head. The others are animation file and so will fail to load with the current script (I'm trying to understand the format to load them too). If you're looking for the body, they are in the co/ folder (co like costume I suppose). Don't know if you can load both on Noesis at same time, I'm using it on linux with wine, and it's not totally working.
## Post #10
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2018-04-24T16:55:31+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

> Reply from xele
>
> azbycx wrote:thk for the work.but the shell will run in error with the other .bum  files just like "ch01_cut00.bum",is it rugular?
and anyone can tell me how to combination the body model with the head? tks a lot

Started to look at the file of this game some times ago. Only the chXX.bum file have a mesh data, and contain only the head. The others are animation file and so will fail to load with the current script (I'm trying to understand the format to load them too). If you're looking for the body, they are in the co/ folder (co like costume I suppose). Don't know if you can load both on Noesis at same time, I'm using it on linux with wine, and it's not totally working.

in Windows I can load the body like the "co/co05_ssr.bum",but the model is only body without the head.so I'm wonder how can I combination these?
## Post #11
- Username: xele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 15, 2018 2:19 am
- Post datetime: 2018-04-25T16:42:25+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

Well I don't know with this tool. I started to make a webGL app to load an display those files. I can decode a lot more than the python script now. I can load those mesh, but also Senran Kagura meshes (even if I4m still missing some data purpose). I have also a start for animation file read and play. I'll make this online tool public later when it's more stable & usable. I can also give you information of the format if someone want to upgrade the Noesis script.

By the way, if someone know were are the shaders used by the game. I suppose they are somewhere in a binary, but didn't found them yet.

Edit : Meshes / Animations & Shaders are now working for gravure chance. I will do some clean and easy interface and make it avaiable by the week probably. I still need to try to extract the shaders for Senran Kagura since they use some others.

Ex :
## Post #12
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2018-04-28T19:35:07+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

> Reply from xele
>
> Well I don't know with this tool. I started to make a webGL app to load an display those files. I can decode a lot more than the python script now. I can load those mesh, but also Senran Kagura meshes (even if I4m still missing some data purpose). I have also a start for animation file read and play. I'll make this online tool public later when it's more stable & usable. I can also give you information of the format if someone want to upgrade the Noesis script.

By the way, if someone know were are the shaders used by the game. I suppose they are somewhere in a binary, but didn't found them yet.

Edit : Meshes / Animations & Shaders are now working for gravure chance. I will do some clean and easy interface and make it avaiable by the week probably. I still need to try to extract the shaders for Senran Kagura since they use some others.

Ex :
it's excellent! thanks for your work.i'll wait for the tool to be released.
## Post #13
- Username: xele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 15, 2018 2:19 am
- Post datetime: 2018-05-01T21:23:39+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

I finished a first version avaiable here : [http://www.xele.org/BumViewer/viewer.html](http://www.xele.org/BumViewer/viewer.html) . Custom mode for dropping data, or select ToLoveRu / SenranKagura to load a preset bg + character + anim (At the moment, I only set a few data for test).
## Post #14
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2018-05-02T15:58:18+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

> Reply from xele
>
> I finished a first version avaiable here : http://www.xele.org/BumViewer/ . Custom mode for dropping data, or select ToLoveRu / SenranKagura to load a preset bg + character + anim (At the moment, I only set a few data for test).
it's awesome work！i test it in the custom mode,and it works well.I'm wonder is there anyway to scroll the page or drag the model? because when I zoom up the model, it would be out of the page .



TIM20180502235332.jpg (196.91 KiB) Viewed 1112 times
## Post #15
- Username: xele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 15, 2018 2:19 am
- Post datetime: 2018-05-02T16:49:13+00:00
- Post Title: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

Use the right button for moving the camera top-down/left-right.
## Post #16
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2018-05-03T13:25:33+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

> Reply from xele
>
> Use the right button for moving the camera top-down/left-right.
3Q.and the l also find it every character has a tail like Lala,I think maybe the non-tail modle  is in the .bsim file in the "/co",could u  try to decode them into the bum?
## Post #17
- Username: xele
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 15, 2018 2:19 am
- Post datetime: 2018-05-03T17:02:22+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

I suppose the tail is hidden by the game depending the character. I will make later an UI to hide/show specific mesh etc... I have not finished all the data guess, and the BSIM is in the list. For what I saw, it seems to contains info to correctly map the hair bones to the standard skeleton. There is also blend mesh for the breast size on some model which I need to setup. And today I found a lot of vertex buffer format which are not correctly read at the moment, so a lot of work to do ^^.
## Post #18
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2018-05-04T10:32:21+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

> Reply from xele
>
> I suppose the tail is hidden by the game depending the character. I will make later an UI to hide/show specific mesh etc... I have not finished all the data guess, and the BSIM is in the list. For what I saw, it seems to contains info to correctly map the hair bones to the standard skeleton. There is also blend mesh for the breast size on some model which I need to setup. And today I found a lot of vertex buffer format which are not correctly read at the moment, so a lot of work to do ^^.
 sounds like a good news.thanks for your work.I will wait it
## Post #19
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2018-11-20T10:46:45+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

Looks great, but will there be anyway to convert them in to a DAE, FBX or anything that supports rigging of any kind?
## Post #20
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-16T08:54:05+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

Does anyone know about three.js?
I've modified the xele code to be able to extract bone structures and json-style animation clips. 
These are converted in three.js to THREE.SkinnedMesh and THREE.AnimationClip respectively. 

I'm finally trying to combine and output these using THREE.GLTFExporter but it doesn't work.
Probably because it uses a "custom mesh", it can be avoided by combining it with Noesis(bum --> GLTF --> three.js), 
but it seems that Animation Clip can only be output with a properly bind Skinned Mesh.
Probably another shot. If anyone can give me some advice, please let me know. 

It's based on xele's code, so I'll ask him if I can share it if it's complete.
## Post #21
- Username: nyxenover
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 17, 2021 2:15 pm
- Post datetime: 2021-09-17T11:48:56+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

> Reply from einherjar007 ↑Fri Jul 16, 2021 4:54 pm at Fri Jul 16, 2021 4:54 pm
>
> 
Does anyone know about three.js?
I've modified the xele code to be able to extract bone structures and json-style animation clips. 
These are converted in three.js to THREE.SkinnedMesh and THREE.AnimationClip respectively. 

I'm finally trying to combine and output these using THREE.GLTFExporter but it doesn't work.
Probably because it uses a "custom mesh", it can be avoided by combining it with Noesis(bum --> GLTF --> three.js), 
but it seems that Animation Clip can only be output with a properly bind Skinned Mesh.
Probably another shot. If anyone can give me some advice, please let me know. 

It's based on xele's code, so I'll ask him if I can share it if it's complete.
out of curiosity would that mean you still have access to the assets on xele's site or the game itself? i know thats probably jumping right into conclusions but ive had little luck finding all the assets that was at some point and i haven't really heard much of anything since the game shut down not to mention it seems this has become a bit stale unfortunately due to the years that have passed
## Post #22
- Username: Tro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 12, 2023 8:34 pm
- Post datetime: 2023-06-01T17:22:47+00:00
- Post Title: Re: To LOVE-Ru Darkness: Gravure Chances .bum noesis script

And the APK and data of To LOVE-Ru Darkness: Gravure Chance, i'm searching but nothing
