## Post #1
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2015-11-23T20:55:46+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

hello, i have files from F.E.A.R Online , the files are in ".arch01" and i used Arch Extractor(Fear 2 tool) to extract them and got .mesh, .mdl, .tex files for each models 

but the problem is i can't use programs(that support .mdl) including Noesis to open\view these .mdl at all (i get error or crash on them), i would like to ask if anyone know how to open these files 

    here is 1 of the models from the game , i have no idea what model is this since i can't open it
mega:///#!IBsCDBKL!lS5R5fCfEFrWZoV5tlFSqLW8F_OkNEfSDfaMmgKn5Fk

    thank you
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-24T07:12:44+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

.tex files are .dds files just delete first 12 bytes and any tool for .dds images will open them (just rename .tex to .dds) .mdl is skeleton and .mesh is actual model. If no one is working on this already, I'll make a maxscript for model import
[http://s8.hostingkartinok.com/uploads/i ... f7c1e9.jpg](http://s8.hostingkartinok.com/uploads/images/2015/11/2e3eebb8185fa5db3eeebda930f7c1e9.jpg)
## Post #3
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2015-11-24T07:19:12+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

zaramot ....

 THANK YOU SO MUCHHHHH <333

i made a thread at facepunch first but people directed me here because it seems like nobody there has managed to open FEAR mesh before because it's hard to do it, this would be perfect for people who would love to work with FEAR 2 \ FEAR Online models

thank you sir!
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-24T09:10:38+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

Stuff is going pretty well, can you send me more models? Characters, no textures if it's not hard
## Post #5
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2015-11-24T09:38:51+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

mesh only yes? okay give me sometimes, i will extract and upload them, lucky that they arn't so big 

you are superb!
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-24T09:54:10+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

.mdl files (skeleton) would be nice too.  I'm implementing rig support (bones+weights), because who wants static models, right?
## Post #7
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2015-11-24T11:06:33+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

thank you so much zaramot,i wish i could give you something in return for doing all these,i have a lot of models(mostly games,mmd) i've been collecting and some ripped myself  in case you are looking for any specific ones

and here is the models i would like first , i would upload more but i don't really want to disturb you much so i picked just some
[https://mega.nz/#!FANj2Zbb!WuFssbvPiq_L ... xb8qSMDfnc](https://mega.nz/#!FANj2Zbb!WuFssbvPiq_LXmX00xmLt6slCpIGEkcTsxb8qSMDfnc)

there are 3 male and 4 female characters ,6.3mb overall , hope its not too much ^^

thank you again!!!! 

ps. if you see any models you would like in fear online, i will be happy to look for it and send right away! 
from here for example:
[http://fear.wikia.com/wiki/Category:F.E ... characters](http://fear.wikia.com/wiki/Category:F.E.A.R._Online_characters)
ps2. if you don't have much time, its ok for the rigging part, i feel bad enough to have you work on the model alone xD
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-24T13:46:00+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

Hi guys! Here's maxscript to import F.E.A.R Online PC models with bones+weights (3ds max 2009-2014). Script is "fresh" lol, so feel free to test it and send bug-reports here!
## Post #9
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2015-11-24T15:22:24+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

it works flawlessly! i can open it just fine with your work on rig, also exported as .obj and open in blender perfectly fine as well

thank you so very much Zaramot! i'm gonna post this back in my thread on [facepunch](https://facepunch.com/showthread.php?t=1494691&p=49178130#post49178130) just in case, wish i could do something for you man, as i said, if you need anything you can pm me anytime!!!
## Post #10
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-24T21:11:30+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

Here to report some bugs.

For me, this script only seems to work with models that banlu uploaded as test samples. Any other model I attempt, and the script hangs and Max crashes. I've tested it with Max 10 and Max 13. At first, I thought this was a problem with the way that I extracted the models. I initially used Dragon UnPACKER for the .arch01 files. But that wasn't it. I then extracted it with the Archextractor, and most models still didn't work. I tried it with "Assassin," which was included in the sample files, and it worked, but it wouldn't with anything else.

Even stranger, I was able to import a head mesh from one of the models not included in the test files, but none of the rest of the body.

On a positive note, this script works with FEAR 2 models. The Assassin model is from that game. This script could also potentially work with Condemned 2: Bloodshot models as well. I think they're the same file type, running on the same version of the same engine.
## Post #11
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2015-11-24T22:13:26+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

mmm yes, the 7 models in the "picked.rar" work perfectly fine but now that Dxfan619 mentioned it, i have tried other models and 3dsmax freeze on importing those as well

but its awesome though those 7 models were my most wanted
## Post #12
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-24T22:30:18+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

> Reply from banlu
>
> mmm yes, the 7 models in the "picked.rar" work perfectly fine but now that Dxfan619 mentioned it, i have tried other models and 3dsmax freeze on importing those as well

but its awesome though those 7 models were my most wanted

Good to know it wasn't only me, haha.

I'm pretty interested in what I found in some of the Alma files. Two different textures for Alma models that aren't in either FEAR game. Caught my eye very quickly. 

But it really is very good that there's progress on this. Back in 09', and 2010, this format wasn't extractable at all.
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-25T09:29:11+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

Feel free to post here (or maybe better in PM?) files which doesn't work. Also, you can send FEAR 2 models, I will try to make script compatible or separate script for this game too. It's a common thing for a MMO to have a lot of file variations, some tiny differences but they means a lot during import
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-26T17:00:47+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

Updated script, should import more models.

EDIT: Tiny fix with Alma model
[FEAR_Online.7z](https://xentaxbackup.github.io/file/10077_FEAR_Online.7z)
## Post #15
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-26T22:25:24+00:00
- Post Title: F.E.A.R Online models (+attach file, can't open .mdl&.tex)

> Reply from zaramot
>
> Updated script, should import more models.

EDIT: Tiny fix with Alma model

Updated script has worked flawlessly so far, very big thanks. Will try this out on Condemned 2 models as soon as I can and report back.
## Post #16
- Username: banlu
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 21, 2015 5:15 am
- Post datetime: 2015-11-27T12:07:26+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

thank you very much zaramot really
## Post #17
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-11-27T19:40:02+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

> Reply from zaramot
>
> Updated script, should import more models.

EDIT: Tiny fix with Alma model

Omg thanks so much   Works perfect on the models i tried so far!

Would you have any interest in FEAR 1 models? The format looks a bit similar to this one (models and skeletons seem to be in the same file tho)
## Post #18
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-27T21:20:58+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

No problem  I'm glad it's working, don't know about FEAR 1, I guess models are low quality there? I'll be more interested maybe in FEAR 3?
## Post #19
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-28T08:34:35+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

> Reply from zaramot
>
> No problem  I'm glad it's working, don't know about FEAR 1, I guess models are low quality there? I'll be more interested maybe in FEAR 3?

The FEAR 3 models are in .dspack files, and I'm not sure anyone ever managed to open those. Would upload a sample but I don't have the game anymore. Speaking purely by polycount, FEAR 3 has superior models, but the FEAR 3 models actually have lower resolution textures than the FEAR models. FEAR models may be easier to open also because they use the same engine as FEAR 2 and FEAR Online. I believe FEAR 3 runs on the Despair Engine.
## Post #20
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-11-28T11:42:35+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Yeah, .dspack Archives are compressed as far as i know and noone ever did a tool/script to unpack them. The FEAR 3 textures are pretty horrible to say the least xD 

Well from either FEAR 1 or 3 i can provide samples =) Or give you the games on steam if you have steam.
## Post #21
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-28T12:00:59+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

I do have steam, but no need to give those games   Thanks a lot for offer anyway!   Well, I guess I'll take a look at FEAR 1 then. Also, what about Condemned 2? This game have nice models? 

P.S. Also, I made script for two MMO's month ago, forgot their names lol they used .arch00 too and .model00p/.mesh00p for models/skeleton. It seams like they similar to FEAR?
## Post #22
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-28T17:36:48+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

> Reply from zaramot
>
> I do have steam, but no need to give those games   Thanks a lot for offer anyway!   Well, I guess I'll take a look at FEAR 1 then. Also, what about Condemned 2? This game have nice models? 

P.S. Also, I made script for two MMO's month ago, forgot their names lol they used .arch00 too and .model00p/.mesh00p for models/skeleton. It seams like they similar to FEAR?

FEAR uses .model00p for models, but I don't recall seeing any .mesh00p files. There's another file type in there as well, but I don't remember what it is.

Do you need samples? I can upload some, or if you have FEAR on Steam, you can install the SDK that comes with the game, which unpacks all of the game's contents.

There are actually a few models in the FEAR files that went unused in the game, and haven't been seen by many people.

Edit: Condemned 2 models are basically the same quality as the models from FEAR 2/FEAR Online. I think they may have even been modeled by the same person. Sorry I haven't gotten any samples yet. Acquiring the game has proven a tad difficult.
## Post #23
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-28T18:43:10+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Ah, so FEAR do using model00p!   I didn't expect those MMO's will be exact same as FEAR 1, since those game are from 2014-2015 still in open betas, but definitely a variations of FEAR 1 format. I don't have any FEAR game on steam, actually my steam account almost empty - only few games. I will gladly start to work on Condemned 2, because from screens I saw the game is better quality than FEAR 1/2, take your time I could wait for samples xD
## Post #24
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-28T19:36:26+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

> Reply from zaramot
>
> Ah, so FEAR do using model00p!   I didn't expect those MMO's will be exact same as FEAR 1, since those game are from 2014-2015 still in open betas, but definitely a variations of FEAR 1 format. I don't have any FEAR game on steam, actually my steam account almost empty - only few games. I will gladly start to work on Condemned 2, because from screens I saw the game is better quality than FEAR 1/2, take your time I could wait for samples xD

Amazing, will start gathering samples soon!
## Post #25
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-11-30T21:51:14+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Updates and samples ahoy.

FEAR 1 models are in Model00p format as I mentioned before.

Condemned 2 presented a challenge. None of the available FEAR tools that I know of worked in opening the .arch02 format that most of the files are in. Quickbms extracted them though, so that was solved. While many of the formats that are present from FEAR 2, such as .bndl and .tex, are also present in Condemned 2, the FEAR 2 tools from here don't work in extracting them. In addition, instead of .mesh, and .mdl like FEAR Online and FEAR 2, Condemned 2 just has .mdl files. Or, at least that's all I've found. I think there may be .mesh files, but I haven't found them. The Condemned 2 texture files are located in .bndl files, but the FEAR 2 .bndl tools won't extract them.

FEAR/Condemned 2 model samples:

[http://www.mediafire.com/download/5rykh ... amples.rar](http://www.mediafire.com/download/5rykhne9x5u993j/FEAR+and+Condemned+Samples.rar)

Here are the tools that were used to open FEAR 2 and FEAR Online files, in case looking at those may help.

[viewtopic.php?f=32&t=3989](http://forum.xentax.com/viewtopic.php?f=32&t=3989)

I also found an old blog from one of the Condemned 2 developers. This is what the models look like, in clearer pictures than just screenshots from the game.

[http://tinybonehands.blogspot.com/2008/ ... s.html?m=1](http://tinybonehands.blogspot.com/2008/03/condemned-2-3d-models.html?m=1)

I have a feeling there may be a need for more Condemned 2 samples. There's about 4.32 GB of content stored within the .bndl files of the game. If there's a need, I can upload them.
## Post #26
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-01T09:39:23+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Thanks a lot for samples
## Post #27
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2015-12-01T09:43:25+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

I think Condemned 2 .mesh files may be in the .bndl files too. I had to extract a couple of them to get meshes from FEAR2 so it may be very similar.
## Post #28
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-01T17:37:21+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Yes, Condemned meshes are in .bndl containers. DXFan619 Condemned 2 samples were from PC version of the game? For now I'm finishing FEAR 1 script (format is much more annoying than FEAR2/Online because skeleton and model in one file, and skeleton is a total mess lol). Then, I'll try to solve Condemned 2, maybe find a way to extract .bndl
## Post #29
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-12-01T18:14:01+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

> Reply from zaramot
>
> Yes, Condemned meshes are in .bndl containers. DXFan619 Condemned 2 samples were from PC version of the game? For now I'm finishing FEAR 1 script (format is much more annoying than FEAR2/Online because skeleton and model in one file, and skeleton is a total mess lol). Then, I'll try to solve Condemned 2, maybe find a way to extract .bndl

Condemned 2 was exclusive to the 360 and Playstation 3. I have the 360 version, so that's where the files are from. I figured that the .mesh files were somewhere else and had to exist because the "models" directory of all the unpacked Condemned 2 contents is less than 10 mb. It only contains the .mdl files. Despite using the same formats as FEAR 2, I guess they were packed and encrypted differently. Aluigi's QuickBMS script for Condemned 2 worked in unpacking the .arch02 files though.
## Post #30
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-02T00:01:55+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Ah, okay - thanks for the info   I think I'll try PS3 version. As I understand FEAR bms script should extract files nicely from there. Even if not, it will be mush easir to deal with textures from PS3 than from Xbox-360
## Post #31
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-12-02T00:07:09+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

> Reply from zaramot
>
> Ah, okay - thanks for the info   I think I'll try PS3 version. As I understand FEAR bms script should extract files nicely from there. Even if not, it will be mush easir to deal with textures from PS3 than from Xbox-360

Ah, cool. There was one or two .tex files outside of the contents of the .bndl files that I tried converting. The FEAR 2 .tex converter was the only one that worked, but I can't seem to open the .dds file that it extracted. You want to take a look at it just in case?
## Post #32
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-04T13:16:05+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

I have some news, good news   I managed to extract PS3 version of the game Condemned 2, .arch2 and .bndl too. Actually I'm finishing model-import script, also I did noesis plugin for .tex images
## Post #33
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-12-04T16:16:15+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

> Reply from zaramot
>
> I have some news, good news   I managed to extract PS3 version of the game Condemned 2, .arch2 and .bndl too. Actually I'm finishing model-import script, also I did noesis plugin for .tex images

Wow, incredible work as always. Are PS3 games universally easy to rip from? I always thought it was the 360 that was easier.
## Post #34
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-04T20:16:24+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Well, there are PS3 games which are almost impossible to get model from, so I can say PS3 harder (though, most of them are same as Xbox-360 in "hardness" to reverse them )
## Post #35
- Username: alvares89
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2016 5:36 pm
- Post datetime: 2016-01-22T09:54:48+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Hi friends, there is news about the opening models of FEAR 2? I myself do modifications to the first part, and added to the editor weapons and characters from add-ons, except for some trifles and shortcomings, I would like to help create their own effects.
## Post #36
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-03-14T23:18:58+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

I have tried extracting some models from fear 2 using this script and the results have been.... weird to say the least....
Most models fail to open, the ones that do open are something completely different from what their name indicates.
## Post #37
- Username: alvares89
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2016 5:36 pm
- Post datetime: 2016-03-15T03:02:20+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

It is interesting that you got?
## Post #38
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-03-15T09:43:04+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Yes, show a picture of what you got. And maybe attach sample of files which imported as complete mess?
## Post #39
- Username: alvares89
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2016 5:36 pm
- Post datetime: 2016-03-15T09:54:17+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

It would be nice.
## Post #40
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-03-15T17:03:58+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

My uploader is not working, so I won't be able to share files. Damn it....
The models that do extract work fine, it's just that the model that comes out is unrelated to it's actual name.
Most models simply do not load and give an integer error.
I will post again when my uploader goes back to working. Currently bogged down with the md5r files from wolf 2009.
## Post #41
- Username: alvares89
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2016 5:36 pm
- Post datetime: 2016-03-15T17:07:26+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

I will wait impatiently))
## Post #42
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-03-15T23:54:34+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

The textures are having similar problems. It seems the arch and bndl extractors screwed up the filenames.
## Post #43
- Username: alvares89
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2016 5:36 pm
- Post datetime: 2016-03-16T02:35:59+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

We'll have to choose manually)
## Post #44
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-03-16T20:03:04+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Well, if you trying to import levels or static objects/maybe even weapons it could crash. This script mostly for characters (since I've had only character samples, and people wanted characters). If you having problems with characters, then upload them here
## Post #45
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-03-16T23:02:32+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

It was weapons I was trying to extract. It is being problematic due to the filenames being messed up.
I will fall back on ninjaripper extraction for now. Need to figure out the .md5r and a8.dds files from wolfenstein 09 first. Thanks anyway.
## Post #46
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-03-21T23:34:10+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Okay, ninjaripper extraction is going well, but there is something I am missing.
The original assault rifle model, with a front post sight and the pistol with a laser sight, both of which were cut from the full game but still exist in the game files.
[http://vignette2.wikia.nocookie.net/fea ... 1223225116](http://vignette2.wikia.nocookie.net/fear/images/8/80/Beckett.jpg/revision/latest?cb=20081223225116)
As seen on this picture.
Since the models have been renamed however, finding them might be a problem.
I will continue going through the game files and searching, if someone can help me get this model, that would be great.
## Post #47
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-03-27T15:04:27+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Having a problem with this (supposed) character mesh: It refuses to open giving an integer error.
[http://www.mediafire.com/download/h1715 ... light.mesh](http://www.mediafire.com/download/h1715nx2ymaa1pn/mp_atc_light.mesh)
Every file in the same folder that I did manage to open was a character model so this one should be too.
If someone can open this it would be quite helpful, although I understand if no one wishes to do it.
## Post #48
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-04-02T10:30:08+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Here's another sample:
[http://www.mediafire.com/download/wrf02 ... /grunt.rar](http://www.mediafire.com/download/wrf021axxwkk05u/grunt.rar)
## Post #49
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-04-18T17:14:34+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Just wanted to ask if there was any progress. If it is necessary, I can provide another sample.
## Post #50
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-19T08:30:39+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

doesn't look like a matter of more samples, it's more a matter of lost interest, I guess  

anyway, here's my tries, the lod0(?) model on the right side is spoiled - you're on your own to fix it using the H2O file as a base:



grunt.jpg (111.91 KiB) Viewed 162 times


H2O, lod0:

0x73518 3246
Vb1
64 99
0x2A508 2218
020000
0x0 255
## Post #51
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-19T10:05:54+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Yes, I lost interest in this one. Well, to say true it was my mistake, this thread was originally about FEAR online models, so I shouldn't try to merge support for fear 2 and fear online in one script, when someone asked me about this. This's not the case, fixing something for fear 2 I'll brake something in fear online and vice versa. If you want this "grunt" model really bad you can use this script, maybe it will even work with some other F2 models. Aslo, mp_atc_light.mesh file which you attached in previous post is animation file, so I edited script to make it skip none model files, just nothing will happen on import xD
[FEAR_2_GRUNT.7z](https://xentaxbackup.github.io/file/10798_FEAR_2_GRUNT.7z)
## Post #52
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-04-19T14:04:40+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Thanks guys, problem is that the arch extractor messed up the files and gave everything wrong names so I do not even know if they files I am uploading are the right ones, which is quite aggravating.
## Post #53
- Username: Akramma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 12, 2018 3:43 am
- Post datetime: 2020-04-30T08:19:15+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

Hello, I just wanted to know how can I open a .tex file exactly, Idk how to delete the 12 bytes you meant in the first page :c

Also I found the Beta Delta Force model from Project Origin E3 but I cant do anything on it, the highpoly is messed up and only the low poly shows.

[https://drive.google.com/open?id=1L2IzZ ... 9zP9xRt8im](https://drive.google.com/open?id=1L2IzZB00_2HyzhtVwHPaeQ9zP9xRt8im)
## Post #54
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-05-19T02:15:04+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

> Reply from Akramma ↑Thu Apr 30, 2020 4:19 pm at Thu Apr 30, 2020 4:19 pm
>
> Hello, I just wanted to know how can I open a .tex file exactly, Idk how to delete the 12 bytes you meant in the first page :c
here is Noesis python script to open those tex files without having to delete bytes.  


 tex_FEAROnline_tex.zip
(516 Bytes) Downloaded 27 times
## Post #55
- Username: Akramma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 12, 2018 3:43 am
- Post datetime: 2020-08-01T09:55:48+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

hello again, I was wondering if there is any way to import this to 3ds max, I tried with the script but there is only bad polygons :c 

[https://drive.google.com/file/d/18JxE8Z ... sp=sharing](https://drive.google.com/file/d/18JxE8Zy9zCkx621BMnT5j9e3cd5gfNmM/view?usp=sharing)
## Post #56
- Username: hunter123520
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 24, 2020 12:40 am
- Post datetime: 2020-08-24T23:01:02+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

hello could any one help me in how to open the model00p and world00p from run and fire  game ( i tried the fear tools but it dosent work for me ) 
 here  is the  files i want to open please if any one could help me i will be glade to him thats so important to me
## Post #57
- Username: hunter123520
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 24, 2020 12:40 am
- Post datetime: 2020-08-25T12:23:46+00:00
- Post Title: Re: F.E.A.R Online models (+attach file, can't open .mdl&.te

[http://www.mediafire.com/file/1ph4lfq90exla80/file](http://www.mediafire.com/file/1ph4lfq90exla80/file)
