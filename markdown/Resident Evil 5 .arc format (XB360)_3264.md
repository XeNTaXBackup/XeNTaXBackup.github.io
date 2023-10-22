## Post #1
- Username: Octave
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 22, 2008 3:13 am
- Post datetime: 2008-12-21T20:11:33+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-12-22T04:45:55+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

The Capcome arc files are almost always the same. I have researched them in the past for dead rising. I quick check shows the formats are the same, although I'm not sure if these ones use zlib.

```

Header:
0 - Magic - Chars(4) //"ARC "
4 - Version - Int16
8 - FileCount - Int16

Files:
0 - FileName - Chars(64)
64 - Unknown - Int32 //Not important, some sort of flag
68 - CompressedSize - Int32
72 - DecompressedSize - Int32
76 - Offset - Int32
```
## Post #3
- Username: Octave
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 22, 2008 3:13 am
- Post datetime: 2008-12-22T12:48:10+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

Using zlib is beyond my limited coding capabilites. how would I go about unpacking them?
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-12-23T10:30:16+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

i don't think the files are zlibeed
## Post #5
- Username: ichigoogle
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2008 12:09 pm
- Post datetime: 2009-03-15T07:29:03+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

maybe RPGviewer will work if you select DMC4

[http://www.sufi.cc/aionemu/RPGViewer_3. ... d1024_.zip](http://www.sufi.cc/aionemu/RPGViewer_3.0__Build1024_.zip)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-08T21:01:30+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2010-01-08T23:01:15+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

There is already a Resident Evil 5 ARC extractor avaliable right here on the forums, also if you want to OPEN and extrac for example ONLY textures (which are augo converted to DSS files) then id recommend using the resident evil 4 arc tool, as its been updated to support RE5 aswell.

If you check out the RE5 topic on this forum then it lists a website somewhere with a link to the program your looking for.
## Post #8
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2010-01-08T23:42:11+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

Has anyone been able to extract the files from Dead Rising, Lost Planet or Devil May Cry 4 on 360? Did those use the same compression too?

> Reply from lionheartuk
>
> There is already a Resident Evil 5 ARC extractor avaliable right here on the forums, also if you want to OPEN and extrac for example ONLY textures (which are augo converted to DSS files) then id recommend using the resident evil 4 arc tool, as its been updated to support RE5 aswell.

If you check out the RE5 topic on this forum then it lists a website somewhere with a link to the program your looking for.
This is about the 360 version, not the PC version. As far as I know, no one has figured out how to decompress the ARCs on 360.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-09T00:22:30+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

i am talking about the 360 files not the pc files.
## Post #10
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2010-01-13T02:58:50+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

> Reply from chrrox
>
> i am talking about the 360 files not the pc files.
yes, However we are still working on that.  We plan to find a way to extract the Xbox 360 arc files to gain access to the new DLC coming to the Consoles.
## Post #11
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2010-01-17T07:37:35+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

If it would help, here's an arc file from PC and 360. I assume they contain the same data:
[http://www.tzarsectus.com/RE5/temp/fig01.arc](http://www.tzarsectus.com/RE5/temp/fig01.arc) (360 version)
[http://www.tzarsectus.com/RE5/temp/fig01.arc.pc](http://www.tzarsectus.com/RE5/temp/fig01.arc.pc) (pc version)
## Post #12
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2010-01-19T00:53:48+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

Xbox 360 files using lzx, I'm grabing then from my hdd right now, will make an app for it later.
## Post #13
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2010-01-19T08:10:56+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

Good to hear! Looking forward to see that utility.
## Post #14
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2010-01-29T03:54:12+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

> Reply from grimdoomer
>
> Xbox 360 files using lzx, I'm grabing then from my hdd right now, will make an app for it later.
A little bump here...

I'm just curious, how did the extraction go? Were you able to extract the archive files, and make an app for it?
## Post #15
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2010-02-08T02:00:18+00:00
- Post Title: Resident Evil 5 .arc format (XB360)

> Reply from Sectus
>
> grimdoomer wrote:Xbox 360 files using lzx, I'm grabing then from my hdd right now, will make an app for it later.
A little bump here...

I'm just curious, how did the extraction go? Were you able to extract the archive files, and make an app for it?
Completly forgot about this. I need to come up with a way to decompress lzx files. If anyone has suggestions for a library that does this please let me know.
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-08T08:52:32+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

xcompress.lib :)

anyway in my tests the XMemDecompression function wasn't able to decompress the RE5 x360 arc files correctly, I guess because it uses different window values (those 2 parameters accepted by the function) but really I don't know.
the script I created works with all the ARC files except re5:
[http://aluigi.org/papers/bms/dmc4.bms](http://aluigi.org/papers/bms/dmc4.bms)
## Post #17
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2010-02-11T04:18:30+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

Got a semi working extractor going thanks to Anthony. But most of the extracted files don't make sense. I can see plain text strings so they decompressed correctly, but like, I have yet to see an actually asset of any kind. Somtimes I get like small <1kb files, sometimes I get these text files that look like scripts, but are scrambled up to hell. I'll look into it tomorrow, and get permission from Anthony to release my extracter as it uses his code for decompression.
## Post #18
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2010-02-11T19:07:55+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

That's good news!

I'm guessing many of the files are the same on PC and 360, I could send you a few files for comparison to see if the extracted files are correct.

Scrambled script files? Do they have XFS in the header by any chance? The game has many files like that which are script-like but it's in a binary format.
## Post #19
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2010-02-11T19:45:59+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

Yea please upload a few. I shall do the same. I've also noticed that there are some "blank" entrys. Were the compressed size is a valid number, and decompressed size is 0. Not sure whats up with that... I'll have to play around with it some more later.
## Post #20
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2010-02-11T20:42:52+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

I've uploaded a few here: [http://www.tzarsectus.com/RE5/RE5-arcs/](http://www.tzarsectus.com/RE5/RE5-arcs/)

Let me know if you want any specific ones.
## Post #21
- Username: Ventrue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 9:28 pm
- Post datetime: 2010-02-23T13:46:32+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

Hey all! Nice to see, that someone is putting some effort on a possible utility for modding RE5 on XBOX360.  So grimdoomer, have you managed to unpack anything?
## Post #22
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2010-06-28T23:51:34+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

how is this going, some brilliant mind already done something?
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-28T23:53:02+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

the ps3 files are easy to extract but the files are reverse endian so they are useless to a pc.
## Post #24
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2010-06-29T00:11:42+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

i got a friend working on a tool to reverse it, but hes on exams so till july he cant finish it. How that resident evil modding community doesnt count with a uberprogrammer for us:( i am gonna cry.
## Post #25
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-29T01:00:45+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

The reason I have not bothered with a mesh converter is the animation format is unkown so the characters would just be the mesh and that is no fun without new moves.
## Post #26
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2010-06-29T05:35:51+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

you could try chris heavymetal and sheva fairtale:P that could be a good begining...mesh + textures, would be good and enough for the moment:), i know they got only one new melee movement, so i dnt care really about its only one new animations.... it will only matter about the new models animations, barry, rebecca, and excella... but someone really should try to make a tool to extract LMT animation files, this could make grow up the modding at least swapping singular animations.
## Post #27
- Username: MrNightmare
- Rank: Banned
- Number of posts: 10
- Joined date: Thu Feb 25, 2010 1:36 am
- Post datetime: 2010-06-30T06:35:51+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

> Reply from rubening
>
> you could try chris heavymetal and sheva fairtale:P that could be a good begining...mesh + textures, would be good and enough for the moment:), i know they got only one new melee movement, so i dnt care really about its only one new animations.... it will only matter about the new models animations, barry, rebecca, and excella... but someone really should try to make a tool to extract LMT animation files, this could make grow up the modding at least swapping singular animations.
Pointless, we lack the files.
## Post #28
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2010-07-07T11:12:46+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

which files?
## Post #29
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2010-08-19T23:45:06+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

chroxx if u're looking this, u should go back to remodding forum u will see teh good progresses coming with the new trainer model swap by WILSONSO, he gonna make the versus mode, i'm sure! we're very close to play it for pc!!!
## Post #30
- Username: homerliew
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 18, 2010 8:17 pm
- Post datetime: 2010-09-18T12:20:28+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

I need this "s105.arc" because everytime I try to install it has error about this file... anyway to make it fixed?
## Post #31
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2010-09-18T12:52:56+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

download gthe game because the next file is damaged too...
## Post #32
- Username: homerliew
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 18, 2010 8:17 pm
- Post datetime: 2010-09-18T15:54:10+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

how do you know that sir?? please just try to post the "s105.arc" file, that's in your data.cab
## Post #33
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-01-16T01:57:56+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

Any news?
## Post #34
- Username: raghavsharma
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 02, 2012 6:58 pm
- Post datetime: 2012-06-02T13:12:26+00:00
- Post Title: Re: Resident Evil 5 .arc format (XB360)

i want msgresource_e.arc plz give me send to [rahulanand16nov@yahoo.com](mailto:rahulanand16nov@yahoo.com)
