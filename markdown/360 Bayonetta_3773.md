## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-09T17:09:34+00:00
- Post Title: 360 Bayonetta

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-18T16:34:17+00:00
- Post Title: 360 Bayonetta

*script removed because doesn't support the compressed files*
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-10-18T20:55:12+00:00
- Post Title: 360 Bayonetta

cpk_unpack in my utf_tab suite ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)) handles the .cpk files in the Bayonetta demo, including the compressed ones (though as of utf_tab 0.3 the decompression is ridiculously slow).

I just found my way over here finally, awesome to see aluigi's scripty thing, that'll come in handy in the future!
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-18T22:35:27+00:00
- Post Title: 360 Bayonetta

is there any way to optimize the extraction of these files it tales about 1 hour per 100mb to extract currently on a 3.2 core 2 duo.
Thanks for the extraction of the files tough
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-10-18T23:14:07+00:00
- Post Title: 360 Bayonetta

utf_tab 0.4 (which has cpk_unpack 0.3) now decompresses into memory, lots faster. Tested on Mario & Sonic Winter Games Wii, I don't have the Bayonetta stuff around anymore.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-18T23:29:22+00:00
- Post Title: 360 Bayonetta

Thank you so much it is about 1,000 x faster
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-19T01:38:45+00:00
- Post Title: 360 Bayonetta

Sorry to double post I will work on a 3d model converter for this game I already see the format clearly.
The only problem I have is how to I do endian swaps with floats in max script can someone help me with this please.

Here is a crude .dat extractor
it will extract the individual parts of the dat files without names.

```
endian big
get FILES long
goto 0x20
math j == FILES
math j -= 1
for i = 0 < FILES
MAth NAME1 += 1
get OFFSET LONG

SAVEPOS OFF
get OFFSET2 long

goto OFF
MATH SIZE == OFFSET2
print "%SIZE%"
MATH SIZE -= OFFSET
print "%SIZE%"

if i = j
goto -1
savepos SIZE
print "%SIZE%"
MATH SIZE += 1
MATH SIZE -= OFFSET
log NAME OFFSET SIZE
else
LOG NAME1 OFFSET SIZE
endif
next i

```


the BMW files appear to be the meshes
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-19T09:56:59+00:00
- Post Title: 360 Bayonetta

why not you change the following:

```
savepos SIZE
print "%SIZE%"
MATH SIZE += 1
```
with the most simple:

```
get SIZE asize
```
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-25T15:12:01+00:00
- Post Title: 360 Bayonetta

Yes those commands would be better it was late at night I was not thinking very well 
I will update the extractor script to support names when I get a chance.
Some progress
## Post #10
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-10-25T23:56:27+00:00
- Post Title: 360 Bayonetta

