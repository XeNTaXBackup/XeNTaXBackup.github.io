## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-18T21:08:07+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

[http://www.megaupload.com/?d=QIJN1PU0](http://www.megaupload.com/?d=QIJN1PU0)

Here is an asr cut from the new avp game. main original file is 800mb or more.



thanks.
## Post #2
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-02-18T23:53:56+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

bump, i was gona add this thread but you beat me to it :p

there a guy at garrysmod that extracting with 3dripper, i hate that prog so hopefully there something better hear.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-19T00:18:53+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

The archive contains soundstreams, not 3d files.
## Post #4
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-02-19T00:42:02+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

kk sorry.

you know anyway of extracting meshes without 3dripper?
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-19T00:47:03+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

no, i only do sounds.
## Post #6
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-21T18:51:41+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

Hi there

Aluigi Qbms script V.2 for asura .asr .pc .en works fine with this title for sounds and textures but no 3d models and ini, hdr files in .pc unfortunately.
Link to .pc [http://www.megaupload.com/?d=MB9NL5RP](http://www.megaupload.com/?d=MB9NL5RP)
Here is the script:

```
#  Sniper Elite
#  Rogue Trooper
#  Guard Shield
#  possibly other Rebellion's games
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get PACK_SIZE asize
getdstring SIGN 8
if SIGN == "AsuraCmp"
    get ZSIZE long
    get SIZE long
    math ZSIZE = PACK_SIZE
    math ZSIZE -= 8
    comtype huffboh
    clog TEMPORARY_FILE 8 ZSIZE SIZE
    open "." TEMPORARY_FILE
    get PACK_SIZE asize
    getdstring SIGN 8
elif SIGN == "AsuraZlb"
    get ZERO long
    get ZSIZE long
    get SIZE long
    savepos OFFSET
    math ZSIZE = PACK_SIZE
    math ZSIZE -= OFFSET
    comtype zlib
    clog TEMPORARY_FILE OFFSET ZSIZE SIZE
    open "." TEMPORARY_FILE
    get PACK_SIZE asize
    getdstring SIGN 8
endif
if SIGN != "Asura   "
    cleanexit
endif

for
    savepos CHUNK_OFFSET
    math TMP = CHUNK_OFFSET
    math TMP += 16
    if TMP >= PACK_SIZE
        cleanexit
    endif
    getdstring CHUNK 4
    get CHUNKSZ long
    get DUMMY long
    get DUMMY long
    if CHUNK == RSCF
        get TYPE long
        get DUMMY long
        get SIZE long
        get NAME string
        math OFFSET = CHUNK_OFFSET
        math OFFSET += CHUNKSZ
        math OFFSET -= SIZE
        log NAME OFFSET SIZE
    #else
        #print "CHUNK %CHUNK% %CHUNK_OFFSET% %CHUNKSZ%"
        #savepos OFFSET
        #math SIZE = CHUNK_OFFSET
        #math SIZE += CHUNKSZ
        #math SIZE -= OFFSET
        #log "" OFFSET SIZE  # comment here if you don't want to extract these useless chunks
    endif
    math CHUNK_OFFSET += CHUNKSZ
    goto CHUNK_OFFSET
next

```


I would appreciate If anyone can get me 3d models and config files.

Aluigi take a look please.

I will upload short .pc ASAP.
Link : [http://www.megaupload.com/?d=MB9NL5RP](http://www.megaupload.com/?d=MB9NL5RP)

Thanks.
## Post #7
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-21T20:21:17+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

Add for post above, more precised , 
3d files and some chunks in dat got extracted but not readable format, either offset is wrong or they are compressed too.
## Post #8
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-02-21T22:06:38+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

niceone maddog, i got exited there but if the models aint comeing ill need to keep looking 

hope more ppl can add to this & if i find anything ill let you know
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-21T23:24:37+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

thx for scripty
## Post #10
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-02-22T22:30:27+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

Maddog, you sir are my hero! I was having an extremely hard time finding the simple small sfx sounds. Like the weapons, impacts, footsteps and the sort. The bigger things were easy but the stuff hiding in these pc files was what I was after. Many thanks to you!
## Post #11
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-23T18:58:37+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

All credit goes to Aluigi, he's the the master mind and I'm only the servant.   
Anyway thank you guys.

Still need him to look at the 3d models and configs.
## Post #12
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-02-23T19:37:59+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

this guy over at garry's mod was pulling models out of the hat.

he said his buddy was useing 3dripper so i tryied it. it captured everything exept meshes, and all the textures came out black & white, so im still working on it too.
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-23T19:44:23+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

THis script does not work for me on the file that i posted.
## Post #14
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-23T20:21:28+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

Yes script doesn't work for that .asr, because chunk name is ASTS and our script has only one chunk name RSCF.
Also offset for that .asr is different than offset of chunk RSCF.
Recognized stream after 2E53 offset is WAVE.
See what i can do.

Edit : you can change chunk name and byte number in script as ASTS instead of RSCF but without right offset for extraction, files will not come out.
## Post #15
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-02-23T22:56:52+00:00
- Post Title: Aliens Vs predator 2010 PC .asr

> Reply from OrangeC
>
> THis script does not work for me on the file that i posted.

DragonUnpacker/Hyperripper worked just fine for me on the all .asr.
## Post #16
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-24T18:56:51+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

Yes but i would like for it to be with the original file names.
## Post #17
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-02-27T00:17:42+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

will work the game with unpacked zlib container?

alser after offzip -a file.asr when i rename the ecactet file to file.asr?
## Post #18
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-27T13:43:11+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

> Reply from Cryptonia
>
> will work the game with unpacked zlib container?

alser after offzip -a file.asr when i rename the ecactet file to file.asr?

Yes game works without problem with AsuraZlb unpacked out of zlib for .asr and .pc files.
en. files are not zlib compressed and those are sounds in wav format.

I still need help with .pc files and 3d models, props.
## Post #19
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-27T14:04:02+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

The contents of this post was deleted because of possible forum rules violation.
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-07T23:27:59+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

I have updated the script for supporting these ASTS chunks:
[http://aluigi.org/papers/bms/asura.bms](http://aluigi.org/papers/bms/asura.bms)

let me know if there are problems with other files
## Post #21
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-03-10T11:27:57+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

Unpacking the some files like :P03_Refinery.en
I get some errors:

> Error: incomplete input file number 0, can't read 1543504108 bytes.
>
>        anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted
## Post #22
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-10T12:03:48+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

it could be a problem in the "pseudo-padding" used in that new chunk of the archive.
I don't know how to handle it, I simply used a work-around to guess the correct value.
if the archive is enough small try to upload it but I can't guarantee a result
## Post #23
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-03-18T19:00:58+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

AVP .asrs are huge mess. In that one we have 4 or 5 more chunks overlapping and that's why RSCF chunk can not be extracted complete.
More .wav files are at the end of that archive and their chunk is plain RIFF without RSCF. Beside, there are chunks DLLN, DLLT, FAAN, ASTS.
Complete mess.   

Aluigi link:

[http://www.megaupload.com/?d=6K6VQ0U0](http://www.megaupload.com/?d=6K6VQ0U0)
## Post #24
- Username: YgNa
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Mar 20, 2010 2:49 am
- Post datetime: 2010-03-20T18:09:21+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

Es facil editar los archivos .ASR Y .PC.
Yo se los edito, pero deben enviarme un link con el archivo .ASR de Skins!!!
Cualquier cosa pregunten [ignacio_14_a@hotmail.com](mailto:ignacio_14_a@hotmail.com)
Web: [http://www.sniperygna.forumotion.com](http://www.sniperygna.forumotion.com)
## Post #25
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-22T18:18:40+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

@maddog
I have updated the asura.bms script on [http://aluigi.org/papers/bms/asura.bms](http://aluigi.org/papers/bms/asura.bms)
the problem was caused by that senseless padding as usual
## Post #26
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-03-22T23:10:56+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

I get error in the files:
M04_Ruins.pc 
and P04_Ruins.pc 

```
Error: No such file or directory

```

I'm using QuickBMS generic files extractor 0.3.14c
## Post #27
- Username: YgNa
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Mar 20, 2010 2:49 am
- Post datetime: 2010-03-25T21:47:12+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

I can Extract Files .ASR .PC and other files.
I Create mods for Sniper Elite, [http://www.sniperygna.forumotion.com](http://www.sniperygna.forumotion.com)
I can not edit 3D files because they have no extension.
But I edit the textures and sounds, and inject them back to the original file.
Add my MSN or by mail if you need help
[ignacio_14_a@hotmail.com](mailto:ignacio_14_a@hotmail.com)
## Post #28
- Username: cenkzenk
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 01, 2009 8:15 pm
- Post datetime: 2010-03-28T13:37:06+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

TY ALUİGİ
[http://www.dailymotion.com/video/xcqt2m ... es?start=1](http://www.dailymotion.com/video/xcqt2m_alien-versus-predator-rebuyld-edyt_videogames?start=1)
## Post #29
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-08T17:11:04+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

in case someone is interested the following is the latest version of my asura.bms script:
[http://aluigi.org/papers/bms/asura.bms](http://aluigi.org/papers/bms/asura.bms)
## Post #30
- Username: YgNa
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Mar 20, 2010 2:49 am
- Post datetime: 2010-04-09T18:54:37+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

This is a program for Asura Engine.
SPANISH


ENGLISH


Downoload in [http://www.sniperygna.forumotion.com](http://www.sniperygna.forumotion.com)!!!
## Post #31
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-10T00:42:00+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

WIP.
## Post #32
- Username: Ihasgoogled
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 16, 2010 11:27 pm
- Post datetime: 2010-04-17T08:04:29+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

So, how do we handle the exported file without extension ? Hex the shit out of it?
DxRipper isnt working for this game. Also, UVmaps not working or just to lazy to apply materials ?
## Post #33
- Username: YgNa
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Mar 20, 2010 2:49 am
- Post datetime: 2010-04-18T00:23:15+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

The contents of this post was deleted because of possible forum rules violation.
## Post #34
- Username: Skynet
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 28, 2010 3:15 am
- Post datetime: 2010-07-28T20:34:41+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

Bump.

Most can extract now but does anyone have the slightest idea of how to build / rebuild these archives?

[http://www.dailymotion.com/video/xcqt2m](http://www.dailymotion.com/video/xcqt2m) ... es?start=1 -> I can see here you are building an ASR archive, does your team share this knowledge / program cenkzenk?
## Post #35
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2011-06-04T18:56:11+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

Hi there,

I can't extract any avp .asr file with this bms srcipt: [http://aluigi.org/papers/bms/asura.bms](http://aluigi.org/papers/bms/asura.bms)

When I run th script I got only one file which seems to be exactly the same as the original one. If I'm right then there should be 90 files in the .asr file.

Am I doing something wrong?

I attached the file. Could somebody take a look at it?

Thank you.
[Cut_En.zip](https://xentaxbackup.github.io/file/4295_Cut_En.zip)
## Post #36
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-04T19:14:23+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

that file contains only texts so it's all correct, there are no files to extract
## Post #37
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2011-06-04T20:47:34+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

> Reply from aluigi
>
> that file contains only texts so it's all correct, there are no files to extract

So you say it's a single text file? Then what about filenames at the end of the file? Isn't it a compressed file?
## Post #38
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2011-09-07T16:22:02+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

The contents of this post was deleted because of possible forum rules violation.
## Post #39
- Username: cenkzenk
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 01, 2009 8:15 pm
- Post datetime: 2012-02-19T13:36:51+00:00
- Post Title: Re: Aleins Vs predator 2010 PC .asr

> Reply from Skynet
>
> Bump.

Most can extract now but does anyone have the slightest idea of how to build / rebuild these archives?

http://www.dailymotion.com/video/xcqt2m ... es?start=1 -> I can see here you are building an ASR archive, does your team share this knowledge / program cenkzenk?

[http://www.sniperelite2.com/?p=406](http://www.sniperelite2.com/?p=406)




[http://www.sniperelite2.com/?p=398](http://www.sniperelite2.com/?p=398)

ALL REBELLİON GAMES SAME (AVP Rogue Warrior Sev2 Shellshock 2 Never Dead)
[http://www.youtube.com/watch?v=tau2bA5R_uI](http://www.youtube.com/watch?v=tau2bA5R_uI)
[http://www.youtube.com/user/zamundatorrent](http://www.youtube.com/user/zamundatorrent)
