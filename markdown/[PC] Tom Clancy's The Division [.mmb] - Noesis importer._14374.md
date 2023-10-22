## Post #1
- Username: tathannibal
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-20T13:57:39+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Current Version: 1.6 (08/07/2019)
1. Fix division by zero crash.
2. UV channel 2 support (not scaled properly)

Supports:
1. .MMB Version 11 files.
2. .MMB Version 10 files.
3. .MMB Version 9 files. 
4. .MMB Version 12 files. New!

Requires (or later):
Noesis v4.1777

Known issues:
1. Auto-texturing is not possible yet. It's controlled by a master resource loading file (not .mmb).
2. UVs are not properly scaled.

Note: this is an early release and thus there may be some bugs.
Due to me having no access to additional file samples. Upload any files you're having issues with so I can solve it more quickly.
[fmt_TCTD_mmb_1_6.zip](https://xentaxbackup.github.io/file/16440_fmt_TCTD_mmb_1_6.zip)
## Post #2
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-05-20T14:58:27+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Thx to you work! 

> Reply from Gh0stBlade
>
> 

Supports:
1. .MMB Version 11 files.

Requires:
Noesis v4.1777

Known issues:
1. Auto-texturing is not possible yet.
2. Skinning may be broken for some meshes.
3. Some UVs may be scaled or incorrectly extracted.
4. .MMB Version 9 files aren't fully supported yet (98% are v11).

Please note, this is an early release and thus there may be some bugs.
## Post #3
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-05-21T05:00:35+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Just found this last night, Was thinking maybe there is a possibility he will release it tomorrow, and look at that sh**. Unfortunately I can't find a model that has the correct uvs, but I'm so so so glad to view models. Hopefully next version will have fixed uvs!:) GOODWORK!
## Post #4
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2016-05-21T16:38:02+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

well yes but thanks sosososso mutch gh0st... for plugin u write couple bugs and ye som mmbs arent support but whatever ... ,,but there is example how i did it hope it helps u guys    

might render wrong som models but so far is very nice i tested couple models include

\rogue\baked\art\[characters]\_e3_2014 - ryan,megan,bronson models 

Amateur fast edit of Picture take a look at my 3mins work
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-21T18:53:30+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from mattyshido
>
> well yes but thanks sosososso mutch gh0st... for plugin u write couple bugs and ye som mmbs arent support but whatever ... ,,but there is example how i did it hope it helps u guys    

might render wrong som models but so far is very nice i tested couple models include

\rogue\baked\art\[characters]\_e3_2014 - ryan,megan,bronson models 

Amateur fast edit of Picture take a look at my 3mins work    [img.]http://i67.tinypic.com/m93mgm.jpg[/img]
Thanks for the feedback! Which mmb files aren't supported? All version 11 files should be supported. Except there are some bugs, like issues with UVs as you mentioned. The UV scale info may not be stored in the mesh files. Which models are not rendering correctly? The ones i tested look perfectly fine.

If anyone is getting crashes loading models upload the file please.

Cheers.
## Post #6
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2016-05-21T22:49:40+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Gh0stBlade
>
> mattyshido wrote:well yes but thanks sosososso mutch gh0st... for plugin u write couple bugs and ye som mmbs arent support but whatever ... ,,but there is example how i did it hope it helps u guys    

might render wrong som models but so far is very nice i tested couple models include

\rogue\baked\art\[characters]\_e3_2014 - ryan,megan,bronson models 

Amateur fast edit of Picture take a look at my 3mins work    [img.]http://i67.tinypic.com/m93mgm.jpg[/img]
Thanks for the feedback! Which mmb files aren't supported? All version 11 files should be supported. Except there are some bugs, like issues with UVs as you mentioned. The UV scale info may not be stored in the mesh files. Which models are not rendering correctly? The ones i tested look perfectly fine.

If anyone is getting crashes loading models upload the file please.

Cheers.

well i notice strikerbackpack and couple backpack dont have UV
## Post #7
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-05-21T23:58:54+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

