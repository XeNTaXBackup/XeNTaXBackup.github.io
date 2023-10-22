## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-15T17:04:21+00:00
- Post Title: [release] SleepingDogs mesh extractor

For discussion I kindly beg to use this thread: [http://forum.xentax.com/viewtopic.php?f ... 160#p88160](http://forum.xentax.com/viewtopic.php?f=16&p=88160#p88160)
and leave this release thread for updates and format contributions.

This is a mesh extractor for SleepingDogs' *.perm.bin files.

### 7 years later, start, [www uploadmb com has ceased working] so I had to collect the 5 exes I had backupped.
########################################
SleepDogs_old.exe is for characters ONLY and the only version using thresholds (notcut/cut button).
########################################
.


 SleepDogs_MeshExtractor.zip
(82.74 KiB) Downloaded 100 times


Having a look into the *_log.txt file finding # threshold correction: off
means that the concerning exe doesn't use those values.

For sampan01 (fender, steering wheel), vertex type 12 I may have optimized too much 7 years ago, dunno.
(At least button t12 is missing in the newer exe files.)

### / 7 years later, end

Character meshes (Jackie, winston) are o.k.
Jackie's UVs need some reducing (faces range = 0.75).

Motorcycle 270DX01 mesh & UVs seem to be o.k. (wheels missing)

shak-otay, September 2013

[](http://www.pic-upload.de/view-20733515/Jackie_textured_3_4.jpg.html)

[](http://www.pic-upload.de/view-20733513/270DX01_3.jpg.html)

format (taken from Jackie.perm.bin):
faces (indexbuffer) f1,f2,f3 as 3 uint16

vertices in a 16 bytes vertexblock:
x,y,z as 3 uint16 - (divided them by 1024 to get floating point values)
10 bytes to skip (00 00 D0 31 BB FF E0 CC 61 FF for example)

texture coords x,y as 2 uint16 (half floats)

edit: u can use Texturefinder on Winston_TS00.temp.bin for example to get the textures: [](http://www.pic-upload.de/view-20738933/TextureFinder.jpg.html)

[](http://www.pic-upload.de/view-20738932/Winston.jpg.html)

(Params for Winston in old MeshExtractor: x= 0.5 and faces range: 0.75)
(Better use new version v2.1 of TextureFinder.)


I don't think this would have been possible without the help of Mariusz Szkaradek.
So a big Thx and the credits go to him!
[](http://www.pic-upload.de/view-20874055/RidgeCopCar.jpg.html)

[](http://www.pic-upload.de/view-20989565/LeoCoastGuard.jpg.html)(Don't ask me why the window-panes do have an offset.)

[](http://www.pic-upload.de/view-20989564/LeoCGuard_Lod0.jpg.html)The cabin seems to have an outer and an inner mesh in LOD0.
## Post #2
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-16T23:57:34+00:00
- Post Title: [release] SleepingDogs mesh extractor

Speaking of which, for most models the mesh is in a ModelName.perm.bin and the textures are in a ModelName_TS0.temp.bin 

However, a large chunk of the characters have generic names in this format:

A/T = [Model]/Texture
M/F = Male/Female (S = Special)
B/H = Body/Head

IE: 
TF_B_001.temp.bin = Texture_Female_Body_001.temp.bin

AS_B_PoliceOfficer.perm.bin = Model_Special_Body_PoliceOfficer.perm.bin
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-21T12:54:43+00:00
- Post Title: [release] SleepingDogs mesh extractor

Well, with the faces of the vehicles it's a little bit complicated.
For bisai01.perm.bin for example I found 193, 1321 and 4529 faces (LOD1,2,3?).
But if you display 3 models there are weird faces for example in LOD2 model.

With the help from Mariusz Szkaradek I understood that the 3 submeshes have to be devided up.

In fact there seem to be 8 submeshes.
SM 0 having 193 faces
no 1 to 3  have 99, 535+579+50 and 46+12 faces (1321 in sum)
The 4529 faces split up on submeshes 4..7

So the riddle is solved thanks Mariusz.

edit: hmm, I've made a comparison between the faces in the submeshes 1 to 3 and the ones of the errorness LOD2 SM.
They are identical!
So my error seems to be in the relation to the vertices list. Sure it's a rather simple one but I have to stick to RL again...
## Post #4
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2013-09-24T05:02:33+00:00
- Post Title: [release] SleepingDogs mesh extractor

Great job guys. Any way to code a method to get the model's armature and weights as well?
## Post #5
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-24T06:44:46+00:00
- Post Title: [release] SleepingDogs mesh extractor

Ooh, yeah, armature would be great. [Here's some stuff that might help with that](http://puu.sh/4yVEz.zip).

But then again it's most likely a whole different realm so I understand if it's not possible at this time.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-26T15:52:06+00:00
- Post Title: [release] SleepingDogs mesh extractor

I'm sure there are methods but since I lost many hours with current coding I think I will be done when vehicles are done.
So this is the weird faces problem I'm just solving (hopefully):

With bisai01 there are 3 LOD models (I just call them like this).
LOD_2 consist of 4 submeshes. One problem was to combine the 7 faces sections they are divided up into.
(Since LOD_1 has 3 submeshes LOD_2 starts from SM 4.)
This is a table of the relative min/max face indices as they are found by the parser:

```
1/1535         
                1/520
1536/3334
                          1/1039
3335/3662
                                     1/346
                                     347/386
```

I didn't want to create an obj for each SM.
Maybe there is a trick with absolute face indices in blender/ wavefront obj format (more than just marking SM groups with 'g ').
I'm pretty sure I fiddled around with a prob that doesn't really exist.  

That is to add 3662 to all face indices of SM 5. But when the parser finds SM5 our last max face index
(of SM4) is 1535. And before we reach 3662 of SM 4 there's another SM 6.

You see/understand the prob? If not don't worry - I think I got it now. I'll simply do a 2nd parsing pass.

(Anyway - if someone is just rolling on the floor/laughing maybe he kindly could tell me a better approach.  )

edit: it's going to look better on vehicles but there are still some planes I'd like to know where they're coming from (hopefully it's only an offset again):
[](http://www.pic-upload.de/view-20841331/bisai01_LOD_2.jpg.html)
Guess in 3 or 4 days I can update the extractor (with minor errors left):
[](http://www.pic-upload.de/view-20841576/bisai01_LOD2_partial.jpg.html)
## Post #7
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-26T20:26:38+00:00
- Post Title: [release] SleepingDogs mesh extractor

Yikes. I'd love to help but all that is way over my head. 
Somewhat of a disappointment that bones/animations won't be supported, but still, thank you once more for all your hard work.

Really hope you get that issue sorted out.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-29T15:22:52+00:00
- Post Title: [release] SleepingDogs mesh extractor

(view upate in first post)
## Post #9
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-29T20:11:33+00:00
- Post Title: [release] SleepingDogs mesh extractor

Thank you, now every single character opens perfectly!

...yet I noticed that some vehicles cause it to crash. [Here's an example bin and the generated files.](http://puu.sh/4DuW7.zip)

Also, the [vehicles that work](http://puu.sh/4DxlW.bin) still seem [kind of wonky](http://puu.sh/4DwbA.jpg). I've tried changing the X, Y, And Z thresholds, but it just doesn't seem to come out correctly.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-30T09:16:08+00:00
- Post Title: [release] SleepingDogs mesh extractor

> Reply from SergeantJoe
>
> Also, the vehicles that work still seem kind of wonky.As I wrote somewhere: "some minor errors are left".

> ...yet I noticed that some vehicles cause it to crash.Yep, weird error. Thx.
Thought I solved it on LeoCoastGuard and wondered about the messy low level LOD_2.
Now RidgeCop works, too (see end of startpost).
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-03T22:26:53+00:00
- Post Title: [release] SleepingDogs mesh extractor

Looks like a sampan01 submesh is ruined by the threshold calculation.
I first made a quickhack for a threshold correction (thc).

Then I decided to remove th on vertex type 12. It's working for LeoCoastGuard and "Dampfross" perm.bins. I also scaled up and rotated the interiors.

(get final version from start post)
If there are problems with other models use "intermediate version".

[](http://www.pic-upload.de/view-20913183/RidgeCop.jpg.html)
## Post #12
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-10-04T04:31:11+00:00
- Post Title: [release] SleepingDogs mesh extractor

Say uh, I think I spotted a rather large problem. 
I know that you said it's not perfect, but for nearly every vehicle I open, the insides are completely missing!

[http://puu.sh/4H6iC.jpg](http://puu.sh/4H6iC.jpg)
[http://puu.sh/4H6mZ.jpg](http://puu.sh/4H6mZ.jpg)
[http://puu.sh/4H6Cj.jpg](http://puu.sh/4H6Cj.jpg)

I've tried messing with the thresholds and thc button, but nothing happens. 
Everything else comes out fine. Is this a problem with the files themselves?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-04T10:04:51+00:00
- Post Title: [release] SleepingDogs mesh extractor

> Reply from SergeantJoe
>
> I know that you said it's not perfect, [...]Yep, it's the missing submesh_1_1 for LeoCoastGuard for example.

I fixed it in my last posts upload (which is replaced now by the final version in the start post).
[](http://www.pic-upload.de/view-20911959/LeoCoastGuard_submesh_1_1.jpg.html)

But as you can see some threshold error again on y axis. Think I never will solve this... 

edit: I used threshold 1.0 for x/y/z.
This seems to work for the wilful submesh (but not for the whole model (all 0.5)):
[](http://postimg.org/image/5bjx09mzh/)

edit2: finally I removed "thresholding" from type 12. If this should be reported to be working on all models I would clear up the versions garbage...
## Post #14
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-10-04T21:53:24+00:00
- Post Title: [release] SleepingDogs mesh extractor

Yay, now all meshes come out perfectly!

But, there is another big problem. The parts that were missing [only have dummy UVs](http://puu.sh/4HEe3.jpg), for both 0.5 and 1.0 thresholds.

I could just remake them from scratch but it would be nice if you could fix this one last thing. 
[Here are the textures](http://puu.sh/4HEt3.zip) for that particular model if you need to test it.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-12T09:16:32+00:00
- Post Title: [release] SleepingDogs mesh extractor

> Reply from SergeantJoe
>
> The parts that were missing only have dummy UVsYes, this was a workaround for existing type 12 submeshes. So for the missing ones now.

But luckily I seem to have found uv data for LeoCG, LOD1, SM 1_1:
[](http://www.pic-upload.de/view-20921017/Leo_LOD_1_submesh_1_1_tex.jpg.html)

Finally I did a final version (-> start post).
Mirrored the mesh. Then there's no need to flip normals. (Seems at the end I will be confused totally...  )

(I really hope there are no more issues 'cause I'm really tired now of "Sleeping Dogs"...  )
## Post #16
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-10-12T15:37:48+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from shakotay2
>
> Finally I did a final version (-> start post).
Mirrored the mesh. Then there's no need to flip normals. (Seems at the end I will be confused totally...  )
Oh my goodness. Shako, you are a hero. 

You deserve all the thanks for going through all of this hard work on your own time and for absolutely no gain. Seriously. 
I don't even know what else to say, after all, you pretty much single-handedly created the first and only model extractor for this game. If you hadn't come along we would all have been sitting here scratching our heads until 2015.

(and by the way the inner mesh on the Leo is supposed to be there, don't worry about it)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-12T16:52:41+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from SergeantJoe
>
> Oh my goodness. Shako, you are a hero.Well, I surely feel: no.
But thanks for the thanks.  

I want to bypass 80% of the thx to Mariusz Szkaradek. Without his help I wouldn't have got only one of the vehicles correctly. I really miss him on this board.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-10T20:32:04+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

I'm pretty sure no one will care except for one person only but anyways the 7 years old "perm.bin to obj" converter is available again here (click up arrow):

> Reply from shakotay2 ↑Mon Sep 16, 2013 1:04 am at Mon Sep 16, 2013 1:04 am
>
> 
(Sadly the perm.bin files of the "definitive edition" have changed a bit, thus the above mentioned converter doesn't work on them.)
## Post #19
- Username: utopiadeferred
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 14, 2021 4:04 pm
- Post datetime: 2021-08-06T08:02:48+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from shakotay2 ↑Fri Jun 11, 2021 4:32 am at Fri Jun 11, 2021 4:32 am
>
> 
I'm pretty sure no one will care except for one person only but anyways the 7 years old "perm.bin to obj" converter is available again here (click up arrow):
shakotay2 wrote: ↑Mon Sep 16, 2013 1:04 am
(Sadly the perm.bin files of the "definitive edition" have changed a bit, thus the above mentioned converter doesn't work on them.)

Getting the "this seems not to be a perm.bin file" error on any perm.bin (using 2012 build of the game). Any ideas, trying it on HK.perm.bin and a few others in Zone and Section.

Only certain vehicles work to add, but 90% of the perm.bins do not. If you aren't sure, I will start going over old threads and start up some new tools on it.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-06T09:30:07+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from utopiadeferred ↑Fri Aug 06, 2021 4:02 pm at Fri Aug 06, 2021 4:02 pm
>
> Any ideas, trying it on HK.perm.bin and a few others in Zone and Section.That's level files, isn't it? Afair the extractor wasn't intended to be used with them.

> Only certain vehicles work to add, but 90% of the perm.bins do not.Usually it says "This doesn't seem to be a perm.bin file!" when the first byte is not 0x6F - I'd need a sample of those which don't work to tell more. But don't expect too much (after 7 years  ).

(And, as I wrote, I wouldn't work on "definitive edition" samples.)
## Post #21
- Username: utopiadeferred
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 14, 2021 4:04 pm
- Post datetime: 2021-08-06T16:54:26+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from shakotay2 ↑Fri Aug 06, 2021 5:30 pm at Fri Aug 06, 2021 5:30 pm
>
> 
utopiadeferred wrote: ↑Fri Aug 06, 2021 4:02 pmAny ideas, trying it on HK.perm.bin and a few others in Zone and Section.That's level files, isn't it? Afair the extractor wasn't intended to be used with them.
Only certain vehicles work to add, but 90% of the perm.bins do not.
Usually it says "This doesn't seem to be a perm.bin file!" when the first byte is not 0x6F - I'd need a sample of those which don't work to tell more. But don't expect too much (after 7 years  ).

(And, as I wrote, I wouldn't work on "definitive edition" samples.)

Checking it out now and for a working vehicle it is obviously 0x6F and for a piece of the level, for example AB_FishMarket_02STD, it is 0x90.

Since I need to keep it under the filesize limit, here is a sample of the LOD instead, still has the same 0x90.
[AB_FishMarket_02LOD.perm.rar](https://xentaxbackup.github.io/file/20588_AB_FishMarket_02LOD.perm.rar)
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-06T18:35:21+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

well, 13 vertices, that's what I get. (Iirc there was a threshold required for correct values.)
.



AB_FishMarket_02LOD-perm-bin.png (27.84 KiB) Viewed 89 times



edit: gosh, this doesn't seem to be a model file - guess for a header file for the textures (in another file)
## Post #23
- Username: utopiadeferred
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 14, 2021 4:04 pm
- Post datetime: 2021-08-06T19:28:18+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from shakotay2 ↑Sat Aug 07, 2021 2:35 am at Sat Aug 07, 2021 2:35 am
>
> 
well, 13 vertices, that's what I get. (Iirc there was a threshold required for correct values.)
.
AB_FishMarket_02LOD-perm-bin.png

Interesting, on the same file I get the error. Tried a few different builds. If I change the byte from 0x09 to 0x6F however, the tool will export a broken version of it.

Started fixing it myself using the old blender tool as a building point, got some stuff workinnn
## Post #24
- Username: utopiadeferred
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 14, 2021 4:04 pm
- Post datetime: 2021-08-06T23:17:02+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from shakotay2 ↑Sat Aug 07, 2021 2:35 am at Sat Aug 07, 2021 2:35 am
>
> 
well, 13 vertices, that's what I get. (Iirc there was a threshold required for correct values.)
.
AB_FishMarket_02LOD-perm-bin.png


ehh? Normals were reversed but that's okay. 

I am still curious about your tool, it does seem like it only will accept a 0x6F.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-07T04:55:14+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

well, now I understand the problem - seems an earlier version of the tool extracted obj from Bisai01_ts001.perm.bin for example (starts with 0x90). (But I can't find the concerning exe file - maybe it's on my old PC, somewhere?  )

> Reply from shakotay2 ↑Sat Sep 21, 2013 8:54 pm at Sat Sep 21, 2013 8:54 pm
>
> 

edit: yeah, no, it was Bisai01.perm.bin, confused seven years later; Bisai01_ts001 is for texture, not a model file!

(This should be a warning to me: never, never touching projects again which were finished more or less.)
## Post #26
- Username: utopiadeferred
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 14, 2021 4:04 pm
- Post datetime: 2021-08-07T06:05:25+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from shakotay2 ↑Sat Aug 07, 2021 12:55 pm at Sat Aug 07, 2021 12:55 pm
>
> 
well, now I understand the problem - seems an earlier version of the tool extracted obj from Bisai01_ts001.perm.bin for example (starts with 0x90). (But I can't find the concerning exe file - maybe it's on my old PC, somewhere?  )
shakotay2 wrote: ↑Sat Sep 21, 2013 8:54 pm

prayyyy, I made some solid progress, but nearly as fast as the tool would be if you have such files. Texture export is a little wonky and some verts are just missing, but they do work and do get textured. I am not sure how far off I am.
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-07T11:41:07+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

So much trouble for nothing.  
Bisai01.perm.bin (starts with 0x6F) works with my tool. But it doesn't care for textures (and was nether intended to do so.)

The 0x90 confusion is solved - this is from Mariusz' script:
#texture 90 A0 BF CD

related files ("header" file (?) and data file):
Bisai01_ts001.perm.bin (starts with 0x90) and Bisai01_ts001.temp.bin

(There's 7 .dds files extracted by his script.)
## Post #28
- Username: utopiadeferred
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 14, 2021 4:04 pm
- Post datetime: 2021-08-07T18:22:00+00:00
- Post Title: Re: [release] SleepingDogs mesh extractor

> Reply from shakotay2 ↑Sat Aug 07, 2021 7:41 pm at Sat Aug 07, 2021 7:41 pm
>
> 
So much trouble for nothing.  
Bisai01.perm.bin (starts with 0x6F) works with my tool. But it doesn't care for textures (and was nether intended to do so.)

The 0x90 confusion is solved - this is from Mariusz' script:
#texture 90 A0 BF CD

related files ("header" file (?) and data file):
Bisai01_ts001.perm.bin (starts with 0x90) and Bisai01_ts001.temp.bin

(There's 7 .dds files extracted by his script.)

If you happen to get a new EXE out please let me know! His old script was utterly broken for me and did not work in 2.49 blender. However, here is my standalone progress. Few cargo mover obj's and some of the dock obj's.
