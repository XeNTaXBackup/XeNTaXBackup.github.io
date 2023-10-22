## Post #1
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-03T20:57:48+00:00
- Post Title: FFX models

Hey everybody,
I am trying to get the models from Final Fantasy X into 3ds max... and I am having no luck whatsoever. I have all the models in their original format, .ffm, and I have several programs that view the models and animations (yaz0r's ffx viewer, Chargeur FFX viewer) and supposedly export them into a format useable in 3ds max (ffm2obj, which exports to .obj) and (Chargeur FFX viewer, exports to .dae) 
The problem is, these programs do not export textures properly. they come out washed out, or glitchy, or pixellated. 
Also, the models themselves have incorrect UV mapping. 
The .ffm model files contain textures, animations, and the mesh itself. 
Can someone help me get some models into 3ds max?
I am specifically working with the high res model of Lulu, and perhaps Auron.
Thanks!
## Post #2
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-03T22:18:31+00:00
- Post Title: FFX models

They work fine. Are you sure your using the correct importer for 3ds max?
## Post #3
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-04T19:11:40+00:00
- Post Title: FFX models

I am using the standard FBX collada importer for 3ds max, I know there is a better one, but it doesn't explain the damaged textures. Can you help me fix the texture problem?
Thanks
## Post #4
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2011-02-04T22:14:33+00:00
- Post Title: FFX models

The textures are fine, they are some weird palette type textures.


If the textures look anything like this then they are fine.

ah nostalgia, FFX was the first game I ripped models from
## Post #5
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-05T01:24:23+00:00
- Post Title: FFX models

Wait, so your saying the textures are supposed to look all wacky and demented?
Hmmm... What importer did you use?   the importer I used gave me a model with screwy UV mapping, and it didn't autoload the textures... I had to texture it manually.... that sucked...

EDIT: I tried other collada importers- none of them auto texture the model, and none change the fact that the model's UV mapping is wrong. Please tell me how you got this to work, because I am out of ideas. I tried to contact the creator of Chargeur FFX viewer, but he ignored me.
## Post #6
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-07T00:41:57+00:00
- Post Title: FFX models

I also got the same odd looking textures, but when I imported the dae file into max9, it worked all right (for the most part.)
If 3dmax isn't autoloading the textures, check to see what it thinks the texture filenames and locations are. The dae file I had was looking for textures named texture_1.tga (etc), in the root folder with the model.

The textures looked odd in preview mode at times, but they rendered fine (although it looks like I'm having a bit of an issue with transparency)

the uv's also seemed okay on mine.
## Post #7
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-08T19:02:36+00:00
- Post Title: FFX models

Hmmm... I think my computer has issues, that seems to be the most common problem I have. Ice, could you perhaps export the models of Lulu and Auron in your version into Max and post them for me? (High Res models, with the textures) I think my computer is just too screwed up for me to really make this work. If you could do that, that would be awesome. Thanks
## Post #8
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-09T01:03:34+00:00
- Post Title: FFX models

Sure your using the collada importer instead of the autodesk one? Easy mistake to make.
## Post #9
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-10T00:03:13+00:00
- Post Title: FFX models

> Reply from DarkScion
>
> Hmmm... I think my computer has issues, that seems to be the most common problem I have. Ice, could you perhaps export the models of Lulu and Auron in your version into Max and post them for me? (High Res models, with the textures) I think my computer is just too screwed up for me to really make this work. If you could do that, that would be awesome. Thanks

Oh, I know the woes of computer issues. I'd be happy to upload them in max format (as long as they came with chargeur, cause I don't have ffx - and I know everyone and their dog has that game, I'm lame.) 

It would be max format 9. I'll do that after I ragequit maya 2011 for the 20th time in the past half hour. Oh my God, I really really REALLY am trying to not HATE maya but every 2 minutes I get stuck on some stupid simple thing that i KNOW how to freaking do in max 9 and how the hell do I simply edit vertex weights for bones I really really freaking miss my modifier stack this node thing is confusing as heck blah blah blah. 

Sorry, I just had to rant about my maya woes somewhere and none of my friends would have any clue what the heck I'm even talking about.
## Post #10
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-10T04:07:19+00:00
- Post Title: FFX models

Hmmm...  a fellow Max user, eh? thats awesome. The high res model of Lulu does not come with Chargeur- I will upload it to megaupload and post it for you, maybe you will have better luck exporting it. Thanks for your help so far, this might be the big breakthrough for me, seeing as I have been trying to do this for years.
## Post #11
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-10T19:26:05+00:00
- Post Title: FFX models

> Reply from DarkScion
>
> Hmmm...  a fellow Max user, eh? thats awesome. The high res model of Lulu does not come with Chargeur- I will upload it to megaupload and post it for you, maybe you will have better luck exporting it. Thanks for your help so far, this might be the big breakthrough for me, seeing as I have been trying to do this for years.

You sound like me with kingdom hearts models.   I've been fiddling with them ever since yaz0r publicly posted his model viewer that let 3dripper rip them. 

I still don't understand why ffx, mdls and mldx models all export with a lot of bones/joints that have no affected vertices. It's confusing as heck. I think that the bones that have no affected vertices are usually ones higher up on the hierarchy, so they're used more as a control for the bones that follow (that usually do end up having affected vertices). So, if you move one of those that has no affected vertices personally, a large portion of the model still ends up moving as a consequence. Still, it's rather odd and confusing.
## Post #12
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-11T05:54:46+00:00
- Post Title: FFX models

I almost forgot about that... I recently reformatted and installed XP on my computer, so I should be able to use 3d ripperDX now. Hehehehehe... this will be awesome... Lulu, here I come...
## Post #13
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-13T00:48:24+00:00
- Post Title: FFX models

Nice... it worked. Thanks, Ice, I finally got the models I have been looking for
## Post #14
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-13T22:34:51+00:00
- Post Title: FFX models

Oh good. So you ripped them with 3dripper? if you use chargeur you can export them rigged though, which is such a gigantic advantage. I know yaz0r's viewer ends up distoring any KH or KH2 models that are ripped, so it probably does the same with ffx ones. In maya, you can fix the distortions (to KH models anyway) by scaling the model like this: x: 0.83 y: 0.558 z: -1
## Post #15
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-15T03:13:20+00:00
- Post Title: FFX models

I ripped them from yaz0rs viewer, and they came out great. The only problem is the "high res" models are not as smooth as they appear in the viewer (more blocky) because of how 3ds max's default camera lighting reflects off the various polygons... Ice, do you know a way to smooth the models? I have used meshsmooth and turbosmooth, but they don't work... some models I have come across don't accept smoothing well, there is a way to get around it, but I don't remember how.
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-15T03:19:50+00:00
- Post Title: Re: FFX models

weld the verts with a value of .001
## Post #17
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-15T20:24:32+00:00
- Post Title: Re: FFX models

NICE. Thanks, Chrrox, that worked.   Unfortunately, it screwed up the normals, but I managed to repair them.
## Post #18
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-16T00:30:49+00:00
- Post Title: Re: FFX models

Thanks Chrrox, I forgot about that bit of info too. Knew I should weld them to some value, but didn't remember which one. Whoops forgot to mention that part DarkScion. 

Something interesting - I've compared a low poly mdls model converted to fbx with chrissquarefan's converter to the same model ripped from yaz0r's viewer with 3dripper. the 3dripper one had 6,000ish verts or something (or maybe it was around 4,000 - can't remember.) the fbx one had like 2,000ish, I think. Then when I welded the 3dripper one, the vert number dropped to 1,000ish. So the 3dripper one went from having about triple the number of verts as the fbx one to having half as many. Hm. 

I think the 3dripper models can also have normal issues.
## Post #19
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-02-20T21:43:01+00:00
- Post Title: Re: FFX models

I have never had issues with 3dripper and normals, although recently I came across a strange error in which models ripped from a game appear transparent like glass in 3ds max... it really didn't make any sense. Anyway though, this worked out great, and now I have the Lulu model with smoothing. Machinima, here I come...
## Post #20
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-03-09T21:28:35+00:00
- Post Title: Re: FFX models

Now with new noesis is really easy export model, but I have some problem with texture!
In preview of noesis the texture are ok, but if I export I have 3 image file with different color, how I have to do?
## Post #21
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-03-10T17:02:35+00:00
- Post Title: Re: FFX models

> Reply from grotesque
>
> Now with new noesis is really easy export model, but I have some problem with texture!
In preview of noesis the texture are ok, but if I export I have 3 image file with different color, how I have to do?
For every texture-palette combination, Noesis just generates a separate texture image entirely. They should be automatically associated with the proper surfaces on export, but are currently not, because of a bit of a mess I've had going on with texture versus material names. That will be sorted out next release. For now you'll have to re-associate your textures with the appropriate materials in the model.
## Post #22
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-03-10T17:57:07+00:00
- Post Title: Re: FFX models

Ok, so I wait for next release 

EDIT:
New noesis work perfect, thanks Mr!
## Post #23
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-03-18T09:30:31+00:00
- Post Title: Re: FFX models

yeah, thanks MRadults
