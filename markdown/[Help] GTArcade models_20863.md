## Post #1
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-07-27T03:01:29+00:00
- Post Title: [Help] GTArcade models?

I've got something very difficult here:

GTArcade might have some of the best models I've seen, but when I try to get them, I face several problems. I've got no idea about working tools, where the files with the models are located and if the version makes any difference... I'm mostly focused on League of Angels III, since I play this game and wishing to get those models. If the problems are packed in questions, these are:
Do some extraction tools for GTArcade games (on PC!) exist?
Where are the files from the games located?
Which platform is better to work with when extracting?

For now, I want to get a closer look on what these models look like outside their "natural" environment - any help with that is appreciated
## Post #2
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-08-01T10:16:00+00:00
- Post Title: [Help] GTArcade models?

Check this directory on your PC for LOA3 files:
\\ Change "YOUR ACCOUNT" to your user account, also I used the GTArcade version, not the browser version;
C:\Users\"YOUR ACCOUNT"\AppData\Local\Gtarcade\plugin\air\main

\\ These contain an ATF header
.DXT files are your textures
.BA files are your models

These files are located in the Assets/xx/xx/xx/.. folder mate. This is as far as I can help you regarding League Of Angels 3, sorry and good luck.

Check out GamesRepository tutorial section for help with Game Of Thrones: Winter Is Coming
[https://gamesrepository.000webhostapp.com/](https://gamesrepository.000webhostapp.com/)
## Post #3
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-03T08:45:13+00:00
- Post Title: [Help] GTArcade models?

This location guide is already nice and I found the files for myself, but... There's the old problem with file formats again... Is there a program which can open .dxt and .ba files without a problem? I tried the guide on the linked site and AssetStudio doesn't load a file
## Post #4
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-08-04T00:37:27+00:00
- Post Title: [Help] GTArcade models?

Glad it helped. GoT-WiC is built on the Unity engine, so AssetStudio works with it. LOA3 uses a different engine mate, sorry. I had a look and couldn't find any tools sorry. You might have to upload some samples and request someone with the skills to have a look at them.
## Post #5
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-26T08:13:08+00:00
- Post Title: [Help] GTArcade models?

Now's the time for the final step before I can take over... I finally got the real model files out of the double-archived thing and now I'm searching for a program and/or script for either Blender and/or Noesis to open up the files... [The zipped file is hosted here.](https://drive.google.com/open?id=1aFNuQ2uI1xoxfHf7N50PWYCJu6RGZ40X) Does anyone know of scripts to open them/a program that opens them and is free to use? The models here come ultimately in .s3d format, something that got introduced waaaay back in 1999 (I'm surprised by that as well) with the game Everquest... 

Also, I just can't figure out where I'd have to start in the files for creating the script to import them in Blender or Noesis... Is there any file engineering expert somewhere?

The files specify that a "s3dMesh" is packed in each of them - it seems that this is something that makes the model ripping really difficult to get done. And with that, there came another thought to my mind: I do think the .s3d files on this one are some kind of dazzler. Why? The appear to be another archive file (in formatting of EverQuest), but they aren't an archive. What's the true file extension to them?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-26T12:10:28+00:00
- Post Title: [Help] GTArcade models?

point cloud of uvs looks ok; problem with faces - despite preceding DW counter being skipped
.



role_m_000-s3d-uvs-point_cloud.png (9.23 KiB) Viewed 461 times
## Post #7
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-26T12:56:24+00:00
- Post Title: [Help] GTArcade models?

> Reply from shakotay2 ↑Mon Aug 26, 2019 8:10 pm at Mon Aug 26, 2019 8:10 pm
>
> 
point cloud of uvs looks ok; problem with faces - despite preceding DW counter being skipped

What does that mean? I'm not seeing clearly through that sentence...
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-26T14:41:22+00:00
- Post Title: [Help] GTArcade models?

It means that I have to do further tests. (There's an unexpected/superfluous counter in the face indices data which I eliminated. But it didn't help to display a proper mesh. Point cloud of uv data seems to be "ok" as can be seen.)
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-26T15:18:18+00:00
- Post Title: [Help] GTArcade models?

> Reply from shakotay2 ↑Mon Aug 26, 2019 8:10 pm at Mon Aug 26, 2019 8:10 pm
>
> 
problem with faces - despite preceding DW counter being skipped
Looks OK to me.



uv.png (84.25 KiB) Viewed 452 times
## Post #10
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-26T15:23:34+00:00
- Post Title: [Help] GTArcade models?

> Reply from Bigchillghost ↑Mon Aug 26, 2019 11:18 pm at Mon Aug 26, 2019 11:18 pm
>
> 
shakotay2 wrote: ↑Mon Aug 26, 2019 8:10 pm
problem with faces - despite preceding DW counter being skipped

Looks OK to me.
uv.png

That program there looks interesting - where did you get that?

Also it's nice to see some hints on what the model looks like - if the textures aren't a problem as well, then I can collect the tools I need to get this done
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-28T07:59:25+00:00
- Post Title: [Help] GTArcade models?

> Reply from LightXPS ↑Mon Aug 26, 2019 11:23 pm at Mon Aug 26, 2019 11:23 pm
>
> 
That program there looks interesting - where did you get that?
See the 2nd link in my signature.

> Reply from LightXPS ↑Mon Aug 26, 2019 11:23 pm at Mon Aug 26, 2019 11:23 pm
>
> 
Also it's nice to see some hints on what the model looks like - if the textures aren't a problem as well, then I can collect the tools I need to get this done
There's no way you can get the mesh without coding a script or something.



head.png (90.17 KiB) Viewed 438 times
## Post #12
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-28T08:02:21+00:00
- Post Title: [Help] GTArcade models?

> Reply from Bigchillghost ↑Wed Aug 28, 2019 3:59 pm at Wed Aug 28, 2019 3:59 pm
>
> 
There's no way you can get the mesh without coding a script or something.

I'm well aware of that, but unfortunately, I'm lacking said script... Is there any for this specific file format?
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-28T08:03:51+00:00
- Post Title: [Help] GTArcade models?

Here's the Noesis script for the test. No guarantee that it'll work with all files.
[fmt_GTArcade_s3d.zip](https://xentaxbackup.github.io/file/16660_fmt_GTArcade_s3d.zip)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-28T08:54:16+00:00
- Post Title: [Help] GTArcade models?

```
...
0x8c0e ( 24 )
0x8c26 ( 24 )
0x8c3e ( 24 )
0x8c56 ( 24 )
0x8c6e ( 24 )
0x8c86 ( 24 )
0x8c9e ( 24 )
0x8cb6 ( 24 )
0x8cce ( 24 )
0x8ce6 ( 24 )
0x8d16 ( 48 )
0x8d2e ( 24 )
0x8d5e ( 48 )
0x8d8e ( 48 )
0x8dbe ( 48 )
0x8dd6 ( 24 )
0x8dee ( 24 )
0x8e06 ( 24 )
0x8e36 ( 48 )
0x8e66 ( 48 )
0x8e7e ( 24 )
0x8e96 ( 24 )
0x8eae ( 24 )
0x8ec6 ( 24 )
0x8ede ( 24 )
0x8ef6 ( 24 )
...

```

Obfuscation at it's best - there's only few people who could have solved this riddle, congratz!  
Offset = blockStart + PositionIdx*0x18 + 0xC  

(Where PositionIDx is really crazy:)

```
0x424a 681
0x425e 730
0x4272 732
0x4286 733
0x429a 734
0x42ae 733
0x42c2 735
0x42d6 737
0x42ea 732
0x42fe 734
0x4312 463
0x4326 738
0x433a 739
0x434e 740
0x4362 679
0x4376 741
0x438a 742
0x439e 743
0x43b2 458
0x43c6 744
0x43da 745
0x43ee 565
0x4402 741
0x4416 746
0x442a 747
0x443e 748
0x4452 750
0x4466 752
0x447a 753
0x448e 710
0x44a2 692
0x44b6 754
0x44ca 710
0x44de 722
0x44f2 756
0x4506 683
0x451a 435
0x452e 756
0x4542 758
0x4556 734
0x456a 747
0x457e 471
0x4592 760
0x45a6 761
0x45ba 762
0x45ce 559
0x45e2 763
0x45f6 764
0x460a 510
0x461e 512
0x4632 765
0x4646 766
0x465a 765
0x466e 767
0x4682 768
0x4696 734
0x46aa 770
0x46be 767
0x46d2 467
0x46e6 460
0x46fa 525
```


> Reply from Bigchillghost ↑Wed Aug 28, 2019 4:03 pm at Wed Aug 28, 2019 4:03 pm
>
> 
Here's the Noesis script for the test. No guarantee that it'll work with all files.For role_m_000.s3d more fiddling to be required:
.



role_boots.png (41.75 KiB) Viewed 428 times
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-28T12:49:11+00:00
- Post Title: [Help] GTArcade models?

> Reply from shakotay2 ↑Wed Aug 28, 2019 4:54 pm at Wed Aug 28, 2019 4:54 pm
>
> 
Obfuscation at it's best - there's only few people who could have solved this riddle, congratz!
Obfuscation, is it? I thought it was just some old game format.

> Reply from shakotay2 ↑Wed Aug 28, 2019 4:54 pm at Wed Aug 28, 2019 4:54 pm
>
> 
Offset = blockStart + PositionIdx*0x18 + 0xC  
(Where PositionIDx is really crazy)
The PositionIdx is the index of the first vertex in a vertex weight group, followed by an int32 weight count. What doesn't make sense is that though the weights add up to 1.0, some skinned to non-zero bone ID are of zero weighted, why bother to store such info if they're weightless?

> Reply from shakotay2 ↑Wed Aug 28, 2019 4:54 pm at Wed Aug 28, 2019 4:54 pm
>
> 
For role_m_000.s3d more fiddling to be required:
Yeah, I noticed that too. But based on the UV, shouldn't it be some kind of body part instead of a boot? I have a couple of theories of getting the actual positions: 1. calculate the average position coordinates in a vertex weight set, or their weighted average; 2. take the coordinates with the largest weight as the position of this vertex. But I don't have time to test it now.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-28T14:02:27+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Wed Aug 28, 2019 8:49 pm at Wed Aug 28, 2019 8:49 pm
>
> 
Obfuscation, is it? I thought it was just some old game format.I wasn't sure, but I couldn't imagine how (and why, during weight painting?) vertices could be "mixed up" in such a strange way. (In most formats I knew so far the first 100 vertices at least build proper faces, usually.)

> Yeah, I noticed that too. But based on the UV, shouldn't it be some kind of body part instead of a boot?Yep - I named the picture "role_boot(s)" because they were the only parts I could identify from the whole mesh.
## Post #17
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-29T11:09:28+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Wed Aug 28, 2019 8:49 pm at Wed Aug 28, 2019 8:49 pm
>
> 
Yeah, I noticed that too. But based on the UV, shouldn't it be some kind of body part instead of a boot? I have a couple of theories of getting the actual positions: 1. calculate the average position coordinates in a vertex weight set, or their weighted average; 2. take the coordinates with the largest weight as the position of this vertex. But I don't have time to test it now.

Judging from the UV, there should be the entire body minus the face in the role_m_000.s3d since the face has a file on its own (and that one displays normally in Noesis). And I think all those parts are somewhere in that mesh mess... Once you find the time, I'm ready to see the result!

Anyhow: Big thanks to all who posted in here so far! This goes in the right direction now
## Post #18
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-09-15T07:09:58+00:00
- Post Title: Re: [Help] GTArcade models?

Sorry for yet another double post, but I'd like to know if there's any progress on this one..? If there is any, what does it look like?

Also, I'd really like to note that there's also the textures available for this model. [Here you go](https://forum.xentax.com/viewtopic.php?f=18&t=20939).

And one last thing to note: Is it possible to convert the .s3d files into something like .dae or .fbx so that I can take the conversion work from there?
## Post #19
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-15T15:20:18+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from LightXPS ↑Sun Sep 15, 2019 3:09 pm at Sun Sep 15, 2019 3:09 pm
>
> I'd like to know if there's any progress on this one..?
If nobody reply to this topic, then the answer is no. All my previous attempts/guesses were failed. No idea why the same method that applies to one model would fail on another.
## Post #20
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-09-15T15:23:01+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Sun Sep 15, 2019 11:20 pm at Sun Sep 15, 2019 11:20 pm
>
> 
If nobody reply to this topic, then the answer is no. All my previous attempts/guesses were failed. No idea why the same method that applies to one model would fail on another.

That's kinda strange - there was some progress before the silence came in where at least a boot was identified and now everything's down the drain? thinks Could this be the model ripper's worst nightmare?
## Post #21
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-11-06T08:37:16+00:00
- Post Title: Re: [Help] GTArcade models?

Any new hints on that project here? The files are available again - I really want that job done (at least so far that I can open the model files with Blender and/or XNALara)...

Btw: How can I open those files without any file ending to it? I'm talking about [this](https://drive.google.com/open?id=15w31iC8oxr2_NtaWK2I2a8U3NxQepqRi) one, for example.

And connecting to [this](https://forum.xentax.com/viewtopic.php?f=16&t=20863#p155730) post: I tried that one as well, but all I get is a meshed triangular piece of crap... Either I'm stupid or something's not working properly here...
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-06T11:31:20+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from LightXPS ↑Wed Nov 06, 2019 4:37 pm at Wed Nov 06, 2019 4:37 pm
>
> 
Any new hints on that project here?
I don't think there're people still watching this. 

> Reply from LightXPS ↑Wed Nov 06, 2019 4:37 pm at Wed Nov 06, 2019 4:37 pm
>
> 
The files are available again
What do you mean by "again"?

> Reply from LightXPS ↑Wed Nov 06, 2019 4:37 pm at Wed Nov 06, 2019 4:37 pm
>
> 
at least so far that I can open the model files with Blender and/or XNALara
Cool. Problem solved?

> Reply from LightXPS ↑Wed Nov 06, 2019 4:37 pm at Wed Nov 06, 2019 4:37 pm
>
> How can I open those files without any file ending to it?
Just a simple container for s3d and act files. Use this BMS script to unpack them.
[s3dUnpacker.zip](https://xentaxbackup.github.io/file/17019_s3dUnpacker.zip)
## Post #23
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-11-06T11:35:36+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Wed Nov 06, 2019 7:31 pm at Wed Nov 06, 2019 7:31 pm
>
> 
I don't think there're people still watching this.
Basically, this has finally gone down the drain?

> Reply from Bigchillghost ↑Wed Nov 06, 2019 7:31 pm at Wed Nov 06, 2019 7:31 pm
>
> 
What do you mean by "again"?
I had them removed from the cloud drive, but I recovered them.

> Reply from Bigchillghost ↑Wed Nov 06, 2019 7:31 pm at Wed Nov 06, 2019 7:31 pm
>
> 
Cool. Problem solved?
Nope, not at all. The body file comes out as a big mess (not a single mesh part visible) and the head file doesn't open in AMR at all...

But I think I'm gonna switch to a different game which - hopefully - is easier to rip since there are already some ripped models available. Just need to find the right one...
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-06T12:11:35+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from LightXPS ↑Wed Nov 06, 2019 7:35 pm at Wed Nov 06, 2019 7:35 pm
>
> 
Basically, this has finally gone down the drain?
Guess so. Mainly it is because of the frustrating format. Also the low quality models just make people lose their appetites.

> Reply from LightXPS ↑Wed Nov 06, 2019 7:35 pm at Wed Nov 06, 2019 7:35 pm
>
> 
the head file doesn't open in AMR at all...
You cannot extract anything manually except for the UVs:



role_m_000_head_UV.png (109.28 KiB) Viewed 249 times
## Post #25
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-11-06T12:16:13+00:00
- Post Title: Re: [Help] GTArcade models?

Okay, then... This project is officially abandonded by me. I've got a couple of models from Vindictus in my sight, I'm gonna get those.
## Post #26
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-04T00:10:45+00:00
- Post Title: Re: [Help] GTArcade models?

> Just a simple container for s3d and act files. Use this BMS script to unpack them.
Hello  Bigchillghost! it's me again XD!, I got some .ba models from LOA3, but seems encrypted, please take a look at them when you can :') 

[https://www.mediafire.com/file/z38ub7vu ... s.zip/file](https://www.mediafire.com/file/z38ub7vumuufvdi/examples_.ba_models.zip/file)
## Post #27
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-05T22:32:21+00:00
- Post Title: Re: [Help] GTArcade models?

Well I was a complete noob and didn't identify the compression xD! The armature loads fine the mesh looks really weird, should be something with the weights, hope you can take a look at it, or maybe can you adapt the script to only loads meshes without bones?    Thanks for all your scripts!



leagueofangelsIII.jpg (83.75 KiB) Viewed 182 times
## Post #28
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-06T06:06:07+00:00
- Post Title: Re: [Help] GTArcade models?

I was checking the other League of angels games (I and II was a pain get the models xD), the texture is compressed and is not DXT1 like LoA III, is DXT5. Well at least I was able to convert the texture to png with their transparency, only the models are left, as I mentioned the position of the bones seems correct, only the weights need to be rechecked. I'm gonna do more research, hope find something.  



mountexample.jpg (128.76 KiB) Viewed 174 times



S3D MODELS : [https://www.mediafire.com/file/hztxuo44 ... s.zip/file](https://www.mediafire.com/file/hztxuo448skq8pi/s3d_models.zip/file)
## Post #29
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-09T01:52:38+00:00
- Post Title: Re: [Help] GTArcade models?

bump bump bump
## Post #30
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-18T06:41:17+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Wed Nov 06, 2019 8:11 pm at Wed Nov 06, 2019 8:11 pm
>
> 
LightXPS wrote: ↑Wed Nov 06, 2019 7:35 pm
Basically, this has finally gone down the drain?
Guess so. Mainly it is because of the frustrating format. Also the low quality models just make people lose their appetites.
LightXPS wrote: ↑Wed Nov 06, 2019 7:35 pm
the head file doesn't open in AMR at all...
You cannot extract anything manually except for the UVs:
role_m_000_head_UV.png
Hello Bigchillghost, could you please take a look at this models?   
[https://www.mediafire.com/file/4u3g0ejd ... S.zip/file](https://www.mediafire.com/file/4u3g0ejdxgp0feb/LOA_MODELS.zip/file)
## Post #31
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-21T17:07:35+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from moonpaladin ↑Tue May 18, 2021 2:41 pm at Tue May 18, 2021 2:41 pm
>
> 
Hello Bigchillghost, could you please take a look at this models?
Well, thought this was gona be a total waste of time but darn, I did it! 
[s3ds.jpg](https://xentaxbackup.github.io/file/20183_s3ds.jpg)
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-21T17:08:06+00:00
- Post Title: Re: [Help] GTArcade models?

Here's the finally working script:


 fmt_GTArcade_s3d.zip
(1.11 KiB) Downloaded 83 times



Skin info is also supported.
## Post #33
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-21T17:51:53+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Sat May 22, 2021 1:08 am at Sat May 22, 2021 1:08 am
>
> 
Here's the finally working script:
fmt_GTArcade_s3d.zip


Skin info is also supported.

omggggggggggggggggggggggggg! THANKS ALOT!
## Post #34
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-23T21:47:38+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Sat May 22, 2021 1:07 am at Sat May 22, 2021 1:07 am
>
> 
moonpaladin wrote: ↑Tue May 18, 2021 2:41 pm
Hello Bigchillghost, could you please take a look at this models?  

Well, thought this was gona be a total waste of time but darn, I did it!

Nice   
Very unusual format, i tried my hand at figuring it out but those damn face indcies never seemed right
## Post #35
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-06-09T07:40:38+00:00
- Post Title: Re: [Help] GTArcade models?

Hello, thank you for this work and the script!!

I have a question, could anyone tell me how to get the models from .BA files? I get the textures from dtx files but i still can't take the models from the BA files.

Thank you so much!
## Post #36
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-10T12:26:48+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Pinstripe ↑Wed Jun 09, 2021 3:40 pm at Wed Jun 09, 2021 3:40 pm
>
> could anyone tell me how to get the models from .BA files?
Use this BMS script to decompress the file:


 lzma86head.zip
(242 Bytes) Downloaded 59 times



Then use the script in this post to unpack the decompressed file:
[viewtopic.php?p=157527#p157527](viewtopic.php?p=157527#p157527)
## Post #37
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-06-10T13:18:32+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Thu Jun 10, 2021 8:26 pm at Thu Jun 10, 2021 8:26 pm
>
> 
Pinstripe wrote: ↑Wed Jun 09, 2021 3:40 pmcould anyone tell me how to get the models from .BA files?

Use this BMS script to decompress the file:
lzma86head.zip

Then use the script in this post to unpack the decompressed file:
viewtopic.php?p=157527#p157527

Thank you so much, the lzma86 was what i missed!
## Post #38
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-06-15T08:02:08+00:00
- Post Title: Re: [Help] GTArcade models?

Hello, its me again, i have a question.
Last few days, the files are not downloaded into assets anymore, its saved into Cache folder in appdata as file without any extension, no BA, no DXT anymore, is there any way how to set the download back into c:/gtarcade or not?
Thank you!
## Post #39
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-10-06T10:08:10+00:00
- Post Title: Re: [Help] GTArcade models?

Hey guys! 
I would like to ask you for something. 
They probably changed the structure of the files, I'm not able to unpack it with lzma script and even the ATF is not openable anymore.

Do you think you could take a look at it? I would be really greatful.

I have added one texture file and one model file.

[https://mega.nz/file/6s5SQBrS#WE_Jd4k43 ... EQnch0SC2g](https://mega.nz/file/6s5SQBrS#WE_Jd4k43im6AvL4F3Oaqe4YEIErPR3PwEQnch0SC2g)
## Post #40
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-10-06T15:12:45+00:00
- Post Title: Re: [Help] GTArcade models?

Alright, i was able to open the model, all i had to do was delete the part on the image.
The ATF file is still mystery for me, if anyone know what it could be, compression or something, i would be greatful.
[test.JPG](https://xentaxbackup.github.io/file/20958_test.JPG)
## Post #41
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-06T17:57:11+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Pinstripe ↑Wed Oct 06, 2021 11:12 pm at Wed Oct 06, 2021 11:12 pm
>
> 
The ATF file is still mystery for me, if anyone know what it could be, compression or something, i would be greatful.
It's still one of the lzma algos but just harder to locate the correct ending boundry of the lzma stream. Maybe uploading a couple more samples would be helpful.
## Post #42
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-10-06T19:55:33+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Thu Oct 07, 2021 1:57 am at Thu Oct 07, 2021 1:57 am
>
> 
Pinstripe wrote: ↑Wed Oct 06, 2021 11:12 pm
The ATF file is still mystery for me, if anyone know what it could be, compression or something, i would be greatful.

It's still one of the lzma algos but just harder to locate the correct ending boundry of the lzma stream. Maybe uploading a couple more samples would be helpful.

Alright, I hope you can find what exactly it is. Thanks!
Here are few more samples:
[https://mega.nz/file/KloSUZjZ#mcMZ8mnkB ... sqMXhOJu6M](https://mega.nz/file/KloSUZjZ#mcMZ8mnkBSG1KkqoLChVjSvwCXBnm8iM_sqMXhOJu6M)
## Post #43
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-07T09:03:36+00:00
- Post Title: Re: [Help] GTArcade models?

Well, under certain circumstances the 24-bit value (as in big-endian) before the lzma stream matches exactly with its size, which can be decompressed successfully with the "lzma_dynamic" algorithm, while others don't. Btw had you modified some of the sample files or do they indeed begin with the "ATF" signature? 

> Reply from Pinstripe ↑Wed Oct 06, 2021 6:08 pm at Wed Oct 06, 2021 6:08 pm
>
> ... and even the ATF is not openable anymore.
I don't recall dealing with anything about "ATF" before. Is it a new file type?
## Post #44
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-10-07T11:15:55+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Thu Oct 07, 2021 5:03 pm at Thu Oct 07, 2021 5:03 pm
>
> 
Well, under certain circumstances the 24-bit value (as in big-endian) before the lzma stream matches exactly with its size, which can be decompressed successfully with the "lzma_dynamic" algorithm, while others don't. Btw had you modified some of the sample files or do they indeed begin with the "ATF" signature? 
Pinstripe wrote: ↑Wed Oct 06, 2021 6:08 pm... and even the ATF is not openable anymore.

I don't recall dealing with anything about "ATF" before. Is it a new file type?

I didn't modify them at all.
Well, there is an tool - [https://vamapaull.com/atf-to-png-converter-tool/](https://vamapaull.com/atf-to-png-converter-tool/) 
called ATF2PNG, which can export the ATF file into PNG. It was working with any problem before, but with those new files im not able to open it anymore. The older ones started always with ATF, the new one has few more characters before (in hex).
If it would help you, here are working ATF files. 

[https://mega.nz/file/b4g2mDbK#HsltMGnAb ... kxxhm8h6O4](https://mega.nz/file/b4g2mDbK#HsltMGnAb8FjFdxj57r8wuTffDKG7fjRMkxxhm8h6O4)
## Post #45
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-09T12:55:54+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Pinstripe ↑Thu Oct 07, 2021 7:15 pm at Thu Oct 07, 2021 7:15 pm
>
> 
there is an tool ... called ATF2PNG, which can export the ATF file into PNG.
I see, so it stands for "Adobe Texture Format".   
I think they have obfuscated the size fields of half of the data bolcks. For instance, the ones of the 1st and the 3rd blocks are always wrong, while the ones of the 2nd and the 4th are correct, and so on. Unfortunately it's unlikely to solve the puzzle with wild guesses. Btw there're two files (f_0000f0.atf and f_000105.atf) in your previously provided samples which seem to be identical to the "normal" atf files. Have you checked if they can be converted?
## Post #46
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-10-11T04:41:42+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Sat Oct 09, 2021 8:55 pm at Sat Oct 09, 2021 8:55 pm
>
> 
Pinstripe wrote: ↑Thu Oct 07, 2021 7:15 pm
there is an tool ... called ATF2PNG, which can export the ATF file into PNG.

I see, so it stands for "Adobe Texture Format".   
I think they have obfuscated the size fields of half of the data bolcks. For instance, the ones of the 1st and the 3rd blocks are always wrong, while the ones of the 2nd and the 4th are correct, and so on. Unfortunately it's unlikely to solve the puzzle with wild guesses. Btw there're two files (f_0000f0.atf and f_000105.atf) in your previously provided samples which seem to be identical to the "normal" atf files. Have you checked if they can be converted?

I have double-checked those 2 files you have mentoined. f_000105 is diffuse texture and i can convert it (sorry for that). However, im not able to convert the second one.
## Post #47
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-10-12T14:53:01+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Sat Oct 09, 2021 8:55 pm at Sat Oct 09, 2021 8:55 pm
>
> 
Pinstripe wrote: ↑Thu Oct 07, 2021 7:15 pm
there is an tool ... called ATF2PNG, which can export the ATF file into PNG.

I see, so it stands for "Adobe Texture Format".   
I think they have obfuscated the size fields of half of the data bolcks. For instance, the ones of the 1st and the 3rd blocks are always wrong, while the ones of the 2nd and the 4th are correct, and so on. Unfortunately it's unlikely to solve the puzzle with wild guesses. Btw there're two files (f_0000f0.atf and f_000105.atf) in your previously provided samples which seem to be identical to the "normal" atf files. Have you checked if they can be converted?

It's me again, i was able to get 2 samples, its the same texture, one of them is before they started to use this encryption, the other one is after. I hope this could help to recognize what exactly it is.
Thank you in advance!

[https://mega.nz/file/mkh2wLzJ#s13WxNbLA ... nx5g9oECH0](https://mega.nz/file/mkh2wLzJ#s13WxNbLARIpYZjPQV08J3Ln7phnxgA74nx5g9oECH0)
## Post #48
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-13T04:45:49+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Pinstripe ↑Tue Oct 12, 2021 10:53 pm at Tue Oct 12, 2021 10:53 pm
>
> 
It's me again, i was able to get 2 samples, its the same texture, one of them is before they started to use this encryption, the other one is after. I hope this could help to recognize what exactly it is.
The new one has 3 extra bytes inserted after (or before?) every 0x30000 bytes of the data. If you remove these bytes and the first 4 bytes the data will be identical to the old one. But the last chunk is completely different, and got smaller, not sure if it's compressed or encrypted. But at least we can be sure that the size fields are not obfuscated.
## Post #49
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2021-10-14T08:01:39+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Wed Oct 13, 2021 12:45 pm at Wed Oct 13, 2021 12:45 pm
>
> 
Pinstripe wrote: ↑Tue Oct 12, 2021 10:53 pm
It's me again, i was able to get 2 samples, its the same texture, one of them is before they started to use this encryption, the other one is after. I hope this could help to recognize what exactly it is.

The new one has 3 extra bytes inserted after (or before?) every 0x30000 bytes of the data. If you remove these bytes and the first 4 bytes the data will be identical to the old one. But the last chunk is completely different, and got smaller, not sure if it's compressed or encrypted. But at least we can be sure that the size fields are not obfuscated.

Thank you for an info. So, there is really nothing you can do?  I was hoping to get the files   
Anyway, thank you for your time and effort to help me!

If anyone else know how it would be possible to get the texture from the ATF file, i would be really greatful or even able to pay something.
## Post #50
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-14T12:06:23+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Pinstripe ↑Thu Oct 14, 2021 4:01 pm at Thu Oct 14, 2021 4:01 pm
>
> 
So, there is really nothing you can do?  I was hoping to get the files
Just tried to scan the compression on the last chunk with & without the 24-bit size field, but no match at all. Up to this point your best chance would be looking into the game dll or executable instead of blind guesses.
## Post #51
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2021-11-21T00:14:12+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Sat May 22, 2021 1:08 am at Sat May 22, 2021 1:08 am
>
> 
Here's the finally working script:
fmt_GTArcade_s3d.zip


Skin info is also supported.

Thank you very much for this great script, it's a very nice job 
I hope you support act(animation) file,ect files


 s3d_act1_unpacked.rar
(160.39 KiB) Downloaded 41 times


keep going man your wonderful 
warm regards to you
## Post #52
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-21T14:42:21+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from masrawy2 ↑Sun Nov 21, 2021 8:14 am at Sun Nov 21, 2021 8:14 am
>
> 
I hope you support act(animation) file
No, I don't deal with animation for requests. Certainly won't make this a start.
## Post #53
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-11-23T15:52:07+00:00
- Post Title: Re: [Help] GTArcade models?

Hi everyone, 

recently a new GTArcade mobile game has been released in beta: league of Angels chaos. content is stored in .pak archive. 
here link for data_1.pak :[https://www.mediafire.com/file/02epyotn ... 1.pak/file](https://www.mediafire.com/file/02epyotnmzanveo/data_1.pak/file)
 here link for first bytes of data_1.pak : [https://www.mediafire.com/file/ioxedzl1 ... s.rar/file](https://www.mediafire.com/file/ioxedzl1gmdau77/samples_bytes.rar/file)

EDIT: Solved , just use Ekey unpacker for League of Angels: Heaven fury , although [viewtopic.php?f=10&t=23918&p=174561&hil ... ls#p174561](https://forum.xentax.com/viewtopic.php?f=10&t=23918&p=174561&hilit=league+of+angels#p174561)
## Post #54
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-01T15:29:57+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Bigchillghost ↑Thu Oct 14, 2021 8:06 pm at Thu Oct 14, 2021 8:06 pm
>
> 
Just tried to scan the compression on the last chunk with & without the 24-bit size field, but no match at all.
Hello!I just found some .dxt textures that cannot be opened with the atftopng, but was able to get the textures with rawtext, for the r_zhanshi (DXT1 - OFFSET 0xD -SIZE 512x512) for z_zhanma (DXT5 - OFFSET 0xD - SIZE 256x256 (not sure, could be 512x512)), the main problem comes with the models. I have seen that they have inserted model of objects (.3ds) those can be opened without problems with 3ds max, but the models of the characters are with an ending (.zs3d), is the .s3d compressed or encrypted or just different? . Im gonna attach the models, please take a look  at them when you can.    
[https://www.mediafire.com/file/ubgjw4j1 ... s.zip/file](https://www.mediafire.com/file/ubgjw4j1s8oo9hm/zs3d_examples.zip/file)
## Post #55
- Username: gunyalizop
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 03, 2021 2:44 am
- Post datetime: 2021-12-03T19:19:26+00:00
- Post Title: Re: [Help] GTArcade models?

could anyone tell me how to get the models from .BA files? I get the textures from dtx files but i still can't take the models from the BA files.
## Post #56
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-07T00:49:48+00:00
- Post Title: Re: [Help] GTArcade models?

> Pinstripe wrote: ↑Wed Jun 09, 2021 3:40 pmcould anyone tell me how to get the models from .BA files?
>
> 
>
> Use this BMS script to decompress the file:
>
> lzma86head.zip
>
> 
>
> Then use the script in this post to unpack the decompressed file:
>
> viewtopic.php?p=157527#p157527
## Post #57
- Username: ragova1312
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 11, 2022 6:00 am
- Post datetime: 2022-02-10T22:46:01+00:00
- Post Title: Re: [Help] GTArcade models?

i am a bit inexperienced, can someone explain to me how to extract models and textures from LOA3? Thanks
## Post #58
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2022-02-27T04:06:43+00:00
- Post Title: Re: [Help] GTArcade models?

If I'm not mistaken (and read this thread correctly), there's a new encryption on the files? If yes, is there a tutorial on how I can get the models extracted?

It has been a long time since I tried to get this thing done...
## Post #59
- Username: ragova1312
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 11, 2022 6:00 am
- Post datetime: 2022-03-17T11:08:27+00:00
- Post Title: Re: [Help] GTArcade models?

Someone could help me to extractm models, texture and animation from LoA3? Thanks
## Post #60
- Username: vandaa95
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 26, 2023 7:02 am
- Post datetime: 2023-07-25T23:06:50+00:00
- Post Title: Re: [Help] GTArcade models?

> Reply from Drawing ↑Tue Nov 23, 2021 11:52 pm at Tue Nov 23, 2021 11:52 pm
>
> 
Hi everyone, 

recently a new GTArcade mobile game has been released in beta: league of Angels chaos. content is stored in .pak archive. 
here link for data_1.pak :https://www.mediafire.com/file/02epyotn ... 1.pak/file
 here link for first bytes of data_1.pak : https://www.mediafire.com/file/ioxedzl1 ... s.rar/file

EDIT: Solved , just use Ekey unpacker for League of Angels: Heaven fury , although viewtopic.php?f=10&t=23918&p=174561&hil ... ls#p174561

Do you still have the files please?
