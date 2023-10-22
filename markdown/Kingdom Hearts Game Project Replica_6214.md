## Post #1
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-13T15:27:57+00:00
- Post Title: Kingdom Hearts Game Project Replica

I am creating a Kingdom Hearts replica project for training purposes. What i need is to find Kingdom hearts models with animation and then export them as .MD2 file format in order to load them with my game engine. If you can help please don't hesitate to answer me.
## Post #2
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-13T22:37:20+00:00
- Post Title: Kingdom Hearts Game Project Replica

You can export Kingdom Hearts 2 models to md2 with Noesis, and you can export animations from several other games to md2 with Noesis, and you can view Kingdom Hearts 2 animations with either kkdf2 or yaz0r's latest MDLX viewers, but you can't export animations from any Kingdom Hearts game to any other format at the present time. If you or someone else made a Kingdom Hearts 2 mset plugin for Noesis, it could be exported to md2 as you require. But no one has done so at the present time, so unless you used 3D Ripper DX or 3D Via PrintScreen to capture every single animation frame of yaz0r's new KH2 model viewer, there's no way you can utilize the animations in other programs at this time.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-14T03:02:50+00:00
- Post Title: Kingdom Hearts Game Project Replica

As soon as a KH/2 mset plugin is made though, it'll be very straight forward from there.

Also, MD2? Might I suggest MD3 instead? MD2 conversion is a bit trying and doesn't support multiple skins as KH uses. It would preserve the model better and MD3 is another documented format used in a number of engines.
## Post #4
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-20T21:46:29+00:00
- Post Title: Kingdom Hearts Game Project Replica

Where can i download Noesis?
## Post #5
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-03-20T22:18:40+00:00
- Post Title: Kingdom Hearts Game Project Replica

you can download it here [http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)
## Post #6
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-21T15:14:30+00:00
- Post Title: Kingdom Hearts Game Project Replica

Ok , i downloaded Noesis. I had found Sora's model in .MDX and i had converted it in .MD3 file format with each of its animations seperated , so what i did was to converted it in .MD2 and today i imported it successfully with all of its animation inside in my Engine. So what i need now is how to find other models from the game in order to open them with Noesis and then export them as .MD2. 

P.S.
I would like to download also Kingdom hearts worlds and i am also interested for Birth By Sleep models.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-21T18:25:45+00:00
- Post Title: Kingdom Hearts Game Project Replica

Hm? All its animations? But animations are not supported yet as said since there are no mset plugins yet.
## Post #8
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-21T19:04:19+00:00
- Post Title: Kingdom Hearts Game Project Replica

Perhaps they meant skinning? When I export models into the dae format from Noesis, Maya doesn't load the model with one skin, it loads a separate skin for each model part. If anyone didn't know, by skin I mean the collection of vertex weights for a model. 

Maya calls them skinclusters. If you tell noesis to combine the mesh, it will combine whatever parts it can (I think based on what parts share the same texture.) So KH2 Kairi went from about 14 different skin clusters down to seven. 

I'd like to edit it so that there is just one skincluster for the entire model, but I'm new with maya and still figuring it out. Also, I read somewhere that if you combine the model so that all the skin clusters are linked to one basic one, it will slow things down a lot cause it'll eat up a ton more memory. I'm not sure if that would apply if all the skinclusters are combined into one large one.. which I'd like to do once I figure it out.

I'm way more comfortable in max9... but for some reason max9 takes FOREVER to load fbx/dae files, and it totally murders my poor cpu. (Seriously, I timed it. To load kh2 kairi's dae file it took FOUR D@MN MINUTES, with the CPU at like 100% the entire time.) Maya 2011 loads the same file in about 30 seconds. So yeah... I'm switching to maya even though I still get really confused and stuck a lot of the time.
## Post #9
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-21T21:51:39+00:00
- Post Title: Kingdom Hearts Game Project Replica

@Darkfox : As i told before i had Sora's model into MD3 file format, so i exported it into MD2 file format with Noesis.

Also does anybody know where can i download "The world that never was" model? Or where can i download Sora's voice clips from Kingdom hearts 1?
## Post #10
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-21T23:05:29+00:00
- Post Title: Kingdom Hearts Game Project Replica

> Reply from sotiris
>
> @Darkfox : As i told before i had Sora's model into MD3 file format, so i exported it into MD2 file format with Noesis.

Also does anybody know where can i download "The world that never was" model? Or where can i download Sora's voice clips from Kingdom hearts 1?

First, you buy the game. Second, you use the dumpers on it
## Post #11
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-22T12:06:31+00:00
- Post Title: Kingdom Hearts Game Project Replica

> Reply from ultimaespio
>
> sotiris wrote:@Darkfox : As i told before i had Sora's model into MD3 file format, so i exported it into MD2 file format with Noesis.

Also does anybody know where can i download "The world that never was" model? Or where can i download Sora's voice clips from Kingdom hearts 1?

