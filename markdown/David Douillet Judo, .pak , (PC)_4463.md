## Post #1
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-05-16T13:55:38+00:00
- Post Title: David Douillet Judo, .pak , (PC)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-16T14:03:51+00:00
- Post Title: David Douillet Judo, .pak , (PC)

This seems very easy, first is the index of all files in the archive, all files are Zlib compressed.
i got out 5MB of DDS files from front-judo file, however the DDS files lacks a DXT header, but it should be replaceable.
## Post #3
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-05-16T14:14:41+00:00
- Post Title: David Douillet Judo, .pak , (PC)

> Reply from Strobe
>
> This seems very easy, first is the index of all files in the archive, all files are Zlib compressed.
i got out 5MB of DDS files from front-judo file, however the DDS files lacks a DXT header, but it should be replaceable.

Thanks for the very fast reply.
I actually want to extract this archive (actually many .pak archives), and then I will give them to someone that I know who is a rigger (he rigs models/skins from other games and puts them to another game).
 I know that judo.pak may not be enough, but I once I figure out how to extract those .pak files I will get all textures,models e.t.c.. 
Will this be easy? What's next?

Thanks again, in advance.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-16T14:20:58+00:00
- Post Title: David Douillet Judo, .pak , (PC)

I would think someone could easly write a BMS extractor script for this format, since nothing seems to be encrypted or anything.
So once the PAK archive for this game is solved, you should be able to open all of the paks for this game, (i would assume),
the most alarming part however is that i dont know if the DDS files will work without modification, (didnt see any model files yet),
but i have high hopes that this will be solved shortly, i could write an extractor myself, and i probably will  , but not just today!
Im so tired at the moment, so i have to continue coding tomorrow instead. ill watch this thread and see if anyone else responds.
## Post #5
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-05-16T14:33:16+00:00
- Post Title: David Douillet Judo, .pak , (PC)

> Reply from Strobe
>
> I would think someone could easly write a BMS extractor script for this format, since nothing seems to be encrypted or anything.
So once the PAK archive for this game is solved, you should be able to open all of the paks for this game, (i would assume),
the most alarming part however is that i dont know if the DDS files will work without modification, (didnt see any model files yet),
but i have high hopes that this will be solved shortly, i could write an extractor myself, and i probably will  , but not just today!
Im so tired at the moment, so i have to continue coding tomorrow instead. ill watch this thread and see if anyone else responds.

Sounds great!
Take your time, I' m not in a hurry at all (and even if I was, who cares ?).
I'm pretty sure that there are models in the game otherwise the game would be 2D not 3D.
I have no personal experiance with DDS files but I 'm pretty sure that my friend has (he has rigged Resident Evil 5 models, Crysis models, Fallout 3 models e.t.c.). I think that he won't have a problem with this unpopular game.
Once he will get the model, he can make a skeleton from it and add the needed human animations to it. It's going to be rigged to the Source engine for your information.

Thanks again!
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-17T17:33:45+00:00
- Post Title: David Douillet Judo, .pak , (PC)

So far doing great progress on this, atleast for the imagefiles that i find in the snippets. im going to make more tries on the actual
gamearchive today.

