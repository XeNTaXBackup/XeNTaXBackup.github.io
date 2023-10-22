## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-05T01:06:14+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

Okay i have here a decrypted file from the game uncharted from ps3, problem is it seems to use zlib compression, hopefully it won't be too difficult to write up an extraction script 

[http://www.megaupload.com/?d=7GG7ZKI3](http://www.megaupload.com/?d=7GG7ZKI3)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-05T03:50:18+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

if you use offzip on it it appears they used zlib chunks the start offset if the offset directly after the word zlib.
then it reads zlib chunks till the end of the file.
i am not sure how to read the starting header of the file before the zlib section.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-05T10:50:51+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

okay i extracted 64kb segments, is that normal?

EDITl nvm found out the 1 file mode
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-11T01:00:00+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

I researched this more with a friend and an extractor should be on its way soon
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-11T01:00:51+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

Hey nice, looking forward to it
## Post #6
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-11T17:25:00+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-11T18:02:26+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

your extractor just crashes on me.
this might help.
[PSARC.rar](https://xentaxbackup.github.io/file/3429_PSARC.rar)
## Post #8
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-11T18:25:21+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

Which .psarc file did you try it on?
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-11T18:33:06+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

a lot of different ones they just crash.
## Post #10
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-09-11T18:41:32+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

Unpacker Error:
## Post #11
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-11T18:53:01+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from chrrox
>
> a lot of different ones they just crash.
Hmmm... and all from Uncharted? I only have access to actor20.psarc, and the chunk posted by OrangeC. So if the file isn't using zlib or the zlib block sizes are greater than 64k, then it won't work. 


> Reply from Researchman
>
> Unpacker Error:
Is that the file OrangeC posted? If so, that's only a chunk of the actual music.psarc file.
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-11T20:47:58+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

so is there a fix for this?
## Post #13
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-11T21:24:33+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from OrangeC
>
> so is there a fix for this?
Have you tried it? It should work on any zlib  compressed psarc files from UDF. For files that aren't zlib, if someone could post a small chunk of the file, I'll try to update the extractor for that type of compression.
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-11T21:27:42+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

i tried it on files that were zlibbed at the beginning but the data was uncompressed in the middle to the end. it still crashed

i will up a sample in a bit.

what do you mean from UDF?
## Post #15
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-09-11T21:51:24+00:00
- Post Title: Uncharted Drakes fortune PS3 .PSARC zlib

The tool works great but only on the Uncharted psarc.
## Post #16
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-11T22:24:00+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from OrangeC
>
> i tried it on files that were zlibbed at the beginning but the data was uncompressed in the middle to the end. it still crashed

i will up a sample in a bit.

what do you mean from UDF?
A sample would be great, thanks.   

From UDF, I meant from Uncharted Drake's Fortune. I was being lazy, and went with the acronym.


> Reply from Barnaby
>
> The tool works great but only on the Uncharted psarc.
It's good to know it works for someone else other than myself. I'll try to update the extractor to the general psarc format given by chrrox.
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-11T22:26:27+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

I would be greatful  thx again
## Post #18
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-12T21:49:40+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #19
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-12T22:42:15+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Sorry but it just crashed while extracting this file. heres a chunk. It stopped right after extracting the movies.

[http://www.megaupload.com/?d=E3VE41BJ](http://www.megaupload.com/?d=E3VE41BJ)
## Post #20
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2010-09-12T22:49:19+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-12T23:30:38+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Gives me an out of range error for me
## Post #22
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-12T23:47:25+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #23
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-13T00:08:08+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Sorry i couldn't get it any bigger, but it should still be readable.

file 1200 seems the error occurs
## Post #24
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-13T00:59:59+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #25
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-13T01:21:40+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Okay well it extract 1200 nicely but it crashed again at this one ;(
## Post #26
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-13T01:26:43+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

OMG, why i'm not see this thread!?  

upd:
ok, i extracted all .pak from actor20.psarc but how extract all this paks?
## Post #27
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-13T02:23:00+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-13T02:44:54+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

on file 1219 i got a OutOfMemoryException. does the program have  amemory limit or something?

man im sure we had it this time
## Post #29
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-13T03:19:54+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #30
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-13T03:54:41+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

FINALLY!! thanks to you it worked
## Post #31
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-09-13T06:43:45+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Works great
## Post #32
- Username: kosmitek
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 21, 2009 6:07 pm
- Post datetime: 2010-09-13T22:17:23+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

sample subtitles file 

```
http://www.megaupload.com/?d=AW9R9MBR
```
## Post #33
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-09-13T22:32:10+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #34
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-09-15T17:44:14+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #35
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-16T01:52:46+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Successfully extracted 6.5 gb Killzone 2 .PSARC file.  

Regards, Insomniac
## Post #36
- Username: bigboot
- Rank: Banned
- Number of posts: 8
- Joined date: Thu Sep 16, 2010 10:10 pm
- Post datetime: 2010-09-17T10:08:48+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

hi all
I am interested in opening PsARC files (MAG game) with psarc.exe , the problem is that I'm very noob and the English is not my language ... 
If they were so kind to explain how to run psarc.exe would be very grateful.

Thanks!
## Post #37
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-17T10:41:40+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

just drag the arc file onto the exe.
## Post #38
- Username: bigboot
- Rank: Banned
- Number of posts: 8
- Joined date: Thu Sep 16, 2010 10:10 pm
- Post datetime: 2010-09-17T18:42:29+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from chrrox
>
> just drag the arc file onto the exe.
thanks!
## Post #39
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2010-09-19T12:01:06+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

works fine with MX vs ATV Untamed  ,but doesnt work with MotorStorm Pacific Rift
## Post #40
- Username: sesiom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 24, 2010 4:33 am
- Post datetime: 2010-09-23T21:02:58+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Hi all.

I have extracted sucefully psarc files from GoW collection, but i will like to know if there are any way to repack the psarc file with the extracted files or delete files inside the psarc package.

Sorry for my very bad english (im not native) and thnx for this great app
## Post #41
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2010-09-26T05:15:33+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

what about psarc packer? can you make it please?
## Post #42
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-09-26T22:23:52+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from Tosyk
>
> Successfully extracted 6.5 gb Killzone 2 .PSARC file.  

Regards, Insomniac

which version did you use?, the latest one with added functionality crashes with OrangeC's described error.
## Post #43
- Username: luker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 27, 2010 2:25 pm
- Post datetime: 2010-09-27T06:27:52+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Not working with MotorStorm 2 with  file ms2.psarc (4.6gb)
## Post #44
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2010-09-30T08:59:48+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Hi

i extract uncharted .psarc, and now i want to extract the .pak file, but how. i find different tool but no chance.

so anybody there to help us

how can we extract uncharted .pak files? 

we need help, please

regards
## Post #45
- Username: traumakom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 04, 2010 11:49 pm
- Post datetime: 2010-10-04T17:15:10+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from luker
>
> Not working with MotorStorm 2 with  file ms2.psarc (4.6gb)

same error!!! please help!!!
## Post #46
- Username: lindax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 06, 2010 4:05 pm
- Post datetime: 2010-10-06T08:14:41+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Howdy!

I'm writing a Linux tool to inspect / extract PSARC files, but I'm running into some of the same problems I see mentioned here; Seemingly corrupt chunks. (No zlib header 0x78da)

Can anyone shed some light on how these are handled in the Windows program? Is there a chance the source code will be released? 

I have a sneaking suspicion that there are corrupt game files flying around. :-/

If anyone has an original disc of Uncharted 2 or MotorStorm: Pacific Rift lying around I'd appreciate it immensely if they could make a fresh backup (using whichever backup manager) and post the MD5 sums of all (or some) of the PSARC files so that I can compare them to mine.
## Post #47
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-07T13:13:00+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Friends I am having problems with god of war collection, I'm trying the god of war 1 it creates three folders, the folder it creates _movie with _ is it so? the crash happens when it tries to access a movie? anyone had any news?
## Post #48
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-09T07:29:26+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib


## Post #49
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-09T07:42:22+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from Researchman
>
> What do you want?
## Post #50
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-09T08:17:44+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Need .Net Framework v4.0.30319.
## Post #51
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-09T08:23:05+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from Researchman
>
> Need .Net Framework v4.0.30319.
You want to someone find it for you?
## Post #52
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-09T08:30:00+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

I searched but found none. If someone has, then give a link to download.
## Post #53
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-09T09:50:17+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from Researchman
>
> I searched but found none. If someone has, then give a link to download.

Google 1.hit!!!
[http://www.microsoft.com/downloads/en/d ... laylang=en](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=9cfb2d51-5ff4-4491-b0e5-b386f32c0992&displaylang=en)
## Post #54
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-10T06:24:20+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

OK.

Works with Warhawk .psarc file.
## Post #55
- Username: phate89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 13, 2010 8:56 am
- Post datetime: 2010-10-13T01:04:29+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

@ INSOMNIAC You stop working on it or youìre still improving it for not working games?
## Post #56
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-13T01:24:36+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

the ps3 3.41 sdk contains the ps arc extractor tool.
## Post #57
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-20T17:29:30+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

I'm having trouble with the files. PSARC
 I decompressed the files and compact only when I is compact with a different structure: example ...
 original file RES.PSARC
Inside it the files are so "/WAD/PS3..."
in compact files that I RES.PSARC
dento is so "WAD/PS3..."
I believe this "/" it interfere ... use file for the game ....
 Can anyone help me?
## Post #58
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-24T18:56:51+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

If anyone have problem with extracting .psarc files you can use [this tool](http://www.mediafire.com/?o3wy35uublreh).
## Post #59
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-25T02:53:12+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

I'm using is the problem in creating after the extraction.
## Post #60
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-25T03:51:54+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from timartinelli
>
> I'm using is the problem in creating after the extraction.
Features of tool from my previous post.

```
         psarc verb [options] [file...]
         psarc --xml=XMLFILE

verbs:
  create     Create an archive. (default)
  extract    Extract contents of an existing archive.
  list       List contents of an existing archive.
  dump       Print detailed info about archive for unit testing.
  verify     Verify an existing archive's structural integrity and
             ensure that all files can be decompressed.
  dtd        Display a DTD describing psarc's XML input syntax.

general options:
  -h, --help             Show this help message and exit.
      --version          Display version and exit.
  -d, --debug            Debug: Show debug messages.
  -v, --verbose          Verbose: Show additional progress. (default)
  -q, --quiet            Quiet: Don't show any progress.
  -y, --overwrite        Overwrite existing files when creating/extracting.
  --xml=XMLFILE          XML list of actions to perform.

create options:
  -oFILE, --output=FILE  Archive filename to create.
  -IINPUTFILE, --inputfile=INPUTFILE
                         Inputfile listing files to archive. Consider
                         --xml instead, which gives you more control.
  -m, --mself            Create a PSARC-MSELF hybrid file for PS3, which can contain
                          encrypted special files like SDATA, SPRX, and SPU SELF.

  --zlib                 Use zlib when compressing. (default)
  --lzma                 Use LZMA when compressing. (usually for PS3 PSN)
  --level=N              Compression quality. 1 is fastest, 9 is best. (default= 9)
  -N, --nocompress       Store all files uncompressed in the archive.
  -bBS, --blocksize=BS   Use blocks of size BS. (default = 64KiB)
  -jJOBS, --jobs=JOBS    Compression threads to run at a time. (default = number of CPUs)

  -sREGEX, --strip=REGEX Perl-compatible regex specifying a prefix to strip
                         from the pathnames stored in the archive. This may be
                         specified more than once. (default = current dir)
  -S, --strip-all        Strip all paths from files stored in the archive.
  -a, --absolute         Make the paths within the archive absolute.
  -R, --relative         Make the paths within the archive relative. (default)
  -i, --ignorecase       Make the archive directory case-insensitive.
  --exclude=WILDCARD     Wildcard specifying files to exclude.
  --skip-missing-files   If set then ignore it when a file cannot be found.
  --mergedups            Compare the content of all files, and merge identical
                         files so that only one copy of the data is included.

extract options:
  --input=FILE           Archive to extract files from. (default is first file argument)
  --to=DIRECTORY         Directory to write extracted files to. (default is current directory)
```
## Post #61
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-25T13:27:10+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

tested with the file that you spent more not sure of what I do is the following ...

gow1.psarc has the file, I want to make him use the extract command psarc gow1.psarc extract, it creates 3 folders. qe my only problem is that redo gow1.psarc with these three folders, I create more until the game does not work.

understand?
## Post #62
- Username: JohnMatrix
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 28, 2010 9:10 pm
- Post datetime: 2010-12-24T22:46:28+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from Tosyk
>
> timartinelli wrote:I'm using is the problem in creating after the extraction.
Features of tool from my previous post.
Code: Select allusage:
         psarc verb [options] [file...]
         psarc --xml=XMLFILE

verbs:
  create     Create an archive. (default)
  extract    Extract contents of an existing archive.
  list       List contents of an existing archive.
  dump       Print detailed info about archive for unit testing.
  verify     Verify an existing archive's structural integrity and
             ensure that all files can be decompressed.
  dtd        Display a DTD describing psarc's XML input syntax.

general options:
  -h, --help             Show this help message and exit.
      --version          Display version and exit.
  -d, --debug            Debug: Show debug messages.
  -v, --verbose          Verbose: Show additional progress. (default)
  -q, --quiet            Quiet: Don't show any progress.
  -y, --overwrite        Overwrite existing files when creating/extracting.
  --xml=XMLFILE          XML list of actions to perform.

create options:
  -oFILE, --output=FILE  Archive filename to create.
  -IINPUTFILE, --inputfile=INPUTFILE
                         Inputfile listing files to archive. Consider
                         --xml instead, which gives you more control.
  -m, --mself            Create a PSARC-MSELF hybrid file for PS3, which can contain
                          encrypted special files like SDATA, SPRX, and SPU SELF.

  --zlib                 Use zlib when compressing. (default)
  --lzma                 Use LZMA when compressing. (usually for PS3 PSN)
  --level=N              Compression quality. 1 is fastest, 9 is best. (default= 9)
  -N, --nocompress       Store all files uncompressed in the archive.
  -bBS, --blocksize=BS   Use blocks of size BS. (default = 64KiB)
  -jJOBS, --jobs=JOBS    Compression threads to run at a time. (default = number of CPUs)

  -sREGEX, --strip=REGEX Perl-compatible regex specifying a prefix to strip
                         from the pathnames stored in the archive. This may be
                         specified more than once. (default = current dir)
  -S, --strip-all        Strip all paths from files stored in the archive.
  -a, --absolute         Make the paths within the archive absolute.
  -R, --relative         Make the paths within the archive relative. (default)
  -i, --ignorecase       Make the archive directory case-insensitive.
  --exclude=WILDCARD     Wildcard specifying files to exclude.
  --skip-missing-files   If set then ignore it when a file cannot be found.
  --mergedups            Compare the content of all files, and merge identical
                         files so that only one copy of the data is included.

extract options:
  --input=FILE           Archive to extract files from. (default is first file argument)
  --to=DIRECTORY         Directory to write extracted files to. (default is current directory)

Works great with MotorStorm Pacific Rift!
Many thanks!!
## Post #63
- Username: ap127
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Sep 28, 2010 7:02 am
- Post datetime: 2011-01-20T12:03:46+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Hi

for this topic there are over 5000 views, they were interested in this, 

i decrypt all the psarc file, there are lot of audio, all language, speech and music 

but all texture and other graphic are decrypt as .pak 

is there a chance to decrypt these file format
## Post #64
- Username: vusigaga
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 29, 2011 3:04 pm
- Post datetime: 2011-02-01T10:39:59+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

How do you connect a ps3 to laptop to share an internet connection via wireless or usb? I use my samsung instinct cell phone as a modem to connect my laptop to the internet but I don't know how to use this feature to connect my ps3 to the internet. Is there a way to connect a laptop running vista to a ps3 to use the laptops internet connection to connect online with the ps3?
____________________________
[yahoo keyword tool](http://www.keywordspy.com/overview/keyword.aspx?q=yahoo%20keyword%20tool) ~ [overture](http://www.keywordspy.com/overview/keyword.aspx?q=overture) ~ [traffic estimator](http://www.keywordspy.com/overview/keyword.aspx?q=traffic%20estimator) ~ [adwords traffic estimator](http://www.keywordspy.com/overview/keyword.aspx?q=adwords%20traffic%20estimator)
## Post #65
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2011-02-10T03:35:28+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Hey is it possible to repack these PSARC?

I'm trying to do a little file swapping from White Knight Chronicles to WKC2 to translate, but it part of a mandatory install, so you see why I need to actually Repack it.

EDIT:

> Reply from Tosyk
>
> If anyone have problem with extracting .psarc files you can use this tool.

Just noticed this tried this out and it also packs, awesome!

EDIT 2: 

Actually, not sure when it screws up, but if I just unpack and repack the game fails to load properly. (Skips all the beginning logos then crashes at title screen.)

Seeing as all I did there was unpack and repack I'm pretty sure one of the two stages something is corrupting?
## Post #66
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-13T00:32:44+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #67
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-14T08:32:26+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Anyone?
## Post #68
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2011-02-16T10:08:24+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
## Post #69
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-03-13T02:27:29+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

The contents of this post was deleted because of possible forum rules violation.
[dump.rar](https://xentaxbackup.github.io/file/4058_dump.rar)
## Post #70
- Username: KIWIDOGGIE
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Jul 28, 2009 1:33 am
- Post datetime: 2011-07-07T11:49:32+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

[http://pastebin.com/Tavb9g0V](http://pastebin.com/Tavb9g0V)

Those are the filenames, will work on extracting it. For some reason the stream does not want to decompress in my app nor in PSARC, but if you use offzip manually on the blocks it works fine.

EDIT: I am getting a ton of Out of Array exceptions for some weird reason. Either the PSARC archive is corrupt or they really have some odd way in reading it out for that PSARC file. Between a bad manifest and bad extraction. I don't really know what is going on.
## Post #71
- Username: Ranker
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 05, 2011 5:03 am
- Post datetime: 2011-07-13T03:41:11+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

This PSARC extractor works fine but the problem is that most of us bump into more encrypted files after the extraction (like .pak files).

The music on the uncharted CD is accessible, but all the cool models are completely unusable.  Shame, because this game is so beautiful!

I would kill if someone found a way to extract the .PAK files.
## Post #72
- Username: lokesea
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 15, 2011 1:58 am
- Post datetime: 2011-07-14T18:03:00+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Is this working with "par" files?

We need to extraxt subtitles from yakuza 4, but files are "par" format.

Thanks a lot.
## Post #73
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2011-11-05T19:19:33+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Hey guys, 
Published anyone a sourcecode unpack/pack . psarc files ? Thanks
## Post #74
- Username: dundun
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 10, 2011 4:48 am
- Post datetime: 2012-01-29T02:48:51+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Hello. I am trying to repack the p0101h.psarc for white knight chronicles but the path begins with /data . How is it possible to add the "/" character when repacking on win7 OS?
## Post #75
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-08T09:20:58+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

> Reply from dundun
>
> Hello. I am trying to repack the p0101h.psarc for white knight chronicles but the path begins with /data . How is it possible to add the "/" character when repacking on win7 OS?

-a, --absolute         Make the paths within the archive absolute.
## Post #76
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2014-05-24T16:40:57+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

hi  

I try to recompile with the command: 

```
 psarc.exe create-y-a - skip-missing-files - output = repacked.psarc - inputfile = FFX-2.txt 
```
 

But nothing happens. I am trying to ask me if I have the right soft. 

```
zlib.net.dll: 68 KB
```


is that correct? 

Even the -h does not work. 

Thank you in advance.

sorry for my english :/ (google trad >_<)


Version Française : 

salut 

J'ai essayer de recompiler avec la command :

```
psarc.exe create -y -a --skip-missing-files --output=repacked.psarc --inputfile=FFX-2.txt
```


Mais il ne se passe rien. je suis entrain de me demander si j'ai le bon soft.

```
zlib.net.dll : 68 Ko
```


est-ce correct ?

Même le -h ne fonctionne pas.

Merci d'avance.
## Post #77
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-06-16T17:17:00+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Does this work with old games? I tried it on a 2008 demo. NBA 09 the inside. So many errors
## Post #78
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2017-09-13T13:19:21+00:00
- Post Title: Re: Uncharted Drakes fortune PS3 .PSARC zlib

Who made the psarc.exe extractor?
