## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-21T01:59:24+00:00
- Post Title: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-21T10:08:36+00:00
- Post Title: Soul Calibur 4

no, it's not xmem. I have tried also various offsets and xmem crashes ever so it's not it.
I have tried also to see if with findxor was possible to find something readable but nothing.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-10-29T12:10:11+00:00
- Post Title: Soul Calibur 4

I saw a news on a japanese forum said that the compression it use is called "xcompression" from X360 SDK.
Which is the same as MS LZX used in their cab file!?

I love this game as well, hope that someone could figure out a decompression method!
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-29T15:48:38+00:00
- Post Title: Soul Calibur 4

judging the tests performed with libmspack and xmemcompress the algorithms of the so called "lzx used in CABs" and the xmem one are differents (maybe just a bit) because libmspack isn't able to unpack the data compressed with XMemCompress using the CAB or the CHM settings.

this can be verified also with quickbms which implements all the 3 algorithms.

while about this SC4 game from my tests the XMemDecompress function crashes ever in any case even adding additional zero bytes (for example like I did with DMC4 with success) or starting the decompression from different offsets.

so if it's xcompress... prove it :)
maybe it could use different initialization parameters (all supported by quickbms) but it's rare.
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-11-25T12:20:42+00:00
- Post Title: Soul Calibur 4

I had downloaded the demo few day ago and found that the compression is a bit different like LZ!?

Here are some files if anyone is interested in this game!

<link removed due forum rules violation>
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-26T18:02:16+00:00
- Post Title: Soul Calibur 4