So far mostly successful conversions to TGA format, with a few exceptions, but i know why they fail, so it should be fixable.
I havent yet found any textures though, only plain bitmaps for 2D Graphics.
[rawdds_ 933889_xxxx.jpg](https://xentaxbackup.github.io/file/3048_rawdds_ 933889_xxxx.jpg)
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-17T18:25:02+00:00
- Post Title: David Douillet Judo, .pak , (PC)

Have discovered Modelfiles, dont know what format they are yet, but they share similarities of other modefiles ive seen so far,
with attributes, like head_tim_1_fx_1.fxCameraProjection.CameraPosition.light_direction.SpecularColor , so with some luck they could
be generic modelfiles.
## Post #8
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-05-17T19:36:19+00:00
- Post Title: David Douillet Judo, .pak , (PC)

> Reply from Strobe
>
> So far doing great progress on this, atleast for the imagefiles that i find in the snippets. im going to make more tries on the actual
gamearchive today.

So far mostly successful conversions to TGA format, with a few exceptions, but i know why they fail, so it should be fixable.
I havent yet found any textures though, only plain bitmaps for 2D Graphics.

> Reply from Strobe
>
> Have discovered Modelfiles, dont know what format they are yet, but they share similarities of other modefiles ive seen so far,
with attributes, like head_tim_1_fx_1.fxCameraProjection.CameraPosition.light_direction.SpecularColor , so with some luck they could
be generic modelfiles.

Good job! You 're awesome!
But maybe the files are corrupted because it's just a 2 MB sample??   
I can upload the full file(s) if you want.

By the way, I have used [3D Ripper DX](http://www.deep-shadows.com/hax/3DRipperDX.htm) and I have extracted all the shaders and textures that the game uses in one single frame! The DDS files refuse to be opened with [GIMP DDS Plug-In](http://code.google.com/p/gimp-dds/) but they do open somehow with [DXT Viewer](http://www.ozone3d.net/dxt_viewer.php).

Here are some examples from the extracted textures (DDS) from [3D Ripper DX](http://www.deep-shadows.com/hax/3DRipperDX.htm) (those are screenshots from [DXT Viewer](http://www.ozone3d.net/dxt_viewer.php)):

Part of White Gi (White judo Uniform):
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=exampletexture1.png)
Front of David Doulleit's face:
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=exampletexture2.png)
Back of the head of a judo player (can't define who he is):
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=exampletexture2.png)
Hands of a judo player (probably Doulliet):
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=exampletexture4.png)
Part of Blue Gi (Blue judo uniform)
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=exampletexture5.png)

However those files have goofy and random names. Can you please explain me what do those model files that you found mean? Is it possible to be imported to the Source engine (there is a Source SDK) or even 3DS Max or something?
Otherwise this seems pretty complex cause he has to make a model from scratch then manually put the textures on it which also seems very complex (there is no info how those textures are connected to each other). I 'm very confused.
Thanks again.

P.S.: Here are 2 examples of what the person that I know has made (rigged from other games to Source engine).:
1#
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=vindiesel.jpg)
2#
[](http://s122.photobucket.com/albums/o261/Agent-Smithy/?action=view&current=solidsnake-1.jpg).
P.S. 2: You think that he can make a model from those textures/models/shaders e.t.c. that I will extract from those archives and provide them to him?
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-21T05:35:45+00:00
- Post Title: David Douillet Judo, .pak , (PC)

Just to let you know im still looking into this!
So far been able to unpack some of the datafiles, most textures are DDS or TGA.
The reeason why this might take longer (and has taken longer than expected) is because modelfiles would be linked
to the texture name of a file, so i cannot really rip out everything blindly and hope it works.
I will need to make an extractor that preserves the original filenames in the archive. It will be done though,
but i cannot give you a deadline for it =(
## Post #10
- Username: Agent Smith
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Sep 11, 2007 6:32 pm
- Post datetime: 2010-05-21T12:43:58+00:00
- Post Title: David Douillet Judo, .pak , (PC)

> Reply from Strobe
>
> Just to let you know im still looking into this!
So far been able to unpack some of the datafiles, most textures are DDS or TGA.
The reeason why this might take longer (and has taken longer than expected) is because modelfiles would be linked
to the texture name of a file, so i cannot really rip out everything blindly and hope it works.
I will need to make an extractor that preserves the original filenames in the archive. It will be done though,
but i cannot give you a deadline for it =(

Thank you for letting me know about your progress  .
So you 're trying to make an extractor that gives the real filenames. This is great and it will save a lot of time!
It's okay, since it will be done anyway, I don't really care when exactly it will be done.
Take your time
Thanks

EDIT: There is demo of this game in case you didn't know:

```
http://www.jeuxvideopc.com/demo/demo-1533-david-douillet-judo.php
```
