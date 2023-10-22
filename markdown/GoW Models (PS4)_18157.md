## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-30T11:06:56+00:00
- Post Title: GoW Models (PS4)

Hello,

I am looking at the files inside the ".lodpack" archive from the new GoW game. The indices seem to be always at the bottom of the file, but I couldn't spot the vertex data. I am looking for reasonable floating point values, but maybe they aren't stored as floats/half floats. I would appreciate it if you can take a look.

Here are some samples.


 GoW_Samples.rar
(150.78 KiB) Downloaded 132 times


I included 3 really small files, and the related ".h2o" files (just indices). Also included 2 larger ones.

Thanks.
## Post #2
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2018-05-31T21:02:21+00:00
- Post Title: GoW Models (PS4)

here's a lodpack for test
[https://mega.nz/#!blMRzQbJ!hXhp3fzC1VVM ... Kyx1YZxyUo](https://mega.nz/#!blMRzQbJ!hXhp3fzC1VVMhYjFw22GV1xJII-14FQLHKyx1YZxyUo)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-31T22:14:41+00:00
- Post Title: GoW Models (PS4)

here's what I got:



86-dat.jpg (76.86 KiB) Viewed 1639 times
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-01T01:25:52+00:00
- Post Title: GoW Models (PS4)

> Reply from shakotay2
>
> here's what I got:
Awesome! What version of hex2obj is that? I haven't seen that checkbox in 0.24d. Is there a newer version? Also what is the meaning of that checkbox?

Thanks.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-01T07:20:30+00:00
- Post Title: GoW Models (PS4)

pm'ed you
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-01T08:05:23+00:00
- Post Title: GoW Models (PS4)

It works great. Thanks again shakotay.



Need to find the UVs now, and after that I will try to make a tool for this.

No idea about the skeleton atm. Lodpack seems to just have files with mesh data, which makes sense actually
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-01T09:06:17+00:00
- Post Title: GoW Models (PS4)

> Reply from shakotay2
>
> here's what I got:
Let me guess, it's a signed/unsigned integer checker right?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-01T09:48:36+00:00
- Post Title: GoW Models (PS4)

yep
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-01T10:22:04+00:00
- Post Title: GoW Models (PS4)

> Reply from shakotay2
>
> yep
And you didn't release it in case of increasing the tool's complexity and newbies misusing it for other data types other than short?

BTW could you please send me a copy as well? Seems I'd encountered same issues with The Witcher 3. Thanks in advance!
## Post #10
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-06-02T18:06:30+00:00
- Post Title: GoW Models (PS4)

> Reply from akderebur
>
> It works great. Thanks again shakotay.



Need to find the UVs now, and after that I will try to make a tool for this.

No idea about the skeleton atm. Lodpack seems to just have files with mesh data, which makes sense actually

I wish i could learn how to do this. is there an indepth tutorial out there?

I'm a software engineer so its not like im a novice.
I want to be able to just get any model i want from any game without bothering people. for example Detroit.
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-02T18:38:14+00:00
- Post Title: GoW Models (PS4)

> Reply from Bladers
>
> 
I wish i could learn how to do this. is there an indepth tutorial out there?
Start with the classic hex2obj tutorial : [viewtopic.php?f=29&t=10894](http://forum.xentax.com/viewtopic.php?f=29&t=10894) . There is also Bigchillghost's tutorial for extracting models : [viewtopic.php?f=29&t=17889](http://forum.xentax.com/viewtopic.php?f=29&t=17889) . I haven't read it from start to finish myself, but it seems to be more in-depth and technical.

It is mostly about experience imo. After seeing some model formats, you begin to see the similarities and notice the model data easier.

> Reply from Bladers
>
> for example Detroit.
Afaik this isn't possible atm. Work on other games until it is possible to get the game files for Detroit
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-02T18:40:33+00:00
- Post Title: GoW Models (PS4)

there is a whole tutorials forum here [viewforum.php?f=29](http://forum.xentax.com/viewforum.php?f=29)

among others you can also see my thread with some videos:
[viewtopic.php?f=29&t=15687](http://forum.xentax.com/viewtopic.php?f=29&t=15687)

but this all will not help getting models from detroit at all
## Post #13
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-06-02T21:19:41+00:00
- Post Title: GoW Models (PS4)

> Reply from daemon1
>
> there is a whole tutorials forum here viewforum.php?f=29

among others you can also see my thread with some videos:
viewtopic.php?f=29&t=15687

but this all will not help getting models from detroit at all

> Reply from akderebur
>
> 
Start with the classic hex2obj tutorial : viewtopic.php?f=29&t=10894 . There is also Bigchillghost's tutorial for extracting models : viewtopic.php?f=29&t=17889 . I haven't read it from start to finish myself, but it seems to be more in-depth and technical.

It is mostly about experience imo. After seeing some model formats, you begin to see the similarities and notice the model data easier.

Thanks.
## Post #14
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2018-06-04T11:29:43+00:00
- Post Title: GoW Models (PS4)

> Reply from Bladers
>
> for example Detroit.

Not possible current exploit is only up to 5.05

Detroit requires 5.50 firmware
## Post #15
- Username: Neverstops
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 06, 2015 7:06 am
- Post datetime: 2018-07-09T12:41:58+00:00
- Post Title: GoW Models (PS4)

From what we do know right now, i looked up inside the .pkg file, and somehow i'd figure there are 2 file format .as .wad could contain the models.

I tried looking up in the .wad file, and i got it extracted with one the .bms file, but turns out the file formats are just nothing. However, i also got name results.

I have some samples here from the extracted .wad, if this would help [https://mega.nz/#!n9JWVKza!xGfTouUY6vwU ... tQYT-Tv4_8](https://mega.nz/#!n9JWVKza!xGfTouUY6vwUh1O34NKNL0RpdaNYY6c-utQYT-Tv4_8)
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-09T14:10:30+00:00
- Post Title: Re: GoW Models (PS4)

The ones with the "_gpu" in the name are model data. They seem to be exactly like the files extracted from the lodpack.

I tried making a tool for loading those files automatically, but files with multiple meshes aren't working that well. Here is some stuff from "MG_heroa00_0_gpu". Looks like the model of the kid.



The ones with fewer meshes are better / more complete. Here is one model I extracted earlier from the lodpack.



There is probably a file with offsets to load the model data properly. I will check out your samples more thoroughly when I have the time.
## Post #17
- Username: Neverstops
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 06, 2015 7:06 am
- Post datetime: 2018-07-09T15:17:41+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from akderebur
>
> The ones with the "_gpu" in the name are model data. They seem to be exactly like the files extracted from the lodpack.

I tried making a tool for loading those files automatically, but files with multiple meshes aren't working that well. Here is some stuff from "MG_heroa00_0_gpu". Looks like the model of the kid.



The ones with fewer meshes are better / more complete. Here is one model I extracted earlier from the lodpack.



There is probably a file with offsets to load the model data properly. I will check out your samples more thoroughly when I have the time.

Great!, i'm surprised this happens. However this i wasn't figuring as much finding Kratos. But this was the model of Kratos i found.

I'm only trying to get the Dragon model where Sindri was being attacked. I'd love to have it with the textures. So It's probably r_dragon00.wad.
---

Besides, was there any possible way for the textures?
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-09T17:28:49+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from akderebur
>
> Here is some stuff from "MG_heroa00_0_gpu". Looks like the model of the kid.

No, the kid is in the file called "son". This one is kratos. You can clearly see his beard and his knife.



the file is so big because he's there with all of his stuff:



and of course textures are extractable
## Post #19
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-09T17:45:06+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> 
No, the kid is in the file called "son". This one is kratos. You can clearly see his beard and his knife.
Lol, that was a beard? I thought it was something else. I didn't know that Kratos carried a bag, so I went with the kid. Need to play the game some time
## Post #20
- Username: Neverstops
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 06, 2015 7:06 am
- Post datetime: 2018-07-09T18:02:46+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> akderebur wrote:Here is some stuff from "MG_heroa00_0_gpu". Looks like the model of the kid.



No, the kid is in the file called "son". This one is kratos. You can clearly see his beard and his knife.



the file is so big because he's there with all of his stuff:



and of course textures are extractable

Didn't expect things to go fast. I hoped there will be simple ways to get them, by creating a tool for the mesh, textures.

Wasn't sure where to find the textures. But i don't know how did you opened them
## Post #21
- Username: Neverstops
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 06, 2015 7:06 am
- Post datetime: 2018-07-13T14:12:15+00:00
- Post Title: Re: GoW Models (PS4)

Any news lately?
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-13T15:16:36+00:00
- Post Title: Re: GoW Models (PS4)

i'm not working on this game. I just did some tests to check the formats.
## Post #23
- Username: Neverstops
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 06, 2015 7:06 am
- Post datetime: 2018-07-13T15:54:32+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> i'm not working on this game. I just did some tests to check the formats.
Oh... I was atleast curious how the models was opened and viewed. Just a simple thought. I'm not only hex editor or programmer like others. (I wasn't here for the game, but i just needed the dragon model with the textures)
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-13T17:09:14+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from Neverstops
>
> Oh... I was atleast curious how the models was opened and viewed. Just a simple thought. I'm not only hex editor or programmer like others.
i'm not sure what you mean, but i can tell you i made a quick research, made a test tool and extracted kratos & thor models/textures with it.
## Post #25
- Username: Neverstops
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 06, 2015 7:06 am
- Post datetime: 2018-07-13T22:56:47+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> Neverstops wrote:Oh... I was atleast curious how the models was opened and viewed. Just a simple thought. I'm not only hex editor or programmer like others.
i'm not sure what you mean, but i can tell you i made a quick research, made a test tool and extracted kratos & thor models/textures with it.
I almost thought you'd release the tools (Atleast if they were still a test), but it seems you have made a good work to it. I'd also want to give the tool a try if it were
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-14T05:42:03+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from Neverstops
>
> I almost thought you'd release the tools (Atleast if they were still a test)
a test tool is called test tool because it can only work for tests, and not real extraction by end users. In other words, it can only extract kratos & thor, and it requires some manual operations (like hex cut/paste) and corrections to code, which makes it impossible to use by users.
## Post #27
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-07-15T13:15:05+00:00
- Post Title: Re: GoW Models (PS4)

whats the vertex count for kratos model?
## Post #28
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-07-15T21:54:01+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> i'm not working on this game. I just did some tests to check the formats.
Are you planning to finish your tool in future? Or you dont want to fully work with that game?
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-16T15:11:08+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from dropoff
>
> daemon1 wrote:i'm not working on this game. I just did some tests to check the formats.
Are you planning to finish your tool in future? Or you dont want to fully work with that game?
akderebur planned to make tool first
so if he will not finish his, then i will think about it.
## Post #30
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-16T15:39:47+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> 
so if he will not finish his, then i will think about it.
Feel free to make a tool. With exams coming up I don't think I will have the time to work on this. Also your progress seems to be already better than mine  I still haven't got the textures.
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-19T15:15:52+00:00
- Post Title: Re: GoW Models (PS4)

Message for everyone PMing me: if i will be answering all messages, i will spend all my time writing answers, and I will have no time left to work on tools.

I will not do anything for GOW right now, because i'm busy with other games.

Also I can't upload Kratos, because his files are more than 1GB.
## Post #32
- Username: HiryuX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 14, 2017 5:12 am
- Post datetime: 2018-07-20T19:45:03+00:00
- Post Title: Re: GoW Models (PS4)

the file is so big because he's there with all of his stuff:




Hey id -- just a thought (and hopeful thinking) -- would it be possible to upload the Kratos model without all the extra armors (just the default mesh and textures, I assume it's the top image you posted)?  I assume that's why it's 1.0gb? =P

Yeah, definitely wouldn't want you to have to sit through that upload, but if it's easy enough to separate the default mesh and it's associated textures, would be very grateful to get that uploaded.  Wouldn't need the armatures or skeleton at all, just the base mesh and the textures that go with it.  No worries, if I'm thinking about it wrong in terms of cutting down the size of the files.
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-21T16:37:28+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from HiryuX
>
> but if it's easy enough to separate the default mesh and it's associated textures, would be very grateful to get that uploaded.Didn't care for textures but if you've patience enough you can get the basic meshes yourself using hex2obj (head uncomplete so far):



MG_heroa00_0_gpu.jpg (243.17 KiB) Viewed 540 times


H2O files for upperbody

0x2BA1E0 42597
Vb1
40 32
0x270AE0 7520
020300
0x0 255

and arms:

0x183860 45852
Vb1
40 32
0x12D4B0 8830
020300
0x0 255

(When "browsing" the MG_heroa00_0_gpu file for other meshes (lower body for example) keep in mind that some have an FVF size of 6 and use short integers.)
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-21T17:26:48+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from HiryuX
>
> if it's easy enough to separate the default mesh and it's associated textures
no, i currently have no way to know which mesh is default
## Post #35
- Username: HiryuX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 14, 2017 5:12 am
- Post datetime: 2018-07-22T13:09:06+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> HiryuX wrote:if it's easy enough to separate the default mesh and it's associated textures
no, i currently have no way to know which mesh is default

Ah, ok -- thanks anyway, I guess I was hoping that the model that Mightyracoon used in the video was something you had on hand.  Doing a Norse-themed 3D art project, and thought using the Kratos model would've been a cool idea, but no worries, can think of something else.

Thanks to everyone on the thread for all the info, really really appreciate it! =)
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-23T09:11:34+00:00
- Post Title: Re: GoW Models (PS4)

In the MG_heroa00_0 file (forget the "..._gpu" below the picture!) I found the counts for the arms and the upper body from my previous post (FI count 42600 instead of 42597, though), and much better, the FI start addresses (blue rectangle) and vertex block start addresses (red rectangle):



MG_heroa00_0_gpu-counts.jpg (191.73 KiB) Viewed 478 times


(there are more counts, of course; now to find out which meshes they belong to...)

this is the H2O file for the complete head for example:

0x240c30 98130
Vb1
40 32
0x199ea0 17085
020300
0x0 255

still missing FVF info, here's a full npc, lower lod, no uvs:

0x31ae60 44406
Vb1
32 99
0x2d8120 8554
020300
0x0 255
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-23T17:48:40+00:00
- Post Title: Re: GoW Models (PS4)

scaling of the lower body is a little bit tricky:



Kratos.jpg (39.7 KiB) Viewed 464 times
## Post #38
- Username: HiryuX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 14, 2017 5:12 am
- Post datetime: 2018-07-23T20:12:20+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from shakotay2
>
> scaling of the lower body is a little bit tricky:
Kratos.jpg

Wow -- nice progress, S! =)
## Post #39
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-26T07:46:07+00:00
- Post Title: Re: GoW Models (PS4)

nope, it's not a progress, it's just a little bit of what daemon1 and akderebur found out already
Kind of progress is when users give it a try themselves, imho.
You could use the latest version of hex2obj
[viewtopic.php?f=29&t=10894&p=142434&hil ... al#p142434](http://forum.xentax.com/viewtopic.php?f=29&t=10894&p=142434&hilit=+actual#p142434)
to get the lower body, which uses shorts, btw.

H2O file:

0x11A160 9930
Vb1
6 99
0x1090B0 2053
020400
0x0 255

beard, maybe:

0x7CD30 4899
Vb1
6 99
0x67f20 1859
020400
0x0 255
## Post #40
- Username: Resiliaxia
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Jun 25, 2016 4:59 am
- Post datetime: 2018-07-30T02:44:53+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from Neverstops
>
> I tried looking up in the .wad file, and i got it extracted with one the .bms file
Where did you get that bms script ? Can you post it here ?
## Post #41
- Username: Neverstops577
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 16, 2016 9:27 am
- Post datetime: 2018-07-30T10:17:34+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from Resiliaxia
>
> Neverstops wrote:I tried looking up in the .wad file, and i got it extracted with one the .bms file
Where did you get that bms script ? Can you post it here ?

I don't remember finding it, but i atleast have the file i saved
[bms.rar](https://xentaxbackup.github.io/file/14682_bms.rar)
## Post #42
- Username: Neverstops
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 06, 2015 7:06 am
- Post datetime: 2018-10-05T19:46:23+00:00
- Post Title: Re: GoW Models (PS4)

I assume it's been more than 2 months now. Anyhow the models have progress, but still no tools yet to "extract" properly anyway.
Although the textures are kind of awkward to get, some case it's size are small if were included in the .wad files along with _gpu, or neither if i'm wrong.

"I might realize those ANM are animations however, fact is, it might be packed with files. Describe that ANM_dragon00 has 5,767KB than MG_dragon00_0_gpu (221KB). Indeed less convenient"



Although it be really nice if someone could help retrieve this dragon Hræzlyr for me. [https://mega.nz/#!KgJxGKJK!CBAXtIj8MAkH ... CtVRAcuUaQ](https://mega.nz/#!KgJxGKJK!CBAXtIj8MAkHWkuItNxXQTPhZUgD0GieeCtVRAcuUaQ)
I have no experiences with hex, which badly confuses me.

----

Edit: I'm not really sure if this is the dragon, but this was the atleast file i carried for months. Pretty much i wiped out the stuff.
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-06T15:55:13+00:00
- Post Title: Re: GoW Models (PS4)

this game is now in top 5 of my queue
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-06T16:52:45+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> this game is now in top 5 of my queueGreat!

> Reply from Neverstops
>
> I have no experiences with hex, which badly confuses me.that's how we all began. 



MG_dragon.png (97.92 KiB) Viewed 232 times



(ANM_dragon00 is too hard for me...)
## Post #45
- Username: gaylord3000
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 29, 2018 5:09 am
- Post datetime: 2018-10-10T12:12:33+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from Neverstops
>
> I assume it's been more than 2 months now. Anyhow the models have progress, but still no tools yet to "extract" properly anyway.
Although the textures are kind of awkward to get, some case it's size are small if were included in the .wad files along with _gpu, or neither if i'm wrong.

"I might realize those ANM are animations however, fact is, it might be packed with files. Describe that ANM_dragon00 has 5,767KB than MG_dragon00_0_gpu (221KB). Indeed less convenient"



Although it be really nice if someone could help retrieve this dragon Hræzlyr for me. https://mega.nz/#!KgJxGKJK!CBAXtIj8MAkH ... CtVRAcuUaQ
I have no experiences with hex, which badly confuses me.

----

Edit: I'm not really sure if this is the dragon, but this was the atleast file i carried for months. Pretty much i wiped out the stuff.

From what I seen (file I was interested) textures in wad files are thumbnails. Actual textures are in texpacks.
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-13T07:10:45+00:00
- Post Title: Re: GoW Models (PS4)


## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-14T16:16:20+00:00
- Post Title: Re: GoW Models (PS4)

I checked my test code and it seems it extacts all models and textures fine. Had no time for skeletons yet. Also, game packages have tree-like structure and i don't know how long it can take to properly parse them. So I'm currently thinking maybe i just publish the tool in its current form where user can manually select model name from the list and export it.
## Post #48
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2018-11-04T17:21:05+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1
>
> I checked my test code and it seems it extacts all models and textures fine. Had no time for skeletons yet. Also, game packages have tree-like structure and i don't know how long it can take to properly parse them. So I'm currently thinking maybe i just publish the tool in its current form where user can manually select model name from the list and export it.

That sounds awesome.
## Post #49
- Username: Neverstops
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 06, 2015 7:06 am
- Post datetime: 2019-01-11T11:40:31+00:00
- Post Title: Re: GoW Models (PS4)

Any good news so far?
## Post #50
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-02-05T18:12:24+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from smasher248
>
> Bladers wrote:for example Detroit.

Not possible current exploit is only up to 5.05

Detroit requires 5.50 firmware
Do you have the profit with Detroit?
## Post #51
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-07T04:03:17+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from TokiChan
>
> smasher248 wrote:Bladers wrote:for example Detroit.

Not possible current exploit is only up to 5.05

Detroit requires 5.50 firmware
Do you have the profit with Detroit?
There is still no available exploit for it so its not possible.
## Post #52
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2019-04-07T00:40:51+00:00
- Post Title: Re: GoW Models (PS4)

Apologies if I am bumping this but, Daemon? Would you still happen to have your code? I have a friend who has actually been trying to get a hold of these models for a while but since there isn't really any other options aside from this thread here... I can only hope you didn't lose your progress or anything.
## Post #53
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-07T06:44:05+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from Mario123311 ↑Sun Apr 07, 2019 8:40 am at Sun Apr 07, 2019 8:40 am
>
> 
Apologies if I am bumping this but, Daemon? Would you still happen to have your code? I have a friend who has actually been trying to get a hold of these models for a while but since there isn't really any other options aside from this thread here... I can only hope you didn't lose your progress or anything.
no, i didn't lose any progress
## Post #54
- Username: enzy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 18, 2019 2:20 pm
- Post datetime: 2019-04-11T02:30:07+00:00
- Post Title: Re: GoW Models (PS4)

Any Kratos textures available? I've looked everywhere, but no luck. (I wouldn't need all of 'em, just the basic skin/eyes if they're there.)
## Post #55
- Username: redman4356
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 27, 2019 4:10 am
- Post datetime: 2019-06-27T11:33:50+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from daemon1 ↑Sat Oct 13, 2018 3:10 pm at Sat Oct 13, 2018 3:10 pm
>
> 

hey daemon
are there any updates?
## Post #56
- Username: fuegofuego2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 24, 2019 11:58 pm
- Post datetime: 2019-09-25T00:59:59+00:00
- Post Title: Re: GoW Models (PS4)

Is there any proven way to extract animations on God of War? Am interested on Jörmungandr animations to exctract them to FBX files! Is the big boss snake!

[](https://ibb.co/Q8NPkTW)

This is the only result that pops up around internet about this kind of files.
## Post #57
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-25T01:55:53+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from fuegofuego2 ↑Wed Sep 25, 2019 8:59 am at Wed Sep 25, 2019 8:59 am
>
> 
Is there any proven way to extract animations on God of War?
Sadly does not exist anywhere, I too am a GOW fan, and I'd love all animations form all GOW games to be exportable to a common format be it BVH or FBX.
Maybe one day in the far future, as usual time will tell.
## Post #58
- Username: Sasukekun2717
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 09, 2017 1:48 am
- Post datetime: 2019-10-23T01:34:50+00:00
- Post Title: Re: GoW Models (PS4)

Guys is there a chance of a Baldur model rip ? I loved the model ! Someone can post a link or maybe the tools and archives to rip it ? thank y´all
## Post #59
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-23T02:48:49+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from Sasukekun2717 ↑Wed Oct 23, 2019 9:34 am at Wed Oct 23, 2019 9:34 am
>
> Someone can post a link or maybe the tools and archives to rip it...
As of yet no tools exist, but for game assets their already spread all over internet.
## Post #60
- Username: td973
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 18, 2019 3:26 am
- Post datetime: 2019-11-17T19:40:03+00:00
- Post Title: Re: GoW Models (PS4)

Any progress on this tool?
## Post #61
- Username: macodys
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 15, 2015 3:09 am
- Post datetime: 2020-04-25T23:05:49+00:00
- Post Title: Re: GoW Models (PS4)

no progress yet? :/
## Post #62
- Username: AppleJuiceGaming
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 05, 2020 7:05 am
- Post datetime: 2020-04-28T01:11:08+00:00
- Post Title: Re: GoW Models (PS4)

god I wish.
## Post #63
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2020-07-19T04:00:28+00:00
- Post Title: Re: GoW Models (PS4)

Anyone knows if there is any progress on the tool for extracting models or textures?
## Post #64
- Username: dezastrunatural
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 16, 2020 1:55 pm
- Post datetime: 2020-08-28T11:13:30+00:00
- Post Title: Re: GoW Models (PS4)

Can someone help me with baldur and atreus please from the bottom of my heart I kept trying but I still can't extract Kratos I couldn't extract it please please if someone can help me
## Post #65
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-08-28T23:24:21+00:00
- Post Title: Re: GoW Models (PS4)

> Reply from dezastrunatural ↑Fri Aug 28, 2020 7:13 pm at Fri Aug 28, 2020 7:13 pm
>
> 
Can someone help me with baldur and atreus please from the bottom of my heart I kept trying but I still can't extract Kratos I couldn't extract it please please if someone can help me

Don't know how it was done, but someone extracted Kratos here.

[https://www.deviantart.com/luxox005/art ... -798081173](https://www.deviantart.com/luxox005/art/God-of-War-Kratos-798081173)

There don't seem to be any other models from the game available.
## Post #66
- Username: dezastrunatural
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 16, 2020 1:55 pm
- Post datetime: 2020-08-29T05:30:09+00:00
- Post Title: Re: GoW Models (PS4)

Yes I need Kratos I still need his atreus child I kept trying to get him out but I don't know how to use meash reseaech I tried to sculpt him too but I can't figure it out I don't want to make a movie for that I need atreus I have an idea wonderful I know how to use blender very well yes atreus is the last impediment for months torment me
## Post #67
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-10-26T00:29:38+00:00
- Post Title: Re: GoW Models (PS4)

Just a heads up, tools were recently released, so we can now get character models from the game   

[viewtopic.php?f=16&t=22897](https://forum.xentax.com/viewtopic.php?f=16&t=22897)
