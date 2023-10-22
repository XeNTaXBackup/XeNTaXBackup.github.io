## Post #1
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2013-01-05T18:31:31+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

Hello all ! 

For a long time on the Internet seeking a program that would find me in-game texts in ARC files. I tried to open with HEX editor, but I did not find the in-game texts... 
I know that the user name Caws created a text editor for Silent Hill Shattered Memories, but it seems to be inactive...

I'm trying to create a program that would set. scanned ARC, and listed it game texts. You do not know any script that would set scan, and texts from him written. Sorry for my English. I am from Czech Republic. 

```
http://img571.imageshack.us/img571/3953/shte.jpg
```


Thank for answer.
## Post #2
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2013-02-21T18:58:07+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

Im looking for the same tool. Russians made one as well, but they want money for it on some website or at least couple of years ago.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-25T15:51:57+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

> Reply from |SyKy|
>
> I'm trying to create a program that would set. scanned ARC, and listed it game texts.
And why? For SHSM i made [unpacker](http://forum.xentax.com/viewtopic.php?p=81649#p81649). Download unpacker. Before extract files from ARC download updated filelist in attach and copy in Project folder (Unpacker). After you can extract files from ARC and found files like:

```
strings.enu
strings.fre
strings.fru
strings.ger
strings.ita
strings.jap
strings.spa
strings.spu
```


> Reply from 3pacalypse
>
> Russians made one as well, but they want money
I dont know where you found these noobs who want money 

PS : for SHO I did not see the archives
[SHSM_Projects_0.2.rar](https://xentaxbackup.github.io/file/6217_SHSM_Projects_0.2.rar)
## Post #4
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2013-03-05T16:12:37+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

I will upload later some archives if you want to take a look. Are you interested?
## Post #5
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2013-03-07T20:25:33+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

> Reply from Ekey
>
> |SyKy| wrote:I'm trying to create a program that would set. scanned ARC, and listed it game texts.
And why? For SHSM i made unpacker. Download unpacker. Before extract files from ARC download updated filelist in attach and copy in Project folder (Unpacker). After you can extract files from ARC and found files like:
Code: Select allstrings.eng
strings.enu
strings.fre
strings.fru
strings.ger
strings.ita
strings.jap
strings.spa
strings.spu
3pacalypse wrote:Russians made one as well, but they want money
I dont know where you found these noobs who want money 

PS : for SHO I did not see the archives

Thanks " I love YOU!!!    How to  put back strings.eng? Thanks
## Post #6
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2013-05-26T19:06:51+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

Here is file "strings.ENG" in HEX Editor. 

Please help how to decode this text. Thanks for answer.
## Post #7
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-05-27T13:47:35+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

It's encoded in UTF-16, any text editor worth using should allow you to edit it without any problem (unless it has an extra non-text header of some kind).
## Post #8
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2017-11-02T20:28:47+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

I extracted file from DATA.ARC contains English subtitles from game. But i translating game with HEX Editor. I must write new letters in same positions of old text. Is any chance to create text editor for translating language file to other language without compliance number of original text? I attached original language file in this message.



Thanks for help  
[2C238264 ORIGINAL.7z](https://xentaxbackup.github.io/file/13516_2C238264 ORIGINAL.7z)
## Post #9
- Username: BANDIT
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 13, 2011 4:19 am
- Post datetime: 2017-11-04T13:24:41+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

Try this tool - [http://www53.zippyshare.com/v/szPV5nqr/file.html](http://www53.zippyshare.com/v/szPV5nqr/file.html)
## Post #10
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2017-11-05T10:49:26+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

> Reply from BANDIT
>
> Try this tool - http://www53.zippyshare.com/v/szPV5nqr/file.html

Thanks. I aready have already this tools. I translated some text in strings.eng and i put back in to the DATA.ARC. DATA.ARC is now a little biggest. But game have a LBA file system security. So i edited SLES_555.69 via HEX Workshop and update strings.eng file size, but game keeps black screen and dont load :/

My steps:

Opened SHSM.iso with CDmage
Extracted DATA.ARC into windows folder
Extracted DATA.ARC with arctool
Translated strings.eng to Czech language
I put back strings.eng to DATA.ARC (now file is little bigger than original)

Work in HEX Editor => SLES_555.69 file

ORIGINAL
strings.eng original size is 431716 kb
hex 06 96 64 in hex editor reverse 64 96 06

REPLACED WITH
new size 456 052 kb
hex 06 F5 74 in hex editor reverse 74 F5 06

But game still not load => only black screen. I think it's a problem in new DATA.ARC (it's bigger)

Please help me. I will translate this game.
## Post #11
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2017-11-08T20:50:39+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

I run Original and Modded game with PCSX2 console log. I add files for download to  this post. Thanks for help 
[PCSX_SHSMoriginal_VS_modded.zip](https://xentaxbackup.github.io/file/13532_PCSX_SHSMoriginal_VS_modded.zip)
## Post #12
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2018-11-12T20:19:02+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

Hello.

I sucessfully translated PS2 version. And i now translating WII version, but i need edit a font file from the game. I must add czech letters like: (ěščřžýáíé), but i have extracted all files from DATA.ARC. all files have name like data_1234,data_1231 etc). I know the font file maybe have .kft file type. Is any way to find this file? THX for answer! 

//EDIT: I found a font file, is any way to edit this? I have a SHSM Font editor, but ive me a error while opening this file. :/
[data_1726.zip](https://xentaxbackup.github.io/file/15185_data_1726.zip)
## Post #13
- Username: ISKA
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 4:52 pm
- Post datetime: 2018-11-23T14:30:38+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

EDIT
## Post #14
- Username: ISKA
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 4:52 pm
- Post datetime: 2020-02-12T00:17:46+00:00
- Post Title: Silent Hill: Shattered Memories font FILE search?

Is there any news? I need edit some characters.
[font_files.zip](https://xentaxbackup.github.io/file/17489_font_files.zip)
