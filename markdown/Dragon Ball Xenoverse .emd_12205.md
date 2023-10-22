## Post #1
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2014-11-07T16:20:33+00:00
- Post Title: Dragon Ball Xenoverse *.emd

I wrote this maxscript not too long ago for Dragon Ball Xenoverse and everything is just about done but I can't get the weighting right. I've never done weighting before and don't have much for a reference. I could need some help here. If anyone could look over the code and tell me what I'm doing wrong, the help would be very much appreciated.



I've listed a couple example files and scripts.
[example files.rar](https://xentaxbackup.github.io/file/8048_example files.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-08T11:05:43+00:00
- Post Title: Dragon Ball Xenoverse *.emd

well, some vertices simply don't move when moving a bone.
So they have a weight's sum of 0.0 what they shouldn't.

Could be possible that there's a VertexID to be read from the model file.

Also the sum of weights is > 1.0 for 688 of 2062 vertices of the upper body.
But this problem should vanish as soon  as the first one is  solved.

btw: nice scripts, great work!:) (the weighting part is borrowed from someone else?)

edit: didn't find VerticeIDs. But it's strange that many vertices have boneID 1 assigned more than once.
So I tried using boneid (instead of boneid + 1) and if (bonex != 0) then
but with no luck.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-08T11:58:11+00:00
- Post Title: Dragon Ball Xenoverse *.emd

can you send his textures also?
## Post #4
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2014-11-09T03:12:51+00:00
- Post Title: Dragon Ball Xenoverse *.emd

VertexID? I'm sorry I don't understand. Anyways thanks, my scripts are often a frankenstein of various other scripts I find. The textures are in EMB archives, the same as the SF4 games. I was able to get the raws from sf4 asset explorer but it turns out they happen to be dds files with a modified header.