First, you buy the game. Second, you use the dumpers on it

I already have Kh1 & Kh2 disk. What dumpers do i need? and will i be able to open the models with Noesis?
## Post #12
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-22T13:25:59+00:00
- Post Title: Kingdom Hearts Game Project Replica

I also need Sora's voice clips from KH1. Also i would like Battle sound effects (e.x beep sound when life points are almost equals to zero ) . Also about the pictures they use in Command menu are availabe?
## Post #13
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-26T17:42:22+00:00
- Post Title: Kingdom Hearts Game Project Replica

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-28T13:54:45+00:00
- Post Title: Kingdom Hearts Game Project Replica

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-29T00:32:47+00:00
- Post Title: Kingdom Hearts Game Project Replica

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-29T11:15:10+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from SoftIce
>
> 
Dude, try to be a tad more undemanding.   No one has to rip stuff for other people, ya know. What sound files of Sora's are you looking for? I have some of his from KH2 in Japanese and I think in English.
I want the voice clips when he attacks , get a hit , jump and when he says  "Give me strength" and whatever else you have.
## Post #17
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-29T11:17:24+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

Here is also a screenshot taken by my game engine
## Post #18
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-03-31T12:51:15+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

wow it looks really good what game Engine do you use?

maybe i should try to make a Replica too but on CryENGINE 2 or 3
## Post #19
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-03-31T13:28:01+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from philip92dk
>
> wow it looks really good what game Engine do you use?

maybe i should try to make a Replica too but on CryENGINE 2 or 3

Thank you! 
Basically it's my own game engine built from scratch.
## Post #20
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-01T00:23:37+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

Can you really make a 3D game environment from scratch?
## Post #21
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-01T11:45:19+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from Mirrorman95
>
> Can you really make a 3D game environment from scratch?
Yes , i can . Why? I use OpenGL for rendering.
## Post #22
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-04-01T23:31:49+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

awesome stuff
## Post #23
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-04-02T00:58:04+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

are you looking for just KH? I'm not sure I have those. I'll look for the CD I burned my sound stuff on though. 

That's an amazing screenshot. Is the replica going to be for the PC or are you making a homebrew ps2 type of thing? That's sweet that you know how to add in the animations and joints and all that. *is impressed*
## Post #24
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-04-02T01:00:53+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

why make your own engine when there are alot of good ones that already works? there is much time just spent on making engine when you can spend it at doing the game instead
## Post #25
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-04-02T14:32:07+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from pixellegolas
>
> why make your own engine when there are alot of good ones that already works? there is much time just spent on making engine when you can spend it at doing the game instead
He already said why in his original post..

> Reply from sotiris
>
> I am creating a Kingdom Hearts replica project for training purposes.
## Post #26
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-02T14:41:01+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from jaden
>
> awesome stuff
Thank you   

> Reply from SoftIce
>
> are you looking for just KH? I'm not sure I have those. I'll look for the CD I burned my sound stuff on though. 

That's an amazing screenshot. Is the replica going to be for the PC or are you making a homebrew ps2 type of thing? That's sweet that you know how to add in the animations and joints and all that. *is impressed*

Ok if you can upload somewhere the sounds let me know. So far the game can run on Windows , Linux , MacOs and wherever OpenGL is supported. I think i could compile it so that it could be run on ps2 but i don't know the procedure   

> Reply from pixellegolas
>
> why make your own engine when there are alot of good ones that already works? there is much time just spent on making engine when you can spend it at doing the game instead

Well i could do that , but i am still young and i would prefer to learn how to think on 3d on my own for now. Basically i am still a student
## Post #27
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-02T16:15:45+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from sotiris
>
> Mirrorman95 wrote:Can you really make a 3D game environment from scratch?
Yes , i can . Why? I use OpenGL for rendering.

Well, what you'll need now are the Map files from KH2, in order to have real Kingdom Hearts environments. They can be exported from KH2FM with kkdf2's exporter and converted to Blender with his viewer or to DAE or OBJ with Revelation's Noesis plugin. If you just have KH2, Yaz0r's newest exporter can export the files, but you need to replace all instances of "map/jp/**##.map" to "map/us/**##.map" in the exe in order to get them.
## Post #28
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-02T20:28:04+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from Mirrorman95
>
> sotiris wrote:Mirrorman95 wrote:Can you really make a 3D game environment from scratch?
Yes , i can . Why? I use OpenGL for rendering.

Well, what you'll need now are the Map files from KH2, in order to have real Kingdom Hearts environments. They can be exported from KH2FM with kkdf2's exporter and converted to Blender with his viewer or to DAE or OBJ with Revelation's Noesis plugin. If you just have KH2, Yaz0r's newest exporter can export the files, but you need to replace all instances of "map/jp/**##.map" to "map/us/**##.map" in the exe in order to get them.

