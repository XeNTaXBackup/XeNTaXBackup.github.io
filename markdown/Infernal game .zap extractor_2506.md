## Post #1
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2007-03-10T17:22:52+00:00
- Post Title: Infernal game .zap extractor

Hi. I would like to edit this file, it is english language from Infernal game, but it looks like it is compressed/encrypted.

Can anyone decode it??

Some links:

```
http://www.playlogicgames.com/games/?id=infernal

```


File attached...
[english_strings.zip](https://xentaxbackup.github.io/file/1086_english_strings.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-11T02:31:57+00:00
- Post Title: Infernal game .zap extractor

The game can be unpacked with zlib, BUT!!!...
I tried to pack with it (zlib) and the game DON'T works, llok dont recognize the recompressed data

if you try precomp or some zlib generic unpacker maybe you can't unpack

The game uses this unpacker "[http://www.winimage.com/zLibDll](http://www.winimage.com/zLibDll)" it's different from zlib.net?
## Post #3
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-03-24T15:09:04+00:00
- Post Title: Infernal game .zap extractor

At the very bottom, you see the 3 fileparts

Before the filepart, there's a single byte, with I think the filecount.

After the filename, there's:

int Position
int Decompressed Filesize
int Compressed filesize
int Unknown (Always 898673295)
int Unknown (Always 0)
int Unknown (Always 517734657)

This post will be edited when I know more.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-04-12T19:28:34+00:00
- Post Title: Infernal game .zap extractor

Well i tested how to unpack the data, and again it's missing some zlib info, here it's the strings file unpacked, i did it manually (i dont know really how i did xDD)

The info of files are down of the file

```
ÿ   6   ]   iteminfos.gamestr    )  à
```

[english_strings.unzapped.rar](https://xentaxbackup.github.io/file/1122_english_strings.unzapped.rar)
## Post #5
- Username: ardalaaan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 09, 2007 4:17 am
- Post datetime: 2007-04-13T15:23:14+00:00
- Post Title: Infernal game .zap extractor

I have just extract sound_english.zap with dragon unpacker 5 to some sound files (.OGG)
and now I want to repack them to .zap file after editing them
what software do u suggest for doing this (repack)
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-13T16:07:59+00:00
- Post Title: Infernal game .zap extractor

> Reply from Savage
>
> Code: Select allíZKSGžsªr
Please post such things in hex code.
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-04-13T17:38:46+00:00
- Post Title: Infernal game .zap extractor

> Reply from Rheini
>
> 
Please post such things in hex code.
Here is, the HEX code of the example
[zap.PNG](https://xentaxbackup.github.io/file/1123_zap.PNG)
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-04-23T17:59:51+00:00
- Post Title: Infernal game .zap extractor

> what software do u suggest for doing this (repack)
try jaeder naub injection
## Post #9
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-05-14T08:48:30+00:00
- Post Title: Infernal game .zap extractor

Hi everyone
There is my personal blog about games and some my tools for it.
[http://int0thegame.blogspot.com/2007/05 ... actor.html](http://int0thegame.blogspot.com/2007/05/infernal-zap-file-extractor.html)
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-05-14T16:49:08+00:00
- Post Title: Infernal game .zap extractor

Thanks!!!!
## Post #11
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-05-15T10:15:01+00:00
- Post Title: Infernal game .zap extractor

You welcome
## Post #12
- Username: ardalaaan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 09, 2007 4:17 am
- Post datetime: 2007-05-16T12:44:45+00:00
- Post Title: Infernal game .zap extractor

nice work
## Post #13
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2007-05-22T11:07:24+00:00
- Post Title: Infernal game .zap extractor

thank's for tools

1: after extract all zap file , zip them by "save full path" ?

2: when i want extract "scenes.zap" see:
## Post #14
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-05-22T14:51:23+00:00
- Post Title: Infernal game .zap extractor

What u did, seems progress bar fucked up   Progress bar not affect on decompression process.
## Post #15
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2007-05-23T05:46:48+00:00
- Post Title: Infernal game .zap extractor

Extract all file is ok , only "scenes.zap" crash...
help me.?
## Post #16
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-05-23T07:57:24+00:00
- Post Title: 

Ill fix it asap, yesterday just finished Lost Planet .ARC Extractor will check Infernal today again
## Post #17
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2007-05-24T19:36:35+00:00
- Post Title: 

Great job...
Thanks you very much...
## Post #18
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2007-05-26T19:33:24+00:00
- Post Title: 

> Reply from mikehood
>
> Extract all file is ok , only "scenes.zap" crash...
help me.?

I use the first verson of zap unpacker to unpack scenes.zap, because the newer version go to cracsh...

Other files can be unpacked with new version
## Post #19
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2007-05-26T19:34:57+00:00
- Post Title: 

> Reply from itg
>
> Ill fix it asap, yesterday just finished Lost Planet .ARC Extractor will check Infernal today again

And are you able to create .zap packer?

I would like to create my own mods and I do not want to unpack all zap files and repack them to .zip...
## Post #20
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-07-13T23:46:39+00:00
- Post Title: 

Can you rehost .ZAP unpacker because the link on your wbsite is not working.
## Post #21
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-14T07:52:40+00:00
- Post Title: 

> Reply from kimkalisto
>
> Can you rehost .ZAP unpacker because the link on your wbsite is not working.

Hm, where is the problem? now all tools hosted on the xentax, here is the direct link.

[http://www.xentax.com/uploads/author/itg/zap.tool.rar](http://www.xentax.com/uploads/author/itg/zap.tool.rar)

Also attachment included 
[zap.tool.rar](https://xentaxbackup.github.io/file/1263_zap.tool.rar)
