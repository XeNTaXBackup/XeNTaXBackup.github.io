## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2008-06-21T12:36:52+00:00
- Post Title: Lego indiana Jones Trilogy

Someone know how unpack the data? is not any deflate compression i know, looks a lzss or lzw (maybe huffman) i dont' know   

[Here a demo (464mb's)](http://download.microsoft.com/download/a/6/3/a6382b62-75a6-479c-9651-976030cfb87c/LEGOIndyDemoSetup.exe)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2008-09-06T18:55:24+00:00
- Post Title: Lego indiana Jones Trilogy

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-10-19T03:30:35+00:00
- Post Title: Lego indiana Jones Trilogy

@bugtest 
i saw the new version of quickbms can handle LZ2K 

> enabled the usage of lz2k
The attachment have LZ2K

> àµÒGàµÒGMETA                                        LZ2K @  ÿ  ,t½ŽÍ&ÿßá
It's the same lz2k?
Thanks!
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-19T10:01:01+00:00
- Post Title: Lego indiana Jones Trilogy

yes it's the same lz2k algorithm, I already checked almost all the games developed by Traveller's Tales:

```
idstring LZ2K
get SIZE long
get ZSIZE long
clog "dump.dat" 12 ZSIZE SIZE
```
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-10-19T15:11:22+00:00
- Post Title: Lego indiana Jones Trilogy

I did like your post but i get:

> quickbms.exe -f 1.bms  RAIDERS.DAT .
>
> QuickBMS generic files extractor 0.3.4a
>
> by Luigi Auriemma
>
> e-mail: aluigi@autistici.org
>
> web:    aluigi.org
>
> 
>
> - open input file RAIDERS.DAT
>
> - open script 1.bms
>
> - set output folder .
>
> 
>
>   offset   filesize   filename
>
> ------------------------------
>
> - 0 files found in 0 seconds
I'm sure i missing something..
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-19T15:39:50+00:00
- Post Title: Lego indiana Jones Trilogy

the script I posted was referred to the LZ2K chunk not to the whole file you posted.
so the LZ2K chunk in a file and launch the script on it.

a chunk is NOT the entire archive for which at the moment doesn't exist a script (I could make one in future since it's a format used in various games)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T13:10:50+00:00
- Post Title: Lego indiana Jones Trilogy

it has been a hard work but I did it :)
[http://aluigi.org/papers/bms/ttgames.bms](http://aluigi.org/papers/bms/ttgames.bms)

the script covers all the games developed by Traveller's Tales included LEGO Batman, LEGO Star Wars (like Complete Saga) and Transformers
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-10-20T15:04:36+00:00
- Post Title: Lego indiana Jones Trilogy

Amazing!!! Thanks...but...i tried the bms with the Demo on Indiana Jones and don't works properly 

> - SCRIPT's MESSAGE:                                                        17:03
>
>   Alert: the crc of the file "audio\_soundfx\1_ra2_td\water_fall_wheel_lp.wav" h
>
> as not been found, it can't be extracted!
>
> 
>
> - SCRIPT's MESSAGE:
>
>   Alert: the crc of the file "audio\_soundfx\1_ra2_td\water_jet_shoot_03.wav" ha
>
> s not been found, it can't be extracted!
>
> 
>
> - SCRIPT's MESSAGE:
>
>   Alert: the crc of the file "audio\_soundfx\1_ra2_td\water_jet_shoot_04.wav" ha
>
> s not been found, it can't be extracted!
I get this errors (a lot of) unpacking the file GAME.DAT

And the file RAIDERS.DAT it's 165.188.872bytes but unpacked it's 100.762.812bytes..it's correct?
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T15:12:58+00:00
- Post Title: Lego indiana Jones Trilogy

unfortunately there are some names for which the crc is not found in the list and in that case I can do almost nothing.
I have even implemented an automatic switch to high chars (A to Z) because in Transformers was the only way to find the files.
practically: no exact crc, no party

so at the moment I have found no ways to bypass this limitation that luckily affects only a very small number of files like none in Transformers and some in the same folder in LEGO Batman.

P.S.: obviously is possible to extract even these "unmatching" files but the problem is that it's not possible to assign them a name... bad
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T16:44:39+00:00
- Post Title: Lego indiana Jones Trilogy

if someone is interested to the extraction of the ALLTXT.PAK file use the following script:

```
get FILES long
get PAK_SIZE long
get DUMMY long
get DUMMY long
get DUMMY long
savepos INFO_OFF

for i = 0 < FILES
    goto INFO_OFF
    get NAMEOFF long
    get OFFSET long
    get SIZE long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    savepos INFO_OFF

    goto NAMEOFF
    get NAME string

    log NAME OFFSET SIZE
next i
```
## Post #11
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-04T02:33:31+00:00
- Post Title: Lego indiana Jones Trilogy

Would be awesome if the script would be finnished some day 
There are so many games with this format by now.
Mostly for modding purposes, the games launch with the plain files but the game ends up being super glitched because not all file are extracted.
Atleast they don't crash.
## Post #12
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2012-08-04T19:25:32+00:00
- Post Title: Lego indiana Jones Trilogy

hm,

did you read [this](http://forum.xentax.com/viewtopic.php?f=10&t=6618&p54165#p54165) post? Did you try the script from that post? I can extract all files from all tt games lego games with it.

Or did I get your request wrong?

fh
## Post #13
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-05T00:14:03+00:00
- Post Title: Lego indiana Jones Trilogy

Oh, I haven't seen that one so far, I always thought the latest one was on aluigis website.
Thanks dude! Works perfectly.
## Post #14
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-07T23:45:40+00:00
- Post Title: Lego indiana Jones Trilogy

> Reply from aluigi
>
> it has been a hard work but I did it 
http://aluigi.org/papers/bms/ttgames.bms

the script covers all the games developed by Traveller's Tales included LEGO Batman, LEGO Star Wars (like Complete Saga) and Transformers
i can say this works on harry potter 1-4 im testing 5-7 but the files are like3 gbs each
## Post #15
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-08T00:01:01+00:00
- Post Title: Lego indiana Jones Trilogy

> Reply from lllccc
>
> aluigi wrote:it has been a hard work but I did it 
http://aluigi.org/papers/bms/ttgames.bms

the script covers all the games developed by Traveller's Tales included LEGO Batman, LEGO Star Wars (like Complete Saga) and Transformers
i can say this works on harry potter 1-4 im testing 5-7 but the files are like3 gbs each

See the posts above
[viewtopic.php?f=10&t=6618&p54165#p54165](http://forum.xentax.com/viewtopic.php?f=10&t=6618&p54165#p54165)
## Post #16
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-08T00:48:21+00:00
- Post Title: Re: Lego indiana Jones Trilogy

> Reply from Gruselgurke
>
> lllccc wrote:aluigi wrote:it has been a hard work but I did it 
http://aluigi.org/papers/bms/ttgames.bms

the script covers all the games developed by Traveller's Tales included LEGO Batman, LEGO Star Wars (like Complete Saga) and Transformers
i can say this works on harry potter 1-4 im testing 5-7 but the files are like3 gbs each

See the posts above
viewtopic.php?f=10&t=6618&p54165#p54165

ok i will check it out but his worked for me unless there files missing? im trying  edit fmv files and xma if you can bump me in the right way that will be helpful
## Post #17
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-02-05T02:24:39+00:00
- Post Title: Re: Lego indiana Jones Trilogy

Thanks for the script Luigi! 

However, when I try to use it on LEGO MARVEL Super Heroes for Xbox 360, I get an ExceptionCode c0000005 with each PAK file. I'll pm you with some samples.
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-26T09:23:29+00:00
- Post Title: Re: Lego indiana Jones Trilogy

I guess it's the same problem of Lego the movie, looks like the developers changed something in the dflt algorithm or added some type of obfuscation in the last chunk of the compressed files.
There is no solution at the moment.
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-03-16T11:02:17+00:00
- Post Title: Re: Lego indiana Jones Trilogy

I have just found in this moment that if I compile quickbms using the gcc option -fno-unit-at-a-time I'm able to decompress the files of Lego Movie PS3 (no problems with PC).

Setting that option in gcc costs me less than reviewing the whole dlft code to understand what's the problem :)
Anyway I cannot guarantee that the last chunk of the compressed files of Lego PS3 are 100% correct, I gave them a quick look and their last part seems ok but I can't be sure.

So in the next quickbms you will be able to extract these files.