I'm most interested in the props/vehicles. And out of 100 props I tested, rarely did I get one that had uvs, as well as the vehicles.
## Post #8
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-22T01:30:44+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Hey guys!

Thanks for the feedback. However, upload the samples where you are seeing no UVs. Otherwise I won't be able to help you (I won't ask this again).

Cheers!
## Post #9
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-05-22T02:21:18+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

First of all,

I found a pack ( I think it was you, who uploaded a pack called "ALL ASSETS FROM THE DIVISION"If not I apologize and possibly the uploader did a bad job keeping the uvs on rip. 

However, Could anyone tell me how I can rip .mmbs? Ninja Ripper doesnt work, nor does 3dRIpper, 

How Can I go about ripping all assets and textures?

Or if someone wants to do this (with proper uvs) I am willing to pay a hefty price for your time and effort!

Thanks!
## Post #10
- Username: yung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 06, 2016 12:16 pm
- Post datetime: 2016-05-22T04:57:28+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Verit0z
>
> First of all,

I found a pack ( I think it was you, who uploaded a pack called "ALL ASSETS FROM THE DIVISION"If not I apologize and possibly the uploader did a bad job keeping the uvs on rip. 

However, Could anyone tell me how I can rip .mmbs? Ninja Ripper doesnt work, nor does 3dRIpper, 

How Can I go about ripping all assets and textures?

Or if someone wants to do this (with proper uvs) I am willing to pay a hefty price for your time and effort!

Thanks!
If you have all the files from the Division as .mmb's, you just go download a free program called Noesis, put the attachment in the first post in it's plugins/python folder, and launch Noesis. From there, you can open just about any .mmb file.
## Post #11
- Username: Timberley
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 01, 2016 3:17 am
- Post datetime: 2016-05-23T20:50:52+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Awesome stuff Ghost, thanks for this!    

One interesting thing that I have noticed, applying this to my own extracted files, is that for some reason the models are mirrored about the X-axis (I think) compared to how they appear in-game.  I noticed the same thing when I tried using NinjaRipper too.  I do wonder what's going on there!

But, keep up the awesome work!
## Post #12
- Username: cameleot
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-26T13:38:41+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Ok so, 1.4 script is available. Supports mesh versions 9 and 10. UVs should be fixed *i hope.

Also, if you want to view the highest or a specific lod level. You can alter the script. There's a little option for that:

```
lodToExtract = 0					#Force load specific lod level (0 = High, 1 = Mid, 2 = Normal, 3 = Low)

```


So to load the highest lod level you would just set bExtractSpecificLod to true.

> Reply from Timberley
>
> Awesome stuff Ghost, thanks for this!    

One interesting thing that I have noticed, applying this to my own extracted files, is that for some reason the models are mirrored about the X-axis (I think) compared to how they appear in-game.  I noticed the same thing when I tried using NinjaRipper too.  I do wonder what's going on there!

But, keep up the awesome work!

Not sure why that's happening. It's not an issue with the importer since there is no flipping applied.
## Post #13
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-05-29T15:04:12+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

if someone could extract all textures/models with (working UV coordinates) All the models I have are either black textured, or the uvs are completely messed up. 

Thanks
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-30T01:02:53+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Verit0z
>
> if someone could extract all textures/models with (working UV coordinates) All the models I have are either black textured, or the uvs are completely messed up. 
Thanks

Have you tried the latest plugin? Upload the .mmb file you are having issues with.

Cheers.
## Post #15
- Username: cameleot
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 21, 2011 1:42 am
- Post datetime: 2016-05-31T12:58:17+00:00
- Post Title: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Any idea where buildings' textures are located at? Most of the texture files inside the [buildings] folder are AO and normalmap texture files but I couldn't find any actual textures the buildings use.
## Post #16
- Username: Fluttershy
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-31T13:22:10+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from cameleot
>
> Any idea where buildings' textures are located at? Most of the texture files inside the [buildings] folder are AO and normalmap texture files but I couldn't find any actual textures the buildings use.

I took a look at the resource loading file. One of the building models is using textures from "rogue\baked\art\[assets]\[generictexture]" Not sure if it includes them all though.

Regards.
## Post #17
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-06-01T00:58:44+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Okay, heres the requested you asked for.

I have all assets/textures
but
every model has jacked up uvs, doesnt make any difference between reversing or not.

the uvs are 20x smaller than anything it appears, they just dont work. if you could tell me how I can fix uvs on models like this.
that'd be amazing.

gas pump:
[https://www.dropbox.com/s/wpzm7p4hjcipe ... p.fbx?dl=0](https://www.dropbox.com/s/wpzm7p4hjcipe9v/Gas%20Pump.fbx?dl=0)

gas pump texture:
[https://www.dropbox.com/s/s4ai621my8z8p38/999.jpg?dl=0](https://www.dropbox.com/s/s4ai621my8z8p38/999.jpg?dl=0)
## Post #18
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-06-01T07:06:23+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Verit0z
>
> Okay, heres the requested you asked for.

I have all assets/textures
but
every model has jacked up uvs, doesnt make any difference between reversing or not.

the uvs are 20x smaller than anything it appears, they just dont work. if you could tell me how I can fix uvs on models like this.
that'd be amazing.

gas pump:
https://www.dropbox.com/s/wpzm7p4hjcipe ... p.fbx?dl=0

gas pump texture:
https://www.dropbox.com/s/s4ai621my8z8p38/999.jpg?dl=0

Hi,

Can you please be more descriptive on how you are obtaining these models. You say:

> every model has jacked up uvs, doesnt make any difference between reversing or not.

There is a definite improvement with UVs for the latest plugin I wrote. I cannot guarantee that UVs are fine for all models but they should be.

Sadly, the files you uploaded aren't of use to me, I did ask you to upload the .mmb file not any exported output.

Cheers.
## Post #19
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-06-01T13:03:47+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

As requested, heres the gas pump
unedited. 

.MMB file

[https://www.dropbox.com/s/7g7y23xg10jrm ... a.mmb?dl=0](https://www.dropbox.com/s/7g7y23xg10jrmxa/pr9020_a.mmb?dl=0)
## Post #20
- Username: Timberley
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 01, 2016 3:17 am
- Post datetime: 2016-06-01T20:54:07+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Gh0stBlade
>
> 

Not sure why that's happening. It's not an issue with the importer since there is no flipping applied.

No, I suspect it's something in the game code itself.  It was more a bit of a PSA for those using the script to not jump to conclusions when the models seem mirrored!
## Post #21
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-06-02T12:53:50+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Some of your UVs are broken because you aren't scaling the SNORM ones.

As for the mirroring, that's just an engine coordinate system thing.
## Post #22
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-06-03T03:02:13+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Please do advise on how to fix the uvs? SNORM? Whats that and how do I fix them? Thank you!:!
## Post #23
- Username: ryouga
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 07, 2016 11:10 pm
- Post datetime: 2016-06-07T15:11:44+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Hi guys, wow you are sorcerers!
Do you think there is a way to have the city on an .obj model or something like that? textures don't matter. It would be extremely usefull to me but I have no idea of 3d software beyond google sketchup.
## Post #24
- Username: Verit0z
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 15, 2013 4:34 am
- Post datetime: 2016-06-07T21:59:20+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from ryouga
>
> Hi guys, wow you are sorcerers!
Do you think there is a way to have the city on an .obj model or something like that? textures don't matter. It would be extremely usefull to me but I have no idea of 3d software beyond google sketchup.

Considering all buildings are mostly made up of pieces that are put together like a puzzle ...good luck lol you'd have to build the city and that'd be very very hard
## Post #25
- Username: mattyshido
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2016 2:55 am
- Post datetime: 2016-07-12T07:54:11+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Backpacks need UVs none of backpack have it :/
## Post #26
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-12T13:34:21+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from mattyshido
>
> Backpacks need UVs none of backpack have it :/
File sample? They're probably there, just not upscaled.
## Post #27
- Username: lxxxk
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 02, 2014 1:33 pm
- Post datetime: 2016-07-12T23:23:09+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Buildings need UVs fix 

Buildings UVs are broken
## Post #28
- Username: gravicapot
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 09, 2016 8:36 pm
- Post datetime: 2016-12-22T02:04:01+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Please tell me how you got to unpack the archive and get the weapon models, characters and so on.   I used rouge_sdf_v2. The only files with extension .mmb this decoration, the railway.
What is the format w_lmg_sa80_t1.mgraphobject?
## Post #29
- Username: gravicapot
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-12-22T12:38:27+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from gravicapot
>
> Please tell me how you got to unpack the archive and get the weapon models, characters and so on.   I used rouge_sdf_v2. The only files with extension .mmb this decoration, the railway.
What is the format w_lmg_sa80_t1.mgraphobject?
You are most likely looking in the wrong folders or didn't fully extract the sdf archives.
## Post #30
- Username: noirfx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 03, 2017 11:21 pm
- Post datetime: 2017-03-11T17:00:40+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

I have a problem with backpacks uv's. It looks like 90% of them (except few backpacks from dlc) are broken.
Here's how it looks:

[](http://piccy.info/view3/10941772/9595daf958699e943e94e3c58f23ae9c/)[](http://i.piccy.info/a3c/2017-03-11-17-00/i9-10941772/240x161-r)


I've tried several formats and export/import options, nothing works. Can we do something with this?

Some examples - [http://www.mediafire.com/file/bjfjp9trt ... ckpack.rar](http://www.mediafire.com/file/bjfjp9trtba66i7/backpack.rar)

Btw, I had this kind of problems when I ripped models with ninja ripper from other games after I entered wrong uv coords in 3ds max ninjaripper exporter.
## Post #31
- Username: Terra854
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 16, 2017 12:46 pm
- Post datetime: 2017-10-16T04:54:26+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Hello. Is there any updates to the tool?

EDIT: Also I am having problems opening .mmb files extracted from the game "The Fractured but Whole". It errors out with "TypeError: an integer is required". If you want, I can send some samples to you to help you to debug the problem
## Post #32
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-10-17T21:23:29+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Terra854
>
> Hello. Is there any updates to the tool?

EDIT: Also I am having problems opening .mmb files extracted from the game "The Fractured but Whole". It errors out with "TypeError: an integer is required". If you want, I can send some samples to you to help you to debug the problem

Then provide samples!
## Post #33
- Username: Terra854
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 16, 2017 12:46 pm
- Post datetime: 2017-10-18T10:14:32+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Here you go.

[https://mega.nz/#!FBFX0YZQ!ok17CZtckaqx ... 8yS2fHdcAA](https://mega.nz/#!FBFX0YZQ!ok17CZtckaqxaciPpLbSnxlNuE5BiZxE18yS2fHdcAA)

And just an update, the mmb files gives out a fileType of 203, so i added the highlighted portion to the script:



Now it errors out with this:

Traceback (most recent call last):
  File "C:\Users\Ben\Downloads\noesisv4294\plugins\python\fmt_TCTD_mmb.py", line 388, in mmbLoadModel
    mesh.loadmmbFile()
  File "C:\Users\Ben\Downloads\noesisv4294\plugins\python\fmt_TCTD_mmb.py", line 173, in loadmmbFile
    meshName = bs.readBytes(bs.readUShort()).decode("ASCII").rstrip("\0")
UnicodeDecodeError: 'ascii' codec can't decode byte 0xbf in position 1: ordinal not in range(128)

I get the same ordinal not in range error for the rest of the mmb files that I have.

I have also provided 2 extra files, same name but ending in cameldata and editordata respectively cause I suspect that they contain texture information. Also, every single mmb file has it's accompanying cameldata and editordata file.
## Post #34
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-10-20T17:43:34+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Terra854
>
> Here you go.

https://mega.nz/#!FBFX0YZQ!ok17CZtckaqx ... 8yS2fHdcAA

And just an update, the mmb files gives out a fileType of 203, so i added the highlighted portion to the script:



Now it errors out with this:

Traceback (most recent call last):
  File "C:\Users\Ben\Downloads\noesisv4294\plugins\python\fmt_TCTD_mmb.py", line 388, in mmbLoadModel
    mesh.loadmmbFile()
  File "C:\Users\Ben\Downloads\noesisv4294\plugins\python\fmt_TCTD_mmb.py", line 173, in loadmmbFile
    meshName = bs.readBytes(bs.readUShort()).decode("ASCII").rstrip("\0")
UnicodeDecodeError: 'ascii' codec can't decode byte 0xbf in position 1: ordinal not in range(128)

I get the same ordinal not in range error for the rest of the mmb files that I have.

I have also provided 2 extra files, same name but ending in cameldata and editordata respectively cause I suspect that they contain texture information. Also, every single mmb file has it's accompanying cameldata and editordata file.

Ah ok, I mis-read. I thought these files came from the same game (Tom Clancy's The Division). Anyway, I have no plans to alter the script to support that game. By looking, it shouldn't be hard since the formats are close. I just don't have the time to do it. The files you provided don't have version info, that's why you get weird version numbers.

Cheers.
## Post #35
- Username: Terra854
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 16, 2017 12:46 pm
- Post datetime: 2017-11-25T06:33:52+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Gh0stBlade
>
> Terra854 wrote:Here you go.

https://mega.nz/#!FBFX0YZQ!ok17CZtckaqx ... 8yS2fHdcAA

And just an update, the mmb files gives out a fileType of 203, so i added the highlighted portion to the script:



Now it errors out with this:

Traceback (most recent call last):
  File "C:\Users\Ben\Downloads\noesisv4294\plugins\python\fmt_TCTD_mmb.py", line 388, in mmbLoadModel
    mesh.loadmmbFile()
  File "C:\Users\Ben\Downloads\noesisv4294\plugins\python\fmt_TCTD_mmb.py", line 173, in loadmmbFile
    meshName = bs.readBytes(bs.readUShort()).decode("ASCII").rstrip("\0")
UnicodeDecodeError: 'ascii' codec can't decode byte 0xbf in position 1: ordinal not in range(128)

I get the same ordinal not in range error for the rest of the mmb files that I have.

I have also provided 2 extra files, same name but ending in cameldata and editordata respectively cause I suspect that they contain texture information. Also, every single mmb file has it's accompanying cameldata and editordata file.

Ah ok, I mis-read. I thought these files came from the same game (Tom Clancy's The Division). Anyway, I have no plans to alter the script to support that game. By looking, it shouldn't be hard since the formats are close. I just don't have the time to do it. The files you provided don't have version info, that's why you get weird version numbers.

Cheers.

Is it possible to tell me how the file is structured? Like maybe post a struct or something? And I am having problems with altering the script as I am not experienced in Python
## Post #36
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-01-24T19:21:35+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Gh0stBlade
>
> 

Current Version: 1.4 (26/05/2016)
1. MMB Version 9 support added.
2. MMB Version 10 support added.
3. UVs should be fixed.

Supports:
1. .MMB Version 11 files.
2. .MMB Version 10 files. New!
3. .MMB Version 9 files. New!

Requires:
Noesis v4.1777

Known issues:
1. Auto-texturing is not possible yet. It's controlled by a master resource loading file (not .mmb).
2. UVs are not properly scaled.

Note: this is an early release and thus there may be some bugs.
Due to me having no access to additional file samples. Upload any files you're having issues with so I can solve it more quickly.
fmt_TCTD_mmb.py is not working properly.
all models have weight and bone  problems.I tried different methods but it was not successful.

Have you made a correction or are you going to do it?
Thanks in advance
## Post #37
- Username: Loginoux
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-01-24T20:40:30+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from TSelman61X
>
>             Gh0stBlade wrote:

Current Version: 1.4 (26/05/2016)
1. MMB Version 9 support added.
2. MMB Version 10 support added.
3. UVs should be fixed.

Supports:
1. .MMB Version 11 files.
2. .MMB Version 10 files. New!
3. .MMB Version 9 files. New!

Requires:
Noesis v4.1777

Known issues:
1. Auto-texturing is not possible yet. It's controlled by a master resource loading file (not .mmb).
2. UVs are not properly scaled.

Note: this is an early release and thus there may be some bugs.
Due to me having no access to additional file samples. Upload any files you're having issues with so I can solve it more quickly.
fmt_TCTD_mmb.py is not working properly.
all models have weight and bone  problems.I tried different methods but it was not successful.

Have you made a correction or are you going to do it?
Thanks in advance

You'll probably want to cut that attitude.
## Post #38
- Username: Eda61
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 08, 2017 4:05 pm
- Post datetime: 2018-01-25T21:55:39+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Gh0stBlade
>
> 
You'll probably want to cut that attitude.[/quote][/quote]

Why,
Everything was going very well. it's just a little problem, it must be a problem to be solved.
after all, you can not have made up for it that much.
## Post #39
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-06-27T08:11:25+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Gh0stBlade, since second part being announced and most of the content for the first part were released it is possible you get back to this project?
just to update plugin. model are really cool

thanks in advanced  

edit: though I have issues with beta .mmb — issue with weights: [https://drive.google.com/open?id=1HY6YK ... SEEz7BKpeK](https://drive.google.com/open?id=1HY6YKo2VgGg0i6sZ_R-iAjSEEz7BKpeK)
## Post #40
- Username: Faithfullfaun
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-07-06T00:54:10+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

New script version released thanks to Sir Kane and Chrrox!

Includes various fixes:
TCTD2 support, UV fixes and Weighting issues should be fixed.
## Post #41
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-07-06T16:36:47+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

I've tried many models. I think it works now. 
Really great, man. Thanks
## Post #42
- Username: Faithfullfaun
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-07-08T15:21:40+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

New version 1.6 script available, should fix a crash.
## Post #43
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-07-13T19:42:51+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Do you still take in issues on the plugin for the division?

It's a vehicle and it may be some kind of scaling issue?
The body is very small compared to the bones and glass

Here is the location and name of the file

Vehicle: vh8002a.mmb
Path is: rogue\baked\art\[assets]\[vehicles]\vh8002

I can also send it if needed
## Post #44
- Username: frosty7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 11, 2019 7:06 am
- Post datetime: 2019-10-16T13:13:12+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Exported meshes have broken normals unfortunately :/ is there any fix for that or I'm doing something wrong?
## Post #45
- Username: vegasfest56
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 26, 2019 11:38 pm
- Post datetime: 2022-02-23T23:43:11+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

How do you apply the textures on extracted models? Everytime to I try to apply textures, they either look broken or it doesn't work at all.
## Post #46
- Username: vegasfest56
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 26, 2019 11:38 pm
- Post datetime: 2022-03-11T21:40:14+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Where do you find the master resource loading file? I'm trying to find Larae Barrett's scarf and hat/beanie texture

Edit: Also the Riker Sniper has messed up UV maps
## Post #47
- Username: DJFox11
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 10, 2022 2:36 pm
- Post datetime: 2022-04-10T06:46:30+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

Hi,
I know this quite an old post, but I needed a .MMB importer for Noesis and found this. Anyway, whenever I import and .MMB file I get an error like this. Any ideas?



Screenshot 2022-04-10 164432.png (22.7 KiB) Viewed 204 times


Cheers.
DJFox11
## Post #48
- Username: vegasfest56
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 26, 2019 11:38 pm
- Post datetime: 2022-04-22T12:38:04+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

I know this will probably be in vain since the person who worked on this probably isn't active anymore. But please see the link below for samples of files that have extremely small UVs

[https://www.mediafire.com/file/fj47fwb6 ... s.zip/file](https://www.mediafire.com/file/fj47fwb6vtcr6m1/BrokenUVs.zip/file)
## Post #49
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2023-01-24T07:39:28+00:00
- Post Title: Re: [PC] Tom Clancy's The Division [.mmb] - Noesis importer.

> Reply from Gh0stBlade ↑Fri May 20, 2016 9:57 pm at Fri May 20, 2016 9:57 pm
>
> 
Note: this is an early release and thus there may be some bugs.
Due to me having no access to additional file samples. Upload any files you're having issues with so I can solve it more quickly.

Hello, thak you for this script. Do you have any plans to work with skeletal animations export?
