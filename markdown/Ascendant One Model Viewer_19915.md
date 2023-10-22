## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-30T07:40:46+00:00
- Post Title: Ascendant One Model Viewer

Textures can be exported with umodel, but it doesn't work for models. So here is a tool for extracting skinned meshes. Material mapping and static meshes are not supported.

Tool overview and example exported model



How to use

Load

Model : Loads a single model file (.uasset).
Folder : Loads all .uasset files inside the selected folder, and combines them into a single model.
Export

NEXA : Exports the model in custom binary format (.nexa), intended to be loaded by Noesis. Noesis script for this format : Nexa Script
Note  : Models will be exported into the folder Export.
Download : [https://www.mediafire.com/file/5jrx8p1p ... 2.rar/file](https://www.mediafire.com/file/5jrx8p1p95eyp5t/AOViewer_Upd2.rar/file)
## Post #2
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2019-03-31T01:11:36+00:00
- Post Title: Ascendant One Model Viewer

hoe to extract file .pak ?
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-31T01:52:04+00:00
- Post Title: Ascendant One Model Viewer

> Reply from godskin ↑Sun Mar 31, 2019 9:11 am at Sun Mar 31, 2019 9:11 am
>
> 
hoe to extract file .pak ?
Noesis works fine.
## Post #4
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2019-03-31T03:25:24+00:00
- Post Title: Ascendant One Model Viewer

THANKS UR GOD
## Post #5
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-03-31T20:21:37+00:00
- Post Title: Ascendant One Model Viewer

Thank you for this! However after some testing I found that some of the bones (right now from what I've seen it's just in the face) get joined into one, I assume due to them not having proper bone names and it doesn't go past 099. Each of the parts that are moved with this bone in the example pic should be moved by their own bone (like eyelid upper 1/2, eyelid corner inner/outer and temple), the other side of the face works fine because they have numbers prior to 099. Hopefully this is easily understandable, the test character I used was Hera.
[Capture.JPG](https://xentaxbackup.github.io/file/15987_Capture.JPG)
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-31T20:43:24+00:00
- Post Title: Ascendant One Model Viewer

> Reply from TRDaz ↑Mon Apr 01, 2019 4:21 am at Mon Apr 01, 2019 4:21 am
>
> 
I assume due to them not having proper bone names and it doesn't go past 099.
Actually there should be proper bone names. Here is how exported Hera skeleton looks like for me.



So the bones shouldn't get numbered. Do you also have that problem when exporting a single mesh? Maybe try updating Noesis to the latest version. If it still doesn't work, send me a PM and I will take a look at your files.
## Post #7
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-03-31T21:02:34+00:00
- Post Title: Ascendant One Model Viewer

They are listed there in your screenshot as Bone_skin_001 etc, after 099 there is a single Bone_skin bone that combines some of the bones that should be separate into one weighted bone.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-31T21:37:50+00:00
- Post Title: Ascendant One Model Viewer

> Reply from TRDaz ↑Mon Apr 01, 2019 5:02 am at Mon Apr 01, 2019 5:02 am
>
> 
single Bone_skin bone that combines some of the bones that should be separate into one weighted bone.
I now get what you are saying, but that isn't something done by the tool or Noesis. There are indeed 100 "Bone_skin" bones in the original .uassset file with exactly those names, and weights are loaded same as any other bone. So there might either be some additional data used (maybe out of standard UE4 format) to fix the weights, or the face is actually skinned like that.

Still I will double check the loading procedure to make sure I am not misreading any data. I am not sure if I can find a solution to this though. Thank you for reporting.
## Post #9
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-03-31T21:40:11+00:00
- Post Title: Ascendant One Model Viewer

Oh that is definitely weird, it can probably be manually fixed anyway so no worries if you don't find anything! Just wanted to let you know in case it was something in relation to the tool.
Thanks again though! Thought we wouldn't get these models at all.
## Post #10
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2019-04-01T21:55:54+00:00
- Post Title: Ascendant One Model Viewer

Hey, thanks for the tool man...
I tried all the models and the only one that wasn't fully imported into the tool viewer is Zeus. 
Only had his armor on...
I checked folder and look like all the meshes are inside as well... Not sure if my files are bad or Zues file are just different from the others.
Here's Zues Mesh folder if you need to check.
Zues.rar: 4MB
[https://www.mediafire.com/file/ucgw1949 ... /Zues.rar/](https://www.mediafire.com/file/ucgw1949pdbu23w/Zues.rar/)
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-04-02T01:20:14+00:00
- Post Title: Ascendant One Model Viewer

> Reply from petventh18 ↑Tue Apr 02, 2019 5:55 am at Tue Apr 02, 2019 5:55 am
>
> 
Not sure if my files are bad or Zues file are just different from the others.
There is a slight bug with Zeus. I will fix it, but probably in couple of days. I am a bit busy atm.
## Post #12
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2019-04-02T09:17:24+00:00
- Post Title: Ascendant One Model Viewer

Thank you so much~~~~
## Post #13
- Username: ialz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 12, 2018 3:25 am
- Post datetime: 2019-04-08T15:51:57+00:00
- Post Title: Ascendant One Model Viewer

wow thank you so much!  I'm looking forward to testing it tonight
## Post #14
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-04-21T20:07:38+00:00
- Post Title: Ascendant One Model Viewer

Finally had the time to update this. It should now load Zeus and also loads some other missing meshes. There seems to be still a problem with Zeus hair, but I will get to that later. Download from the updated link in the first post.
## Post #15
- Username: calypsoup
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Sep 12, 2016 3:51 am
- Post datetime: 2019-04-22T15:28:42+00:00
- Post Title: Ascendant One Model Viewer

can this export animations ?
## Post #16
- Username: sydie
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Nov 30, 2016 6:45 am
- Post datetime: 2019-04-22T17:13:09+00:00
- Post Title: Re: Ascendant One Model Viewer

Hey, thanks for the tool!
However, I can’t find where to download the game?!
I was waiting for it to come out for a year now - is it out of early access?
I hope it’s not region-locked   

Thanks.
## Post #17
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2019-04-25T19:04:07+00:00
- Post Title: Re: Ascendant One Model Viewer

Hey Thanks a lot for this tool! This might be a similar issue as the other problematic model, but the new character's hair only imports the low poly mesh, not the high poly. Is there a way to fix this eventually? 
[https://mega.nz/#!Pv50xI4Z!9kZwdKDRgndz ... MgqSdGyCOY](https://mega.nz/#!Pv50xI4Z!9kZwdKDRgndz-vUCG4GXjYWvywx7sOMiUMgqSdGyCOY)
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-04-25T21:00:46+00:00
- Post Title: Re: Ascendant One Model Viewer

Looks like it was just a tiny error. Hair also loads now. Tool link updated.




> Reply from o0Crofty0o ↑Fri Apr 26, 2019 3:04 am at Fri Apr 26, 2019 3:04 am
>
> 
the new character's hair only imports the low poly mesh
That was related to Unity's vertex count limit. I also fixed that, should export the first LOD too now.
## Post #19
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2019-04-25T21:09:38+00:00
- Post Title: Re: Ascendant One Model Viewer

That was super fast! Thanks a lot
## Post #20
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-04-26T19:45:19+00:00
- Post Title: Re: Ascendant One Model Viewer

Have you ever tried getting the animations to extract?
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-04-26T23:28:51+00:00
- Post Title: Re: Ascendant One Model Viewer

> Reply from WollieWoltaz ↑Sat Apr 27, 2019 3:45 am at Sat Apr 27, 2019 3:45 am
>
> 
Have you ever tried getting the animations to extract?

Not planning to support animations atm.
## Post #22
- Username: luckso
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Aug 14, 2012 11:51 am
- Post datetime: 2019-04-28T06:32:43+00:00
- Post Title: Re: Ascendant One Model Viewer

hi and thx great tool
where do I find umode for extracting textures pls?
## Post #23
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2019-05-27T19:02:22+00:00
- Post Title: Re: Ascendant One Model Viewer

Hi, your model viewer doesn't work anymore on newer version of Ascendant One, maybe because of .uasset being split into .uasset and .uexp
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-27T19:20:51+00:00
- Post Title: Re: Ascendant One Model Viewer

> Reply from joeyq ↑Tue May 28, 2019 3:02 am at Tue May 28, 2019 3:02 am
>
> 
your model viewer doesn't work anymore on newer version of Ascendant One
You have to be more specific. What doesn't work? What file are you trying to load? Always send me a sample file so that I can understand the problem.
## Post #25
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2019-05-27T23:17:24+00:00
- Post Title: Re: Ascendant One Model Viewer

> Reply from akderebur ↑Tue May 28, 2019 3:20 am at Tue May 28, 2019 3:20 am
>
> 
joeyq wrote: ↑Tue May 28, 2019 3:02 am
your model viewer doesn't work anymore on newer version of Ascendant One

You have to be more specific. What doesn't work? What file are you trying to load? Always send me a sample file so that I can understand the problem.

I just learned from akderebur that you can merge 2 files with command prompt, so here's a batch file that merges .uasset and .uexp so you can view the models in the model viewer:

```
IF NOT EXIST "./output" (md output)
for %%s in (*.uasset) do copy /b "%%s"+"%%~ns.uexp" "./output/%%s"
pause

```

copy the code above into a .txt file, rename it "batch_merge_uasset_and_uexp.bat" and place it in a folder where the .uasset and .uexp are, this creates a subfolder "output" with the merged files which are viewable in the model viewer.
Thanks akderebur!
## Post #26
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-19T02:20:55+00:00
- Post Title: Re: Ascendant One Model Viewer

> Reply from akderebur ↑Sat Apr 27, 2019 7:28 am at Sat Apr 27, 2019 7:28 am
>
> Not planning to support animations atm.
But will there ever be a chance to support animations in future, or not a chance at all?
The animations are simply flawlessly gorgeous, one of a kind.
## Post #27
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-08-19T05:54:12+00:00
- Post Title: Re: Ascendant One Model Viewer

> Reply from mono24 ↑Mon Aug 19, 2019 10:20 am at Mon Aug 19, 2019 10:20 am
>
> 
But will there ever be a chance to support animations in future, or not a chance at all?
It probably uses one of the existing UE4 animation datatypes. So I think it can be done. I don't know if I will ever have the time to do that though.
## Post #28
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-19T09:12:50+00:00
- Post Title: Re: Ascendant One Model Viewer

> Reply from akderebur ↑Mon Aug 19, 2019 1:54 pm at Mon Aug 19, 2019 1:54 pm
>
> I don't know if I will ever have the time to do that though.
Please do consider it, these animations are worth it, I genuinely hope you can in the future.
Gildor is aware of your tool and unfortunately will not touch the game, at least please consider it for later on.
It would be a shame to see it die, the characters are just extraordinary.
## Post #29
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-08-19T18:29:39+00:00
- Post Title: Re: Ascendant One Model Viewer

I fully agree
## Post #30
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-08-19T18:55:35+00:00
- Post Title: Re: Ascendant One Model Viewer

> Reply from mono24 ↑Mon Aug 19, 2019 5:12 pm at Mon Aug 19, 2019 5:12 pm
>
> 
Gildor is aware of your tool and unfortunately will not touch the game
I would do the same in his place. Would be a waste trying to support every UE game that has non-standard stuff.

> Reply from mono24 ↑Mon Aug 19, 2019 5:12 pm at Mon Aug 19, 2019 5:12 pm
>
> 
Please do consider it, these animations are worth it, I genuinely hope you can in the future.

I won't say never, but I am finding less and less time for model ripping. Don't want to give anyone hope with this
## Post #31
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2019-08-28T10:20:18+00:00
- Post Title: Re: Ascendant One Model Viewer

Gildor's umodel has been updated to fully support Ascendant One
[https://www.youtube.com/watch?v=rew3u9eUucg](https://www.youtube.com/watch?v=rew3u9eUucg)
## Post #32
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T08:09:22+00:00
- Post Title: Re: Ascendant One Model Viewer

Thanks for your help
## Post #33
- Username: LAUVz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 11, 2019 3:29 am
- Post datetime: 2019-10-26T10:29:56+00:00
- Post Title: Re: Ascendant One Model Viewer

Does anyone have full game files for AscendantOne? if someone has could they please share them with me in pm?
## Post #34
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-26T23:27:35+00:00
- Post Title: Re: Ascendant One Model Viewer

> Reply from LAUVz ↑Sat Oct 26, 2019 6:29 pm at Sat Oct 26, 2019 6:29 pm
>
> 
Does anyone have full game files for AscendantOne? if someone has could they please share them with me in pm?
Game is already dead and devs pulled the plug permanently on it so the files are already out in the open, like this one:
[https://www.gildor.org/smf/index.php/to ... l#msg33513](https://www.gildor.org/smf/index.php/topic,6741.msg33513.html#msg33513)
