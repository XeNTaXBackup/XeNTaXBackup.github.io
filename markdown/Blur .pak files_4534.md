## Post #1
- Username: btlncn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2009 10:17 am
- Post datetime: 2010-05-30T17:50:27+00:00
- Post Title: Blur .pak files

I have some .pak files from the game Blur. If someone could help me decompress them I would appreciate it. I've included files from both the 360 and PC versions of the game.
[http://www.megafileupload.com/en/file/2 ... s-zip.html](http://www.megafileupload.com/en/file/235836/PAKFiles-zip.html)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-30T21:42:02+00:00
- Post Title: Blur .pak files

unfortunately the table with the name of the files is obfuscated in some way, for the rest the following is the script for QuickBMS compatible with both the PC and the 360 version:

[http://aluigi.org/papers/bms/blur.bms](http://aluigi.org/papers/bms/blur.bms)

*edit* the script has been updated!
## Post #3
- Username: btlncn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2009 10:17 am
- Post datetime: 2010-05-30T23:32:30+00:00
- Post Title: Blur .pak files

Thanks a million.
## Post #4
- Username: btlncn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2009 10:17 am
- Post datetime: 2010-05-31T00:14:22+00:00
- Post Title: Blur .pak files

Well it does work for the ones I sent you but on the others its throwing an error. (Something about an incorrect zlib/deflate input as well as a negative output size for the PC version, and trying the other xbox files cause a hard lock up). Most of the others ones are too large to upload but here is one that didnt work that is a reasonable size. I uploaded it here.
[http://www.megaupload.com/?d=VAO0FWB7](http://www.megaupload.com/?d=VAO0FWB7)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-31T09:39:51+00:00
- Post Title: Blur .pak files

ok I have updated the script, anyway I can't assure it will work with the other files because the format is strange and I used work-arounds
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-31T10:46:30+00:00
- Post Title: Blur .pak files

I have found the xor key for the names so now the new script I have linked in my original post extracts the file with all their names :)
## Post #7
- Username: bigBear
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Oct 09, 2009 2:51 am
- Post datetime: 2010-05-31T15:05:23+00:00
- Post Title: Blur .pak files

Next time use Sendspace or Mediafire.
The site you used is so damn annoying as hell!
Full of advertisements and scripts wich makes downloaling impossible.
And even impossible the downloadlink after finished counting.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-31T15:51:47+00:00
- Post Title: Blur .pak files

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-31T16:46:27+00:00
- Post Title: Blur .pak files

I have just updated the script (0.2.1) adding another work-around for supporting the non-compressed files.
I hope that now it will work with the majority of the archives.
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-31T18:47:34+00:00
- Post Title: Blur .pak files

Thanks a lot for this!
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-31T19:32:09+00:00
- Post Title: Blur .pak files

If anyone is interested, here's a *.baf extractor I wrote. All those baf archives are contained in the pak files of Blur. Only tested with the 360 version though but I guess it works the same with the PC version.
EDIT: updated the script with an XMA header writer! All extracted XMA files can be decoded with toWAV now - correct frequency and channels obtained from baf header. 

```
# script version 1.1

endian big
idstring BANK
goto 0x04
get INFOSTART long
get DUMMY long
get FILES long
goto INFOSTART

for i = 0 < FILES
   savepos MYOFF
   getDstring TYPE 0x4
   get INFOLENGTH long
   get UNKNOWN long
   savepos CURR
   get NAME string
   math CURR += 0x20
   goto CURR
   get OFFSET long
   get SIZE long
   if TYPE == "WAVE"
      get UNKNOWN long
	  get UNKNOWN long
	  get FREQ long
	  ReverseLong FREQ
	  get UNKNOWN long
	  get DUMMY threebyte
	  get CH byte
      callfunction xmaheader
	  string NAME += ".xma"
	  log NAME 0 SIZE MEMORY_FILE
   else
      log NAME OFFSET SIZE
   endif
   
   math MYOFF += INFOLENGTH
   goto MYOFF
next i

startfunction xmaheader
   set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"
   set RIFFSIZE SIZE
   ReverseLong RIFFSIZE
   putVarChr MEMORY_FILE 0x38 RIFFSIZE long # data size
   math RIFFSIZE += 0x34
   putVarChr MEMORY_FILE 0x04 RIFFSIZE long
   putVarChr MEMORY_FILE 0x24 FREQ long
   putVarChr MEMORY_FILE 0x31 CH byte
   append
   log MEMORY_FILE OFFSET SIZE
   append
   math SIZE += 0x3c
endfunction

```
## Post #12
- Username: btlncn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2009 10:17 am
- Post datetime: 2010-05-31T21:07:53+00:00
- Post Title: Blur .pak files

Thanks very much, sorry about the megaupload thing, I just used the first one that popped up.
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-31T23:25:09+00:00
- Post Title: Blur .pak files

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-01T14:30:09+00:00
- Post Title: Blur .pak files

ops sorry my fault, I compared SIZE with the aligned size of ZSIZE and forgot to compare it with the original ZSIZE :)
updated version 0.2.2 (the last? maybe)
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-06-01T15:04:57+00:00
- Post Title: Blur .pak files

Aluigi, the bms works perfect   
Alphatwtythree i get errors in the audio files i'm using a PC version:

> - open input file env_traffic.baf
>
> - open script bluraud.bms
>
> - set output folder .
>
> 
>
>   offset   filesize   filename
>
> ------------------------------
>
> 
>
> Error: incomplete input file number 0, can't read 4 bytes.
>
>        anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted
## Post #16
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-01T15:15:24+00:00
- Post Title: Re: Blur .pak files

PC version isn't big endian and of course the audio files aren't xma - so just use this script:

```
# (c) 06-2010 by Alpha23

idstring BANK
goto 0x4
get INFOSTART long
get DUMMY long
get FILES long
goto INFOSTART

for i = 0 < FILES
   savepos MYOFF
   getDstring TYPE 4
   get INFOLENGTH long
   get UNKNOWN long
   getDstring NAME 0x20
   get OFFSET long
   get SIZE long
   log NAME OFFSET SIZE
   math MYOFF += INFOLENGTH
   goto MYOFF
next i
```
## Post #17
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-01T15:21:17+00:00
- Post Title: Re: Blur .pak files

> Reply from aluigi
>
> ops sorry my fault, I compared SIZE with the aligned size of ZSIZE and forgot to compare it with the original ZSIZE 
updated version 0.2.2 (the last? maybe)
THANKS - terrific!
## Post #18
- Username: btlncn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2009 10:17 am
- Post datetime: 2010-06-01T17:15:23+00:00
- Post Title: Re: Blur .pak files

TwentyThree have you found the texture files for the cars, I can't seem to find them and thus I'm assumming they are bundled in the .model files.
## Post #19
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-02T15:23:01+00:00
- Post Title: Re: Blur .pak files

Probably, yes. I'm only after the music though.
## Post #20
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2010-06-14T09:12:46+00:00
- Post Title: Re: Blur .pak files

> Reply from aluigi
>
> ops sorry my fault, I compared SIZE with the aligned size of ZSIZE and forgot to compare it with the original ZSIZE 
updated version 0.2.2 (the last? maybe)
I extracted root.pak from pc version of blur and get 3388 files, with total of 131841695 bytes.
root.pak is 559652864 bytes long. biggest extracted file is 65536 bytes. maybe compressed files are chunked?

ps: quickbms - ver. 0.4.5; blur.bms - ver. 0.2.2
ps2: same issue with other .pak files
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-14T14:46:58+00:00
- Post Title: Re: Blur .pak files

if you receive the request of overwriting files with the same name then yes it could be, if you receive no request means that it's all ok as is (for example they could be chunked but the engine handles them as single files)
## Post #22
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2010-06-16T10:47:17+00:00
- Post Title: Re: Blur .pak files

rewrited aluigi's script.
sorry, no longer xbox360 support, but now extracts "full" files from pc-version PAKs 

```
if SIGN != "2KAP"
    print "Unsupported archive type"
    cleanexit
endif

get VERSION long
if VERSION != 2
    print "Unsupported archive version"
    cleanexit
endif

get MYALIGN long
get DUMMY long
get COMP_TYPE byte
goto MYALIGN
get NAMES_SIZE long

savepos OFFSET
encryption xor "VXo40j3@$%\\%`x"
log MEMORY_FILE OFFSET NAMES_SIZE
encryption "" ""
math OFFSET += NAMES_SIZE
math OFFSET x= MYALIGN
goto OFFSET

get FILES long
get FILES_SIZE long
for i = 0 < FILES
    get DUMMY long
    get NAME_OFF long
    get DUMMY long
    get SIZE long
    get TIMESTAMP longlong
    get OFFSET longlong
    get DUMMY long
    get ZSIZE long
    if COMP_TYPE == 2
        getdstring DUMMY 0x18
    endif


    goto NAME_OFF MEMORY_FILE
    get NAME string MEMORY_FILE

    if OFFSET != -1
        math OFFSET *= MYALIGN
        savepos TMP
        goto OFFSET
        if COMP_TYPE == 4
            log MEMORY_FILE2 0 0
            append
            get CHUNK_SIZE long
            comtype deflate
            math CHUNKS = SIZE
            math CHUNKS x= CHUNK_SIZE
            math CHUNKS /= CHUNK_SIZE
            for j = 0 < CHUNKS
                get ZSIZE long
                savepos OFFSET
                clog MEMORY_FILE2 OFFSET ZSIZE CHUNK_SIZE
                math OFFSET += ZSIZE
                goto OFFSET
            next j
            append
            log NAME 0 SIZE MEMORY_FILE2
        elif COMP_TYPE == 2
            comtype zlib
            clog NAME OFFSET ZSIZE SIZE
        elif COMP_TYPE == 1
            log NAME OFFSET SIZE
        endif
        savepos OFFSET
        goto TMP
    endif
next i

```
## Post #23
- Username: Roofel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 17, 2010 1:09 am
- Post datetime: 2010-06-16T18:44:21+00:00
- Post Title: Re: Blur .pak files

Know what "filetype" the extracted "music" is? Been trying to play it with VLC, checking for any signs of what it can be but cant find anything... Would really love some feedback on that
## Post #24
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-16T22:31:27+00:00
- Post Title: Re: Blur .pak files

[viewtopic.php?f=17&t=4542](http://forum.xentax.com/viewtopic.php?f=17&t=4542)
new format... :\
## Post #25
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-11T23:59:08+00:00
- Post Title: Re: Blur .pak files

I got errors about deflate when unpacking shaders-speed.pak.
Can anyone help me with this issue?
## Post #26
- Username: Fenris93
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Jul 20, 2010 6:51 am
- Post datetime: 2010-11-05T11:35:51+00:00
- Post Title: Re: Blur .pak files

Someone knows how to pack again the .pak file? Thanks!
## Post #27
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-10T19:41:37+00:00
- Post Title: Re: Blur .pak files

Can someone update script for this file. Is different as original gamedata.pak. Please hurry.

```
http://www.multiupload.com/EQD16C4N59
```
## Post #28
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-10T19:58:58+00:00
- Post Title: Re: Blur .pak files

from what version and platform of Blur have you got that file?
## Post #29
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-10T20:27:23+00:00
- Post Title: Re: Blur .pak files

anyway script update to version 0.2.3:
[http://aluigi.org/papers/bms/blur.bms](http://aluigi.org/papers/bms/blur.bms)
## Post #30
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-11T19:28:06+00:00
- Post Title: Re: Blur .pak files

Thanks, aluigi. This file is from PC version
## Post #31
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-06-23T04:41:26+00:00
- Post Title: Re: Blur .pak files

The contents of this post was deleted because of possible forum rules violation.
## Post #32
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-06-27T17:31:54+00:00
- Post Title: Re: Blur .pak files

Can anyone help me with this files to ps3?
## Post #33
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-06-27T23:14:25+00:00
- Post Title: Re: Blur .pak files

Very unfortunately... there's not much support in trying to get this game modded further.
I've tried even contacting some of the ex-developers and didn't get very far.
## Post #34
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-28T14:47:38+00:00
- Post Title: Re: Blur .pak files

I have updated the script to version 0.2.4 for maximum compatibility, so test it and let me know if the files are all correctly extracted:
[http://aluigi.org/papers/bms/blur.bms](http://aluigi.org/papers/bms/blur.bms)
## Post #35
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-06-28T17:04:06+00:00
- Post Title: Re: Blur .pak files

Thank aluigi.
## Post #36
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-04T04:10:53+00:00
- Post Title: Re: Blur .pak files

The tool of. Loc pc does not work with. Loc the ps3, does anyone know these files?
[files.rar](https://xentaxbackup.github.io/file/4434_files.rar)
## Post #37
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-13T00:52:09+00:00
- Post Title: Re: Blur .pak files

Aluigi, I'm trying to do the reimport with this code only he did not re-import anything I've done it with other more with this script is not the case have any merit?

Is to make a simple script to support the re-importation?

Thank you.
## Post #38
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-15T12:26:59+00:00
- Post Title: Re: Blur .pak files

The contents of this post was deleted because of possible forum rules violation.
## Post #39
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-07-16T20:26:56+00:00
- Post Title: Re: Blur .pak files

Use script (version 0.2.4) that is posted in this thread. It's also for console version of Blur.
## Post #40
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-18T10:48:08+00:00
- Post Title: Re: Blur .pak files

Friend, version 0.2.4 does not re-import the files.

Can anyone help me? just need to translate this game.

Hug.
## Post #41
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-07-18T21:25:35+00:00
- Post Title: Re: Blur .pak files

Oh yes, reimporting. I thought you want to extract that .dat file.   
Did you translate .loc files?
## Post #42
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-07-18T21:37:17+00:00
- Post Title: Re: Blur .pak files

Yes, the tool made ​​of caws .Loc

now just need it re-import the .pak
## Post #43
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2012-10-04T18:35:46+00:00
- Post Title: Re: Blur .pak files

Tool does not properly extracts some files. For example, from root.pak file 
roo\ui\data\ui_font_eur.bpr seems 64kb, but when I looked with hex that offset, there is more 64kb chunks that all of them constitutes real complete  file. 
4byte(decompressed chunksize) 4 byte(size of compressed chunk1)  COMPRESSED_CHUNK1 4 byte(size of compressed chunk2)  COMPRESSED_CHUNK2 .... goes like that.
I calculated complete size of file around 1024kb.
Now, Im waiting aluigi to make proper his bms script please.
## Post #44
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-04T22:14:28+00:00
- Post Title: Re: Blur .pak files

I don't see chunks in blur.bms
## Post #45
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2012-10-05T08:15:36+00:00
- Post Title: Re: Blur .pak files

Sorry, if my english has lead to misundertanding. I was talking about root.pak file. I went to start offset of compressed data of that file root\ui\data\ui_font_eur.bpr. Now Im attaching that part of file. I hope now it will be more clear. 
"compressed" is part from root.pak file that  contains  compressed parts of root\ui\data\ui_font_eur.bpr
"ui_font_eur.bpr"  is incomplete file that is extracted by blur.bms.
When I extracted this "compressed"  file with "offzip -a -z -15 compressed output 0" there are many extracted files 64kb and the last one less than that.
[example.7z](https://xentaxbackup.github.io/file/5878_example.7z)
## Post #46
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-06T09:11:04+00:00
- Post Title: Re: Blur .pak files

ok understood, so I guess there is one of those DUMMY fields in blur.bms that is used to track chunked files.
how much big is root.pak?
I don't have the game.
## Post #47
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2012-10-06T12:38:34+00:00
- Post Title: Re: Blur .pak files

root.pak is 533MB. 
But, I found similar problem in the another file that has smaller size.
Here the file: [lut_rampak.pak](http://www28.zippyshare.com/v/66529189/file.html)
## Post #48
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-06T13:14:42+00:00
- Post Title: Re: Blur .pak files

ok done thanx.
I have attached the current script to this thread so you can perform additional tests and when/if it's enough stable I will update the one online.

as written in the title of the script I have just left all the compatibility work-arounds I inserted in the various versions of the script to grant access to the various archives for xbox, pc, ps3 and so on.
that means it's not 100% stable but hopefully works correctly.

let me know the result with root.pak

*edit*
[http://aluigi.altervista.org/papers/bms/blur.bms](http://aluigi.altervista.org/papers/bms/blur.bms)
## Post #49
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2012-10-06T13:29:26+00:00
- Post Title: Re: Blur .pak files

Now, it seems extracted well. Thanks for update.
But, in console extraction offset is for all files are 00000000 .
## Post #50
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-06T13:43:27+00:00
- Post Title: Re: Blur .pak files

yeah it's normal because the chunks get unpacked in memory and so 0 is the offset of the resulted memory file
## Post #51
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-03T21:52:29+00:00
- Post Title: Re: Blur .pak files

up 

So extracted *.loc files and translated all *.txt files and reimport.
Then how can we force the game to read and display them?
