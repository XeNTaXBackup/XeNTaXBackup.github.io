## Post #1
- Username: lclumos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 03, 2009 3:52 am
- Post datetime: 2009-05-07T09:08:04+00:00
- Post Title: Need advice about pack/unpack files...

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-08T12:20:27+00:00
- Post Title: Need advice about pack/unpack files...

dxm and acv files seem to be compressed. tbm seems to contain audio data.
## Post #3
- Username: lclumos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 03, 2009 3:52 am
- Post datetime: 2009-05-08T14:30:14+00:00
- Post Title: Need advice about pack/unpack files...

Yep, actually the most important file that I want to ask for help is the .acv file...
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-09T00:51:35+00:00
- Post Title: Need advice about pack/unpack files...

QuickBMS
I made a script but it is not 100% I am sure someone can help you finish it.
This will be an extractor only.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get FILES long
math FILES -= 1

for i = 0 < FILES

getdstring NAME 160
get UNK1 long
get ZSIZE long
get SIZE long
get OFFSET long

    set OFFSETS long 176
    math OFFSETS *= 2
    math OFFSETS += 4
    math OFFSET += OFFSETS

clog NAME OFFSET ZSIZE SIZE
next i

```


Everything works great in this code except I can't figure out how to convert     math OFFSETS *= 2 into     math OFFSETS *= FILES
so until someone fixes my mistake just look at the file in hex and convert math OFFSETS *= 2 into math OFFSETS *= the number of files listed -1 and you will be all set

I attached the archive that has 2 files in it this script will work un modified on this archive.

for example archive 036.avc contains 2040 files so it would be  math OFFSETS * 2040

I am not sure if it needs the append option or not.
[032.rar](https://xentaxbackup.github.io/file/2017_032.rar)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T10:55:48+00:00
- Post Title: Need advice about pack/unpack files...

it's simple, build a FILE_OFFSET or a BASE_OFFSET that then you must simply add to the read OFFSET like in this example:

```
set FILE_OFFSET long FILES
math FILE_OFFSET *= 176
math FILE_OFFSET += 4

for i = 0 < FILES
    getdstring NAME 160
    get UNK1 long
    get ZSIZE long
    get SIZE long
    get OFFSET long

    math OFFSET += FILE_OFFSET
    clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-09T13:28:36+00:00
- Post Title: Need advice about pack/unpack files...

Thanks bugtest now I know how to do this kind of archive 
I should of looked beforehand but this is the same format as company of heroes
and there is already mod tools for this game.
[http://forum.ragezone.com/f268/acv-tool ... er-456025/](http://forum.ragezone.com/f268/acv-tool-release-acv-unpacker-456025/)
I also took a look at these files and it seems that any avc file > 40 has a different archive format.

```
get FILES long
set FILE_OFFSET long FILES
math FILE_OFFSET *= 180
math FILE_OFFSET += 8

for i = 0 < FILES
    getdstring NAME 160
    get NULL long
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get NULL long

    math OFFSET += FILE_OFFSET
    clog NAME OFFSET ZSIZE SIZE
next i

```


I don't know what compression these files are though I know I have the file table right and the zip size + offset and the name right but I can't figure out the rest.
here is a file.
[http://www.MegaShare.com/876991](http://www.MegaShare.com/876991)
## Post #7
- Username: lclumos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 03, 2009 3:52 am
- Post datetime: 2009-05-10T23:10:26+00:00
- Post Title: Need advice about pack/unpack files...

[http://forum.ragezone.com/f268/acv-tool ... er-456025/](http://forum.ragezone.com/f268/acv-tool-release-acv-unpacker-456025/)
This link here is about the acv pack and unpack tool. Unfortunately, Audition is the online game, so the acv. files are updated monthly. And because a lot of people used that pack and unpack tool to make hack-tools or cheat-tools, the acv now are compressed in different ways that prevent pack and unpack tool from extracting them. The acv files are now from 001.acv to 065.acv and many of them cannot be opened by the tool on the link above. If you guys want to know, I will upload all of them. Moreover, the reasons I ask for help here are because xentax works specifically in this area ( if I do not misunderstand ), and because Audition is only popular in Asia, there would be few people who know about this thread. Therefore, there would be less hack-tools. My purpose is not like making hack-tools and I hate them. I just want to extract the acv files to see what in there, to change some textures and stuffs like that.
## Post #8
- Username: lclumos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 03, 2009 3:52 am
- Post datetime: 2009-05-10T23:17:39+00:00
- Post Title: Need advice about pack/unpack files...

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-05-11T21:08:11+00:00
- Post Title: Need advice about pack/unpack files...

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: lclumos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 03, 2009 3:52 am
- Post datetime: 2009-05-13T00:43:43+00:00
- Post Title: Need advice about pack/unpack files...

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-23T01:45:27+00:00
- Post Title: Need advice about pack/unpack files...

Google gave me this while I was looking for audition unpacker.
The poster said 2 years ago that the tool from ragezone didn't work.

Got out the first 39 archives, then everything else is compressed.
It gets out a lot of models and textures though, so it should be enough if people just want models.