[http://platinumgames.com/2009/04/24/modeling-bayonetta/](http://platinumgames.com/2009/04/24/modeling-bayonetta/)

a small article from the character designer behind bayonetta
## Post #11
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-10-29T11:44:59+00:00
- Post Title: 360 Bayonetta

This one extract all resource in dat file beautifually!

```
# by Fatduck    Oct 2009
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big

idstring "DAT\0"
get NUMRES long
get OFSRESLIST long
get OFSRESTYPELIST long		#no needed
get OFSRESNAMELIST long
get OFSSIZERESLIST long

goto OFSRESNAMELIST
get STGLEN long
savepos OFSRESNAMELIST

for i = 0 < NUMRES
  goto OFSRESLIST
  get OFSRES long
  savepos OFSRESLIST
  
  goto OFSRESNAMELIST
  getdstring RESNAME STGLEN
  savepos OFSRESNAMELIST
  
  goto OFSSIZERESLIST
  get SIZERES long
  savepos OFSSIZERESLIST
  
  log RESNAME OFSRES SIZERES
next i
```


PS: the textures are in xpr which use common swizzling method across Xbox
## Post #12
- Username: fireninja
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 01, 2009 2:49 pm
- Post datetime: 2009-12-08T08:51:42+00:00
- Post Title: 360 Bayonetta

there are progress on model converter
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-01T03:03:21+00:00
- Post Title: 360 Bayonetta

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-02T00:58:39+00:00
- Post Title: 360 Bayonetta

aluigi has implemented cpk compression in bms and along with it has sped up extraction by 10,000,000% and it now supports folders.
his bms script is here
[http://aluigi.org/papers/bms/cpk.bms](http://aluigi.org/papers/bms/cpk.bms)
and the newest version of quickbms is needed also which can be found here
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #15
- Username: fireninja
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 01, 2009 2:49 pm
- Post datetime: 2010-01-02T16:11:42+00:00
- Post Title: 360 Bayonetta

if .wmb files is the meshe,and .wtb the textures,how i can import them in 3dsmax ?
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-08T22:29:23+00:00
- Post Title: Re: 360 Bayonetta

You will be able to import them soon
## Post #17
- Username: fireninja
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 01, 2009 2:49 pm
- Post datetime: 2010-01-09T09:23:50+00:00
- Post Title: Re: 360 Bayonetta

chrrox your work is just amazing
## Post #18
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2010-01-17T21:48:02+00:00
- Post Title: Re: 360 Bayonetta

Hi,

I'm also trying to find out the format of the model from this game.
I'm quite a newbie to all this reverse engineering stuff.

I can see that chrrox already achieved some nice results, can you give us some hints.
I already passed a lot of time analyzing the wmb files in a hex editor to try to find a pattern but all i can get for the moment is points garbage
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-17T21:49:44+00:00
- Post Title: Re: 360 Bayonetta

post what you have and ill correct it for you.
## Post #20
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2010-01-18T20:40:29+00:00
- Post Title: Re: 360 Bayonetta

I created a new post in the 3D/2D model section to discuss about it:

[viewtopic.php?f=16&t=4059](http://forum.xentax.com/viewtopic.php?f=16&t=4059)
## Post #21
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2010-01-21T22:58:42+00:00
- Post Title: Re: 360 Bayonetta

Do you have any idea how to decode the textures from this game.

Fatduck mentioned the xpr format and swizzling but i'm not able to find much info about that.
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-21T23:50:02+00:00
- Post Title: Re: 360 Bayonetta

you recreate an xpr header on the files then use the xbox sdk tool called unbundler.exe on them.
## Post #23
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2010-01-23T11:55:49+00:00
- Post Title: Re: 360 Bayonetta

OK, this is giving me a hard time.

I created a resource with bundler to have a xpr header.

Then I forged a xpr file using a modified header and the data from a wtb file from the game.
I ran unbundler on that and it didn't complained, it extracted 7 files:
6 tga file that looks like texture and its mipmaps and 1 tga file with a "_miptail" suffix, dunno what is that.

however the extracted tga file looks like garbage:

[](http://img704.imageshack.us/i/miplevel2.jpg/)
The above picture show what the mip level 2 texture looks like.

I don't know if I messed up the header of my forged xpr or if I need to do additional steps on the texture.
Do you have any idea ?
## Post #24
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-04-18T18:59:42+00:00
- Post Title: Re: 360 Bayonetta

Hi there!
Any progress on tools?
## Post #25
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2010-06-11T15:27:07+00:00
- Post Title: Re: 360 Bayonetta

this is awesome.  if someone can extract the tpr file or dds files or 3d model i can make some skins/costumes.
## Post #26
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-12T20:17:29+00:00
- Post Title: Re: 360 Bayonetta

here is the full toolset thanks to chroxx, aluigi,hcs, fatduck and me
[http://www.mediafire.com/?twinmymtndz](http://www.mediafire.com/?twinmymtndz)
## Post #27
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-13T02:55:22+00:00
- Post Title: Re: 360 Bayonetta

> Reply from shadowmoy
>
> here is the full toolset thanks to chroxx, aluigi,hcs, fatduck and me
http://www.mediafire.com/?twinmymtndz
Thanks, great news.  Today i will test it.

Can you make tutorial on how to convert models and twxtures?
## Post #28
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-13T07:53:03+00:00
- Post Title: Re: 360 Bayonetta

put the wmb and wtb exporter in the folder you want to extract model and textures

textures : drop wtb on the wtbexporter4.exe exe 
models : drop the wmb on the wmbtoobj.exe to convert it to obj


also :
- the obj materials are not assignated directly 
- textures need to be flipped upside down manually
- all lods seems to be also exported , i have not found any flag to remove them.
## Post #29
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-13T09:38:06+00:00
- Post Title: Re: 360 Bayonetta

Thanks so much guys for the tools, the only problem is the textures files but what ever thanks
## Post #30
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-21T01:06:39+00:00
- Post Title: Re: 360 Bayonetta

> Reply from chrrox
>
> you recreate an xpr header on the files then use the xbox sdk tool called unbundler.exe on them.

Thanks chrrox and guys, your work is amazing, but i can't find the tool, if any somebody have this tools or other to export the xpr texture to other friendly file format please share
## Post #31
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-21T11:20:14+00:00
- Post Title: Re: 360 Bayonetta

the link is some post before
## Post #32
- Username: swordzero
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 17, 2009 2:07 am
- Post datetime: 2010-06-23T22:53:00+00:00
- Post Title: Re: 360 Bayonetta

Can someone help me I don't know how to get the files, I used Xbox Backup Creator and explored my disc, there are cpks in media (data00 to data 13) in the subfolder bgm there's BGM000.cpk (oviusly music but I extracted it anyways,) and in se There's a bunch of files ev0##.cpk and r###.cpk but no matter what file I extract from the extracted files are all .aax.
Thanks in advance.
## Post #33
- Username: iCube
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 29, 2010 12:08 pm
- Post datetime: 2010-07-03T03:40:25+00:00
- Post Title: Re: 360 Bayonetta

Hi friends, 
what the other file types in .dat files?
.clp, .col, .eff, .mot, .sdx, .seq, .exp and more. how view or edit it 
and many of this file size in 0kb
## Post #34
- Username: iCube
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 29, 2010 12:08 pm
- Post datetime: 2010-07-07T03:08:09+00:00
- Post Title: Re: 360 Bayonetta

HELLO! ANY ONE CAN HELP!!
## Post #35
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-07T03:47:39+00:00
- Post Title: Re: 360 Bayonetta

> Reply from iCube
>
> HELLO! ANY ONE CAN HELP!!
If no one answers, so nobody knows.
## Post #36
- Username: iCube
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 29, 2010 12:08 pm
- Post datetime: 2010-07-07T11:34:29+00:00
- Post Title: Re: 360 Bayonetta

> Reply from Tosyk
>
> iCube wrote:HELLO! ANY ONE CAN HELP!!
If no one answers, so nobody knows.
thanks for answer
## Post #37
- Username: fewks
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 28, 2010 6:05 pm
- Post datetime: 2010-07-24T10:40:14+00:00
- Post Title: Re: 360 Bayonetta

Anyone know which of cpk archives contains bayonetta's and other character models?
## Post #38
- Username: fewks
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 28, 2010 6:05 pm
- Post datetime: 2010-07-25T18:35:05+00:00
- Post Title: Re: 360 Bayonetta

ah, nevermind found it already
## Post #39
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2010-10-24T02:24:59+00:00
- Post Title: Re: 360 Bayonetta

How can I import wmb model file to 3dsmax?

EDIT : I got it
## Post #40
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2019-04-03T00:43:43+00:00
- Post Title: Re: 360 Bayonetta

> Reply from shadowmoy ↑Sun Jun 13, 2010 4:17 am at Sun Jun 13, 2010 4:17 am
>
> 
here is the full toolset thanks to chroxx, aluigi,hcs, fatduck and me
http://www.mediafire.com/?twinmymtndz

Does anyone still have these tools? I can't find an alt download anywhere.
## Post #41
- Username: loridaz
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 17, 2010 6:51 am
- Post datetime: 2019-04-11T16:10:16+00:00
- Post Title: Re: 360 Bayonetta

> Reply from Doctor Loboto ↑Wed Apr 03, 2019 8:43 am at Wed Apr 03, 2019 8:43 am
>
> 
shadowmoy wrote: ↑Sun Jun 13, 2010 4:17 am
here is the full toolset thanks to chroxx, aluigi,hcs, fatduck and me
http://www.mediafire.com/?twinmymtndz


Does anyone still have these tools? I can't find an alt download anywhere.

I had to search quite a lot to check if I still had things related to Bayonetta. I guess this is it : [https://ufile.io/g1aps](https://ufile.io/g1aps)
(note: this file will expire in 30 days, if you know a better file hosting, let me know)
## Post #42
- Username: RonaldGriggs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 06, 2019 10:40 am
- Post datetime: 2019-05-06T02:56:44+00:00
- Post Title: Re: 360 Bayonetta

chrrox your work is just amazing
## Post #43
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2019-09-11T13:35:24+00:00
- Post Title: Re: 360 Bayonetta

Yeah the file expired before I could download it. Had some technical problems recently that took priority, sorry. Could you put it somewhere like mediafire or something?
## Post #44
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-11-18T08:09:03+00:00
- Post Title: Re: 360 Bayonetta

> Reply from loridaz ↑Fri Apr 12, 2019 12:10 am at Fri Apr 12, 2019 12:10 am
>
> 
Doctor Loboto wrote: ↑Wed Apr 03, 2019 8:43 am
shadowmoy wrote: ↑Sun Jun 13, 2010 4:17 am
here is the full toolset thanks to chroxx, aluigi,hcs, fatduck and me
http://www.mediafire.com/?twinmymtndz


Does anyone still have these tools? I can't find an alt download anywhere.


I had to search quite a lot to check if I still had things related to Bayonetta. I guess this is it : https://ufile.io/g1aps
(note: this file will expire in 30 days, if you know a better file hosting, let me know)

Do you still have these tools?