I have already bought the KH2 disk , where can i find more info about this <<Yaz0r's exporter>> ? Do you know the procedure ? Is there any other guy who has extracted the <<real Kingdom Hearts enviroments>> ?
## Post #29
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-04-02T21:17:42+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from sotiris
>
> 
Ok if you can upload somewhere the sounds let me know. So far the game can run on Windows , Linux , MacOs and wherever OpenGL is supported. I think i could compile it so that it could be run on ps2 but i don't know the procedure

lol still awesome though. You should totally make a custom level for a world not included in the original game! haha, I saw some tutorial for how to make a red square pixel for a homebrew ps2 game... it was like a page of code. lol. I'll try to find my cd and I'll see if I have KH Sora on it. Have you tried using Jaeder Naub on it? That's what I used I think. If you tell it to extract .vag files it should find a lot of them.
## Post #30
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-03T03:35:22+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

The contents of this post was deleted because of possible forum rules violation.
## Post #31
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-04-03T04:13:03+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

when its finish are you gonna share your kingdom heart replica game ?????????
## Post #32
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-03T09:16:00+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

The contents of this post was deleted because of possible forum rules violation.
## Post #33
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-03T09:18:27+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from jaden
>
> when its finish are you gonna share your kingdom heart replica game ?????????

I haven't thought about that yet , but maybe yes.
## Post #34
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-03T15:18:12+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

The contents of this post was deleted because of possible forum rules violation.
## Post #35
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-03T15:54:45+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from Mirrorman95
>
> 
That makes a difference. Alright, I've updated that link to hold two versions of the dumper; dumpU for the US ISO, and dumpE for the European ISO (assuming the symbol for the EUR disk is eu). If this doesn't work, I'll just have to manually find the real symbol out of my own KH2 disk.

I have the same problem with dumpE.
## Post #36
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-04-03T16:46:33+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

I use the gameengine called gamecore3d and also wish to make a project. Something similar to kingdom hearts would be really cool.

It supports 3ds, obj, fbx, ms3d

Fbx is best because it bakes model, texture, animation and even lights.

Well, that is just a thought 

[www.gamecore3d.com](http://www.gamecore3d.com) if you want to look. And I know you stated that you want to learn by yourself and that is really great. But I have seen so many mini engines being created that leads to frustration that sometimes it's just better to get good at what is out there. But cudos to you for trying
## Post #37
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-03T23:20:46+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from sotiris
>
> Mirrorman95 wrote:
That makes a difference. Alright, I've updated that link to hold two versions of the dumper; dumpU for the US ISO, and dumpE for the European ISO (assuming the symbol for the EUR disk is eu). If this doesn't work, I'll just have to manually find the real symbol out of my own KH2 disk.

I have the same problem with dumpE.

The available remaining options are uk, it, sp, gr, and fr. The United Kingdom, Italy, Spain, Germany, and France. Which should I do first?
## Post #38
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-04T11:50:09+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from Mirrorman95
>
> sotiris wrote:Mirrorman95 wrote:
That makes a difference. Alright, I've updated that link to hold two versions of the dumper; dumpU for the US ISO, and dumpE for the European ISO (assuming the symbol for the EUR disk is eu). If this doesn't work, I'll just have to manually find the real symbol out of my own KH2 disk.

I have the same problem with dumpE.

The available remaining options are uk, it, sp, gr, and fr. The United Kingdom, Italy, Spain, Germany, and France. Which should I do first?

UK
## Post #39
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-04T16:04:08+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

I have modified the dumper so use the UK region keyword. The same link has been updated with the dumper. If this is a UK disk, it should dump correctly this time.
## Post #40
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-04T16:38:28+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

> Reply from Mirrorman95
>
> I have modified the dumper so use the UK region keyword. The same link has been updated with the dumper. If this is a UK disk, it should dump correctly this time.

Same problem , same error   . I can't understand the reason why you don't upload the files yourself if you know the procedure?
## Post #41
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-04T23:30:03+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

The contents of this post was deleted because of possible forum rules violation.
## Post #42
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-04-07T11:10:50+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

The contents of this post was deleted because of possible forum rules violation.
## Post #43
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-07T14:16:39+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

Vsb and map files can both be open by kkdf2's Map viewer. There should be a map folder in there.
## Post #44
- Username: sotiris
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Feb 27, 2011 6:17 am
- Post datetime: 2011-06-11T11:49:56+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

Hey Guys,
i have just recored a video of my game and uploaded it on youtube
[http://www.youtube.com/watch?v=oWHtLphlwHQ](http://www.youtube.com/watch?v=oWHtLphlwHQ)

tell me your opinion ( if you want ).

PS
I will continue the development the next year.
## Post #45
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-06-11T20:02:59+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

You reanimated Sora. That definitely takes a lot of work. I can't wait to see what other things you have in store for this game.
## Post #46
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-07-01T12:04:06+00:00
- Post Title: Re: Kingdom Hearts Game Project Replica

me too. completely interested!