this is the same format used also in other games like Wolfenstein and the game posted here [viewtopic.php?f=21&t=3891](http://forum.xentax.com/viewtopic.php?f=21&t=3891)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T16:32:27+00:00
- Post Title: Soul Calibur 4

just for keeping the thread updated, I have been able to successfully decompress the [0x0FF512EE files](http://aluigi.org/papers/bms/xcompress_file.bms) but still no luck with the 0x0FF512ED ones
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T16:42:20+00:00
- Post Title: Soul Calibur 4

an idea, in the meantime that I solve the technical doubts why not using directly the xbdecompress.exe tool?
it works perfectly so who cares? :)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T17:15:36+00:00
- Post Title: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2009-12-20T17:41:19+00:00
- Post Title: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: Tosyk
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-20T17:52:13+00:00
- Post Title: Soul Calibur 4

I am working on a max importer ill post it here when i am done.
## Post #12
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2009-12-20T17:54:20+00:00
- Post Title: Soul Calibur 4

> Reply from chrrox
>
> I am working on a max importer ill post it here when i am done.
wonderfull  So we can make our own taki wallpaper?
## Post #13
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2009-12-20T19:17:33+00:00
- Post Title: Soul Calibur 4

> Reply from chrrox
>
> I am working on a max importer ill post it here when i am done.

Great!!! hope this is a xmas gift =D
## Post #14
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-21T22:58:30+00:00
- Post Title: Soul Calibur 4

that is wonderful news.
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-22T07:16:56+00:00
- Post Title: Soul Calibur 4

Any progress on the 3d max importer?
## Post #16
- Username: alvincx
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-23T20:52:53+00:00
- Post Title: Re: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2010-01-05T01:58:47+00:00
- Post Title: Re: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #18
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2010-01-18T19:24:07+00:00
- Post Title: Re: Soul Calibur 4

someone have extracted the model. here is the image of shura.
[](http://img697.imageshack.us/i/shaurafront.jpg/) [](http://img403.imageshack.us/i/shauraback.jpg/)
## Post #19
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2010-01-19T08:11:23+00:00
- Post Title: Re: Soul Calibur 4

Nice! Has the model extract tool been released yet?
## Post #20
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2010-01-20T13:42:15+00:00
- Post Title: Re: Soul Calibur 4

I second on the model extract tool(s)!!
## Post #21
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2010-01-20T16:10:55+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Mike
>
> someone have extracted the model. here is the image of shura.
Looks great  But i want sophitia and taki )
## Post #22
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-01-22T15:16:07+00:00
- Post Title: Re: Soul Calibur 4

i've ripped this game from my disk to my drive now and i can't find the textures lol...

can anyone tell me in which file(s) the character textures are?
## Post #23
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-01-24T06:33:12+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Itze
>
> i've ripped this game from my disk to my drive now and i can't find the textures lol...

can anyone tell me in which file(s) the character textures are?
How to extract DDS from the file?
## Post #24
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-01-24T11:06:24+00:00
- Post Title: Re: Soul Calibur 4

i too am stumped on how to access the textures... i've seen that someone posted some compressed dds and jpeg files which i was able to decompress using xbdecompress and they worked...

however when i run xbdecompress on any of the .spd archives i still don't see any dds files or png's / jpegs whatever inside
## Post #25
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-01-24T14:40:34+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Itze
>
> i too am stumped on how to access the textures... i've seen that someone posted some compressed dds and jpeg files which i was able to decompress using xbdecompress and they worked...

however when i run xbdecompress on any of the .spd archives i still don't see any dds files or png's / jpegs whatever inside

How does the xbdecompress work?? I was trying to make it work but I couldn't
## Post #26
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-01-24T15:19:16+00:00
- Post Title: Re: Soul Calibur 4

you just write xbdecompress inputfile outputfile and  it decompresses the file for you...

i've found out that soul calibur iv runs with decompressed files too, so that makes modding a bit easier 

i still don't know how to get usable texture out of the uncompressed bigfiles tho 

i'm guessing that NMD = namco model data
and NTXR = namco texture

but theres also NDXR files

i can''t do anything with any of those tho 

where is  chrrox    when you need him?
## Post #27
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-24T16:12:29+00:00
- Post Title: Re: Soul Calibur 4

I can read the face data now I am just putting it all together in a script ill release it once i am all done.
here is one model file vertex view.

[](http://img402.imageshack.us/img402/5169/testsc4.jpg)
## Post #28
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2010-01-24T17:59:21+00:00
- Post Title: Re: Soul Calibur 4

Awesome ^__^.
Thanks Chroxx.
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-25T03:38:56+00:00
- Post Title: Re: Soul Calibur 4

its getting there just need to look at one other type of mesh then it should be good.
## Post #30
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-01-25T07:06:55+00:00
- Post Title: Re: Soul Calibur 4

looking good Chrrox   

i've found out that model swapping works (try replacing f_face_* with m_face_* brrr   )

do you think it's possible to modify the mesh and inject it back into the bigfiles?

also do you know anything about the texture format yet?

i'd love to mod this game like sf iv, not "just" extract stuff from it
## Post #31
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-01-26T01:40:42+00:00
- Post Title: Re: Soul Calibur 4

looks like a very clean extract. i mean like no extra faces needed to be deleted
## Post #32
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-01-28T10:27:10+00:00
- Post Title: Re: Soul Calibur 4

How to extract DDS from the file?sophitia
## Post #33
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-01-29T17:23:50+00:00
- Post Title: Re: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #34
- Username: Rolandonmilk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 30, 2010 5:26 am
- Post datetime: 2010-01-30T10:35:34+00:00
- Post Title: Re: Soul Calibur 4

i got this so far its just  all the color customizable meshes r greyish here r just a few of wat i already exported lol 

[](http://img64.imageshack.us/i/ssssu.png/)[](http://img685.imageshack.us/i/ovsa.png/)
[](http://img64.imageshack.us/i/model12345678.png/)[](http://img692.imageshack.us/i/ivy7.png/)
## Post #35
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2010-01-30T14:33:27+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Rolandonmilk
>
> i got this so far its just  all the color customizable meshes r greyish here r just a few of wat i already exported lol
Looks good but i have same problem like Itze, i have only lots of garbage in maya after importing model. How way you find to import models?
## Post #36
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-01-30T16:32:07+00:00
- Post Title: Re: Soul Calibur 4

SirLoon which region is your Soul Calibur IV? Mine is PAL.. i thought that the NTSC Version might store models slightly different? would make no sense but i have no other idea
## Post #37
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-01-30T16:35:00+00:00
- Post Title: Re: Soul Calibur 4

I use 2 tools: xbdecompress.exe and SPD_EX.exe on file R_ALL_011_360.spd, get obj, fbx, and texture. But when I try to open the fbx in 3d max, I get such a mess here:

[](http://s002.radikal.ru/i200/1001/86/3a814899f585.png)

How do you get to extract the model?
## Post #38
- Username: Rolandonmilk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 30, 2010 5:26 am
- Post datetime: 2010-01-30T23:12:33+00:00
- Post Title: Re: Soul Calibur 4

good news it can also export stages musicvoice and weapons  dtx is exportable as well 

[](http://img402.imageshack.us/i/weaponz.png/)


the texture comes out grey so u gotta reskin it :< dunno how tho lol only the parts that u could alter the color on custimization "ps the mesh comes out fine for me lol"
## Post #39
- Username: alvincx
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Nov 24, 2009 7:15 pm
- Post datetime: 2010-01-31T10:47:46+00:00
- Post Title: Re: Soul Calibur 4

hey chrrox, we're still waiting for you're max importer, please don't let us down..
## Post #40
- Username: Shepperd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 31, 2010 7:38 am
- Post datetime: 2010-01-31T13:29:51+00:00
- Post Title: Re: Soul Calibur 4

Hi.

I have the same problem that Itze, SirLoon and Tosyk...   

When I try to import the meshes in Max2009 they are ''hidden'' or are ''garbage''... I use Milkshape too but the results are the same... 

Any help with the problem?

I'm waiting for chrrox max importer too...  

Thanks in advance.
## Post #41
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-01-31T14:44:24+00:00
- Post Title: Re: Soul Calibur 4

I'm just guessing... but maybe the problem is with regional settings for the decimal separator. Does your OS region use "," or "."? If it uses the comma, then you probably need to change it for the extractor to work.
## Post #42
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-01-31T14:47:17+00:00
- Post Title: Re: Soul Calibur 4

stages you say? that is quite interesting
## Post #43
- Username: Shepperd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 31, 2010 7:38 am
- Post datetime: 2010-01-31T17:41:56+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Insomniac
>
> I'm just guessing... but maybe the problem is with regional settings for the decimal separator. Does your OS region use "," or "."? If it uses the comma, then you probably need to change it for the extractor to work.

It works now! Thanks Insomniac!  

Facepalm for me...
## Post #44
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-01-31T17:50:38+00:00
- Post Title: Re: Soul Calibur 4

thanks Insomniac... pretty lame bug if you ask me but after i changed the decimal seperator from , to . it works:


note: model looks fine normally... i justed wanted to see how it's build up
## Post #45
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2010-02-01T04:02:09+00:00
- Post Title: Re: Soul Calibur 4

> good news it can also export stages musicvoice and weapons dtx is exportable as well

OK, I'm able to extract character models using xbdecompress and spd_ex.  I can also extract models from the stages as well.  But how can you extract the voices.  After decompressing the file and using spd_ex on any of the voice clips (i.e.  voice_us00b.dtx) I get a series of spd files  (voice_us00b_001.spd, voice_us00b_002.spd, voice_us00c_003,spd, etc.)  But its not useable as an audio form (either *.wav, *.mp2/3, *.aiff etc).  I tried extracting these individual files again using spd_ex.exe but it yields nothing.   Does anyone know how to get to the voices?
## Post #46
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-02-01T08:08:06+00:00
- Post Title: Re: Soul Calibur 4

DELETE
## Post #47
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-02-01T08:21:07+00:00
- Post Title: Re: Soul Calibur 4

Insomniac Tell me more how to change regional settings?
## Post #48
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-02-01T15:29:42+00:00
- Post Title: Re: Soul Calibur 4

It's under language options in the systemmenu.

After fiddling around with the spks i was finally able to inject my modified files again 

I edited the model(corrupted some parts parts of the blouse so it disappears with  my trusty friend hexworkshop   ) and modified the skin textures(could be better but good enough for the test)   

If you want to replace textures i suggest todo this for now:

1. use spk extractor to get the correct textures
2. modify them to your liking, save whatever type it is(dxt1 to dxt5) with 3(THREE) mipmaps so the size stays the same
3. open the edited dds in hexworkshop or similiar, tools->operations->byte flip->16 bit -> ok
4. wait for the magic to complete
5. ignore the first 80 bytes and copy the rest
6. open the spk file with the hexeditor and search for the correct GIDX entry, the extracted dds files contain their position in the texture block at the last position r_all_blah_95.dds etc
so search 95 times for gidx and you have the correct position (find all helps alot here)
7. ignore the first 10 bytes
8. select block of same size of the dds texture you copied to your clipboard, press delete then paste your edited texture(or overwrite if your app supports it... DO NOT INSERT WITHOUT REMOVING THE SAME AMOUNT OF BYTES FIRST!!!)

The result of way too much work:
NSFW PICTURES
[](http://img13.imagevenue.com/img.php?image=37242_P010210_16.07_123_472lo.JPG) [](http://img183.imagevenue.com/img.php?image=37232_P010210_15.56_123_130lo.JPG)
## Post #49
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-02-01T16:54:37+00:00
- Post Title: Re: Soul Calibur 4

How to hack SPK[cassandra + setsuka + xianghua ] from the GAME?
it is error!!!
## Post #50
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-02-01T20:50:03+00:00
- Post Title: Re: Soul Calibur 4

you can't just make a texture black and hope that it becomes transparent lol

you have to edit the mesh or the mesh / original texture has to support the alpha channel... which only very few do
## Post #51
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-02-01T21:06:22+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Itze
>
> you can't just make a texture black and hope that it becomes transparent lol

you have to edit the mesh or the mesh / original texture has to support the alpha channel... which only very few do


I'm hacking the file......

why is error?
## Post #52
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-02-01T22:08:00+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Itze
>
> It's under language options in the systemmenu.

After fiddling around with the spks i was finally able to inject my modified files again 

I edited the model(corrupted some parts parts of the blouse so it disappears with  my trusty friend hexworkshop   ) and modified the skin textures(could be better but good enough for the test)   

If you want to replace textures i suggest todo this for now:

1. use spk extractor to get the correct textures
2. modify them to your liking, save whatever type it is(dxt1 to dxt5) with 3(THREE) mipmaps so the size stays the same
3. open the edited dds in hexworkshop or similiar, tools->operations->byte flip->16 bit -> ok
4. wait for the magic to complete
5. ignore the first 80 bytes and copy the rest
6. open the spk file with the hexeditor and search for the correct GIDX entry, the extracted dds files contain their position in the texture block at the last position r_all_blah_95.dds etc
so search 95 times for gidx and you have the correct position (find all helps alot here)
7. ignore the first 10 bytes
8. select block of same size of the dds texture you copied to your clipboard, press delete then paste your edited texture(or overwrite if your app supports it... DO NOT INSERT WITHOUT REMOVING THE SAME AMOUNT OF BYTES FIRST!!!)

The result of way too much work:
NSFW PICTURES

SPK extractor?? Isn't it spd extractor??
## Post #53
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-02-02T06:12:31+00:00
- Post Title: Re: Soul Calibur 4

yes spd sorry   

most meshes aren't "nude"... they only contain the stuff that is visible normally to save polys
## Post #54
- Username: truonggiang
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 14, 2009 7:59 pm
- Post datetime: 2010-02-02T16:52:01+00:00
- Post Title: Re: Soul Calibur 4

I can't download xbdecompress .... please help mee....
## Post #55
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-02-02T19:56:06+00:00
- Post Title: Re: Soul Calibur 4

delete
## Post #56
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2010-02-02T23:22:11+00:00
- Post Title: Re: Soul Calibur 4

I have spent the last couple of weeks trying to adjust colors on models in maya.
the shader parameters was really helpful. 
some of my work:-
[](http://img237.imageshack.us/i/rall00b360ivyfront1.jpg/) [](http://img3.imageshack.us/i/rall00b360ivyfront2.jpg/) [](http://img697.imageshack.us/i/rall003360takifront1.jpg/) [](http://img715.imageshack.us/i/rall003360takifront2.jpg/)
[](http://img9.imageshack.us/i/rall005360voldofront1.jpg/) [](http://img46.imageshack.us/i/rall005360voldofront2.jpg/) [](http://img24.imageshack.us/i/rall006360sophitiafront.jpg/) [](http://img697.imageshack.us/i/rall006360sophitiafront.jpg/)
[](http://img24.imageshack.us/i/rall017360cassandrafron.jpg/) [](http://img715.imageshack.us/i/rall017360cassandrafron.jpg/) [](http://img697.imageshack.us/i/rall030360amyfront1.jpg/) [](http://img715.imageshack.us/i/rall030360amyfront2.jpg/)
## Post #57
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-02-02T23:35:58+00:00
- Post Title: Re: Soul Calibur 4

Looks cool.
Can you maybe release them for Garry's Mod?
## Post #58
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2010-02-04T10:19:41+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Mike
>
> I have spent the last couple of weeks trying to adjust colors on models in maya.
the shader parameters was really helpful. 
some of my work:-

Can you make a quick tutorial of the process please?
## Post #59
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-02-04T10:25:13+00:00
- Post Title: Re: Soul Calibur 4

Anybody tell me more how to change regional settings? I can not convert models.
## Post #60
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-02-04T14:44:36+00:00
- Post Title: Re: Soul Calibur 4

those models look good. i want to get my hands on those. but i only have the ps3 version of sc4.
## Post #61
- Username: unkoburizou
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 01, 2010 4:47 pm
- Post datetime: 2010-02-05T03:46:21+00:00
- Post Title: Re: Soul Calibur 4

> Reply from onionhead
>
> those models look good. i want to get my hands on those. but i only have the ps3 version of sc4.
## Post #62
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-02-05T20:21:37+00:00
- Post Title: Re: Soul Calibur 4

wut was that for?
## Post #63
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-02-09T10:33:59+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Itze
>
> It's under language options in the systemmenu.

HELLO Itze

I'm hacking the SC4 (to get unlimited 3D model)


can you share those sc4 dds and skin[dds]? cassandra setsuka xianghua Sophitia

i am not good at  Photoshop


i wnat help!
## Post #64
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-04-18T14:15:44+00:00
- Post Title: Re: Soul Calibur 4

Thanks for all, now I can extract the characters, but how I have oto do for extract the stages?
## Post #65
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-04-19T14:17:04+00:00
- Post Title: Re: Soul Calibur 4

Does anyone can upload an archive with all models only the characters in the format spd (I think), I accidentally deleted my models  

Thanks in advance.
## Post #66
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-17T18:32:49+00:00
- Post Title: Re: Soul Calibur 4

Guy's I hate to ask, but I can't seem to find any files on my DVD, all I see are 2 folders: one called AUDIO_TS and VIDEO_TS
and stranger yet the audio folder has nothing in it, and the files in the Video folder only take up 4.6 MB. I am doing something wrong? This is the first time I put a Xbox360 disc in my computer....
## Post #67
- Username: rodolpho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-17T20:59:06+00:00
- Post Title: Re: Soul Calibur 4

you need to rip the 360 iso using a 360 or a compatible pc drive and the program to read 360 discs.
## Post #68
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-05-18T01:06:20+00:00
- Post Title: Re: Soul Calibur 4

Sorry but I ask again, how I have to do for extract the stages (and maybe the weapons)?
## Post #69
- Username: rodolpho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 19, 2010 12:00 am
- Post datetime: 2010-05-18T16:11:59+00:00
- Post Title: Re: Soul Calibur 4

> Reply from chrrox
>
> you need to rip the 360 iso using a 360 or a compatible pc drive and the program to read 360 discs.

What program you use to read the xbox360 .iso file? 

My only problem is where i found the .spd files.  i.i

Thanks guys!
## Post #70
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-05-18T18:24:57+00:00
- Post Title: Re: Soul Calibur 4

> Reply from rodolpho
>
> chrrox wrote:you need to rip the 360 iso using a 360 or a compatible pc drive and the program to read 360 discs.

What program you use to read the xbox360 .iso file? 

My only problem is where i found the .spd files.  i.i

Thanks guys!

Xbox backup creator is what I use
## Post #71
- Username: rodolpho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 19, 2010 12:00 am
- Post datetime: 2010-05-19T02:15:57+00:00
- Post Title: Re: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #72
- Username: rodolpho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 19, 2010 12:00 am
- Post datetime: 2010-05-28T23:38:26+00:00
- Post Title: Re: Soul Calibur 4

UP
## Post #73
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2010-06-11T13:22:58+00:00
- Post Title: Re: Soul Calibur 4

this is epic!  i tried using the program but my computer does not like it.  can someone share the exported 3d models or the dds files.  i am really good in photoshop so i will obviously share my skin mods with u.
## Post #74
- Username: rpgaudioso
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 18, 2010 10:33 am
- Post datetime: 2010-06-18T12:57:56+00:00
- Post Title: Re: Soul Calibur 4

what's the problem with my extracted SPD file?


Anyone here have OBJ's or SPD's of Nigthmare and Soulcalibur Sword?

I need them to convert into papercraft model to share with us!

Thank u so much!
## Post #75
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2010-06-27T12:58:00+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Tosyk
>
> Does anyone can upload an archive with all models only the characters in the format spd (I think), I accidentally deleted my models  

Thanks in advance.

Я тут забацал инструкцию. Напишешь как у тебя? С глюками или без?
[Setting for import.jpg](https://xentaxbackup.github.io/file/3174_Setting for import.jpg)
## Post #76
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-27T13:03:49+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Slozhny
>
> Tosyk wrote:Does anyone can upload an archive with all models only the characters in the format spd (I think), I accidentally deleted my models  

Thanks in advance.

Я тут забацал инструкцию. Напишешь как у тебя? С глюками или без?

Yes, thanks. I solved this problem already.
## Post #77
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-06-28T06:18:58+00:00
- Post Title: Re: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #78
- Username: fewks
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 28, 2010 6:05 pm
- Post datetime: 2010-06-28T12:54:20+00:00
- Post Title: Re: Soul Calibur 4

hi all, anyone know what archive contains default character editor f/m models and textures for them.

thanx.
## Post #79
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-07-26T22:12:33+00:00
- Post Title: Re: Soul Calibur 4

Hey, I'm new to this forum, and I came across this thread... I have worked with SC4 before, but I could never get the models to come out right- I only want four of them, though. I noticed previous posts in this thread contained images of models that had been properly extracted, textured, and rendered (with full color textures, not the gray-scale I tend to get). I only want Ivy, Sophitia, Shura, and Taki- can someone email them/somehow share these four models with me? I have tried lots of methods, but the models and their textures don't work for me. If someone could get me these four models, in the quality shown in the images, that would be AWESOME. Thanks
## Post #80
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-07-26T22:13:34+00:00
- Post Title: Re: Soul Calibur 4

I use 3ds max 2010 and 3ds max 8, so .obj, .max, or preferably .3ds would be great.
## Post #81
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-07-27T04:46:11+00:00
- Post Title: Re: Soul Calibur 4

> Reply from kingfisher13
>
> Hey, I'm new to this forum, and I came across this thread... I have worked with SC4 before, but I could never get the models to come out right- I only want four of them, though. I noticed previous posts in this thread contained images of models that had been properly extracted, textured, and rendered (with full color textures, not the gray-scale I tend to get). I only want Ivy, Sophitia, Shura, and Taki- can someone email them/somehow share these four models with me? I have tried lots of methods, but the models and their textures don't work for me. If someone could get me these four models, in the quality shown in the images, that would be AWESOME. Thanks

Unfortunetally the models come with gray textures to be rendered according the color you have selected with the shading system of the graphic engine.

Also, not all the parts come in the place where they must be, so you need in some cases, rotate them and place them manually.

If you want to get the "real color" of the textures, get an hd videocard recorder and get the colors from it and edit the gray textures in photosphop.
## Post #82
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-07-27T14:33:52+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Darko
>
> 

Unfortunetally the models come with gray textures to be rendered according the color you have selected with the shading system of the graphic engine.

Also, not all the parts come in the place where they must be, so you need in some cases, rotate them and place them manually.

If you want to get the "real color" of the textures, get an hd videocard recorder and get the colors from it and edit the gray textures in photosphop.

That is the problem I have come across- the models look REALLY bad in 3ds max, but that is not the only problem. Some of the faces of the models appear black, and will not assume texturing. I assume it has something to do with backface culling, and if that is true, there is nothing I can do about it, except redo the object in question. This is a big mess, and its not that I am lazy and not willing to do the work, but to me it ruins it if I have to edit and attempt to fix errors in a model that was supposed to come render-ready. Making my own models, of course is different- but I would really appreciate it if someone who has repaired the model, the textures, and everything would share a copy of those four models I mentioned above. I would love to be able to render them as I saw them rendered in previous posts of this thread...
## Post #83
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-27T15:24:34+00:00
- Post Title: Re: Soul Calibur 4

> Reply from kingfisher13
>
> Darko wrote:it has something to do with backface culling, and if that is true, there is nothing I can do about it
Enter EditableMesh -> Select black face -> Press Normal-Flip
## Post #84
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-07-28T00:37:00+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Tosyk
>
> 
Enter EditableMesh -> Select black face -> Press Normal-Flip

Thanks, Tosyk... I was wondering what I was supposed to do with those. I downloaded a copy of all of the character models from the game, in .fbx, .obj, and .mtl form... As I said, I enjoy editing models, but I would have preferred to download the finished product, render ready. I would ask again, if anyone is willing to share the four render ready models I asked about, please tell me now. If not, I need to know the names of the models for Sophitia, Taki, Shura, and Ivy. There are around one hundred models extracted into usable formats, and at several points I caused 3ds max to crash, from errors related to constant importing of .obj and .fbx. Apparently 3ds max 8 doesn't like .fbx, or importing for that matter. If it is possible, perhaps someone could share the repaired and recolored textures for these four models, in the exact naming that they came in? I am fairly good with photoshop, but I don't know how one would go about recoloring the textures, or even how one would combine the eye textures, the lip textures, or the eyebrow textures. I'm not quite on that level... I'm also not sure how to make hair textures appear without the white background, with just the hair showing. 

Thanks
## Post #85
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-07-29T14:58:36+00:00
- Post Title: Re: Soul Calibur 4

(SIGH........)

It appears that this thread is no longer in use. If anyone can answer my questions.... Like I said, I have been searching for this stuff for a long time, only to come to the only (supposedly) place on the internet that has it, and hit a dead end...
## Post #86
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-07-31T19:53:34+00:00
- Post Title: Re: Soul Calibur 4

Just so you know.. The textures are not " broken " in anyway. i know this because they render as expected on mine. Most Unreal 3 based game rips have the same "problem" due to the way most 3d editors handle transparency, which is differently to the way unreal handles them.

In regards to the textures looking wrong. The only thing im aware of that causes problems in the display is the fact all the maps have a transparency channel so most textures will display looking "washed out" or even invisible, if you load the textures into something like photoshop and remove the alpha channel the texture will look normal and bright again.

Also with the Hair problem of the white border... Is that just on the view port of max or actually happening when you render an image? because that white border is VERY normal to see in the view port, ( due to view ports not handling transparency properly) but is usually not visible when you render a frame out.

But yeah as i said, removing the transparency channel from the diff textures should fix the problems your having. As a test i just loaded the yoda model up and he has a grey face with green inner ears    After removing the transparency channel all his face went green again ( like it should be )

Oh and not really important but.... The only reason i didn't release the models as " render ready" as you put it, was because i wasn't ready to render them at the time of ripping. i ripped them coz i could, not coz i needed them. Then a friend asked if he could have them too, so i uploaded them for him.. then i saw a few people in here were having issues with ripping them so i posted the links in here too.

Hope that helps you in some way...

Nobby
## Post #87
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-08-01T17:16:18+00:00
- Post Title: Re: Soul Calibur 4

Hey, thanks for responding! I was worried the thread was dead... I will try removing the transparency, maybe that will help. About the white background with the hair: It does appear that way in the render, as well- I think it has something to do with the image file type in question being unable to support transparency. But on another note, how do you combine the facial textures? The eye textures are really odd, and don't work well together, the lip texture and eyebrow textures are also not really set up right, I guess the texture set isn't really set up for drag and drop texturing in 3ds max. One more thing: which of the models are Shura, Sophitia, Ivy, and Taki?
Thanks again for your help,
Kingfisher13
## Post #88
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-08-01T19:52:53+00:00
- Post Title: Re: Soul Calibur 4

Oh god...    I think removing the alpha channels will not work. My poor brain... it hurts... Anyway, the textures from the model set are in .dds format, which photoshop can't read, and when I converted  the pics to .jpeg, it removed the differentiation between channels. There are now only RGB, red, blue, and green channels, no RBGA or alpha channels present. 
To be quite honest, this is getting to be a very tiring adventure. Nobby, would you be willing to share the models and textures (with the alpha channel removed so I can see the color), or just the textures, for Sophitia, Taki, Shura, and Ivy?
That would really be a great help. 
Thanks,
Kingfisher13
## Post #89
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-08-01T20:12:35+00:00
- Post Title: Re: Soul Calibur 4

unfortunately i cannot share any named models as i dont know which are which, the only figures i recognised while looking was yoda, vader and that dude from force unleashed .   

Photoshop CAN read dds files, but you have to get the nvidia plugin for photoshop ( from the nvidia site ) once you install that you can read in DDS files and create NORMAL maps as well. you can remove the alpha channel and just save the files as png or tga.

OR if you have a copy of Deep Exploration you can just load all the DDS files into that and batch convert them to png/tga  ( actually you could just batch convert the models in it as well ( thats what i used to convert them in the first place, i just left the textures as dds )

To be honest i havnt done anything with the models myself.. i ripped them, made sure they had basic texture assignments then saved them. the only reason i know about that transparency issue was because i loaded the yoda face image and removed the alpha channel. then saved as png. i then temp mapped the png as the face texture ( but i didn't save the model afterwards, it was just to see if it reacted as expected, which it did)

Ill actually texture them up properly as and when i need the models ( if i ever do need them ) i mainly just build up my collection, you never know when you might need a certain model for an animation. 

Heres the link for the PS [plugin](http://developer.nvidia.com/object/photoshop_dds_plugins.html). Hope that helps
## Post #90
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-08-01T21:22:36+00:00
- Post Title: Re: Soul Calibur 4

Thanks for your quick reply. 
I used the plugin, and opened the .dds files. I still don't get an alpha channel option for some of the textures... for example, I found Shura's textures and model, and opened the .dds files in photoshop. I looked at the hair, and it appeared grey. This applies to several other parts of the model as well. I didn't see an alpha channel option for the greyed out textures- in fact, even the background of the greyed out textures was grey. This is what I meant when I was talking about damaged textures. I know they aren't damaged, but how can I get the original color they are supposed to be (example: Shuras hair is, obviously, supposed to be black)?

EDIT: Also, when I render the model, parts of the model appear washed out, almost white. is there anything I can do about that?
Thanks,
Kingfisher13
## Post #91
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-08-01T22:43:00+00:00
- Post Title: Re: Soul Calibur 4

Bearing in mind that pretty much all materials have at least 2 different textures ( usually diffuse and bump, or diffuse and specular or diffuse and alpha ) 
You may find the hair and things like that are done with a simple colour applied to the material then the textures are added on top, so you get for example black coloured hair  with a hair texture on top to give it a hair pattern. kinda similar to how in a car game if you can change the cars colour. the car has stickers on it, thats a texture map covering the entire car but most of it is transparent so you can see the surface colour underneath and when you change the car paint colour all you are changing is that surface colour... they may have done the surfaces like that, im really not sure..  

Im currently working on an animation so im kinda tied up with that, but ill try and look into this a little bit if i get some free time..
Could you let me know one of the offending models to look at... please dont say the characters name as i dont know who that will be  , just tell me which folder it is such as 00e or 128.  and ill try and have a look at the files and see whats going on..

Nobby
## Post #92
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-02T20:38:15+00:00
- Post Title: Re: Soul Calibur 4

Updated August 04, 2010
Attached Sample

I created tutorial for coloring characters with standard 3ds max tools and without photoshop.

Download Tutorial
Updated August 03, 2010

Download Sample (Shura)
Updated August 04, 2010

After tutorial you can coloring your characters like this:

[](http://s54.radikal.ru/i144/1008/63/b165a0a2d519.jpg) [](http://s42.radikal.ru/i096/1008/80/4cc3bd527a22.jpg)

[](http://s49.radikal.ru/i123/1008/e2/74d50ad24f15.jpg) [](http://s52.radikal.ru/i135/1008/0c/54586a6b3757.jpg)

[](http://s001.radikal.ru/i193/1008/4e/b4e6170a04b0.jpg)
## Post #93
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-08-02T21:22:53+00:00
- Post Title: Re: Soul Calibur 4

Ahh so the textures are being applied as an ADDITIVE texture ( in max thats the mix map )  where it has a base colour and the texture is applied on top, using the RGB tint maps to control the mixing...  They are done like that because of ' Node materials ' in Unreal 3 engine.  Ive used Node materials a little bit in Lightwave 3D and in UDK, once you get the hang of them, they are easier to get the results you want and also you can have really complex materials..

I must get around to using them more often.....  Cheers for the tutorial Tosyk i'm sure many people will find it handy especially Kingfisher13
## Post #94
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-08-02T23:27:53+00:00
- Post Title: Re: Soul Calibur 4

Grrrr.... This didn't work either...
I followed your tutorial exactly, but found two problems straight off the bat. First: I am using model 142, which is Shura. I opened the material editor, and noticed that there were no free slots. the highest number of slots I could manage was 4x6, and they were all full. I then condensed the material slots, opening two free slots. However, when I opened one of those, it did not say "(#) - default" it said "Standard_(#)" I clicked the "standard" button next to that, and it came up with a material/map browser window. This isn't how it is in the tutorial... Although, when I first opened the tutorial and my model, it did do as it said in the tutorial, then I had another issue which made me attempt to reset- then it didn't follow the tutorial anymore...
(Sigh...)  I must have done something really wrong here...
Nobby, you asked which model I was working on to see what my problem was: model #142.
Thanks guys for all your help- maybe this will work this time around...

EDIT: 
Tosyk, you seem to have this figured out. perhaps you could do what you did in the tutorial with the models for sophitia, taki, ivy, and shura, and send me the models? 
This is getting to be more frustrating then it should be... If you could do that, that would be awesome. 
Thanks again
## Post #95
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-03T03:29:15+00:00
- Post Title: Re: Soul Calibur 4

2kingfisher13:
I updated tutorial. See post above  
If you have problems just let me know.

p.s.: i can't prepare models you want for render, i have no time for this.

UPD:
I attached to my post above sample file with full prepare-for-render character of Shura with materials and textures(142):

[](http://s53.radikal.ru/i140/1008/33/fef48b532afa.jpg) [](http://s48.radikal.ru/i122/1008/60/b8cbc7990ac3.jpg)

[](http://i058.radikal.ru/1008/49/f4147da927cd.jpg) [](http://s002.radikal.ru/i197/1008/16/21f3772f91d9.jpg)

[](http://s60.radikal.ru/i168/1008/30/add8a477595d.jpg) [](http://s60.radikal.ru/i167/1008/dc/b72c27ab8898.jpg)
## Post #96
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-08-03T16:17:01+00:00
- Post Title: Re: Soul Calibur 4

Someone might find this useful. List of models for those who don't want to rummage within the files to find a certain character:

001_Mitsurugi.fbx
002_Seong_Mi-Na.fbx
003_Taki.fbx
004_Maxi.fbx
005_Voldo.fbx
006_Sophitia.fbx
007_Siegfried.fbx
008_Rock.fbx
00b_Ivy.fbx
00c_Kilik.fbx
00d_Xianghua.fbx
00e_Lizardman.fbx
00f_Yoshimitsu.fbx
011_Nightmare.fbx
012_Astaroth.fbx
014_Cervantes_de_Leon.fbx
015_Raphael.fbx
016_Talim.fbx
017_Cassandra.fbx
01a_Yun-Seong.fbx
022_Setsuka.fbx
023_Tira.fbx
024_Zasalamel.fbx
028_Hilde.fbx
029_Algol.fbx
02a_Vader.fbx
02b_Yoda.fbx
02c_Apprentice.fbx
030_Amy.fbx
040_Angol-fear.fbx
041_Kamikirimusi.fbx
042_Shura.fbx
043_Ashlotte.fbx
044_Scheherazade.fbx
050_Arcturus.fbx
080_male.fbx
081_female.fbx
082_Jacqueline.fbx
083_Auguste.fbx
084_Lizardman.fbx
085_male.fbx
086_Valmiro.fbx
087_Algol.fbx
088_Mitsurugi (gray dummy).fbx
08f_male.fbx
101_Mitsurugi.fbx
102_Seong Mi-na.fbx
103_Taki.fbx
104_Maxi.fbx
105_Voldo.fbx
106_Sofitia.fbx
107_Siegfried.fbx
108_Rock.fbx
10b_Ivy.fbx
10c_Kilik.fbx
10d_Xianghua.fbx
10e_Lizardman.fbx
10f_Yoshimitsu.fbx
111_Nightmare.fbx
112_Astaroth.fbx
114_Cervantes_de_Leon.fbx
115_Raphael.fbx
116_Talim.fbx
117_Cassandra.fbx
11a_Yun-seong.fbx
122_Setsuka.fbx
123_Tira.fbx
124_Dverger.fbx
128_Hilde.fbx
129_Algol.fbx
12a_Vader.fbx
12b_Yoda.fbx
12c_Apprentice.fbx
130_Amy.fbx
140_Angol-fear.fbx
141_Kamikirimusi.fbx
142_Shura.fbx
143_Ashlotte.fbx
144_Scheherazade.fbx
150_male.fbx
180_female.fbx
183_Marienbard.fbx
184_Lizardman.fbx
185_male.fbx
186_male.fbx
188_male.fbx
18f_female.fbx
285_male.fbx
286_male.fbx
381_male.fbx
385_male.fbx
485_male.fbx

Whenever I couldn't determine who the character is, I just put down the sex attribute (male/female).

Added a few names to the list from here: [viewtopic.php?p=51899#p51899](http://forum.xentax.com/viewtopic.php?p=51899#p51899)
## Post #97
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2010-08-03T18:46:37+00:00
- Post Title: Re: Soul Calibur 4

Thanks, Tosyk!!! YES! I finally have Shura!    
Now.... to make my evil plan work, I need one more thing... I need to know how to rig the model. I have tried ragdoll before, but it didn't make a whole lot of sense. I also tried using a biped, but I don't know how to apply a biped to a solid mesh. I also tried bones, but that is so complex I think I had better stick with biped or ragdoll. Tosyk, oh great god of 3d modeling, can you show me how to animate the model you just posted for me? 
That would make my week.   

Also, I know you said you were busy, but if you ever had time, I would greatly appreciate it if you were to share Taki, Sophitia, and Ivy the same way you shared Shura. I think many people out there would also thank you.

Thanks,
Kingfisher13
## Post #98
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-03T19:00:52+00:00
- Post Title: Re: Soul Calibur 4

> Reply from kingfisher13
>
> Missing DLLS

Filename: vrender2009.dlr   Class: VRay Mtl  SuperClass: 0xC00
Filename: vrneder2009.dlr   Class: VRayHDRI  Superclass: 0xC10
Filename: vrender2009.dlr   Class: VRayLight  Superclass: 0x30
Filename: vrender2009.dlr   Class: V-Ray DEMO 1.50.SP2 Superclass: 0xF00

How can I fix this?Install latest Vray (additional renderer). You don't get same quality of renders like on my post above if you will use standard 3ds max renderer.

p.s.: I use 3ds max 2009 and Vray 1.50
## Post #99
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-08-04T14:18:58+00:00
- Post Title: Re: Soul Calibur 4

Hey tossyk, can you upload the Ivvy from the render you posted before?? Just want to see something in your materials settings
## Post #100
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2010-08-05T13:17:25+00:00
- Post Title: Re: Soul Calibur 4

does anyone know how to take your modified textures or model and put it back into the game?
## Post #101
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-08-05T13:27:10+00:00
- Post Title: Re: Soul Calibur 4

Awww come on guys give Tosyk a break now... 

You have access to all the files now, Tosyk has shown us all how to get the textures looking correct in MAX, and he even uploaded a finished model for us to all compare against. He then said he didn't have time to do anymore stuff ( he actually said it before posting the finished model ) 
And people are still asking for easy things like models and rigging help.   He has provided more than enough to be able to help all of us get the models looking proper in max ourselves, so there is no need for him to post the other character models ( which in all fairness kingfisher. nobody else needed those models, it was just you that specifically wanted those ones. your just looking for someone else to do all the work for you ) 
And a rigging tutorial ?!?   there are hundreds of tutorials all over the internet regarding rigging charcters in 3ds max. if you need to know how max works id suggest you read some of those. This really isnt the place to be asking for or expecting to get help with the basic functionality of 3dsmax, This is a file format information site, not a 3ds max site. 

When tosyk said he didn't have the time , he really doesnt.  he is active in loads of different threads, this is just one of many he posts in. 
so how about we cut him some slack and stop asking him to supply everything for us.

Besides, count yourselves lucky    while you just have to follow the tutorial tosyk provided. I have to try and translate his tutorial into some thing that kinda looks like this..(below). but more complex   This is basically how unreal engine and Lightwave ( the 3d app i use ) sees Node based materials ( thats why you have things like the mix map texture where you only use the red channel, thats all from node based materials )
[](http://img203.imageshack.us/i/83900250.jpg/)
That image is actually 1 section ( of 5 ) that are used to make up a indoor water material ( complete with animating waves )
## Post #102
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2010-08-10T03:13:16+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Tosyk
>
> Updated August 04, 2010
Attached Sample

I created tutorial for coloring characters with standard 3ds max tools and without photoshop.

Download Tutorial
Updated August 03, 2010

Download Sample (Shura)
Updated August 04, 2010

After tutorial you can coloring your characters like this:

I don't have XBox or PS3.
So... Could you please upload Ivy's model too? I really like that babe... nice and hot
## Post #103
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2010-08-10T03:37:38+00:00
- Post Title: Re: Soul Calibur 4

The contents of this post was deleted because of possible forum rules violation.
## Post #104
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2010-08-13T21:25:39+00:00
- Post Title: Re: Soul Calibur 4

Hi everybody. Can anybody say how fix this bug (look attach)?
Or it's normally? Has anybody tihs problem too?
P.S. On Tosyks pictures sabers and skull on themselfs places. Sorry my English.

Тосик, может ты подскажешь где я делаю ошибку?

мой алгоритм: пуск->cmd-> перетаскиваем туда xbdecompress.exe R_ALL_042_360.spd выбираем перезаписать
cmd-> перетаскиваем туда SPD_EX.exe R_ALL_042_360.spd -> давим enter
[Shura_bug.jpg](https://xentaxbackup.github.io/file/3319_Shura_bug.jpg)
## Post #105
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-08-14T10:28:11+00:00
- Post Title: Re: Soul Calibur 4

Realign those parts manually.
## Post #106
- Username: Neo Cyrus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 25, 2010 2:45 pm
- Post datetime: 2010-08-25T21:06:31+00:00
- Post Title: Re: Soul Calibur 4

I was surprised when I saw there was progress on this. I suppose the last time I looked it up it wasn't listed on the first several pages of google.

I registered on this forum to basically start learning, I was hoping Tosyk or one of you who have progressed could write a mini guide/FAQ for those of us (such as myself) who are completely new to this and haven't the slightest clue what to do.

As someone pointed out before I know this isn't the place to be asking how to use 3DS Max, but a mini guide pointing in the right direction is what I'm asking about in case there are some specifics here we need to know that a general guide might not point out. Just a guideline to know what to do, from there we can look it up and find out ourselves.
## Post #107
- Username: DioBrando
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 06, 2010 11:59 am
- Post datetime: 2010-09-08T00:24:42+00:00
- Post Title: Re: Soul Calibur 4

I'm trying to follow the IVY tutorial by Tosyk, can someone tell me what's wrong here?:
[http://i.imgur.com/hSsA0.jpg](http://i.imgur.com/hSsA0.jpg)

The gold doesn't seem to mix with the purple at the composite node.
## Post #108
- Username: vicviper573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 21, 2010 7:19 am
- Post datetime: 2010-10-08T09:12:56+00:00
- Post Title: Re: Soul Calibur 4

This thread hasn't been touched in awhile, which is a shame since there is some really great info here, - enough to inspire me into doing some modding, and to sign up here and contribute myself.

I was hoping that it would somehow be possible to extract and inject assets from/to the other.spd files in the creation/model directory; specifically the customization parts like F_BODY, F_JKET, F_CHAM, etc.  The old utility seemed to extract only from the R_ALL files, and I don't think it had a way to re-inject into the big files.

 I have tried Itze's method of manually pasting the edited texture data from hex workshop into the .spd, but failed miserably - maybe a step by step walkthru with screens would make it possible.  I'd love to be able to edit the textures as I'm pretty good in photoshop.  Itze, please help?

Messing around with the files, I have made some progress, and my notes I'm sure may be of use to others.  The customization parts can can be swapped with one another, and makes for some interesting effects.  If you want to get an "almost topless" character - you can replace the data of file where their geometry isn't hidden to save polygons (I recommend Coiled Breastplate since it's ugly anyway) - and replace it with something that has little consequence to the model such as wings or socks, and bam, they're almost topless - but there are these gray "strips" that remain on the model to cover them.  It may be possible to edit the texture.. if only we could get access to F_NUDE_001 and re inject...



I have also found that replacing F_NUDE_001's data with LM_NUDE_001 will allow you to make a lizard female; or basically a female character with a lizard body that still looks right and plays properly - very interesting to see. Hey, Ivy here is nude.. but alas, she isn't human...


To make this stuff possible, I went into literally dozens of the customization assets and identified them best I can (as they are named in the game).  I'll post the results of this here.  Its not complete, but it covers most of the useful assets that can be used to mod the character body.  

F_JKET_201_360: Ashigaru Shirt
F_JKET_202_360: Sleeveless Kimono
F_JKET_203_360: Leather Tunic
F_JKET_204_360: Cloth Tunic
F_JKET_206_360: Short Shirt
F_JKET_208_360: Prayer Robe
F_JKET_212_360: Frilled Blouse
F_JKET_213_360: Longming Qipao
F_JKET_214_360: Tight Shirt
F_JKET_215_360: Jester's Clothes
F_JKET_218_360: Clergy Clothes
F_JKET_221_360: Longhua Qipao
F_JKET_222_360: Hemp Kimono
F_JKET_223_360: Warrior's Robe
F_JKET_224_360: Priestess Kimono
F_JKET_226_360: Battle Dress
F_JKET_230_360: Arabesque Vest
F_JKET_232_360: Kongtian Armor
F_JKET_235_360: DLC? Secret??? Pretty Blouse
F_JKET_236_360: Menghu Clothes
F_JKET_237_360: Wonder Jacket
F_JKET_238_360: Drum Corp Jacket
F_JKET_240_360: DLC? Secret??? Sleeves 
F_JKET_241_360: White Shirt
F_JKET_242_360: DLC? Secret???  Torn School Shirt
F_JKET_243_360: DLC? Secret???  Sailor Shirt
F_JKET_246_360: Flight Jacket
F_JKET_247_360: Nurse's Uniform
*F_JKET_248_360: Frilled Apron
F_JKET_249_360: Parlor Blouse
F_JKET_250_360: DLC? Secret??? Plaid Parlor Blouse 
F_JKET_252_360: DLC? Secret??? Fur-trimmed dress
F_JKET_254_360: Kittymeow Suit
F_JKET_255_360: Kunoichi Robes
F_JKET_256_360: Bong-seon Blouse
F_JKET_258_360: DLC? Secret??? Striped Sleeves
F_JKET_259_360: Kitty Tunic? Panties??
F_JKET_262_360: Atalanta's Jacket
F_JKET_264_360: Frilled Drape
F_JKET_266_360: Princess Dress
*F_JKET_267_360: Spy Robe
F_JKET_269_360: Night Butterfly Dress
F_JKET_270_360: Raven Dress
F_JKET_271_360: Huayin Dress

F_BODY_005_360: Sarashi
F_BODY_008_360: Tanned Leather Armor
F_BODY_009_360: Chain Mail
F_BODY_011_360: Sleeveless Shirt
F_BODY_012_360: Scaled Suit
F_BODY_016_360: Full Leggings
F_BODY_017_360: Ring Trousers
F_BODY_018_360: Leggings
F_BODY_020_360: Atalanta's Tights
F_BODY_021_360: Bordered Suit
F_BODY_024_360: Hunter's Suit
F_BODY_025_360: Tiger Lily Stockings
F_BODY_028_360: Bong-Seong Underwear
F_BODY_030_360: Kunoichi Tights
F_BODY_032_360: Belle Dress

*F_CHAM_201_360: Dancer's Breastplate
*F_CHAM_202_360: Coiled Breastplate
*F_CHAM_204_360: Tiger Lily Breastplates
*F_CHAM_205_360: Voodoo Breastplate
F_CHAM_206_360: Tortoise Cuirass
F_CHAM_207_360: Breastplate
F_CHAM_209_360: DLC? Secret??? Breastplate; covered
F_CHAM_211_360: Gorgon Cuirass
F_CHAM_212_360: Thief's Belt
F_CHAM_213_360: Quiver
F_CHAM_214_360: Dragon Breastplate
F_CHAM_217_360: Ashigaru Cuirass
F_CHAM_218_360: Scarlet Blossoms
F_CHAM_220_360: Menghu Cuirass
F_CHAM_221_360: Goddess Cuirass

F_SOKS_201_360: Shinobi Tabi
F_SOKS_202_360: Bandages
F_SOKS_205_360: Short Socks
F_SOKS_206_360: DLC? School Socks
F_SOKS_207_360: DLC? Loose Socks
F_SOKS_208_360: Laced Stockings
F_SOKS_210_360: Night Butterfly Socks
F_SOKS_211_360: Huayin Socks

F_WCBL_206_360: DLC? Maid Apron..?
F_WCBL_207_360: Kitty Sash

F_NUDE_001_360: Base Female

F_MANT_202_360: Roman Mantle
F_MANT_203_360: Feathered Wings
F_MANT_204_360: Jolly Roger
F_MANT_205_360: Priestess Mantle
F_MANT_206_360: War Cloak


Didn't do these fully, but I could tell that they were generally:

F_BOTS: Boots
F_ARAM: Wrist
F_FAAM: Arm
F_HEBD: Headgear
F_LGAM: Leg Armor
F_SHAM: Shoulder Armor

F_SHOS: Shoes/Sandals
F_SKRT: Skirt
F_SOKS: Socks/Stocking
F_WSAM: Waist Armor

LM_CHAM: Lizard Chest Armor
LM_HAIR: Lizard Head Accessory
LM_NUDE: Lizard Body
LM_SHAM: Lizard Shoulder Armor
LM_WSAM: Lizard Waist Armor

F is for female, LM is for Lizardman, M is for Male.
* = allows for "almost topless" base

I'm hoping its still possible to spur some activity for this beautiful game.  I am very thankful to this board for the info it provided, and would love to give back and keep the thread going.  So here's hoping there's a way to get some texture work into the game - especially for the character customization parts!
## Post #109
- Username: jordanpower6
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 28, 2010 8:27 pm
- Post datetime: 2010-10-13T10:52:56+00:00
- Post Title: Re: Soul Calibur 4

How do you open the models in 3d max 9?
## Post #110
- Username: vicviper573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 21, 2010 7:19 am
- Post datetime: 2010-10-18T04:51:02+00:00
- Post Title: Re: Soul Calibur 4

I was eventually able to manually extract all the textures from the files that wouldn't work with the extractor, by searching for the GIDX then skipping 12 positions to find the start of the file.  Itze's method of opening the edited texture in hexworkshop, ignoring the first 80, copying the data, then replacing it over the main file after doing the 16 bit byte flip works perfectly.  By doing that method I was able to replace textures on pretty much any of the customization parts - allowing for a whole new world of custom characters.

I've opened the models in 3DSmax 10 by importing them as fbx.  A lot of work to make them usable for anything, it seems.
## Post #111
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-10-23T14:09:50+00:00
- Post Title: Re: Soul Calibur 4

Hi
I was bored, and was working on correcting the colours on Amy. 

I thought I would share a summary of the things I used and gathered.

Item 1 - Models
Nobby Posted packs of the models:

Characters - 494mb
[url]hxxp://[www.megaupload.com/?d=4C5PS7F7](http://www.megaupload.com/?d=4C5PS7F7)[/url] OR [url]hxxp://depositfiles.com/files/a2jw75ius[/url]
Stages 317 mb
[url]hxxp://[www.megaupload.com/?d=BJK9NDWP](http://www.megaupload.com/?d=BJK9NDWP)[/url] OR [url]hxxp://depositfiles.com/files/agevh1qct[/url]
Weapons 86mb
[url]hxxp://[www.megaupload.com/?d=SOYNC1TZ](http://www.megaupload.com/?d=SOYNC1TZ)[/url] OR [url]hxxp://depositfiles.com/files/fm7lkanme[/url]

Item 2 - Image Samples from the game
I took image captures using my capture card:
[url]hxxp://[www.mediafire.com/?rdjw1o972zgfzy4](http://www.mediafire.com/?rdjw1o972zgfzy4)[/url]

Item 3 - Texture Colouring Guide
Tosyk made a nice guide showing how to set materials in 3dsmax:
[url]hxxp://[www.sendspace.com/file/clhj6u](http://www.sendspace.com/file/clhj6u)[/url]

his guide is pretty good, except that he is using mix/blend instead of Mask. all you need to form a proper diffuse is Composite, Multiply, and Mask.
anyway I mirrored it in a HUGE image link:

[http://img51.imageshack.us/img51/7269_a/image1nc.png](http://img51.imageshack.us/img51/7269_a/image1nc.png)
## Post #112
- Username: TIOVICKO
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 30, 2010 1:18 pm
- Post datetime: 2010-10-25T03:24:17+00:00
- Post Title: Re: Soul Calibur 4

Thank You So Much mariokart64n I truly appreciate your time and effort
## Post #113
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2010-11-15T16:53:58+00:00
- Post Title: Re: Soul Calibur 4

@vicviper573:

can you please write a step by step process for having nude characters ? or if possible uploading a .bat for the copy / renaming ?

what files you have to exchange exactly ?

I'll be using the PS3 version, as the files are visible and easilly exchangeable...

Thanks in advance
## Post #114
- Username: vicviper573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 21, 2010 7:19 am
- Post datetime: 2010-12-15T19:32:15+00:00
- Post Title: Re: Soul Calibur 4

> Reply from orbbu
>
> @vicviper573:

can you please write a step by step process for having nude characters ? or if possible uploading a .bat for the copy / renaming ?

what files you have to exchange exactly ?

I'll be using the PS3 version, as the files are visible and easilly exchangeable...

Thanks in advance

I use the 360 version, for those same reasons, technique should still work, but I don't have a PS3 setup for this to test.

1.  Get your desired .spd file and decompress it with xbdecompress. (for 360 version only I'm guessing)  If you want a nude character, I suggest modding something in the undergarments (F_BODY) section like Tanned Leather Armor (F_BODY_008)  or Scaled Suit (F_BODY_012).  You can also edit F_NUDE itself which is the basic underwear which may be easier to photoshop. I have not yet found the model/file for what's "under" the F_NUDE basic clothing which is what I show in the screenshots earlier in the thread, so if anyone cares to help, please assist.

2.  Use SPD_EX.exe to extract the file.  If it spits out another SPD file, you may have to do this a few times.  Do this until it spits out DDS files, which is what you'll be editing in photoshop.

3.  Make sure you have the Nvidia DDS plugin installed into your photoshop, or it won't load.  Google it, its a free dev tool available on nvidia's site.

4.  Open the DDS files in photoshop and have fun making your nudies/customs/etc.  If you open a file thats blue tinted, thats a normal map, which is used for surface details, height maps, bumps n such.  Your nvidia DDS plugin will give you the ability to turn grayscale images into normalmaps with desired height and effects.  If you aren't experienced with this, experiment and look up techniques on the net.  If you edit a texture, you should definitely edit its normal map to match it, otherwise it will NOT LOOK RIGHT when you get it back into the game, and will still have its original bumps and normalmapping.  Simple temporary solution?  Use color picker on a part of the blue texture and paint over the whole thing flat blue.  But if you are skilled, you can use the normal maps do some great things when modding the graphics.

5.  Make sure you save your edited texture as DDS, DXT1 (No Alpha) with 3 mipmaps.  Double check that the file size is the same as it started.

6.  Dump the edited DDS into Hex Workshop.  Go to Tools -> Operations -> Byte Flip -> 16 bit.  It will alter the data.

7.  Go to position 80 in the file.  This is the start of the actual texture data.  Hold SHIFT and hit END, or Down Arrow/page down until you hit the end of the file.  You can select it with your mouse too but that takes forever.  According to Hex Workshop, you should have A800, 15000, or 2A000 bytes selected. Remember this value.  Hover your mouse over the HEX window (the one on the left) right click and COPY.

8.  Have the source SPD file also opened in Hex Workshop. You want to determine which texture you want to replace.  Do a search for GIDX.  Hex Workshop will make a nice little list for you in the lower right pane of each instance and you can navigate to each by clicking on the instance.  SPD_EX extracted the textures in the order it found them in, thus the texture you want to replace will correspond accordingly.  For instance, the first texture SPD_EX spat out will be after the first GIDX instance, the second will be after the second GIDX and so forth.  I double checked by comparing the data with what spd_ex had extracted just to be sure and to get the hang of things, so you might want to as well, your first time around.

9.  After you find the instance of GIDX you want to replace, move your cursor to just after the 'GIDX'.  Now press Right Arrow 12 (twelve) times.  This is the start of the texture data.    Go to Edit -> Select Block.  Remember how big the data block you copied was?  It was either A800, 15000, or 2A000.  Enter the appropriate size value into the prompt ('Hex' and Size of Block' should be selected as well), and then hit 'OK'  The data area will be highlighted.

10.  Hover your mouse over the HEX window (the one on the left) right click and hit PASTE.  The data you copied from the edited DDS should replace the data in the SPD.  Save the SPD.  The game will read uncompressed SPD's so you can go ahead and copy that right back into the game.

11.  Test, show off, blog, fap, etc.  Share with us here!
## Post #115
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2010-12-16T03:25:31+00:00
- Post Title: Re: Soul Calibur 4

Thanks for the write up on this and all your help  

I can change basic textures but I still need to experiment more.  One thing I noticed was some stuff such as armor or clothing are actually DXT5 with alphas and not DXT1.  Also trying to figure out how to corrupt certain items as mention in previous post by Itze so the models dont intefere or show all together.  It seems textures/normal maps can be edited and injected back in however the underlying mesh is still there.  So the question is once the mesh is edited in 3ds max or whatever how do you inject them back into the game?   You can find GIDX for textures by its dds name/number but how do you do this for the other stuff like obj,fbx.. etc?

Also in order for you to see whats visible in the F_NUDE_001_360.spd, after extracting the file with spd_ex.exe you'll get 2 files: 

F_NUDE_001_360_000.spd
F_NUDE_001_360_001.spd.   

Just run the extractor again on the first file F_NUDE_001_360_000.spd and you should be able to get the textures, obj and fbx files.  This is the same for weapons models.

The only thing available however are the mesh/model and texture/normal map for undewear.  There is no texture/normal map for skin etc. And of course no face mesh as this is generic fit for all characters.  So the resources are just pointing to each character's assets or a different location.

The question I have though is how will you inject this back in since they were two separate spd files coupled together in one file.  Where would you look for the GIDX or equivalent?

Great progress so far, hoping the good work continues perhaps even lead to a stand lone compiler of some sort.
## Post #116
- Username: vicviper573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 21, 2010 7:19 am
- Post datetime: 2010-12-16T04:13:32+00:00
- Post Title: Re: Soul Calibur 4

I'll have to look at them again to see which ones had the DXT5 with alphas.  I know there were some parts that had magenta-blue zoning which determined which color zone would be affected when you edit them in the character creation menu (Jester clothes come to mind).  Others like Hunter Suit have a way of "cutting out" areas of the texture to make parts of them transparent for holes, torn edges or a more seamless look.  Most of my discussion on this is from memory as I haven't touched this stuff in some months but hopefully I can find some time to mess around with it again soon.

One thing I am desperate to find out is where the SPECULAR data is being kept in regards to the textures. If you aren't familiar with the term, specular maps define the level of shininess or light reflection a texture or material experiences as it interacts with the ingame lights.   In other games, the specular map is kept either as a seperate grayscale image or as the alpha channel in the main diffuse texture or normal map files.  I have NOT been able to find out how Soul Calibur IV does this, and would really like to decrease/increase the specular intensity on a lot of the items for better customization.  An example of the behavior ingame: the Sarashi bandages undergarment is not shiny at all, while the Kunoichi tights undergarment is really, really shiny.  The materials define this behavior somewhere, just don't know how to change it yet.  HELP!

As for editing the models, I believe that Itze corrupted Sophitia's blouse by zeroing random places in her spd file.  The geometry data of course would be where the textures are not.  I've also done this to models, backgrounds, etc too, with varying results, and nothing useful as of yet.  Its like shooting in the dark.  I haven't heard of a way of importing them back to fbx after they have been opened in 3Ds, which is why I haven't tried to do anything in it at all.


> Reply from skytoast
>
> Thanks for the write up on this and all your help  

I can change basic textures but I still need to experiment more.  One thing I noticed was some stuff such as armor or clothing are actually DXT5 with alphas and not DXT1.  Also trying to figure out how to corrupt certain items as mention in previous post by Itze so the models dont intefere or show all together.  It seems textures/normal maps can be edited and injected back in however the underlying mesh is still there.  So the question is once the mesh is edited in 3ds max or whatever how do you inject them back into the game?   You can find GIDX for textures by its dds name/number but how do you do this for the other stuff like obj,fbx.. etc?

Also in order for you to see whats visible in the F_NUDE_001_360.spd, after extracting the file with spd_ex.exe you'll get 2 files: 

F_NUDE_001_360_000.spd
F_NUDE_001_360_001.spd.   

Just run the extractor again on the first file F_NUDE_001_360_000.spd and you should be able to get the textures, obj and fbx files.  This is the same for weapons models.

The question I have though is how will you inject this back in since they were two separate spd files coupled together in one file.  Where would you look for the GIDX?

Great progress so far, hoping the good work continues perhaps even lead to a stand lone compiler of some sort.
## Post #117
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2010-12-17T13:30:35+00:00
- Post Title: Re: Soul Calibur 4

@vicviper573, thanks for the tutorial  I'll test that when I'll have some free time
## Post #118
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2011-01-17T13:34:21+00:00
- Post Title: Re: Soul Calibur 4

if anyone would like to send me the dds files i can make them nude and send them back to u.  i am a great artist but not so good with technical programming or any crazy injecting extracting stuff.
## Post #119
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2011-01-19T16:30:14+00:00
- Post Title: Re: Soul Calibur 4

.
## Post #120
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2011-01-19T17:20:47+00:00
- Post Title: Re: Soul Calibur 4

sprayer
In your pic it looks like she is about to take a dump.
## Post #121
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2011-01-19T17:49:25+00:00
- Post Title: Re: Soul Calibur 4

firsak забыл сменить ей выражение на физиономии))
## Post #122
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-02-09T15:48:38+00:00
- Post Title: Re: Soul Calibur 4

Maybe you find this [useful](http://cgig.ru/en/2011/02/converting-3d-model-from-soul-calibur-4-en/).
## Post #123
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-10T02:23:09+00:00
- Post Title: Re: Soul Calibur 4

Thanks a lot tosyk
## Post #124
- Username: Antuniey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 14, 2011 11:40 pm
- Post datetime: 2011-02-21T18:33:43+00:00
- Post Title: Re: Soul Calibur 4

hello... hey... somebody can send to me where I get a "spd extractor"??? XD
## Post #125
- Username: ekul1021
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 23, 2011 4:21 am
- Post datetime: 2011-03-22T20:24:16+00:00
- Post Title: Re: Soul Calibur 4

Are you guys using a modded Xbox 360 for this?
## Post #126
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-03-22T20:57:38+00:00
- Post Title: Re: Soul Calibur 4

> Reply from ekul1021
>
> Are you guys using a modded Xbox 360 for this?

Nope, install your game in an USB memory flash and then extract those files to your PC using some scene 360 software or download an iso of the game.
## Post #127
- Username: Logan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 26, 2011 11:20 pm
- Post datetime: 2011-03-26T15:28:58+00:00
- Post Title: Re: Soul Calibur 4

Ok I'm sorry for reviving this, but I have no knowledge about 3dsmax or anything, but I really want to get some nice high res screenshots of my favorite Ivy. I've downloaded a characters archive posted here and even managed to open Ivy model in 3dsmax (it's the first one, R_ALL_00b_360.lbx). But when I try to render it, it says that textures missing and asks me to show the way where they are. I do but program still can't see them. Any help please. Or better yet, is it possible to simply post here a ready Ivy model in any 3d program?
## Post #128
- Username: inferry
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 30, 2011 3:10 am
- Post datetime: 2011-03-30T07:31:49+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Logan
>
> Ok I'm sorry for reviving this, but I have no knowledge about 3dsmax or anything, but I really want to get some nice high res screenshots of my favorite Ivy. I've downloaded a characters archive posted here and even managed to open Ivy model in 3dsmax (it's the first one, R_ALL_00b_360.lbx). But when I try to render it, it says that textures missing and asks me to show the way where they are. I do but program still can't see them. Any help please. Or better yet, is it possible to simply post here a ready Ivy model in any 3d program?

You are not reviving nothing, the tread only have four days of inactivity.
For the model, you must optimize the textures in order to 3dMax to show them, I encourage you to follow the Tosyk's tutorial, like 4 or 5 coments above.

> Reply from maniacoloco
>
> ekul1021 wrote:Are you guys using a modded Xbox 360 for this?

Nope, install your game in an USB memory flash and then extract those files to your PC using some scene 360 software or download an iso of the game.

How you do that, as far as I know you can't install a game in any other place than the hard drive?

Now to the topic:
The characters pack that was posted here before does not only contains the figthing characters, but the characters that you must have to figth in some history mode events, it also contains the models from the initial cut-escene of Algol and Arcturus who apears at the last time just before to be turned in cristal or ice, wathever, and the gray mitsurugi "dummy" the game use for show the combos list and combat practice.
Thank you so much for sharing them.

This is a little update to the firsak's characters list:
088_Mitsurugi.fbx ----> 088_GMitsurugi_Dummy.fbx
101_male.fbx ---------> 101_Mitsurugi.fbx
104_male.fbx ---------> 104_Maxi.fbx
108_male.fbx ---------> 108_Rock.fbx
112_male.fbx ---------> 112_Astaroth.fbx
114_male.fbx ---------> 114_Cervantes_de_Leon.fbx

Now for the users of 3DMax, is there a way to export the bones out to max to any other format like .bvh or .c3d), I want them to used it on blender, but any usable format would be welcome.
If this is not posible, how can I see the vertices afected for certain bones in 3DMax?

Tanks in advance.  
Sorry for my english.
## Post #129
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-31T15:23:25+00:00
- Post Title: Re: Soul Calibur 4

> Reply from inferry
>
> This is a little update to the firsak's characters list:
088_Mitsurugi.fbx ----> 088_GMitsurugi_Dummy.fbx
101_male.fbx ---------> 101_Mitsurugi.fbx
104_male.fbx ---------> 104_Maxi.fbx
108_male.fbx ---------> 108_Rock.fbx
112_male.fbx ---------> 112_Astaroth.fbx
114_male.fbx ---------> 114_Cervantes_de_Leon.fbx

Now for the users of 3DMax, is there a way to export the bones out to max to any other format like .bvh or .c3d), I want them to used it on blender, but any usable format would be welcome.
If this is not posible, how can I see the vertices afected for certain bones in 3DMax?
thanks for sharing your researches, you can export animation in *.fbx from max and importing *.fbx files into the blender, but i'm not really sure about animation, just try your luck
## Post #130
- Username: inferry
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 30, 2011 3:10 am
- Post datetime: 2011-04-01T03:08:55+00:00
- Post Title: Re: Soul Calibur 4

But the *.fbx format is exclusive to autodesk applications, you can export them from blender but you can't import to it, there was a plugin in development but they never finished, I actually have tried with all the available file formats in 3DMax that blender can import, like *.dae, *.dxf, etc. many import just the mesh with UV and others like collada, don't import nothing.

That's why I was asking for only animation because I see the option in 3DMax but it says  that no frames were animated (or something like that).

So i'm still looking a way to export the stuff, and now that I think abouth it, witch file format is the one you get from the *.spd files afther extraction? is the *.fbx?

Anyway, thanks for the help.

@orbbu
Could you post the PS3 model for cassandra if you have it, I would like to see the diferences in the polys of the models.

Edit: corrected "Autodesk" instead of "adove", that should be "Adobe" by the way
## Post #131
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-01T03:27:24+00:00
- Post Title: Re: Soul Calibur 4

> Reply from inferry
>
> But the *.fbx format is exclusive to adove applications, you can export them from blender but you can't import to itah, yeah you right, sorry, so no way for now, or maybe you can find more help on blender nation
## Post #132
- Username: ekul1021
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 23, 2011 4:21 am
- Post datetime: 2011-04-03T15:46:24+00:00
- Post Title: Re: Soul Calibur 4

Is it possible to edit and put the "edited" clothing texture back into the game without using 3dmax?
## Post #133
- Username: daydreamdirty
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 05, 2011 7:23 pm
- Post datetime: 2011-04-05T11:26:25+00:00
- Post Title: Re: Soul Calibur 4

Ok definitely interested in this whole thread and read it all.  I will see how far i can get hacking soul calibur 4 but in the mean time i have a question.  

Who here has successfully hacked it so far?
And if so, can you make me a copy?
Willing to pay for your services if that's what it takes.
## Post #134
- Username: daydreamdirty
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 05, 2011 7:23 pm
- Post datetime: 2011-04-05T11:27:43+00:00
- Post Title: Re: Soul Calibur 4

Also forgot to mention i'm primarily interested in the nude hack but if there's other cool hacks out there....say a lightsaber hack, that would definitely be wanted as well.
## Post #135
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2011-04-06T07:14:02+00:00
- Post Title: Re: Soul Calibur 4

> Reply from ekul1021
>
> Is it possible to edit and put the "edited" clothing texture back into the game without using 3dmax?

No first of all you dont use 3DSmax at all to put anything back into the game.  You're using 3DSMax (or other 3D application) to edit the characters from the extracted models, textures, etc. from the game.  Unfortunately, it isn't a simple process to reverse this and put all this edited stuff back into the game.   You're using spd tools to extract the models but there isn't a compiler to bundle it all back together.  Also if you're using an xbox360, its pretty strict in terms of what can be changed since there is some sort of CRC-like check so any changes in file size and such will cause the game to freeze.   Not sure how it goes on the PS3 but I imagine it to be very similar.  

The down and dirty method is using a hex editor but this isnt an easy process.  You can read about it in previous posts in this thread.  The only other "easy" trick is model swapping existing clothing which is simply done by rearranging or "renaming" files.  As for a nude hack (...always seem to be the sought after thing in these kind of games... gees.. lol), sorry but doesnt exist in this game.  The developers did not include the extra meshes (either to save space/game resources or keep dirty minds away ..hehe) so all the "private parts" are missing.  If you were to remove all the clothing, you'll get these empty areas that resemble blank patches or just an empty space.  If you're still persistent, the best you could probably do is create it yourself but good luck trying to get it to work - for reasons already mentioned =).
## Post #136
- Username: ekul1021
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 23, 2011 4:21 am
- Post datetime: 2011-04-06T07:33:43+00:00
- Post Title: Re: Soul Calibur 4

So I'm guessing that if I want to edit like "boots that are too high" which I want to shorten them down by making an alpha channel, its gonna be like a transparent space on the game huh?
## Post #137
- Username: daydreamdirty
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 05, 2011 7:23 pm
- Post datetime: 2011-04-06T12:02:58+00:00
- Post Title: Re: Soul Calibur 4

> Reply from skytoast
>
> ekul1021 wrote:Is it possible to edit and put the "edited" clothing texture back into the game without using 3dmax?

No first of all you dont use 3DSmax at all to put anything back into the game.  You're using 3DSMax (or other 3D application) to edit the characters from the extracted models, textures, etc. from the game.  Unfortunately, it isn't a simple process to reverse this and put all this edited stuff back into the game.   You're using spd tools to extract the models but there isn't a compiler to bundle it all back together.  Also if you're using an xbox360, its pretty strict in terms of what can be changed since there is some sort of CRC-like check so any changes in file size and such will cause the game to freeze.   Not sure how it goes on the PS3 but I imagine it to be very similar.  

The down and dirty method is using a hex editor but this isnt an easy process.  You can read about it in previous posts in this thread.  The only other "easy" trick is model swapping existing clothing which is simply done by rearranging or "renaming" files.  As for a nude hack (...always seem to be the sought after thing in these kind of games... gees.. lol), sorry but doesnt exist in this game.  The developers did not include the extra meshes (either to save space/game resources or keep dirty minds away ..hehe) so all the "private parts" are missing.  If you were to remove all the clothing, you'll get these empty areas that resemble blank patches or just an empty space.  If you're still persistent, the best you could probably do is create it yourself but good luck trying to get it to work - for reasons already mentioned =).

well thanks.  If i had this for the PC, i'd definitely go mod it, but i was already unsure since this is the Xbox we're talking about here.  I'm not about to get my new xbox banned.  But regardless, thank you all for your help.
## Post #138
- Username: dzk87
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 08, 2011 5:34 am
- Post datetime: 2011-04-08T14:38:35+00:00
- Post Title: Re: Soul Calibur 4

So I download the Shura model that Tossyk gave us, but when I open it, I get missing textures errors...
I renamed the right ones, but they still won't show properly.
## Post #139
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-17T19:00:41+00:00
- Post Title: Re: Soul Calibur 4

> Reply from maniacoloco
>
> ekul1021 wrote:Are you guys using a modded Xbox 360 for this?

Nope, install your game in an USB memory flash and then extract those files to your PC using some scene 360 software or download an iso of the game.

I've seen this thrown around a bit, But I am unsure on how to actually get files off the usb in a usable format.

When I last tried, the game had been split into smaller archives on the usb drive. Is there an actual program out there that'll convert those files into one .iso or into a format that can be readily explored?
## Post #140
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-04-18T03:44:53+00:00
- Post Title: Re: Soul Calibur 4

> Smaller archives

You mean like split rar archives?
I don't really understand how it makes that much of a difference whether you use a USB, flash card, external HDD, or whatever methods people suggest.

Just extract the files or combine them if they're split into .001, .002, etc. and then use Schtrom 360 or any other 360 back-up tools to extract the contents of the full 360 image.
## Post #141
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2011-04-19T00:33:59+00:00
- Post Title: Re: Soul Calibur 4

> Reply from finale00
>
> Smaller archives

You mean like split rar archives?
I don't really understand how it makes that much of a difference whether you use a USB, flash card, external HDD, or whatever methods people suggest.

Just extract the files or combine them if they're split into .001, .002, etc. and then use Schtrom 360 or any other 360 back-up tools to extract the contents of the full 360 image.

Well, Whenever you use the dashboard software to install a game to a usb drive/HDD, The Image is packed into archives such as 'data0001, data0002" and so on.

So rather than the the XBox creating a giant 6.5 GB image, It creates a bunch of 128 MB or so fragments.

It is those fragments 'data0001, data0002' that I am unable to combine or extract an image from... Unless I am missing something
## Post #142
- Username: Shad
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 05, 2011 4:32 pm
- Post datetime: 2011-05-05T11:53:16+00:00
- Post Title: Re: Soul Calibur 4

Hello,
in each character textures there is some weird green textures that are probably related to the normal maps.

Each one has the following RGBA channels:
red: black
green: a texture
blue: black
alpha: another texture
the green and alpha channel textures look like normal map component.

Does anybody here have an idea of how to use it?
## Post #143
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2011-05-07T05:41:06+00:00
- Post Title: Re: Soul Calibur 4

Those green dds files appear to be normal maps for skin textures.  Not sure how it translates or how its handled in the game engine.  I have seen similar maps in sports games like NBA2K series for the players.  Not sure how to properly edit these either but I imagine it should work similarly.  Everything else like equipment and clothing in the game have the 'normal' normal maps (blue-purple).  I guess you could experiment and see what works.  Also be aware these green textures are DXT5, so includes alpha unlike DXT1 like the other textures.
## Post #144
- Username: ekul1021
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 23, 2011 4:21 am
- Post datetime: 2011-05-30T16:52:12+00:00
- Post Title: Re: Soul Calibur 4

Looks like someone has managed to make clothes editing here.

[http://www.coregrafx.info/sexy/moegrafx.php?res=1685](http://www.coregrafx.info/sexy/moegrafx.php?res=1685)

Don't know how they did it though.
## Post #145
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-06-08T02:41:56+00:00
- Post Title: Re: Soul Calibur 4

why I can't get the texture folder?
[no texture folder.jpg](https://xentaxbackup.github.io/file/4309_no texture folder.jpg)
## Post #146
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2011-06-24T09:10:06+00:00
- Post Title: Re: Soul Calibur 4

For those of you who played and are familiar with the game, here is the complete list of all characters (with proper names).  Note 2P version marked.

Also to note, all the files related to a particular character will have same offset throughout the game for model, texture, sound, etc) {i.e. 0B = Ivy, 0B=Mitsurugi, etc}

Soul Calibur IV Character index   
------------------------------------
001_Mitsurugi
002_Seong_Mi-Na
003_Taki
004_Maxi
005_Voldo
006_Sophitia
007_Siegfried
008_Rock
00b_Ivy
00c_Kilik
00d_Xianghua
00e_Lizardman
00f_Yoshimitsu
011_Nightmare
012_Astaroth
014_Cervantes de Leon
015_Raphael
016_Talim
017_Cassandra
01a_Yun-Seong
022_Setsuka
023_Tira
024_Zasalamel
028_Hilde
029_Algol
02a_Vader
02b_Yoda
02c_Apprentice
030_Amy
040_Angol-fear
041_Kamikirimusi
042_Shura
043_Ashlotte
044_Scheherazade
050_Arcturus
080_Zasalamel (wearing suit)
081_Picks
082_Jacqueline
083_Auguste
084_Lizardman
085_Solnhofen
086_Valmiro
087_Algol
088_Mitsurugi (grey AI training mode)
08f_Villager Male
101_Mitsurugi 2P
102_Seong Mina 2P
103_Taki 2P
104_Maxi 2P
105_Voldo 2P
106_Sophitia 2P
107_Siegfried 2P
108_Rock 2P
10b_Ivy 2P
10c_Kilik 2P
10d_Xianghua 2P
10e_Lizardman 2P
10f_Yoshimitsu 2P
111_Nightmare 2P
112_Astaroth 2P
114_Cervantes 2P
115_Raphael
116_Talim 2P
117_Cassandra 2P
11a_Yun-seong 2P
122_Setsuka 2P
123_Tira 2P
124_Zasalamel 2P
128_Hilde 2P
129_Algol 2P
12a_Vader 2P
12b_Yoda 2P
12c_Apprentice 2P
130_Amy 2P
140_Angol-fear 2P
141_Kamikirimusi 2P
142_Shura 2P
143_Ashlotte 2P
144_Scheherazade 2P
150_Arcturus 2P
180_Female Secretary (from Zasalamel's Ending cutscene)
181_Polygon A (color boxes - placeholder?)
183_Marienbard
184_Lizardman
185_Johan Dürer
186_Phantasm
188_Gargantua
18f_Villager Female
281_Polygon B (color boxes - place holder?)
285_Gargantua (bald no helmet)
286_Red Skull footsoldier
381_White Skull footsoldier
385_Dverger
485_Shark
## Post #147
- Username: mrSl1m
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 29, 2011 7:31 pm
- Post datetime: 2011-07-29T23:27:20+00:00
- Post Title: Re: Soul Calibur 4

Всем привет, вижу что здесь русскоговорящие братья, надеюсь в первую очередь на вашу помощь )))
Вообщем сейчас делаю игрушку на спрайтах очень нужны короткие короткие и зацикленные анимации, сойл калибур для этого подходит идеально, ну а еще это моя любимая игрушка...
Можно как-то выдрать оттуда анимации и реально ли это, в какой-нибудь формат bvh , bip  и так далее ? Буду признателен за помощь )))
Ну и как начинающему аниматору будет полезно поизучать движения персонажей поближе )

Hi there. Any progress to extract the animation ???
## Post #148
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-09-23T21:08:24+00:00
- Post Title: Re: Soul Calibur 4

I made a quick program for simplifying how to replace textures. It basically automates all of the hex editing as explained by itze and vicviper573. Here's the download: [http://www.tzarsectus.com/SC4/spdddsinject.exe](http://www.tzarsectus.com/SC4/spdddsinject.exe)

Step by step guide:
-Use xbdecompress to decompress an SPD file.
-Use spd_ex to extract all of the textures from that SPD.
-Use my utility for replacing any of the textures (it's commandline. first argument is name of SPD, second argument is name of DDS. make sure the DDS filename is the same as original, otherwise my program will be confused as to which DDS to replace). Remember that texture needs to be the exact same size as the original. Most textures are DXT1 (some are DXT5). Almost every texture has 3 mipmaps, but there's a few which has zero.
## Post #149
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-09-26T03:40:08+00:00
- Post Title: Re: Soul Calibur 4

Thanks Sectus, your tool makes things nice and easy.
Can anyone tell me how to identify different meshes within the spd? (way back on page 4 somebody corrupted sophitias blouse mesh for a topless mod)
## Post #150
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-09-26T05:49:20+00:00
- Post Title: Re: Soul Calibur 4

> Reply from irishwhip
>
> Thanks Sectus, your tool makes things nice and easy.
Can anyone tell me how to identify different meshes within the spd? (way back on page 4 somebody corrupted sophitias blouse mesh for a topless mod)
I have no idea how to identify meshes, but if you're trying to remove Sophitia's blouse that can be done by adding alpha channels to the blouse textures.
## Post #151
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-09-26T20:30:47+00:00
- Post Title: Re: Soul Calibur 4

i was thinking more along the lines of setsukas bra
## Post #152
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-10-01T01:45:07+00:00
- Post Title: Re: Soul Calibur 4

doing a text search for "ndxr" in hex workshop reveals some meshes that can have their visibility toggled. 00d2be00 in R_ALL_022_360.spd seems to control setsukas main body meshes, if you corrupt the value at 00d2be00 the bra disappears, but so does most of the rest of her.
## Post #153
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-10-01T11:46:09+00:00
- Post Title: Re: Soul Calibur 4

Someone has been able to remove her bra only so it's definitely possible somehow.

Someone on a Japanese forum gave some helpful tips. Change these two bytes in Cassandra's SPD 00000049 "DE B8" to "E4 D0" and she'll have damaged middle armour from the start. I wonder if you can do the same with other characters, like Hilde. Also C4780B "01" to "00" is supposed to remove her shirt, but it has no effect for me.
## Post #154
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-10-01T12:24:18+00:00
- Post Title: Re: Soul Calibur 4

c4780b removes "munehimo", the little bit of string that was visible on your xianghua mod
## Post #155
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-10-01T14:03:38+00:00
- Post Title: Re: Soul Calibur 4

Ah, okie. I thought it was for removing the entire shirt.
## Post #156
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-10-02T12:40:18+00:00
- Post Title: Re: Soul Calibur 4

this is from the japanese board:
    >remove Setsuka's bra
    >1. 00D2C7EB 14->12
    >2. exchange 00D2D450(60)<->00D2D4B0(90)

having trouble understanding the second part. swap 60 bytes with 90 bytes from those offsets? that just caused a crash
## Post #157
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-10-02T12:47:09+00:00
- Post Title: Re: Soul Calibur 4

Yeah, I'm not sure what he means either. I tried moving the second 90 bytes first, and the 60 bytes to be after that. That didn't cause a crash, but it also didn't have any effect whatsoever ingame.
## Post #158
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-10-02T13:29:45+00:00
- Post Title: Re: Soul Calibur 4

changing 00D2C7EB 14->0a removes the bra fully, but also removes the face. its a little closer than my earlier butchery though
## Post #159
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-10-02T17:53:35+00:00
- Post Title: Re: Soul Calibur 4

i fugured out what those japanese guys were saying. lookie:
[](http://img155.imagevenue.com/img.php?image=75131_DSC00584_122_170lo.JPG)

[](http://img140.imagevenue.com/img.php?image=75291_Untitled_122_486lo.jpg)
## Post #160
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-10-02T17:59:37+00:00
- Post Title: Re: Soul Calibur 4

Yeah, I just figured it out too. I think what I did first was right, but I must have fumbled around when swapping the 2 sections.

I guess the only remaining mystery now are the CAS characters.
## Post #161
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-10-02T18:02:38+00:00
- Post Title: Re: Soul Calibur 4

any possibilities with Ivy, Tira, Taki etc? Taki is practically nude anyway, might be able to tweak the specular on her jumpsuit
## Post #162
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-10-02T18:26:56+00:00
- Post Title: Re: Soul Calibur 4

Ivy is a no, for both 1P and 2P, same thing with Tira. Taki might be possible. Actually, I'm curious if they've still got her body under the suit. Once her suit is damaged, you can see parts of her body underneath. I looked at her model file, but it was a bit tricky to figure out. There's multiple models which looks the same, so I'm not sure if one of them is the body or if they're all variations of the suit. Taki 2p might be possible, but then you'd have to change the shading on her underclothing.

It's interesting to see how the models are all built. I won't be surprised if characters like Ivy were created late into development as that model has basically nothing redundant, there's no hidden geometry. Same thing with all the bonus characters and some other characters (Seoung Mina and Tira for instance).
## Post #163
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-10-02T19:36:17+00:00
- Post Title: Re: Soul Calibur 4

looking at sophitia in blender, she could probably go fully nude. but its a lot of meshes to mess around with...
## Post #164
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-10-02T19:42:46+00:00
- Post Title: Re: Soul Calibur 4

I suspect most of her outfit can be made fully transparent with alpha channels. It worked for her top at least.
## Post #165
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2011-10-02T21:09:29+00:00
- Post Title: Re: Soul Calibur 4

theres a file in cdata/texture/ called creation.tld. It has a bunch of DDS files inside but i lack the knowhow to unpack them correctly. maybe the F_NUDE_001 body textures are in there.
## Post #166
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-10-03T05:10:00+00:00
- Post Title: Re: Soul Calibur 4

xbdecompress and spd_ex is able to extract all the textures from it. Some textures aren't extracted properly, but since all the other textures are just 2D elements of the CAS creation screen I doubt this is what we're looking for.
## Post #167
- Username: midnightfc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 13, 2011 7:12 am
- Post datetime: 2011-10-12T23:24:20+00:00
- Post Title: Re: Soul Calibur 4

> Reply from Sectus
>
> Ivy is a no, for both 1P and 2P, same thing with Tira. Taki might be possible.

That may be the case with textures, but at the least, it would be nice to increase breast volume just to have big, crazy boobs bouncing around...especially for characters like Ivy & Taki.  I used to mod games like KoF MIA and DOAX1 to that effect.

> Actually, I'm curious if they've still got her body under the suit. Once her suit is damaged, you can see parts of her body underneath. I looked at her model file, but it was a bit tricky to figure out.

Taki's undamaged state just looks like naked boobs with paint on them.  Her damaged states look to be texture tricks and minor additional modeling elements to add the effect of torn clothes.  There's definitely no 'clothing layer' on her, like other characters.
## Post #168
- Username: WoobiE
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 14, 2011 12:48 pm
- Post datetime: 2011-11-23T12:22:23+00:00
- Post Title: Re: Soul Calibur 4

Hi guys,

I've been paying attention to the thread for a while now and have gotten the files needed to rig these characters. I do have some questions though. The skin files seem to have a shade over them, this is where the clothing goes. When in the game some characters lose all their gear and only have under garments on. How does the game get the characters to have none of that shade over the skin? I was wondering if there was any thing that we missed that would get us the shadowless skin meshes in 3ds max or any 3d modelling software. Because it seems as though there is a base female and male body with only under garments some where in the game.

I have a image here which I randomly found on the internet, this is what I am trying to achieve:
[http://danbooru.donmai.us/post/show/979 ... rs-boots-c](http://danbooru.donmai.us/post/show/979592/3d-amy_sorel-artist_request-bare_shoulders-boots-c)
## Post #169
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2011-12-14T07:31:21+00:00
- Post Title: Re: Soul Calibur 4

Hi!
Just gave this whole thread a good read.  Gone through like every post made here lol.  Lots of info for a noob.  Thanks everyone for them works they'd done so far.  

I have one small question though.  How are you guys testing your works?  Are you using a modded/jtag xbox?  I want to know how are you guys putting your edited textures back into the xbox iso.  And you certainly can't be buring a new DVD everytime you want to test a change you've made, that'd be crazy!!!  

I read in a previous page somewhere that they were installing the game to a USB drive.  Okay, I can do that.  They they said extract iso from that USB to your PC.  Need some help/hint this part.  And definitely need help on how to put the edited files back to that iso/USB flash drive!!!!

Please any help will be greatly appreciated.  possibly from few guys on last 2-3 page(sectus/irishwhip) or anyone else who knows this!  

Thanks.
and uh, sorry if this is reviving a dead old thread.  I am new here, really really want to try out modding SC4.
## Post #170
- Username: ayasuke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 23, 2011 2:19 pm
- Post datetime: 2011-12-23T06:23:15+00:00
- Post Title: Re: Soul Calibur 4

Mr.sectus, 
Please let me know a password. 

[http://www.tzarsectus.com/SC4/spdddsinject.exe](http://www.tzarsectus.com/SC4/spdddsinject.exe)

Xianghua.Sophitia.Cassandra.screenshot...
## Post #171
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2011-12-24T20:01:03+00:00
- Post Title: Re: Soul Calibur 4

> Reply from khanbot
>
> I have one small question though.  How are you guys testing your works?  Are you using a modded/jtag xbox?  I want to know how are you guys putting your edited textures back into the xbox iso.  And you certainly can't be buring a new DVD everytime you want to test a change you've made, that'd be crazy!!! 

I read in a previous page somewhere that they were installing the game to a USB drive.  Okay, I can do that.  They they said extract iso from that USB to your PC.  Need some help/hint this part.  And definitely need help on how to put the edited files back to that iso/USB flash drive!!!!

Please any help will be greatly appreciated.  possibly from few guys on last 2-3 page(sectus/irishwhip) or anyone else who knows this!  

Thanks.
and uh, sorry if this is reviving a dead old thread.  I am new here, really really want to try out modding SC4.
I'm using a jtag for all modding on the xbox. I don't know of any other ways to get the 360 to load modified files.

> Reply from ayasuke
>
> Mr.sectus, 
Please let me know a password. 

http://www.tzarsectus.com/SC4/spdddsinject.exe

Xianghua.Sophitia.Cassandra.screenshot...
If you're asking about the rar archives, the password is fluffles
## Post #172
- Username: ayasuke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 23, 2011 2:19 pm
- Post datetime: 2011-12-25T04:46:02+00:00
- Post Title: Re: Soul Calibur 4

Mr.sectus, 
Thank you for the Christmas present.
## Post #173
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2011-12-30T18:02:26+00:00
- Post Title: Re: Soul Calibur 4

bummer.  guess I'll try to find me some jtag.   

I got one more question.  I tried to extract from F_NUDE_001_360.spd using spd extractor and it gave two more .spd files, 000.spd and 001.spd
I ran spd extractor again on 000.spd file and I got some textures and obj and stuff, but running it on 001.spd file, the extractor crashes and I get this error in cmd 

```
File Size : 507008 bytes.
Entry Count : 18.
Joint Count : 121.
Creating FBX File...
Unhandled Exception: System.IndexOutOfRangeException: Index was outside the bounds of the array.
   at SPD_EX.FBX.convert(List`1 jnts, String fileName, List`1 mMMeshes, Int32 te
xCount)
   at SPD_EX.Program.exSPD(String fileName)
   at SPD_EX.Program.Main(String[] args)

```


Can someone help me with this one?  It is doubtful that file is corrupted, maybe something wrong with extractor but I don't have neither it's source or any coding experience so yea I am stuck.     All help is appreciated much!  
Thanks.  

edit: it seems that file has no textures whatsoever lol.  I tried opening 001 file hex workshop and searched for gidx and it found no such entry while it does finds that in 000 file.
## Post #174
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-01-10T19:31:33+00:00
- Post Title: Re: Soul Calibur 4

Yeah, I've never been able to extract those .001 files either. I dunno if there's anything in them at all or if it's just a weird bug with the spd extractor.

If I recall, regcommon.nut has a TON of general textures which is used throughout the game (like the skin textures for CAS), but spd extractor refuses to work with it. However, those files are uncompressed and not encrypted so someone could create a tool for extracting all of the DDS files which are there. I'd do it myself, but I don't know how to translate the header of the game's DDS files.
## Post #175
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2012-02-12T12:39:08+00:00
- Post Title: Re: Soul Calibur 4

is there an export script for the obj files in the bin container?
## Post #176
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-03-12T16:02:09+00:00
- Post Title: Re: Soul Calibur 4

has anyone tried modding ps3 version of this game?  

I've got a ps3 version and the files looks the same as xbox 360 version, lots of spd files.

but using spd extractor on ps3 version of .spd files just gives a bunch of more spd files, and using spd extractor again of any of those extracted .spd files gives nothing!!  

If I rename ps3 .spd files to .nmd files, noesis can open those files with no problems.  


Please if anyone can offer any help with ps3 version of this game, please do!  

thanks
## Post #177
- Username: daydreamdirty
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 05, 2011 7:23 pm
- Post datetime: 2012-04-23T20:07:17+00:00
- Post Title: Re: Soul Calibur 4

I was interested in it for awhile and it has been done before, probably most likely by someone over in Japan as if I remember correctly.
Not really interested in it anymore.  Also btw, I still think SC4 is better than 5.  Tried it a few months ago and turned it back in about a week later.  No story and only way to look up the character's bios is online.
## Post #178
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-06-08T09:29:30+00:00
- Post Title: Re: Soul Calibur 4

Hello everyone!
Can someone tell me, where are textures for base male and female nude SC IV models situated? Any help would be appreciated.
## Post #179
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-06-08T10:46:42+00:00
- Post Title: Re: Soul Calibur 4

> Reply from zaramot
>
> Hello everyone!
Can someone tell me, where are textures for base male and female nude SC IV models situated? Any help would be appreciated.
If I recall, it's in regcommon.nut
## Post #180
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-06-08T11:11:35+00:00
- Post Title: Re: Soul Calibur 4

Thank you very much Sectus! Tell me please, do you know how those textures can be extracted from there?
## Post #181
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-06-08T14:48:04+00:00
- Post Title: Re: Soul Calibur 4

My tool should work: [http://www.tzarsectus.com/SC4/spdddsinject.exe](http://www.tzarsectus.com/SC4/spdddsinject.exe)
## Post #182
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-06-08T18:07:05+00:00
- Post Title: Re: Soul Calibur 4

Thanks a lot friend! Your cool tool works perfectly, it's saved me
## Post #183
- Username: Aethr
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 26, 2017 3:19 am
- Post datetime: 2017-01-25T19:34:08+00:00
- Post Title: Re: Soul Calibur 4

Perhaps this is the wrong thread, but maybe someone could help me here. I'm trying to figure out how this was achieved. I can only assume that they extracted the individual Pyrrha create a character parts from SCV's ISO/DLC, opened it in a hex editor, changed some values around, renamed it to an existing SCIV create a character part, and repacked the SCIV ISO. Am I correct? Maybe someone who knows more than me could briefly describe the process? I would love to pack an "SCIV.5" ISO containing costume parts from SCV, and potentially the original character alternate costumes.

Which brings me to question number 2. If I understand the file structure of SCV correctly from my fiddling with save data editing, the original character costumes are stored as a single model but also as a costume part-- meaning, when you create an "edit color" for a 1p/2p in SCV, the save data for that character slot contains a hex value for a single 1P/2P model. Could we, in theory, back port the 1p/2p model and use it to replace, for example, a T-Shirt model, so that when the character equips the T-Shirt model, their entire model is swapped to a 1p/2p from SCV? I feel as though that is too simple. Obviously we could back-port 1p/2p models from SCV as long as they are offered as create a character parts (such as Pyrrha 1p, Natsu 2p, Patroklos 1p and 2p, Ivy 1p and 2p etc), but what about those that are not offered as create a character parts?

Sorry for the bump-- I hope someone could answer these questions for me. I'll likely just get both ISOs and start fooling with them and comparing files and whatnot.
## Post #184
- Username: Aethr
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 26, 2017 3:19 am
- Post datetime: 2017-09-11T21:09:16+00:00
- Post Title: Re: Soul Calibur 4

Anyone know where the moveset data is on the disc?