[http://www.mediafire.com/download/2j6zg ... xtures.rar](http://www.mediafire.com/download/2j6zg79mls96chg/Textures.rar)
## Post #5
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-14T10:00:44+00:00
- Post Title: Dragon Ball Xenoverse *.emd

> Reply from killercracker
>
> VertexID? I'm sorry I don't understand. Anyways thanks, my scripts are often a frankenstein of various other scripts I find. The textures are in EMB archives, the same as the SF4 games. I was able to get the raws from sf4 asset explorer but it turns out they happen to be dds files with a modified header.

http://www.mediafire.com/download/2j6zg ... xtures.rarThis game is very classic, hope someone can modify the script error. Support
## Post #6
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-29T17:27:03+00:00
- Post Title: Dragon Ball Xenoverse *.emd

> Reply from killercracker
>
> I wrote this maxscript not too long ago for Dragon Ball Xenoverse and everything is just about done but I can't get the weighting right. I've never done weighting before and don't have much for a reference. I could need some help here. If anyone could look over the code and tell me what I'm doing wrong, the help would be very much appreciated.



I've listed a couple example files and scripts.Hello, my friend, I tested all your files very well, since I don't have this game so I cannot test the model file. You can upload this game download links
## Post #7
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2015-01-24T01:39:11+00:00
- Post Title: Dragon Ball Xenoverse *.emd

Finished the .emd files with bones and weights but only having problems with the .emo files. For some reason they have more than one bone matrix, the second one without any bone id's that I could find, so that's one more obstacle to overturn. I've also linked the script for anyone who wants it to play with or add on too. Hopefully after all of this I'll have gained enough knowlege to figure out the animation.



[https://www.mediafire.com/folder/rdm1lq ... se_project](https://www.mediafire.com/folder/rdm1lq0om7oa4/Xenoverse_project)
## Post #8
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-01-24T16:20:26+00:00
- Post Title: Dragon Ball Xenoverse *.emd

> Reply from killercracker
>
> Finished the .emd files with bones and weights but only having problems with the .emo files. For some reason they have more than one bone matrix, the second one without any bone id's that I could find, so that's one more obstacle to overturn. I've also linked the script for anyone who wants it to play with or add on too. Hopefully after all of this I'll have gained enough knowlege to figure out the animation.



https://www.mediafire.com/folder/rdm1lq ... se_projectHi killercracker My friend, thank you very much for the great work. Dragonball z has always been my favorite
## Post #9
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-02-28T17:00:40+00:00
- Post Title: Dragon Ball Xenoverse *.emd

> Reply from killercracker
>
> Finished the .emd files with bones and weights but only having problems with the .emo files. For some reason they have more than one bone matrix, the second one without any bone id's that I could find, so that's one more obstacle to overturn. I've also linked the script for anyone who wants it to play with or add on too. Hopefully after all of this I'll have gained enough knowlege to figure out the animation.



https://www.mediafire.com/folder/rdm1lq ... se_project

Does this support pc version??
## Post #10
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2015-03-02T02:52:49+00:00
- Post Title: Dragon Ball Xenoverse *.emd

Just tested the script on freshly extracted PC files (from the pc verison) here is the error I get:

It works on the files you provide in your mediafire.
I've been wondering if there is a way to convert them back after we're done in 3Dsmax.
## Post #11
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2015-03-04T06:44:55+00:00
- Post Title: Dragon Ball Xenoverse *.emd

Is it possible to not only import, but also re-import back to the original format of the game?
In any case thank you for spending so much time on this!
## Post #12
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2015-03-04T17:41:04+00:00
- Post Title: Dragon Ball Xenoverse *.emd

Apparently he uploaded a script for PC models, there are still some models that don't load though (--unable to convert: undefined to type: integer)  ,but it works for most of them, at least I can do some models.
Now when importing one .emd it imports a whole set of models (other .emd) at once, is this normal?
## Post #13
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2015-03-07T09:43:23+00:00
- Post Title: Dragon Ball Xenoverse *.emd

Hi to all!
Great work with the importer!

I'm having problems importing some parts from the PC files, for example I can't load the Piccolo's cape, am I doing something wrong or the script isn't complete?
## Post #14
- Username: PGV
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 03, 2013 11:24 pm
- Post datetime: 2015-03-07T15:41:05+00:00
- Post Title: Dragon Ball Xenoverse *.emd

you did a great job in there, but as you were able to make an import everybody here would appreciate an .emd meshes EXPORT SCRIPT, so that we can isert in game our creations.

I know I'm asking a great effort, but you would make happy hundreds thousands of people...

It shall be able to generate

-.emd (for 3d model mesh)
- .emb (for texture)
- .esk (for structure and position I think)
- .emm (no idea what it is exactly)

The .esk of addon objects (such as hats, wings etc) for the characters are different than the .esk you provided (of a full model) in the sample pack, and your script won't read them sadly...
## Post #15
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-03-07T16:29:51+00:00
- Post Title: Dragon Ball Xenoverse *.emd

> Reply from PGV
>
> you did a great job in there, but as you were able to make an import everybody here would appreciate an .emd meshes EXPORT SCRIPT, so that we can isert in game our creations.

I know I'm asking a great effort, but you would make happy hundreds thousands of people...

It shall be able to generate

-.emd (for 3d model mesh)
- .emb (for texture)
- .esk (for structure and position I think)
- .emm (no idea what it is exactly)

The .esk of addon objects (such as hats, wings etc) for the characters are different than the .esk you provided (of a full model) in the sample pack, and your script won't read them sadly...

emm is material, xenoverse is using the same engine as SFIV. The pc script also has a little issue with uv mapping, uv's are too big.
## Post #16
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2015-03-07T17:22:52+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

[https://github.com/DarioSamo/LibXenoverse](https://github.com/DarioSamo/LibXenoverse)
## Post #17
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2015-03-08T20:37:18+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

Didn't think anybody had an interest in the game. Some body parts of the model have their own skeleton. Right now I'm reworking the script so that it loads both models and skeleton without crashing. If you want the hair and other stuff to appear you need to delete the two " and TestLodType != "scd" " and turn loadskel to false. But then the model wont have any skinning. Also can I have some example models for the pc version. Sorry I should of tested it more.
## Post #18
- Username: XZTopazZX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 05, 2015 4:00 am
- Post datetime: 2015-03-09T06:53:37+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

The first link is a model that opens fine with the script, while the second gets the integer error with the same script

[http://www.mediafire.com/download/734f7 ... e_base.emd](http://www.mediafire.com/download/734f72hp1k20zz1/HUM_004_Face_base.emd)


[http://www.mediafire.com/download/onnix ... 8_Rist.emd](http://www.mediafire.com/download/onnixgvmg81me2t/HUM_518_Rist.emd)
## Post #19
- Username: Dario ff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 01, 2012 6:48 am
- Post datetime: 2015-03-09T23:27:00+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

> Reply from PGV
>
> It shall be able to generate

-.emd (for 3d model mesh)
- .emb (for texture)
- .esk (for structure and position I think)
- .emm (no idea what it is exactly)
Tools for generating/exporting all of these are in my repository here [https://github.com/DarioSamo/LibXenoverse](https://github.com/DarioSamo/LibXenoverse), except for the esk file. I have a parser for it but didn't do a importer/writer yet.

The EMMs however are pretty annoying to edit as they're highly dependent on the textures in dyt.emb and regular emb. (One of the parameters in each material seems to be an index to the row in dyt emb). The material name must be in the matching EMM for the EMD for it to be used.
## Post #20
- Username: basara669
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 06, 2012 3:58 pm
- Post datetime: 2015-03-15T01:07:35+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

as work with file emd in blender or 3dsmax
## Post #21
- Username: dirtypantsdan
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 03, 2012 3:33 am
- Post datetime: 2015-03-17T00:53:54+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

By the way is there anyway to get to the DLC model files yet? Using the extractor all I get is a .bac on Pan's folder it seems.
## Post #22
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-03-17T03:25:02+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

> Reply from dirtypantsdan
>
> By the way is there anyway to get to the DLC model files yet? Using the extractor all I get is a .bac on Pan's folder it seems.

For 360 files, you can get her using noesis extractor.
## Post #23
- Username: dirtypantsdan
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 03, 2012 3:33 am
- Post datetime: 2015-03-17T18:29:12+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

Thanks for the Suggestion Darko, unfortunately I tried this using Noesis on the 360 version, as well as uncompressed through Critools, and I still just get the .bac. Are you able to see them?

Now I'm starting to think maybe her files are made from custom character assets somehow. :-0
## Post #24
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-03-17T19:31:27+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

> Reply from dirtypantsdan
>
> Thanks for the Suggestion Darko, unfortunately I tried this using Noesis on the 360 version, as well as uncompressed through Critools, and I still just get the .bac. Are you able to see them?

Now I'm starting to think maybe her files are made from custom character assets somehow. :-0

¿You want Pan?
## Post #25
- Username: dirtypantsdan
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 03, 2012 3:33 am
- Post datetime: 2015-03-17T21:06:45+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

Sure, If it's not too much trouble. I primarily wanted to use the model for sfm,I have 3D studio, even if it has weighting issues I can try to add new ones entirely myself. :0
## Post #26
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-03-18T03:30:37+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

> Reply from dirtypantsdan
>
> Sure, If it's not too much trouble. I primarily wanted to use the model for sfm,I have 3D studio, even if it has weighting issues I can try to add new ones entirely myself. :0

Ready, she's totally rigged:



Check your pm's
## Post #27
- Username: XZTopazZX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 05, 2015 4:00 am
- Post datetime: 2015-03-18T05:06:04+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

^ did you figure out the texture issue or did you add materials yourself for the pan model?
## Post #28
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-03-18T14:48:09+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

> Reply from XZTopazZX
>
> ^ did you figure out the texture issue or did you add materials yourself for the pan model?

I used the ramps in the dty files to get the color and then I just edited and cleaned the black textures in photohop and applied that color.
## Post #29
- Username: LoreMX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 14, 2015 4:30 pm
- Post datetime: 2015-07-14T08:38:37+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

I'm new to this site, but I just have to ask.
Has anymore progress been made with extracting the models? These models are WAY better done then the ones from all the other Dragon Ball games.
## Post #30
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-26T21:26:14+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

many thanks for the wonderful work guys, I have a question, is possible check files from game Saint Seiya Soldiers Soul (PS3)? it used same format of game, but script no work, after try load emo files, got error can covert type integer64.
## Post #31
- Username: Justdragos
- Rank: advanced
- Number of posts: 69
- Joined date: Tue Feb 21, 2012 3:19 pm
- Post datetime: 2017-03-01T22:20:42+00:00
- Post Title: Re: Dragon Ball Xenoverse *.emd

Hello. Can somebody help me. I managed to unpack the .cpk files. But how can i import the models with the bones?
