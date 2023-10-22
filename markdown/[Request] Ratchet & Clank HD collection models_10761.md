## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-08T06:54:43+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

Can anyone make a script to help extract the models from the ratchet and clank hd collection? I looked through R&C1-3+DL and they all seem to have the same file structure. Textures are in *.vram and models are in some of the *.ps3 (most models seem to be in the engine.ps3) files.
ps23dformat has a script that works on R&C1 HD but not on the others and it only extracts the first model in the engine.ps3 file. you can find the script here [http://ps23dformat.wikispaces.com/Non+PS2+Games](http://ps23dformat.wikispaces.com/Non+PS2+Games)

Can some one try to build on that to extract all the models, and maybe support the other games in the collection?
If anyone needs any files I can pm some to them.
## Post #2
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-09T04:32:10+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

Is there anything anybody needs to get started on this?

I got parts of the engine files from each of the games if anyone wants to look at them. I'm not sure if it will help much, but I hope it will.

[https://www.dropbox.com/sh/6pw9eys15bp0v8i/tSBD0wPar6](https://www.dropbox.com/sh/6pw9eys15bp0v8i/tSBD0wPar6)

Edit:
Well I found out that the textures are headerless dxt3 files. Also I looked through some files in R&C3 hd and I think the mobyload#.ps3 files could have models as well. 
In the level23 folder I found this texture in mobyload2.ps3

It's chauffeur ratchet from one of the secret agent clank cutscenes.
I split and added part of the mobyload2.ps3 to the link above if anyone wants to look at it.
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-09-11T07:38:55+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

You need to be more specific with what you have posted though. At the moment you've posted on a few files but it's quite suggestive in the filename that they could be either split or are each part of a different game within the collection as it's related to the "engine".

I could take a look which would only require proper file distinctions between the games, named individually, categoryised by game and full file samples. I'd also be interested in seeing a file directory listing too.

I can see that one of the files you provided did contain a model when i checked well, a few (probably split up). But i feel that other files could be of more use than these ones and without other samples from the same game, extraction isn't going to be possible.
## Post #4
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-11T09:16:52+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

Whoops. Yeah, all the files I posted were spit and the ones labeled rac1engine, rac2engine, ect. were from the first level of each game.

I thought it was against the rules to post full files?

anyway here is a bunch of stuff I already uploaded for ps23dformat to look at

[https://www.dropbox.com/sh/yvabdxvu94xgquv/rzgWIECHbx](https://www.dropbox.com/sh/yvabdxvu94xgquv/rzgWIECHbx)
it's just the first few files from the first couple levels.

the file structure for all 4 games looks pretty muck like this


Inside the global folder is stull like the hud, the transition files for when you travel, basically stuff that should get loaded in every level.
inside the scene folders are chunk#.ps3 files wich are all no more than 200kb each.

There not much difference between games other than the later ones having more level folders.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-12T09:39:25+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

[](http://www.pic-upload.de/view-20698688/mobyload2.jpg.html)

Cut some faces (seems too many) because there was some mess.
Format of this model (mobyload2) being rather simple: 40 bytes vertex block,
3 floats vertices, 3 floats normals, 2 floats tex coords, 2 DWORDs
WORD faceIndices for triangles: f1 f2 f3

(all values big endian, means high byte/low byte order)

well, 2nd try: [](http://www.pic-upload.de/view-20698867/mobyload2_.jpg.html)

[](http://www.pic-upload.de/view-20699357/mobyload3_SM2.jpg.html)
## Post #6
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-12T11:08:30+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

Amazing. Any chance on getting a script to get the models in a usable format?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-12T11:31:25+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> Amazing. Any chance on getting a script to get the models in a usable format?Wavefront obj being a useable format (?) [http://www.uploadmb.com/dw.php?id=1378986342](http://www.uploadmb.com/dw.php?id=1378986342)
loadable in blender 2.66 for example (in blender 2.49 I didn't see them)
Again: normals included but not "addressed" by faces.

I don't code scripts; preferring "C". An exporter should be no problem but I'm just working on one for SleepingDogs.

The problem is always (well, mostly) to get an universal solution. This can be very time wasting.
(While it's often very simple to get the obj for one single model.) 

I gave the format so anyone with some scripting skills should be able to code a script.
## Post #8
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-12T11:49:41+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

Yeah anything that can load in blender or 3ds max works for me.

Well if you aren't able to do it, maybe someone else can. I've been trying to get the ratchet and clank models for almost a year and a half now.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-12T12:01:22+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> I've been trying to get the ratchet and clank models for almost a year and a half now.Here on Xentax? Can't believe this.

My flat rate limit is nearly reached so if you uploaded up to 10 *.ps3 models of your choice (zipped < 5 MB) I might have a look at them next week or so (if noone other cares). 

(There are two objs in my previous post.)
## Post #10
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-12T12:37:23+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> o0DemonBoy0o wrote:I've been trying to get the ratchet and clank models for almost a year and a half now.Here on Xentax? Can't believe this.

My flat rate limit is nearly reached so if you uploaded up to 10 *.ps3 models of your choice (zipped < 5 MB) I might have a look at them next week or so (if noone other cares). 

(There are two objs in my previous post.)

Well it started out with trying to get the models from the orginal ps2 games over at ps23dformat
[http://ps23dformat.wikispaces.com/share ... d=64974480](http://ps23dformat.wikispaces.com/share/view/53390612?replyId=64974480)
I posted on here once to but i don't think anyone could do anything because of the games *.wad format.

Just recently I decided to look at the files in the Ratchet & Clank hd collection.

Well those two models are of Clank and Sasha so i'm pretty happy about that. if you want to go ahead and get a couple more models for me, these are the 10 that I would want the most. 
[https://www.dropbox.com/s/klutvp6nc5n2iz1/files.rar](https://www.dropbox.com/s/klutvp6nc5n2iz1/files.rar)
I'm sure these files should have the models I want in them

Thanks again!
## Post #11
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-13T14:33:46+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

I'm reversing texture files from Ratchet and Clank QForce





I took a look at those .vram .ps3 files still trying to figure those out but anyway ill post what i find
## Post #12
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-13T15:03:46+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

> Reply from cra0
>
> 
I took a look at those .vram .ps3 files still trying to figure those out but anyway ill post what i find

All textures in the hd collection are dxt3 with no headers. They are usually separated by a line of 0's, but not always, like so



I made a small script to separate the textures and from there I use texturefinder to save them.
## Post #13
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-13T15:14:13+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> cra0 wrote:
I took a look at those .vram .ps3 files still trying to figure those out but anyway ill post what i find

All textures in the hd collection are dxt3 with no headers. They are usually separated by a line of 0's, but not always, like so



I made a small script to separate the textures and from there I use texturefinder to save them.

Ah the pixel size and depth should be somewhere around if I can find that extracting them all would be easy.

Ok ty for that info going to take a closer look later

textures look good in 512 as apposed to the ps2 ones which are 128

-edit-
ok textures for Qforce are donish
## Post #14
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-16T15:15:21+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

So is there anyone that can help with getting these models? Extracting the models from the hd collection would be way better than my old method of getting the model through the ps2 games with pcsx2.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-16T22:17:28+00:00
- Post Title: [Request] Ratchet & Clank HD collection models

keep cool - things take time:
[](http://www.pic-upload.de/view-20747283/wrench.jpg.html)
## Post #16
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-16T22:34:40+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> keep cool - things take time:

Yeah I know, sorry about that. I was hoping someone could find a way to get the models with a bms script or some kind of program rather than having to do it manually. 
That's some good work right there though. I appreciate it shakotay2.
## Post #17
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-16T23:23:51+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> keep cool - things take time:

Can you share a little bit more info on the format. Great work man!!!

I'm writting a tool to extract the streaming archives the image info is apparently stored in the .ps3 files along with the model data. No idea about the big texture packs though header seems different.

-EDIT-
ok completely figured out the texture streaming format
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-17T13:37:04+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> I was hoping someone could find a way to get the models with a bms script or some kind of program rather than having to do it manually.I like to repeat:
while it's often easy to do it for a single model it can be very time consuming to get a universal solution.

That's the reason why some coders (like me) bother creating a program.
An intermediate solution would be to let the user chose between params in the program.
(Means leaving some efforts to the user.)
But many user can't handle that - they just want the universal solution.  

I'm working on a version that can handle your armors at least. But from armor6 on it's required
to use a damned param what I'm tired to acquire automatically:
[](http://www.pic-upload.de/view-20750769/PS3_armor7.jpg.html)

> Reply from cra0
>
> Can you share a little bit more info on the format. Great work man!!!
Thx - (it would be great if I had a universal solution, though  ).

For wrench2.ps3 the format is very simple:
[](http://www.pic-upload.de/view-20750768/PS3_wrench.jpg.html)
All values big endian!
DWORD verts start, DWORD face indices start (there: 3 uint16 f1,f2,f3)
From 0x80 (verts block start): 3 floats x,y,z vertices - 3 floats normals - 2 floats texture coords x,y
2 DWORDs to skip

edit: 045C is the vertices count
## Post #19
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-17T14:34:51+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> o0DemonBoy0o wrote:I was hoping someone could find a way to get the models with a bms script or some kind of program rather than having to do it manually.I like to repeat:
while it's often easy to do it for a single model it can be very time consuming to get a universal solution.

That's the reason why some coders (like me) bother creating a program.
An intermediate solution would be to let the user chose between params in the program.
(Means leaving some efforts to the user.)
But many user can't handle that - they just want the universal solution.  

I'm working on a version that can handle your armors at least. But from armor6 on it's required
to use a damned param what I'm tired to acquire automatically:

cra0 wrote:Can you share a little bit more info on the format. Great work man!!!
Thx - (it would be great if I had a universal solution, though  ).

For wrench2.ps3 the format is very simple:

All values big endian!
DWORD verts start, DWORD face indices start (there: 3 uint16 f1,f2,f3)
From 0x80 (verts block start): 3 floats x,y,z vertices - 3 floats normals - 2 floats texture coords x,y
2 DWORDs to skip

edit: 045C is the vertices count

Universal solution tell me about it man there are like 5 different types of texture archives I have come across   doing checks for each one hopefully I don't see any more differences. Thanks for that info your doing a great job!
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-17T16:32:41+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

This is a tiny mesh exporter for some models:
[http://www.uploadmb.com/dw.php?id=1379435242](http://www.uploadmb.com/dw.php?id=1379435242)

(Seems to get the "wrong" model from nefariousmobyload2.ps3
as there seem to be several models contained in some ps3 files.)

edit: last version to be found here:
[viewtopic.php?f=16&t=10788](http://forum.xentax.com/viewtopic.php?f=16&t=10788)
## Post #21
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-17T17:24:56+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Awesome. Your program seems to work on most, if not all, the armor files and some of the mobyload files. It seems to hate files with multiple models in them, though that's fine. 

Thanks again Shakotay.
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-18T09:30:44+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

[](http://www.pic-upload.de/view-20758446/nefarious.jpg.html)

wavefront obj
[http://www.uploadmb.com/dw.php?id=1379496368](http://www.uploadmb.com/dw.php?id=1379496368)
## Post #23
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-18T09:58:46+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> 

wavefront obj
http://www.uploadmb.com/dw.php?id=1379496368

I get an error importing the decompiled obj in 3ds max says invalid vert list. It opens in Noesis however the smoothing and faces are completely broken ;(
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-18T10:27:47+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from cra0
>
> I get an error importing the decompiled obj in 3ds max says invalid vert list.With blender 2.66 there is no such error. I can't fix this if you can't specify the error.

> It opens in Noesis however the smoothing and faces are completely broken ;(The smoothing prob is present in blender, too. But I didn't change anything in the data. It's just presented as it is in the files:
f 1 2 3
f 2 3 4
f 3 4 5

it may vary like this:
f 73 74 75
f 74 75 76
f 75 76 61
f 76 61 62
f 77 78 79

i.e. there's some kind of break in the continous face indices sequence 
in the last three faces.

First I was thinking of tri strips but seems it's not.

edit: in Noesis you can simply press F4 (toggle face cull) and then File Export from preview
## Post #25
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-18T11:33:06+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> 

wavefront obj
http://www.uploadmb.com/dw.php?id=1379496368

The model is actually easier to use without the UV overlap. The model uses two textures and it's easier for me to separate the mesh when the two uv maps are separate, but that may just be me.

Your program is pretty great. Fiddling around with a hex editor I got it to export models when it said it couldn't although it's usually missing a couple faces.

[](http://www.pic-upload.de/view-20759157/models.png.html)
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-18T11:39:22+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> The model is actually easier to use without the UV overlap. The model uses two textures and it's easier for me to separate the mesh when the two uv maps are separate, but that may just be me.Nice to hear. Could you upload the two textures for the nefariousmobyload2.ps3, please?

btw: which 3D program do you use for displaying the objs?
## Post #27
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-18T12:06:30+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> cra0 wrote:I get an error importing the decompiled obj in 3ds max says invalid vert list.With blender 2.66 there is no such error. I can't fix this if you can't specify the error.
 It opens in Noesis however the smoothing and faces are completely broken ;(The smoothing prob is present in blender, too. But I didn't change anything in the data. It's just presented as it is in the files:
f 1 2 3
f 2 3 4
f 3 4 5

it may vary like this:
f 73 74 75
f 74 75 76
f 75 76 61
f 76 61 62
f 77 78 79

i.e. there's some kind of break in the continous face indices sequence 
in the last three faces.

First I was thinking of tri strips but seems it's not.

edit: in Noesis you can simply press F4 (toggle face cull) and then File Export from preview
Ah yeah that works I'm playing around with the format myself too see why its doing that 

btw parsed all the texture structures
## Post #28
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-18T12:10:25+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> Nice to hear. Could you upload the two textures for the nefariousmobyload2.ps3, please?

btw: which 3D program do you use for displaying the objs?

sure
[](http://www.pic-upload.de/view-20759381/nefarious1.png.html)
[](http://www.pic-upload.de/view-20759382/nefarious2.png.html)

For the picture above? I used noesis. I use it to make sure the models came out ok before editing them in 3ds max.
Also nefariousmobyload2 is actually supposed to be named just mobyload2 in case you didn't know. I had a few of them in a folder and i renamed them to tell them apart.

> Reply from cra0
>
> 
Ah yeah that works I'm playing around with the format myself too see why its doing that 

btw parsed all the texture structures

Nice. Does it work with the engine.vram files?
## Post #29
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-18T12:35:07+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> shakotay2 wrote:Nice to hear. Could you upload the two textures for the nefariousmobyload2.ps3, please?

btw: which 3D program do you use for displaying the objs?

sure



For the picture above? I used noesis. I use it to make sure the models came out ok before editing them in 3ds max.
Also nefariousmobyload2 is actually supposed to be named just mobyload2 in case you didn't know. I had a few of them in a folder and i renamed them to tell them apart.
cra0 wrote:
Ah yeah that works I'm playing around with the format myself too see why its doing that 

btw parsed all the texture structures


Nice. Does it work with the engine.vram files?

yeah wad0.vram etc also works
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-18T13:19:24+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> shakotay2 wrote:Nice to hear. Could you upload the two textures for the nefariousmobyload2.ps3, please?

sureThx!  
Well, in blender's texture paint view it doesn't look very nice.  
But I didn't find the "face culling button" in blender so far...
## Post #31
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-19T15:21:37+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Ok done please test it out and get back to me it should support all the texture archive formats.


[http://cra0kalo.com/public/R%26C_Textool.zip](http://cra0kalo.com/public/R%26C_Textool.zip)
## Post #32
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-19T16:23:45+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Sweet those armor models are looking great!
## Post #33
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-19T20:29:17+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from cra0
>
> 

Ok done please test it out and get back to me it should support all the texture archive formats.

I just finished testing it and it works great. It doesn't seem to work on the mobyload or the dealocked files though.
Everything else is fine though. 


Also great tool shakotay. Any chance of supporting the engine.ps3 files? I would love to get my hands on the level terrain.
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-19T23:05:59+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

atm I feel finished.  - maybe in two weeks or so.
## Post #35
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-20T03:05:01+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> cra0 wrote:

Ok done please test it out and get back to me it should support all the texture archive formats.


I just finished testing it and it works great. It doesn't seem to work on the mobyload or the dealocked files though.
Everything else is fine though. 


Also great tool shakotay. Any chance of supporting the engine.ps3 files? I would love to get my hands on the level terrain.
Could you pm me some of those dreadlock files
## Post #36
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-21T09:11:46+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

ty for files

(updated to v1.1) – supports Ratchet Deadlock
[http://cra0kalo.com/public/R%26C_Textool.zip](http://cra0kalo.com/public/R%26C_Textool.zip)
## Post #37
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2013-09-29T21:07:28+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Nice Tool But is there a way to Calculate the Normals wen converting to OBJ??

Also is there a way to Pull models out of the VRam.ps3 or Engine.ps3...

Trying to get Courtney Gears (Stage21) the Moby's only have Clank and Skidd/MechaSkidd
## Post #38
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-09-29T21:16:12+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from Arymond
>
> Nice Tool But is there a way to Calculate the Normals wen converting to OBJ??

Also is there a way to Pull models out of the VRam.ps3 or Engine.ps3...

Trying to get Courtney Gears (Stage21) the Moby's only have Clank and Skidd/MechaSkidd

The vram files only contain textures. 

Anyway, I found a way to rip just about anything, It just involves some hex editing and the first revision of shatokay's tool.
## Post #39
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2013-09-29T21:21:21+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

is said tool in this topic?

and if you can show my the places to cut in hex that'd be real cool!
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-30T09:34:07+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from Arymond
>
> Nice Tool But is there a way to Calculate the Normals wen converting to OBJ??In blender 2.66, Wavefornt obj export, check Include Normals check box in the Export obj menu. You may have to recalculate the normals before in (edit mode, mesh tools, normals)

> Also is there a way to Pull models out of the VRam.ps3 or Engine.ps3...For engine.ps3 there is. But I'm rather busy atm.
## Post #41
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-30T10:42:21+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> Arymond wrote:Nice Tool But is there a way to Calculate the Normals wen converting to OBJ??In blender 2.66, Wavefornt obj export, check Include Normals check box in the Export obj menu. You may have to recalculate the normals before in (edit mode, mesh tools, normals)
Also is there a way to Pull models out of the VRam.ps3 or Engine.ps3...For engine.ps3 there is. But I'm rather busy atm.

Ill take a look at the format after im done writing my .bdae mesh exporter
## Post #42
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-10-17T11:31:11+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

I don't suppose you guys have any update on getting the level terrain? 
Would it be to much trouble to ask you guys to see if you can get the models from the Jak and Daxter HD Collection?
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-17T19:01:32+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> I don't suppose you guys have any update on getting the level terrain?Not really.
As you know I made a research on rac1engine.ps3 and only found a sphere so far.
But I'm working on a "noob's tool for getting meshes". Maybe (not sure) it can be used for getting level meshes.
(I will test this as soon as I'm done with the tool.)

> Would it be to much trouble to ask you guys to see if you can get the models from the Jak and Daxter HD Collection?"trouble?" - who knows?  If you uploaded 2 or three samples I could give an answer, I guess.

(Again my flat rate has run "off limit". So small zips/rars (<5MB) please due to my 10kByte/s download atm.)
## Post #44
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-10-17T20:17:36+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> Not really.
As you know I made a research on rac1engine.ps3 and only found a sphere so far.
But I'm working on a "noob's tool for getting meshes". Maybe (not sure) it can be used for getting level meshes.
(I will test this as soon as I'm done with the tool.)
well I know for sure that 3dformat, I think he's known as furryfan here, has gotten the level terrain. i just don't know how.


> Reply from shakotay2
>
> "trouble?" - who knows?  If you uploaded 2 or three samples I could give an answer, I guess.

(Again my flat rate has run "off limit". So small zips/rars (<5MB) please due to my 10kByte/s download atm.)

Cool. Well here are some models. These are from Jak3 HD. You can Ignore the texture file. It's like 50mb
Maybe cra0 can take a look at that? He seems good with textures.
[https://www.dropbox.com/sh/0928iacp2lfgp44/D99heeYQex](https://www.dropbox.com/sh/0928iacp2lfgp44/D99heeYQex)
## Post #45
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-17T22:04:26+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> well I know for sure that 3dformat, I think he's known as furryfan here, has gotten the level terrain. i just don't know how.Why not aks him?  
(Do you know in which engine.ps3 file that level is contained?)

> Cool. Well here are some models. These are from Jak3 HD.Thx. Are there other model files than these *-ag.go files? Cause I can't recognize any face indices in them.
## Post #46
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-10-17T22:41:16+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> Why not aks him?  
(Do you know in which engine.ps3 file that level is contained?)
I did ask him quite a while ago. he just never replied.
oh and yeah. It should be in the level0 file.

> Thx. Are there other model files than these *-ag.go files? Cause I can't recognize any face indices in them.
Well if you take a look at that text file, then you can see all the files withing the game.
I'm pretty sure those *-ag.go files contain the models though. I'm not sure what else can if not those.
Maybe this can help you if it's the same as the ps2 version.
[http://ps23dformat.wikispaces.com/Jak+3](http://ps23dformat.wikispaces.com/Jak+3)
## Post #47
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-18T03:27:03+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from o0DemonBoy0o
>
> I don't suppose you guys have any update on getting the level terrain? 
Would it be to much trouble to ask you guys to see if you can get the models from the Jak and Daxter HD Collection?

I'll take a look at the level geometry and the bone/skinning info on the models soon. As for the Jak and Daxter files yeah send me some ill take a quick look.

Texture Extraction looks straight forward its like the streaming archive in Ratchet & Clank but with a bit of bit shifting

-EDIT- you might want to start a new thread for jAK stuff
## Post #48
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-10-18T21:06:56+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from cra0
>
> 
I'll take a look at the level geometry and the bone/skinning info on the models soon. As for the Jak and Daxter files yeah send me some ill take a quick look.

Texture Extraction looks straight forward its like the streaming archive in Ratchet & Clank but with a bit of bit shifting

-EDIT- you might want to start a new thread for jAK stuff

Getting the models with the bones would be really cool. I wonder if animations are also possible.

That sounds like a good idea. I'll go ahead and make a new thread.
## Post #49
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2013-11-07T23:36:49+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Hate to be a bother but the Ratchet and Clank ps3 converter always gives me a 'type' error. It then says I can change the types byte at address 0x0003, which I have no idea how to do properly. Anyone have a way to get this thing working for me correctly?
## Post #50
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-07T23:53:15+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Which model is it you want to convert?
The converter only supports the types 2, 5 and 16 (=0x10).

So you might change the model type at address 0x0003 of the model file to one of these values.
You'll need a hex editor to do this.
On your own risk. May work or not.
## Post #51
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-11-08T00:51:54+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Actually I have a way that will extract pretty much any model except the level terrain.

sorry for the long post. does xentax not use spoiler bbcode?

using ship_bodies0.ps3 from R&C2 as an example

open it up and look for a line that looks similar to this



now delete everything before it up to 0x0010

now at 0x0022 change the 01 00 into 00 80 like so



now the start of the data is at 0x00A0 you can usually tell because there are lines of 00's before it.
Now just delete everything up to 0x0080



Look at 0x0025-28 and go to that address That would be 018090. You should see something like this



now take that address to the left (018010) and change the values at the start of 0x0025 to mach it

after that just replace the start of the file with
00 00 00 10 00 03 9C C0 00 00 00 02 00 00 00 00

and save



After that just extract like normal. 

the values at 0x0003 should be 10, 0x0013 should be 02, and 0x0023 should be 80. If there are not the model might not extract.
the start of the model should be at 0x0080.
the end of the model is marked by 0x0025-28, and at that address should be something that looks very similar to 
00 00 00 01 00 02 00 03 00 04 00 05 00 04 00 05
## Post #52
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-07T13:04:21+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Here's an update of hex2obj.exe to get the terrain levels:
[http://www.uploadmb.com/dw.php?id=1410093768](http://www.uploadmb.com/dw.php?id=1410093768)

It's the exe only so you'll need to download hex2obj_022 zip (view link in my sig) and replace the hex2obj exe.



engine_ps3_lvl_mesh.JPG (123.1 KiB) Viewed 263 times
## Post #53
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-04-12T08:36:30+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Where is the h2o script for this?
## Post #54
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-12T10:50:28+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

0xEC590 80088
Vb1
28 99
0x9B90 23206
120000
0xBF060 8

(It's not a script it's just a parameter file.)

I changed the uv's start address to 0xBF060 since the uvs seem to be fit better then.
But they look funny no matter how I split up into submeshes:



enigne_ps3_uvs.JPG (89.05 KiB) Viewed 199 times



(mesh is in engine.ps3, 13,493,680 bytes)
## Post #55
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-04-14T11:18:19+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shakotay2
>
> 0xEC590 80088
Vb1
28 99
0x9B90 23206
120000
0xBF060 8

(It's not a script it's just a parameter file.)

I changed the uv's start address to 0xBF060 since the uvs seem to be fit better then.
But they look funny no matter how I split up into submeshes:
enigne_ps3_uvs.JPG

(mesh is in engine.ps3, 13,493,680 bytes)

I will take a look hopefully this week when I have time. A friend and I have been wanting to get the environments out for a very long time.
## Post #56
- Username: Lizzy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 12, 2015 4:41 pm
- Post datetime: 2015-10-30T21:16:41+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Hate to dig up old threads, but I've been attempting to extract level model files for quite some time and just can't get a good footing.

Has anyone else poked around with these files? I have the disc here and am willing to upload any files as needed.

Thanks!
## Post #57
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-31T08:13:51+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

it's a matter of finding some decent uvs - so far the ones I found are too regular (the block ends at 0xEC590 so we've a size of 23206x8 bytes which fits perfectly if they were float uvs);
maybe need some handling as half floats plus divider and two bytes skipped, who knows?

Or maybe it's more likely to have the uvs in the FVF block.



engine_PS3_level.JPG (195.93 KiB) Viewed 130 times
## Post #58
- Username: shoopdahoop22
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 28, 2016 1:16 am
- Post datetime: 2016-07-21T20:09:24+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

[deleted]
## Post #59
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-24T16:27:26+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

yeah, see, the administration has a keen eye on what users post, meanwhile.
Really appreciate this.  

(and removed my reply which just contained a repetition of the foreposters 8 letter word - I feel guilty, confessed  )
## Post #60
- Username: shoopdahoop22
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 28, 2016 1:16 am
- Post datetime: 2016-08-09T16:46:25+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Anyways, I want to rip the HUD textures from UYA with the extractor that cra0 made.

Trying to rip the file gives out this error:



However, if I swap engine.PS3 with a different .ps3 file and rename it...



It kind of works.

Any idea on how I could get it to properly extract without needing to swap files around?

EDIT: I think I know what the problem could be.

Every other graphic is stored in a file with the name of vram.ps3.

The HUD graphics are stored in a different archive format - hud.vram
## Post #61
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2016-08-23T04:10:34+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from shoopdahoop22
>
> Anyways, I want to rip the HUD textures from UYA with the extractor that cra0 made.

Trying to rip the file gives out this error:



However, if I swap engine.PS3 with a different .ps3 file and rename it...



It kind of works.

Any idea on how I could get it to properly extract without needing to swap files around?

EDIT: I think I know what the problem could be.

Every other graphic is stored in a file with the name of vram.ps3.

The HUD graphics are stored in a different archive format - hud.vram

It's been so long since I looked at it but the engine ps3 file has indexes and texture sizes for the textures which are in the vram file.
## Post #62
- Username: kellne
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 25, 2017 8:29 pm
- Post datetime: 2017-04-25T19:17:08+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Any links to some Models ?

Or it is impossible to extract them 

I have original DVD with Ratchet and Clank 3 if that helps !
## Post #63
- Username: shoopdahoop22
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 28, 2016 1:16 am
- Post datetime: 2017-04-25T19:49:44+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from kellne
>
> Any links to some Models ?

Or it is impossible to extract them 

I have original DVD with Ratchet and Clank 3 if that helps !
Unfortunately, ripping Ratchet and Clank models from the WAD files is currently impossible at the moment. The files on the UYA disc are also hidden.

You can get RAC models here, but GC/UYA doesn't have as much ripped as RAC1:

[https://www.models-resource.com/playstation_2/R.html](https://www.models-resource.com/playstation_2/R.html)
## Post #64
- Username: shoopdahoop22
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 28, 2016 1:16 am
- Post datetime: 2017-04-26T02:56:52+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Anyways, here's a download link to the UYA HUD graphics I cant extract with the texture tool. Could someone please take a closer look at these?
[https://www.dropbox.com/s/wxrv8gw7htwnu ... 3.zip?dl=0](https://www.dropbox.com/s/wxrv8gw7htwnu9k/UYA%20Hud%20VRAM%20%2B%20PS3.zip?dl=0)
## Post #65
- Username: kellne
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 25, 2017 8:29 pm
- Post datetime: 2017-04-26T15:50:25+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

I dont want rips from HD versions.

I am asking if it is possible to rip PS 2 Ratchet and Clank games
## Post #66
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-04-26T23:00:35+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

> Reply from kellne
>
> I dont want rips from HD versions.

I am asking if it is possible to rip PS 2 Ratchet and Clank games

Models are probably the same except the textures.
## Post #67
- Username: kellne
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 25, 2017 8:29 pm
- Post datetime: 2017-04-28T18:02:38+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Can you please tell how to get textures ?

I tried Texmod but no luck.

Is there better way ?

Please.
## Post #68
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-04-29T03:28:53+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

I don't own the game.
## Post #69
- Username: kellne
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 25, 2017 8:29 pm
- Post datetime: 2017-04-29T14:27:36+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Are there some tools or programms to extract textures from PS 2 games ?

Or some emulator with that function
## Post #70
- Username: shoopdahoop22
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 28, 2016 1:16 am
- Post datetime: 2017-06-18T23:05:24+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

You can use Ninjaripper to extract the textures from the game. However, the game's mipmapping will end up resulting in lots of tiny textures.

Anyways, here is a DL link to the Up Your Arsenal HUD graphics:

[https://www.dropbox.com/s/wxrv8gw7htwnu ... 3.zip?dl=0](https://www.dropbox.com/s/wxrv8gw7htwnu9k/UYA%20Hud%20VRAM%20%2B%20PS3.zip?dl=0)

They cannot be extracted with the texture tool. Can somebody please give me a little bit of help with extraction?
## Post #71
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-07-06T04:20:57+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

I do wonder in which file format the models from - at least - Ratchet & Clank: Going Commando and Up Your Arsenal (the 2nd and 3rd game in this HD Collection) originally come out. Does anyone still have them lying around somewhere? If yes, I only need Angela Cross from Going Commando and Sasha Phyronix from Up Your Arsenal.

I'm asking 'cause I want to try something that is not possible to do with the obj files I find anywhere on the internet.
## Post #72
- Username: Nooga
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 28, 2021 3:19 pm
- Post datetime: 2021-04-28T07:28:39+00:00
- Post Title: Re: [Request] Ratchet & Clank HD collection models

Sorry to bump an old thread like this, but I'd like some help, please. I've been trying my hand at ripping from Ratchet and Clank 3 HD. Would anybody happen to have a mirror for the texture extractor? The link in this thread is unfortunately dead. I've managed to find some of the skins in the armour files, which is awesome, but without that texture tool I can't complete the file for submission to models resource.

BTW, does anybody know if it's possible to extract the weapons and/or gadgets? I can't seem to find an obvious candidate for the weapons files, but there is a multimodel file containing the gadgets (presumably, anyway, given the filename) - sadly it gives me a type error when trying to extract with Shakotay's tool (which is awesome BTW, thank you so much for taking the time to make that). I attempted to change the type as advised in this thread with a hex editor, but no cigar. I will admit though I'm a total noob when it comes to hex editing, so user error is definitely a possibility.

Thanks for your time.
