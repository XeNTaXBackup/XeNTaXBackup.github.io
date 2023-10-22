## Post #1
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-01-25T22:19:55+00:00
- Post Title: Noesis g1m/g1t/g1a importer

Important info first :
If you have some questions about assets' extraction, ask them on Yretenai's thread here viewtopic.php?f=10&t=21679
If you used the python script before and want to use the new C++ plugin, make sure to delete the former
If Noesis crashes when using that plugin, DO NOT SEND the crash report, even though you're asked to. This is not a Noesis problem, it's a plugin issue so it'll be a false positive report, instead make a post on that thread or on the github repo


Features :
Loads g1m model files
Merges split g1m model files automatically, removing duplicate bones and preserving everything. All physics bones/meshes are merged seamlessly.
Loads g1t texture files, either independently or applied to a model
Supports the recent G2A animation format and the old G1A format. For both of them, only skeletal animations are supported for now. Additive animations (provided it's relative to the rest pose) are supported.
Big Endian and Little Endian support
Physics bones for hair strands and accessories correctly extracted and rigged to the main armature
NUNO type 1, NUNO type 3, NUNV type 1, NUNS type 1 physics meshes supported. The physics nodes and their associated "driver" meshes are respectively exported as bones and blank meshes, correctly rigged to the base armature. 

You can access the plugin's options by clicking on the "Tools" pannel in Noesis :
Merge all assets in the same folder : Self explanatory. That option will take every g1m, g1t, g1a, g2a, oid file in the folder and merge them accordingly.
Only models when merging : If the above option is set to true, only the g1m files will be merged together. 
Select G1T when non/partial merge : When loading model files only, ask for a g1t file per "true" model. This is useful if the game has the texture file in a separate folder and you don't want to copy it to the model folder everytime for all the models.
Additive animations : The animations will be loaded as additive anims. As of now only additive anims on top of the base pose are supported. Only use this if the animation doesn't look right (DOA6 facial anims for example).
Process vertex colors : Self explanatory
Display physics drivers : Self explanatory, only relevant when the model has some "NUN" sections
Disable NUN nodes : NUN bones and drivers won't be in the final model at all, not just hidden

Now a few notes about merging, 2 merge types are supported :
The "classic" split g1m files, where the skeleton is in its own g1m file and the geometry in one or several other g1ms. There's a single g1t file for all of these. To get that model correctly with all the parts, just set the merge option to true, and open whatever g1m
The "complete" g1m files. For example in DOA6 and FETH head and body are in separate g1m files but each one of them has the skeleton, geometry and an associated g1t file. Merging those is supported too : place all the g1m and their g1t files  in a single folder and use the merge options.

That's pretty much it.

Native Noesis C++ plugin : https://github.com/Joschuka/Project-G1M/releases/latest  

Old python script (deprecated, only use if the new plugin doesn't work) : [https://github.com/Joschuka/fmt_g1m](https://github.com/Joschuka/fmt_g1m)




Additionnal credits (for the last version):
-Rich Whitehouse, for making such a great tool in the first place and for all the help he gave me when writing the plugin. The latter wouldn't be nearly as complete without all the handy functions and interfaces available in Noesis.
-Chrrox for all the general Noesis help.
-Eternity/Vagonumero13 for some new format findings during the last months.
-Kerilk, Yretenai, PredatorCZ and Rich for the Noesis C++ plugin samples.
-Raytwo for finding the flag to discriminate between split and non split models.
-DeathChaos25, Moonling, mono24, Allanoon and einherjar007 for testing and reporting bugs.

Credits (first version):
-My partner Yretenai who helped me by providing me samples, figuring out the formats with me, developping custom tools and writing binary templates.
-Semory/Howfie who did a phenomenal job figuring out most of the g1m/g1t formats, the gas machine source code was my main reference when working on the plugin.
-Chrrox and Rich Whitehouse for their help during the development and their Noesis scripts that I used as reference.
-Acewell for his Noesis scripts for various texture formats that I used as reference.
-VitaSmith for the gust-tools which helped us for g1t
-Ploaj for his work on cloth type 1, which helped me to better understand the computation needed for this cloth type
-Daemon's NT Tool, which output was used as reference for some models.
-Eternity, who we teamed up with to figure out the animation formats.
-PredatorCZ for his help on the animation binary template when we hit a dead end.
-Delguoqing for his research on g1a
-S-ilent, who provided me some BE samples and pushed me to add BE support.
-DeathChaos who provided me samples, tested the plugin and proposed some features.
-Demonslayerx8 for a lot of testing and samples sharing.
## Post #2
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-01-26T15:35:24+00:00
- Post Title: Noesis g1m/g1t/g1a importer

oh this is actually nice, but seems like MUA3 has meshes not lined up with the boneset


If ya like, I can send ya a few samples, maybe some uncompressed files too?

edit:
also doing Merger gives me this


[G1M's for Vision (along with G1T) here](https://cdn.discordapp.com/attachments/278347451583299585/671017728903217152/0004_VISION_mdl.rar)
## Post #3
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2020-01-26T16:29:56+00:00
- Post Title: Noesis g1m/g1t/g1a importer

May I know what games have you tested your tool with?

I'm interested in testing the ones you did not try yet, possibly increasing your compatibility list. 
This is pretty nice
## Post #4
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-01-26T17:04:35+00:00
- Post Title: Noesis g1m/g1t/g1a importer

> Reply from demonslayerx8 ↑Sun Jan 26, 2020 11:35 pm at Sun Jan 26, 2020 11:35 pm
>
> 
oh this is actually nice, but seems like MUA3 has meshes not lined up with the boneset


If ya like, I can send ya a few samples, maybe some uncompressed files too?

edit:
also doing Merger gives me this


G1M's for Vision (along with G1T) here

Thank you for the samples, seems like some blendweight issue. I probably missed some semantics, will take a look at the files when I have some time.

Merging works for me, the above error happens when you don't provide a valid skeleton.

> Reply from lolwatt ↑Mon Jan 27, 2020 12:29 am at Mon Jan 27, 2020 12:29 am
>
> 
May I know what games have you tested your tool with?

I'm interested in testing the ones you did not try yet, possibly increasing your compatibility list. 
This is pretty nice

Pretty much all of my testing samples were from Fire emblem three houses, dissidia NT and hyrule warriors. I also tried a few atelier models here and there, feel free to report any issue you have with any game with the tool so I can add support to it. The game I'm currently focusing on is DOA6, most models work fine but there are some issues.
## Post #5
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-01-26T17:56:04+00:00
- Post Title: Noesis g1m/g1t/g1a importer

> Reply from lolwatt ↑Mon Jan 27, 2020 12:29 am at Mon Jan 27, 2020 12:29 am
>
> 
May I know what games have you tested your tool with?

I'm interested in testing the ones you did not try yet, possibly increasing your compatibility list. 
This is pretty nice

I've been testing it thoroughly, and here's my list
-Warriors All Stars[PC]
-Warriors Orochi 4[Switch]
-Hyrule Warriors[WiiU]/Definitive Edition[Switch]
--->Animations work
-Fire Emblem Warriors[Switch]
--->Animations work; G2A for Body, G1A for face
-Marvel Ultimate Alliance 3[Switch] (main model needs to be aligned to boneset tho)
--->Animations work; G2A Format
-Fire Emblem Three Houses[Switch]
--->Animations work; G2A Format
-One Piece Pirate Warriors 3[PC] (same issue as MUA3)
-Samurai Warriors 4-II[PC]
-Berserk and the Band of the Hawk[PC] (same issue as MUA3, some models have weight issue's)
--->Animations work; G2A Format
## Post #6
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-01-26T23:29:06+00:00
- Post Title: Noesis g1m/g1t/g1a importer

Fantastic Tool, thank you!
EDITED: It works with Toukiden Kiwami (meshes, anim, texture too i supose), will try with Toukiden 2 too, for big bosses you need to enable manual skeleton loading or it'll throw an error (just needed to read better ^^")

Question 2: is there an "easy" way to identify the animation or the best bet is "load everything"? xD
## Post #7
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-01-27T01:27:07+00:00
- Post Title: Noesis g1m/g1t/g1a importer

> Reply from Allanoon ↑Mon Jan 27, 2020 7:29 am at Mon Jan 27, 2020 7:29 am
>
> 
Fantastic Tool, thank you!
EDITED: It works with Toukiden Kiwami (meshes, anim, texture too i supose), will try with Toukiden 2 too, for big bosses you need to enable manual skeleton loading or it'll throw an error (just needed to read better ^^")

Question 2: is there an "easy" way to identify the animation or the best bet is "load everything"? xD

Glad you like it, thank you for testing the script on these games.

Unfortunately most KT games won't have filenames so yeah I'd the say the best solution for now if your extractor doesn't provide some would be :
-load whole folders of animations
-check the results on preview 
-when you see an animation you like, pause and check at which frame you are (top right)
-open the data viewer (tool/data viewer) and check the Animation section, you'll have the start and end frame of each animation, enabling you to get the animation name
-put all of the animations you want in a folder, load them all, export

Good luck !
## Post #8
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-01-27T19:42:56+00:00
- Post Title: Noesis g1m/g1t/g1a importer

Hello, need help, maybe i dont understand
i use latest version Noesis4417, copy two files .py in noesisv4417\plugins\python
try star noesis.exe and see this error
tool_merge.py and fmt_g1m.py, same error too
[image.png](https://xentaxbackup.github.io/file/17425_image.png)
## Post #9
- Username: Crazy31139
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2020-01-27T21:09:54+00:00
- Post Title: Noesis g1m/g1t/g1a importer

you did not download the files you saved the webpage of the files.
## Post #10
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-01-28T07:27:12+00:00
- Post Title: Noesis g1m/g1t/g1a importer

Small question:
Why when I load a model from NT, the texture come all like in lines? Beside that UV actually work, just the texture come out like that (and still don't know were the animation are lol, but, me ok)
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2020-01-28T09:28:34+00:00
- Post Title: Noesis g1m/g1t/g1a importer

what version are you using ps4 or pc?
## Post #12
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-01-28T13:41:29+00:00
- Post Title: Noesis g1m/g1t/g1a importer

> Reply from chrrox ↑Tue Jan 28, 2020 5:28 pm at Tue Jan 28, 2020 5:28 pm
>
> 
what version are you using ps4 or pc?
PS4.
Wait, now it is possible to unpack Steam version?
## Post #13
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-28T15:42:32+00:00
- Post Title: Noesis g1m/g1t/g1a importer

> Reply from Darkhowlings ↑Tue Jan 28, 2020 9:41 pm at Tue Jan 28, 2020 9:41 pm
>
> 
chrrox wrote: ↑Tue Jan 28, 2020 5:28 pm
what version are you using ps4 or pc?

PS4.
Wait, now it is possible to unpack Steam version?

You can dump textures from memory.


On an aside: I noticed something interesting with G1T textures, if people could PM me G1T samples from different platforms I'd appreciate it.
## Post #14
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-01-29T11:31:16+00:00
- Post Title: Noesis g1m/g1t/g1a importer

Hi Again, I tested the program with some other games~
So yeah Toukiden 2 perfectly works too!
The Program also work with BladeStorm Nightmare (unpacked with Steven's gas machine)
It also work with Nioh, i can load Textures and models after extracting with daemon1 tool, Animations seems to be working too (they're packed together i manually extracted them with HxD). Unfortunately the bms script doesn't extract everything and everything is a mess so i stopped looking.

It partially works with Deception IV Blood Ties PS3 (Kagero Dark Side Princess with Steven's machine), the meshes are loaded but require to load the skeleton, Texture throws this error (although they can be extracted with Steven's machine i guess)

There some G1A anim and various G2A too, both give errors when trying to load them
G1A

G2A

If You're interestend in taking a look i can up them.

And now 2 OT questiong regarding Hyrule Warriors:
1- Could someone point me out how to extract animations properly? I decrypt the file with daemon1 tool, Then i used the same method of Nioh, Cut/Paste in HxD but manualy doing so to extract 1xx file is... ugly   
2- I noticed that out of the 186 animations extracted (Lizalfos enemy) only the 1st 95 works, the others area loaded but break the model are they like... additive animations or.. what?
## Post #15
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-29T15:11:57+00:00
- Post Title: Noesis g1m/g1t/g1a importer

> Reply from Allanoon ↑Wed Jan 29, 2020 7:31 pm at Wed Jan 29, 2020 7:31 pm
>
> 
1- Could someone point me out how to extract animations properly? I decrypt the file with daemon1 tool, Then i used the same method of Nioh, Cut/Paste in HxD but manualy doing so to extract 1xx file is... ugly

Use my tool Cethleann [https://github.com/healingbrew/Cethlean ... ts/1421065](https://github.com/healingbrew/Cethleann/suites/426779901/artifacts/1421065), drag the decrypted motion bin.gz file into Cethleann.Unbundler.exe.
Read more about it here [viewtopic.php?f=10&t=21679](https://forum.xentax.com/viewtopic.php?f=10&t=21679)
## Post #16
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-01-29T21:13:29+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

First update released 
-oid support added by Yretenai and S-ilent
-skeletons will now be lined up accordingly for all the meshes
-the G2A anim parser was slightly off and broke some animations, all anims should work correctly now
-new datatypes have been added for existing semantics
-new texture formats are now supported, including PS4 swizzled textures.

I am aware of some issues involving NUNO sections and bone index buffers, I wil look into them

Big thanks to Acewell for his scripts which I used as a reference for most of the new texture formats

Also my partner Yretenai released some tools to unpack/extract models compatible with this script, definitely check these out [viewtopic.php?f=10&t=21679](https://forum.xentax.com/viewtopic.php?f=10&t=21679)

> Reply from Allanoon ↑Wed Jan 29, 2020 7:31 pm at Wed Jan 29, 2020 7:31 pm
>
> 
It partially works with Deception IV Blood Ties PS3 (Kagero Dark Side Princess with Steven's machine), the meshes are loaded but require to load the skeleton, Texture throws this error (although they can be extracted with Steven's machine i guess)

The first and last error you mentionned should be fixed with the last update. I am aware of the second one and will look into it. Thank you for testing the script.

> Reply from Allanoon ↑Wed Jan 29, 2020 7:31 pm at Wed Jan 29, 2020 7:31 pm
>
> 
2- I noticed that out of the 186 animations extracted (Lizalfos enemy) only the 1st 95 works, the others area loaded but break the model are they like... additive animations or.. what?

I'm not 100% sure but we saw that some g1a are used for camera animations in DOA6 and in some games g1a can be used for morph targets. As of now the parser considers that it's a skeletal anim everytime which can probably lead to some really weird results. We'll look more into it.

> Reply from Darkhowlings ↑Tue Jan 28, 2020 3:27 pm at Tue Jan 28, 2020 3:27 pm
>
> 
Small question:
Why when I load a model from NT, the texture come all like in lines? Beside that UV actually work, just the texture come out like that (and still don't know were the animation are lol, but, me ok)

I didn't have support for PS4 textures at that time as that tool was developped with the PC version. Use Yretenai's utilities to unpack the animations.
## Post #17
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-01-29T21:57:43+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Awesome  !

Even do, I'm still wonder how they end extracting the steam version of NT, I remember it was impossible to unpack it...
## Post #18
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-30T01:58:48+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Darkhowlings ↑Tue Jan 28, 2020 3:27 pm at Tue Jan 28, 2020 3:27 pm
>
> 
Small question:
Why when I load a model from NT, the texture come all like in lines? Beside that UV actually work, just the texture come out like that (and still don't know were the animation are lol, but, me ok)

Which textures?
## Post #19
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-01-30T18:30:33+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Darkhowlings ↑Thu Jan 30, 2020 5:57 am at Thu Jan 30, 2020 5:57 am
>
> 
Awesome  !

Even do, I'm still wonder how they end extracting the steam version of NT, I remember it was impossible to unpack it...

My toolsuite Cethleann has a program called Ninja.DataExtractor.exe, which can decompress the files. You can find the link to the post in my signature, but it requires some command line usage knowledge.

```

```


in other words usage is:

```

```


I'm a little anxious sharing this, I don't want them to change the way the files are compressed and having this tool might lead to just that. They could also just DMCA my repository.
## Post #20
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-01-31T05:16:54+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Yeah, I've told on private about the tool and how use it, but, I thank you & Joschka for take time on answer me too.
## Post #21
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-01T00:45:10+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Thu Jan 30, 2020 5:13 am at Thu Jan 30, 2020 5:13 am
>
> 
Allanoon wrote: ↑Wed Jan 29, 2020 7:31 pm
It partially works with Deception IV Blood Ties PS3 (Kagero Dark Side Princess with Steven's machine), the meshes are loaded but require to load the skeleton, Texture throws this error (although they can be extracted with Steven's machine i guess)


The first and last error you mentionned should be fixed with the last update. I am aware of the second one and will look into it. Thank you for testing the script.
Allanoon wrote: ↑Wed Jan 29, 2020 7:31 pm
2- I noticed that out of the 186 animations extracted (Lizalfos enemy) only the 1st 95 works, the others area loaded but break the model are they like... additive animations or.. what? 


I'm not 100% sure but we saw that some g1a are used for camera animations in DOA6 and in some games g1a can be used for morph targets. As of now the parser considers that it's a skeletal anim everytime which can probably lead to some really weird results. We'll look more into it.

Nono, thank YOU i LOVE model viewing and having quite a bunch of games to see is always nice ! 
Unfortunately imma gona pester you with errors and such, apologize, bear with me   

Regarding Kagero: yes! Textures now work and .g1a animation seems to be loading too (but are few and doesn't work on models i guess they regard something else) .g2a still throw the error of my previous post.

Fist of the North Star 2: Texture loads but are horribles [https://i.imgur.com/88pYVpg.png](https://i.imgur.com/88pYVpg.png) Models mostly works except for bodies, those give this error 

Animations are .g2a and give an error "similar" to Kagero


One Piece Pirate Warriors 3: Almost everything works, but for some models the body gives this error


Some games: Textures loads but Diffuse one are visualized much like kenshiro textures.

[Here are the files](https://www.mediafire.com/file/yfxt7d5ha1j74rm/Games_Files.rar/file) which i talked about in case you need them.


> Reply from Yretenai ↑Wed Jan 29, 2020 11:11 pm at Wed Jan 29, 2020 11:11 pm
>
> 
Allanoon wrote: ↑Wed Jan 29, 2020 7:31 pm
1- Could someone point me out how to extract animations properly? I decrypt the file with daemon1 tool, Then i used the same method of Nioh, Cut/Paste in HxD but manualy doing so to extract 1xx file is... ugly   


Use my tool Cethleann https://github.com/healingbrew/Cethlean ... ts/1421065, drag the decrypted motion bin.gz file into Cethleann.Unbundler.exe.
Read more about it here viewtopic.php?f=10&t=21679

You're a lifesaver! thank you for your tools! Looking forward those extractors
## Post #22
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-01T12:11:20+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Sat Feb 01, 2020 8:45 am at Sat Feb 01, 2020 8:45 am
>
> 
Some games: Textures loads but Diffuse one are visualized much like kenshiro textures.

Already fixed in the latest version, Kenshiro still borked.
I'm looking into Kenshiro textures, might have to do with the fact it's a BE file.

Edit: Yep. The texture data is endian flipped. Will be fixed next update.
## Post #23
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-01T22:46:40+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

New update
-Xbox 360 texture support has been added
-If a model was supposed to have several g1t files it won't crash anymore because of missing indexes.
-Morph target support. Choose a G1H file and an offset in the parameters and it'll output all of them. Thanks to S-ilent for his research on the format.


> Reply from Allanoon ↑Sat Feb 01, 2020 8:45 am at Sat Feb 01, 2020 8:45 am
>
> 

Nono, thank YOU i LOVE model viewing and having quite a bunch of games to see is always nice ! 
Unfortunately imma gona pester you with errors and such, apologize, bear with me

Hehe no problem. You have a bunch of BE games and platforms we didn't have samples from so it's nice to be able to work on these.

> Reply from Allanoon ↑Sat Feb 01, 2020 8:45 am at Sat Feb 01, 2020 8:45 am
>
> 
Regarding Kagero: yes! Textures now work and .g1a animation seems to be loading too (but are few and doesn't work on models i guess they regard something else) .g2a still throw the error of my previous post.

Textures should now be ok with the last update. g1a animation are probably for cameras or fields, in DOA all anims are in G2A whereas g1a is only for camera. I can confirm the error, I'm pretty sure it comes from the fact that it's Big Endian, we didn't have BE samples for animations, I'll take a look.

> Reply from Allanoon ↑Sat Feb 01, 2020 8:45 am at Sat Feb 01, 2020 8:45 am
>
> 
Fist of the North Star 2: Texture loads but are horribles Models mostly works except for bodies, those give this error
Yes, this was because we didn't have X360 texture support. Yretenai added it so it should work fine. The error came from the fact that only g1t containing all textures for the models were supported, if they were split in 2 g1ts or more it crashed. It should now work with crashes but you won't be able to load all of them at once for now. You will have to export them separately.

> Reply from Allanoon ↑Sat Feb 01, 2020 8:45 am at Sat Feb 01, 2020 8:45 am
>
> 
One Piece Pirate Warriors 3: Almost everything works, but for some models the body gives this error
Ah yes I'm aware of this error on some models, this will be the next thing I'll look into.

> Reply from Allanoon ↑Sat Feb 01, 2020 8:45 am at Sat Feb 01, 2020 8:45 am
>
> 
Some games: Textures loads but Diffuse one are visualized much like kenshiro textures.
Most X360, PS4, ETC1 (mobile), Vita, Switch and PC textures should now load fine with the last update. WiiU swizzle is still unsupported but you can use Switch Toolbox for them
## Post #24
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2020-02-02T07:52:15+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Stupid question about DOA6, the breasts are not rigged or they are influeced by the softbodies engine?
## Post #25
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-02T11:31:04+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Darko ↑Sun Feb 02, 2020 3:52 pm at Sun Feb 02, 2020 3:52 pm
>
> 
Stupid question about DOA6, the breasts are not rigged or they are influeced by the softbodies engine?

That's not a stupid question at all

Similarly to NUNO/NUNV for cloth, DOA6 (and other games) have SOFT and HAIR chunks that contain the necessary info for simulation.
For breasts the SOFT chunks are used. From what we discovered it would be probably be possible to construct physics bones similarly to what we did for the cloth drivers with NUNO/NUNV. We may look into it at some point, I'd like to fix the few NUN sections issues before that though
## Post #26
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-02-03T03:40:58+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Feb 02, 2020 7:31 pm at Sun Feb 02, 2020 7:31 pm
>
> 
Darko wrote: ↑Sun Feb 02, 2020 3:52 pm
Stupid question about DOA6, the breasts are not rigged or they are influeced by the softbodies engine?


That's not a stupid question at all

Similarly to NUNO/NUNV for cloth, DOA6 (and other games) have SOFT and HAIR chunks that contain the necessary info for simulation.
For breasts the SOFT chunks are used. From what we discovered it would be probably be possible to construct physics bones similarly to what we did for the cloth drivers with NUNO/NUNV. We may look into it at some point, I'd like to fix the few NUN sections issues before that though

That happen with NT hair too, no?
Or on NT they simple don't have?
## Post #27
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-03T08:12:58+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Darkhowlings ↑Mon Feb 03, 2020 11:40 am at Mon Feb 03, 2020 11:40 am
>
> 
Joschka wrote: ↑Sun Feb 02, 2020 7:31 pm
Darko wrote: ↑Sun Feb 02, 2020 3:52 pm
Stupid question about DOA6, the breasts are not rigged or they are influeced by the softbodies engine?


That's not a stupid question at all

Similarly to NUNO/NUNV for cloth, DOA6 (and other games) have SOFT and HAIR chunks that contain the necessary info for simulation.
For breasts the SOFT chunks are used. From what we discovered it would be probably be possible to construct physics bones similarly to what we did for the cloth drivers with NUNO/NUNV. We may look into it at some point, I'd like to fix the few NUN sections issues before that though


That happen with NT hair too, no?
Or on NT they simple don't have?
NT uses animated hair, not simulated.
## Post #28
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-02-03T10:54:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Cloth meshes all are broken or disappeared for Fatal Frame Maiden of Black water G1Ms
Can you check this?
Also, how do you extract animations?
[G_BOS_A.GMPK.7z](https://xentaxbackup.github.io/file/17450_G_BOS_A.GMPK.7z)
## Post #29
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-03T12:28:39+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Script updated
-Yretenai managed to figure out more about the materials and textures, the models will now have have normal maps automatically mapped and more
-Fixed the bone index buffer bug, models with this issue should now load fine


> Reply from ngovandang ↑Mon Feb 03, 2020 6:54 pm at Mon Feb 03, 2020 6:54 pm
>
> 
Cloth meshes all are broken or disappeared for Fatal Frame Maiden of Black water G1Ms
Can you check this?
Also, how do you extract animations?

I will eventually but not soon, I discovered some issues with the way I compute cloth and the NUN sections but I don't want to work on it right now, these are really annoying to deal with. Next fixes are the G2A Big endian and the second layers of blendweights that I overlooked then Persona 5 S will have my whole attention. So unless P5S really needs it I won't update it in the next days.

You need G1A/G2A, don't know what your game uses. If your game has G2A you'll need to wait for my Big Endian fix since it seems to be a WiiU game. Use Yretenai's utilities to get them, they're probably in a GAPK or something
## Post #30
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-02-04T01:46:59+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Mon Feb 03, 2020 8:28 pm at Mon Feb 03, 2020 8:28 pm
>
> 
Script updated
-Yretenai managed to figure out more about the materials and textures, the models will now have have normal maps automatically mapped and more
-Fixed the bone index buffer bug, models with this issue should now load fine
My heart... my heart, I don't feel it after seeing this glorious update!

> Reply from Yretenai ↑Mon Feb 03, 2020 4:12 pm at Mon Feb 03, 2020 4:12 pm
>
> 
NT uses animated hair, not simulated.

I see, thanks again for the info!
## Post #31
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-04T17:58:12+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Script updated

-KSLT support. You can now open and preview these files. These are UI textures.
-G2A version 0200 and 0300 Big endian should now work. I didn't have many samples so tell me if you have any issue with these.
-My partner Yretenai added Nioh support to her Cethleann tools, you can now extract models and animations from this game. HOWEVER the script as it currently is will take some time to load the models so be patient if you want to preview the models right now. I plan to rework some parts to speed things up.
## Post #32
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-04T18:37:34+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Feb 05, 2020 1:58 am at Wed Feb 05, 2020 1:58 am
>
> 
Script updated

-KSLT support. You can now open and preview these files. These are UI textures.
-G2A version 0200 and 0300 Big endian should now work. I didn't have many samples so tell me if you have any issue with these.
-My partner Yretenai added Nioh support to her Cethleann tools, you can now extract models and animations from this game. HOWEVER the script as it currently is will take some time to load the models so be patient if you want to preview the models right now. I plan to rework some parts to speed things up.

Note: KSLT files are primarily used in Team Ninja games, such as Dead or Alive, Dissidia NT, and Nioh.
Support for it is preliminary, with only 4 texture types supported.
## Post #33
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-04T19:12:45+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Feb 05, 2020 1:58 am at Wed Feb 05, 2020 1:58 am
>
> 
Script updated

-KSLT support. You can now open and preview these files. These are UI textures.
-G2A version 0200 and 0300 Big endian should now work. I didn't have many samples so tell me if you have any issue with these.
-My partner Yretenai added Nioh support to her Cethleann tools, you can now extract models and animations from this game. HOWEVER the script as it currently is will take some time to load the models so be patient if you want to preview the models right now. I plan to rework some parts to speed things up.

Unfortunately regarding G2A animations, i'm still getting the exact same error of my previous post. I can send more samples if you need tou.

+ the script is working fine with Attack on Titans 1 (2 too most likely), Dragon Quest heroes 2 (pc) and Trinity: souls of zill'o II (ps3)
## Post #34
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-04T19:40:24+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Wed Feb 05, 2020 3:12 am at Wed Feb 05, 2020 3:12 am
>
> 
Joschka wrote: ↑Wed Feb 05, 2020 1:58 am
Script updated

-KSLT support. You can now open and preview these files. These are UI textures.
-G2A version 0200 and 0300 Big endian should now work. I didn't have many samples so tell me if you have any issue with these.
-My partner Yretenai added Nioh support to her Cethleann tools, you can now extract models and animations from this game. HOWEVER the script as it currently is will take some time to load the models so be patient if you want to preview the models right now. I plan to rework some parts to speed things up.


Unfortunately regarding G2A animations, i'm still getting the exact same error of my previous post. I can send more samples if you need tou.

Hmm weird, I can extract the Fist of the North Star 2 animations you gave me fine 



Couldn't try with Kagero ones because the skeleton was not compatible with the anims but I didn't have errors during parsing.
Yes, feel free to send me some non working samples so I can take a look.

> Reply from Allanoon ↑Wed Feb 05, 2020 3:12 am at Wed Feb 05, 2020 3:12 am
>
> 
the script is working fine with Attack on Titans 1 (2 too most likely), Dragon Quest heroes 2 (pc) and Trinity: souls of zill'o II (ps3)
Oh nice, as a big Dragon quest fan I wanted to see if that worked with DQH2, there are some really nice models in that game for many great characters of the series
## Post #35
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-04T20:30:16+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

PC Nioh models, textures and screen textures work btw, just no clue which animations are the right ones.



20200204202604.jpg (178.48 KiB) Viewed 674 times
## Post #36
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-04T21:00:41+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Feb 05, 2020 3:40 am at Wed Feb 05, 2020 3:40 am
>
> 
...

It seems like i had some problem with noesis, strange, dunno what i touched really, maybe it was loading an older version of the script, well i apologize    and thanks will thoroughly check them!
## Post #37
- Username: nekoknight
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 31, 2018 10:27 am
- Post datetime: 2020-02-05T00:39:56+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Awesome tool. Handled almost everything I threw at it... Except for some Atelier Ryza models. 



G1MError.PNG (40.28 KiB) Viewed 653 times



sample file: [https://www.mediafire.com/file/gmss9gf5 ... t.zip/file](https://www.mediafire.com/file/gmss9gf5exqusix/PC00I_MODEL_default.zip/file)
## Post #38
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-02-05T01:39:48+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Yretenai ↑Wed Feb 05, 2020 2:37 am at Wed Feb 05, 2020 2:37 am
>
> 
Joschka wrote: ↑Wed Feb 05, 2020 1:58 am
Script updated

-KSLT support. You can now open and preview these files. These are UI textures.
-G2A version 0200 and 0300 Big endian should now work. I didn't have many samples so tell me if you have any issue with these.
-My partner Yretenai added Nioh support to her Cethleann tools, you can now extract models and animations from this game. HOWEVER the script as it currently is will take some time to load the models so be patient if you want to preview the models right now. I plan to rework some parts to speed things up.


Note: KSLT files are primarily used in Team Ninja games, such as Dead or Alive, Dissidia NT, and Nioh.
Support for it is preliminary, with only 4 texture types supported.

Me. Can. Die. Happy.
That is what I most need, thanks a lot!!!
## Post #39
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-05T13:21:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Wed Feb 05, 2020 5:00 am at Wed Feb 05, 2020 5:00 am
>
> 
It seems like i had some problem with noesis, strange, dunno what i touched really, maybe it was loading an older version of the script, well i apologize    and thanks will thoroughly check them!

No problem, I sometimes forget to reload the script after modifying it too. You can use the shortcut Alt-T then Alt-R to reload the script quickly without closing noesis. Thank you for all the tests !

> Reply from nekoknight ↑Wed Feb 05, 2020 8:39 am at Wed Feb 05, 2020 8:39 am
>
> 
Awesome tool. Handled almost everything I threw at it... Except for some Atelier Ryza models.

Ah yes I am aware of this issue, it is related to the way I parse the NUN sections. As I said in a previous post I will modify the cloth computation at some point since I was slightly off and found out more stuff after more research. As of now most models seem to work but some of them have wrongly placed or not working cloth type 1 meshes. 
Will probably do that next week or something like that unless P5S demo assets have this issue too, in which case I'll fix that sooner.

> Reply from Darkhowlings ↑Wed Feb 05, 2020 9:39 am at Wed Feb 05, 2020 9:39 am
>
> 
Me. Can. Die. Happy.
That is what I most need, thanks a lot!!!

Glad you like it !
## Post #40
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-06T18:54:06+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

I can confirm that Persona 5 S models mostly work without any modification. Only annoying thing is that texture files are split like in DOA6 so no automatic mapping. You'll have to extract them separately and place them in your favorite 3D software. Check Yretenai's tools new update for extraction of the files [viewtopic.php?f=10&t=21679&start=30#p159700](https://forum.xentax.com/viewtopic.php?f=10&t=21679&start=30#p159700)

Good news for some people : some persona models have the cloth issue seen on other models like Ryza and DOA so I'll fix it sooner than expected.
## Post #41
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-07T12:48:01+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hi Again~

For both Deception IV and Kenshiro animations i upped other files
[https://www.mediafire.com/file/ryq62857 ... n.rar/file](https://www.mediafire.com/file/ryq62857324pylp/Deception_IV_-_Ken.rar/file)

Deception IV those are all  the animations, but the "characters" one are in folder 0776 although only a handful loads.
Kenshiro some models load mostly all animations (i pointed the ones not loading), Kenshiro character animations all gives "not compatible" (Thanks einherjar007 for noticing!) despite being 100% sure i'm using the correct skeleton, same for one entire folder of the 2xx boss fighter.
I hope these samples are enough but i'll look for more if you need.
## Post #42
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-07T19:42:03+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Fri Feb 07, 2020 8:48 pm at Fri Feb 07, 2020 8:48 pm
>
> 
Hi Again~

For both Deception IV and Kenshiro animations i upped other files
https://www.mediafire.com/file/ryq62857 ... n.rar/file

Deception IV those are all  the animations, but the "characters" one are in folder 0776 although only a handful loads.
Kenshiro some models load mostly all animations (i pointed the ones not loading), Kenshiro character animations all gives "not compatible" (Thanks einherjar007 for noticing!) despite being 100% sure i'm using the correct skeleton, same for one entire folder of the 2xx boss fighter.
I hope these samples are enough but i'll look for more if you need.

Hopefully fixed with the last update, let me know if that still doesn't work.
## Post #43
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-09T18:33:13+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sat Feb 08, 2020 3:42 am at Sat Feb 08, 2020 3:42 am
>
> 
Hopefully fixed with the last update, let me know if that still doesn't work.

Yes, a good 95% of the animations are loaded now and that's good enough for me, thank you!
## Post #44
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-11T12:20:13+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Script updated

-New layer of bones and weights added + weight fixes, models with more than 4 weights per vertex should now work perfectly.If you had some weights issues (happened on some DOA6 faces and some MUA models for example) this update probably solved it. 
-I added 2 UV layers. So models with more than one uv layer should now have these. Let me know if you have weird results, wasn't able to test it thoroughly.

Cloth/NUNO/NUNV bug fixes are next.

> Reply from Allanoon ↑Mon Feb 10, 2020 2:33 am at Mon Feb 10, 2020 2:33 am
>
> 
Yes, a good 95% of the animations are loaded now and that's good enough for me, thank you!

Out of curiosity what's the issue with the other 5% ?
## Post #45
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-11T14:39:58+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Tue Feb 11, 2020 8:20 pm at Tue Feb 11, 2020 8:20 pm
>
> 
Out of curiosity what's the issue with the other 5% ?

Well i noticed that the only "error" the debug point out is "WARNING: Discarding keyframed animation because it contains no usable keys." that may simply be the reason for the script not to load them.
## Post #46
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-11T14:51:23+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Tue Feb 11, 2020 10:39 pm at Tue Feb 11, 2020 10:39 pm
>
> 
Well i noticed that the only "error" the debug point out is "WARNING: Discarding keyframed animation because it contains no usable keys." that may simply be the reason for the script not to load them.

Oh I see, it's probably because they are not character animations or something like that. If these animations are not among hundred others and you can find them easily, I can take a look if you want.

Thank you for all the tests and reporting btw, really appreciate it !
## Post #47
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2020-02-11T20:05:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Is there any chance for you to support DW9 g1m files? I mainly want support so I can use the animation files on them, I can provide whatever samples you need.
## Post #48
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-11T21:01:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

They don't work with the script ? Cause most games do now.
If that's some cloth mesh issue I'm currently working on it.
## Post #49
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2020-02-13T05:49:40+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

getting this error on some g1m files from dead or alive 6. even after update



error.png (13.8 KiB) Viewed 412 times


here some files [http://www.mediafire.com/file/s4v4im4mi ... es.7z/file](http://www.mediafire.com/file/s4v4im4mi9gcbj8/nyo_samples.7z/file)
## Post #50
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-13T09:23:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Yeah I worked on it yesterday and have a fix ready, I'll push it soon
## Post #51
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-13T22:17:43+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Tue Feb 11, 2020 10:51 pm at Tue Feb 11, 2020 10:51 pm
>
> 
Oh I see, it's probably because they are not character animations or something like that. If these animations are not among hundred others and you can find them easily, I can take a look if you want.

Thank you for all the tests and reporting btw, really appreciate it !

Naa it's my pleasure   
And well, only if you really want, while listing some of them i indeed noticed that they're all small files, 3-6kb big, so most likely we aren't missing anything important.

On another note, Dragon Quest Builder 2 is working, i couldn't check much yet but i've upped a monster+anim with some funny animations, if you want to check them and see if they're similar to hyrule one or such   

[https://www.mediafire.com/file/3nqvgjjz ... z.rar/file](https://www.mediafire.com/file/3nqvgjjzxdh2vyh/Filez.rar/file)
## Post #52
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2020-02-14T16:00:09+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hello, I was wondering, does Dissidia NT have OID.bins for bone names, cause i cannot seem to find anything related to those?
## Post #53
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-14T19:59:05+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

SCRIPT UPDATED

-I did more research on the NUNO/NUNV sections and changed the way I parse them. If you had some errors like that one, you shouldn't have them anymore.

```
  File "D:\Programs\noesis\plugins\python\fmt_g1m.py", line 1679, in LoadModel
    mesh.skinWeightList[v][0]
  File "D:\Programs\noesis\plugins\python\fmt_g1m.py", line 1019, in processClothVertex
    temp = NoeVec3()
KeyError: 18
```


-KT extended their NUN sections with some new info on recent models, which made the script crash. This is fixed, if you had this error before :

that should not happen anymore.

-After this update, DOA6 should now have full model support. Misplaced cloth meshes, errors on loading or weighting issues should be completely gone on all the models. 


-The fixes have mostly fixed Fatal Frame models. Cloth models and meshes are mostly well placed, with some rare exceptions, which can be fixed by hand. No texture support for now, WiiU swizzle is not implemented. Animations are in GAPK file but Yretenai tools are for LE only so you'll have to extract them on your own, make a quick bms script or something like that.
 

-I had a very limited amount of samples but DW models seem to work too now after this update.


As of now, all models should import without any errors
In some really rare cases, some cloth mesh is misplaced but the overwhelming majority should now be fine. If the model looked fine before the update it shouldn't have changed (let me know if it did), only the wrongly placed ones were affected. I'll see if I can find why there are a few exceptions.
## Post #54
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-14T20:07:27+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Fri Feb 14, 2020 6:17 am at Fri Feb 14, 2020 6:17 am
>
> 
Naa it's my pleasure   
And well, only if you really want, while listing some of them i indeed noticed that they're all small files, 3-6kb big, so most likely we aren't missing anything important.

Thanks, I'll take a look. Did you only try them on body meshes or did you try faces too ? They may be face animations.

> Reply from Allanoon ↑Fri Feb 14, 2020 6:17 am at Fri Feb 14, 2020 6:17 am
>
> 
On another note, Dragon Quest Builder 2 is working, i couldn't check much yet but i've upped a monster+anim with some funny animations, if you want to check them and see if they're similar to hyrule one or such

Oh I didn't know Koei made Dragon Quest Builders, I'll have a look at these assets for sure, thanks for the info !

> Reply from MarieRose1301 ↑Sat Feb 15, 2020 12:00 am at Sat Feb 15, 2020 12:00 am
>
> 
Hello, I was wondering, does Dissidia NT have OID.bins for bone names, cause i cannot seem to find anything related to those?

Yretenai didn't find some for that game so I don't think so.
## Post #55
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-15T08:00:05+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from MarieRose1301 ↑Sat Feb 15, 2020 12:00 am at Sat Feb 15, 2020 12:00 am
>
> 
Hello, I was wondering, does Dissidia NT have OID.bins for bone names, cause i cannot seem to find anything related to those?

Only Gust uses Object ID (OID) name lists, KTGL2 (RDB, first seen in DoA6, but also used by Persona 5 Scramble and Romance of the Three Kingdoms 14)  uses OIDs but with hashed names (often not refering to bone names either)
## Post #56
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-02-15T20:43:22+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sat Feb 15, 2020 4:07 am at Sat Feb 15, 2020 4:07 am
>
> 
Allanoon wrote: ↑Fri Feb 14, 2020 6:17 am
Naa it's my pleasure   
And well, only if you really want, while listing some of them i indeed noticed that they're all small files, 3-6kb big, so most likely we aren't missing anything important.


Thanks, I'll take a look. Did you only try them on body meshes or did you try faces too ? They may be face animations.

Good Guess, i usually overlook faces xD
...but nope, it doesn't seems to work for them too.
## Post #57
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-02-16T10:51:34+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

hi how can i unpacked GMPK file for Fatal Frame  Maiden of Black Water
please help me
## Post #58
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-16T18:49:09+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from gamer1977 ↑Sun Feb 16, 2020 6:51 pm at Sun Feb 16, 2020 6:51 pm
>
> 
hi how can i unpacked GMPK file for Fatal Frame  Maiden of Black Water
please help me

If the game isn't big endian, Cethleann.Unbundler should be able to unpack it.

I should really make bms scripts for these things.
## Post #59
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-17T20:15:33+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Sun Feb 16, 2020 4:43 am at Sun Feb 16, 2020 4:43 am
>
> 
Good Guess, i usually overlook faces xD
...but nope, it doesn't seems to work for them too.

Let's just say they're not important then hehe. They may be used for maps or something else, I know some g1a files can be used for map animations.

> Reply from gamer1977 ↑Sun Feb 16, 2020 6:51 pm at Sun Feb 16, 2020 6:51 pm
>
> 
hi how can i unpacked GMPK file for Fatal Frame  Maiden of Black Water
please help me

If that's a WiiU game Yretenai tools won't work. You can try the NT tools, I think Daemon implemented GMPK unpacking (use the Big Endian version if so)
## Post #60
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-02-17T20:41:32+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

NT tools don't work too
## Post #61
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-17T20:57:34+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from gamer1977 ↑Tue Feb 18, 2020 4:41 am at Tue Feb 18, 2020 4:41 am
>
> 
NT tools don't work too

I just googled "fatal frame gmpk" and the first link was  [https://www.vg-resource.com/thread-31370.html](https://www.vg-resource.com/thread-31370.html)

You have two bms script in that link, one for the g1m files and one for the g1t
## Post #62
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-02-18T03:45:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

thanks worked just models and textures extracted animations don't extracted
## Post #63
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-02-18T23:03:19+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Well, for last news, it is safe to say the tools will work on NT, because it will not get update after 3 of March.
## Post #64
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-20T07:25:22+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Darkhowlings ↑Wed Feb 19, 2020 7:03 am at Wed Feb 19, 2020 7:03 am
>
> 
Well, for last news, it is safe to say the tools will work on NT, because it will not get update after 3 of March.

there will still be bug fixes, but yeah no new content unfortunately 
DFFNT was one of the 3 reasons I started this entire thing lol, I love NT.

Ah well. Maybe i'll make a private server when the servers go down in three years
## Post #65
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-02-20T11:38:59+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Yretenai ↑Thu Feb 20, 2020 3:25 pm at Thu Feb 20, 2020 3:25 pm
>
> 
There will still be bug fixes, but yeah no new content unfortunately 
DFFNT was one of the 3 reasons I started this entire thing lol, I love NT.

Ah well. Maybe i'll make a private server when the servers go down in three years

Is that even possible? I read long time ago someone crack the game for play offline, but is hard to say that moving xxxxx files of the same size of the whole game to the Steam files is a real crack... but, maybe now that will chance because they don't have other way?

Yet, NT falls on the same place as Mobius...
Had to admit, but, I will love to play offline Mobius over NT.

But to end, who knows what future awaits to them? They can get forgotten or being remind as a crack game or private serves (maybe even with mods like 012).
On my case, it is kind sad, I was waiting they add more character or give the rest DLC like The Emperor of Heavens, Tidus and Jekkt 012 outfits, but all end on nothing, now.

RIP NT.
## Post #66
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-20T18:23:15+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Darkhowlings ↑Thu Feb 20, 2020 7:38 pm at Thu Feb 20, 2020 7:38 pm
>
> 
Yretenai wrote: ↑Thu Feb 20, 2020 3:25 pm
There will still be bug fixes, but yeah no new content unfortunately 
DFFNT was one of the 3 reasons I started this entire thing lol, I love NT.

Ah well. Maybe i'll make a private server when the servers go down in three years


Is that even possible? I read long time ago someone crack the game for play offline, but is hard to say that moving xxxxx files of the same size of the whole game to the Steam files is a real crack... but, maybe now that will chance because they don't have other way?

Yes, but the question is, is it worth it?
## Post #67
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-02-20T18:50:06+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Yretenai ↑Fri Feb 21, 2020 2:23 am at Fri Feb 21, 2020 2:23 am
>
> 
Yes, but the question is, is it worth it?

Obviusly no. For what I read, it was the same game and still use steam, but you cannot ask more from a cheap crack, if that is called a crack, once again.
## Post #68
- Username: EmptyMan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2016 2:22 am
- Post datetime: 2020-02-21T18:50:52+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hi, Joschka.
Thank you for the awesome script!
Can you add support for attached files (DQH2)?
I think, it's bgra8 format.
dxt1/dxt5 works fine.

> Extra Header found: Size 12, Version 16
>
> possible unknown format !
>
> Loaded Texture 1 of 7; 1024x1024; Format A; Size 400000; System B; Mips 1
>
> Unsupported DDS format: 0.
>
> WARNING: Constructing default image because data could not be decoded.
>
> Extra Header found: Size 12, Version 16
>
> possible unknown format !
>
> Loaded Texture 2 of 7; 64x64; Format A; Size 4000; System B; Mips 1
>
> Unsupported DDS format: 0.
>
> WARNING: Constructing default image because data could not be decoded.
>
> Extra Header found: Size 12, Version 16
>
> possible unknown format !
>
> Loaded Texture 3 of 7; 256x32; Format A; Size 8000; System B; Mips 1
>
> Unsupported DDS format: 0.
>
> WARNING: Constructing default image because data could not be decoded.
>
> Extra Header found: Size 12, Version 16
>
> possible unknown format !
>
> Loaded Texture 4 of 7; 32x64; Format A; Size 2000; System B; Mips 1
>
> Unsupported DDS format: 0.
>
> WARNING: Constructing default image because data could not be decoded.
[dqh.rar](https://xentaxbackup.github.io/file/17534_dqh.rar)
## Post #69
- Username: Sundownsyndrome
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 12, 2015 11:15 am
- Post datetime: 2020-02-22T00:22:06+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

hey man, this is some awesome work you managed to get down, and you've been pretty good with getting updates. i do, however, see one issue that i don't know that's been addressed, and that's sometimes models have a skeleton inside of their own G1M, rather than it being read from a specific one. you can check this out on Exdeath from dissidia where he has a wrist bangle hanging off his wrist, it's not rigged properly since some of the bones are actually inside of its own model.

i'm checking out berserk as well and, it works fine, but also has similar issues on specific models, like so:


the leg bone is out and it's deforming the hair. this isn't necessarily a rigging error. it's just there's another set of bone chains within the model's own G1M that has to be read, but because that didn't get extracted it's instead deforming off of the skeleton that i loaded in. if you think it's worth looking into, i'd appreciate it because i've seen it pop up a couple of times now. let me know if you need samples.
## Post #70
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-23T11:13:08+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Rainx ↑Sat Feb 22, 2020 2:50 am at Sat Feb 22, 2020 2:50 am
>
> 
Hi, Joschka.
Thank you for the awesome script!
Can you add support for attached files (DQH2)?
I think, it's bgra8 format.

Oh never saw that ID before, I took a quick look at these using the texture cooker and it seems to be bgr8 indeed.
 
I'll add support for it when I'll start working on it again, taking a few days break from RE rn.

> Reply from Sundownsyndrome ↑Sat Feb 22, 2020 8:22 am at Sat Feb 22, 2020 8:22 am
>
> 
hey man, this is some awesome work you managed to get down, and you've been pretty good with getting updates. i do, however, see one issue that i don't know that's been addressed, and that's sometimes models have a skeleton inside of their own G1M, rather than it being read from a specific one. you can check this out on Exdeath from dissidia where he has a wrist bangle hanging off his wrist, it's not rigged properly since some of the bones are actually inside of its own model.

i'm checking out berserk as well and, it works fine, but also has similar issues on specific models, like so:

the leg bone is out and it's deforming the hair. this isn't necessarily a rigging error. it's just there's another set of bone chains within the model's own G1M that has to be read, but because that didn't get extracted it's instead deforming off of the skeleton that i loaded in. if you think it's worth looking into, i'd appreciate it because i've seen it pop up a couple of times now. let me know if you need samples.

Hmm interesting, you mean that I'd need to read both the external and the internal skeleton section for these ? I never saw that before, only saw models with full skeleton located in an external g1m or with the skeleton contained inside their own g1m (in this case either select the same g1m file or turn off bautoLoadG1MS and bLoadG1MS). I'll take a look at Exdeath's model and keep you updated, probably during next week or something like that.
## Post #71
- Username: Sundownsyndrome
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 12, 2015 11:15 am
- Post datetime: 2020-02-23T16:20:48+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

that's my assumption from daemon's tools when i worked with it. sephiroth similarly does this. for the record, i did try both ways, but it was spitting out an out of bounds error. it could be differently handled for all i know. but thank you regardless.

as an aside, is getting proper vertex normals for cloth physic meshes on the list, just low priority? if it is, that's fine, just curious is all
## Post #72
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-23T23:44:01+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Sundownsyndrome ↑Mon Feb 24, 2020 12:20 am at Mon Feb 24, 2020 12:20 am
>
> 
that's my assumption from daemon's tools when i worked with it. sephiroth similarly does this. for the record, i did try both ways, but it was spitting out an out of bounds error. it could be differently handled for all i know. but thank you regardless.

as an aside, is getting proper vertex normals for cloth physic meshes on the list, just low priority? if it is, that's fine, just curious is all

Ah I see, I must have missed something then, I'll take a look at these.
Oh lol, I just wasn"t aware of the issue, I'll fix that too then.
## Post #73
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-26T13:35:11+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

SCRIPT UPDATED

-I added formats 0x9 and 0xA for G1T files. Let me know if there are some issues with 0x9, I only had one sample so some channels might be wrong.
-Yretenai started adding KHM support. These are heightmaps used in some games for terrains


> Reply from Rainx ↑Sat Feb 22, 2020 2:50 am at Sat Feb 22, 2020 2:50 am
>
> 
Can you add support for attached files (DQH2)?

These files should now display correctly, let me know if you find some issues. 

> Reply from Sundownsyndrome ↑Mon Feb 24, 2020 12:20 am at Mon Feb 24, 2020 12:20 am
>
> 
that's my assumption from daemon's tools when i worked with it. sephiroth similarly does this. for the record, i did try both ways, but it was spitting out an out of bounds error.

Ok I looked into this and it's not skeleton related. There are very few bones sometimes in the model g1m indeed but their position don't match the cloth at all so they must be here for other purposes (sockets or something else maybe).

Now for your issue. Basically there are two types of cloth in KT games : 
-cloth type 1 : these have NUN sections associated to them and the necessary info to construct and simulate them are in these sections.
-cloth type 2 : these are little meshes (usually "dangling" parts) that have to be reconstructed in a different way. They are simulated in a different way with the swing physics engine and the necessary info for that is most likely in the swg file. If you're familiar with UE4, these are somewhat like animDynamics/rigidBodies
[https://docs.unrealengine.com/en-US/Eng ... index.html](https://docs.unrealengine.com/en-US/Engine/Animation/NodeReference/SkeletalControls/AnimDynamics/index.html)
[https://docs.unrealengine.com/en-US/Eng ... index.html](https://docs.unrealengine.com/en-US/Engine/Animation/NodeReference/SkeletalControls/RigidBody/index.html)

They have weights and bone indexes sometimes but these don't match the correct bone at all most of the time and it leads to completely deformed meshes. My assumption is that the weight and bone index buffers are used differently for them (like some channels used completely differently for NUN cloth meshes). I wanted to put them to 0 like I did with NUN meshes but it turns out that they sometimes work with the base armature : [https://github.com/Joschuka/fmt_g1m/issues/6](https://github.com/Joschuka/fmt_g1m/issues/6)

So yeah you'd better export these and put all weights to 0 in your 3D software and then use physics sim/rerig the parts to accurately animate them. Since it seems to be all physics related I can't do much about it.
You can check this answer I gave to some user who had the same issue with Tifa for a more visual explanation [https://github.com/Joschuka/fmt_g1m/iss ... -584847119](https://github.com/Joschuka/fmt_g1m/issues/7#issuecomment-584847119)

However if you find out that Daemon's tool deforms them correctly or has additional bones for these let me know, that'd mean I missed something. But I think our outputs match for these kinds of models.
## Post #74
- Username: Sundownsyndrome
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 12, 2015 11:15 am
- Post datetime: 2020-02-26T15:10:04+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

yeah, daemon's script was able to spit out bones with weights, the caveat was basically we had to only drag and drop the model G1M itself onto the tool, rather than the skeleton G1M and model G1M. that's really where my assumption came in to begin with.

here's an example:


and it deforming:


the other caveat was that the skeleton or mesh had to be manually repositioned since these didn't get correctly placed, but cloth also did this on occasion.
## Post #75
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-26T17:39:56+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

All right looks like I was quite wrong about this cloth type indeed, thanks for pointing that out. 
I actually tried to only drag the g1m on daemon's tool but the ascii crashed on Noesis because of missing bones referenced by the vertices whereas you probably imported the ascii directly into Blender, so I completely missed that.
Going to see if I can find a way to put all of them at once, since there are overlapping local indices I'll need to find a good way to put all of them. I'll try to place them correctly too. I'll keep you updated.

Could you send me a few Berserk samples with the same issue for testing ?
## Post #76
- Username: EmptyMan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2016 2:22 am
- Post datetime: 2020-02-27T12:05:26+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Feb 26, 2020 9:35 pm at Wed Feb 26, 2020 9:35 pm
>
> 
These files should now display correctly, let me know if you find some issues.
Yeah, thanks!
I've attached more samples.
It looks like bc5.
[new.rar](https://xentaxbackup.github.io/file/17571_new.rar)
## Post #77
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-27T13:13:22+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Rainx ↑Thu Feb 27, 2020 8:05 pm at Thu Feb 27, 2020 8:05 pm
>
> 
It looks like bc5.

BC5_Unorm for those indeed, updated the script to support them.
## Post #78
- Username: Sundownsyndrome
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 12, 2015 11:15 am
- Post datetime: 2020-02-28T00:55:45+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

forgive my punctuality, here:
[http://www.mediafire.com/file/a9ggqhyc0 ... M.rar/file](http://www.mediafire.com/file/a9ggqhyc0ikc5wj/Griffith_G1M.rar/file)

i haven't seen others, albeit out of too big of a sample size. i also included one other model which was not opening oddly enough, but the other two have the same issue.
## Post #79
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-28T17:02:13+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

SCRIPT UPDATED

-Added Cloth type 2 bone support. As of now when selecting an external skeleton, the base g1m's G1MS section will be parsed to check if there are any physics bones in it. If found, the latter will be extracted, correctly placed and parented accordingly to the main armature. Weights will also be adjusted too. These bones will have the "Cloth" keyword in their name.

I didn't try animations yet but I don't expect them to be animated by an animator, the bones are probably used by the physics engine. If you don't see any motion for these when loading a g1a/g2a then that's the reason why.
Most of the time these meshes are hair strands/little dangling accessories.


-Yretenai made a big update to her tools. If you work on a game with all the character textures separated in several g1t files with a unique texture in it (DOA6 and P5S), you can use these to combine all the textures back into a single g1t file and then use that file with the script to place them directly on the model. Refer to her last post for instructions : [viewtopic.php?f=10&t=21679&start=45#p160417](https://forum.xentax.com/viewtopic.php?f=10&t=21679&start=45#p160417)


> Reply from Sundownsyndrome ↑Fri Feb 28, 2020 8:55 am at Fri Feb 28, 2020 8:55 am
>
> 
I also included one other model which was not opening oddly enough, but the other two have the same issue.

i fixed the issue for the non working model. Cloth bones are also computed correctly now. Let me know if you find some issue
## Post #80
- Username: PRP1986
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Mar 26, 2018 1:18 am
- Post datetime: 2020-02-28T23:49:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Feb 05, 2020 3:40 am at Wed Feb 05, 2020 3:40 am
>
> 
Allanoon wrote: ↑Wed Feb 05, 2020 3:12 am
Joschka wrote: ↑Wed Feb 05, 2020 1:58 am
Script updated

-KSLT support. You can now open and preview these files. These are UI textures.
-G2A version 0200 and 0300 Big endian should now work. I didn't have many samples so tell me if you have any issue with these.
-My partner Yretenai added Nioh support to her Cethleann tools, you can now extract models and animations from this game. HOWEVER the script as it currently is will take some time to load the models so be patient if you want to preview the models right now. I plan to rework some parts to speed things up.


Unfortunately regarding G2A animations, i'm still getting the exact same error of my previous post. I can send more samples if you need tou.


Hmm weird, I can extract the Fist of the North Star 2 animations you gave me fine 



Couldn't try with Kagero ones because the skeleton was not compatible with the anims but I didn't have errors during parsing.
Yes, feel free to send me some non working samples so I can take a look.
Allanoon wrote: ↑Wed Feb 05, 2020 3:12 am
the script is working fine with Attack on Titans 1 (2 too most likely), Dragon Quest heroes 2 (pc) and Trinity: souls of zill'o II (ps3)

Oh nice, as a big Dragon quest fan I wanted to see if that worked with DQH2, there are some really nice models in that game for many great characters of the series

Sorry to quote an old post, but could I ask how you were able to obtain the anims for Fist of The North Star 2. I have unpacked the Linkdata files using a bms script, however the models and animations are bin format, which I assume is a container file with multiple files within. If you don't mind me asking, which tool did you use to unpack the bin file?
## Post #81
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-02-29T00:12:38+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from PRP1986 ↑Sat Feb 29, 2020 7:49 am at Sat Feb 29, 2020 7:49 am
>
> 
Sorry to quote an old post, but could I ask how you were able to obtain the anims for Fist of The North Star 2. I have unpacked the Linkdata files using a bms script, however the models and animations are bin format, which I assume is a container file with multiple files within. If you don't mind me asking, which tool did you use to unpack the bin file?

Try renaming .bin to .g1m or .g1t, or drag the bin files into Cethleann.Unbundler. See link in my signature.
## Post #82
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-02-29T09:39:22+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from PRP1986 ↑Sat Feb 29, 2020 7:49 am at Sat Feb 29, 2020 7:49 am
>
> 
Sorry to quote an old post, but could I ask how you were able to obtain the anims for Fist of The North Star 2. I have unpacked the Linkdata files using a bms script, however the models and animations are bin format, which I assume is a container file with multiple files within. If you don't mind me asking, which tool did you use to unpack the bin file?

The animations are samples given to me by Allanoon, I don't have a full dump myself. 

Yretenai's tools won't work on that game since it's big endian. He probably used Steven's gas machine to extract the game, you should try that.
## Post #83
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-29T10:00:04+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Fist of The North Star 2's use zlib compression.
you need use offzip

offzip -a -1 *.bin

Then, split G1M,G1T and G1A(G2A) as needed.
## Post #84
- Username: PRP1986
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Mar 26, 2018 1:18 am
- Post datetime: 2020-02-29T18:28:27+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Thanks all, I have tried the above methods, with no luck unfortunately, though most likely it is something I am doing! I tried with Steven's Gas Machine using various game profiles (as there isn't a profile for Fist of The North Star), but was only able to get texture files from the LINKDATA files. I also tried the offzip method but just get .dat files.

Anyway I won't keep hijacking the thread, thanks again
## Post #85
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-29T19:19:16+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from PRP1986 ↑Sun Mar 01, 2020 2:28 am at Sun Mar 01, 2020 2:28 am
>
> 
Thanks all, I have tried the above methods, with no luck unfortunately, though most likely it is something I am doing! I tried with Steven's Gas Machine using various game profiles (as there isn't a profile for Fist of The North Star), but was only able to get texture files from the LINKDATA files. I also tried the offzip method but just get .dat files.

Anyway I won't keep hijacking the thread, thanks again
[viewtopic.php?p=82156#p82156](https://forum.xentax.com/viewtopic.php?p=82156#p82156)

LINKDATA in Fist of the North Star Ken's Rage 2 has different specifications than other games.
Use the bms script created by chrrox. Also, the files that can be obtained with XBOX360 and PS3 are different.
Either way, not all data can be obtained. Some files are corrupted and can be between 1KB and 2KB.
However, all of the main files are available without problems.

And yes, uncompress * .bin with offzip to * .dat. These include models, textures, and animations.
By splitting the file from the data header, you can get the file properly.
## Post #86
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-01T15:33:55+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Sundownsyndrome ↑Mon Feb 24, 2020 12:20 am at Mon Feb 24, 2020 12:20 am
>
> 
as an aside, is getting proper vertex normals for cloth physic meshes on the list, just low priority? if it is, that's fine, just curious is all

I pushed a fix to let Noesis auto compute the normals for NUN meshes, it won't be perfect but it'll be much better already. As of now I can't find a way to compute these correctly using the base values
If you find a tool that computes them correctly though let me know, I'll probably be able to use that as reference. But I think neither Semory or Daemon get these correctly either
## Post #87
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-03-02T11:12:11+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from PRP1986 ↑Sun Mar 01, 2020 2:28 am at Sun Mar 01, 2020 2:28 am
>
> 
Thanks all, I have tried the above methods, with no luck unfortunately, though most likely it is something I am doing! I tried with Steven's Gas Machine using various game profiles (as there isn't a profile for Fist of The North Star), but was only able to get texture files from the LINKDATA files. I also tried the offzip method but just get .dat files.

Anyway I won't keep hijacking the thread, thanks again
[http://www.mediafire.com/file/8ne700n3l ... 2.rar/file](http://www.mediafire.com/file/8ne700n3lognm5y/Fist_of_North_Star_2.rar/file)

Here are the files i used.
NS2.bms is chrrox script to decrypt the files (MUST BE PS3, XBOX360 are a mess).
Then there's the python script (can't remember where i found it), you need it to decrypt files that have KTZ0 header (like models/anim).
Trim Header, is a powershell script to mass trim the textures header so they can be easily readable on noesis (edit it first).
The XML files are for VGMtoolbox to mass extract G1M/G2A files from the new .bin files that you get with the python script, put them into plugins/AdvanceCutter folder and load them.

On another note Warriors Legend of Troy (2011!) works with the script.
The file are in .cpkg .mpkg format
[viewtopic.php?f=16&t=6252](https://forum.xentax.com/viewtopic.php?f=16&t=6252) thanks to chrrox   
Once you've the big .dat file you can use VGMtoolbox or w/e to extract .g1m .g1t .g1a files.

OT: A pity that Ninja Gaidens use a different format. 
Also, does anyone got a better Koei game list than the one on Wikipedia? It's out of date; missing games like Persona 4/5 or Dragon Quest Builders. I'm kinda out of games to check, if any, ahah.
## Post #88
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-03T22:07:42+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Mon Mar 02, 2020 7:12 pm at Mon Mar 02, 2020 7:12 pm
>
> 
On another note Warriors Legend of Troy (2011!) works with the script.

It's actually quite crazy how they've been milking that file format. They have been some changes, especially for the cloth meshes, but most of it stayed the same during all these years.

> Reply from Allanoon ↑Mon Mar 02, 2020 7:12 pm at Mon Mar 02, 2020 7:12 pm
>
> 
Also, does anyone got a better Koei game list than the one on Wikipedia? It's out of date; missing games like Persona 4/5 or Dragon Quest Builders. I'm kinda out of games to check, if any, ahah.

Let me know if you find one please, I actually quickly looked for something like that too recently but couldn't find a better one.
## Post #89
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-03-06T00:14:08+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

An "update" Regarding Nioh CE...
I opened the PS4 pkg and... surprise surprise, files aren't packed in there!
They're all nicely ordered in named folders which have .g1t files and .pg2a .pg1m files (easily extractable with Cethleann.Unbundler). Everything seems to work fine (i'll check later....). 
So unless Yretenai have some personal reason i think finding the xor for PC archive01 is "useless" at this point  

> Reply from Joschka ↑Wed Mar 04, 2020 6:07 am at Wed Mar 04, 2020 6:07 am
>
> 
Let me know if you find one please, I actually quickly looked for something like that too recently but couldn't find a better one.

Maybe on koei fandom but even there titles seems to be missing, i also didn't notice that Personas are from Atlus while DQ builders is Square Enix despite using the same engine of many Koei games. Maybe there're some more lost in other company xD
## Post #90
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-03-07T01:47:04+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Fri Mar 06, 2020 8:14 am at Fri Mar 06, 2020 8:14 am
>
> 
An "update" Regarding Nioh CE...
I opened the PS4 pkg and... surprise surprise, files aren't packed in there!
They're all nicely ordered in named folders which have .g1t files and .pg2a .pg1m files (easily extractable with Cethleann.Unbundler). Everything seems to work fine (i'll check later....). 
So unless Yretenai have some personal reason i think finding the xor for PC archive01 is "useless" at this point  
Joschka wrote: ↑Wed Mar 04, 2020 6:07 am
Let me know if you find one please, I actually quickly looked for something like that too recently but couldn't find a better one.


Maybe on koei fandom but even there titles seems to be missing, i also didn't notice that Personas are from Atlus while DQ builders is Square Enix despite using the same engine of many Koei games. Maybe there're some more lost in other company xD

It was the right answer to focus on the PS4 version. Thanks for your discovery, Allanoon.

pg1m and pg2a seem to be concatenated files with pack headers at the beginning. Even if Cethleann.Unbundler does not work, it is possible to play without problems by dividing by M1G or A2G.

pg1m contains some g1m, but some seem to have invalid weights. However, the weight was loaded without any problem by selecting another g1m that was in the same pack.

I hope Nioh 2 can get the files in the same way...
## Post #91
- Username: icoee
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 31, 2018 3:50 pm
- Post datetime: 2020-03-08T09:29:02+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Thanks for your script. But when I try to export the PC00B g1m file from Atelier Ryza, get an error:  WARNING: Weight contains an out of range bone index. Discarding model.   Please help!!!

Here is the file:  [https://mega.nz/#!89wykQwB!vi0v9NTKKmHv ... u6cNX-Kf4Y](https://mega.nz/#!89wykQwB!vi0v9NTKKmHvi81KMAg9McOfb4k47wMjwu6cNX-Kf4Y)
## Post #92
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-08T12:52:03+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Allanoon ↑Fri Mar 06, 2020 8:14 am at Fri Mar 06, 2020 8:14 am
>
> 
...

> Reply from einherjar007 ↑Sat Mar 07, 2020 9:47 am at Sat Mar 07, 2020 9:47 am
>
> 
...
Great news, thanks for testing ! I'll try to make the optimization I talked about before to make the script run faster this week, the few Nioh samples I tried took quite a bit of time to load.

> Reply from Allanoon ↑Fri Mar 06, 2020 8:14 am at Fri Mar 06, 2020 8:14 am
>
> 
Maybe on koei fandom but even there titles seems to be missing, i also didn't notice that Personas are from Atlus while DQ builders is Square Enix despite using the same engine of many Koei games. Maybe there're some more lost in other company xD
Yep basically KT do their own games but also work with other studios sometimes, for example Hyrule Warriors and Fire Emblem for Nintendo and the others you mentionned.  I actually had no idea that they made DQB2 before you mentionned it for example, thought the game was made by Square internally. 
I think the best thing to do would just be to edit that wikipedia list at that point, it has most of the titles already.

> Reply from icoee ↑Sun Mar 08, 2020 5:29 pm at Sun Mar 08, 2020 5:29 pm
>
> 
Thanks for your script. But when I try to export the PC00B g1m file from Atelier Ryza, get an error:  WARNING: Weight contains an out of range bone index. Discarding model.   Please help!!!

Here is the file:  https://mega.nz/#!89wykQwB!vi0v9NTKKmHv ... u6cNX-Kf4Y

Your model had some cloth type 2 with the new physics bones I implemented for Dissidia in the last updates. But I didn't know these meshes could have bone indices to the main armature too, which was the case in your model. I pushed a fix for that, should now work as expected.
## Post #93
- Username: icoee
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 31, 2018 3:50 pm
- Post datetime: 2020-03-08T18:13:27+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Mar 08, 2020 8:52 pm at Sun Mar 08, 2020 8:52 pm
>
> 
Allanoon wrote: ↑Fri Mar 06, 2020 8:14 am
...

einherjar007 wrote: ↑Sat Mar 07, 2020 9:47 am
...

Great news, thanks for testing ! I'll try to make the optimization I talked about before to make the script run faster this week, the few Nioh samples I tried took quite a bit of time to load.
Allanoon wrote: ↑Fri Mar 06, 2020 8:14 am
Maybe on koei fandom but even there titles seems to be missing, i also didn't notice that Personas are from Atlus while DQ builders is Square Enix despite using the same engine of many Koei games. Maybe there're some more lost in other company xD

Yep basically KT do their own games but also work with other studios sometimes, for example Hyrule Warriors and Fire Emblem for Nintendo and the others you mentionned.  I actually had no idea that they made DQB2 before you mentionned it for example, thought the game was made by Square internally. 
I think the best thing to do would just be to edit that wikipedia list at that point, it has most of the titles already.
icoee wrote: ↑Sun Mar 08, 2020 5:29 pm
Thanks for your script. But when I try to export the PC00B g1m file from Atelier Ryza, get an error:  WARNING: Weight contains an out of range bone index. Discarding model.   Please help!!!

Here is the file:  https://mega.nz/#!89wykQwB!vi0v9NTKKmHv ... u6cNX-Kf4Y


Your model had some cloth type 2 with the new physics bones I implemented for Dissidia in the last updates. But I didn't know these meshes could have bone indices to the main armature too, which was the case in your model. I pushed a fix for that, should now work as expected.

It works!!  Thanks very much!
But now I found a ploblem for the hair of other model after export.

Here is the file : [https://mega.nz/#!hlYG2aba!oKr4O4ARw1fa ... T5-Fr3-h4c](https://mega.nz/#!hlYG2aba!oKr4O4ARw1fahwT0FfEiJFvkMvaXkwNvZT5-Fr3-h4c)
[MY1(X`%%KAGVGDJRW~@K3}V.jpg](https://xentaxbackup.github.io/file/17654_MY1(X`%%KAGVGDJRW~@K3}V.jpg)
## Post #94
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2020-03-08T21:10:41+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Excellent work guys! Will be sure to try it out! I see you guys actually figured out what the vertex shader was doing rather than trying to just interpret the byte code like I did   .
## Post #95
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-09T01:07:44+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from howfie ↑Mon Mar 09, 2020 5:10 am at Mon Mar 09, 2020 5:10 am
>
> 
Excellent work guys! Will be sure to try it out! I see you guys actually figured out what the vertex shader was doing rather than trying to just interpret the byte code like I did   .

There's still a bit to go, normals are re-generated in the vertex shader in newer versions. It's causing a bit of a headache, but we're back to interpreting bytecode
## Post #96
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-03-09T10:18:06+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

edit:
there was a problem here, it's gone now
## Post #97
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-09T12:00:56+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from icoee ↑Mon Mar 09, 2020 2:13 am at Mon Mar 09, 2020 2:13 am
>
> 
It works!!  Thanks very much!
But now I found a ploblem for the hair of other model after export.

Looks like your were unlucky enough to find the 3rd NUN mesh that doesn't work among the hundred others that work fine. I guess that my cloth computation must be slightly off somewhere, fixing that in non trivial unfortunately and I don't want to do some hack that could break other models so better wait for us to update the equations when we'll add proper normal support for the cloth meshes.

> Reply from howfie ↑Mon Mar 09, 2020 5:10 am at Mon Mar 09, 2020 5:10 am
>
> 
Excellent work guys! Will be sure to try it out!

The gas machine man himself ! Really glad to see you here Semory ! :D
As mentionned in the credits all of this wouldn't have been possible without your gas machine source code as a basis, thanks a ton for your hard work on these formats ! (as you can see they're still milking their engine with only a few changes...)

> Reply from howfie ↑Mon Mar 09, 2020 5:10 am at Mon Mar 09, 2020 5:10 am
>
> 
 I see you guys actually figured out what the vertex shader was doing rather than trying to just interpret the byte code like I did  :mrgreen: .
Oh don't worry we still have almost no clue about what's actually happening, the shader code has just been converted to a more compact form hehe
I did find similar ideas with the control points and all in APEX clothing but I think they did their own solution. I'll probably look a bit more into it soon now that most bugs are solved, as you can see above there are still some rare cases where it gives some weird results.

What we have so far is that there's a computation of the center of mass of the 4 closest control points using the 4 components of the 4D vertices of the cloth meshes as weights for each one (done in what I've called processClothVertex).  Then these centers of mass are themselves used in another weighted sum to get a final vector (so the center of mass of the center of masses) This is repeated 3 times to get all the vectors (d4,d5,d6)
Then these vectors are used in a scalar triple product and the resulting values are fed to the vector components of the position vector
## Post #98
- Username: icoee
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 31, 2018 3:50 pm
- Post datetime: 2020-03-09T14:21:52+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Mon Mar 09, 2020 8:00 pm at Mon Mar 09, 2020 8:00 pm
>
> 
Looks like your were unlucky enough to find the 3rd NUN mesh that doesn't work among the hundred others that work fine. I guess that my cloth computation must be slightly off somewhere, fixing that in non trivial unfortunately and I don't want to do some hack that could break other models so better wait for us to update the equations when we'll add proper normal support for the cloth meshes.

Ok, I get it now, thanks!
## Post #99
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-09T19:46:42+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from icoee ↑Mon Mar 09, 2020 10:21 pm at Mon Mar 09, 2020 10:21 pm
>
> 
Joschka wrote: ↑Mon Mar 09, 2020 8:00 pm
Looks like your were unlucky enough to find the 3rd NUN mesh that doesn't work among the hundred others that work fine. I guess that my cloth computation must be slightly off somewhere, fixing that in non trivial unfortunately and I don't want to do some hack that could break other models so better wait for us to update the equations when we'll add proper normal support for the cloth meshes.


Ok, I get it now, thanks!

This custom script will fix your model, normals are not computed correctly though but this is easier to fix in a 3d software. Only use it for that model, it's just a quick and dirty hack until a proper fix.

[fmt_g1m_PCOOD.zip](https://xentaxbackup.github.io/file/17664_fmt_g1m_PCOOD.zip)
## Post #100
- Username: icoee
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 31, 2018 3:50 pm
- Post datetime: 2020-03-10T11:43:49+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Tue Mar 10, 2020 3:46 am at Tue Mar 10, 2020 3:46 am
>
> 
This custom script will fix your model, normals are not computed correctly though but this is easier to fix in a 3d software. Only use it for that model, it's just a quick and dirty hack until a proper fix.

It's awesome!! Thank you so much!!!
## Post #101
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-10T13:02:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Pushed a quick fix for BE models. Fatal Frame models should now be fully supported, with cloth meshes fixed.
Still have no immediate plans for texture support since it's the only one using Wiiu swizzle, don't really want to implement that for just one game.
## Post #102
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-03-11T08:24:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hi, i try open Noesis and see this error, maybe you can help me
[image.png](https://xentaxbackup.github.io/file/17687_image.png)
## Post #103
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-11T12:42:29+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Crazy31139 ↑Wed Mar 11, 2020 4:24 pm at Wed Mar 11, 2020 4:24 pm
>
> 
Hi, i try open Noesis and see this error, maybe you can help me
[viewtopic.php?f=16&t=21666#p159400](https://forum.xentax.com/viewtopic.php?f=16&t=21666#p159400)
## Post #104
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-11T14:59:49+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from icoee ↑Tue Mar 10, 2020 7:43 pm at Tue Mar 10, 2020 7:43 pm
>
> 
It's awesome!! Thank you so much!!!

I did more research and pushed a universal fix for that so you won't need the custom script anymore, just download the latest version and you should be good. Thank you for the bug report, made me aware of that error.
Just need to fix the normals properly and I think the script will be pretty much complete. After that I'll be able to focus on optimization.

All the models should now import correctly for all games, cloth/hair meshes included.
## Post #105
- Username: shenglong
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 04, 2019 3:18 pm
- Post datetime: 2020-03-17T10:56:23+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hello, thank you very much for sharing such an excellent tool. 

I'm also analyzing G1M files, so I'd like to ask you some questions about the G1M file format: 

1.What is the structure of the G1M file? (PC platform file). 

2.The vertex data at the beginning of the 0x04000100 mark in the GM1G4400 block contains vertex structures described as 0x7C size. I guess these structures are cloth physical meshes, because I can't extract mesh data correctly, they always appear as flat meshes. How can I correctly analyze these data? 

3.What is the structure of ONUN8200 and VNUN1100 blocks? 

The above questions have perplexed me for a long time. I hope to get your answer. Thank you again!
## Post #106
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-17T17:55:42+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from shenglong ↑Tue Mar 17, 2020 6:56 pm at Tue Mar 17, 2020 6:56 pm
>
> 
1.What is the structure of the G1M file? (PC platform file).

G1MS : Skeleton info
G1MF : Some info about number of submeshes and other details about the sections in the file. I don't use it to reconstruct models
G1MM : Bone matrices, I don't use this section either
G1MG : Geometry and platform info, divided in 9 subsections
NUNO/NUNV/NUNS : cloth/hair meshes data used for physics sim
SOFT : same for breast (I don't use it)
COLL : We assume it's for collision shapes used to collide with the cloth driver nodes
HAIR: No clue yet, name seems obvious but that chunk was always empty in the models we saw
EXTR : No clue either yet, it's empty 99% of the time, we only saw a few models with that chunk used

> Reply from shenglong ↑Tue Mar 17, 2020 6:56 pm at Tue Mar 17, 2020 6:56 pm
>
> 
2.The vertex data at the beginning of the 0x04000100 mark in the GM1G4400 block contains vertex structures described as 0x7C size.
I don't see what you're referring to here

> Reply from shenglong ↑Tue Mar 17, 2020 6:56 pm at Tue Mar 17, 2020 6:56 pm
>
> 
 I guess these structures are cloth physical meshes, because I can't extract mesh data correctly, they always appear as flat meshes. How can I correctly analyze these data?
The meshes are extracted correctly but then ingame the vertices' final position are computed by a vertex shader, that's what you're missing. It goes like : cloth mesh vertices lying on the ground -> driver nodes are used by the physics sim -> vertices are reconstructed thanks to these nodes by the vertex shader. The nodes' position are in the NUN sections

> Reply from shenglong ↑Tue Mar 17, 2020 6:56 pm at Tue Mar 17, 2020 6:56 pm
>
> 
3.What is the structure of ONUN8200 and VNUN1100 blocks?
I think it's quicker to just check our binary templates, you'll have all the info that you need. You can check my script code too to see how I parse these sections.
[https://github.com/three-houses-researc ... ormats/G1M](https://github.com/three-houses-research-team/010-binary-templates/tree/master/Model%20related%20formats/G1M)

> Reply from shenglong ↑Tue Mar 17, 2020 6:56 pm at Tue Mar 17, 2020 6:56 pm
>
> 
The above questions have perplexed me for a long time. I hope to get your answer. Thank you again!

Hopefully the above info helped, let me know if you have more questions after checking these resources.
## Post #107
- Username: shenglong
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 04, 2019 3:18 pm
- Post datetime: 2020-03-18T09:04:06+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Thank you very much for your answer. This knowledge is very helpful to me.
## Post #108
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-03-19T16:46:41+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Dynasty Warriors Online (Sangoku Musou Online Z) seems to use the same file format.

Texture and weapon models appear to be load, but other models can't.
Upload a sample. of course provide more files as needed.
[sangokuZ.zip](https://xentaxbackup.github.io/file/17742_sangokuZ.zip)
## Post #109
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-03-20T01:00:26+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

There's some models that get the "List index out of range" from some of the dragon quest heroes 2
## Post #110
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-03-20T16:10:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Mar 18, 2020 1:55 am at Wed Mar 18, 2020 1:55 am
>
> 
G1MS : Skeleton info
G1MF : Some info about number of submeshes and other details about the sections in the file. I don't use it to reconstruct models
G1MM : Bone matrices, I don't use this section either
G1MG : Geometry and platform info, divided in 9 subsections
NUNO/NUNV/NUNS : cloth/hair meshes data used for physics sim
SOFT : same for breast (I don't use it)
COLL : We assume it's for collision shapes used to collide with the cloth driver nodes
HAIR: No clue yet, name seems obvious but that chunk was always empty in the models we saw
EXTR : No clue either yet, it's empty 99% of the time, we only saw a few models with that chunk used

Specifically:

G1MS: Skeleton
G1MF: Format
G1MM: Matrix
G1MG: Geometry
NUNO: Cloth (in Japanese)
NUNS: Cloth Skeleton
NUNV: ClothViz
SOFT: Softbody Dot Matrix
COLL: Collision
HAIR: Hair Strand Matrix
EXTR: Varies per game
## Post #111
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-20T20:24:00+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Script updated

NUNS support added. So far I only saw it on Spiritus and on one Noctis skin in DFFNT. It's similar to NUNO/NUNV but the associated control points overlap existing bones from the base skeleton. Anyways it's now there, it'll help for cloth sim if people want to use these particular models.

> Reply from einherjar007 ↑Fri Mar 20, 2020 12:46 am at Fri Mar 20, 2020 12:46 am
>
> 
Dynasty Warriors Online (Sangoku Musou Online Z) seems to use the same file format.
Texture and weapon models appear to be load, but other models can't.
Upload a sample. of course provide more files as needed.
The geometry section used an old version I never saw before so there were some little differences. It should now work as expected, let me know if you find more models with some issues since I only adapted the script based on what I saw on these two, there may be other sections using older versions in that game.

> Reply from Enkidu115 ↑Fri Mar 20, 2020 9:00 am at Fri Mar 20, 2020 9:00 am
>
> 
There's some models that get the "List index out of range" from some of the dragon quest heroes 2
Samples ?
## Post #112
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-03-21T00:58:11+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sat Mar 21, 2020 4:24 am at Sat Mar 21, 2020 4:24 am
>
> 
einherjar007 wrote: ↑Fri Mar 20, 2020 12:46 am
Dynasty Warriors Online (Sangoku Musou Online Z) seems to use the same file format.
Texture and weapon models appear to be load, but other models can't.
Upload a sample. of course provide more files as needed.

The geometry section used an old version I never saw before so there were some little differences. It should now work as expected, let me know if you find more models with some issues since I only adapted the script based on what I saw on these two, there may be other sections using older versions in that game.

Thanks update, it works!
I'll Perform more tests and report if issues found.

*character model location
LoadData\0006\od\on\ge200\

*animation data location
LoadData\0007\ot****.bin

need to change the extension. Also, split g1a because it is linked.
If anyone interested in this work, please refer to it
## Post #113
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-03-21T02:14:30+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sat Mar 21, 2020 4:24 am at Sat Mar 21, 2020 4:24 am
>
> 
Script updated

NUNS support added. So far I only saw it on Spiritus and on one Noctis skin in DFFNT. It's similar to NUNO/NUNV but the associated control points overlap existing bones from the base skeleton. Anyways it's now there, it'll help for cloth sim if people want to use these particular models.
einherjar007 wrote: ↑Fri Mar 20, 2020 12:46 am
Dynasty Warriors Online (Sangoku Musou Online Z) seems to use the same file format.
Texture and weapon models appear to be load, but other models can't.
Upload a sample. of course provide more files as needed.

The geometry section used an old version I never saw before so there were some little differences. It should now work as expected, let me know if you find more models with some issues since I only adapted the script based on what I saw on these two, there may be other sections using older versions in that game.
Enkidu115 wrote: ↑Fri Mar 20, 2020 9:00 am
There's some models that get the "List index out of range" from some of the dragon quest heroes 2

Samples ?

do you just want the g1m and g1t or the whole character folder?
## Post #114
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-21T09:17:38+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Enkidu115 ↑Sat Mar 21, 2020 10:14 am at Sat Mar 21, 2020 10:14 am
>
> 
do you just want the g1m and g1t or the whole character folder?

Send me the whole folders for a few non working characters with that error, that should be enough
## Post #115
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-03-21T10:21:19+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sat Mar 21, 2020 5:17 pm at Sat Mar 21, 2020 5:17 pm
>
> 
Enkidu115 wrote: ↑Sat Mar 21, 2020 10:14 am
do you just want the g1m and g1t or the whole character folder?


Send me the whole folders for a few non working characters with that error, that should be enough
[https://drive.google.com/file/d/1V-VAS_ ... sp=sharing](https://drive.google.com/file/d/1V-VAS_pP6mJUahDsNRRfblE_lpNeOUnB/view?usp=sharing)
## Post #116
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-21T12:16:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Enkidu115 ↑Sat Mar 21, 2020 6:21 pm at Sat Mar 21, 2020 6:21 pm
>
> 
Joschka wrote: ↑Sat Mar 21, 2020 5:17 pm
Enkidu115 wrote: ↑Sat Mar 21, 2020 10:14 am
do you just want the g1m and g1t or the whole character folder?


Send me the whole folders for a few non working characters with that error, that should be enough

https://drive.google.com/file/d/1V-VAS_ ... sp=sharing

Works fine for me 

Also there was a bunch of stuff not in the game by default in your folder, I assume it was the output of daemon's tools on your g1m
## Post #117
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-21T12:57:20+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

A few people asked me about this so I'd like to make a quick tutorial about the issue. As you know right now the model merger doesn't work with animations, unless you choose not to merge bones. This leads to a lot of duplicate bones and it's annoying to fix. Here's a possible workflow that I use to get around it :

-Make sure that the model merger option at the top of the merge.py is set to 1. Merge the models you want to without selecting any animation. Here I merged Edelgard's head and body meshes (I didn't bother with textures). The bones are correctly merged and you'll have one single armature. Export that file as fbx (I'll call it model.fbx)


-Now load only one of the meshes (for big models load the lightest ones so it's faster) and put all the anims that you want on that one. Here I put the animation that I want on Edelgard's body. If the game you're extracting from has skeleton g1m files, I'd recommend loading the animations on it. Export that file (I'll call it animation.fbx)


-In Blender, import the animation.fbx file and directly save it as a blend file. I'll call it animation.blend

-Make a new scene in Blender and now import your model file. Now go to "File" > "append", double click on the animation.blend then go to the "actions" folder and double-click on the file inside it (there should only be one action file unless you added more or split them in the animation.blend, if you just followed the steps above there'll only be one).

-Select your armature. Now go to the action editor and click on the icon next to the "New" button. I repeat, select the icon, not the new button. . Then choose the action you just appended in the list.


That's it, the merged model will now have all the animations without duplicate bones.
## Post #118
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-03-21T20:34:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

glad to see its not a problem with the model and just how i used it, so it had to do with the fact that theres duplicate bones?
## Post #119
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-03-21T21:14:05+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sat Mar 21, 2020 8:16 pm at Sat Mar 21, 2020 8:16 pm
>
> 
Enkidu115 wrote: ↑Sat Mar 21, 2020 6:21 pm
Joschka wrote: ↑Sat Mar 21, 2020 5:17 pm


Send me the whole folders for a few non working characters with that error, that should be enough

https://drive.google.com/file/d/1V-VAS_ ... sp=sharing


Works fine for me 

Also there was a bunch of stuff not in the game by default in your folder, I assume it was the output of daemon's tools on your g1m

is there something in the script setting i should turn to true or false?
## Post #120
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-21T21:17:59+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Enkidu115 ↑Sun Mar 22, 2020 4:34 am at Sun Mar 22, 2020 4:34 am
>
> 
glad to see its not a problem with the model and just how i used it, so it had to do with the fact that theres duplicate bones?

All right tell me the exact steps you did, I won't let a fellow DQ fan without help hehe

First make sure that you have the last version of the script by downloading it on the repo.
In order to get this model to work you need to have the option "bAutoLoadG1MS" to False and "bLoadG1MS" to True, as with your naming convention the skeleton g1m is not the first one in the folder.
Select either the hair or the body, when prompted choose the g1t texture file, then choose the skeleton g1m when prompted. Then choose anim files if you let the option and have some files or press cancel.

Make sure you follow these steps and it should work as expected
## Post #121
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-03-21T21:35:13+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Mar 22, 2020 5:17 am at Sun Mar 22, 2020 5:17 am
>
> 
Enkidu115 wrote: ↑Sun Mar 22, 2020 4:34 am
glad to see its not a problem with the model and just how i used it, so it had to do with the fact that theres duplicate bones?


All right tell me the exact steps you did, I won't let a fellow DQ fan without help hehe

First make sure that you have the last version of the script by downloading it on the repo.
In order to get this model to work you need to have the option "bAutoLoadG1MS" to False and "bLoadG1MS" to True, as with your naming convention the skeleton g1m is not the first one in the folder.
Select either the hair or the body, when prompted choose the g1t texture file, then choose the skeleton g1m when prompted. Then choose anim files if you let the option and have some files or press cancel.

Make sure you follow these steps and it should work as expected

lol. Oh i see now- let me try that now
## Post #122
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-03-21T22:02:10+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Enkidu115 ↑Sun Mar 22, 2020 5:35 am at Sun Mar 22, 2020 5:35 am
>
> 
Joschka wrote: ↑Sun Mar 22, 2020 5:17 am
Enkidu115 wrote: ↑Sun Mar 22, 2020 4:34 am
glad to see its not a problem with the model and just how i used it, so it had to do with the fact that theres duplicate bones?


All right tell me the exact steps you did, I won't let a fellow DQ fan without help hehe

First make sure that you have the last version of the script by downloading it on the repo.
In order to get this model to work you need to have the option "bAutoLoadG1MS" to False and "bLoadG1MS" to True, as with your naming convention the skeleton g1m is not the first one in the folder.
Select either the hair or the body, when prompted choose the g1t texture file, then choose the skeleton g1m when prompted. Then choose anim files if you let the option and have some files or press cancel.

Make sure you follow these steps and it should work as expected


lol. Oh i see now- let me try that now

so i got the body and the skeleton to work, but i don't know how to add the hair to the model as when i try using the merger option it crashes
## Post #123
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-21T22:39:14+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Enkidu115 ↑Sun Mar 22, 2020 6:02 am at Sun Mar 22, 2020 6:02 am
>
> 
Enkidu115 wrote: ↑Sun Mar 22, 2020 5:35 am
Joschka wrote: ↑Sun Mar 22, 2020 5:17 am


All right tell me the exact steps you did, I won't let a fellow DQ fan without help hehe

First make sure that you have the last version of the script by downloading it on the repo.
In order to get this model to work you need to have the option "bAutoLoadG1MS" to False and "bLoadG1MS" to True, as with your naming convention the skeleton g1m is not the first one in the folder.
Select either the hair or the body, when prompted choose the g1t texture file, then choose the skeleton g1m when prompted. Then choose anim files if you let the option and have some files or press cancel.

Make sure you follow these steps and it should work as expected


lol. Oh i see now- let me try that now


so i got the body and the skeleton to work, but i don't know how to add the hair to the model as when i try using the merger option it crashes

Yeah that's because the skeleton g1m is with the others, I mentionned it here [https://github.com/Joschuka/fmt_g1m#model-merging](https://github.com/Joschuka/fmt_g1m#model-merging)
So it tries to load it as a "classic" g1m too as the merger parses everything with the same extension in the folder, which causes a bug. To fix that simply put it in another folder. You'll have to select it for both models when asked. Don't forget to put the option to 1 in the merger so the bones will be merged accordingly.
## Post #124
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-03-21T23:18:10+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Mar 22, 2020 6:39 am at Sun Mar 22, 2020 6:39 am
>
> 
Enkidu115 wrote: ↑Sun Mar 22, 2020 6:02 am
Enkidu115 wrote: ↑Sun Mar 22, 2020 5:35 am


lol. Oh i see now- let me try that now


so i got the body and the skeleton to work, but i don't know how to add the hair to the model as when i try using the merger option it crashes


Yeah that's because the skeleton g1m is with the others, I mentionned it here https://github.com/Joschuka/fmt_g1m#model-merging
So it tries to load it as a "classic" g1m too as the merger parses everything with the same extension in the folder, which causes a bug. To fix that simply put it in another folder. You'll have to select it for both models when asked. Don't forget to put the option to 1 in the merger so the bones will be merged accordingly.
 ah okay it worked, thank you!
## Post #125
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-03-22T12:58:35+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Mar 18, 2020 1:55 am at Wed Mar 18, 2020 1:55 am
>
> 

G1MS : Skeleton info
G1MF : Some info about number of submeshes and other details about the sections in the file. I don't use it to reconstruct models
G1MM : Bone matrices, I don't use this section either
G1MG : Geometry and platform info, divided in 9 subsections
NUNO/NUNV/NUNS : cloth/hair meshes data used for physics sim
SOFT : same for breast (I don't use it)
COLL : We assume it's for collision shapes used to collide with the cloth driver nodes
HAIR: No clue yet, name seems obvious but that chunk was always empty in the models we saw
EXTR : No clue either yet, it's empty 99% of the time, we only saw a few models with that chunk used

Is a Blender plugin required to read each of these information?
If there was such thing as a Blender plugin, could you export a full model from Noesis and import it into Blender, then modify its skeleton a bit, and import your edits back into the model so you have a custom rig and new physics data?
## Post #126
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-03-23T14:45:11+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

(this question is related to games with g1m mods injector)


Mesh data can be edited, as seen here: [http://fav.me/dd92pht](http://fav.me/dd92pht)

Can other data that is contained in g1m files be modified, potentially?
## Post #127
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-23T22:31:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Thony ↑Sun Mar 22, 2020 8:58 pm at Sun Mar 22, 2020 8:58 pm
>
> 
If there was such thing as a Blender plugin, could you export a full model from Noesis and import it into Blender, then modify its skeleton a bit, and import your edits back into the model so you have a custom rig and new physics data?
For custom rigs there are several layers :
-a map mapping "global" indices to "local" ones (for example global bone 200 may be bone 123 for a model and bone 126 for another model).
-a map for each individual model submesh mapping "local" bone indices (used by the armature for parenting) to the custom bone indices starting from 0 and growing 3 by 3. That map also holds some clothing index and an index to a G1MM matrix (which is the bind pose for the referenced bone).

So to add bones I guess you could make a custom bonemap, force all your submeshes to use it and make them point to new G1MM matrices you would have computed beforehand. You'll need to add new entries to the global indices map too and it may be hardcoded so not even sure if you could do that.

For physics data it combines the NUN sections, the vertex shader and some buffer values. You'd need to do the operations I do for these meshes in my script backward, generate the driver nodes then reconstructing the NUN sections, that are not completely reversed yet. 

> Reply from Thony ↑Mon Mar 23, 2020 10:45 pm at Mon Mar 23, 2020 10:45 pm
>
> 
Mesh data can be edited, as seen here: http://fav.me/dd92pht
Can other data that is contained in g1m files be modified, potentially?
Potentially yeah you could try to do the rig stuff I told above and start experimenting with physics meshes but I won't be the one to do that. This format is extremely annoying to deal with and I have no particular interested in model repacking myself. Even from a learning perspective it wouldn't be worth it, it'd be like working as a KT technical artist on an extremely boring task and without any compensation so I have zero motivation for that.

So yeah if you have any question about the format specs or anything I'll be glad to answer them but I won't do anything related to model repacking, I'm only interested in extracting/viewing content.
## Post #128
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-03-24T11:49:35+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Thank you very much for your detailed answer!

[https://youtu.be/4-rE8zxyhik?t=172](https://youtu.be/4-rE8zxyhik?t=172)
Model swaps are possible in DOA6.
Costume transfers between characters of different heights is something I'd like to experiment on (scaling mesh to fit armature or vice versa).

Also sorry for digressing, g1m format is just unnecessarily complex and you've really helped deciphering it more.
## Post #129
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-24T21:07:16+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Thony ↑Tue Mar 24, 2020 7:49 pm at Tue Mar 24, 2020 7:49 pm
>
> 
Thank you very much for your detailed answer!

https://youtu.be/4-rE8zxyhik?t=172
Model swaps are possible in DOA6.
Costume transfers between characters of different heights is something I'd like to experiment on (scaling mesh to fit armature or vice versa).
Ah yes these edits are with loverslab' g1mtools right ? I actually teamed up with its creator vagonumero13/Eternity to reverse the g2a animation format. 

> Reply from Thony ↑Tue Mar 24, 2020 7:49 pm at Tue Mar 24, 2020 7:49 pm
>
> 
Also sorry for digressing, g1m format is just unnecessarily complex and you've really helped deciphering it more.

No problem, as long as its related to KT's models/animations formats I'd be glad to answer, good luck for your projects !
## Post #130
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-03-26T05:21:43+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

OnePiece Pirate Warriors 4(Switch) is in --rdb.
It is possible to decompress with Cethleann.

Some g1m and g1a can be played, but many files cannot be read.
I'll check a more files and upload samples as needed.
## Post #131
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-26T11:08:32+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from einherjar007 ↑Thu Mar 26, 2020 1:21 pm at Thu Mar 26, 2020 1:21 pm
>
> 
OnePiece Pirate Warriors 4(Switch) is in --rdb.
It is possible to decompress with Cethleann.

Some g1m and g1a can be played, but many files cannot be read.
I'll check a more files and upload samples as needed.

I see, so they are starting to use rdb on all their games as Yretenai suspected
Don't worry about the samples, I bought the game so I'll check myself, I wonder what they changed...
## Post #132
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2020-03-27T17:02:30+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

It looks like it's a physics thing again, models without physics seem to work fine but those with give an error.
## Post #133
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-27T17:55:42+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from TRDaz ↑Sat Mar 28, 2020 1:02 am at Sat Mar 28, 2020 1:02 am
>
> 
It looks like it's a physics thing again, models without physics seem to work fine but those with give an error.

Yeah, they used a new NUNO version.

SCRIPT UPDATED

Added NUNOv32 support. Most models from OPPW4 should now import correctly, you can use Yretenai's tools to reconstruct the G1T files. I tested the new version on the first 15 playable characters so let me know if there are some models with issues.
## Post #134
- Username: peak899
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 19, 2020 12:34 am
- Post datetime: 2020-03-28T18:13:50+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Greate work! Testing on DOA6 (PC),  body animations are ok, only have some  trouble with Face animations.
[Capture.jpg](https://xentaxbackup.github.io/file/17825_Capture.jpg)
## Post #135
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-28T22:11:09+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from peak899 ↑Sun Mar 29, 2020 2:13 am at Sun Mar 29, 2020 2:13 am
>
> 
Greate work! Testing on DOA6 (PC),  body animations are ok, only have some  trouble with Face animations.

Precisely I was talking with someone about these yesterday. I really don't know why they're so broken, facial anims work for FETH and Dissidia and they use the same format...
This will be the next thing I'll look into.

Also I've been told that some OPPW4 anims break, I'll see wha's wrong with these.

EDIT : Pushed a fix for the OPPW4 anims, they should all work now. If any old anim doesn't work anymore tell me, should be good though.
## Post #136
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-29T16:06:57+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

SCRIPT UPDATED

While looking at the DOA face animations I noticed that some animations had bones which only had 1 keyframe so they were ignored by my parser as my interpolation assumed they were at least 2 keyframes. Animations with every bone having only 1 frame are used when you just want to put all bones into a pose directly and nothing else.
Here's an example of such anims on lightning, which previously gave invalid entries in Noesis and were ignored :

To see these I recommend loading them and then going in the Noesis dataviewer then select them. Since they only last 1 frame it's hard to check without using that method.
This fix also fixed some weird bones rotations on some anims (like fingers which previously had weird orientation).

For DOA6 I still don't really know why it deforms so bad. When ignoring position keyframes it looks much better so the problem must come from here I guess. I'll look more into it next week
## Post #137
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-03-29T20:57:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Mon Mar 30, 2020 12:06 am at Mon Mar 30, 2020 12:06 am
>
> 
SCRIPT UPDATED

While looking at the DOA face animations I noticed that some animations had bones which only had 1 keyframe per bone so they were ignored by my parser as my interpolation assumed they were at least 2 keyframes. Animations with every bone having only 1 frame are used when you just want to put all bones into a pose directly and nothing else.
Here's an example of such anims on lightning, which previously gave invalid entries in Noesis and were ignored :

To see these I recommend loading them and then going in the Noesis dataviewer then select them. Since they only last 1 frame it's hard to check without using that method.
This fix also fixed some weird bones rotations on some anims (like fingers which previously had weird orientation).

For DOA6 I still don't really know why it deforms so bad. When ignoring position keyframes it looks much better so the problem must come from here I guess. I'll look more into it next week
The irony that after all this time, I've not figure out were are the animation on NT  .
But, I doubt I will use them, but those are an interesting one, do you think they're used on fights?
## Post #138
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-03-29T20:59:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

I try the Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW but can,t geting error may you can"t figure it out I wii  had this up untell april1.2020 [https://sta.sh/025i9b293gl](https://sta.sh/025i9b293gl)
## Post #139
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-29T21:46:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Darkhowlings ↑Mon Mar 30, 2020 4:57 am at Mon Mar 30, 2020 4:57 am
>
> 
The irony that after all this time, I've not figure out were are the animation on NT  .
But, I doubt I will use them, but those are an interesting one, do you think they're used on fights?

If you extracted the game using Cethleann the animations should be in the "character" folder. For p_tht100_1p1c for example (Lightning) they're in the "p_tht100" folder. The GAPKs are there, you can drag and drop them on Cethleann.Unbundler and you'll get the g2a files.

Yes, theses anims above are all 1 frame battle animations, respectively "attack", "damage", "dead", "default", "guard". The only "long" face animation is the "summon" one, at least for battles.

> Reply from blacknight411 ↑Mon Mar 30, 2020 4:59 am at Mon Mar 30, 2020 4:59 am
>
> 
I try the Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW but can,t geting error may you can"t figure it out I wii  had this up untell april1.2020 https://sta.sh/025i9b293gl

Your samples work fine (don't mind my orange filter) :



Just put "bAutoLoadG1MS" to True at the beginning of the script. And select the g1m with the "default" name.
## Post #140
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-03-30T02:29:19+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

DO I have to install it in  sign  in to visual studio beacuse I can,t  open it untell  I sign  in  plus  30 day is out for  for that to. can I just give the model  of the one I want done in thin link it back to me.
## Post #141
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-03-30T03:16:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

can you send me  the right tool.
## Post #142
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-03-30T13:21:23+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from blacknight411 ↑Mon Mar 30, 2020 11:16 am at Mon Mar 30, 2020 11:16 am
>
> 
can you send me  the right tool.
just go to the python script that's located on github, once you get to the coding screen of the script, just click on the icon that says "raw"


after that, right click>save as
save it in the plugin\python folder in noesis directory
## Post #143
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-03-30T15:49:34+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

most of Nioh g1ms open come with different errors
the other which is fine to open, take much time to load
Hope I am not using it wrong way
## Post #144
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-30T17:01:35+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from ngovandang ↑Mon Mar 30, 2020 11:49 pm at Mon Mar 30, 2020 11:49 pm
>
> 
most of Nioh g1ms open come with different errors
the other which is fine to open, take much time to load
Hope I am not using it wrong way

Didn't know that Nioh used NUNS. Send me your samples, I only had those two dissidia models who had that chunk to work with so I'm not surprised. 
They worked before according to Allanoon/einherjar007 cause I was ignoring it

Also can't do much about loading times on detailed models, I need to optimize some parts but I don't have the time for that rn
## Post #145
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-30T17:35:13+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

I pushed a small update with a new parameter "bOnlyLoadG1MS". If that parameter is set to True only the skeleton and the driver shapes will be loaded, which can be useful to quickly check animations especially on models which take a long time to load.

Combined with that trick [viewtopic.php?f=16&t=21666&start=105#p161145](https://forum.xentax.com/viewtopic.php?f=16&t=21666&start=105#p161145) you'll just have to load the mesh once in Noesis.
## Post #146
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-03-30T18:52:01+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Joschka for atelier ryza do I need the whole game to make work it  or  just  need glm and g1t file  I drag MOB21A_MODEL_default to the Cethleann.Unbundler in it give me this 0000.G1Mf,0001.G1MS,0003.G1MG,0004.COLL,0005.NUNO and 0006.EXTR.
## Post #147
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-03-30T19:08:56+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from blacknight411 ↑Tue Mar 31, 2020 2:52 am at Tue Mar 31, 2020 2:52 am
>
> 
Joschka for atelier ryza do I need the whole game to make work it  or  just  need glm and g1t file  I drag MOB21A_MODEL_default to the Cethleann.Unbundler in it give me this 0000.G1Mf,0001.G1MS,0003.G1MG,0004.COLL,0005.NUNO and 0006.EXTR.
your doing it all wrong... you OPEN the G1M files in NOESIS.
## Post #148
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-03-30T19:28:29+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Ok I OPEN the G1M files in NOESIS but keep geting  error. how do  I send pictures.
## Post #149
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-30T20:23:50+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from blacknight411 ↑Tue Mar 31, 2020 3:28 am at Tue Mar 31, 2020 3:28 am
>
> 
Ok I OPEN the G1M files in NOESIS but keep geting  error. how do  I send pictures.

Cethleann is used when you need to extract the g1m/g1t files from the game archives. Since you already have them you don't need to use it.

Now for your g1m files, you have a game for which the skeleton is contained in a separate file than the model. So you need to open my script in a text editor, change 

```
bLoadG1MS = False
```

to 

```
bLoadG1MS = True
```

and save.
Then restart Noesis or reload the plugin. Open the g1m file with the "default" in the name. When asked, choose the g1t file, it contains the texture. 
Then it will ask for a skeleton g1m, choose the file without the "default" in the name.
## Post #150
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-03-30T21:00:57+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

where  in a text editor to put  it at the script .
## Post #151
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-30T21:40:12+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Just grab the attached script.

Put the fmt_g1m.py inside in the Noesis/noesisvxxx/plugins/python folder 


Then open Noesis. Click file, open and choose the file with "default" in its name 


Open it, wait for a bit. Then a window will open, choose the g1t file 


Then wait and you'll have your model
[fmt_g1m.zip](https://xentaxbackup.github.io/file/17846_fmt_g1m.zip)
## Post #152
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-03-31T01:48:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

try it  keep geting  error  traceback,most recent call  last, file "C; \ Users  \ plugin\ python\fmt_g1m.py",line1195,in load model parseG1MS(current position,bs,file"C\Users plugins\python\fmt_g1m.py",line 392,in parseG1MS bone.setMatrix(bone.getMatrix ()*bonelist(parentId).getMatrix()) index error:list index  out of range sorry I can,t do screenshot.
## Post #153
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-03-31T01:52:31+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Here it is more better  read Traceback (most recent call last):
  File "C:\Users\Thomas Glenn\Pictures\fin\New folder\plugins\python\fmt_g1m.py", line 1195, in LoadModel
    parseG1MS(currentPosition, bs)
  File "C:\Users\Thomas Glenn\Pictures\fin\New folder\plugins\python\fmt_g1m.py", line 392, in parseG1MS
    bone.setMatrix(bone.getMatrix() * boneList[parentId].getMatrix())
IndexError: list index out of range
## Post #154
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-31T09:48:47+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

This error happens when the skeleton is not detected so you either did not follow my instructions or you have other stuff in you folder which is loaded as a skeleton. Put your 3 files in a new folder, do the steps I told above with the script I attached and it'll work
## Post #155
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-03-31T11:13:02+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Here is sample for NUNS problems

[https://file.io/NJzRsh](https://file.io/NJzRsh)
## Post #156
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-31T11:49:55+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from ngovandang ↑Tue Mar 31, 2020 7:13 pm at Tue Mar 31, 2020 7:13 pm
>
> 
Here is sample for NUNS problems

https://file.io/NJzRsh

got a 404 error
## Post #157
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-03-31T14:30:40+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Tue Mar 31, 2020 7:49 pm at Tue Mar 31, 2020 7:49 pm
>
> 
got a 404 error

Oops, I am sorry

Here
[https://mega.nz/#!2oR2nI5Y!Ssz0ZVpDgdNH ... KIU96wnCpc](https://mega.nz/#!2oR2nI5Y!Ssz0ZVpDgdNH5OLIoWPG5Hv59ZLRRRyBsKIU96wnCpc)
## Post #158
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-03-31T19:46:16+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

SCRIPT UPDATED

> Reply from peak899 ↑Sun Mar 29, 2020 2:13 am at Sun Mar 29, 2020 2:13 am
>
> 

DOA6 facial animations are now extracted correctly. Put the new parameter at the top "bDOA6FaceAnims" to True and load them as any other animation file. Don't forget to put it to False for all the other animations or you'll have some deformed meshes.



> Reply from ngovandang ↑Tue Mar 31, 2020 10:30 pm at Tue Mar 31, 2020 10:30 pm
>
> 

I updated the NUNS parser and added an option to load that chunk or not since I still don't really know what it does and it introduces a lot of overlapping bones. Driver shapes may be useful for simulation though so I let it in case people want to use that. Let me know if there are still some issues, I only had 3 samples in total to work with so my parser might still break.
## Post #159
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-04-01T07:51:53+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Joschka one more thing what is this  rpdb-0.16 in the python folder above.
## Post #160
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-01T10:34:50+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

You don't need it, it's a python debugger that I use when developping my scripts.
## Post #161
- Username: peak899
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 19, 2020 12:34 am
- Post datetime: 2020-04-01T15:07:55+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Just tested DOA6 facial animations, worked perfectly.
## Post #162
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-04-02T20:55:33+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

At last  finally  got  it working  the problem  was need to take out in put back in  thank  you  for all your help Joschka.
## Post #163
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-04-05T07:20:38+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

night azure  do not works.
## Post #164
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-06T14:48:54+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from blacknight411 ↑Sun Apr 05, 2020 3:20 pm at Sun Apr 05, 2020 3:20 pm
>
> 
night azure  do not works.

You're sure that you followed the instructions correctly ? If so I need a few samples to look into it
## Post #165
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-04-06T21:49:09+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

here a samplehttps://sta.sh/0gzwqtlr8w6
## Post #166
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-07T16:07:31+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

I fixed NUNS again, pretty confident in my parser now, your model is now working 



SCRIPT UPDATED TO VERSION 1.2.0
## Post #167
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2020-04-08T00:41:30+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hiii, I was trying to rip models from Atelier Escha & Logy DX (PC) and came across an error when trying to import with mesh animations;



error.png (28.36 KiB) Viewed 335 times



Just wondering if perhaps I did something wrong in the process or if there isn't support for this game yet.

Sample just in case;
[https://mega.nz/file/Tll2GAzC#85lbCkwNW ... d0bH4GDqhY](https://mega.nz/file/Tll2GAzC#85lbCkwNWzadqG2td3pgIAqqOESIUE8crd0bH4GDqhY)
## Post #168
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-04-08T01:20:15+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

where the SCRIPT UPDATED TO VERSION 1.2.0 link at.
## Post #169
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-08T11:36:23+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from anime663 ↑Wed Apr 08, 2020 8:41 am at Wed Apr 08, 2020 8:41 am
>
> 
Hiii, I was trying to rip models from Atelier Escha & Logy DX (PC) and came across an error when trying to import with mesh animations;
Just wondering if perhaps I did something wrong in the process or if there isn't support for this game yet.

i took a look at your sample, the error actually doesn't come from the animation but from the morph target (G1H file), this is what G1H is used for :


Unfortunately the research I was given was partly wrong so it only works on a few models, since no one seemed to care about that stuff I didn't look into it myself.

There are two types of animations for games using g1a : morph anims and skeletal anims. I only support the latter for now. Contrary to recent games who have a face rig, your Escha model uses morph anims for the face (in the samples you sent me you can see all g1a are for the eyes and mouth, which have no rig). This kind of anim is probably some interpolation between several morph shapes. 
So yeah these face anims are not supported, but body anims should work(they're probably in another folder). If there's some interest I can try to fix the G1H so you could have the different expressions. Can't really give an ETA if so though since I pretty much moved on to my next project already.

> Reply from blacknight411 ↑Wed Apr 08, 2020 9:20 am at Wed Apr 08, 2020 9:20 am
>
> 
where the SCRIPT UPDATED TO VERSION 1.2.0 link at.
The link in my first post always has the most up to date script.
## Post #170
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2020-04-08T21:56:53+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Apr 08, 2020 7:36 pm at Wed Apr 08, 2020 7:36 pm
>
> 
anime663 wrote: ↑Wed Apr 08, 2020 8:41 am
Hiii, I was trying to rip models from Atelier Escha & Logy DX (PC) and came across an error when trying to import with mesh animations;
Just wondering if perhaps I did something wrong in the process or if there isn't support for this game yet.


i took a look at your sample, the error actually doesn't come from the animation but from the morph target (G1H file), this is what G1H is used for :


Unfortunately the research I was given was partly wrong so it only works on a few models, since no one seemed to care about that stuff I didn't look into it myself.

There are two types of animations for games using g1a : morph anims and skeletal anims. I only support the latter for now. Contrary to recent games who have a face rig, your Escha model uses morph anims for the face (in the samples you sent me you can see all g1a are for the eyes and mouth, which have no rig). This kind of anim is probably some interpolation between several morph shapes. 
So yeah these face anims are not supported, but body anims should work(they're probably in another folder). If there's some interest I can try to fix the G1H so you could have the different expressions. Can't really give an ETA if so though since I pretty much moved on to my next project already.

Yeah I was interested in the morph anims, I hope there will be support someday! Please take your time with it though ^^
Thanks for the response.
## Post #171
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-04-08T23:30:04+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

I went to the first link i do not see the script.
## Post #172
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2020-04-12T06:07:32+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Thank you for providing such a convenient tool

[https://www.gamecity.ne.jp/nol](https://www.gamecity.ne.jp/nol) 
Nobunaga Online  Windows HD

Can you please support the G1M format of this game

This is an example of the game

[https://mega.nz/file/gGARDYgI#eUKezXPpg ... ydsRkicD3o](https://mega.nz/file/gGARDYgI#eUKezXPpgVCPPsbqUS_D1-Ntpja7YbW9wydsRkicD3o)

Thank you
## Post #173
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-12T12:36:52+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from wordhg ↑Sun Apr 12, 2020 2:07 pm at Sun Apr 12, 2020 2:07 pm
>
> 
Thank you for providing such a convenient tool

https://www.gamecity.ne.jp/nol 
Nobunaga Online  Windows HD

Can you please support the G1M format of this game

This is an example of the game

https://mega.nz/file/gGARDYgI#eUKezXPpg ... ydsRkicD3o

Thank you

These models seem to work, the problem is that 90 and 91 need an external skeleton, which is not there.

89 works fine as it has its skeleton inside 


So you need to find the humanoid skeleton associated with the models. There are usually less than a 100 kB g1m files contrary to the models g1m. I'd recommend to use the "bLoadG1MSOnly" option, if it gives an error then the g1m doesn't have a skeleton. Otherwise it'll load and you will be able to see its shape. Then you'll just have to load the models g1m (those 90 and 91 for example) and choose the associated skeleton, it'll work.
## Post #174
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2020-04-13T11:20:18+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Apr 12, 2020 8:36 pm at Sun Apr 12, 2020 8:36 pm
>
> 
So you need to find the humanoid skeleton associated with the models. There are usually less than a 100 kB g1m files contrary to the models g1m. I'd recommend to use the "bLoadG1MSOnly" option, if it gives an error then the g1m doesn't have a skeleton. Otherwise it'll load and you will be able to see its shape. Then you'll just have to load the models g1m (those 90 and 91 for example) and choose the associated skeleton, it'll work.
Thanks for the answer, I know how to use it
thank you very much
## Post #175
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-04-14T13:39:49+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hi there, I was able to extract the files for AOT2 with Yretenai's tool, folders with g1t textures seem to be working fine.
Although unpacking the ptrbundles with Cethleann.Unbundler for the model files gave me g1m files, noesis gave an error message when trying to preview them 
is there any way to fix them/make them work?
## Post #176
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-14T15:14:09+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Eag1e ↑Tue Apr 14, 2020 9:39 pm at Tue Apr 14, 2020 9:39 pm
>
> 
Hi there, I was able to extract the files for AOT2 with Yretenai's tool, folders with g1t textures seem to be working fine.
Although unpacking the ptrbundles with Cethleann.Unbundler for the model files gave me g1m files, noesis gave an error message when trying to preview them 
is there any way to fix them/make them work?

Can't see your image and you didn't attach samples, I can't take a look. If this is the bone.setMatrix Index out of range error that means that you didn't select the skeleton g1m.
## Post #177
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-04-14T22:51:47+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Tue Apr 14, 2020 11:14 pm at Tue Apr 14, 2020 11:14 pm
>
> 
Eag1e wrote: ↑Tue Apr 14, 2020 9:39 pm
Hi there, I was able to extract the files for AOT2 with Yretenai's tool, folders with g1t textures seem to be working fine.
Although unpacking the ptrbundles with Cethleann.Unbundler for the model files gave me g1m files, noesis gave an error message when trying to preview them 
is there any way to fix them/make them work?




Can't see your image and you didn't attach samples, I can't take a look. If this is the bone.setMatrix Index out of range error that means that you didn't select the skeleton g1m.

Ah, here's the files in the folder I tried to load with the plugin [https://mega.nz/file/FdNQgYDI#8Lex2u3SJ ... YMbAKk8R0o](https://mega.nz/file/FdNQgYDI#8Lex2u3SJ2Gsgu9xqdV9uBhTIpp2Q4RXtYMbAKk8R0o)
## Post #178
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-15T10:18:25+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Works fine for me, the skeleton g1m is the first one 

Meshes are split in several files, use the model merger with the instructions mentionned on my repo to merge everything. You may or may not want to disable NUNS parsing if you don't want the associated drivers on every mesh.
## Post #179
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-04-15T17:18:30+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Apr 15, 2020 6:18 pm at Wed Apr 15, 2020 6:18 pm
>
> 
Works fine for me, the skeleton g1m is the first one 

Meshes are split in several files, use the model merger with the instructions mentionned on my repo to merge everything. You may or may not want to disable NUNS parsing if you don't want the associated drivers on every mesh.

Alright, so I followed the steps in the github page, these are my settings (I have MERGE_BONES at option 1 btw)


Then I put the 0001.gmt in a separate folder like the guide told me, right clicked the 0002.gmt selected merge, loaded the g1t file, loaded 0001.gmt, but I get this error, apologies if I'm making dumb mistakes
## Post #180
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-15T18:00:12+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Eag1e ↑Thu Apr 16, 2020 1:18 am at Thu Apr 16, 2020 1:18 am
>
> 

You're doing the right steps but from what I see you have an old version of the script, make sure to grab the latest one on the github repository and it should work as expected.
## Post #181
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-04-15T19:26:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Thu Apr 16, 2020 2:00 am at Thu Apr 16, 2020 2:00 am
>
> 
Eag1e wrote: ↑Thu Apr 16, 2020 1:18 am


You're doing the right steps but from what I see you have an old version of the script, make sure to grab the latest one on the github repository and it should work as expected.

Ah yes it works now, thank you!

Sorry for spamming these questions, but I've got one more thing, when trying to load .oid files to give PW4 models bone names, i get this error, loading them without oid works fine though, it's just that I need to rename the bones which takes some time


Here's the files [https://mega.nz/file/kQVGAIQB#_ZnYR0ZBg ... ecXZt9NIQY](https://mega.nz/file/kQVGAIQB#_ZnYR0ZBgenMkrMlYkhRCFB-ayzN4bs3vecXZt9NIQY)
## Post #182
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-16T11:30:38+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Eag1e ↑Thu Apr 16, 2020 3:26 am at Thu Apr 16, 2020 3:26 am
>
> 

Ah yes it works now, thank you!

Sorry for spamming these questions, but I've got one more thing, when trying to load .oid files to give PW4 models bone names, i get this error, loading them without oid works fine though, it's just that I need to rename the bones which takes some time

Yretenai took a look at it, unfortunately it seems they don't leave bone names anywhere anymore. There are now hashes only in the oid files and the original names won't be retrievable. 
She pushed an update to handle these files so it won't crash anymore but you'll have the hashes, not the original bone names.
## Post #183
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-04-16T22:37:16+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Thu Apr 16, 2020 7:30 pm at Thu Apr 16, 2020 7:30 pm
>
> 
Eag1e wrote: ↑Thu Apr 16, 2020 3:26 am

Ah yes it works now, thank you!

Sorry for spamming these questions, but I've got one more thing, when trying to load .oid files to give PW4 models bone names, i get this error, loading them without oid works fine though, it's just that I need to rename the bones which takes some time


Yretenai took a look at it, unfortunately it seems they don't leave bone names anywhere anymore. There are now hashes only in the oid files and the original names won't be retrievable. 
She pushed an update to handle these files so it won't crash anymore but you'll have the hashes, not the original bone names.

Alright, thanks for all the help!
## Post #184
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-04-17T02:44:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Really thanks for your awesome work!
But I've got a weird .g1m file that cannot be loaded in Noesis and extracted by the other tools.
When I open it in Noesis, Noesis keeps showing me this error:


Here's the samples extracted from Warriors Orochi 4(The other models work fine with this script):
[https://mega.nz/file/ykV03KCT#p4LRuv7au ... iKHibURTsg](https://mega.nz/file/ykV03KCT#p4LRuv7auvrd9-tKHx-q0R0EaKTlgefFLiKHibURTsg)
## Post #185
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-19T18:19:03+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Kanbara ↑Fri Apr 17, 2020 10:44 am at Fri Apr 17, 2020 10:44 am
>
> 
Really thanks for your awesome work!
But I've got a weird .g1m file that cannot be loaded in Noesis and extracted by the other tools.
When I open it in Noesis, Noesis keeps showing me this error:


Here's the samples extracted from Warriors Orochi 4(The other models work fine with this script):
https://mega.nz/file/ykV03KCT#p4LRuv7au ... iKHibURTsg

Np, glad you like the tool.
I'll take a look at your file tomorrow, never saw that error before, that's weird.
## Post #186
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-20T12:22:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

That was a really weird file, some specs had a negative vertex count and weird fields... I pushed a fix for that, never saw that before.
## Post #187
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2020-04-21T02:17:08+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Mon Apr 20, 2020 8:22 pm at Mon Apr 20, 2020 8:22 pm
>
> 
That was a really weird file, some specs had a negative vertex count and weird fields... I pushed a fix for that, never saw that before.

Yes. There are some files also showing this error as well.
I used deamon1's tools to try to decompress this .g1m file into several .ascii files and it doesn't work either  
Koei tecmo!What have you done on these files?
## Post #188
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-04-21T12:03:07+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Kanbara ↑Tue Apr 21, 2020 10:17 am at Tue Apr 21, 2020 10:17 am
>
> 
Joschka wrote: ↑Mon Apr 20, 2020 8:22 pm
That was a really weird file, some specs had a negative vertex count and weird fields... I pushed a fix for that, never saw that before.


Yes. There are some files also showing this error as well.
I used deamon1's tools to try to decompress this .g1m file into several .ascii files and it doesn't work either  
Koei tecmo!What have you done on these files?

It still doesn't work with the latest version ? I updated the script
## Post #189
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-04-23T21:48:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Mon Apr 20, 2020 8:22 pm at Mon Apr 20, 2020 8:22 pm
>
> 
That was a really weird file, some specs had a negative vertex count and weird fields... I pushed a fix for that, never saw that before.

Negative counts would indicate it's either a shorter width (16-bit rather than 32-bit) or unsigned
## Post #190
- Username: ChikoLad
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 13, 2017 3:51 am
- Post datetime: 2020-05-12T00:10:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

I'm trying to use this tool to get assets from Dissidia Opera Omnia (the mobile game spin-off of Dissidia NT), but I keep getting this error when I try to load the textures of most of the models (only exception is Laguna's textures for some reason).



I can load the models fine but I get this error whenever I try to load textures on any model besides Laguna.
## Post #191
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-05-12T13:22:37+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from ChikoLad ↑Tue May 12, 2020 8:10 am at Tue May 12, 2020 8:10 am
>
> 
I'm trying to use this tool to get assets from Dissidia Opera Omnia (the mobile game spin-off of Dissidia NT), but I keep getting this error when I try to load the textures of most of the models (only exception is Laguna's textures for some reason).

You probably need to update Noesis
## Post #192
- Username: ChikoLad
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 13, 2017 3:51 am
- Post datetime: 2020-05-12T23:26:07+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Tue May 12, 2020 9:22 pm at Tue May 12, 2020 9:22 pm
>
> 
ChikoLad wrote: ↑Tue May 12, 2020 8:10 am
I'm trying to use this tool to get assets from Dissidia Opera Omnia (the mobile game spin-off of Dissidia NT), but I keep getting this error when I try to load the textures of most of the models (only exception is Laguna's textures for some reason).


You probably need to update Noesis

Thank you, that fixed things for me!

So I successfully made a DFFOO vertex and texture edit with the assets I extracted and am interested in saving it back into the G1M and G1T formats and then repackaging them back into the .dz archives the game uses. Are there any established tools for converting back to G1M and G1T used for other Koei Tecmo games?
## Post #193
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-15T16:30:31+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

can .t open the model [https://sta.sh/018ds7lvs9n0](https://sta.sh/018ds7lvs9n0)
## Post #194
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-05-16T18:34:17+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from ChikoLad ↑Wed May 13, 2020 7:26 am at Wed May 13, 2020 7:26 am
>
> 
Joschka wrote: ↑Tue May 12, 2020 9:22 pm
ChikoLad wrote: ↑Tue May 12, 2020 8:10 am
I'm trying to use this tool to get assets from Dissidia Opera Omnia (the mobile game spin-off of Dissidia NT), but I keep getting this error when I try to load the textures of most of the models (only exception is Laguna's textures for some reason).


You probably need to update Noesis


Thank you, that fixed things for me!

So I successfully made a DFFOO vertex and texture edit with the assets I extracted and am interested in saving it back into the G1M and G1T formats and then repackaging them back into the .dz archives the game uses. Are there any established tools for converting back to G1M and G1T used for other Koei Tecmo games?

This is not trivial for g1m considering how annoying this format is... For textures there are a few g1t repackers out there I think but they probably won't work for you since I doubt they support the ETC1 format used on mobile. So yeah I don't think there are tools suitable for what you want to do unfortunately

> Reply from blacknight411 ↑Sat May 16, 2020 12:30 am at Sat May 16, 2020 12:30 am
>
> 
can .t open the model https://sta.sh/018ds7lvs9n0

It works for me, just reread the instructions and what I told you in the previous messages.
## Post #195
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-17T05:50:31+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Ok is this  the SCRIPT UPDATED TO VERSION 1.2.0 [https://github.com/Joschuka/fmt_g1m](https://github.com/Joschuka/fmt_g1m)
## Post #196
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-28T02:46:10+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Please answer me  you said just reread the instructions and what I told you in the previous messages  like your 1 post I know that but  went I went to  your 1 post  but I can't find SCRIPT UPDATED TO VERSION 1.2.0 only this [https://github.com/Joschuka/fmt_g1m](https://github.com/Joschuka/fmt_g1m)  please can  you link me the script please please please link me.
## Post #197
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-05-28T12:29:34+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from blacknight411 ↑Thu May 28, 2020 10:46 am at Thu May 28, 2020 10:46 am
>
> 
Please answer me  you said just reread the instructions and what I told you in the previous messages  like your 1 post I know that but  went I went to  your 1 post  but I can't find SCRIPT UPDATED TO VERSION 1.2.0 only this https://github.com/Joschuka/fmt_g1m  please can  you link me the script please please please link me.

bruh... that IS the updated script.
## Post #198
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-03T22:55:08+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Anything on Persona 5 Scramble since it's on the same engine as DOA6
## Post #199
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-04T08:41:23+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from qs12 ↑Thu Jun 04, 2020 6:55 am at Thu Jun 04, 2020 6:55 am
>
> 
Anything on Persona 5 Scramble since it's on the same engine as DOA6

What do you mean ? P5S has been extractable for a while [viewtopic.php?f=16&t=21666&start=30#p159703](https://forum.xentax.com/viewtopic.php?f=16&t=21666&start=30#p159703)
## Post #200
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-05T00:25:00+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

How do you load all the textures for a single model? In noesis it will only load one file
## Post #201
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-05T01:58:59+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from qs12 ↑Fri Jun 05, 2020 8:25 am at Fri Jun 05, 2020 8:25 am
>
> 
How do you load all the textures for a single model? In noesis it will only load one file
[viewtopic.php?f=10&t=21679&start=45#p160417](https://forum.xentax.com/viewtopic.php?f=10&t=21679&start=45#p160417)
## Post #202
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-05T03:01:36+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Fri Jun 05, 2020 9:58 am at Fri Jun 05, 2020 9:58 am
>
> 
qs12 wrote: ↑Fri Jun 05, 2020 8:25 am
How do you load all the textures for a single model? In noesis it will only load one file

viewtopic.php?f=10&t=21679&start=45#p160417

Thanks so much!
## Post #203
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2020-06-05T09:26:40+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

I have MOD (modification) model from atelier ryza. But it look like have some error or maybe just me can't open it.

this is the file
[https://mega.nz/file/bHAxBQwb#UhD0HqVkx ... 4czxamqcvw](https://mega.nz/file/bHAxBQwb#UhD0HqVkxuM--zFtUorN4ZzraRhkGCqO24czxamqcvw)
## Post #204
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-05T13:24:32+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from alictzelt ↑Fri Jun 05, 2020 5:26 pm at Fri Jun 05, 2020 5:26 pm
>
> 
I have MOD (modification) model from atelier ryza. But it look like have some error or maybe just me can't open it.

this is the file
https://mega.nz/file/bHAxBQwb#UhD0HqVkx ... 4czxamqcvw

These files are corrupted. The g1t are wrong values in the texture offsets section which completely breaks the parser after texture 4.
The g1m file had a wrong G1MS size section (off by 4) which broke the parser too. 


Why is this file so big though ? The Ryza samples I got from other people were much lighter, this one takes much more time to load
## Post #205
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-06T00:33:15+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

How do i find the animations for Persona 5 scramble? I followed this [viewtopic.php?f=10&t=21679&start=60#p160886](https://forum.xentax.com/viewtopic.php?f=10&t=21679&start=60#p160886) but it was really confusing.
## Post #206
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2020-06-06T05:47:52+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Fri Jun 05, 2020 9:24 pm at Fri Jun 05, 2020 9:24 pm
>
> 

These files are corrupted. The g1t are wrong values in the texture offsets section which completely breaks the parser after texture 4.
The g1m file had a wrong G1MS size section (off by 4) which broke the parser too. 

Why is this file so big though ? The Ryza samples I got from other people were much lighter, this one takes much more time to load

What I have to do to make it work? At least I can get the model + bones for moving without the textures if the g1t not working
## Post #207
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-06T20:34:12+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from qs12 ↑Sat Jun 06, 2020 8:33 am at Sat Jun 06, 2020 8:33 am
>
> 
How do i find the animations for Persona 5 scramble? I followed this viewtopic.php?f=10&t=21679&start=60#p160886 but it was really confusing.

Eh, I can make another example I guess but you have more questions better ask on her thread though, I almost didn't touch anything related to RDB, she took care of all the extraction stuff while I worked on the files directly.
## Post #208
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-06T20:45:07+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from alictzelt ↑Sat Jun 06, 2020 1:47 pm at Sat Jun 06, 2020 1:47 pm
>
> 
Joschka wrote: ↑Fri Jun 05, 2020 9:24 pm

These files are corrupted. The g1t are wrong values in the texture offsets section which completely breaks the parser after texture 4.
The g1m file had a wrong G1MS size section (off by 4) which broke the parser too. 

Why is this file so big though ? The Ryza samples I got from other people were much lighter, this one takes much more time to load


What I have to do to make it work? At least I can get the model + bones for moving without the textures if the g1t not working

Replace the byte at offset 32. Put 30 instead of 34. For g1t it's fixable too but you'll need some knowledge about the g1t format.
Anyways I don't know where you got these broken files (dumped from memory or something I guess) but I'd recommend doing a clean extraction with Cethleann if you want proper assets which are not 4 times the size of the correct ones
## Post #209
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-06T22:41:13+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Okay I got them extracted but the tool doesn't read .g1a files
## Post #210
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-06T22:55:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from qs12 ↑Sun Jun 07, 2020 6:41 am at Sun Jun 07, 2020 6:41 am
>
> 
Okay I got them extracted but the tool doesn't read .g1a files

Check the options, instructions are on the github repo.
## Post #211
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2020-06-06T23:18:19+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Jun 07, 2020 4:45 am at Sun Jun 07, 2020 4:45 am
>
> 
Replace the byte at offset 32. Put 30 instead of 34. For g1t it's fixable too but you'll need some knowledge about the g1t format.
Anyways I don't know where you got these broken files (dumped from memory or something I guess) but I'd recommend doing a clean extraction with Cethleann if you want proper assets which are not 4 times the size of the correct ones

finally.. now its work, its take a lot time when parsing the mesh, but its ok
I got the files from fanmod, so its unofficial mod.

Actually I have another fanmod files, all files broken. Unfortunately this way not work for another files.
Can you give me an advice how to find wrong value and how to fix it, like Replace the byte at offset 32. Put 30 instead of 34.
## Post #212
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-07T08:07:25+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from alictzelt ↑Sun Jun 07, 2020 7:18 am at Sun Jun 07, 2020 7:18 am
>
> 

finally.. now its work, its take a lot time when parsing the mesh, but its ok
I got the files from fanmod, so its unofficial mod.
Yeah it takes some time because it has many more polys. Ryza's ingame models are usually around 1Mo I think while this one is 4 times bigger.

> Reply from alictzelt ↑Sun Jun 07, 2020 7:18 am at Sun Jun 07, 2020 7:18 am
>
> 
Actually I have another fanmod files, all files broken. Unfortunately this way not work for another files.
Can you give me an advice how to find wrong value and how to fix it, like Replace the byte at offset 32. Put 30 instead of 34.

You would need some knowledge about the formats to fix the files. I can take a quick look if you upload samples but I can't give genera advice, unless the g1m is broken in a similar way
## Post #213
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2020-06-07T13:23:34+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Jun 07, 2020 4:07 pm at Sun Jun 07, 2020 4:07 pm
>
> 
You would need some knowledge about the formats to fix the files. I can take a quick look if you upload samples but I can't give genera advice, unless the g1m is broken in a similar way

what about this, look like file size is normal
[https://mega.nz/file/PW4jnJaT#LvFZ5MsBw ... 8GNHGR5oss](https://mega.nz/file/PW4jnJaT#LvFZ5MsBwqxK2UrRH5FQEMYnyZBceJYjZ8GNHGR5oss)
## Post #214
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-07T14:54:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from alictzelt ↑Sun Jun 07, 2020 9:23 pm at Sun Jun 07, 2020 9:23 pm
>
> 
what about this, look like file size is normal

Some semantics have weird values, I'd need to edit the script to account for some stuff but I don't want to do that since I never saw a "real" g1m with these issues, sorry.
## Post #215
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-06-13T16:45:27+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

When I load a DOA6 model file using the script, G1M mesh loads perfectly but why won't textures show on it?

There are two windows when I open the G1M file:
1st one for texture files: I select the first g1t file, inside the folder where all g1t textures are located (kidsalb.g1t, kidsnmh.g1t, etc.)
2nd one for skeleton file: I select the G1M file.
## Post #216
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-13T19:46:23+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Thony ↑Sun Jun 14, 2020 12:45 am at Sun Jun 14, 2020 12:45 am
>
> 
When I load a DOA6 model file using the script, G1M mesh loads perfectly but why won't textures show on it?

There are two windows when I open the G1M file:
1st one for texture files: I select the first g1t file, inside the folder where all g1t textures are located (kidsalb.g1t, kidsnmh.g1t, etc.)
2nd one for skeleton file: I select the G1M file.

Yes that's because the multitexture g1t files are split in several ones in games with RDB. You need to recombine all of them in a single g1t file using the method here [viewtopic.php?f=10&t=21679&start=45#p160417](https://forum.xentax.com/viewtopic.php?f=10&t=21679&start=45#p160417) 
Also you can put bLoadG1MS to False for DOA6 so you won't have to choose the same G1M everytime since in DOA6 the file has the skeleton too
## Post #217
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-06-15T14:54:39+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Jun 14, 2020 3:46 am at Sun Jun 14, 2020 3:46 am
>
> 
Yes that's because the multitexture g1t files are split in several ones in games with RDB. You need to recombine all of them in a single g1t file using the method here viewtopic.php?f=10&t=21679&start=45#p160417 
Also you can put bLoadG1MS to False for DOA6 so you won't have to choose the same G1M everytime since in DOA6 the file has the skeleton too

It's a bit complex. For future reference, could you please make a quick guide with step-by-step pictures?
## Post #218
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-16T10:55:26+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Thony ↑Mon Jun 15, 2020 10:54 pm at Mon Jun 15, 2020 10:54 pm
>
> 
Joschka wrote: ↑Sun Jun 14, 2020 3:46 am
Yes that's because the multitexture g1t files are split in several ones in games with RDB. You need to recombine all of them in a single g1t file using the method here viewtopic.php?f=10&t=21679&start=45#p160417 
Also you can put bLoadG1MS to False for DOA6 so you won't have to choose the same G1M everytime since in DOA6 the file has the skeleton too


It's a bit complex. For future reference, could you please make a quick guide with step-by-step pictures?

What's your issue ? The post is a bit intimidating but the most important thing you need to get out of it is the following command line, this is all you need to know :

```
-g Scramble
X:\path\to\doa6output\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb 
X:\path\to\doa6output\MaterialEditor\g1t 
X:\path\to\doa6output\CharacterEditor\ktid\H0000_Joker.ktid 
```


From one character to another you'll only need to change the last line with the corresponding name. Also the game name will be different, you'll need to replace "Scramble" by "DeadOrAlive6".
## Post #219
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-06-16T12:31:57+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Tue Jun 16, 2020 6:55 pm at Tue Jun 16, 2020 6:55 pm
>
> 
Code: Select allNyotengu.KTID.exe
-g Scramble
X:\path\to\doa6output\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb 
X:\path\to\doa6output\MaterialEditor\g1t 
X:\path\to\doa6output\CharacterEditor\ktid\H0000_Joker.ktid

What are the first steps before you get to type this?
## Post #220
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-06-16T14:03:41+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Replying form the model resource thread
I'm working with animations from Blue reflection (anims are g1a, models are same format as atelier, gz, elixir etc.) and in blender/noesis the animation seems fine(facials animation) but once exported the bones are very stretched, i already tried scaling model, applying rotation and scale, clearing delta, nothing seems to work, reminds me of doa6 animations before updating
Here screenshots
[https://sta.sh/2wwph9dspyj](https://sta.sh/2wwph9dspyj) noesis vs exported, it's clear to tell which one is noesis
## Post #221
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-16T17:06:40+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Thony ↑Tue Jun 16, 2020 8:31 pm at Tue Jun 16, 2020 8:31 pm
>
> 
Joschka wrote: ↑Tue Jun 16, 2020 6:55 pm
Code: Select allNyotengu.KTID.exe
-g Scramble
X:\path\to\doa6output\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb 
X:\path\to\doa6output\MaterialEditor\g1t 
X:\path\to\doa6output\CharacterEditor\ktid\H0000_Joker.ktid 


What are the first steps before you get to type this?

Download Cethleann from the other thread and type that stuff in a command prompt. If you have more questions about extraction and stuff ask directly on the other thread since it's not related to model viewing.

> Reply from Makoto ↑Tue Jun 16, 2020 10:03 pm at Tue Jun 16, 2020 10:03 pm
>
> 
Replying form the model resource thread
I'm working with animations from Blue reflection (anims are g1a, models are same format as atelier, gz, elixir etc.) and in blender/noesis the animation seems fine(facials animation) but once exported the bones are very stretched, i already tried scaling model, applying rotation and scale, clearing delta, nothing seems to work, reminds me of doa6 animations before updating
Here screenshots
https://sta.sh/2wwph9dspyj noesis vs exported, it's clear to tell which one is noesis

Got the files ? (don't upload on that deviantart stuff please, it's annoying to log in just to DL)
## Post #222
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-06-16T21:50:57+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Jun 17, 2020 1:06 am at Wed Jun 17, 2020 1:06 am
>
> 
Thony wrote: ↑Tue Jun 16, 2020 8:31 pm
Joschka wrote: ↑Tue Jun 16, 2020 6:55 pm
Code: Select allNyotengu.KTID.exe
-g Scramble
X:\path\to\doa6output\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb 
X:\path\to\doa6output\MaterialEditor\g1t 
X:\path\to\doa6output\CharacterEditor\ktid\H0000_Joker.ktid 


What are the first steps before you get to type this?


Download Cethleann from the other thread and type that stuff in a command prompt. If you have more questions about extraction and stuff ask directly on the other thread since it's not related to model viewing.

It is.
If the thread title is Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...), I expect to load and to view a DOA6 model without having to type stuff in a command prompt first.
## Post #223
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-06-16T23:26:31+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

How to extract and view a DOA6 model on Noesis with this script and with Cethleann:

On your desktop, create a new folder and name it model (or anything you like).
Open it and create 3 folders. Name them:
CharacterEditor
KIDSSystemResource
MaterialEditor

Open the CharacterEditor folder. Inside of it, create a folder and name it ktid.
Open the KIDSSystemResource folder. Inside of it, create a folder and name it kidsobjdb.
Open the MaterialEditor folder. Inside of it, create a folder and name it g1t.


Download rdbtool by vagonumero13 from this NSFW website to extract files from the game:
https://www.loverslab.com/topic/120211- ... tools-021/

Launch the qrdbtool.exe, and click on Open.

Navigate to where your Dead or Alive 6 folder is located and select it
(i.e. C:\Program Files\Steam\steamapps\common\Dead or Alive 6).


Load the file CharacterEditor.rdb 
Extract the g1m file of the model wherever you want.
Extract the ktid file of the model into the ktid folder.

NYO_COS_002.g1m
NYO_COS_002.ktid

If you get a window asking:
Do you want to store the files in a folder called CharacterEditor inside the selected folder?
Choose No.


Load the file KIDSSystemResource.rdb
Extract the file CharacterEditor.kidssingletondb.kidsobjdb into the kidsobjdb folder:
CharacterEditor.kidssingletondb.kidsobjdb

If you get a window asking:
Do you want to store the files in a folder called KIDSSystemResource inside the selected folder?
Choose No.


Load the file MaterialEditor.rdb
Extract the g1t textures of the model into the g1t folder.

MPR_Muscle_Character_NYOCOS002_a01_kidsalb.g1t
...
MPR_Muscle_Character_NYOCOS002_body_kidsalb.g1t
...


If you get a window asking:
Do you want to store the files in a folder called MaterialEditor inside the selected folder?
Choose No.



Download CethleannStandalone_netcore30 here:
[https://ci.appveyor.com/project/yretena ... /artifacts](https://ci.appveyor.com/project/yretenai/cethleann/build/artifacts)

Extract the files in a folder on your desktop. Name that folder Cethleann (or anything you like).
Open a command prompt and type:

```
cd %USERPROFILE%\Desktop\Cethleann
```

Press Enter.
Type:

```
Nyotengu.KTID.exe -g deadoralive6 %USERPROFILE%\Desktop\model\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb.kidsobjdb %USERPROFILE%\Desktop\model\MaterialEditor\g1t %USERPROFILE%\Desktop\model\CharacterEditor\ktid\NYO_COS_002.ktid
```


> Nyotengu.KTID.exe
>
> -g deadoralive6
>
> X:\path\to\doa6output\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb 
>
> X:\path\to\doa6output\MaterialEditor\g1t 
>
> X:\path\to\doa6output\CharacterEditor\ktid\H0000_Joker.ktid

If everything went well, a new G1T file got created inside the ktid folder.
NYO_COS_002.g1t

You can now load the g1m file with it and view the model with textures on Noesis.

Voilà!
## Post #224
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-06-17T09:01:13+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Jun 17, 2020 1:06 am at Wed Jun 17, 2020 1:06 am
>
> 
Thony wrote: ↑Tue Jun 16, 2020 8:31 pm
Joschka wrote: ↑Tue Jun 16, 2020 6:55 pm
Code: Select allNyotengu.KTID.exe
-g Scramble
X:\path\to\doa6output\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb 
X:\path\to\doa6output\MaterialEditor\g1t 
X:\path\to\doa6output\CharacterEditor\ktid\H0000_Joker.ktid 


What are the first steps before you get to type this?


Download Cethleann from the other thread and type that stuff in a command prompt. If you have more questions about extraction and stuff ask directly on the other thread since it's not related to model viewing.
Makoto wrote: ↑Tue Jun 16, 2020 10:03 pm
Replying form the model resource thread
I'm working with animations from Blue reflection (anims are g1a, models are same format as atelier, gz, elixir etc.) and in blender/noesis the animation seems fine(facials animation) but once exported the bones are very stretched, i already tried scaling model, applying rotation and scale, clearing delta, nothing seems to work, reminds me of doa6 animations before updating
Here screenshots
https://sta.sh/2wwph9dspyj noesis vs exported, it's clear to tell which one is noesis


Got the files ? (don't upload on that deviantart stuff please, it's annoying to log in just to DL)

 yeah, i know, i used it only to let you see example of pictures since it was fast, didn't know u had to log in even to just view them
load the "default" and then for skel load the file with same name without _default
[https://www.mediafire.com/file/wfvu6cqz ... e.zip/file](https://www.mediafire.com/file/wfvu6cqztgyox4g/Blue_Ref_Sample.zip/file)
## Post #225
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-17T10:51:04+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Thony ↑Wed Jun 17, 2020 5:50 am at Wed Jun 17, 2020 5:50 am
>
> 
Joschka wrote: ↑Wed Jun 17, 2020 1:06 am
Thony wrote: ↑Tue Jun 16, 2020 8:31 pm


What are the first steps before you get to type this?


Download Cethleann from the other thread and type that stuff in a command prompt. If you have more questions about extraction and stuff ask directly on the other thread since it's not related to model viewing.


It is.
If the thread title is Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...), I expect to load and to view a DOA6 model without having to type stuff in a command prompt first.

I mean yeah but there's a process of extraction and packing first to prepare the resources, all of that needs to be done with Cethleann. My script is built to read the final files.
But anyways you figured it out, keep in mind you can use Cethleann directly to extract the game and have the necessary folders directly extracted instead of vago's tools but that works too.

> Reply from Makoto ↑Wed Jun 17, 2020 5:01 pm at Wed Jun 17, 2020 5:01 pm
>
> 
Joschka wrote: ↑Wed Jun 17, 2020 1:06 am
Thony wrote: ↑Tue Jun 16, 2020 8:31 pm


What are the first steps before you get to type this?


Download Cethleann from the other thread and type that stuff in a command prompt. If you have more questions about extraction and stuff ask directly on the other thread since it's not related to model viewing.
Makoto wrote: ↑Tue Jun 16, 2020 10:03 pm
Replying form the model resource thread
I'm working with animations from Blue reflection (anims are g1a, models are same format as atelier, gz, elixir etc.) and in blender/noesis the animation seems fine(facials animation) but once exported the bones are very stretched, i already tried scaling model, applying rotation and scale, clearing delta, nothing seems to work, reminds me of doa6 animations before updating
Here screenshots
https://sta.sh/2wwph9dspyj noesis vs exported, it's clear to tell which one is noesis


Got the files ? (don't upload on that deviantart stuff please, it's annoying to log in just to DL)


 yeah, i know, i used it only to let you see example of pictures since it was fast, didn't know u had to log in even to just view them
load the "default" and then for skel load the file with same name without _default
https://www.mediafire.com/file/wfvu6cqz ... e.zip/file

Yeah I wasn't referring to the pictures you posted, I just had another user upload some models using that stuff and had to log in with my never used DA profile just to get them so that was annoying.

Anyways, I misunderstood your issue : the anims look fine in Noesis and Blender right ? I guess the problem comes from the Blender exporter when you export it again then ? If so I can't really help, better ask on a Blender forum, unless I missed something.
## Post #226
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-06-17T11:42:45+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Jun 17, 2020 6:51 pm at Wed Jun 17, 2020 6:51 pm
>
> 
Thony wrote: ↑Wed Jun 17, 2020 5:50 am
Joschka wrote: ↑Wed Jun 17, 2020 1:06 am


Download Cethleann from the other thread and type that stuff in a command prompt. If you have more questions about extraction and stuff ask directly on the other thread since it's not related to model viewing.


It is.
If the thread title is Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...), I expect to load and to view a DOA6 model without having to type stuff in a command prompt first.


I mean yeah but there's a process of extraction and packing first to prepare the resources, all of that needs to be done with Cethleann. My script is built to read the final files.
But anyways you figured it out, keep in mind you can use Cethleann directly to extract the game and have the necessary folders directly extracted instead of vago's tools but that works too.
Makoto wrote: ↑Wed Jun 17, 2020 5:01 pm
Joschka wrote: ↑Wed Jun 17, 2020 1:06 am


Download Cethleann from the other thread and type that stuff in a command prompt. If you have more questions about extraction and stuff ask directly on the other thread since it's not related to model viewing.



Got the files ? (don't upload on that deviantart stuff please, it's annoying to log in just to DL)


 yeah, i know, i used it only to let you see example of pictures since it was fast, didn't know u had to log in even to just view them
load the "default" and then for skel load the file with same name without _default
https://www.mediafire.com/file/wfvu6cqz ... e.zip/file


Yeah I wasn't referring to the pictures you posted, I just had another user upload some models using that stuff and had to log in with my never used DA profile just to get them so that was annoying.

Anyways, I misunderstood your issue : the anims look fine in Noesis and Blender right ? I guess the problem comes from the Blender exporter when you export it again then ? If so I can't really help, better ask on a Blender forum, unless I missed something.
yeah that's my issue, thought t was blender related because doa6 used to be fine before exporting and then got fixed and was fine both in blender and once exported, i'll look around, thanks
## Post #227
- Username: Thony
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jun 30, 2017 3:54 am
- Post datetime: 2020-06-17T15:13:57+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Wed Jun 17, 2020 6:51 pm at Wed Jun 17, 2020 6:51 pm
>
> 
I mean yeah but there's a process of extraction and packing first to prepare the resources, all of that needs to be done with Cethleann. My script is built to read the final files.
But anyways you figured it out, keep in mind you can use Cethleann directly to extract the game and have the necessary folders directly extracted instead of vago's tools but that works too.

Good to know, though the integrated UI of his tool simplifies the process.
## Post #228
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-06-17T16:32:53+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

@Joschka, can you add support for Nioh 2 anims and models?
## Post #229
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-18T09:38:01+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Tosyk ↑Thu Jun 18, 2020 12:32 am at Thu Jun 18, 2020 12:32 am
>
> 
@Joschka, can you add support for Nioh 2 anims and models?

Yes. 
The format is the same as OPPW4 but it seems that my research on some chunks wasn't completely accurate since it breaks on some Nioh 2 models. Going to work on it when I have the time.
The animation format is still the same.
## Post #230
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-19T12:34:17+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Fixes were easy enough, I missed something obvious when working on OPPW4.

SCRIPT UPDATED
-new textures formats added
-NUNO v32 fixes

Nioh 2 models should now work, only tested a few as I didn't have much time so report issues if you find some


A few notes about working on that game with the plugin :
Extraction
-The g1m and g1t files are in the pg1m containers. Use the latest version of Cethleann to unpack these : drag and drop the pg1m on Cethleann.Unbundler.exe to get a g1mpack and an exarg container. Drag and drop these once more to get the g1m and g1t.
-The animation files are in the pg2a containers. Drag and drop them on the Unbundler to get the anim files.

Models
-Some models are high poly so loading some of them will take a bit of time. I'll need to rewrite some code parts and make a C++ native plugin at some point for performance but I don't have the time for that right now.
-Some models are split into different parts. Use the model merger to load all of them at once, with the option value set at 1 to merge the bones (in the merge file). If you do that make sure that the skeleton g1m is not next to the other otherwise it won't work
-For those models split in parts, I recommend using the console options to not have to specify the skeleton everytime (set them in Tools > data viewer > persistent settings > other > default preview commands). I recommend setting up a "resource" folder where you'll put the associated g1t and skeleton file, that way you won't have to change the path everytime, in the console, just change the skeleton and g1t file for each model.
Make sure to remove these commands when you're done

Animations
-Animations are working but the split models make it a bit difficult to work with them since the merger doesn't work with anims without duplicating bones. Here's a possible workflow :

Step 1 : Load the model in Noesis, without animations. Then export it.


Step 2 : Turn the anim loading option on (either individual or folder), load the skeleton g1m file (0001.g1m) and put all the animations that you want on that file. Export that file too.


So now you have the model in one file and the animations in another file, you just need to merge them using a 3d software. Here's a possible workflow to do that in Blender, there may be a better way :

Step 1 : Import the animation file in Blender and directly save it as a blend file. I'll call it animation.blend

Step 2 : Make a new scene in Blender and now import your model file. Now go to "File" > "append", double click on the animation.blend then go to the "actions" folder and double-click on the file inside it (there should only be one action file unless you added more or split them in the animation.blend, if you just followed the steps above there'll only be one).

Step 3 : Select your armature. Now go to the action editor and click on the icon next to the "New" button. I repeat, select the icon, not the new button. . Then choose the action you just appended in the list.


That's it, the merged model will now have all the animations without duplicate bones.


Keep in mind that the physics meshes will not be animated as usual, only the driver meshes will follow the movement. So make sure to rig them properly as usual beforehand.
## Post #231
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2020-06-24T19:26:45+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

do you think you could support gundam dynasty reborn? 
[https://cdn.discordapp.com/attachments/ ... 21/002.g1m](https://cdn.discordapp.com/attachments/717987484587393084/725431678138449921/002.g1m)
## Post #232
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-06-24T20:16:51+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Rin ↑Thu Jun 25, 2020 3:26 am at Thu Jun 25, 2020 3:26 am
>
> 
do you think you could support gundam dynasty reborn? 
https://cdn.discordapp.com/attachments/ ... 21/002.g1m

It crashes because the skeleton g1m is missing. Probably 001.g1m or something. 
Other than that the model seems to be working, you just need to find the associated skeleton and it should work
## Post #233
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-07-01T01:10:51+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

This atelier game model would not opening  [https://sta.sh/028k1k8tnnc6](https://sta.sh/028k1k8tnnc6)
## Post #234
- Username: kenshin20080
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 20, 2020 11:47 pm
- Post datetime: 2020-07-12T12:01:36+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Nice plugin! Thank you so much!
## Post #235
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2020-07-30T07:39:51+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Having some issues with a few models from the new Fairy Tail game.

Keeps giving this error:



err.png (7.29 KiB) Viewed 338 times


[https://drive.google.com/file/d/1ciDbzv ... sp=sharing](https://drive.google.com/file/d/1ciDbzvc7sXNWu9jFG6ABxgxFoEAkMZ-o/view?usp=sharing)

If you could take a look at these that'd be great thanks!
## Post #236
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-30T12:23:28+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from anime663 ↑Thu Jul 30, 2020 3:39 pm at Thu Jul 30, 2020 3:39 pm
>
> 
Having some issues with a few models from the new Fairy Tail game.

Keeps giving this error:
err.png

https://drive.google.com/file/d/1ciDbzv ... sp=sharing

If you could take a look at these that'd be great thanks!

Should be fixed with the latest version
## Post #237
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-07-30T16:53:36+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hyrule Warriors animations seem pretty jittery...i don't remember them being like that last time i used the script
## Post #238
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-30T20:48:06+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from CosmicDreams ↑Fri Jul 31, 2020 12:53 am at Fri Jul 31, 2020 12:53 am
>
> 
Hyrule Warriors animations seem pretty jittery...i don't remember them being like that last time i used the script

Samples ?
## Post #239
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-07-31T17:28:34+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Fri Jul 31, 2020 4:48 am at Fri Jul 31, 2020 4:48 am
>
> 
CosmicDreams wrote: ↑Fri Jul 31, 2020 12:53 am
Hyrule Warriors animations seem pretty jittery...i don't remember them being like that last time i used the script


Samples ?
[https://cdn.discordapp.com/attachments/ ... 554/hw.zip](https://cdn.discordapp.com/attachments/419711036837330956/738810187997118554/hw.zip)
Zelda + G1A anims from COMMON_FEMALE.bin.gz
## Post #240
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-07-31T18:03:38+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from CosmicDreams ↑Sat Aug 01, 2020 1:28 am at Sat Aug 01, 2020 1:28 am
>
> 
Joschka wrote: ↑Fri Jul 31, 2020 4:48 am
CosmicDreams wrote: ↑Fri Jul 31, 2020 12:53 am
Hyrule Warriors animations seem pretty jittery...i don't remember them being like that last time i used the script


Samples ?

https://cdn.discordapp.com/attachments/ ... 554/hw.zip
Zelda + G1A anims from COMMON_FEMALE.bin.gz

Should be fixed with the latest update, thanks for the heads up. Some interpolation changes I made on the recent g2a format weren't suitable for the old g1a format used by HW.
## Post #241
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-08-02T02:05:44+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

From Fairy Tail
Is this cloth driver and bones are at wrong position compare to her dress, or this is normal?
## Post #242
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-02T09:02:46+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hard to say with just a screenshot, I don't have the game myself and I'm not familiar with the series.
I'd say it's correct, they'd just simulate the bottom of the dress. If the dress is split in two submeshes (upper and lower) that's probably the case
## Post #243
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-08-04T10:14:17+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

wow  Noesis always crashed when ever I try to merge character models from Nioh
## Post #244
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-08-04T12:52:57+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Jan 26, 2020 6:19 am at Sun Jan 26, 2020 6:19 am
>
> 
Grab the tool on my github repository, check the readme for some usage instructions (Link down below)...

First of all thanks for the tool   
Is it possible to make a list of game supported by this tool?
## Post #245
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-04T17:00:07+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from ngovandang ↑Tue Aug 04, 2020 6:14 pm at Tue Aug 04, 2020 6:14 pm
>
> 
wow  Noesis always crashed when ever I try to merge character models from Nioh
[viewtopic.php?f=16&t=21666&start=225#p164319](https://forum.xentax.com/viewtopic.php?f=16&t=21666&start=225#p164319)

> Reply from Drawing ↑Tue Aug 04, 2020 8:52 pm at Tue Aug 04, 2020 8:52 pm
>
> 
First of all thanks for the tool   
Is it possible to make a list of game supported by this tool?

Np, glad you like it.
There are a LOT of them from what I've been told by different users so I'd need to make some research and cross reference all the different posts I saw to make an exhaustive list.
Out of my head :

-Dissidia NT
-Dissidia Opera Omnia
-Fire Emblem Three Houses
-Many Atelier games
-Fire Emblem Warriors
-Hyrule Warriors
-Dead or Alive 6
-Persona 5 Scramble
-Fairy Tale RPG
-Marvel Ultimate Alliance 3
-Berserk
-One Piece Pirate Warriors 3
-One Piece Pirate Warriors 4
-Dragon Quest Builders 2
-Dragon Quest Heroes
-Dragon Quest Heroes 2
-Nioh
-Nioh 2
-Toukiden
-Toukiden II
-Dynasty Warriors 7
-Dynasty Warriors 8
-Dynasty Warriors 9
-Warriors All Stars
-Warriors Orochi 4
-Fatal Frame (WiiU)
-BladeStorm Nightmare
-Deception IV Blood Ties
-Fist of the North Star 2
-Samurai Warriors 4-II
-Warriors Legend of Troy
-Dynasty Warriors Online
-Nobunaga Online
-Attack of Titan 2
-Night of Azure 2
-Ar noSurge

There are probably more that I forgot, basically pretty much any Koei Tecmo game that uses that g1m format should work with the plugin. Big thanks to Allanoon and einherjar007 for all the testing
## Post #246
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-08-04T23:06:01+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Does it work with Arslan: The Warriors of Legend?
## Post #247
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-05T11:11:59+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from andree ↑Wed Aug 05, 2020 7:06 am at Wed Aug 05, 2020 7:06 am
>
> 
Does it work with Arslan: The Warriors of Legend?

If it uses g1m probably. I don't have the game so I can't tell.
## Post #248
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2020-08-06T16:55:38+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

It's working with fairy tail:

[https://www.youtube.com/watch?v=YFsuYsjiXhg](https://www.youtube.com/watch?v=YFsuYsjiXhg)
## Post #249
- Username: dukemagus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 18, 2014 4:58 am
- Post datetime: 2020-08-30T03:22:21+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

A bit of a technical question: i'm examining some g1t files from Final Fantasy Dissidia Opera Omnia and they are composed of multiple images with different sizes. 

While a few of them are packs of character textures (kinda reminds me of UDIMs), others seem like packs of random stuff

They aren't an animation and there's no way to fit them neatly in a power of 2 square without losing a lot of space. Also while some of them look like a flat texture for a background prop, others are decorative images for the UI

What were these files meant to be? why would they pack it in this way rather than by what each component uses?
## Post #250
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-30T15:42:12+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from dukemagus ↑Sun Aug 30, 2020 11:22 am at Sun Aug 30, 2020 11:22 am
>
> 
A bit of a technical question: i'm examining some g1t files from Final Fantasy Dissidia Opera Omnia and they are composed of multiple images with different sizes. 

While a few of them are packs of character textures (kinda reminds me of UDIMs), others seem like packs of random stuff

They aren't an animation and there's no way to fit them neatly in a power of 2 square without losing a lot of space. Also while some of them look like a flat texture for a background prop, others are decorative images for the UI

What were these files meant to be? why would they pack it in this way rather than by what each component uses?

I didn't play/datamine that game, could you send me a sample of what you're talking about ? A friend of mine will take a look.
## Post #251
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-08-30T16:33:20+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Does anyone know if Nioh 2's files are available publicly anywhere yet? If they are private only that's fine, I just wanted to make sure.

Cheers
## Post #252
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-08-30T20:52:17+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Aug 30, 2020 11:42 pm at Sun Aug 30, 2020 11:42 pm
>
> 
I didn't play/datamine that game, could you send me a sample of what you're talking about ? A friend of mine will take a look.

If he does, you could try to look at the characters, weapon and monsters textures, because the old tool that exist for that format of texture, usually unpack them without alpha.
## Post #253
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-30T21:30:09+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from gep55 ↑Mon Aug 31, 2020 12:33 am at Mon Aug 31, 2020 12:33 am
>
> 
Does anyone know if Nioh 2's files are available publicly anywhere yet? If they are private only that's fine, I just wanted to make sure.

Cheers

I don't think so

> Reply from Darkhowlings ↑Mon Aug 31, 2020 4:52 am at Mon Aug 31, 2020 4:52 am
>
> 
Joschka wrote: ↑Sun Aug 30, 2020 11:42 pm
I didn't play/datamine that game, could you send me a sample of what you're talking about ? A friend of mine will take a look.


If he does, you could try to look at the characters, weapon and monsters textures, because the old tool that exist for that format of texture, usually unpack them without alpha.

You mean that the script has a wrong output ? Or are there texture files that are not g1t files that are not extracted correctly by an existing tool ?
I did a few tests on the g1t textures of DFOO a while ago and it looked ok to me at that time
## Post #254
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-08-31T04:34:39+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Mon Aug 31, 2020 5:30 am at Mon Aug 31, 2020 5:30 am
>
> 
You mean that the script has a wrong output ? Or are there texture files that are not g1t files that are not extracted correctly by an existing tool ?
I did a few tests on the g1t textures of DFOO a while ago and it looked ok to me at that time

No. The old tool does the job and unpack all the textures without problem. But, when it comes to Characters, Weapon and Monster textures, it unpack them as PNG, but without Alpha, so they don't have any transparency.
## Post #255
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-08-31T15:56:19+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Darkhowlings ↑Mon Aug 31, 2020 12:34 pm at Mon Aug 31, 2020 12:34 pm
>
> 
Joschka wrote: ↑Mon Aug 31, 2020 5:30 am
You mean that the script has a wrong output ? Or are there texture files that are not g1t files that are not extracted correctly by an existing tool ?
I did a few tests on the g1t textures of DFOO a while ago and it looked ok to me at that time


No. The old tool does the job and unpack all the textures without problem. But, when it comes to Characters, Weapon and Monster textures, it unpack them as PNG, but without Alpha, so they don't have any transparency.

You are right, I looked at a few samples and there was some weird stuff going on. Yretenai pushed some fixes, try to download the latest version of the script and let us know if you find any issues.
## Post #256
- Username: dukemagus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 18, 2014 4:58 am
- Post datetime: 2020-08-31T19:58:48+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Joschka ↑Sun Aug 30, 2020 11:42 pm at Sun Aug 30, 2020 11:42 pm
>
> 

I didn't play/datamine that game, could you send me a sample of what you're talking about ? A friend of mine will take a look.
[http://www.mediafire.com/file/c0x8yvrl3f7gn5q/file](http://www.mediafire.com/file/c0x8yvrl3f7gn5q/file)

These are some of the textures i'm curious about. that black and white texture seems useless, use an entirely new texture just to change the character expression seems wasteful and the environment textures are packed with completely different sizes. never seen things made this way
## Post #257
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2020-08-31T21:50:22+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from dukemagus ↑Tue Sep 01, 2020 3:58 am at Tue Sep 01, 2020 3:58 am
>
> 
Joschka wrote: ↑Sun Aug 30, 2020 11:42 pm

I didn't play/datamine that game, could you send me a sample of what you're talking about ? A friend of mine will take a look.

http://www.mediafire.com/file/c0x8yvrl3f7gn5q/file

These are some of the textures i'm curious about. that black and white texture seems useless, use an entirely new texture just to change the character expression seems wasteful and the environment textures are packed with completely different sizes. never seen things made this way

Hi there! I've been datamining DFFOO for a while now so I can help with this. 

The character textures have other more than one layer for "blinking" and other texture changing animations. So that's what you're seeing in those files that start with "C".

Those "S###.g1t.dz" files are textures for scenery (or maps) files. They have matching model files with the same numbers, but .bin files like "S###.bin.dz". (Thanks to Joschka here) After you unzip the file .bin file, if you rename it to .g1m, it will load in Noesis with the match texture
## Post #258
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-01T08:33:14+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from hellacopters ↑Tue Sep 01, 2020 5:50 am at Tue Sep 01, 2020 5:50 am
>
> 
dukemagus wrote: ↑Tue Sep 01, 2020 3:58 am
Joschka wrote: ↑Sun Aug 30, 2020 11:42 pm

I didn't play/datamine that game, could you send me a sample of what you're talking about ? A friend of mine will take a look.

http://www.mediafire.com/file/c0x8yvrl3f7gn5q/file

These are some of the textures i'm curious about. that black and white texture seems useless, use an entirely new texture just to change the character expression seems wasteful and the environment textures are packed with completely different sizes. never seen things made this way


Hi there! I've been datamining DFFOO for a while now so I can help with this. 

The character textures have other more than one layer for "blinking" and other texture changing animations. So that's what you're seeing in those files that start with "C".

Those "S###.g1t.dz" files are textures for scenery (or maps) files. They have matching model files with the same numbers, but .bin files like "S###.bin.dz". (Thanks to Joschka here) After you unzip the file .bin file, if you rename it to .g1m, it will load in Noesis with the match texture

To add to this (keep in mind this is only assumptions since I didn't play the game) :
-the whole texture replacement just for blinking I'm not so sure about it. Maybe it was more convenient for them not to make a submesh just for the eyes' region and not to make a single texture for that. I'm a bit confused about it too since I saw other games having a submesh just for that region and have a texture with all the different expressions, then they just used UV sliding to switch between them.
-The black and white texture may be a specular map ?
-The different textures are packed to load all of them directly, it's faster to load an archive instead of files one by one. The different sizes are because the resolution must change depending of the meshes : for a big mesh you want a higher res texture otherwise it'll look very blurry since it's spread all across the mesh for example. For minor elements it's not that big of a deal.
## Post #259
- Username: Jokerfire94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 08, 2020 4:15 pm
- Post datetime: 2020-09-08T08:39:23+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hello im having trouble i did download the .py file that i then transofmred into a txt file to modify it then i put them in the python file but i get a debug log when i open noesis and i cant acces to any doa6 facial animation. Can someone tell me what am i doing wrong ?
[Capture.PNG](https://xentaxbackup.github.io/file/18709_Capture.PNG)
## Post #260
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-08T10:18:41+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

If you don't want the log put the bLog option to False in the script.
For animations put the bLoadG1AG2A or bLoadG1AG2AFolder to True. For face anims put bDOA6FaceAnims to True too, put back to False for body anims.
Then just select the g1m model and during loading you'll be able to choose the animations.
## Post #261
- Username: Jokerfire94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 08, 2020 4:15 pm
- Post datetime: 2020-09-08T15:32:19+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

You have my thanks i was able to make it work somehow(saying that cuz im sure i had the doa6 facial  and the  bLoadG1AG2A/bLoadG1AG2AFolder to True) but now it works thanks again! also i am able to get the texture file but for some reason its all in the eye like that
[encore tst.PNG](https://xentaxbackup.github.io/file/18711_encore tst.PNG)
## Post #262
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-08T16:57:38+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Jokerfire94 ↑Tue Sep 08, 2020 11:32 pm at Tue Sep 08, 2020 11:32 pm
>
> 
You have my thanks i was able to make it work somehow(saying that cuz im sure i had the doa6 facial  and the  bLoadG1AG2A/bLoadG1AG2AFolder to True) but now it works thanks again! also i am able to get the texture file but for some reason its all in the eye like that

That's probably because you used a single G1T file, the games with RDB like DOA6 need them to be repacked. 
Check that tutorial here for more info : [viewtopic.php?f=16&t=21666&start=210#p164234](https://forum.xentax.com/viewtopic.php?f=16&t=21666&start=210#p164234)
That'll give you a new g1t that will work this time.
## Post #263
- Username: Jokerfire94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 08, 2020 4:15 pm
- Post datetime: 2020-09-08T18:21:13+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

While im here i was wondering ( i am a newbie sorry) i used only one g1a and was able to see it in noesis but i can still import it as an fbx file to modify it in blender am i doing it wrong ? like do i have to use several g1a file then import it as an fbx file to start modifying it and then put it back as an g1a file ? (sorry if it look a bit confused i am doing this without any idea i appreciate the help!) and i also got that error when i tried to do the tuto
[ff.PNG](https://xentaxbackup.github.io/file/18713_ff.PNG)
## Post #264
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-08T20:05:57+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

If you're able to see the model in Noesis then you can export it using File->Export from preview to FBX and then the FBX file will be importable in Blender. It shouldn't matter if you have one or many animations.

This plugin is only for extraction for now so re-exporting to g1a/g1m will need other tools (I know that vago on LL has an animation repacker but I didn't try it myself).

That error is weird, can you upload the g1m and g1a that give the error please ?
## Post #265
- Username: Jokerfire94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 08, 2020 4:15 pm
- Post datetime: 2020-09-08T20:50:57+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

[https://mega.nz/file/IiJxQKpZ#SAspzsNqH ... hnPXZ2AbTM](https://mega.nz/file/IiJxQKpZ#SAspzsNqHwoSC6zZCdZp_6X-byc-pHj7QhnPXZ2AbTM)
[https://mega.nz/file/FqYDXIII#WZuzdKHIE ... EP29p7uYic](https://mega.nz/file/FqYDXIII#WZuzdKHIEGPR5iuI0L2EltW67FljvGOw8EP29p7uYic) 
here they are,quote that in the cmd i did recieve some error that said that some texture were missing or not here  like that and yeah i know for vago tools but i tried to make and fbx into a g1a didnt worked for now =/
[fff.PNG](https://xentaxbackup.github.io/file/18715_fff.PNG)
## Post #266
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-09T10:02:06+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

> Reply from Jokerfire94 ↑Wed Sep 09, 2020 4:50 am at Wed Sep 09, 2020 4:50 am
>
> 
https://mega.nz/file/IiJxQKpZ#SAspzsNqH ... hnPXZ2AbTM
https://mega.nz/file/FqYDXIII#WZuzdKHIE ... EP29p7uYic 
here they are,quote that in the cmd i did recieve some error that said that some texture were missing or not here  like that and yeah i know for vago tools but i tried to make and fbx into a g1a didnt worked for now =/

Oh I meant the g1m and the animation file, since that error you got above came from the anim file apparently (maybe you used an animation on the wrong character ?)

For those unknown g1t files that's weird, can you try to do a clean extraction using Cethleann instead of vago's tools and repeat the previous steps ? 

```
Cethleann.DataExporter --rdb -g DeadOrAlive6 "path-to-extract" "pathToFiles"
```
## Post #267
- Username: Jokerfire94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 08, 2020 4:15 pm
- Post datetime: 2020-09-09T10:54:15+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

i have another question  because in the end the texture file isnt neccesary no ? i was able to check some animations without texture but then when i export the fbx file and put it into blender the size is way smaller than the one i get with vago tools , + when i tried to use the vago tools to make the fbx from noesis  into an g1a i got an error that says there is no animations im confused sorry
[https://mega.nz/file/BqYQkSLB#Rs7OW630H ... BpwqYsBwTA](https://mega.nz/file/BqYQkSLB#Rs7OW630Hz2CuGbtRi18Bst-hL1trIHcIBpwqYsBwTA)
[https://mega.nz/file/NyQ2CACJ#U_iURyUw_ ... v_YCsos6Ak](https://mega.nz/file/NyQ2CACJ#U_iURyUw_16liM2s8sQBAA4HNPvzlzEkRv_YCsos6Ak) 
And here are the animation file to use with to g1m i posted earlier
And yeah i will try with ceth
## Post #268
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-09T12:15:56+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Let's sum up real quick :

-the g1m file has the model
-the g1t file has the texture
-the g1a/g2a files have the animations

If you only want to see the animations, you don't need the g1t files indeed, I thought you wanted to see the textured models. So forget about the g1t files. You can just put the bLoadG1T file option to False or press "Cancel" when you get asked to give a G1T file.
The facial animations are additive so you need to put the "bDOA6FaceAnims" to True if you want to preview them, otherwise the mesh will be completely deformed. If you want to see body animations you need to put the option back to False.

Your error above comes from the fact that you tried to see some FACIAL animations on a BODY model. The anims you uploaded are supposed to be applied to the head model so that's why it's crashing.

For the size difference I think vago's models are 100 times bigger than mine for some reason, that's just a scale parameter, you can probably just scale the model in Blender or I can add a scale parameter if you want.

For reimporting I'm not familiar with vago's tools for animations so you should probably ask him directly.
## Post #269
- Username: Jokerfire94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 08, 2020 4:15 pm
- Post datetime: 2020-09-09T12:25:19+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

Hey unlucky i just finished to impot every file but its true for the animation file it was mb also yeah if you could add an option for the scale it would be much appreciated so that i can try again on blender thanks for all the help you gave me!
## Post #270
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-09T14:34:11+00:00
- Post Title: Re: Noesis g1m/g1t importer with animations (FETH, Dissidia, DOA6, FEW, HW...)

There you go, I put a "scaleFactor" parameter just below "bDOA6FaceAnims", let me know if you see an issue (make sure to delete the old fmt_g1m from the plugin folder) :


 fmt_g1m_scale.zip
(18.82 KiB) Downloaded 29 times
## Post #271
- Username: Jokerfire94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 08, 2020 4:15 pm
- Post datetime: 2020-09-09T18:53:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Thanks again for all the help,i wish i will find a way to get thoses into g1a sooner or later
Oh and i get this error No animated parts found in the fbx (stack=Noesis Frames, layer=Noesis Layer).
Import failed.
Press enter to exit. when i try to go from fbx to g1a
## Post #272
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-10T18:23:20+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Better ask vago for that one, I'm not familiar with his tools unfortunately. I may do some repackers myself one day but it won't be soon.
## Post #273
- Username: U653748
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 05, 2015 5:33 am
- Post datetime: 2020-09-12T07:14:37+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

When trying to open certain character models from fatal frame 5 i get this error.

> Traceback (most recent call last):
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_g1m - Copy.py", line 1900, in LoadModel
>
>     parseG1MS(currentPosition, bs)
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_g1m - Copy.py", line 459, in parseG1MS
>
>     parseG1MS(currentPosition2, bs2, False)
>
>   File "[REDACTED]\Noesis\plugins\python\fmt_g1m - Copy.py", line 489, in parseG1MS
>
>     bone.setMatrix(bone.getMatrix() * boneList[parentId].getMatrix())
>
> IndexError: list index out of range

From what i can tell these are the models that have swappable parts, namely the feet for when they are in doors
## Post #274
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-12T08:38:13+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi,
Send me a few samples that don't work, I'll take a look.
## Post #275
- Username: U653748
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 05, 2015 5:33 am
- Post datetime: 2020-09-13T00:34:35+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Sep 12, 2020 4:38 pm at Sat Sep 12, 2020 4:38 pm
>
> 
Hi,
Send me a few samples that don't work, I'll take a look.
Sorry for the late reply, here you go, this is all the G1m's extracted from Hisoka's A folder, the largest file in it is the character model itself. [http://www.mediafire.com/file/nstr6xiio ... _A.7z/file](http://www.mediafire.com/file/nstr6xiioxwmf0x/H_HIS_A.7z/file) Let me know if you want more i'll probably have to extract them.
## Post #276
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-13T08:59:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Alright make sure that you have the latest script version, put the "bAutoLoadG1MS" option to True and it should work, I got all the parts displayed correctly without errors.
You can also put the "bLoadG1MS" to True and manually select the first g1m when prompted instead but the former option is faster.
## Post #277
- Username: U653748
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 05, 2015 5:33 am
- Post datetime: 2020-09-13T19:11:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sun Sep 13, 2020 4:59 pm at Sun Sep 13, 2020 4:59 pm
>
> 
Alright make sure that you have the latest script version, put the "bAutoLoadG1MS" option to True and it should work, I got all the parts displayed correctly without errors.
You can also put the "bLoadG1MS" to True and manually select the first g1m when prompted instead but the former option is faster. That Seems to have done the trick, i'll post up any other errors i encounter with other Fatal Frame 5 Models models as i find them, thanks for the assist
## Post #278
- Username: dukemagus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 18, 2014 4:58 am
- Post datetime: 2020-09-24T18:03:37+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Question: using the script can noesis batch export g1a files to fbx without the model or we need to use the g1m and then to point to the folder with the animations so noesis packs everything into a single fbx?
## Post #279
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-09-30T00:26:07+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

how to open 0x272c6efb.files
## Post #280
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-10-05T09:17:23+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi, me again
And again thanks for all of the tools stuff
I was wondering, is there a way to get animations for hyrule warriors definitve edition? If so, where are they stored? I tried to look in motion folder but i get dat files by extracting the bin.gz with daemon's ffnt exe(i couldn't find any other method to extract the bin.gz)
## Post #281
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-05T11:36:08+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from dukemagus ↑Fri Sep 25, 2020 2:03 am at Fri Sep 25, 2020 2:03 am
>
> 
Question: using the script can noesis batch export g1a files to fbx without the model or we need to use the g1m and then to point to the folder with the animations so noesis packs everything into a single fbx?

The anim files need the model's skeleton so you need to use it.


> Reply from Makoto ↑Mon Oct 05, 2020 5:17 pm at Mon Oct 05, 2020 5:17 pm
>
> 
Hi, me again
And again thanks for all of the tools stuff
I was wondering, is there a way to get animations for hyrule warriors definitve edition? If so, where are they stored? I tried to look in motion folder but i get dat files by extracting the bin.gz with daemon's ffnt exe(i couldn't find any other method to extract the bin.gz)

I think HW's bin.gz files are actually not gz compressed for some odd reason so simply drag and drop these on Cethleann.Unbundler.exe and you'll get some .datatable files. Drag the biggest one on the unbundler again and you'll get the anim files. You can also use the recursive option of the Unbundler to unpack everything directly.
For games where bin.gz are actually Gz compressed the workflow is the same, just need to decompress the folders first using Cethleann.Gz
## Post #282
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-10-05T13:05:30+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Oct 05, 2020 7:36 pm at Mon Oct 05, 2020 7:36 pm
>
> 
dukemagus wrote: ↑Fri Sep 25, 2020 2:03 am
Question: using the script can noesis batch export g1a files to fbx without the model or we need to use the g1m and then to point to the folder with the animations so noesis packs everything into a single fbx?


The anim files need the model's skeleton so you need to use it.

Makoto wrote: ↑Mon Oct 05, 2020 5:17 pm
Hi, me again
And again thanks for all of the tools stuff
I was wondering, is there a way to get animations for hyrule warriors definitve edition? If so, where are they stored? I tried to look in motion folder but i get dat files by extracting the bin.gz with daemon's ffnt exe(i couldn't find any other method to extract the bin.gz)


I think HW's bin.gz files are actually not gz compressed for some odd reason so simply drag and drop these on Cethleann.Unbundler.exe and you'll get some .datatable files. Drag the biggest one on the unbundler again and you'll get the anim files. You can also use the recursive option of the Unbundler to unpack everything directly.
For games where bin.gz are actually Gz compressed the workflow is the same, just need to decompress the folders first using Cethleann.Gz

I see, do i need some command line command or do i just drag all bin.gz files at once onto the exe?
## Post #283
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-05T14:32:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I think drag and drop could work but if you just want to do one big mass extract I'd just to something like that :
-copy the motion folder next to Cethleann.Unbundler.exe (the one from data\action\)
-launch cmd, go to the folder that has the unbundler and execute 

```
Cethleann.Unbundler.exe -R motion
```


Wait for it to extract everything, then most anims will be in the 0009.datable folder for each character
## Post #284
- Username: mistralsiege
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 08, 2019 5:45 am
- Post datetime: 2020-10-06T02:33:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Getting some issues when I'm trying to rip some Dissidia mods; it lets me load a G1M, a G1T, a G1M Skeleton file, and then animations, but then I'm getting this issue:


I'm also having another issue where the mod I'm trying to rip works, but some parts of the mesh don't load.
[g1m issue.PNG](https://xentaxbackup.github.io/file/18800_g1m issue.PNG)
## Post #285
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-06T10:57:27+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I'll take a look if you upload some samples but no promises for fixing, I only support non modded G1M files considering how hacky G1M editing is
## Post #286
- Username: mistralsiege
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 08, 2019 5:45 am
- Post datetime: 2020-10-07T02:24:32+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

[http://www.mediafire.com/file/rtabcjo4o ... t.rar/file](http://www.mediafire.com/file/rtabcjo4ovw0ooe/Vincent_Test.rar/file)

Included three potential skeleton files, the main G1M, and the G1T. This one is the one that doesn't load most of the submeshes. 
Thank you for even considering taking a look at this for me.
## Post #287
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-10-09T05:11:14+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from mistralsiege ↑Wed Oct 07, 2020 10:24 am at Wed Oct 07, 2020 10:24 am
>
> 
http://www.mediafire.com/file/rtabcjo4o ... t.rar/file

Included three potential skeleton files, the main G1M, and the G1T. This one is the one that doesn't load most of the submeshes. 
Thank you for even considering taking a look at this for me.took a look at it myself, but yeah, happens to me too.
## Post #288
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-09T09:33:49+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Took a quick look, I'll release a proper update in the next days, quite busy with some other stuff right now.
## Post #289
- Username: Van12311
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 14, 2020 7:05 pm
- Post datetime: 2020-10-14T11:44:20+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I am new to this kind of format ripping, but does anyone know where to find the animation files for Hyrule Warriors DE?
## Post #290
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-15T20:27:40+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

The script that I started working on for a single game kept growing to support more games and formats. However as I was learning Noesis and figuring out the formats at the same time some parts were poorly implemented and the codebase became quite annoying to work with. Also the script's performance wasn't good on some games with high poly meshes and some features like model merging and all the popups were annoying to deal with.

I recently got the motivation (not at all influenced by a recent game announcement I swear...) to rewrite the script from scratch and turn it into a native Noesis plugin. The first post has been edited with all necessary information but for those used to the old script here's what's new :

-Faster load times for models. Without textures or anims, they now take between a few milliseconds to a second or 2 to load, even the high poly ones. 
-Easier merging. No need to select the skel and texture assets several times anymore, everything is taken care of by the plugin with an option.
-Better previewing. The physics meshes will now move with their drivers insead of staying in place and stretching.
-Easier to change options. No need to edit a file anymore, everything is taken care of in Noesis (thanks to Yretenai for that one)

For all the info, check the edited first post.

Credits for that C++ version :
-Rich Whitehouse, for making such a great tool in the first place and for all the help he gave me when writing the plugin. The latter wouldn't be nearly as complete without all the handy functions and interfaces available in Noesis.
-Chrrox for all the general Noesis help.
-Eternity/Vagonumero13 for some new format findings during the last months.
-Kerilk, Yretenai, PredatorCZ and Rich for the Noesis C++ plugin samples.
-Raytwo for finding the flag to discriminate between split and non split models.
-DeathChaos25, Moonling, mono24, Allanoon and einherjar007 for testing and reporting bugs.
## Post #291
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-15T20:31:25+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from mistralsiege ↑Wed Oct 07, 2020 10:24 am at Wed Oct 07, 2020 10:24 am
>
> 
The new plugin will load your model without problems, make sure you only have p_sev100_3p1c.g1m, p_sev100_3p1c.g1t and p_sev100_3p1c_default.g1m in the folder, then  copy all the animations that you want there. Select the "merge all" option and click on whatever g1m.

> Reply from Van12311 ↑Wed Oct 14, 2020 7:44 pm at Wed Oct 14, 2020 7:44 pm
>
> 
I am new to this kind of format ripping, but does anyone know where to find the animation files for Hyrule Warriors DE?

See [viewtopic.php?f=16&t=21666&start=270#p167381](https://forum.xentax.com/viewtopic.php?f=16&t=21666&start=270#p167381)
## Post #292
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-10-16T01:40:57+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

So how do I load the .g1a files with the new C++ version?
EDIT: Oh wait, nevermind, I figured it out
## Post #293
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-25T17:21:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Version 1.1 is now live for the C++ plugin :
-Fixes a crash that happened when selecting a geometry g1m with NUN sections without the skeleton
-Fixes a bug on big endian non squared textures
-Adds a new option to disable NUN bones and driver meshes
-Puts the options in a dedicated plugin submenu

Make sure that Noesis is up to date
## Post #294
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-28T20:40:57+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Version 1.2 is now live for the C++ plugin :
-Implements the new UV datatype used in HW2
-UV layering will be taken into account when assigning textures in the preview
## Post #295
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-11-01T15:44:32+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I was trying to load a nioh 2 .g1m file using the new C+ plugin for noesis, but the program just crashes when I try. This applies to any .g1m file for Nioh 2.

I have attached a crash log below

[https://pastebin.com/mtyuSGVA](https://pastebin.com/mtyuSGVA)


Thanks for all your great work 

Edit- Please ignore this, it turns out the tools work absolutely fine.Turns out I hadn't read the instructions properly.

Thanks for all your great work
## Post #296
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-01T17:01:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from gep55 ↑Sun Nov 01, 2020 11:44 pm at Sun Nov 01, 2020 11:44 pm
>
> 
I was trying to load a nioh 2 .g1m file using the new C+ plugin for noesis, but the program just crashes when I try. This applies to any .g1m file for Nioh 2.

I have attached a crash log below

https://pastebin.com/mtyuSGVA


Thanks for all your great work 

Edit- Please ignore this, it turns out the tools work absolutely fine.Turns out I hadn't read the instructions properly.

Thanks for all your great work

Can you give more details about how you got the crash in the first place ? (Which options you used and what files you had in your folder)
Because I can't see how it would crash with the latest version, even if you did something wrong with the setup
## Post #297
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-11-01T17:51:33+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I was using the tool here [viewtopic.php?f=16&t=18042](https://forum.xentax.com/viewtopic.php?f=16&t=18042)

rather than the Unbundler to extract the .g1m files from the .pg1m container.

These files for some reason crash when loaded by the plugin.
## Post #298
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-01T18:47:20+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from gep55 ↑Mon Nov 02, 2020 1:51 am at Mon Nov 02, 2020 1:51 am
>
> 
I was using the tool here viewtopic.php?f=16&t=18042

rather than the Unbundler to extract the .g1m files from the .pg1m container.

These files for some reason crash when loaded by the plugin.

I see thanks, I just tested and that's because Daemon's tool wrongly labels the first file (index 0) as g1m, while it's not a g1m file. So when using the merge it breaks.
So yeah use Cethleann as you did when unpacking KT games if you want to use my plugin, since we're developping our tools in tandem you'll have everything setup correctly.
## Post #299
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-11-01T20:23:52+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Nov 02, 2020 2:47 am at Mon Nov 02, 2020 2:47 am
>
> 
gep55 wrote: ↑Mon Nov 02, 2020 1:51 am
I was using the tool here viewtopic.php?f=16&t=18042

rather than the Unbundler to extract the .g1m files from the .pg1m container.

These files for some reason crash when loaded by the plugin.


I see thanks, I just tested and that's because Daemon's tool wrongly labels the first file (index 0) as g1m, while it's not a g1m file. So when using the merge it breaks.
So yeah use Cethleann as you did when unpacking KT games if you want to use my plugin, since we're developing our tools in tandem you'll have everything setup correctly.

Thanks. I've included some Nioh 2 character mesh for the character Okuni in the link below. For some reason, when I export via .fbx to blender, I get buggy weight painting when moving her head.

Picture of bug [http://www.mediafire.com/view/pojdpyj01 ... e.PNG/file](http://www.mediafire.com/view/pojdpyj01dtmwga/Capture.PNG/file)

Source files for bugged character (I'll PM you these). Load these using the plugin and then export the model to the 3d program of your choice.
## Post #300
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-01T22:26:15+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from gep55 ↑Mon Nov 02, 2020 4:23 am at Mon Nov 02, 2020 4:23 am
>
> 
Joschka wrote: ↑Mon Nov 02, 2020 2:47 am
gep55 wrote: ↑Mon Nov 02, 2020 1:51 am
I was using the tool here viewtopic.php?f=16&t=18042

rather than the Unbundler to extract the .g1m files from the .pg1m container.

These files for some reason crash when loaded by the plugin.


I see thanks, I just tested and that's because Daemon's tool wrongly labels the first file (index 0) as g1m, while it's not a g1m file. So when using the merge it breaks.
So yeah use Cethleann as you did when unpacking KT games if you want to use my plugin, since we're developing our tools in tandem you'll have everything setup correctly.


Thanks. I've included some Nioh 2 character mesh for the character Okuni in the link below. For some reason, when I export via .fbx to blender, I get buggy weight painting when moving her head.

Picture of bug http://www.mediafire.com/view/pojdpyj01 ... e.PNG/file

Source files for bugged character (I'll PM you these). Load these using the plugin and then export the model to the 3d program of your choice.

I made a wrong assumptions about split meshes when they each have physics bones, should be fixed with the attached build. Please download it and retry, if it works I'll push it on github as v1.3.2


 projectG1M.zip
(84.91 KiB) Downloaded 49 times



Thank you for the report, appreciate it.

EDIT : Released
## Post #301
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-11-01T22:51:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Nov 02, 2020 6:26 am at Mon Nov 02, 2020 6:26 am
>
> 
gep55 wrote: ↑Mon Nov 02, 2020 4:23 am
Joschka wrote: ↑Mon Nov 02, 2020 2:47 am


I see thanks, I just tested and that's because Daemon's tool wrongly labels the first file (index 0) as g1m, while it's not a g1m file. So when using the merge it breaks.
So yeah use Cethleann as you did when unpacking KT games if you want to use my plugin, since we're developing our tools in tandem you'll have everything setup correctly.


Thanks. I've included some Nioh 2 character mesh for the character Okuni in the link below. For some reason, when I export via .fbx to blender, I get buggy weight painting when moving her head.

Picture of bug http://www.mediafire.com/view/pojdpyj01 ... e.PNG/file

Source files for bugged character (I'll PM you these). Load these using the plugin and then export the model to the 3d program of your choice.


I made a wrong assumptions about split meshes when they each have physics bones, should be fixed with the attached build. Please download it and retry, if it works I'll push it on github as v1.4

projectG1M v1.4

Thank you for the report, appreciate it.

Thanks, that fixed it
## Post #302
- Username: banan039eu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 12, 2020 4:52 am
- Post datetime: 2020-11-18T10:35:01+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi Joschka! Few weeks back You were so kind to pair g1t materials with proper g1m file for Age of Calamity DEMO on  BOTW modding discord hub. Since the full version is out, would You be willing to do the same for full version? If not, could You teach me how to do it? I have unpacked all rdb files with cethlean tool, I have all g1m and g1t files in CharacterEditor and FieldEditor4, all I would need is to pair them (just like You did that and posted it in txt file). I do not mean to be pushy or annoying, I know You suddenly left our discord server and I respect Your decision. Your support on DEMO significantly boosted my project Hyrule Rebuild Attempt - I credited You in the submission in order to honor Your support.

If You are not interested in working on Age of Calamity, that is completely understandable and I will not harass You further.

Looking forward to Your answer!
## Post #303
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-21T14:06:20+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from banan039eu ↑Wed Nov 18, 2020 6:35 pm at Wed Nov 18, 2020 6:35 pm
>
> 
Hi Joschka! Few weeks back You were so kind to pair g1t materials with proper g1m file for Age of Calamity DEMO on  BOTW modding discord hub. Since the full version is out, would You be willing to do the same for full version? If not, could You teach me how to do it? I have unpacked all rdb files with cethlean tool, I have all g1m and g1t files in CharacterEditor and FieldEditor4, all I would need is to pair them (just like You did that and posted it in txt file). I do not mean to be pushy or annoying, I know You suddenly left our discord server and I respect Your decision. Your support on DEMO significantly boosted my project Hyrule Rebuild Attempt - I credited You in the submission in order to honor Your support.

If You are not interested in working on Age of Calamity, that is completely understandable and I will not harass You further.

Looking forward to Your answer!

Hi,

Basically after talking with my friend we decided not to share that info online for the final release, since it puts the bar too low to get everything out of the game on the release. This will lead to asset encryption for future games eventually, which we don't want to deal with.
However all the necessary info to reconstruct such a document is online and can be figured out with a bit of research so it'll only take a bit of effort to get the pairs.

Edit : Apparently you figured it out, good job.
## Post #304
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-21T14:27:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Version 1.4 is now live
-Implements a new UV datatype used in the final release of Hyrule Warriors 2
-New option to choose to completely disable NUNO nodes (the physics mesh will still be reconstructed before, all the extra bones and drivers will just not be there)

I also started to work on reconstructing maps, more about this later since it's sill very early WIP
## Post #305
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-26T15:43:51+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Probably not compatible with the current Koei engine, but do you have any plans for older files?
I have an old file with headers such as "XKMD0020" and "XFTX0010". These are used in Dynasty Warriors 4 and other XBOX games.
[oldkoei.zip](https://xentaxbackup.github.io/file/19095_oldkoei.zip)
## Post #306
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-28T17:22:58+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I'm sorry to more post.
I'm currently looking into an old Koei game.

When I checked the files of Sengoku Musou 2 / Samurai Warrors 2, g1t could be loaded, but g1m was damaged.
mesh is fine but the skeleton is broken. I can't confirm the playback of g1a because the skeleton is damaged, but it is played.

Here are the dumped g1m and g1a samples.

*no difference between the PS3 version and the PS Vita version. Both have the same problem. The sample is PS3.

------
*EDIT
Some games seem to use some kind of compression starting with the LZP2 header. They are mainly used only for textures, but only Dynasty Warriors Strike Force uses LZP2 compression for all files.
I don't know if it's a same algorithm, but it seems that some koei PSP games have adopted LZP2 and they could be unzipped with 356resource.exe (search for "356resource.rar"). , I tried to unzip with that tool but it can't load.
I looked at 356resource.exe in dnspy and it seems that it uses a kind of custom lz77 algorithm.

I think it's a low priority because it's a unique format that uses compression.
Also, most games have uncompressed character files, which makes them even lower priority. Only Strike force uses it for all files.
If necessary, I will provide a sample.
[sengoku_2.zip](https://xentaxbackup.github.io/file/19103_sengoku_2.zip)
## Post #307
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-29T19:35:56+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from einherjar007 ↑Sun Nov 29, 2020 1:22 am at Sun Nov 29, 2020 1:22 am
>
> 
I'm sorry to more post.
I'm currently looking into an old Koei game.

When I checked the files of Sengoku Musou 2 / Samurai Warrors 2, g1t could be loaded, but g1m was damaged.
mesh is fine but the skeleton is broken. I can't confirm the playback of g1a because the skeleton is damaged, but it is played.

Here are the dumped g1m and g1a samples.

*no difference between the PS3 version and the PS Vita version. Both have the same problem. The sample is PS3.

------
*EDIT
Some games seem to use some kind of compression starting with the LZP2 header. They are mainly used only for textures, but only Dynasty Warriors Strike Force uses LZP2 compression for all files.
I don't know if it's a same algorithm, but it seems that some koei PSP games have adopted LZP2 and they could be unzipped with 356resource.exe (search for "356resource.rar"). , I tried to unzip with that tool but it can't load.
I looked at 356resource.exe in dnspy and it seems that it uses a kind of custom lz77 algorithm.

I think it's a low priority because it's a unique format that uses compression.
Also, most games have uncompressed character files, which makes them even lower priority. Only Strike force uses it for all files.
If necessary, I will provide a sample.

I will take a look during the week or next week, going to see what I can do about it.

> Reply from einherjar007 ↑Thu Nov 26, 2020 11:43 pm at Thu Nov 26, 2020 11:43 pm
>
> 
Probably not compatible with the current Koei engine, but do you have any plans for older files?
I have an old file with headers such as "XKMD0020" and "XFTX0010". These are used in Dynasty Warriors 4 and other XBOX games.

After a quick look, these files seem to be completely different from their current formats. I'm really busy with other projects right now so I won't be able to look into it myself unfortunately
## Post #308
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-03T21:16:07+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Ryza 2 seems to work, bone names have been left too.
## Post #309
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2020-12-05T05:52:15+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Does anyone know how to extract MUA3 animations? Tried the Unbundler but nothing gets extracted.
## Post #310
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-05T10:57:46+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from MarioSonicU ↑Sat Dec 05, 2020 1:52 pm at Sat Dec 05, 2020 1:52 pm
>
> 
Does anyone know how to extract MUA3 animations? Tried the Unbundler but nothing gets extracted.

Workaround for now 
-replace the "ZL" extension by "idxout"
-place all of these in a folder
-use Steven's gas machine on that folder with the [PC] Samurai Warriors 4-II option
-click "no" for everything except "process idxout"

Then all the g2a files will be extracted
## Post #311
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-12-06T08:55:57+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hows the wip of the AOC map reconstruction going
Have you discovered the model file names also, The have been found by a modder


 AOC_normal_names_rev_1.rar
(73.24 KiB) Downloaded 42 times


Its the file names which is attached to several models files as listed
Dont know if this would help not seen you mention file names so i thought id show incase it might help
## Post #312
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-06T10:31:27+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from speaker60 ↑Sun Dec 06, 2020 4:55 pm at Sun Dec 06, 2020 4:55 pm
>
> 
Hows the wip of the AOC map reconstruction going
Have you discovered the model file names also, The have been found by a modder
AOC_normal_names_rev_1.rar
Its the file names which is attached to several models files as listed
Dont know if this would help not seen you mention file names so i thought id show incase it might help

I didn't touch it since the last time, I've been busy with other stuff but I plan to get back to it when I have some time. I need to work on some small model related stuff first though and add support for some files mentionned above. Need to actually play the game too...

Thanks for the names, I'm already aware of these, they left a few clear strings in the files/binary and those can be easily dumped but most of them (texture related stuff for example) are scrapped. Some matches with the hashes have been made but the filelist is not big enough for now to be worth sharing
EDIT : Actually there are quite a bit of names missing from the list, wonder how they constructed it. Who worked on this actually ?
## Post #313
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-12-06T13:39:53+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Bran whos doing the hyrule rebuild project posted the list, I know you left the modding server 
Im not getting involved with that lol

Im not actually modding botw or aoc 

Im working on a project to make a 3d map/world of all of hyrule and then make inspired versions of hyrule from each game fitting to botw/aoc map as its the latest and most realistic in scale and realism Aoc seems to have alot of lod terrain so i can better recreate the world in blender then just using botws heightmap image

This is all so i can make a fancy time lapse of the land of hyrule and how it changes through the many many years of the zeldas story 
Seeing how a version of ocerana of times map could have looked if it was remade to match botw world ect seeing lake hylia change that sort of thing
So my project isnt for any one specific game but a sort of celebration of them all. Its also just for like a recorded video not a mod so its just a fan art project

Ill have to make up alot of stuff in order for it to work in a chronological scene, ill be making various backstory for things like in twilight hylia bridge had a dead tree at one end where as in bot it dost and the bridge seems to be longer so i have a backstory that a chunk of the land and the end of the bridge with the dead tree crumbles and falls into the lake below taking the tree and part f the bridge with it. To explain what happened to the tree and why the bridge is now longer just subtle things like that. Ofcorse i have to ignore why the lake is no longer by the castle like it was in twilight, I can only do my best lol
## Post #314
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-06T19:39:57+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from speaker60 ↑Sun Dec 06, 2020 9:39 pm at Sun Dec 06, 2020 9:39 pm
>
> 
Bran whos doing the hyrule rebuild project posted the list, I know you left the modding server 
Im not getting involved with that lol

I'm not really sure why people made such a big deal about it actually, the only reason I left was because no research on Age Of Calamity was made there, only extraction and use of existing tools but I didn't have any problems with anyone there. I think people got the wrong idea because I deleted all my messages but that's something I always do before leaving a discord server.

> Reply from speaker60 ↑Sun Dec 06, 2020 9:39 pm at Sun Dec 06, 2020 9:39 pm
>
> 
Im not actually modding botw or aoc 

Im working on a project to make a 3d map/world of all of hyrule and then make inspired versions of hyrule from each game fitting to botw/aoc map as its the latest and most realistic in scale and realism Aoc seems to have alot of lod terrain so i can better recreate the world in blender then just using botws heightmap image

This is all so i can make a fancy time lapse of the land of hyrule and how it changes through the many many years of the zeldas story 
Seeing how a version of ocerana of times map could have looked if it was remade to match botw world ect seeing lake hylia change that sort of thing
So my project isnt for any one specific game but a sort of celebration of them all. Its also just for like a recorded video not a mod so its just a fan art project

Ill have to make up alot of stuff in order for it to work in a chronological scene, ill be making various backstory for things like in twilight hylia bridge had a dead tree at one end where as in bot it dost and the bridge seems to be longer so i have a backstory that a chunk of the land and the end of the bridge with the dead tree crumbles and falls into the lake below taking the tree and part f the bridge with it. To explain what happened to the tree and why the bridge is now longer just subtle things like that. Ofcorse i have to ignore why the lake is no longer by the castle like it was in twilight, I can only do my best lol

I see, this sounds really ambitious, I can see why you'd want map support for the game. I can't really give an ETA though, the next days will be quite busy for me and I have a few things to update regarding the models. 
I use this thread as the main place to share my progress so keep coming from time to time, when I'll have some new things to share regarding maps I'll make sure to post them here.
Best of luck for your project(s)
## Post #315
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-12-07T00:23:26+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Dec 07, 2020 3:39 am at Mon Dec 07, 2020 3:39 am
>
> 
I'm not really sure why people made such a big deal about it actually, the only reason I left was because no research on Age Of Calamity was made there, only extraction and use of existing tools but I didn't have any problems with anyone there. I think people got the wrong idea because I deleted all my messages but that's something I always do before leaving a discord server.

Ah so your typical overblown drama lol I tend to ignore stuff like that haha
Better stuff to be doing like my project 

> Reply from Joschka ↑Mon Dec 07, 2020 3:39 am at Mon Dec 07, 2020 3:39 am
>
> 
I see, this sounds really ambitious, I can see why you'd want map support for the game. I can't really give an ETA though, the next days will be quite busy for me and I have a few things to update regarding the models. 
I use this thread as the main place to share my progress so keep coming from time to time, when I'll have some new things to share regarding maps I'll make sure to post them here.
Best of luck for your project(s)

Yer its ambitious a guess its just a hobby thing so ill take my time with it
Im a game dev myself so im often busy with work projects so im not always working on hobby projects

I figured this was the main place so ill keep checking here from time to time, i appreciate your working on it at all in your own pace. Maps and such if often overlooked as character models is the more popular thing. Iv always been more interested in the environments of games 

Your file name list would be usefull if its a more complete list
for me and branan having a name attached to a model helps know what it is without having to load the model up to see
for both our projects. So like having the map models imported into blender if in the hierarchy have names and not arbitrary numbers would be quite usefull.

Some kind of toggle option that would auto rename models to there file names when you export out of noesis would be awesome if its a simple thing to do?
## Post #316
- Username: banan039eu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 12, 2020 4:52 am
- Post datetime: 2020-12-08T22:08:20+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sun Dec 06, 2020 6:31 pm at Sun Dec 06, 2020 6:31 pm
>
> 
speaker60 wrote: ↑Sun Dec 06, 2020 4:55 pm
Hows the wip of the AOC map reconstruction going
Have you discovered the model file names also, The have been found by a modder
AOC_normal_names_rev_1.rar
Its the file names which is attached to several models files as listed
Dont know if this would help not seen you mention file names so i thought id show incase it might help


I didn't touch it since the last time, I've been busy with other stuff but I plan to get back to it when I have some time. I need to work on some small model related stuff first though and add support for some files mentionned above. Need to actually play the game too...

Thanks for the names, I'm already aware of these, they left a few clear strings in the files/binary and those can be easily dumped but most of them (texture related stuff for example) are scrapped. Some matches with the hashes have been made but the filelist is not big enough for now to be worth sharing
EDIT : Actually there are quite a bit of names missing from the list, wonder how they constructed it. Who worked on this actually ?

Actually I was working on it. I parsed all files in KIDSSystemResource dir into xml and extracted as many names as possible. There are around 1000 models in CharacterEditor and 8000 in FieldEditor - I only found around 5000 names of models from FieldEditor, 0 from CharacterEditor. I also found the coordinates and rotations data of objects in game files, but I could not match it properly with proper g1m model. Can You tell me please how You find coordinates,  Joschka?
## Post #317
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-15T21:42:00+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Project G1M has been updated to version 1.4.1. This update is mostly a combination of little bug fixes I've been doing during free time.

-Fixed a UV layer bug that made some Nioh 2 submeshes have wrong UVs since I added the new UV type introduced in AoC
-Fixed an animation bug that made animations of less than a second last till a second, with the character being stuck at the last frame for the extra duration
-New option to enable/disable the autorig for NUN meshes
-New mobile texture format supported, used in Dynasty Warriors Mobile
-Support added for Dynasty Warrior 5 model files (2005 !). As of now only geometry (vertices, UVs, normals) is supported, the skeleton format was different at the time and will need a bit more research, same for the texture format. The BPK bundles containing the files can now be unpacked using Cethleann.Unbundler.



-Support added for Hyrule Warriors Legend (3DS) texture format, check Yretenai's last update for instructions to extract the game [viewtopic.php?f=10&t=21679&start=225#p169433](https://forum.xentax.com/viewtopic.php?f=10&t=21679&start=225#p169433). Big thanks to OnePieceFreak's ETC1 decompression tool that I used as a reference. 




> Reply from banan039eu ↑Wed Dec 09, 2020 6:08 am at Wed Dec 09, 2020 6:08 am
>
> 
I'm going to resume working on maps hopefully soon. My coordinates are not good as of now, some objects seem placed correctly whereas others are not, there seems to be some parenting stuff going on.

> Reply from speaker60 ↑Mon Dec 07, 2020 8:23 am at Mon Dec 07, 2020 8:23 am
>
> 
Some kind of toggle option that would auto rename models to there file names when you export out of noesis would be awesome if its a simple thing to do?
We do that using filelists, with Cethleann. As of now we don't have enough names to make it worth adding but hopefully we'll have at some point.
## Post #318
- Username: banan039eu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 12, 2020 4:52 am
- Post datetime: 2020-12-17T15:37:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Nov 21, 2020 10:27 pm at Sat Nov 21, 2020 10:27 pm
>
> 
Version 1.4 is now live
-Implements a new UV datatype used in the final release of Hyrule Warriors 2
-New option to choose to completely disable NUNO nodes (the physics mesh will still be reconstructed before, all the extra bones and drivers will just not be there)

I also started to work on reconstructing maps, more about this later since it's sill very early WIP

Where I can find *.rdmap files? I can't find them anywhere in game files
## Post #319
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-17T20:59:17+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from banan039eu ↑Thu Dec 17, 2020 11:37 pm at Thu Dec 17, 2020 11:37 pm
>
> 
Joschka wrote: ↑Sat Nov 21, 2020 10:27 pm
Version 1.4 is now live
-Implements a new UV datatype used in the final release of Hyrule Warriors 2
-New option to choose to completely disable NUNO nodes (the physics mesh will still be reconstructed before, all the extra bones and drivers will just not be there)

I also started to work on reconstructing maps, more about this later since it's sill very early WIP




Where I can find *.rdmap files? I can't find them anywhere in game files

These don't exist, it's an intermediate format that I created to make it easier for the plugin to parse the info directly.
## Post #320
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2020-12-18T14:17:12+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Are there any Warriors games (besides the licensed ones (Berserk, Zelda, etc.) that has animation files (g1a/g2a)?
## Post #321
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-12-20T20:38:59+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

So i recently updated the g1m plug in to the native one, also updated noesis. I tried to check option under "Project G1M" but i can't seem to find what i need. I'm trying to load a g1m, that also has a paired g1m skeleton, a g1t and an oid file for bone names as well as all animations in a folder. What am I supposed to do, click and such? I'm just too used to the old one
## Post #322
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-20T20:48:00+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from MarioSonicU ↑Fri Dec 18, 2020 10:17 pm at Fri Dec 18, 2020 10:17 pm
>
> 
Are there any Warriors games (besides the licensed ones (Berserk, Zelda, etc.) that has animation files (g1a/g2a)?

All recent KT games use g1a/g2a

> Reply from Makoto ↑Mon Dec 21, 2020 4:38 am at Mon Dec 21, 2020 4:38 am
>
> 
So i recently updated the g1m plug in to the native one, also updated noesis. I tried to check option under "Project G1M" but i can't seem to find what i need. I'm trying to load a g1m, that also has a paired g1m skeleton, a g1t and an oid file for bone names as well as all animations in a folder. What am I supposed to do, click and such? I'm just too used to the old one

Put all the stuff in the same folder (g1m, g1t, oid, g1a etc), go to tools->project G1M and make sure that the first option (merge all) is selected. Then open whatever g1m that is in the folder.
## Post #323
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2020-12-20T21:39:51+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Has any progress been made for Hyrule Warriors Age of Calamity on applying the correct textures to the correct models? Having to comb through thousands of g1t's for each model is far too time consuming.
## Post #324
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-12-21T07:08:11+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Dec 21, 2020 4:48 am at Mon Dec 21, 2020 4:48 am
>
> 
MarioSonicU wrote: ↑Fri Dec 18, 2020 10:17 pm
Are there any Warriors games (besides the licensed ones (Berserk, Zelda, etc.) that has animation files (g1a/g2a)?


All recent KT games use g1a/g2a
Makoto wrote: ↑Mon Dec 21, 2020 4:38 am
So i recently updated the g1m plug in to the native one, also updated noesis. I tried to check option under "Project G1M" but i can't seem to find what i need. I'm trying to load a g1m, that also has a paired g1m skeleton, a g1t and an oid file for bone names as well as all animations in a folder. What am I supposed to do, click and such? I'm just too used to the old one


Put all the stuff in the same folder (g1m, g1t, oid, g1a etc), go to tools->project G1M and make sure that the first option (merge all) is selected. Then open whatever g1m that is in the folder.

so there is no way to make it like the older plug in where you can choose single files to open?
## Post #325
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-21T11:50:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from ninetalescommander ↑Mon Dec 21, 2020 5:39 am at Mon Dec 21, 2020 5:39 am
>
> 
Has any progress been made for Hyrule Warriors Age of Calamity on applying the correct textures to the correct models? Having to comb through thousands of g1t's for each model is far too time consuming.

This is possible since Persona 5 Scramble back in February, check the Cethleann topic, this question has been answered several times.

> Reply from Makoto ↑Mon Dec 21, 2020 3:08 pm at Mon Dec 21, 2020 3:08 pm
>
> 
Joschka wrote: ↑Mon Dec 21, 2020 4:48 am
MarioSonicU wrote: ↑Fri Dec 18, 2020 10:17 pm
Are there any Warriors games (besides the licensed ones (Berserk, Zelda, etc.) that has animation files (g1a/g2a)?


All recent KT games use g1a/g2a
Makoto wrote: ↑Mon Dec 21, 2020 4:38 am
So i recently updated the g1m plug in to the native one, also updated noesis. I tried to check option under "Project G1M" but i can't seem to find what i need. I'm trying to load a g1m, that also has a paired g1m skeleton, a g1t and an oid file for bone names as well as all animations in a folder. What am I supposed to do, click and such? I'm just too used to the old one


Put all the stuff in the same folder (g1m, g1t, oid, g1a etc), go to tools->project G1M and make sure that the first option (merge all) is selected. Then open whatever g1m that is in the folder.


so there is no way to make it like the older plug in where you can choose single files to open?

No, I don't see the point in reimplementing it. If you want to open a single anim you just need to copy it next to the g1m and load it using merge all. If you want to identify anims you can just load a batch of animations and then note its name by checking them individually using Tools->DataViewer and clicking on the anim names.
## Post #326
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2020-12-21T15:24:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Dec 21, 2020 7:50 pm at Mon Dec 21, 2020 7:50 pm
>
> 
ninetalescommander wrote: ↑Mon Dec 21, 2020 5:39 am
Has any progress been made for Hyrule Warriors Age of Calamity on applying the correct textures to the correct models? Having to comb through thousands of g1t's for each model is far too time consuming.


This is possible since Persona 5 Scramble back in February, check the Cethleann topic, this question has been answered several times.
Makoto wrote: ↑Mon Dec 21, 2020 3:08 pm
Joschka wrote: ↑Mon Dec 21, 2020 4:48 am


All recent KT games use g1a/g2a



Put all the stuff in the same folder (g1m, g1t, oid, g1a etc), go to tools->project G1M and make sure that the first option (merge all) is selected. Then open whatever g1m that is in the folder.


so there is no way to make it like the older plug in where you can choose single files to open?


No, I don't see the point in reimplementing it. If you want to open a single anim you just need to copy it next to the g1m and load it using merge all. If you want to identify anims you can just load a batch of animations and then note its name by checking them individually using Tools->DataViewer and clicking on the anim names.

I think you've misunderstood what I'm saying here.
Yes I am aware you can merge the content in 1 folder but because there's thousands of g1t files, there's no way of knowing which textures apply to the model in question unless you comb through every single g1t file. If I already knew what files to put into the folder to have noesis to merge, I wouldn't even be here.
Here's an example to what I mean: [https://gyazo.com/b9281d567678556a552998cfe3a69099](https://gyazo.com/b9281d567678556a552998cfe3a69099)
## Post #327
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-21T17:49:26+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from ninetalescommander ↑Mon Dec 21, 2020 11:24 pm at Mon Dec 21, 2020 11:24 pm
>
> 

I think you've misunderstood what I'm saying here.
Yes I am aware you can merge the content in 1 folder but because there's thousands of g1t files, there's no way of knowing which textures apply to the model in question unless you comb through every single g1t file. If I already knew what files to put into the folder to have noesis to merge, I wouldn't even be here.
Here's an example to what I mean: https://gyazo.com/b9281d567678556a552998cfe3a69099

That was precisely what I was talking about, autodetecting + recombining g1t files in RDB games has been explained several times in the Cethleann thread.
## Post #328
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2020-12-21T18:10:45+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Tue Dec 22, 2020 1:49 am at Tue Dec 22, 2020 1:49 am
>
> 
ninetalescommander wrote: ↑Mon Dec 21, 2020 11:24 pm

I think you've misunderstood what I'm saying here.
Yes I am aware you can merge the content in 1 folder but because there's thousands of g1t files, there's no way of knowing which textures apply to the model in question unless you comb through every single g1t file. If I already knew what files to put into the folder to have noesis to merge, I wouldn't even be here.
Here's an example to what I mean: https://gyazo.com/b9281d567678556a552998cfe3a69099


That was precisely what I was talking about, autodetecting + recombining g1t files in RDB games has been explained several times in the Cethleann thread.

Alright, I'll look at that thread.
## Post #329
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2020-12-30T21:41:13+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Dec 05, 2020 6:57 pm at Sat Dec 05, 2020 6:57 pm
>
> 
MarioSonicU wrote: ↑Sat Dec 05, 2020 1:52 pm
Does anyone know how to extract MUA3 animations? Tried the Unbundler but nothing gets extracted.


Workaround for now 
-replace the "ZL" extension by "idxout"
-place all of these in a folder
-use Steven's gas machine on that folder with the [PC] Samurai Warriors 4-II option
-click "no" for everything except "process idxout"

Then all the g2a files will be extracted

How can I discover the root cause of this misalignment on animation in MUA3?, my suspect is the method to extract the .g2a or the noesis g1m/g1t/g1a importer, however some .g2a fails but other are correct, for example Invisible Woman does not present this problem, if I copy it on Wasp, the problem disappears 



Capture11.PNG (122.74 KiB) Viewed 341 times



Files to reproduce it
[https://www.mediafire.com/file/cvl9mvbv ... p.zip/file](https://www.mediafire.com/file/cvl9mvbvve3vtm1/wasp.zip/file)
## Post #330
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-01-17T12:11:21+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Dec 21, 2020 4:48 am at Mon Dec 21, 2020 4:48 am
>
> 
MarioSonicU wrote: ↑Fri Dec 18, 2020 10:17 pm
Are there any Warriors games (besides the licensed ones (Berserk, Zelda, etc.) that has animation files (g1a/g2a)?


All recent KT games use g1a/g2a
Makoto wrote: ↑Mon Dec 21, 2020 4:38 am
So i recently updated the g1m plug in to the native one, also updated noesis. I tried to check option under "Project G1M" but i can't seem to find what i need. I'm trying to load a g1m, that also has a paired g1m skeleton, a g1t and an oid file for bone names as well as all animations in a folder. What am I supposed to do, click and such? I'm just too used to the old one


Put all the stuff in the same folder (g1m, g1t, oid, g1a etc), go to tools->project G1M and make sure that the first option (merge all) is selected. Then open whatever g1m that is in the folder.

Sorry for bothering, would there be a possibility of re implemeting at least oid files loading? I tried putting them in the same folder as the model and all, but it doesn't get bone names (tried with blue reflection g1m) texture, anim, mesh, everything else works, just can't get bone names from the oid unlike old script...
## Post #331
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-01-17T12:33:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Delbozkester ↑Thu Dec 31, 2020 5:41 am at Thu Dec 31, 2020 5:41 am
>
> 
How can I discover the root cause of this misalignment on animation in MUA3?, my suspect is the method to extract the .g2a or the noesis g1m/g1t/g1a importer, however some .g2a fails but other are correct, for example Invisible Woman does not present this problem, if I copy it on Wasp, the problem disappears

I'll take a look when I have the time.

> Reply from Makoto ↑Mon Dec 21, 2020 4:38 am at Mon Dec 21, 2020 4:38 am
>
> 
Sorry for bothering, would there be a possibility of re implemeting at least oid files loading? I tried putting them in the same folder as the model and all, but it doesn't get bone names (tried with blue reflection g1m) texture, anim, mesh, everything else works, just can't get bone names from the oid unlike old script...

Weird, it should load just fine. Can you upload a sample ?

EDIT : I asked a friend to test on a blue reflection model and it worked fine
## Post #332
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-20T01:43:56+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

hello thony, sensational tutorial, very detailed.
I know that here, in this topic, the subject is plugin, but I would really like you to help me extract the LINKDATA_A file, from (game attack on titan 2).
I know that the tool to extract this file is Cethleann.Exporter.exe, but I don't know how to use this tool with cmd
I know that cmd has to be opened inside the folder where Cethleann.Exporter.exe is located
can you help me, i am very lay in extraction using cmd
## Post #333
- Username: vanilla1
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 23, 2015 10:51 pm
- Post datetime: 2021-01-20T01:52:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

hello thony, this tutorial (How to extract and view a DOA6 model on Noesis with this script and with Cethleann) was sensational, very detailed.
I know that here, in this topic the subject is plugin, but I would like you to help me extract the file LINKDATA_A, from (game attack on titan 2).
I know that the tool to extract this file is Cethleann.Exporter.exe, but I don't know how to use this tool with cmd
I know that cmd has to be opened inside the folder where Cethleann.Exporter.exe is located
please help, i am very lay in extraction using cmd
Cethleann.Exporter is on the desktop, in a folder with the name cethleann, the LINKDATA_A file is in a folder with the name attackontitan2 and I created it a folder that is empty with the name AOT2, this last folder would be the place where LINKDATA_A will be extracted, but I don't know how to type the command in cmd to do the extraction
Note: the three folders (cethleann, attackontitan2 and AOT2) are on the desktop
## Post #334
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2021-01-29T10:43:36+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

hi all and thanks for this tool.

its any way the option in Tool menu this plugin add can assign with hotkey? you know when toggle on and off merge all and staff like that.
## Post #335
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-01-30T00:58:12+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from neusi ↑Fri Jan 29, 2021 6:43 pm at Fri Jan 29, 2021 6:43 pm
>
> 
hi all and thanks for this tool.

its any way the option in Tool menu this plugin add can assign with hotkey? you know when toggle on and off merge all and staff like that.

It is not possible.
## Post #336
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2021-01-30T01:19:24+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Jan 30, 2021 8:58 am at Sat Jan 30, 2021 8:58 am
>
> 
neusi wrote: ↑Fri Jan 29, 2021 6:43 pm
hi all and thanks for this tool.

its any way the option in Tool menu this plugin add can assign with hotkey? you know when toggle on and off merge all and staff like that.


It is not possible.

Ahh. Ok thanks for answering so fast.
## Post #337
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2021-02-12T04:35:06+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

When I tested MUA3, everything worked besides the facial animations. Any fix for that?
## Post #338
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-02-12T11:47:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from MarioSonicU ↑Fri Feb 12, 2021 12:35 pm at Fri Feb 12, 2021 12:35 pm
>
> 
When I tested MUA3, everything worked besides the facial animations. Any fix for that?

You need to be much more specific than "it doesn't work". I don't have the game myself.
## Post #339
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2021-02-12T12:41:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Feb 12, 2021 7:47 pm at Fri Feb 12, 2021 7:47 pm
>
> 
MarioSonicU wrote: ↑Fri Feb 12, 2021 12:35 pm
When I tested MUA3, everything worked besides the facial animations. Any fix for that?


You need to be much more specific than "it doesn't work". I don't have the game myself.

I mean that when playing an animation, they seem to have the same facial expressions when T-posed (i.e. they dont have any smiling, hurt, or shocked expressions). I have a feeling that it might use blend shapes or face morphs.
## Post #340
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-02-12T18:14:15+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from MarioSonicU ↑Fri Feb 12, 2021 8:41 pm at Fri Feb 12, 2021 8:41 pm
>
> 
I mean that when playing an animation, they seem to have the same facial expressions when T-posed (i.e. they dont have any smiling, hurt, or shocked expressions). I have a feeling that it might use blend shapes or face morphs.

I see. A few possibilities I can think about :
-they actually didn't bother about facial anims during gameplay (not sure if true since I didn't play the game)
-they're using blend shapes as you suspect. If so there should be some g1h files somewhere to confirm they do. However I don't support them as of now.
-the facial anims are stored separately elsewhere, in other animation files. This was the case for other games like Dissidia NT, Dead or alive 6 and FETH
## Post #341
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-02-28T18:33:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Having an issue exporting some Persona 5 Strikers (PC) animations on some of the new characters, in noesis they seem to have some weird vertex issues for the cloth simulations. This might be an issue of me being stupid but I figured I would report it just in case!
[cloth sim explosion.PNG](https://xentaxbackup.github.io/file/19616_cloth sim explosion.PNG)
## Post #342
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-02-28T21:22:10+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Crash ↑Mon Mar 01, 2021 2:33 am at Mon Mar 01, 2021 2:33 am
>
> 
Having an issue exporting some Persona 5 Strikers (PC) animations on some of the new characters, in noesis they seem to have some weird vertex issues for the cloth simulations. This might be an issue of me being stupid but I figured I would report it just in case!

Physics meshes (NUN meshes) are only weighted using a very basic autorig functionality, the goal was to make them somewhat follow the overall anim, along with their associated physics nodes, the results' quality varies from model to model. 
But in reality these meshes aren't rigged at all and their shape is computed using cloth simulation at runtime using a vertex shader and the physics nodes. So the only thing possible is to reconstruct their shape at rest. 
The best solution is to disable the autorig in the options to make them stay static, export, then rig them to the physics nodes or do actual cloth simulation or whatever in your 3D software. The autorig is here only to make most anims look less awkward when previewing.
If you're wondering why Joker looks so good in comparison for example it's because his outfit's uses baked physics sim and isn't simulated at runtime.
## Post #343
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-02-28T22:05:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Mar 01, 2021 5:22 am at Mon Mar 01, 2021 5:22 am
>
> 
Crash wrote: ↑Mon Mar 01, 2021 2:33 am
Having an issue exporting some Persona 5 Strikers (PC) animations on some of the new characters, in noesis they seem to have some weird vertex issues for the cloth simulations. This might be an issue of me being stupid but I figured I would report it just in case!


Physics meshes (NUN meshes) are only weighted using a very basic autorig functionality, the goal was to make them somewhat follow the overall anim, along with their associated physics nodes, the results' quality varies from model to model. 
But in reality these meshes aren't rigged at all and their shape is computed using cloth simulation at runtime using a vertex shader and the physics nodes. So the only thing possible is to reconstruct their shape at rest. 
The best solution is to disable the autorig in the options to make them stay static, export, then rig them to the physics nodes or do actual cloth simulation or whatever in your 3D software. The autorig is here only to make most anims look less awkward when previewing.
If you're wondering why Joker looks so good in comparison for example it's because his outfit's uses baked physics sim and isn't simulated at runtime.

Makes sense, wasn't sure if it was something worth reporting and I've been able to work around it p easily, as far as I know this is the only model I've encountered with this issue. Thanks for the info though!
## Post #344
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2021-03-06T19:18:32+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Question regarding Hyrule Warriors Age of Calamity
Does anyone know where the textures are for the paragliders? I've found the 1 that Link uses but can't find the ones for other characters.
## Post #345
- Username: Firefly177
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 17, 2021 3:13 am
- Post datetime: 2021-03-17T20:11:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I got some problems with OPPW4 animations. They all appear to be completely broken. Maybe I did something wrong?

[https://i.gyazo.com/ca7a20aecc17d8eb075 ... f04de0.mp4](https://i.gyazo.com/ca7a20aecc17d8eb0751befd63f04de0.mp4)
## Post #346
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-03-17T21:01:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Firefly177 ↑Thu Mar 18, 2021 4:11 am at Thu Mar 18, 2021 4:11 am
>
> 
I got some problems with OPPW4 animations. They all appear to be completely broken. Maybe I did something wrong?

https://i.gyazo.com/ca7a20aecc17d8eb075 ... f04de0.mp4

Thanks for the report, I broke something with the last versions. I'll push a fix when I have the time.

EDIT : This is now fixed in the latest version [https://github.com/Joschuka/Project-G1M ... g/v1.4.2.2](https://github.com/Joschuka/Project-G1M/releases/tag/v1.4.2.2)
## Post #347
- Username: Firefly177
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 17, 2021 3:13 am
- Post datetime: 2021-03-18T20:45:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Thanks for the fast fix Joschka!

Now I got a little problem...
How can I fix that the weapon is on an 90° degree in all animations?
[https://gyazo.com/a79062cab91d00798155f4fb3d8504ed](https://gyazo.com/a79062cab91d00798155f4fb3d8504ed)

Edit:
Better picture:
[https://i.gyazo.com/93b6f54d251e17b8ebb ... 945623.png](https://i.gyazo.com/93b6f54d251e17b8ebb06e4d00945623.png)
## Post #348
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-03-18T21:10:49+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Firefly177 ↑Fri Mar 19, 2021 4:45 am at Fri Mar 19, 2021 4:45 am
>
> 
Thanks for the fast fix Joschka!

Now I got a little problem...
How can I fix that the weapon is on an 90° degree in all animations?
https://gyazo.com/a79062cab91d00798155f4fb3d8504ed

Edit:
Better picture:
https://i.gyazo.com/93b6f54d251e17b8ebb ... 945623.png

Ah yeah I can't do much about that, basically Koei has some special meshes that don't have weights or bone indices at all. Usually these are physics meshes but it happens that some rare other meshes don't have some either (they have a special flag for these). I don't know how they end up getting attached for now unfortunately.
What happens here is that the very basic autorig functionality weighs the mesh to the closest bone. But it's probably not the right one and it's done roughly, hence the wrong weapon positionning. If you disable the autorig (turn off NUN autorig in the plugin's option), both his cape and weapon won't move during the animation. In the cape's case that's because it's supposed to be physics driven at runtime, in the weapon's case that's just because it doesn't have weights at all.


However as you can see he has a dedicated socket bone for the weapon 

So what I'd recommend would be to export the animations and in your 3d software attach the submesh manually by either using a location/rotation constraint or by fully skinning the mesh to the socket bone.

Hope that helps.
## Post #349
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-03-18T21:14:13+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

OK actually just after posting this I think I got an idea about how they attach it by taking another look. I'll try something in a few days when I have the time since that will need a bit of testing but that's promising.

EDIT : Ok I don't know how I overlooked that before, it was actually pretty simple. Grab the latest plugin version on github and the weapon will be attached correctly.
## Post #350
- Username: Firefly177
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 17, 2021 3:13 am
- Post datetime: 2021-03-18T22:35:45+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Thank you for your awesome work- I'll try it tomorrow!

Edit: I meant the first idea you had. Not the fix. God damn, you're fast.
## Post #351
- Username: Firefly177
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 17, 2021 3:13 am
- Post datetime: 2021-03-18T22:38:13+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Mar 19, 2021 5:14 am at Fri Mar 19, 2021 5:14 am
>
> 
OK actually just after posting this I think I got an idea about how they attach it by taking another look. I'll try something in a few days when I have the time since that will need a bit of testing but that's promising.

EDIT : Ok I don't know how I overlooked that before, it was actually pretty simple. Grab the latest plugin version on github and the weapon will be attached correctly.

My dude you said a few days. Can I donate somewhere?

You fix it faster then I can thank you!
## Post #352
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-03-19T12:31:00+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Firefly177 ↑Fri Mar 19, 2021 6:38 am at Fri Mar 19, 2021 6:38 am
>
> 
My dude you said a few days. Can I donate somewhere?

You fix it faster then I can thank you!

No worries, the fix was very simple after all, I just overlooked something obvious for this submesh type.
I appreciate the intent but I don't take donations, I just do REing for fun/learning. Buy yourself something nice with that money and drink to my health  ; )
## Post #353
- Username: U653748
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 05, 2015 5:33 am
- Post datetime: 2021-03-20T10:28:56+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

greetings all,

I ran into a strange problem after getting back into extracting Fatal frame 5 models again, it's similar to the issue i ran into last sept in which it does not display all the correct pieces on the swappable parts versions of the characters. However this time it's reading those individual swappable parts models just fine, but not the skeletons for them and a few parts are actually missing in the g1m version of the main body when viewed in Noesis.


(I am using the latest version of the plug in downloaded aprox an hour ago and a half ago at the time of the post and still getting the same result,
The older python script version appears to read the model just fine, so it appears to be an issue with the .dll version )

In the g1m file being read by noesis, the character is missing her hair as well as a flexible piece of cloth that is supposed to be apart of her top. (See examples 1 and 2 below)

Example1: G1m Version in Noesis 
[https://i.gyazo.com/59c66c7357f749d93b7 ... ac02cc.png](https://i.gyazo.com/59c66c7357f749d93b701fa569ac02cc.png)

Example 2: OBJ version in Noesis
[https://i.gyazo.com/d9cf4eb6b93cff95a31 ... 017523.png](https://i.gyazo.com/d9cf4eb6b93cff95a3193858af017523.png)

In the OBJ version those parts are present, however they are out of place and centered on the grid in Noesis (turned off for better viewing). When extracting other versions of the same model with the same plug in these pieces are not only present, but also in their correct positions and with a skeleton. 

Normally that wouldn't be an issue having multiple versions of the model, however this is the default version of this particular character, Labeled "H_YRI_A" or the A Version. it's counterpart labeled "H_YRI_L" or the L version do not share the same textures exactly and thus are not interchangeable. See example below

Texture difference between A and L versions
[https://i.gyazo.com/9f9a2aa25e3c6492e63 ... 357ec5.jpg](https://i.gyazo.com/9f9a2aa25e3c6492e63e131332357ec5.jpg)

as you can see the A version has 3 variants to swap between, and the L version only has one, the UV's for the A are sized differently from the L model to accommodate the 3 variations. the skin and face textures are also altered between the A and L models in a similar manner.

Link to the problem model in question.
[https://www.mediafire.com/file/4tgg7uax ... es.7z/file](https://www.mediafire.com/file/4tgg7uaxhq7fedv/H_YRI_A_Samples.7z/file)
## Post #354
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-03-20T11:12:33+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Tools -> Project G1M -> Merge all assets in same folder

Then open whatever g1m in your folder.
## Post #355
- Username: U653748
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 05, 2015 5:33 am
- Post datetime: 2021-03-20T11:17:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Mar 20, 2021 7:12 pm at Sat Mar 20, 2021 7:12 pm
>
> 
Tools -> Data Viewer -> Merge all assets in same folder

Then open whatever g1m in your folder.That did the trick, thanks for the help
## Post #356
- Username: FannyTijeras
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 12, 2020 5:10 am
- Post datetime: 2021-03-20T21:48:55+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

im unable to make the plugin work 
the tools seem to be missing as well and i dont know what to do to fix it
## Post #357
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-04-02T07:54:42+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hello,how can i get the animation file from Dynasty Warriors 9 and load it in noesis? I have the g1m file from the linkdata and load it in blender.Really thanks.
## Post #358
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-04-03T21:29:38+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from cjdung ↑Fri Apr 02, 2021 3:54 pm at Fri Apr 02, 2021 3:54 pm
>
> 
Hello,how can i get the animation file from Dynasty Warriors 9 and load it in noesis? I have the g1m file from the linkdata and load it in blender.Really thanks.

Hi,
I don't have the game myself but if this is like other linkdata games then animations are in separate folders when you extract. So for example folder 3000 or something would have the model while folder 4000, 4001 etc would have the animations.
Unfortunately there are probably no names so you'd have to find the g1a/g2a anim files and do some trial and error until you find the right ones. 

So basically try to find folders with anim files, try these folders one by one on your character, then try to find a rule of thumb to match anims with the corresponding models (for example folder number + 1200 = anim folder or something like that). 
This is the best I can do to help, without names you're going to need to do some manual digging.
## Post #359
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-04-06T07:01:08+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sun Apr 04, 2021 5:29 am at Sun Apr 04, 2021 5:29 am
>
> 
cjdung wrote: ↑Fri Apr 02, 2021 3:54 pm
Hello,how can i get the animation file from Dynasty Warriors 9 and load it in noesis? I have the g1m file from the linkdata and load it in blender.Really thanks.


Hi,
I don't have the game myself but if this is like other linkdata games then animations are in separate folders when you extract. So for example folder 3000 or something would have the model while folder 4000, 4001 etc would have the animations.
Unfortunately there are probably no names so you'd have to find the g1a/g2a anim files and do some trial and error until you find the right ones. 

So basically try to find folders with anim files, try these folders one by one on your character, then try to find a rule of thumb to match anims with the corresponding models (for example folder number + 1200 = anim folder or something like that). 
This is the best I can do to help, without names you're going to need to do some manual digging.
I don't know how to extract the linkdata into the g1a/g2a anim files.Basically I get the linkdata file extracted as .data file and dds texture, and I drag it on the ffsnt tool which will extracted .ascii model and I can import the model in blender.I just don't know how to get the g1a/g2a anim files.Hope you can show me how to access these files,thanks a lot.
## Post #360
- Username: Tangil
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2020 5:06 pm
- Post datetime: 2021-05-03T01:32:48+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Suppose if I want to merge a character's head with one of the generic class body models. How would I go around to do something like that?

I have attempted to do a merge with Marianne's head and one of the generic Myrimdon female body models by moving the g1m files for Marianne's head in the same place when the Myrimdon body g1m files, but it resulted in height mismatch with the neck and head floating just a little bit above the Myrimdon body model.

Also one more thing, for the [ female chest modifier](female%20chest%20modifier), how do you apply that modifier into generic class body models, so that chest appears smaller or larger depending on the modifier? Or is that something that has done in our modeling program?
## Post #361
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-05-03T11:49:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Tangil ↑Mon May 03, 2021 9:32 am at Mon May 03, 2021 9:32 am
>
> 
Suppose if I want to merge a character's head with one of the generic class body models. How would I go around to do something like that?

I have attempted to do a merge with Marianne's head and one of the generic Myrimdon female body models by moving the g1m files for Marianne's head in the same place when the Myrimdon body g1m files, but it resulted in height mismatch with the neck and head floating just a little bit above the Myrimdon body model.

Also one more thing, for the  female chest modifier, how do you apply that modifier into generic class body models, so that chest appears smaller or larger depending on the modifier? Or is that something that has done in our modeling program?

Every character has some modifier values to adapt the class model to themselves. You can see those values using Progenitor (check the "other" section in the persona data editor screenshot) [https://github.com/three-houses-researc ... ata-editor](https://github.com/three-houses-research-team/Progenitor#persondata-editor)
Part 1 means before the timeskip, a value of -1 means that the post timeskip value is the same as the pretimeskip one. So you'll have to scale the body model with the given values.
For the chest modifier I think you'll just have to scale the corresponding bones with the given values, I never tried it myself but that should work.
## Post #362
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-05-13T10:12:44+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi Everyone!

I´m new at this and I´m exporting the models for Nioh 2 I have access to all the characters and item models from the base game and the first 2 DLCs thanks to Daemon´s tool, but I havent been able to find the data for the 3 DLC, The First Samurai, have anyone been able to find it?
## Post #363
- Username: christiankin2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 20, 2021 5:56 am
- Post datetime: 2021-05-15T12:31:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi,

when do you think we will be able to fully merge the environment from AOC? like export it in full instead of pieces.
## Post #364
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-05-17T11:33:22+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from christiankin2 ↑Sat May 15, 2021 8:31 pm at Sat May 15, 2021 8:31 pm
>
> 
Hi,

when do you think we will be able to fully merge the environment from AOC? like export it in full instead of pieces.

I'm working on other projects right now, I can't give an ETA sorry.
## Post #365
- Username: DiMickfoxed65
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Feb 13, 2020 12:41 pm
- Post datetime: 2021-05-17T22:17:48+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Im fighting with the Toukiden2 Files because well, the comand i used is the next:
"Cethleann\Cethleann.DataExporter.exe -- -g Toukiden2 C:\Users\diego\Toukiden2\eXPORT C:\Users\diego\Toukiden2\LINKDATA0"

So is right my command or i need do something with it because everytime i ejecute it, appears a system error saying it cant run the app   

So any help?
## Post #366
- Username: lsbg18
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 26, 2021 6:20 pm
- Post datetime: 2021-05-30T14:33:46+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Wed Feb 05, 2020 1:58 am at Wed Feb 05, 2020 1:58 am
>
> 
Script updated

-KSLT support. You can now open and preview these files. These are UI textures.
-G2A version 0200 and 0300 Big endian should now work. I didn't have many samples so tell me if you have any issue with these.
-My partner Yretenai added Nioh support to her Cethleann tools, you can now extract models and animations from this game. HOWEVER the script as it currently is will take some time to load the models so be patient if you want to preview the models right now. I plan to rework some parts to speed things up.
I know the Nioh game has two generation.so which vervison the Nioh you said ，1 or 2？and the version？PC or PS4？I want to extract the animation.
## Post #367
- Username: lsbg18
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 26, 2021 6:20 pm
- Post datetime: 2021-05-30T14:53:27+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from AzothRaven ↑Thu May 13, 2021 6:12 pm at Thu May 13, 2021 6:12 pm
>
> 
Hi Everyone!

I´m new at this and I´m exporting the models for Nioh 2 I have access to all the characters and item models from the base game and the first 2 DLCs thanks to Daemon´s tool, but I havent been able to find the data for the 3 DLC, The First Samurai, have anyone been able to find it?
Can you tell me whether the animation of Nioh 2 can be extracted？Which version you export ,PC or PS4?
## Post #368
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-01T15:18:52+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from lsbg18 ↑Sun May 30, 2021 10:33 pm at Sun May 30, 2021 10:33 pm
>
> 
Joschka wrote: ↑Wed Feb 05, 2020 1:58 am
Script updated

-KSLT support. You can now open and preview these files. These are UI textures.
-G2A version 0200 and 0300 Big endian should now work. I didn't have many samples so tell me if you have any issue with these.
-My partner Yretenai added Nioh support to her Cethleann tools, you can now extract models and animations from this game. HOWEVER the script as it currently is will take some time to load the models so be patient if you want to preview the models right now. I plan to rework some parts to speed things up.

I know the Nioh game has two generation.so which vervison the Nioh you said ，1 or 2？and the version？PC or PS4？I want to extract the animation.

Both Nioh1 and 2 work, use the PS4 versions, it's the simplest ones to get the files from. You'll be able to unpack the bundles it comes with using Cethleann.Unbundler
## Post #369
- Username: MarineIdle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 08, 2021 2:53 am
- Post datetime: 2021-06-08T00:50:44+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I succeeded in getting the models by using QuickBMS to get the initial .MDL files, then using FFSNT ([viewtopic.php?f=16&t=18042](https://forum.xentax.com/viewtopic.php?f=16&t=18042)) to convert the .MDL files into .G1M and .G1T files. Finally I used this Noesis plugin to view the merged assets (.G1M & .G1T files).

A quick tip for those of you trying to extract models from the PC version of Nioh 2:

If Noesis crashes when attempting to view the merged assets in the model viewer, try deleting the 00.g1m file. For whatever reason, that file seems to cause problems for this Noesis g1m/g1t/g1a importer plugin.

On the other hand, if you're using Cethleann to get the .G1M and .G1T files, this isn't a problem. Cethleann labels the 00.g1m file as 0000.exhead so Noesis won't accidentally include the file when merging assets.
## Post #370
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-08T10:12:19+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from MarineIdle ↑Tue Jun 08, 2021 8:50 am at Tue Jun 08, 2021 8:50 am
>
> 
If Noesis crashes when attempting to view the merged assets in the model viewer, try deleting the 00.g1m file. For whatever reason, that file seems to cause problems for this Noesis g1m/g1t/g1a importer plugin.

This is because ffsnt wrongly labels the first file as a g1m file, if you look at it in hex you'll see it that it doesn't have the g1m magic. Hence the crash since I currently only check the magic of the first file (the one you double click on in Noesis).
So yeah better use Cethleann directly, this plugin is primarly meant to be used with it since we worked on these games together.
## Post #371
- Username: Tangil
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2020 5:06 pm
- Post datetime: 2021-06-10T00:52:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon May 03, 2021 7:49 pm at Mon May 03, 2021 7:49 pm
>
> 
Every character has some modifier values to adapt the class model to themselves. You can see those values using Progenitor (check the "other" section in the persona data editor screenshot) https://github.com/three-houses-researc ... ata-editor
Part 1 means before the timeskip, a value of -1 means that the post timeskip value is the same as the pretimeskip one. So you'll have to scale the body model with the given values.
For the chest modifier I think you'll just have to scale the corresponding bones with the given values, I never tried it myself but that should work.

Hey again, thanks for help earlier.

I do have one more question for you. I am trying to get access to the fixed_materialdata file via Progenitor, so I can retrieve the material data for the skin coloring used in-game (That is if it's in that file.), but the option to open a fixed_materialdata file is grayed out in the Progenitor program and I am not really sure how to get that option to open up.
## Post #372
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-10T10:37:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Tangil ↑Thu Jun 10, 2021 8:52 am at Thu Jun 10, 2021 8:52 am
>
> 
Joschka wrote: ↑Mon May 03, 2021 7:49 pm
Every character has some modifier values to adapt the class model to themselves. You can see those values using Progenitor (check the "other" section in the persona data editor screenshot) https://github.com/three-houses-researc ... ata-editor
Part 1 means before the timeskip, a value of -1 means that the post timeskip value is the same as the pretimeskip one. So you'll have to scale the body model with the given values.
For the chest modifier I think you'll just have to scale the corresponding bones with the given values, I never tried it myself but that should work.


Hey again, thanks for help earlier.

I do have one more question for you. I am trying to get access to the fixed_materialdata file via Progenitor, so I can retrieve the material data for the skin coloring used in-game (That is if it's in that file.), but the option to open a fixed_materialdata file is grayed out in the Progenitor program and I am not really sure how to get that option to open up.

-Open the head model (or full model if NPC like Rhea, Jeralt or whoever if the model isn't split) of the character you want.
In dataviewer, click on the different submeshes until you find the one representing the face. Note down the submesh index (0 here) 
-Open the g1m file in 010 and execute our g1m binary template. Deploy the G1MG section, then in the submeshes section jump to the index you noted before and note the shader param index associated : 
-Then jump to the 2nd section of the G1MG section (shader one), go to the index you noted above and in this one go to the "ccrMCol" value. The value there will be the skin Color in RGB. 

If you don't have 010 you can also just directly do a ccrMCol search in whatever hex editor you have, the 3 float values just after are the RGB ones 
With this method you'll sometimes have several results since other materials use this parameter but you'll have at most 3 or 4 to try so it's n big deal

Btw considering the number of FETH questions you ask I'd suggest joining the FETH discord server, all the members of the FETH research team are there.
## Post #373
- Username: Tangil
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2020 5:06 pm
- Post datetime: 2021-06-10T17:00:20+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Thu Jun 10, 2021 6:37 pm at Thu Jun 10, 2021 6:37 pm
>
> 
Btw considering the number of FETH questions you ask I'd suggest joining the FETH discord server, all the members of the FETH research team are there.

My apologies, I really couldn't find any good places to discuss about that. If you can provide the discord link, I will happily check it out.
## Post #374
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-06-10T17:04:14+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Tangil ↑Fri Jun 11, 2021 1:00 am at Fri Jun 11, 2021 1:00 am
>
> 
Joschka wrote: ↑Thu Jun 10, 2021 6:37 pm
Btw considering the number of FETH questions you ask I'd suggest joining the FETH discord server, all the members of the FETH research team are there.


My apologies, I really couldn't find any good places to get to discuss about. If you can provide the discord link, I will happily check it out.

Oh I wasn't reproaching you, just that it'd be more convenient for you to join instead of waiting for my answers. I'll PM you the invite link.
## Post #375
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2021-06-18T01:57:38+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Samurai Warriors 5 (Japanese Switch Demo) is compatible with the noesis tool
## Post #376
- Username: Equirah
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 16, 2021 4:49 am
- Post datetime: 2021-06-26T09:44:21+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Would it be possible to get a step by step tutorial and/or a list of programs and plugins required?

I'm trying to extract models from Nioh 2 and Dissidia NT, so far only managed to extract Nioh 2 with quickbms but when I run the .dat files through daemon1's tool most texture files are broken, and I can't open the models with Noesis.
As for Dissida NT I've gotten nowhere with that game; tried to link the files but that didn't work, tried to mem dump it but only got a 4Gb file out of it and I'm out of ideas.

Edit: Figured out you have to run the .mdl "twice" by running the .g1m files it extracts, out of the 3 files only one seemed usable but it looks like this:



Nioh Model.jpg (238.94 KiB) Viewed 618 times



It might be rubble but i don't remember ever seeing this model in the game and when i panned the camera or zoomed in/out ddifferent areas of the model became visible/invisible. Any suggestions?
## Post #377
- Username: liquer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 28, 2021 10:44 pm
- Post datetime: 2021-06-29T06:11:46+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from demonslayerx8 ↑Fri Jun 18, 2021 9:57 am at Fri Jun 18, 2021 9:57 am
>
> 
Samurai Warriors 5 (Japanese Switch Demo) is compatible with the noesis tool
Could you tell me how to find the g1t textures corresponding to the g1m files?
I find all the g1m models but have no idea about g1t files.
Thanks.
## Post #378
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2021-07-12T09:00:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from liquer ↑Tue Jun 29, 2021 2:11 pm at Tue Jun 29, 2021 2:11 pm
>
> 
demonslayerx8 wrote: ↑Fri Jun 18, 2021 9:57 am
Samurai Warriors 5 (Japanese Switch Demo) is compatible with the noesis tool


Could you tell me how to find the g1t textures corresponding to the g1m files?
I find all the g1m models but have no idea about g1t files.
Thanks.
it's a goose hunt.
## Post #379
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-08-16T11:17:56+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Version 1.5 is now available

-Joints are now colored (green for "classic" joints, blue for physics nodes)
-G2A version 4 support
-New G1T format support
## Post #380
- Username: zxhxy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 08, 2020 4:27 pm
- Post datetime: 2021-08-20T08:12:11+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Aug 16, 2021 7:17 pm at Mon Aug 16, 2021 7:17 pm
>
> 
Version 1.5 is now available

-Joints are now colored (green for "classic" joints, blue for physics nodes)
-G2A version 4 support
-New G1T format support
How do I find the g1M action file for my character
## Post #381
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2021-10-25T07:00:46+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hello friend, I am new here, and I would like you to help me, you will see I have an error or problem when importing G1A files from doa 6 V1.22 and then converting them to FBX format and working with them with G1M models and G1T textures I have no problems but with the animations yes and I do not know what to do or I do not know what I am doing wrong and the truth is I read your previous or old comments where you explained all that to a user but I did not understand much to say since I am that guy of people who learn better and more easily through videos or even images rather than in writing but hey I don't know if I express myself well I mean if I explain my problem correctly by the way I am using the most current version of your plugin or script for noesis Please I hope you can help me I want you to guide me and well I leave that image as a reference I do not know if it works I will be waiting for your answer thank you
[00.jpg](https://xentaxbackup.github.io/file/21074_00.jpg)
## Post #382
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-25T10:31:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from RoockyGTA ↑Mon Oct 25, 2021 3:00 pm at Mon Oct 25, 2021 3:00 pm
>
> 
Hello friend, I am new here, and I would like you to help me, you will see I have an error or problem when importing G1A files from doa 6 V1.22 and then converting them to FBX format and working with them with G1M models and G1T textures I have no problems but with the animations yes and I do not know what to do or I do not know what I am doing wrong and the truth is I read your previous or old comments where you explained all that to a user but I did not understand much to say since I am that guy of people who learn better and more easily through videos or even images rather than in writing but hey I don't know if I express myself well I mean if I explain my problem correctly by the way I am using the most current version of your plugin or script for noesis Please I hope you can help me I want you to guide me and well I leave that image as a reference I do not know if it works I will be waiting for your answer thank you

-Put the g1m file and the g1a/g2a file you want to preview in the same folder, for example (model in red, anim in blue) : 

-Under Tools -> project G1M make sure that merge all assets in the same folder is ticked
-Then just open the g1m file and the animations will be loaded automatically on the model
## Post #383
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2021-10-26T00:10:54+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Well hello again friend I did what you told me in version 4439 of noesis and it did not work for me when importing the G1M model it did not load me and when selecting it it gave me crashed and it closed me and I used that method in version 4455 and yes The G1M model reads me but the animations do not appear and that I did what you said that all the files were in the same folder I also noticed that the options of your plugin or script that I am doing wrong or what else I can do do not appear to be able to export everything to fbx? And also what version do you use of the noesis? sorry for the disturbances
[10.jpg](https://xentaxbackup.github.io/file/21076_10.jpg)
## Post #384
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-26T05:09:17+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from RoockyGTA ↑Tue Oct 26, 2021 8:10 am at Tue Oct 26, 2021 8:10 am
>
> 

Well hello again friend I did what you told me in version 4439 of noesis and it did not work for me when importing the G1M model it did not load me and when selecting it it gave me crashed and it closed me and I used that method in version 4455 and yes The G1M model reads me but the animations do not appear and that I did what you said that all the files were in the same folder I also noticed that the options of your plugin or script that I am doing wrong or what else I can do do not appear to be able to export everything to fbx? And also what version do you use of the noesis? sorry for the disturbances

-First make sure that you have the latest Noesis version ; "Tools" -> "check for updates"
-Go to "Tools"->"Display plugin tools". Then "Tools"->"project g1m"-> make sure that the option "merge all assets in the same folder" is selected.
-Don't open the g1m directly there because it will load everything in this folder. Copy the g1m model and the animation files you want in another folder.
-Then open the g1m file
## Post #385
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2021-10-30T08:06:52+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi

When i export the character for Noesis the dress bones are not connected to the dress. The dress bones are connected to a white mesh how to fix this ? 

thanks
## Post #386
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-30T11:48:45+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Pigeon ↑Sat Oct 30, 2021 4:06 pm at Sat Oct 30, 2021 4:06 pm
>
> 
Hi

When i export the character for Noesis the dress bones are not connected to the dress. The dress bones are connected to a white mesh how to fix this ? 

thanks

Yes, that's because the cloth/hair meshes sometimes don't have classic skinning data, their vertices are moved at runtime using physics simulation in a weird way. The "dress bones" aren't true bones, I represent these this way since I don't have other choices, if you click on the skeleton icon in Noesis, you can see these in blue. The white meshes you're referring too are driver meshes, 
I put both these physics nodes and the driver meshes so you can use them to rig the cloth however you want : you can just rig to the physics nodes, use the Blender data transfer modifier or whatever your editor has to transfer the weights from the driver mesh to the actual cloth/hair mesh or just do proper cloth simulation.
## Post #387
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2021-10-31T07:55:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

[img]

Friend I did everything you told me and it finally worked thank you very much I understood it and it turned out very well now one more question is that as the models are separated by bodies, heads and hair, if I export the animation in fbx format and load it in a program like blender or 3ds max will only see the animation in that part of the body with which it exported? In a few words, I mean if I export the animation of the whole body but not of the head, the animation will not be seen in that missing part? in this case of the head I do not know if I explain or express it well I hope you have understood me
[20.jpg](https://xentaxbackup.github.io/file/21110_20.jpg)
## Post #388
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-31T12:02:53+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from RoockyGTA ↑Sun Oct 31, 2021 3:55 pm at Sun Oct 31, 2021 3:55 pm
>
> 
Friend I did everything you told me and it finally worked thank you very much I understood it and it turned out very well now one more question is that as the models are separated by bodies, heads and hair, if I export the animation in fbx format and load it in a program like blender or 3ds max will only see the animation in that part of the body with which it exported? In a few words, I mean if I export the animation of the whole body but not of the head, the animation will not be seen in that missing part? in this case of the head I do not know if I explain or express it well I hope you have understood me

Yes it's easy, do the same thing but put the head g1m file in the folder too. So you'll have head.g1m, body.g1m and the animations. Then open one of the g1m in Noesis and everything will be merged and loaded directly.
## Post #389
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2021-11-02T04:50:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

[img]

Hear one more question and is that here what happened? I put only the textures that are from the correct body parts but it gave me that error, what can I do there? It is not as important as the animations but I would like to know out of curiosity why this happened?
[50.jpg](https://xentaxbackup.github.io/file/21121_50.jpg)
## Post #390
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-11-02T07:38:23+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from RoockyGTA ↑Tue Nov 02, 2021 12:50 pm at Tue Nov 02, 2021 12:50 pm
>
> 
[img]

Hear one more question and is that here what happened? I put only the textures that are from the correct body parts but it gave me that error, what can I do there? It is not as important as the animations but I would like to know out of curiosity why this happened?

This is because the G1T files are split and need to be recombined into a single one. Check this tutorial here : [viewtopic.php?p=164248#p164234](https://forum.xentax.com/viewtopic.php?p=164248#p164234)
New Cethleann link that you'll need [https://github.com/yretenai/Cethleann/r ... ag/1.1.104](https://github.com/yretenai/Cethleann/releases/tag/1.1.104)
When you'll have the G1T recombined just put it next to the models and animations.
## Post #391
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2021-11-07T08:08:23+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

we dont support kscl format from fatal frame 5 remastered?
## Post #392
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-11-07T08:15:24+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from ngovandang ↑Sun Nov 07, 2021 4:08 pm at Sun Nov 07, 2021 4:08 pm
>
> 
we dont support kscl format from fatal frame 5 remastered?

I don't even know what these are, kslt were supported in fmt_g1m before and I never bothered adding these back to project G1M considering the lack of interest. If you're referring to these I can add them back when I have the time.
## Post #393
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2021-11-07T08:19:13+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sun Nov 07, 2021 4:15 pm at Sun Nov 07, 2021 4:15 pm
>
> 
ngovandang wrote: ↑Sun Nov 07, 2021 4:08 pm
we dont support kscl format from fatal frame 5 remastered?


I don't even know what these are, kslt were supported in fmt_g1m before and I never bothered adding these back to project G1M considering the lack of interest. If you're referring to these I can add them back when I have the time.
Oh right, its KSLT, hehe
here is samples
[ff system_layout.rar](https://xentaxbackup.github.io/file/21174_ff system_layout.rar)
## Post #394
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-11-07T08:37:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from ngovandang ↑Sun Nov 07, 2021 4:19 pm at Sun Nov 07, 2021 4:19 pm
>
> 
Joschka wrote: ↑Sun Nov 07, 2021 4:15 pm
ngovandang wrote: ↑Sun Nov 07, 2021 4:08 pm
we dont support kscl format from fatal frame 5 remastered?


I don't even know what these are, kslt were supported in fmt_g1m before and I never bothered adding these back to project G1M considering the lack of interest. If you're referring to these I can add them back when I have the time.

Oh right, its KSLT, hehe
here is samples

Alright I'll add support for these later, in the meantime you can use the old python plugin for these, it opens your samples without problem (make sure to remove it when you're done with KSLT files or it will be used instead of the DLL plugin) [https://github.com/Joschuka/fmt_g1m](https://github.com/Joschuka/fmt_g1m)
## Post #395
- Username: DonSkook
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 05, 2020 10:35 am
- Post datetime: 2021-11-12T15:47:58+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Anyone found a way to reimport the edited models back in the game proper? 

It's fine that I can extract the models and edit them but the goal is to make mods, so I need a way to put them back into the game. 

How do we go about this?
## Post #396
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-11-13T17:34:24+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from DonSkook ↑Fri Nov 12, 2021 11:47 pm at Fri Nov 12, 2021 11:47 pm
>
> 
Anyone found a way to reimport the edited models back in the game proper? 

It's fine that I can extract the models and edit them but the goal is to make mods, so I need a way to put them back into the game. 

How do we go about this?

There's this: [https://www.loverslab.com/topic/120211- ... edelbe-30/](https://www.loverslab.com/topic/120211-vagonumero13-tools-redelbe-rdbtool-g1mtools-doa6decsave-update-17-aug-redelbe-30/).
It works with DOA6, I'm not sure if this tool works with other Koei Tecmo games.
## Post #397
- Username: banan039eu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 12, 2020 4:52 am
- Post datetime: 2021-11-27T09:39:51+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Nov 21, 2020 10:27 pm at Sat Nov 21, 2020 10:27 pm
>
> 
Version 1.4 is now live
-Implements a new UV datatype used in the final release of Hyrule Warriors 2
-New option to choose to completely disable NUNO nodes (the physics mesh will still be reconstructed before, all the extra bones and drivers will just not be there)

I also started to work on reconstructing maps, more about this later since it's sill very early WIP

Hi Joschka!

I am looking for Hyrule Warriors: Age of Calamity maps objects coordinates. I could not find them in  KIDSSystemResource directory. Could You please tell me which directory contains files with such coordinates? I am only asking for pointing in right direction, I want to find those coordinates myself
## Post #398
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-11-27T10:16:55+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from banan039eu ↑Sat Nov 27, 2021 5:39 pm at Sat Nov 27, 2021 5:39 pm
>
> 
Joschka wrote: ↑Sat Nov 21, 2020 10:27 pm
Version 1.4 is now live
-Implements a new UV datatype used in the final release of Hyrule Warriors 2
-New option to choose to completely disable NUNO nodes (the physics mesh will still be reconstructed before, all the extra bones and drivers will just not be there)

I also started to work on reconstructing maps, more about this later since it's sill very early WIP




Hi Joschka!

I am looking for Hyrule Warriors: Age of Calamity maps objects coordinates. I could not find them in  KIDSSystemResource directory. Could You please tell me which directory contains files with such coordinates? I am only asking for pointing in right direction, I want to find those coordinates myself

Checking my old notes the coordinates should be in the KIDSSystemResource\kidsobjdb, a bunch of these databases are for maps. After dumping these to text which the Nyotengu util you should see that some of these have "Float32 WorldPosition" and "Float32 WorldQuaternion" fields, along with the KTID to the actual physical object + some parenting info sometimes.
## Post #399
- Username: banan039eu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 12, 2020 4:52 am
- Post datetime: 2021-11-27T10:30:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Thank You for such quick answer! Do You happen to know the command for extracting KIDSSystemResource files to plaintext using Nyotengu? I have extracted them using fid_utility.exe (a tool I found online for Dead or Alive 6) but most data were lost during conversion process
## Post #400
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-11-27T14:41:39+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from banan039eu ↑Sat Nov 27, 2021 6:30 pm at Sat Nov 27, 2021 6:30 pm
>
> 
Thank You for such quick answer! Do You happen to know the command for extracting KIDSSystemResource files to plaintext using Nyotengu? I have extracted them using fid_utility.exe (a tool I found online for Dead or Alive 6) but most data were lost during conversion process

Iirc you just need to do 
```
Nyotengu.Database.exe @FILE > @FILE.txt"
```

Replace @FILE by one of the files in the kidsobjdb folders and it should dump the result to a txt file with the same name
## Post #401
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2021-11-28T04:02:36+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hello everyone can anyone help me to extract n DOAX VenusVacatio steam ver files
## Post #402
- Username: xathu0904
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 06, 2018 10:25 pm
- Post datetime: 2021-12-03T07:54:42+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

anyone know how to edit .anmpk file on fatal frame 5 ? i try to swap it but game crash
## Post #403
- Username: Jlripps
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 22, 2019 1:30 pm
- Post datetime: 2021-12-09T12:02:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hey A bit slow, forgive me, Trying to extract Models from Fatal Frame 5 Wiiu, got as far as the .GMPK and extracted that, but no model? where are the models located at? and what toll do i use?
## Post #404
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2022-02-19T06:00:53+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hello friend, how long have I had a new question and maybe it will be the last I don't know but I want to export the animation of doa 6 and then import it into the 3ds max program I use the 2010 version and an FBX file plugin or tell me should I export it in another type format such as BVH? to then apply it on a biped? so that you understand me better how should I export the animation to import it and edit it in a 3d program?
[Export Media File.jpg](https://xentaxbackup.github.io/file/21812_Export Media File.jpg)
## Post #405
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2022-02-19T18:31:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Nov 27, 2021 10:41 pm at Sat Nov 27, 2021 10:41 pm
>
> 
banan039eu wrote: ↑Sat Nov 27, 2021 6:30 pm
Thank You for such quick answer! Do You happen to know the command for extracting KIDSSystemResource files to plaintext using Nyotengu? I have extracted them using fid_utility.exe (a tool I found online for Dead or Alive 6) but most data were lost during conversion process


Iirc you just need to do Code: Select allNyotengu.Database.exe @FILE > @FILE.txt"
Replace @FILE by one of the files in the kidsobjdb folders and it should dump the result to a txt file with the same name

Hello friend, how long have I had a new question and maybe it will be the last I don't know but I want to export the animation of doa 6 and then import it into the 3ds max program I use the 2010 version and an FBX file plugin or tell me should I export it in another type format such as BVH? to then apply it on a biped? so that you understand me better how should I export the animation to import it and edit it in a 3d program?
[Export Media File.jpg](https://xentaxbackup.github.io/file/21816_Export Media File.jpg)
## Post #406
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2022-02-20T14:19:30+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hello, I'm trying to rip Dead or alive 6 animations, in particular face animations.
[https://imgur.com/a/k962Ivd](https://imgur.com/a/k962Ivd) these are my settings, yet noesis won't show the g1a files...i have noesis up to date as well, not sure why the anims won't show up for selection
## Post #407
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2022-02-28T21:07:11+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Solved previous issue by merging assets in the folder
I have a problem with Atelier sophie 2,it just came out. It just crashes. 
[https://www.mediafire.com/file/6wy1a3bc ... l.zip/file](https://www.mediafire.com/file/6wy1a3bcls7axqo/pc00a_model.zip/file) sample model
## Post #408
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-03-01T00:16:32+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Makoto ↑Tue Mar 01, 2022 5:07 am at Tue Mar 01, 2022 5:07 am
>
> 
Solved previous issue by merging assets in the folder
I have a problem with Atelier sophie 2,it just came out. It just crashes. 
https://www.mediafire.com/file/6wy1a3bc ... l.zip/file sample model

They introduced a new cloth update (NUNO5). I'll have to reverse it but I'm busy with other projects right now so no ETA.
## Post #409
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2022-03-10T06:00:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Tue Mar 01, 2022 8:16 am at Tue Mar 01, 2022 8:16 am
>
> 
Makoto wrote: ↑Tue Mar 01, 2022 5:07 am
Solved previous issue by merging assets in the folder
I have a problem with Atelier sophie 2,it just came out. It just crashes. 
https://www.mediafire.com/file/6wy1a3bc ... l.zip/file sample model


They introduced a new cloth update (NUNO5). I'll have to reverse it but I'm busy with other projects right now so no ETA.

Hello friend a question tell me how I can correctly import a doa 6 animation to any 3d program like blender or 3ds max? I use that in the 2010 version but when I want to import the fbx file, nothing opens, nothing happens, the character does not appear with the animation, what am I doing wrong? or something I forget to do in the noesis when exporting? please help
## Post #410
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-03-14T12:23:25+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

please update for AtelierSophie2
## Post #411
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2022-03-18T15:32:49+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Stranger of Paradise Final Fantasy Origin just recently came out. Cethleann Seems to extract the files just fine, ofc, nameless.
G1M files are mildly supported, some crash, some are deformed looking, other seems fine (mainly equipments?).
I didn't check much animations, but they load and there was no crash so far.
Textures also seems to work.

I'll drop a link with some working/not working g1m for if and when Joschka will have time. Thanks~
[https://www.mediafire.com/file/ikpc6k0u ... in.7z/file](https://www.mediafire.com/file/ikpc6k0u95ynusl/FFOrigin.7z/file)
## Post #412
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-03-18T23:12:35+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Allanoon ↑Fri Mar 18, 2022 11:32 pm at Fri Mar 18, 2022 11:32 pm
>
> 
Stranger of Paradise Final Fantasy Origin just recently came out. Cethleann Seems to extract the files just fine, ofc, nameless.
G1M files are mildly supported, some crash, some are deformed looking, other seems fine (mainly equipments?).
I didn't check much animations, but they load and there was no crash so far.
Textures also seems to work.

I'll drop a link with some working/not working g1m for if and when Joschka will have time. Thanks~
https://www.mediafire.com/file/ikpc6k0u ... in.7z/file

This game is crazy, the dev team went all bonkers and made the models/textures unnecessarily large, Sophia (the lady with long gray hair) is nearly 300k polygons, most of them compose the hair . . . why?!, and that's her "basic" (underwear) model, put more polygons on top of that when wearing any armor and combine that with all the polygons from the other characters, enemies AND the stage, no wonder this game runs all wonky on some platforms.
## Post #413
- Username: xrevo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 09, 2016 8:56 am
- Post datetime: 2022-03-19T01:06:07+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

So far my experience with SoP is about the same as Allanoon, some things load, some things crash noesis. Jack Garland is 170k tris for his base model.
## Post #414
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2022-03-19T11:25:08+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

From what I've seen, everything that doesn't work seems to be models with NUNO cloth, I assume it's the new version of NUNO that was previously mentioned that isn't supported yet.
## Post #415
- Username: starfire
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Oct 14, 2018 9:01 am
- Post datetime: 2022-03-19T12:10:24+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

So how do I unpack the game then ?
## Post #416
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-03-20T17:41:56+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Just to post a small update : I've been working on the new NUNO5 during my free time for the past 4 days or so (starting with Atelier 2 and then it turned out that SoP used it too). This new NUNO section is quite complex and they changed the cloth meshes computation too so I had to reverse their new cloth shader on top of this new section. 
I got most of the assets working at this point but there are still some very annoying edge cases (all from SoP) that I need to understand/figure out eventually before a proper release (like some NUNO linked entries and some weird negative cloth weights that I have no idea how to deal with for now).
Needless to say after spending most of my time working with bytes, shader assembly and linear algebra during the last days I'm probably going to take a break before finishing the job completely so I can't really give a proper release window for now.

> Reply from Allanoon ↑Fri Mar 18, 2022 11:32 pm at Fri Mar 18, 2022 11:32 pm
>
> 
G1M files are mildly supported, some crash, some are deformed looking, other seems fine (mainly equipments?).

The "deformed" models you're referring to are actually low LOD asssets ! For some reason they've stopped using the built-in G1M system and put the different LODs in different assets, I saw that in Age of Calamity before too.




On top of the new games support I'll have other additions and I'll take this opportunity to make x64 builds for Noesis64 too.
## Post #417
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-03-21T00:36:57+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Mar 21, 2022 1:41 am at Mon Mar 21, 2022 1:41 am
>
> 
Just to post a small update

thx for all ur time and hard works
## Post #418
- Username: Sreliata
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 30, 2015 3:04 am
- Post datetime: 2022-03-21T02:25:58+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Mar 21, 2022 1:41 am at Mon Mar 21, 2022 1:41 am
>
> 
Just to post a small update ...

Thank you so much for your hard work.
I've spent the my whole day on going through the "Stranger of Paradise" files and can confirm that currently, only the assets that don't really need /use physics, work. Such as Neon (short grey haired girl), most of the men and monsters. I just wanted to say that I really appreciate what you're doing and I am so excited for the updated version. So, so excited.

Again: thank you very much for doing this.
## Post #419
- Username: Tahugamer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 26, 2018 3:46 pm
- Post datetime: 2022-03-21T22:49:51+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Can anyone please share Neon's g1m/g1t?
## Post #420
- Username: Rookie201
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jun 18, 2019 1:19 pm
- Post datetime: 2022-03-23T20:20:39+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Can someone help me with extraction files for Stranger of Paradise Final Fantasy Origin?
Can't figure out how to properly do it
Thanks in advance
## Post #421
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2022-03-25T06:05:07+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Mar 21, 2022 1:41 am at Mon Mar 21, 2022 1:41 am
>
> 
Just to post a small update : I've been working on the new NUNO5 during my free time for the past 4 days or so (starting with Atelier 2 and then it turned out that SoP used it too). This new NUNO section is quite complex and they changed the cloth meshes computation too so I had to reverse their new cloth shader on top of this new section. 
I got most of the assets working at this point but there are still some very annoying edge cases (all from SoP) that I need to understand/figure out eventually before a proper release (like some NUNO linked entries and some weird negative cloth weights that I have no idea how to deal with for now).
Needless to say after spending most of my time working with bytes, shader assembly and linear algebra during the last days I'm probably going to take a break before finishing the job completely so I can't really give a proper release window for now.
Allanoon wrote: ↑Fri Mar 18, 2022 11:32 pm
G1M files are mildly supported, some crash, some are deformed looking, other seems fine (mainly equipments?).


The "deformed" models you're referring to are actually low LOD asssets ! For some reason they've stopped using the built-in G1M system and put the different LODs in different assets, I saw that in Age of Calamity before too.




On top of the new games support I'll have other additions and I'll take this opportunity to make x64 builds for Noesis64 too.

hello friend look so as not to bother you since that is not my intention I will explain it here I could see the animation in an autodesk program it is a file viewer but in the 3ds max program neither the character appears nor much less the animation and that I'm importing the FBX file fine so tell me what can I do? or what am I doing wrong? or what do I need to do? I want to edit the animation help me please
[Autodesk FBX Review (v1.5.2.0).jpg](https://xentaxbackup.github.io/file/22013_Autodesk FBX Review (v1.5.2.0).jpg)
## Post #422
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-03-26T17:46:06+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from RoockyGTA ↑Fri Mar 25, 2022 2:05 pm at Fri Mar 25, 2022 2:05 pm
>
> 
hello friend look so as not to bother you since that is not my intention I will explain it here I could see the animation in an autodesk program it is a file viewer but in the 3ds max program neither the character appears nor much less the animation and that I'm importing the FBX file fine so tell me what can I do? or what am I doing wrong? or what do I need to do? I want to edit the animation help me please

I'm not a 3ds max user so no idea sorry. If you were able to export the fbx from Noesis then the plugin is working as expected. I can't really help more than that, you should ask on 3ds max forums or maybe try another format.
## Post #423
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-03-26T18:42:17+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Version 1.7 is now available

The biggest feature is NUNO5 support, the new physics update introduced by Koei Tecmo. 

-Noesis 64 bit support. This new version introduces 64bit builds. I'll keep including 32bit dlls in the releases but I recommend switching to Noesis64 if you can, especially if you're looking into "big" games. This way you won't have memory constraints anymore.

-Support for NUNO5 physics meshes. This new chunk is used in Atelier Sophie 2 and FF Origins and will most likely be used from now on in the next games. This chunk now enables them to have different physics LODs (compare the number of physics nodes on both pics). I only care about the highest one with the plugin.
 vs 

-Support for NUNO5 subsets. Their vertex shader has a hardcoded limit of 512 control points being fed into the constant buffer. However in games like FFOrigins where they have crazy amounts of nodes, they now have a parent entries to define all of them and then children NUNO entries to cherry-pick the ones necessary for a given submesh. This is why you'll notice big capes etc being split into several submeshes.


-Support for Nintendo Switch texture untiling. It seems that 5 years after the console's release they finally decided to use Switch tiling for their textures (about time...). Touken Ranbu Musou was the first game to use it, texture support is now available for this game

-Support added for G1M v30 and G1A v40. Both were used in older games, including Dynasty Warriors 5. 

Credits:
-Many thanks to DeathChaos for his help with a lot of testing, modding, frame dumping and bug reporting, this new version wouldn't have been available so fast without him. 
-Similarly, thanks to Yretenai for providing me frame dumps that enabled me to start the new cloth shader research.
-Finally, thanks to einherjar007 for sending me some DW5 samples.

N.B.
Reminder for those interested in FF Origins : you can "equip" a character by simply putting his body and accessory g1m files in the same folder then loading whatever one with the "merge all" option. Make sure to disable it if you're looking for a specific g1m file in CharacterEditor/g1m or a similar folder or you'll load every single g1m there. Textures and anims related to a g1m can be found just like you do for other RDB games. If you put everything in the same folder they'll be taken into account too, here's an example where I put 3 g1m files (Jack, a coat, some trousers) and a few anims
## Post #424
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-03-27T06:36:46+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

THANKS
## Post #425
- Username: consume
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 07, 2021 6:12 am
- Post datetime: 2022-03-28T01:50:48+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Tahugamer ↑Tue Mar 22, 2022 6:49 am at Tue Mar 22, 2022 6:49 am
>
> 
Can anyone please share Neon's g1m/g1t?
g1m
Neon - a2849b6b
Sophia - 34bd3a3e

No idea where their textures are.
## Post #426
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-03-28T03:23:36+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Thanks for your awesome plugin and great effort!   
But I came across a problem that I cannot figure out what caused it:



The noraml for the "driver" parts are comletely a mess. Is there any way to fix this?
Thanks in advance!!
## Post #427
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-03-28T06:13:01+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Joschka  I keep  getting this  Traceback (most recent call last):
  File "C:\Users\User\Pictures\fin\New folder\New folder\plugins\python\fmt_g1m.py", line 2549, in LoadModel
    nunoMap = clothMap[ID2s[currentMesh]]
IndexError: list index out of range with Sophie 2
## Post #428
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-03-28T13:55:53+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I just released a small update to get models from Samurai Warriors 2 working (thanks to einherjar007 for the report). I also added a Noesis version check, this way people will be prompted to update if their version is too old instead of getting crashes. Now to answer a few questions :

> Reply from consume ↑Mon Mar 28, 2022 9:50 am at Mon Mar 28, 2022 9:50 am
>
> 
g1m
Neon - a2849b6b
Sophia - 34bd3a3e
No idea where their textures are.


 FFThingy.zip
(6.56 KiB) Downloaded 99 times



Usage : Given a g1m hash (left column), get the ktid hash (right column). After that just use Nyotengu.KTID to reconstruct the g1t.
Ex : Given 1c31305b.g1m, I get b77f6980 from the list so 
```
Nyotengu.KTID.exe GameDump\KIDSSystemResource\kidsobjdb\CharacterEditor.kidssingletondb GameDump\MaterialEditor\g1t GameDump\CharacterEditor\ktid\b77f6980.ktid
```

The reconstructed g1t will have the same name as the ktid and will be located next to it. Then just create a folder, place the g1t and the g1m there, make sure that the "merge all" option is enabled and load the g1m to auto apply the textures.
Another way is to just set the "select g1t" option and you'll get prompted to choose a g1t file when you load a g1m file. It may be the best solution to avoid forgetting to untick "merge all" and load every single g1m at the same time from CharacterEditor/g1m, which you definitely don't want to.

If you want to also merge different g1m files at the same time, name them accordingly so that the g1t and g1m are in the good order. For example 0.g1m, 1.g1m for a head + body and 0.g1t, 1.g1t for their associated textures. Another way would be to just rename the g1t to the same hash of the g1m. 

> Reply from Kanbara ↑Mon Mar 28, 2022 11:23 am at Mon Mar 28, 2022 11:23 am
>
> 
Thanks for your awesome plugin and great effort!   
But I came across a problem that I cannot figure out what caused it:
The noraml for the "driver" parts are comletely a mess. Is there any way to fix this?
Thanks in advance!!

Yeah unfortunately this happened with other games too, what happens is that since those physics meshes' vertices linked to the NUNO sections get moved around and transformed a lot, normals would in theory need similar computation. So far I just let Noesis auto generate them, which gave good enough normals most of the time but not always (the first boss' cape is another example where it gives unpleasant results). 
I'd have to go back to shader decomp and see what they do with these eventually to get normals correctly working but I just got hardware issues that I need to solve and I'm also not sure if I have enough motivation for now to look into this. So yeah I'd recommend regenerating normals yourself for these until I finally look into this, which may happen when Fire Emblem Three Hopes will release.

> Reply from blacknight411 ↑Mon Mar 28, 2022 2:13 pm at Mon Mar 28, 2022 2:13 pm
>
> 
Joschka  I keep  getting this  Traceback (most recent call last):
  File "C:\Users\User\Pictures\fin\New folder\New folder\plugins\python\fmt_g1m.py", line 2549, in LoadModel
    nunoMap = clothMap[ID2s[currentMesh]]
IndexError: list index out of range with Sophie 2

fmt_g1m is deprecated,delete it and use project G1M.
## Post #429
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-03-28T16:01:11+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Mon Mar 28, 2022 9:55 pm at Mon Mar 28, 2022 9:55 pm
>
> Yeah unfortunately this happened with other games too, what happens is that since those physics meshes' vertices linked to the NUNO sections get moved around and transformed a lot, normals would in theory need similar computation. So far I just let Noesis auto generate them, which gave good enough normals most of the time but not always (the first boss' cape is another example where it gives unpleasant results). 
I'd have to go back to shader decomp and see what they do with these eventually to get normals correctly working but I just got hardware issues that I need to solve and I'm also not sure if I have enough motivation for now to look into this. So yeah I'd recommend regenerating normals yourself for these until I finally look into this, which may happen when Fire Emblem Three Hopes will release.

Thanks for your reply! And also appreciate that list for assembling g1m with g1t!!
## Post #430
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-03-29T00:22:41+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

A another question  Joschuka do I need  this  to  Source code (tar.gz) or  just  the projectG1M.zip
## Post #431
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-03-29T20:54:59+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from blacknight411 ↑Tue Mar 29, 2022 8:22 am at Tue Mar 29, 2022 8:22 am
>
> 
A another question  Joschuka do I need  this  to  Source code (tar.gz) or  just  the projectG1M.zip

You just need projectG1M.zip, the source code is for developpers. Extract it and put the content from the "plugins" folder in the Noesis' plugins folder.
## Post #432
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-03-30T07:30:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Ok I got it open Joschka  but  there  no bone  and textures for the model.
## Post #433
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-03-30T11:04:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Atelier games have split assets. 
Tools -> Display plugin tools
Tools -> projectG1M-> merge all assets in same folder
Then load again
## Post #434
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-03-31T06:38:27+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Went I  merge all assets in same folder the model was mess up and I keep on going getting this Reading 'C:\Users\User\Pictures\atlier\newgust_tools-master\pc00a_model\\driver_10_mat'...Failed. and  lot of bone are not attached I try to send you a picture  but it takes only 256 KiB.
and thank you for asking  me back.
## Post #435
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-03-31T11:46:58+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from blacknight411 ↑Thu Mar 31, 2022 2:38 pm at Thu Mar 31, 2022 2:38 pm
>
> 
Went I  merge all assets in same folder the model was mess up
If you just opened an asset you just extracted it shouldn't be, all the samples from Sophie 2 I tried worked.

> Reply from blacknight411 ↑Thu Mar 31, 2022 2:38 pm at Thu Mar 31, 2022 2:38 pm
>
> 
I keep on going getting this Reading 'C:\Users\User\Pictures\atlier\newgust_tools-master\pc00a_model\\driver_10_mat'...Failed.
Ignore these warnings

> Reply from blacknight411 ↑Thu Mar 31, 2022 2:38 pm at Thu Mar 31, 2022 2:38 pm
>
> 
and lot of bone are not attached

NUNO physics nodes are not true bones, I just represent them as is so users can do whatever they want with them.
## Post #436
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-03-31T23:42:40+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Ok here a picture shot of the problem the skirt and sleeve by her face.[https://sta.sh/229fvg7ut9ap?edit=1](https://sta.sh/229fvg7ut9ap?edit=1)
## Post #437
- Username: RoockyGTA
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Oct 16, 2021 1:00 pm
- Post datetime: 2022-04-01T05:30:53+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sun Mar 27, 2022 1:46 am at Sun Mar 27, 2022 1:46 am
>
> 
RoockyGTA wrote: ↑Fri Mar 25, 2022 2:05 pm
hello friend look so as not to bother you since that is not my intention I will explain it here I could see the animation in an autodesk program it is a file viewer but in the 3ds max program neither the character appears nor much less the animation and that I'm importing the FBX file fine so tell me what can I do? or what am I doing wrong? or what do I need to do? I want to edit the animation help me please


I'm not a 3ds max user so no idea sorry. If you were able to export the fbx from Noesis then the plugin is working as expected. I can't really help more than that, you should ask on 3ds max forums or maybe try another format.

I understand but you don't use any 3D program such as Blender to import characters and verify that your scripts work or something like that?
## Post #438
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-04-01T07:09:33+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sun Mar 27, 2022 2:42 am at Sun Mar 27, 2022 2:42 am
>
> 

Would it be convenient for you to tell me that which package contains character's animations? I have been searching round and round and still have no clue of it.   Maybe I should ask this question on the Cethleann post if here is not the right place to ask...

-------------------

Edited: Never mind! I find them in a package called "EventMaker3.rdb" file！
## Post #439
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-04-05T12:24:47+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from blacknight411 ↑Fri Apr 01, 2022 7:42 am at Fri Apr 01, 2022 7:42 am
>
> 
Ok here a picture shot of the problem the skirt and sleeve by her face.https://sta.sh/229fvg7ut9ap?edit=1

Not sure how you got this, even with the basic autorig this model looks good enough, the software you use probably did something wrong.


> Reply from RoockyGTA ↑Fri Apr 01, 2022 1:30 pm at Fri Apr 01, 2022 1:30 pm
>
> 
I understand but you don't use any 3D program such as Blender to import characters and verify that your scripts work or something like that?

I do sometimes (although I'm mostly interested in checking anims so usually the Noesis preview is enough for me) and it works fine, as long as you manage to export to fbx you can import it where you want. It's probably a problem with your 3dsmax version or something like that and I can't help more since I'm not familiar with 3dsMax.

> Reply from Kanbara ↑Fri Apr 01, 2022 3:09 pm at Fri Apr 01, 2022 3:09 pm
>
> 
Edited: Never mind! I find them in a package called "EventMaker3.rdb" file！

Usually most character anims are found in RRPreview, at least the ones related to gameplay.I actually never checked the ones in EventMaker3, I assume they are the ingame cutscenes related ones or something ? I'll take a look out of curiosity when I'll get back to Koei research.
## Post #440
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-04-06T11:40:12+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I think I found out the problems g1a is working but the  mesh are not moving with the bone. how to fix this.
## Post #441
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-04-11T10:53:40+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I extracted the model animation texture of Dynasty Warriors 8 using Steven's Gas Machine tool, but there are some errors when using the G1M script,
Both the old py script and the latest dll have been tested, and the whole series of "dynasty warriors 8 empires" "DYNASTY WARRIORS 8: Xtreme Legends" of this game have this problem,





I will upload some model texture animation samples

[https://drive.google.com/file/d/1odQhcj ... sp=sharing](https://drive.google.com/file/d/1odQhcjuL1qpSZPRfVEqGToYe6JLfkdbb/view?usp=sharing)
## Post #442
- Username: leckock
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 04, 2020 11:48 pm
- Post datetime: 2022-05-03T23:16:54+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hello, how i supposed to recompil animation from stranger of paradise, i assume i have to use Nyotengu.AnimationGraph but i don't understand how it's supposed to work.
## Post #443
- Username: Gnomoed
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Mar 05, 2022 10:47 pm
- Post datetime: 2022-05-11T04:37:07+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Exporting to FBX does not work with Atelier Nelke files. I get infinite "constructing meshes" that never ends and never exports a file. If I check "Merge all assets in the same folder" in G1M tools settings, Noesis manages to export an FBX with armature but no weight paint. 
Sample files - [https://mega.nz/folder/XrgXkJjQ#sn0-f1RTR8unctBLFPUjJg](https://mega.nz/folder/XrgXkJjQ#sn0-f1RTR8unctBLFPUjJg)

I used gust tools to get those files out of the .pak - [https://github.com/VitaSmith/gust_tools](https://github.com/VitaSmith/gust_tools)
## Post #444
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-05-11T10:41:05+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Gnomoed ↑Wed May 11, 2022 12:37 pm at Wed May 11, 2022 12:37 pm
>
> 
Exporting to FBX does not work with Atelier Nelke files. I get infinite "constructing meshes" that never ends and never exports a file. If I check "Merge all assets in the same folder" in G1M tools settings, Noesis manages to export an FBX with armature but no weight paint. 
Sample files - https://mega.nz/folder/XrgXkJjQ#sn0-f1RTR8unctBLFPUjJg

I used gust tools to get those files out of the .pak - https://github.com/VitaSmith/gust_tools

try download the newest version of Noesis from official site
## Post #445
- Username: Gnomoed
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Mar 05, 2022 10:47 pm
- Post datetime: 2022-05-11T12:36:55+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from wansf ↑Wed May 11, 2022 6:41 pm at Wed May 11, 2022 6:41 pm
>
> 
Gnomoed wrote: ↑Wed May 11, 2022 12:37 pm
Exporting to FBX does not work with Atelier Nelke files. I get infinite "constructing meshes" that never ends and never exports a file. If I check "Merge all assets in the same folder" in G1M tools settings, Noesis manages to export an FBX with armature but no weight paint. 
Sample files - https://mega.nz/folder/XrgXkJjQ#sn0-f1RTR8unctBLFPUjJg

I used gust tools to get those files out of the .pak - https://github.com/VitaSmith/gust_tools


try download the newest version of Noesis from official site

Of course I am using the latest one.
Also, when I export to gltf or collada I get the weight paint groups exported, though most of them are empty and armature is only partially exported.
Does it work fine for you on the latest version of Noesis or am I the only one having this issue?
This is very odd because Noesis exported FBX just fine before, from other games.
## Post #446
- Username: dark9090
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 09, 2021 4:55 pm
- Post datetime: 2022-05-12T00:05:23+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Using any model, I have extracted all the textures from the charactereditor folder in png format, the model in fbx, and I wanted to know if the plugin would open any way to correctly detect its textures when loading the model, or do I have to search manually? stranger of paradise, I've been ordering textures all day
## Post #447
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-05-14T07:10:06+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Gnomoed ↑Wed May 11, 2022 8:36 pm at Wed May 11, 2022 8:36 pm
>
> 

Of course I am using the latest one.
Also, when I export to gltf or collada I get the weight paint groups exported, though most of them are empty and armature is only partially exported.
Does it work fine for you on the latest version of Noesis or am I the only one having this issue?
This is very odd because Noesis exported FBX just fine before, from other games.

yea i dun hv any issue with this great tool
maybe try export from preview?
if this also not work , make a new clean noesis folder that only contain this tool
## Post #448
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-05-17T15:18:08+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Version 1.7.3 is now available

I was finally tired of seeing awful normal coordinates for cloth meshes so I went through the shader bytecode again to fix these once and for all. The NUN meshes should now have accurate normal and tangents.

Before :

Now :


Even when the auto generation worked good enough you could notice some problems at the edges :


Now :
## Post #449
- Username: Gnomoed
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Mar 05, 2022 10:47 pm
- Post datetime: 2022-05-24T13:04:26+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from wansf ↑Sat May 14, 2022 3:10 pm at Sat May 14, 2022 3:10 pm
>
> 
yea i dun hv any issue with this great tool
maybe try export from preview?
if this also not work , make a new clean noesis folder that only contain this tool

Thanks to your suggestion I was able to extract a model with weight paint and armature intact using "Export from preview" option. Very weird that normal "export" don't work as intended.
## Post #450
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-06-09T13:16:56+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Fire Emblem Warriors Three Hopes works with it!

Image is taken by Joschka and the files in this image were extracted with his own script, for right now, wait for Cethleann to fully support with files from Fire Emblem Warriors Three Hopes.
## Post #451
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-10T09:07:49+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I can indeed confirm that Three Hopes is fully supported. No NUNO5 used, chunk versions and "classic" texture formats really close to what was used in Three Houses so no problems at all. Cethleann has been updated to extract the assets properly so now everyone can dump them easily. 

However after 2 years and a half maintaining Cethleann, Yretenai has decided to take a break from working on all these Koei archives and won't make any more updates for a while to focus on other projects.
## Post #452
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-06-10T15:59:12+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Jun 10, 2022 5:07 pm at Fri Jun 10, 2022 5:07 pm
>
> 
I can indeed confirm that Three Hopes is fully supported. No NUNO5 used, chunk versions and "classic" texture formats really close to what was used in Three Houses so no problems at all. Cethleann has been updated to extract the assets properly so now everyone can dump them easily. 

However after 2 years and a half maintaining Cethleann, Yretenai has decided to take a break from working on all these Koei archives and won't make any more updates for a while to focus on other projects.

So I tried loading the same file (85ce161d.g1m) as you did only to get a crash, please tell me how did you load this up without crashing?
## Post #453
- Username: Diblox
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 11, 2022 12:39 am
- Post datetime: 2022-06-10T17:14:00+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from andree ↑Fri Jun 10, 2022 11:59 pm at Fri Jun 10, 2022 11:59 pm
>
> 
Joschka wrote: ↑Fri Jun 10, 2022 5:07 pm
I can indeed confirm that Three Hopes is fully supported. No NUNO5 used, chunk versions and "classic" texture formats really close to what was used in Three Houses so no problems at all. Cethleann has been updated to extract the assets properly so now everyone can dump them easily. 

However after 2 years and a half maintaining Cethleann, Yretenai has decided to take a break from working on all these Koei archives and won't make any more updates for a while to focus on other projects.


So I tried loading the same file (85ce161d.g1m) as you did only to get a crash, please tell me how did you load this up without crashing?

I have the same problem. Did you figured it out?
## Post #454
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-10T21:22:08+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Do NOT use Ceth 1.2.1, it's specific to P5S PC version and will corrupt your file by trying to decrypt them whereas this game has no encryption in any way. 
Use Ceth 1.2.0 instead if you want to get Three Hopes assets, or literally any RDB game that is not Strikers Steam version

Anyways here's the usual list to rebuild the g1t files given a g1m hash, command line at the top :


 MaterialList.zip
(21.66 KiB) Downloaded 109 times
## Post #455
- Username: Diblox
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 11, 2022 12:39 am
- Post datetime: 2022-06-13T15:12:22+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Jun 11, 2022 5:22 am at Sat Jun 11, 2022 5:22 am
>
> 
Do NOT use Ceth 1.2.1, it's specific to P5S PC version and will corrupt your file by trying to decrypt them whereas this game has no encryption in any way. 
Use Ceth 1.2.0 instead if you want to get Three Hopes assets, or literally any RDB game that is not Strikers Steam version

Anyways here's the usual list to rebuild the g1t files given a g1m hash, command line at the top :
MaterialList.zip

Hello! Thank you for the MaterialList, it has been a really big help. But I've noticed that some characters g1m hashs are not present in the list. Is this normal?
## Post #456
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-06-13T19:53:07+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Diblox ↑Mon Jun 13, 2022 11:12 pm at Mon Jun 13, 2022 11:12 pm
>
> 
Hello! Thank you for the MaterialList, it has been a really big help. But I've noticed that some characters g1m hashs are not present in the list. Is this normal?

Considering the weird new schemes that they introduced in this game I wouldn't be surprised if there were some shared resources or similar (this is what happens with anims). Can you give me an example of such hashes so I can check what's going on ?
## Post #457
- Username: Diblox
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 11, 2022 12:39 am
- Post datetime: 2022-06-14T13:29:30+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Tue Jun 14, 2022 3:53 am at Tue Jun 14, 2022 3:53 am
>
> 
Diblox wrote: ↑Mon Jun 13, 2022 11:12 pm
Hello! Thank you for the MaterialList, it has been a really big help. But I've noticed that some characters g1m hashs are not present in the list. Is this normal?


Considering the weird new schemes that they introduced in this game I wouldn't be surprised if there were some shared resources or similar (this is what happens with anims). Can you give me an example of such hashes so I can check what's going on ?

Sorry, it was on me. It seems my text editor didn't load the full list for some reason reason when I searched for the hashes. I didn't have any problems since but if I do and the hashes are really not there I will post again on this thread.

Sorry again and thanks!
## Post #458
- Username: Tangil
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2020 5:06 pm
- Post datetime: 2022-06-25T00:21:33+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Jun 11, 2022 5:22 am at Sat Jun 11, 2022 5:22 am
>
> 
Do NOT use Ceth 1.2.1, it's specific to P5S PC version and will corrupt your file by trying to decrypt them whereas this game has no encryption in any way. 
Use Ceth 1.2.0 instead if you want to get Three Hopes assets, or literally any RDB game that is not Strikers Steam version

Anyways here's the usual list to rebuild the g1t files given a g1m hash, command line at the top :
MaterialList.zip

Is there a command to rebuild these g1t files in bulk? It's pretty tedious to rebuild the g1t files individually.

Also, is there a filelist of the file names for Three Hopes that I cross-reference with the hash names? It would be much appreciated if we didn't had to go through every g1m file to find a specific model(s)
## Post #459
- Username: Twn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 11, 2022 2:09 am
- Post datetime: 2022-07-10T21:57:15+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Jun 10, 2022 5:07 pm at Fri Jun 10, 2022 5:07 pm
>
> 
I can indeed confirm that Three Hopes is fully supported. No NUNO5 used, chunk versions and "classic" texture formats really close to what was used in Three Houses so no problems at all. Cethleann has been updated to extract the assets properly so now everyone can dump them easily. 

However after 2 years and a half maintaining Cethleann, Yretenai has decided to take a break from working on all these Koei archives and won't make any more updates for a while to focus on other projects.

Hey, I was able to get the merged models and textures of a character from FEW3H, but I have no idea how you managed to get the animations working. Things I tried was putting all the g1a of the game in the model folder, it didn't load anything (Maybe it's not supposed to in that specific case), and I also tried to use Nyotengu.AnimationGraph.exe to somehow find the compatible g1a but no success. Is there some trick to find the compatible g1a for a character like the g1t?
## Post #460
- Username: threadbareplover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 30, 2022 11:38 pm
- Post datetime: 2022-07-13T10:16:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Jun 11, 2022 5:22 am at Sat Jun 11, 2022 5:22 am
>
> 
Do NOT use Ceth 1.2.1, it's specific to P5S PC version and will corrupt your file by trying to decrypt them whereas this game has no encryption in any way. 
Use Ceth 1.2.0 instead if you want to get Three Hopes assets, or literally any RDB game that is not Strikers Steam version

Anyways here's the usual list to rebuild the g1t files given a g1m hash, command line at the top :
MaterialList.zip

Hi, I'm having trouble finding some g1m hashes in this list. I've tried using a few different text editors to open the MaterialList, but none have found the missing models. Is there a particular one you would reccommend?

Here are some of the missing hashes:
ed339933
29629ff7 
b5236798
57434dcb
d37edda3

All of the Ashen Wolves are missing, along with the Asura models, maybe that means something. The rest of the characters seem to be there, including new ones like Monica and Holst.
## Post #461
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2022-07-15T09:56:40+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from threadbareplover ↑Wed Jul 13, 2022 6:16 pm at Wed Jul 13, 2022 6:16 pm
>
> 
Joschka wrote: ↑Sat Jun 11, 2022 5:22 am
Do NOT use Ceth 1.2.1, it's specific to P5S PC version and will corrupt your file by trying to decrypt them whereas this game has no encryption in any way. 
Use Ceth 1.2.0 instead if you want to get Three Hopes assets, or literally any RDB game that is not Strikers Steam version

Anyways here's the usual list to rebuild the g1t files given a g1m hash, command line at the top :
MaterialList.zip


Hi, I'm having trouble finding some g1m hashes in this list. I've tried using a few different text editors to open the MaterialList, but none have found the missing models. Is there a particular one you would reccommend?

Here are some of the missing hashes:
ed339933
29629ff7 
b5236798
57434dcb
d37edda3

All of the Ashen Wolves are missing, along with the Asura models, maybe that means something. The rest of the characters seem to be there, including new ones like Monica and Holst.

It's because the list was made on the demo. We would need a new one for the final game.
## Post #462
- Username: threadbareplover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 30, 2022 11:38 pm
- Post datetime: 2022-07-15T18:11:12+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Petrgold ↑Fri Jul 15, 2022 5:56 pm at Fri Jul 15, 2022 5:56 pm
>
> 
threadbareplover wrote: ↑Wed Jul 13, 2022 6:16 pm
Joschka wrote: ↑Sat Jun 11, 2022 5:22 am
Do NOT use Ceth 1.2.1, it's specific to P5S PC version and will corrupt your file by trying to decrypt them whereas this game has no encryption in any way. 
Use Ceth 1.2.0 instead if you want to get Three Hopes assets, or literally any RDB game that is not Strikers Steam version

Anyways here's the usual list to rebuild the g1t files given a g1m hash, command line at the top :
MaterialList.zip


Hi, I'm having trouble finding some g1m hashes in this list. I've tried using a few different text editors to open the MaterialList, but none have found the missing models. Is there a particular one you would reccommend?

Here are some of the missing hashes:
ed339933
29629ff7 
b5236798
57434dcb
d37edda3

All of the Ashen Wolves are missing, along with the Asura models, maybe that means something. The rest of the characters seem to be there, including new ones like Monica and Holst.


It's because the list was made on the demo. We would need a new one for the final game.

Ah, ok, that makes a lot of sense. Thanks for pointing that out! Is there a way to generate a list for the full game?
## Post #463
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2022-07-16T08:24:15+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from threadbareplover ↑Sat Jul 16, 2022 2:11 am at Sat Jul 16, 2022 2:11 am
>
> 
Ah, ok, that makes a lot of sense. Thanks for pointing that out! Is there a way to generate a list for the full game?

There is probably a way but I don't know how it's done sorry.
## Post #464
- Username: JunHimekawa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 06, 2020 1:16 pm
- Post datetime: 2022-07-16T19:14:07+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

How do I even get the g1m files for Stranger of Paradise? I don't see any of them in the PC files.
## Post #465
- Username: EricVito
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 11, 2022 4:37 pm
- Post datetime: 2022-07-21T17:26:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Allanoon ↑Fri Mar 18, 2022 11:32 pm at Fri Mar 18, 2022 11:32 pm
>
> 
Stranger of Paradise Final Fantasy Origin just recently came out. Cethleann Seems to extract the files just fine, ofc, nameless.
G1M files are mildly supported, some crash, some are deformed looking, other seems fine (mainly equipments?).
I didn't check much animations, but they load and there was no crash so far.
Textures also seems to work.

I'll drop a link with some working/not working g1m for if and when Joschka will have time. Thanks~
https://www.mediafire.com/file/ikpc6k0u ... in.7z/file
How did you do it? I don't know how to open it .bin or .file？
## Post #466
- Username: EricVito
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 11, 2022 4:37 pm
- Post datetime: 2022-07-21T17:27:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Sreliata ↑Mon Mar 21, 2022 10:25 am at Mon Mar 21, 2022 10:25 am
>
> 
Joschka wrote: ↑Mon Mar 21, 2022 1:41 am
Just to post a small update ... 

Thank you so much for your hard work.
I've spent the my whole day on going through the "Stranger of Paradise" files and can confirm that currently, only the assets that don't really need /use physics, work. Such as Neon (short grey haired girl), most of the men and monsters. I just wanted to say that I really appreciate what you're doing and I am so excited for the updated version. So, so excited.

Again: thank you very much for doing this.
How did you do it? I don't know how to open it .bin or .file？
## Post #467
- Username: leckock
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 04, 2020 11:48 pm
- Post datetime: 2022-07-21T22:06:37+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

hello, i search for help for stranger of paradise, i recently try to recompile animation with Nyotengu.AnimationGraph, i have CE1CommonResource.motor.kidsobjdb, i have CE1CommonResource.motor.kidssingletondb, but it dosen't work, i maybe miss somthing, if someone could help me for this mystery. i apologies for my lack of knowledge   
Thanks in advance.
## Post #468
- Username: Tahugamer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 26, 2018 3:46 pm
- Post datetime: 2022-08-04T01:55:02+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

For Fire emblem warriors three hopes some g1m's don't have working g1t's like the wolves or asura. I understand this is because the material list is from the demo not the fully game? I am wondering how or if anyone knows how to get those last remaining g1t's?
## Post #469
- Username: threadbareplover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 30, 2022 11:38 pm
- Post datetime: 2022-08-04T12:54:32+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Tahugamer ↑Thu Aug 04, 2022 9:55 am at Thu Aug 04, 2022 9:55 am
>
> 
For Fire emblem warriors three hopes some g1m's don't have working g1t's like the wolves or asura. I understand this is because the material list is from the demo not the fully game? I am wondering how or if anyone knows how to get those last remaining g1t's?

I've found a way, far from ideal but it works.

First, open CharacterEditor.kidssingletondb (in root/kidsobjdb) using Cethleann's NyotenguDatabase. You can use command prompt (if on Windows) to write the result to a .txt file, like so:
*path to NyotenguDatabase.exe* *path to CharacterEditor.kidssingletondb* > *desired output path.txt*
You can drag and drop the first two into command prompt, probably the quickest way. If you've done this right, you'll end up with a .txt file (I would upload this here, but it's too big.)

Now that you've got this file, open it in a text editor like wordpad and search it using Ctrl+F for the hash of the model you need textures for. It should appear as part of a list. From the same list, grab the hash under 'TexturesRenderStateObjectHash' and search for this instead.
This should take you to another list. The value under 'TextureBindTableCSVFileResourceHash' is the ktid hash you need, use it with Nyotengu.KTID.exe as usual and you should get the g1t file you want.

I've been able to get textures for the ashen wolves and asura models with this, but I don't know for sure if it works with all models.
## Post #470
- Username: CarpetStain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 27, 2022 8:11 pm
- Post datetime: 2022-09-10T18:23:01+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

has anyone extracted the dragon quest heroes 2 animations or have them at all? i've been trying to get them for a while and i can't seem to find them or get them viewable
## Post #471
- Username: ndsno1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 23, 2021 9:26 pm
- Post datetime: 2022-10-09T15:42:23+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I am encountering problem with wrong animation reading on Atelier Shallie DX on PC. The new one (dll) seems to confuses the orientation of the bone. The old one (python) works fine.

The old one: Proper animation, bone, model, texture

The new one:
Original Bone:

After importing animation:
## Post #472
- Username: XxMichiFreddy35xX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 23, 2016 1:35 am
- Post datetime: 2022-10-31T20:59:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from einherjar007 ↑Sat Feb 29, 2020 6:00 pm at Sat Feb 29, 2020 6:00 pm
>
> 
Fist of The North Star 2's use zlib compression.
you need use offzip

offzip -a -1 *.bin

Then, split G1M,G1T and G1A(G2A) as needed.

how is that gonna work?
## Post #473
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-11-09T14:15:08+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I am trying to get Touken Ranbu Warriors models, models and textures were extracted via Cethleann that only gave hash names ( maybe I missed something?).

Model and textures load fine with the plugin, however I really dunno how to search for proper textures... is there a way or I need to find them manually?
## Post #474
- Username: Stradydou
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 11, 2020 6:21 pm
- Post datetime: 2022-12-02T16:43:53+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi,

How can I export facial animation from fairy tail game ?

Character animation work fin but I can't do the same with facial animation
## Post #475
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2023-02-17T14:38:51+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

'Am dropping some samples from the new game WildHeart.
The game seems to extract fine but the importer crash when trying to load g1m/g1t files.

[https://www.mediafire.com/file/qmo14huy ... rt.7z/file](https://www.mediafire.com/file/qmo14huyw1f193x/SamplesWildHeart.7z/file)
## Post #476
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-02-17T15:06:26+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Allanoon ↑Fri Feb 17, 2023 10:38 pm at Fri Feb 17, 2023 10:38 pm
>
> 
'Am dropping some samples from the new game WildHeart.
The game seems to extract fine but the importer crash when trying to load g1m/g1t files.

https://www.mediafire.com/file/qmo14huy ... rt.7z/file

Hmm all your samples are invalid (basically a bunch of bytes without any meaning, no correct G1M, G1A or G1T magic) so I'm guessing something wrong happened during the extraction. I don't have the game however so I cannot check it out myself but I suggest trying with the "RDX support" Cethleann version, not the "Scramble fix" one, there was the same issue with FE Three Hopes
I should probably put a proper check in the C++ plugin to throw a warning when this happens.
## Post #477
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2023-02-17T19:35:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Feb 17, 2023 11:06 pm at Fri Feb 17, 2023 11:06 pm
>
> 
Allanoon wrote: ↑Fri Feb 17, 2023 10:38 pm
'Am dropping some samples from the new game WildHeart.
The game seems to extract fine but the importer crash when trying to load g1m/g1t files.

https://www.mediafire.com/file/qmo14huy ... rt.7z/file


Hmm all your samples are invalid (basically a bunch of bytes without any meaning, no correct G1M, G1A or G1T magic) so I'm guessing something wrong happened during the extraction. I don't have the game however so I cannot check it out myself but I suggest trying with the "RDX support" Cethleann version, not the "Scramble fix" one, there was the same issue with FE Three Hopes
I should probably put a proper check in the C++ plugin to throw a warning when this happens.

Thanks for the hint Joschka, 'am extracting with the RDX version now, altough... Noesis still crash. Upped a a few more files with this new extraction.

[https://www.mediafire.com/file/q6d02nxp ... e2.7z/file](https://www.mediafire.com/file/q6d02nxp6m9uruh/Sample2.7z/file)
## Post #478
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-02-17T21:08:49+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Allanoon ↑Sat Feb 18, 2023 3:35 am at Sat Feb 18, 2023 3:35 am
>
> 
Joschka wrote: ↑Fri Feb 17, 2023 11:06 pm
Allanoon wrote: ↑Fri Feb 17, 2023 10:38 pm
'Am dropping some samples from the new game WildHeart.
The game seems to extract fine but the importer crash when trying to load g1m/g1t files.

https://www.mediafire.com/file/qmo14huy ... rt.7z/file


Hmm all your samples are invalid (basically a bunch of bytes without any meaning, no correct G1M, G1A or G1T magic) so I'm guessing something wrong happened during the extraction. I don't have the game however so I cannot check it out myself but I suggest trying with the "RDX support" Cethleann version, not the "Scramble fix" one, there was the same issue with FE Three Hopes
I should probably put a proper check in the C++ plugin to throw a warning when this happens.


Thanks for the hint Joschka, 'am extracting with the RDX version now, altough... Noesis still crash. Upped a a few more files with this new extraction.

https://www.mediafire.com/file/q6d02nxp ... e2.7z/file

Yeah those are still extracted incorrectly unfortunately, I wonder if they changed something or encrypted them. Can you DM me some archives please so I could take a look?
## Post #479
- Username: xieronis
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jun 20, 2021 11:43 pm
- Post datetime: 2023-02-22T02:07:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Sat Feb 18, 2023 5:08 am at Sat Feb 18, 2023 5:08 am
>
> 
Allanoon wrote: ↑Sat Feb 18, 2023 3:35 am
Joschka wrote: ↑Fri Feb 17, 2023 11:06 pm


Hmm all your samples are invalid (basically a bunch of bytes without any meaning, no correct G1M, G1A or G1T magic) so I'm guessing something wrong happened during the extraction. I don't have the game however so I cannot check it out myself but I suggest trying with the "RDX support" Cethleann version, not the "Scramble fix" one, there was the same issue with FE Three Hopes
I should probably put a proper check in the C++ plugin to throw a warning when this happens.


Thanks for the hint Joschka, 'am extracting with the RDX version now, altough... Noesis still crash. Upped a a few more files with this new extraction.

https://www.mediafire.com/file/q6d02nxp ... e2.7z/file


Yeah those are still extracted incorrectly unfortunately, I wonder if they changed something or encrypted them. Can you DM me some archives please so I could take a look?

If they haven't responded, I could provide. I'm having issues too, if you could provide how you get them to work (if you do) that would be greatly appreciated!
## Post #480
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-02-22T11:12:38+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from xieronis ↑Wed Feb 22, 2023 10:07 am at Wed Feb 22, 2023 10:07 am
>
> 
Joschka wrote: ↑Sat Feb 18, 2023 5:08 am
Allanoon wrote: ↑Sat Feb 18, 2023 3:35 am


Thanks for the hint Joschka, 'am extracting with the RDX version now, altough... Noesis still crash. Upped a a few more files with this new extraction.

https://www.mediafire.com/file/q6d02nxp ... e2.7z/file


Yeah those are still extracted incorrectly unfortunately, I wonder if they changed something or encrypted them. Can you DM me some archives please so I could take a look?


If they haven't responded, I could provide. I'm having issues too, if you could provide how you get them to work (if you do) that would be greatly appreciated!

Yeah Allanoon sent me a few archives and I made a quick and dirty quickbms script (they changed their archive layouts a bit so Ceth outputs corrupted files).
We're not 100% sure that it works correctly so he was going to do more tests before I'd release it but if you're willing to try it out too in the meantime and send crashing g1m files if you find any, here it is: 
EDIT: Script outdated and removed, see next posts
Usage is simply 

```
quickbms_4gb_files.exe fdata.bms inputFolderWithTheFdataFiles [optionalOutputFolder]
```
## Post #481
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2023-02-22T11:54:59+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Wed Feb 22, 2023 7:12 pm at Wed Feb 22, 2023 7:12 pm
>
> 

Yeah Allanoon sent me a few archives and I made a quick and dirty quickbms script (they changed their archive layouts a bit so Ceth outputs corrupted files).
We're not 100% sure that it works correctly so he was going to do more tests before I'd release it but if you're willing to try it out too in the meantime and send crashing g1m files if you find any, here it is: 
fdata.zip
Usage is simply 
Code: Select allquickbms_4gb_files.exe fdata.bms inputFolderWithTheFdataFiles [optionalOutputFolder]

I'll suggest to remove the 1kb files as quite a few of them will make quickbms extraction process stop; Also do that with .rdb .rdx and .lang files.
It's better to extract just an handfull of files (like 1000-2000 together) as if the process hang there's the risk you won't extract everything OR you'll have to extract them again just to be sure.
## Post #482
- Username: xieronis
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jun 20, 2021 11:43 pm
- Post datetime: 2023-02-22T17:42:25+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Allanoon ↑Wed Feb 22, 2023 7:54 pm at Wed Feb 22, 2023 7:54 pm
>
> 
Joschka wrote: ↑Wed Feb 22, 2023 7:12 pm

Yeah Allanoon sent me a few archives and I made a quick and dirty quickbms script (they changed their archive layouts a bit so Ceth outputs corrupted files).
We're not 100% sure that it works correctly so he was going to do more tests before I'd release it but if you're willing to try it out too in the meantime and send crashing g1m files if you find any, here it is: 
fdata.zip
Usage is simply 
Code: Select allquickbms_4gb_files.exe fdata.bms inputFolderWithTheFdataFiles [optionalOutputFolder]


I'll suggest to remove the 1kb files as quite a few of them will make quickbms extraction process stop; Also do that with .rdb .rdx and .lang files.
It's better to extract just an handfull of files (like 1000-2000 together) as if the process hang there's the risk you won't extract everything OR you'll have to extract them again just to be sure.

Right now it's only wanting to extract 6 total files (even after deleting the 1kb files). The files come out with odd extensions (ex: .82945A44) It did extract 16 g1t files.

Edit: Apparently I had to just keep rerunning it.
## Post #483
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-02-24T14:04:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Update: I checked a few of these 1kb files and it looks like they're just empty so it makes the qbms script crash. Not sure what Koei is doing with these useless things, you can add a size check to prevent the script from crashing.

Also I took a look at some samples and some crash for two reasons:
-Some files have the g1m hash type in the archives but are in reality morph shape containers that they were using in Atelier games before. 
-NUNO5 update (their latest cloth/hair meshes util). I'll probably won't be as annoying to crack from scratch this time contrary to SoP (it's pretty much reserved fields that started to get used) but will still be very tedious and I don't have the necessary interest/motivation right now to go through this. 

So yeah don't expect an update very soon on my end.
## Post #484
- Username: benjamin77
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Apr 17, 2020 12:01 am
- Post datetime: 2023-03-06T07:57:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from threadbareplover ↑Thu Aug 04, 2022 8:54 pm at Thu Aug 04, 2022 8:54 pm
>
> 
Tahugamer wrote: ↑Thu Aug 04, 2022 9:55 am
For Fire emblem warriors three hopes some g1m's don't have working g1t's like the wolves or asura. I understand this is because the material list is from the demo not the fully game? I am wondering how or if anyone knows how to get those last remaining g1t's?


I've found a way, far from ideal but it works.

First, open CharacterEditor.kidssingletondb (in root/kidsobjdb) using Cethleann's NyotenguDatabase. You can use command prompt (if on Windows) to write the result to a .txt file, like so:
*path to NyotenguDatabase.exe* *path to CharacterEditor.kidssingletondb* > *desired output path.txt*
You can drag and drop the first two into command prompt, probably the quickest way. If you've done this right, you'll end up with a .txt file (I would upload this here, but it's too big.)

Now that you've got this file, open it in a text editor like wordpad and search it using Ctrl+F for the hash of the model you need textures for. It should appear as part of a list. From the same list, grab the hash under 'TexturesRenderStateObjectHash' and search for this instead.
This should take you to another list. The value under 'TextureBindTableCSVFileResourceHash' is the ktid hash you need, use it with Nyotengu.KTID.exe as usual and you should get the g1t file you want.

I've been able to get textures for the ashen wolves and asura models with this, but I don't know for sure if it works with all models.

I've parsed and rebuilt the correct g1t and outputted it in the same folder as ktid
But when I browse g1m in Noesis, I don't see the textrue display.
May I ask how to get the AoCThingy table so that g1m and g1t can correspond?

I refer to your method, but I don't get the hash value content of txt
May I ask where I did wrong?
[v2.png](https://xentaxbackup.github.io/file/23504_v2.png)
## Post #485
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2023-03-07T15:41:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Wed Feb 22, 2023 7:12 pm at Wed Feb 22, 2023 7:12 pm
>
> 
Yeah Allanoon sent me a few archives and I made a quick and dirty quickbms script (they changed their archive layouts a bit so Ceth outputs corrupted files).
Thanks, this script works like a charm.

Wo Long definitely seems to be a hard to crack. First, PS4 and PC version both have archives, and script works on both - this is a good news.
Bad news, is that PS4 version no longer have loose files with filenames, they probably all are in .rdb headers

Nioh2 tool by id-daemon works on models, and extract smd skeleton and ascii model. Meshes with new weights format are all borked
## Post #486
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-03-07T17:03:22+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from fullinu ↑Tue Mar 07, 2023 11:41 pm at Tue Mar 07, 2023 11:41 pm
>
> 
Joschka wrote: ↑Wed Feb 22, 2023 7:12 pm
Yeah Allanoon sent me a few archives and I made a quick and dirty quickbms script (they changed their archive layouts a bit so Ceth outputs corrupted files).
Thanks, this script works like a charm.

Wo Long definitely seems to be a hard to crack. First, PS4 and PC version both have archives, and script works on both - this is a good news.
Bad news, is that PS4 version no longer have loose files with filenames, they probably all are in .rdb headers

Nioh2 tool by id-daemon works on models, and extract smd skeleton and ascii model. Meshes with new weights format are all borked

Yeah that's expected, as Daemon's current util just outright skips the new NUNO5 chunks. So all the associated meshes (capes and other simulated parts) will render with their default positions, without the vertex shader transform applied to give them their correct shape.
Meanwhile Noesis crashes as KT updated the aforementioned chunks, since they're tightly packed it leads to a crash.

I got some samples from WH and grabbed WoLong's demo but I'm busy with other reverse engineering projects currently so not sure when I'll look into this.
## Post #487
- Username: benjamin77
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Apr 17, 2020 12:01 am
- Post datetime: 2023-03-08T04:31:18+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Wed Mar 08, 2023 1:03 am at Wed Mar 08, 2023 1:03 am
>
> 
fullinu wrote: ↑Tue Mar 07, 2023 11:41 pm
Joschka wrote: ↑Wed Feb 22, 2023 7:12 pm
Yeah Allanoon sent me a few archives and I made a quick and dirty quickbms script (they changed their archive layouts a bit so Ceth outputs corrupted files).
Thanks, this script works like a charm.

Wo Long definitely seems to be a hard to crack. First, PS4 and PC version both have archives, and script works on both - this is a good news.
Bad news, is that PS4 version no longer have loose files with filenames, they probably all are in .rdb headers

Nioh2 tool by id-daemon works on models, and extract smd skeleton and ascii model. Meshes with new weights format are all borked



Yeah that's expected, as Daemon's current util just outright skips the new NUNO5 chunks. So all the associated meshes (capes and other simulated parts) will render with their default positions, without the vertex shader transform applied to give them their correct shape.
Meanwhile Noesis crashes as KT updated the aforementioned chunks, since they're tightly packed it leads to a crash.

I got some samples from WH and grabbed WoLong's demo but I'm busy with other reverse engineering projects currently so not sure when I'll look into this.

Hello Joschka, I have successfully extracted in SAMURAI WARRIORS 5. And use Nyotengu.KTID.exe to successfully merge the g1t file into the ktid directory. But I open the model with g1m, still can't see the texture. I also used Nyotengu.Database.exe to analyze CharacterEditor.kidssingletondb to get a txt hash list, but I don't know how to match g1m and g1t, can you help me?

And there is no fmt_g1m.py file in my plugin folder? How to get this?
[v3.jpg](https://xentaxbackup.github.io/file/23518_v3.jpg)
## Post #488
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-03-08T13:34:38+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from benjamin77 ↑Wed Mar 08, 2023 12:31 pm at Wed Mar 08, 2023 12:31 pm
>
> 
Hello Joschka, I have successfully extracted in SAMURAI WARRIORS 5. And use Nyotengu.KTID.exe to successfully merge the g1t file into the ktid directory. But I open the model with g1m, still can't see the texture. I also used Nyotengu.Database.exe to analyze CharacterEditor.kidssingletondb to get a txt hash list, but I don't know how to match g1m and g1t, can you help me?

And there is no fmt_g1m.py file in my plugin folder? How to get this?

Hello,
After you generated the g1t file, put the g1t and the g1m in the same folder, then in Noesis go to Tools->Plugin Options->Project G1M and select "Merge All". After that simply load the g1m and the g1t next to it will be loaded automatically.

WoLong/Wild Hearts update: I started to look into these more seriously and got most of the samples loading. I'll do a few more tests/fixes later and will release a testing build here in the next days.
## Post #489
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-03-09T00:36:23+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Version 1.7.4 is now available
This update adds support for the new NUNO update that TN/OF have been using for their recent titles.



I also updated the quickbms script to properly discriminate between the g1m files and the g1h containers, you should do a new proper extraction to have everything set up accordingly. It will also ignore the useless little files.


 fdata.zip
(852 Bytes) Downloaded 240 times
## Post #490
- Username: csh0748
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 22, 2022 2:06 pm
- Post datetime: 2023-03-09T06:17:14+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Thu Mar 09, 2023 8:36 am at Thu Mar 09, 2023 8:36 am
>
> 
Version 1.7.4 is now available
This update adds support for the new NUNO update that TN/OF have been using for their recent titles.



I also updated the quickbms script to properly discriminate between the g1m files and the g1h containers, you should do a new proper extraction to have everything set up accordingly. It will also ignore the useless little files.
fdata.zip
Hello, thank you very much for your hard work on this tool. What I want to know now is that the g1m and g1t files obtained after using quickbms to unpack Wolong’s assets seem to be a bunch of random file names. How can I Know which file number corresponds to the corresponding model in the game? Or is there a way to unpack other assets to get a list file table for mapping the corresponding model in the game? Thank you again
## Post #491
- Username: benjamin77
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Apr 17, 2020 12:01 am
- Post datetime: 2023-03-09T06:21:44+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Wed Mar 08, 2023 9:34 pm at Wed Mar 08, 2023 9:34 pm
>
> 
benjamin77 wrote: ↑Wed Mar 08, 2023 12:31 pm
Hello,
After you generated the g1t file, put the g1t and the g1m in the same folder, then in Noesis go to Tools->Plugin Options->Project G1M and select "Merge All". After that simply load the g1m and the g1t next to it will be loaded automatically.


Thanks Joschka
## Post #492
- Username: iceS
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 04, 2022 8:23 pm
- Post datetime: 2023-03-09T12:04:27+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Thu Mar 09, 2023 8:36 am at Thu Mar 09, 2023 8:36 am
>
> 
Version 1.7.4 is now available
This update adds support for the new NUNO update that TN/OF have been using for their recent titles.



I also updated the quickbms script to properly discriminate between the g1m files and the g1h containers, you should do a new proper extraction to have everything set up accordingly. It will also ignore the useless little files.
fdata.zip

Script error while unpacking RRPreview.rdb

```
325519424
325519480
1397904193
  0000000000000000 4644528    srsa\0x58883b0c.srsa
328782896
328782952

Error: offset in GetVarChr (0x0000000000000000) is bigger than the var (0x00000000)

Last script line before the error or that produced the error:
  153 GetVarChr MAGIC MEMORY_FILE 0 long
  coverage file 0    21%   328711999  1523384985 . offset 000000001398d472
```
## Post #493
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-03-09T20:20:51+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from csh0748 ↑Thu Mar 09, 2023 2:17 pm at Thu Mar 09, 2023 2:17 pm
>
> 
Hello, thank you very much for your hard work on this tool. What I want to know now is that the g1m and g1t files obtained after using quickbms to unpack Wolong’s assets seem to be a bunch of random file names. How can I Know which file number corresponds to the corresponding model in the game? Or is there a way to unpack other assets to get a list file table for mapping the corresponding model in the game? Thank you again

Use these to make the g1t file associated to a given g1m. As for filenames they are stripped so you will only have the hashes.


 WHWOThingy.zip
(44.84 KiB) Downloaded 175 times



G1m hash on the left as usual, then

```
Nyotengu.KTID.exe ..\kidsobjdb\0xb290631c.kidsobjdb ..\g1t ..\ktid\valueOnRightColumn.ktid
```

Only the non field props are covered by these (ie characters, mobs, animatable models etc), I'm not dling several dozens of gigs to make exhaustive file lists for games I'm not personally interested in.

Many thanks to Allanoon for testing and reporting bugs for this update.
## Post #494
- Username: benjamin77
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Apr 17, 2020 12:01 am
- Post datetime: 2023-03-10T06:15:37+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Mar 10, 2023 4:20 am at Fri Mar 10, 2023 4:20 am
>
> 
csh0748 wrote: ↑Thu Mar 09, 2023 2:17 pm
Hello, thank you very much for your hard work on this tool. What I want to know now is that the g1m and g1t files obtained after using quickbms to unpack Wolong’s assets seem to be a bunch of random file names. How can I Know which file number corresponds to the corresponding model in the game? Or is there a way to unpack other assets to get a list file table for mapping the corresponding model in the game? Thank you again


Use these to make the g1t file associated to a given g1m. As for filenames they are stripped so you will only have the hashes.
WHWOThingy.zip

G1m hash on the left as usual, then
Code: Select allNyotengu.KTID.exe ..\kidsobjdb\0xb290631c.kidsobjdb ..\g1t ..\ktid\valueOnRightColumn.ktid
Only the non field props are covered by these (ie characters, mobs, animatable models etc), I'm not dling several dozens of gigs to make exhaustive file lists for games I'm not personally interested in.

Many thanks to Allanoon for testing and reporting bugs for this update.

good job
## Post #495
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2023-03-11T13:17:12+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Thu Mar 09, 2023 8:36 am at Thu Mar 09, 2023 8:36 am
>
> 
Version 1.7.4 is now available
This update adds support for the new NUNO update that TN/OF have been using for their recent titles.

I also updated the quickbms script to properly discriminate between the g1m files and the g1h containers, you should do a new proper extraction to have everything set up accordingly. It will also ignore the useless little files.

Thank you, this is really helpful
## Post #496
- Username: whtlook
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 31, 2022 12:37 am
- Post datetime: 2023-03-16T05:43:49+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Preview.png (173.57 KiB) Viewed 645 times


Works fine, Thanks a lot!
## Post #497
- Username: csh0748
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 22, 2022 2:06 pm
- Post datetime: 2023-03-16T12:08:35+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from whtlook ↑Thu Mar 16, 2023 1:43 pm at Thu Mar 16, 2023 1:43 pm
>
> 
Preview.png
Works fine, Thanks a lot!

deleted..
## Post #498
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2023-03-16T16:21:45+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

So i'm wondering, is there a way to get the g1a shapekey/morphs to load on the models yet ?
## Post #499
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-03-16T19:18:37+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Tsunani ↑Fri Mar 17, 2023 12:21 am at Fri Mar 17, 2023 12:21 am
>
> 
So i'm wondering, is there a way to get the g1a shapekey/morphs to load on the models yet ?

Nope. I'm not personally interested in them so I didn't research these at all.
## Post #500
- Username: ningen112
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 17, 2018 2:13 am
- Post datetime: 2023-03-18T11:55:21+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

So..Since I'm a dumbass, could someone help me get started with some general tips etc?  Or if possible grab me a couple of the models? I don't care about weights etc XD
## Post #501
- Username: ysjysj734
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Mar 26, 2023 11:01 pm
- Post datetime: 2023-03-28T01:10:06+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from whtlook ↑Thu Mar 16, 2023 1:43 pm at Thu Mar 16, 2023 1:43 pm
>
> 
Preview.png
Works fine, Thanks a lot!

I used Cethleann to extract the g1m file from Wolong, but my Noesis plugin was installed to preview the g1m file and it would crash. What's the matter, because I'm a novice
## Post #502
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-03-31T07:46:34+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Thu Mar 09, 2023 8:36 am at Thu Mar 09, 2023 8:36 am
>
> 
Version 1.7.4 is now available
This update adds support for the new NUNO update that TN/OF have been using for their recent titles.



I also updated the quickbms script to properly discriminate between the g1m files and the g1h containers, you should do a new proper extraction to have everything set up accordingly. It will also ignore the useless little files.
fdata.zip

Hi there!

Thank you for your hard work and help so far!

I have been extracting Wo Long with the .bms script and its working without issues, but when I try to do the same when loading all the .fdata files of Wild Hearts it simply crashes after a few seconds. 

Is Wild Hearts extracted using a different tool or script? here is the error that I get in quickbms

- 0 files found in 0 seconds
  coverage file 0    99%   1112811    1113452    . offset 000000000010fd6a
- open input file E:\Game\Wild Hearts\00_game\target_origin\ex\asset\fdata_ms12\package\0x00cca8fb.fdata
- open script I:\WORKING ON\Wild Hearts & Wo Long\quickbms\fdata.bms
- set output folder I:\WORKING ON\Wild Hearts & Wo Long\Wild Hearts

  offset           filesize   filename
--------------------------------------
16
72

Error: offset in GetVarChr (0x0000000000000000) is bigger than the var (0x00000000)

Last script line before the error or that produced the error:
  115 GetVarChr MAGIC MEMORY_FILE 0 long
  coverage file 0     0%   54         727145     . offset 0000000000000052

Press ENTER or close the window to quit
## Post #503
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-03-31T16:16:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hey there!

In Wo Long, I´m Trying to make the g1m files load with textures and I have used the following syntax:

Nyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" "Wo Long\CharacterEditor\ktid\*.ktid"

Obviously nothing happens, I know Im missing an element, perhaps the g1m I´m supposed to be point to, but I'm unsure where and how, and also if the *.kidsobjdb fiel I´m poin to towards is the adequate.

Could anyone please help me?
## Post #504
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2023-04-03T18:12:36+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Mar 10, 2023 4:20 am at Fri Mar 10, 2023 4:20 am
>
> 

Use these to make the g1t file associated to a given g1m. As for filenames they are stripped so you will only have the hashes.
WHWOThingy.zip

G1m hash on the left as usual, then
Code: Select allNyotengu.KTID.exe ..\kidsobjdb\0xb290631c.kidsobjdb ..\g1t ..\ktid\valueOnRightColumn.ktid
Only the non field props are covered by these (ie characters, mobs, animatable models etc), I'm not dling several dozens of gigs to make exhaustive file lists for games I'm not personally interested in.

Many thanks to Allanoon for testing and reporting bugs for this update.

Thanks for this but the KTID stuff usually works for me but for some reason with Wo Long it doesn't? The 0xb290631c file doesn't exist and CharacterEditor.kidssingletondb which usually works causes Cethleann to have an error. Am I misunderstanding something?
## Post #505
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-04-04T12:38:44+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from AzothRaven ↑Sat Apr 01, 2023 12:16 am at Sat Apr 01, 2023 12:16 am
>
> 
Hey there!

In Wo Long, I´m Trying to make the g1m files load with textures and I have used the following syntax:

Nyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" "Wo Long\CharacterEditor\ktid\*.ktid"

Obviously nothing happens, I know Im missing an element, perhaps the g1m I´m supposed to be point to, but I'm unsure where and how, and also if the *.kidsobjdb fiel I´m poin to towards is the adequate.

Could anyone please help me?

After executing the command the g1t path will be shown at the end. Put it next to the g1m file in a folder, make sure only these two are there then load the g1m file in Noesis with the "merge all" option ticked.

> Reply from TRDaz ↑Tue Apr 04, 2023 2:12 am at Tue Apr 04, 2023 2:12 am
>
> 
Thanks for this but the KTID stuff usually works for me but for some reason with Wo Long it doesn't? The 0xb290631c file doesn't exist and CharacterEditor.kidssingletondb which usually works causes Cethleann to have an error. Am I misunderstanding something?

Ceth outputs corrupted files due to them changing the layouts, you need to extract the .bins using the qbms script here [viewtopic.php?p=190489#p190489](https://forum.xentax.com/viewtopic.php?p=190489#p190489)
## Post #506
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2023-04-04T12:59:40+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Tue Apr 04, 2023 8:38 pm at Tue Apr 04, 2023 8:38 pm
>
> 
Ceth outputs corrupted files due to them changing the layouts, you need to extract the .bins using the qbms script here viewtopic.php?p=190489#p190489
Oh damnit I did extract the characters with this a bit ago and only just got to sorting the textures and forgot all about the bms script, what an idiot. Thank you!
## Post #507
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-04-05T06:52:42+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Tue Apr 04, 2023 8:38 pm at Tue Apr 04, 2023 8:38 pm
>
> 
AzothRaven wrote: ↑Sat Apr 01, 2023 12:16 am
Hey there!

In Wo Long, I´m Trying to make the g1m files load with textures and I have used the following syntax:

Nyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" "Wo Long\CharacterEditor\ktid\*.ktid"

Obviously nothing happens, I know Im missing an element, perhaps the g1m I´m supposed to be point to, but I'm unsure where and how, and also if the *.kidsobjdb fiel I´m poin to towards is the adequate.

Could anyone please help me?


After executing the command the g1t path will be shown at the end. Put it next to the g1m file in a folder, make sure only these two are there then load the g1m file in Noesis with the "merge all" option ticked.
TRDaz wrote: ↑Tue Apr 04, 2023 2:12 am
Thanks for this but the KTID stuff usually works for me but for some reason with Wo Long it doesn't? The 0xb290631c file doesn't exist and CharacterEditor.kidssingletondb which usually works causes Cethleann to have an error. Am I misunderstanding something?


Ceth outputs corrupted files due to them changing the layouts, you need to extract the .bins using the qbms script here viewtopic.php?p=190489#p190489

Hi Joschka!

Thank you for the help!
I just tried doing it like that using the first one for the WOThingy (that I assume is for Wo long and the WHThingy I assume is for Wild Hearts) and the command resolves without error but it doesn´t  give me the path fo the g1t, here is the full result:

```
[2023-04-05T06:43:07][Nyotengu] Nyotengu.KTID v1.0.0.0
[2023-04-05T06:43:08][Nyotengu] Arguments: ["I:\\WORKING ON\\Wild Hearts \u0026 Wo Long\\Wo Long\\KIDSSystemResource\\kidsobjdb\\0xb290631c.kidsobjdb","I:\\WORKING ON\\Wild Hearts \u0026 Wo Long\\Wo Long\\MaterialEditor\\g1t","I:\\WORKING ON\\Wild Hearts \u0026 Wo Long\\Wo Long\\MaterialEditor\\ktid\\0xf4c461ab.ktid"]
[2023-04-05T06:43:08][FileList] Loading filelist for unknown-rdb
```


Is the command ok like this? everytime that I run it it has to point towards the 0xb290631c.kidsobjdb in the kidsobjdb of the KIDSSystemResource extraction?

Any help you could provide would be highly appreciated
## Post #508
- Username: csh0748
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 22, 2022 2:06 pm
- Post datetime: 2023-04-06T08:01:30+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Mar 10, 2023 4:20 am at Fri Mar 10, 2023 4:20 am
>
> 
csh0748 wrote: ↑Thu Mar 09, 2023 2:17 pm
Hello, thank you very much for your hard work on this tool. What I want to know now is that the g1m and g1t files obtained after using quickbms to unpack Wolong’s assets seem to be a bunch of random file names. How can I Know which file number corresponds to the corresponding model in the game? Or is there a way to unpack other assets to get a list file table for mapping the corresponding model in the game? Thank you again


Use these to make the g1t file associated to a given g1m. As for filenames they are stripped so you will only have the hashes.
WHWOThingy.zip

G1m hash on the left as usual, then
Code: Select allNyotengu.KTID.exe ..\kidsobjdb\0xb290631c.kidsobjdb ..\g1t ..\ktid\valueOnRightColumn.ktid
Only the non field props are covered by these (ie characters, mobs, animatable models etc), I'm not dling several dozens of gigs to make exhaustive file lists for games I'm not personally interested in.

Many thanks to Allanoon for testing and reporting bugs for this update.
Now I know how to use the commands, Now there is only one problem left, none of the extracted characters have eye textures
## Post #509
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2023-04-06T08:34:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Jun 19, 2020 8:34 pm at Fri Jun 19, 2020 8:34 pm
>
> 
Fixes were easy enough, I missed something obvious when working on OPPW4.

SCRIPT UPDATED
-new textures formats added
-NUNO v32 fixes

Nioh 2 models should now work, only tested a few as I didn't have much time so report issues if you find some


A few notes about working on that game with the plugin :
Extraction
-The g1m and g1t files are in the pg1m containers. Use the latest version of Cethleann to unpack these : drag and drop the pg1m on Cethleann.Unbundler.exe to get a g1mpack and an exarg container. Drag and drop these once more to get the g1m and g1t.
-The animation files are in the pg2a containers. Drag and drop them on the Unbundler to get the anim files.

Models
-Some models are high poly so loading some of them will take a bit of time. I'll need to rewrite some code parts and make a C++ native plugin at some point for performance but I don't have the time for that right now.
-Some models are split into different parts. Use the model merger to load all of them at once, with the option value set at 1 to merge the bones (in the merge file). If you do that make sure that the skeleton g1m is not next to the other otherwise it won't work
-For those models split in parts, I recommend using the console options to not have to specify the skeleton everytime (set them in Tools > data viewer > persistent settings > other > default preview commands). I recommend setting up a "resource" folder where you'll put the associated g1t and skeleton file, that way you won't have to change the path everytime, in the console, just change the skeleton and g1t file for each model.
Make sure to remove these commands when you're done

Animations
-Animations are working but the split models make it a bit difficult to work with them since the merger doesn't work with anims without duplicating bones. Here's a possible workflow :

Step 1 : Load the model in Noesis, without animations. Then export it.


Step 2 : Turn the anim loading option on (either individual or folder), load the skeleton g1m file (0001.g1m) and put all the animations that you want on that file. Export that file too.


So now you have the model in one file and the animations in another file, you just need to merge them using a 3d software. Here's a possible workflow to do that in Blender, there may be a better way :

Step 1 : Import the animation file in Blender and directly save it as a blend file. I'll call it animation.blend

Step 2 : Make a new scene in Blender and now import your model file. Now go to "File" > "append", double click on the animation.blend then go to the "actions" folder and double-click on the file inside it (there should only be one action file unless you added more or split them in the animation.blend, if you just followed the steps above there'll only be one).

Step 3 : Select your armature. Now go to the action editor and click on the icon next to the "New" button. I repeat, select the icon, not the new button. . Then choose the action you just appended in the list.


That's it, the merged model will now have all the animations without duplicate bones.


Keep in mind that the physics meshes will not be animated as usual, only the driver meshes will follow the movement. So make sure to rig them properly as usual beforehand.

I don't understand the step 2 what is anim loading option and where isit?
## Post #510
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-04-08T19:49:22+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hey people!

Figured out the correct syntax for the Nyotengu and generate the g1t list of textures for each g1m model

in Wolong

```
Nyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" " Wo Long\CharacterEditor\ktid\rightcolumvalue.ktid"
```


In Wild Hearts

```
Nyotengu.KTID.exe "Wild Hearts\kidsobjdb\0xb290631c.kidsobjdb" "Wild Hearts\g1t" "\Wild Hearts\ktid\rightcolumvalue.ktid"
```


Hope it helps whoever needs it
## Post #511
- Username: csh0748
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 22, 2022 2:06 pm
- Post datetime: 2023-04-09T06:00:56+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from AzothRaven ↑Sun Apr 09, 2023 3:49 am at Sun Apr 09, 2023 3:49 am
>
> 
Hey people!

Figured out the correct syntax for the Nyotengu and generate the g1t list of textures for each g1m model

in Wolong
Code: Select allNyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" " Wo Long\CharacterEditor\ktid\rightcolumvalue.ktid"

In Wild Hearts
Code: Select allNyotengu.KTID.exe "Wild Hearts\kidsobjdb\0xb290631c.kidsobjdb" "Wild Hearts\g1t" "\Wild Hearts\ktid\rightcolumvalue.ktid"

Hope it helps whoever needs it

Thank you for your help. Now I have successfully unpacked Wolong, but I can’t find the eye textures of the characters. I don’t know where they are hidden. Did you find them?
## Post #512
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-04-09T17:22:11+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from csh0748 ↑Sun Apr 09, 2023 2:00 pm at Sun Apr 09, 2023 2:00 pm
>
> 
AzothRaven wrote: ↑Sun Apr 09, 2023 3:49 am
Hey people!

Figured out the correct syntax for the Nyotengu and generate the g1t list of textures for each g1m model

in Wolong
Code: Select allNyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" " Wo Long\CharacterEditor\ktid\rightcolumvalue.ktid"

In Wild Hearts
Code: Select allNyotengu.KTID.exe "Wild Hearts\kidsobjdb\0xb290631c.kidsobjdb" "Wild Hearts\g1t" "\Wild Hearts\ktid\rightcolumvalue.ktid"

Hope it helps whoever needs it


Thank you for your help. Now I have successfully unpacked Wolong, but I can’t find the eye textures of the characters. I don’t know where they are hidden. Did you find them?

No, sorry, Im still checking the assets from Wild Hearts first
## Post #513
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2023-04-12T09:43:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Mar 10, 2023 4:20 am at Fri Mar 10, 2023 4:20 am
>
> 
csh0748 wrote: ↑Thu Mar 09, 2023 2:17 pm
Hello, thank you very much for your hard work on this tool. What I want to know now is that the g1m and g1t files obtained after using quickbms to unpack Wolong’s assets seem to be a bunch of random file names. How can I Know which file number corresponds to the corresponding model in the game? Or is there a way to unpack other assets to get a list file table for mapping the corresponding model in the game? Thank you again


Use these to make the g1t file associated to a given g1m. As for filenames they are stripped so you will only have the hashes.
WHWOThingy.zip

G1m hash on the left as usual, then
Code: Select allNyotengu.KTID.exe ..\kidsobjdb\0xb290631c.kidsobjdb ..\g1t ..\ktid\valueOnRightColumn.ktid
Only the non field props are covered by these (ie characters, mobs, animatable models etc), I'm not dling several dozens of gigs to make exhaustive file lists for games I'm not personally interested in.

Many thanks to Allanoon for testing and reporting bugs for this update.

Good day Joschka,

Thank you for all your work so far!

The process works just fine, Im combing though the Wild Hearts files with it and its awesome. One (I think, can be totally wrong) simple question. How do you produce the file lists that contain the g1m and the appropriate kitd?

I ask because knowing Koei Tecmo there will be DLCs both for Wo Long and Wind Hearts, (the latter has been announced with new monsters and all) and I wanted to know if its a process that can be done with Cethleann or any other tool for when that happens.

As always any help would be greatly appreciated it.
## Post #514
- Username: leckock
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 04, 2020 11:48 pm
- Post datetime: 2023-04-26T13:42:55+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hello,

When i try to extract fdata from Wild Hearts with quickbms fdata script, it show me this error message.

Any suggestions ?

Have a good day  
[Capture.PNG](https://xentaxbackup.github.io/file/23715_Capture.PNG)
## Post #515
- Username: voyennyy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 17, 2019 8:50 am
- Post datetime: 2023-05-06T02:35:27+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from AzothRaven ↑Sun Apr 09, 2023 3:49 am at Sun Apr 09, 2023 3:49 am
>
> 
Hey people!

Figured out the correct syntax for the Nyotengu and generate the g1t list of textures for each g1m model

in Wolong
Code: Select allNyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" " Wo Long\CharacterEditor\ktid\rightcolumvalue.ktid"

In Wild Hearts
Code: Select allNyotengu.KTID.exe "Wild Hearts\kidsobjdb\0xb290631c.kidsobjdb" "Wild Hearts\g1t" "\Wild Hearts\ktid\rightcolumvalue.ktid"

Hope it helps whoever needs it

This is great! Nice and clear. Using this worked flawlessly!
## Post #516
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2023-05-26T15:29:07+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

So I've extracted both Strangers of Paradise: Final Fantasy Origin and Hyrule Warriors: Age of Calamity DLC and I'm getting crashes for some reason, any chance these could be looked at? One of the files in the FFO samples doesn't crash but just loads bones.

[https://drive.google.com/file/d/1O1_rw- ... sp=sharing](https://drive.google.com/file/d/1O1_rw-w3c25LTiFSwAuCJ0z7xwMymM2J/view?usp=sharing)
## Post #517
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-05-30T18:19:47+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from TRDaz ↑Fri May 26, 2023 11:29 pm at Fri May 26, 2023 11:29 pm
>
> 
So I've extracted both Strangers of Paradise: Final Fantasy Origin and Hyrule Warriors: Age of Calamity DLC and I'm getting crashes for some reason, any chance these could be looked at? One of the files in the FFO samples doesn't crash but just loads bones.

https://drive.google.com/file/d/1O1_rw- ... sp=sharing

Looks like these files weren't extracted correctly, some section headers are missing (among other issues).
## Post #518
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2023-05-30T19:53:03+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Wed May 31, 2023 2:19 am at Wed May 31, 2023 2:19 am
>
> Looks like these files weren't extracted correctly, some section headers are missing (among other issues).
That's weird, I used Cethleann the same way I did for the base game which worked perfectly so I don't understand what went wrong. I'll have to try and extract them again.
## Post #519
- Username: ZeroFX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 24, 2016 10:46 am
- Post datetime: 2023-05-30T22:26:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi, first off thanks for the plugin, i was able to load a Nioh 2 PS4's 1.27 model along with it's textures and animations. But i'm having a hard time getting the bone names of the skeleton, any tips regarding this? I noticed the model has a btree file, maybe it's related? I packed the character's files for you to take a look if needed.
[https://www.mediafire.com/file/vyy9ezq3 ... HI.7z/file](https://www.mediafire.com/file/vyy9ezq3bdr9fss/CE_TATEEBOSHI.7z/file)
## Post #520
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-05-31T10:09:24+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from ZeroFX ↑Wed May 31, 2023 6:26 am at Wed May 31, 2023 6:26 am
>
> 
Hi, first off thanks for the plugin, i was able to load a Nioh 2 PS4's 1.27 model along with it's textures and animations. But i'm having a hard time getting the bone names of the skeleton, any tips regarding this? I noticed the model has a btree file, maybe it's related? I packed the character's files for you to take a look if needed.

Most of the KT games don't have joint names, Atelier being their only series for which they usually leave them. They're usually stored in .oid files and most of the time they're hashed too.
So yeah you won't be able to retrieve these most likely as they cross reference everything using the joint IDs only.
## Post #521
- Username: ZeroFX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 24, 2016 10:46 am
- Post datetime: 2023-05-31T21:02:15+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Wed May 31, 2023 6:09 pm at Wed May 31, 2023 6:09 pm
>
> 
ZeroFX wrote: ↑Wed May 31, 2023 6:26 am
Hi, first off thanks for the plugin, i was able to load a Nioh 2 PS4's 1.27 model along with it's textures and animations. But i'm having a hard time getting the bone names of the skeleton, any tips regarding this? I noticed the model has a btree file, maybe it's related? I packed the character's files for you to take a look if needed.


Most of the KT games don't have joint names, Atelier being their only series for which they usually leave them. They're usually stored in .oid files and most of the time they're hashed too.
So yeah you won't be able to retrieve these most likely as they cross reference everything using the joint IDs only.

I see, that makes sense, thank you very much! I have another question for you, same model but exported as fbx, it is normal for cloth that is supposed (i suppose) to be skinned by nunobones to be unskinned?
## Post #522
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-06-01T07:40:18+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from ZeroFX ↑Thu Jun 01, 2023 5:02 am at Thu Jun 01, 2023 5:02 am
>
> 
I see, that makes sense, thank you very much! I have another question for you, same model but exported as fbx, it is normal for cloth that is supposed (i suppose) to be skinned by nunobones to be unskinned?

Unfortunately yeah, these nuno bones are not "true" bones but physics nodes simulated by the CPU and used in a complex vertex shader at runtime to deform the cloth with a very different algorithm than standard skinning. So there's no real weight data to be extracted, I can only emulate the vshader at the rest pose to have the cloth mesh loaded correctly.
I represent these nodes as bones so users can rig these manually or use cloth simulation or whatever they prefer.
## Post #523
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-06-01T08:51:27+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from AzothRaven ↑Sun Apr 09, 2023 3:49 am at Sun Apr 09, 2023 3:49 am
>
> 
Hey people!

Figured out the correct syntax for the Nyotengu and generate the g1t list of textures for each g1m model

in Wolong
Code: Select allNyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" " Wo Long\CharacterEditor\ktid\rightcolumvalue.ktid"

In Wild Hearts
Code: Select allNyotengu.KTID.exe "Wild Hearts\kidsobjdb\0xb290631c.kidsobjdb" "Wild Hearts\g1t" "\Wild Hearts\ktid\rightcolumvalue.ktid"

Hope it helps whoever needs it
i tried to do this in command prompt and it said loading Filelist.... Can someone please have a look and tell me what to do next. Im new to this, any help would be much appreciated. It seems i cant find "rightcolumvalue.ktid in the folder ktid. im trying to find texture for the models

C:\Users\ADMIN>D:\Downloads\Cethleann\Nyotengu.KTID.exe "D:\New folder\wo long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "D:\New folder\wo long\MaterialEditor\g1t" " D:\New folder\wo long\CharacterEditor\ktid\rightcolumvalue.ktid"
[2023-06-01T16:12:35][Nyotengu] Nyotengu.KTID v1.1.104.0
[2023-06-01T16:12:35][Nyotengu] Arguments: ["D:\\New folder\\wo long\\KIDSSystemResource\\kidsobjdb\\0xb290631c.kidsobjdb","D:\\New folder\\wo long\\MaterialEditor\\g1t"," D:\\New folder\\wo long\\CharacterEditor\\ktid\\rightcolumvalue.ktid"]
[2023-06-01T16:12:36][FileList] Loading filelist for unknown-rdb
## Post #524
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-06-02T02:49:41+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Mar 10, 2023 4:20 am at Fri Mar 10, 2023 4:20 am
>
> 
csh0748 wrote: ↑Thu Mar 09, 2023 2:17 pm
Hello, thank you very much for your hard work on this tool. What I want to know now is that the g1m and g1t files obtained after using quickbms to unpack Wolong’s assets seem to be a bunch of random file names. How can I Know which file number corresponds to the corresponding model in the game? Or is there a way to unpack other assets to get a list file table for mapping the corresponding model in the game? Thank you again


Use these to make the g1t file associated to a given g1m. As for filenames they are stripped so you will only have the hashes.
WHWOThingy.zip

G1m hash on the left as usual, then
Code: Select allNyotengu.KTID.exe ..\kidsobjdb\0xb290631c.kidsobjdb ..\g1t ..\ktid\valueOnRightColumn.ktid
Only the non field props are covered by these (ie characters, mobs, animatable models etc), I'm not dling several dozens of gigs to make exhaustive file lists for games I'm not personally interested in.

Many thanks to Allanoon for testing and reporting bugs for this update.

Can you please tell me more about steps to make g1t file associated to g1m? im confused how to add the WOThingy. Thanks in advance
## Post #525
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-06-02T06:07:04+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer


## Post #526
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-06-02T07:37:14+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Jun 02, 2023 2:07 pm at Fri Jun 02, 2023 2:07 pm
>
> 

Thank you for helping. After i following your guide, i found the correct ktid, but what i need to do next. It still said loading filelist (below), but i dont know where to find the filelist to know which g1t for g1m. Thanks again for the help.

C:\Users\ADMIN>D:\Downloads\CethleannStandalone\Nyotengu.KTID.exe "D:\New folder\wo long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "D:\New folder\wo long\MaterialEditor\g1t" " D:\New folder\wo long\CharacterEditor\ktid\0x205b2d3f.ktid"
[2023-06-02T07:24:15][Nyotengu] Nyotengu.KTID v1.1.104.0
[2023-06-02T07:24:15][Nyotengu] Arguments: ["D:\\New folder\\wo long\\KIDSSystemResource\\kidsobjdb\\0xb290631c.kidsobjdb","D:\\New folder\\wo long\\MaterialEditor\\g1t"," D:\\New folder\\wo long\\CharacterEditor\\ktid\\0x205b2d3f.ktid"]
[2023-06-02T07:24:16][FileList] Loading filelist for unknown-rdb

Edited: NVM, i figured it out, its because a space in the code. Thank you for helping.
## Post #527
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2023-06-02T20:18:27+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

How did you extract the game files?
## Post #528
- Username: superlbr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 08, 2023 6:56 pm
- Post datetime: 2023-06-09T00:15:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Jun 02, 2023 2:07 pm at Fri Jun 02, 2023 2:07 pm
>
> 
Hi, which kidsobjdb should i use to deal those ktid?
## Post #529
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-06-18T06:58:26+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from superlbr ↑Fri Jun 09, 2023 8:15 am at Fri Jun 09, 2023 8:15 am
>
> 
Joschka wrote: ↑Fri Jun 02, 2023 2:07 pm


Hi, which kidsobjdb should i use to deal those ktid?

Use this below to extract the correct file bro:

> Reply from AzothRaven ↑Sun Apr 09, 2023 3:49 am at Sun Apr 09, 2023 3:49 am
>
> 
Hey people!

Figured out the correct syntax for the Nyotengu and generate the g1t list of textures for each g1m model

in Wolong
Code: Select allNyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" " Wo Long\CharacterEditor\ktid\rightcolumvalue.ktid"

In Wild Hearts
Code: Select allNyotengu.KTID.exe "Wild Hearts\kidsobjdb\0xb290631c.kidsobjdb" "Wild Hearts\g1t" "\Wild Hearts\ktid\rightcolumvalue.ktid"

Hope it helps whoever needs it
## Post #530
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-06-18T07:00:01+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Jun 02, 2023 2:07 pm at Fri Jun 02, 2023 2:07 pm
>
> 

Hi Joschka, is there anyway to find the creation character that we created in Wolong ? i really want to extract the head model, but i cant find it. Thanks for the help !
## Post #531
- Username: superlbr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 08, 2023 6:56 pm
- Post datetime: 2023-06-21T09:38:47+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Steven2212 ↑Sun Jun 18, 2023 2:58 pm at Sun Jun 18, 2023 2:58 pm
>
> 
Use this below to extract the correct file bro:
AzothRaven wrote: ↑Sun Apr 09, 2023 3:49 am
Hey people!

Figured out the correct syntax for the Nyotengu and generate the g1t list of textures for each g1m model

in Wolong
Code: Select allNyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" " Wo Long\CharacterEditor\ktid\rightcolumvalue.ktid"

In Wild Hearts
Code: Select allNyotengu.KTID.exe "Wild Hearts\kidsobjdb\0xb290631c.kidsobjdb" "Wild Hearts\g1t" "\Wild Hearts\ktid\rightcolumvalue.ktid"

Hope it helps whoever needs it

ktid\rightcolumvalue.ktid not found, all 0a66bc90.ktid like..
## Post #532
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-06-29T14:01:28+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from superlbr ↑Wed Jun 21, 2023 5:38 pm at Wed Jun 21, 2023 5:38 pm
>
> 
Steven2212 wrote: ↑Sun Jun 18, 2023 2:58 pm
Use this below to extract the correct file bro:
AzothRaven wrote: ↑Sun Apr 09, 2023 3:49 am
Hey people!

Figured out the correct syntax for the Nyotengu and generate the g1t list of textures for each g1m model

in Wolong
Code: Select allNyotengu.KTID.exe "Wo Long\KIDSSystemResource\kidsobjdb\0xb290631c.kidsobjdb" "Wo Long\MaterialEditor\g1t" " Wo Long\CharacterEditor\ktid\rightcolumvalue.ktid"

In Wild Hearts
Code: Select allNyotengu.KTID.exe "Wild Hearts\kidsobjdb\0xb290631c.kidsobjdb" "Wild Hearts\g1t" "\Wild Hearts\ktid\rightcolumvalue.ktid"

Hope it helps whoever needs it



ktid\rightcolumvalue.ktid not found, all 0a66bc90.ktid like..
You have to find which .g1m model you need to extract, then find the vale on the right colum in the Wothingy file that Joschka provie. Then you use Nyotengu.KTID.exe with the syntax AzothRaven provide above to extract .g1t that fit with .g1m you want. After that put these files in the same place so you can view on Noesis.
## Post #533
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-06-29T14:04:21+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi Joschka, can you please update Wothingy file for Wolong with the new DLC, they add some new models to the game. its so hard to file the correct g1t files. Thanks so much for your help !!
## Post #534
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2023-07-04T15:52:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from leckock ↑Wed Apr 26, 2023 9:42 pm at Wed Apr 26, 2023 9:42 pm
>
> 
Hello,

When i try to extract fdata from Wild Hearts with quickbms fdata script, it show me this error message.

Any suggestions ?

Have a good day
I get the same error when trying to unpack some Wo Long archives (RRPreview.rdb.bin or EventMaker3.rdb.bin, or both)

> Reply from Steven2212 ↑Thu Jun 29, 2023 10:04 pm at Thu Jun 29, 2023 10:04 pm
>
> 
Hi Joschka, can you please update Wothingy file for Wolong with the new DLC, they add some new models to the game. its so hard to file the correct g1t files. Thanks so much for your help !!

you can try narrow your searches, if you have 1.09 game version archives extracted prior to DLC, you can use any program like "SearchMyFiles" to get only new ktid files
## Post #535
- Username: Steven2212
- Rank: n00b
- Number of posts: 12
- Joined date: Wed May 31, 2023 8:20 pm
- Post datetime: 2023-07-05T07:46:45+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

[/quote]
you can try narrow your searches, if you have 1.09 game version archives extracted prior to DLC, you can use any program like "SearchMyFiles" to get only new ktid files
[/quote]

Can you please tell me which program to open the ktid? i counldnt find one. Thank you !
## Post #536
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2023-07-18T12:36:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Steven2212 ↑Wed Jul 05, 2023 3:46 pm at Wed Jul 05, 2023 3:46 pm
>
> 
Can you please tell me which program to open the ktid? i counldnt find one. Thank you !
I don't know. Just extract 1.09 and post-patch Wo Long and use program to search duplicate files and delete them, remaining output should be all unique new files and textures...
## Post #537
- Username: dukitamoy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 25, 2023 12:30 pm
- Post datetime: 2023-07-25T16:47:22+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Is there a file similar to WOthingy for Stranger of Paradise? Or a way i could find out which textures go to which models? Thanks for any help.
## Post #538
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2023-07-25T17:07:06+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from dukitamoy ↑Wed Jul 26, 2023 12:47 am at Wed Jul 26, 2023 12:47 am
>
> 
Is there a file similar to WOthingy for Stranger of Paradise? Or a way i could find out which textures go to which models? Thanks for any help.

In this post here yeah [viewtopic.php?p=183455#p183455](https://forum.xentax.com/viewtopic.php?p=183455#p183455)
## Post #539
- Username: dukitamoy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 25, 2023 12:30 pm
- Post datetime: 2023-07-25T17:10:25+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Petrgold ↑Wed Jul 26, 2023 1:07 am at Wed Jul 26, 2023 1:07 am
>
> 
dukitamoy wrote: ↑Wed Jul 26, 2023 12:47 am
Is there a file similar to WOthingy for Stranger of Paradise? Or a way i could find out which textures go to which models? Thanks for any help.


In this post here yeah viewtopic.php?p=183455#p183455

Thanks so much! I didn't see that. 

EDIT: 
I think it's only able to be used on character assets. Is there a way I can find which textures go to which models for the background objects?
## Post #540
- Username: wuxiao
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 07, 2021 3:36 pm
- Post datetime: 2023-07-30T08:46:48+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

There are only body models here, is there a way to find other parts of the model?
## Post #541
- Username: wuxiao
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 07, 2021 3:36 pm
- Post datetime: 2023-07-30T08:48:04+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Is there a way to find kitd similar to the g1t file, and combine the models of the same kit together?
## Post #542
- Username: KristalWolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 19, 2023 6:04 am
- Post datetime: 2023-08-18T22:23:54+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hiya~

So I've downloaded what I believe to be the most recent up-to-date plugins and Noesis version, and I have .g1a files extracted from One Piece Pirate Warriors 4 on PC, but Noesis doesn't recognise them at all. It doesn't have a dedicated filetype filter for them or anything.

I'm new to extracting Koei Tecmo games assets, and how to use Noesis properly, so I've probably missed something important in this forum, but right now I'm just lost on what to do.

Any help would be appreciated, thanks~ 



image_2023-08-18_232301536.png (4.11 KiB) Viewed 458 times
## Post #543
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-19T16:19:43+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I don't think you can load .g1a files separately, do you?

Allegedly you'll need to load a g1m file before. (In Noesis you might also have a lock at Tools\Project G1M.)
## Post #544
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-08-24T07:43:23+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from shakotay2 ↑Sun Aug 20, 2023 12:19 am at Sun Aug 20, 2023 12:19 am
>
> 
I don't think you can load .g1a files separately, do you?

Allegedly you'll need to load a g1m file before. (In Noesis you might also have a lock at Tools\Project G1M.)

This is correct, you need to:
-put the g1m file and the g1a files you want loaded in the same folder.
-under "tools->pg1m" make sure that "merge all" is selected.
-open the g1m file, the g1a files next to it will be loaded automatically.
## Post #545
- Username: PiqMonKey
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 26, 2010 5:05 pm
- Post datetime: 2023-08-24T19:28:30+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi, someone know where to find character gameplay animations in Wo Long? g1a files I found are mainly for cutscene
## Post #546
- Username: Relyt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 22, 2021 4:43 pm
- Post datetime: 2023-08-28T14:46:56+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

if the Stranger of Paradise file used for character texture is CharacterEditor.kidssingletondb,so which kidssingletondb file is used in the level scene models?i think there are too many textures in the scene model,hard to find out which textures go to which models...
## Post #547
- Username: KristalWolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 19, 2023 6:04 am
- Post datetime: 2023-08-30T12:29:16+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Thu Aug 24, 2023 3:43 pm at Thu Aug 24, 2023 3:43 pm
>
> 
shakotay2 wrote: ↑Sun Aug 20, 2023 12:19 am
I don't think you can load .g1a files separately, do you?

Allegedly you'll need to load a g1m file before. (In Noesis you might also have a lock at Tools\Project G1M.)


This is correct, you need to:
-put the g1m file and the g1a files you want loaded in the same folder.
-under "tools->pg1m" make sure that "merge all" is selected.
-open the g1m file, the g1a files next to it will be loaded automatically.

I apologise in advance if there's something obvious that I should be doing, but I have followed those steps, and yet the animations still don't load and can't be previewed.

These are my 'Project G1M' settings: 


image_2023-08-30_132356014.png (44.09 KiB) Viewed 313 times
## Post #548
- Username: AdmiralTraun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 01, 2020 3:46 pm
- Post datetime: 2023-09-07T21:22:29+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from KristalWolf ↑Wed Aug 30, 2023 8:29 pm at Wed Aug 30, 2023 8:29 pm
>
> 
Joschka wrote: ↑Thu Aug 24, 2023 3:43 pm
shakotay2 wrote: ↑Sun Aug 20, 2023 12:19 am
I don't think you can load .g1a files separately, do you?

Allegedly you'll need to load a g1m file before. (In Noesis you might also have a lock at Tools\Project G1M.)


This is correct, you need to:
-put the g1m file and the g1a files you want loaded in the same folder.
-under "tools->pg1m" make sure that "merge all" is selected.
-open the g1m file, the g1a files next to it will be loaded automatically.


I apologise in advance if there's something obvious that I should be doing, but I have followed those steps, and yet the animations still don't load and can't be previewed.

These are my 'Project G1M' settings: image_2023-08-30_132356014.png
did you figure out how to solve the problem?
## Post #549
- Username: KristalWolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 19, 2023 6:04 am
- Post datetime: 2023-09-09T10:53:19+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I'm afraid not. This is all still pretty foreign to me
## Post #550
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-09T13:18:53+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from KristalWolf ↑Sat Sep 09, 2023 6:53 pm at Sat Sep 09, 2023 6:53 pm
>
> 
I'm afraid not. This is all still pretty foreign to meUsually there is a Noesis log window. What does it show after you opened a g1m file?

btw: the log is enabled in this python function like so:
def registerNoesisTypes():
...
    noesis.logPopup()
return 1
## Post #551
- Username: huuvien23102000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 08, 2023 6:38 am
- Post datetime: 2023-09-09T14:44:13+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Hi, I'm curious about how they generated some .csv filetables for games like OPPW4, Fairy Taiil, and DOA6 that show the name of the extracted file according to the character, scene, material, etc. Is it something achievable since they are [rdb] format? And if it does, how can I generate one for myself for the new DLCs coming up for OPPW4? Thank you so much.
## Post #552
- Username: KristalWolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 19, 2023 6:04 am
- Post datetime: 2023-09-10T09:08:38+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from shakotay2 ↑Sat Sep 09, 2023 9:18 pm at Sat Sep 09, 2023 9:18 pm
>
> 
KristalWolf wrote: ↑Sat Sep 09, 2023 6:53 pm
I'm afraid not. This is all still pretty foreign to me
Usually there is a Noesis log window. What does it show after you opened a g1m file?

btw: the log is enabled in this python function like so:
def registerNoesisTypes():
...
    noesis.logPopup()
return 1

It finds a lot of Texture Material info, loads the submeshes, but then fails to read 'something'



image_2023-09-10_100709577.png (6.66 KiB) Viewed 200 times
## Post #553
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-10T14:03:53+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I think you can ignore these fails. I saw similar for many other formats (really need to check this one day  ).

If it loads sub meshes then try to export as .obj file (File\Export, choose main output type ".obj - wavefront OBJ").

Then check that .obj file. 
Should look like

```
#
mtllib unused.mtl
g
v  -0.000234 -0.062526 1.514810
v  0.036685 -0.043366 1.486024
v  0.032603 -0.043747 1.525223
...
g somename00
usemtl None
f  1/1/1 2/2/2 3/3/3
f  4/4/4 5/5/5 6/6/6
f  7/7/7 8/8/8 9/9/9
...

```
## Post #554
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2023-09-12T10:29:54+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Allanoon ↑Mon Mar 02, 2020 7:12 pm at Mon Mar 02, 2020 7:12 pm
>
> 
PRP1986 wrote: ↑Sun Mar 01, 2020 2:28 am
Thanks all, I have tried the above methods, with no luck unfortunately, though most likely it is something I am doing! I tried with Steven's Gas Machine using various game profiles (as there isn't a profile for Fist of The North Star), but was only able to get texture files from the LINKDATA files. I also tried the offzip method but just get .dat files.

Anyway I won't keep hijacking the thread, thanks again 

http://www.mediafire.com/file/8ne700n3l ... 2.rar/file

Here are the files i used.
NS2.bms is chrrox script to decrypt the files (MUST BE PS3, XBOX360 are a mess).
Then there's the python script (can't remember where i found it), you need it to decrypt files that have KTZ0 header (like models/anim).
Trim Header, is a powershell script to mass trim the textures header so they can be easily readable on noesis (edit it first).
The XML files are for VGMtoolbox to mass extract G1M/G2A files from the new .bin files that you get with the python script, put them into plugins/AdvanceCutter folder and load them.

On another note Warriors Legend of Troy (2011!) works with the script.
The file are in .cpkg .mpkg format
viewtopic.php?f=16&t=6252 thanks to chrrox   
Once you've the big .dat file you can use VGMtoolbox or w/e to extract .g1m .g1t .g1a files.

OT: A pity that Ninja Gaidens use a different format. 
Also, does anyone got a better Koei game list than the one on Wikipedia? It's out of date; missing games like Persona 4/5 or Dragon Quest Builders. I'm kinda out of games to check, if any, ahah.

isit possible to reupload the files the mediafire link is ded
## Post #555
- Username: zaay
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 16, 2023 10:30 pm
- Post datetime: 2023-09-16T15:56:09+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

when i try to export or open a g1m file noesis crashes can someone help me out here?
## Post #556
- Username: zaay
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 16, 2023 10:30 pm
- Post datetime: 2023-09-16T19:39:49+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from KristalWolf ↑Sat Aug 19, 2023 6:23 am at Sat Aug 19, 2023 6:23 am
>
> 
Hiya~

So I've downloaded what I believe to be the most recent up-to-date plugins and Noesis version, and I have .g1a files extracted from One Piece Pirate Warriors 4 on PC, but Noesis doesn't recognise them at all. It doesn't have a dedicated filetype filter for them or anything.

I'm new to extracting Koei Tecmo games assets, and how to use Noesis properly, so I've probably missed something important in this forum, but right now I'm just lost on what to do.

Any help would be appreciated, thanks~ 

image_2023-08-18_232301536.png

how did you get the luffy mesh because it only shows the skeleton for me?
## Post #557
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-09-29T06:05:37+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

The new Fate game works fine with the latest project G1M version



G1M/G1T list:


 FateThingy.zip
(8.7 KiB) Downloaded 79 times
## Post #558
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2023-09-29T07:33:42+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from Joschka ↑Fri Sep 29, 2023 2:05 pm at Fri Sep 29, 2023 2:05 pm
>
> 
The new Fate game works fine with the latest project G1M version



G1M/G1T list:

FateThingy.zip

May I ask where can u found animation for specific character? i want to get Zhou Yu animation too
## Post #559
- Username: 萌豚燃
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 27, 2022 10:05 am
- Post datetime: 2023-10-01T06:18:31+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

Excuse me, where can I obtain the script for the new single machine decompression of the fat in fdata format and use this script to obtain the g1m g1t file?
## Post #560
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2023-10-01T15:08:16+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from 萌豚燃 ↑Sun Oct 01, 2023 2:18 pm at Sun Oct 01, 2023 2:18 pm
>
> 
Excuse me, where can I obtain the script for the new single machine decompression of the fat in fdata format and use this script to obtain the g1m g1t file?
[viewtopic.php?t=21666&start=480](https://forum.xentax.com/viewtopic.php?t=21666&start=480)
Page 33, scroll down, for Joschka answers
## Post #561
- Username: mi z
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 28, 2023 12:15 pm
- Post datetime: 2023-10-06T05:46:54+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

> Reply from 萌豚燃 ↑Sun Oct 01, 2023 2:18 pm at Sun Oct 01, 2023 2:18 pm
>
> 
Excuse me, where can I obtain the script for the new single machine decompression of the fat in fdata format and use this script to obtain the g1m g1t file?

Did you succeed? When I open g1m, my Noesis will crash
## Post #562
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2023-10-09T00:07:11+00:00
- Post Title: Re: Noesis g1m/g1t/g1a importer

I've been trying to export the files from Stranger of Paradise but i have not been successful, am I supposed to use the bms scripts for this game, because when i use Ceth the G1Ms are corrupted.
