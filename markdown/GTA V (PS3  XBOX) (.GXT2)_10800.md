## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-22T21:09:20+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

Well i made next functions for my parser > Import / Export to TXT , Load / Save GXT2 files. Need someone who have console XBOX/PS3 for test .

Warning: Text files from my old parser NOT SUPPORTED.
Warning2: Text files format should be HASH TAB TEXT (for make tab use TAB button)

Usage:

1.) File > Load GXT2 (Open any gxt2 file)
2.) File > Export to TXT
3.) Translate text or add new labels with text
4.) File > New GXT2
5.) File > Import TXT (Select translated file)
6.) File > Save GXT2
7.) Profit 

Any comments and suggestions  
[GXT2Tools_r19.rar](https://xentaxbackup.github.io/file/6633_GXT2Tools_r19.rar)
## Post #2
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-09-30T16:11:55+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

Tested right now, working good.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-30T22:02:41+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

Excellent. Thanks
## Post #4
- Username: oG Goddess
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Sep 20, 2013 10:52 pm
- Post datetime: 2013-10-30T22:21:11+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

Maybe a find tool? So if i want to look for something in particular like the ...has been shot down by........

Great work.
## Post #5
- Username: Killermannvs
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 07, 2013 4:57 am
- Post datetime: 2013-11-10T09:41:06+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

Ekey, I have found a little issue in your exp/imp function.

If you export and import file global.gxt2 and then you will compare them to original file, for expamle in Total Commander, you will see that CR (0x0D) is replaced by SPACE (0x20).
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-12T06:45:05+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

> Reply from Killermannvs
>
> Ekey, I have found a little issue in your exp/imp function.

If you export and import file global.gxt2 and then you will compare them to original file, for expamle in Total Commander, you will see that CR (0x0D) is replaced by SPACE (0x20).
Yep i know. While export to txt all tab's (0x0A, 0x0D) replaced by to single line and game after translate works without problems.
## Post #7
- Username: ChrisTuffurlo9l
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 05, 2014 4:51 am
- Post datetime: 2014-04-05T15:36:47+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

After importing my TXT, then trying to save, I get this error: [http://grab.by/vMTc](http://grab.by/vMTc)

I'd have typed it, but is has characters my keyboard doesn't.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-06T13:48:03+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

> Reply from ChrisTuffurlo9l
>
> After importing my TXT, then trying to save, I get this error: http://grab.by/vMTc

I'd have typed it, but is has characters my keyboard doesn't.
Open translated txt and on first line delete strange symbols (before 0002EBA8)
## Post #9
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-04-06T20:05:39+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

This BOM from UTF-8 =)
## Post #10
- Username: Metistofel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 27, 2014 3:06 am
- Post datetime: 2014-11-26T20:01:19+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

Need help. with GTA5
Thanks to your program
GXT2Tools.ehe I was able to remove the text, but did not understand how they compare with audio files seized by a
GTAV_PS3_AWCDecoder.ehe (Example (0x15D0FB9F.mp3))
Similar files simply do not
## Post #11
- Username: rugaviyahu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 20, 2014 1:48 am
- Post datetime: 2015-04-20T13:28:01+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

Ekey, do you plan to update your tool for PC version? If not, can you please share source code or gxt2 file structure? Thank you.
## Post #12
- Username: rugaviyahu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 20, 2014 1:48 am
- Post datetime: 2015-04-20T14:47:40+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

> Reply from michalss
>
> Editor for all Platforms:
Code: Select allhttps://dl.dropboxusercontent.com/u/38234344/GTA%20V%20GXT2%20Editor%20V2.rar
Oh, thank you very much! Can you tell about TXT files converted from GXT2? For example, I don't understand, why is needed numerical strings, which contains stuff like "190010190010190010190010190010190010190010190010190". And what means constructions like that?

```
ANIML_GZAI
ANIML_GZAJ
ANIML_CNAB
SFX_PAUSE_554
ANIML_AXAN
ANIML_AJAE
ANIML_FCAH
ANIML_FEAE

```

Is it empty strings or what?
## Post #13
- Username: rugaviyahu
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-04-20T18:33:39+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

Means who talking ids or whateever need tobe there!
## Post #14
- Username: tarique
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 20, 2014 12:03 am
- Post datetime: 2015-05-21T15:39:58+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

this tool is cant open pc files. is there a tool for pc .gxt2??
## Post #15
- Username: timo23
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 26, 2015 6:22 am
- Post datetime: 2015-06-25T23:13:42+00:00
- Post Title: GTA V (PS3 / XBOX) (*.GXT2)

This gxt2 tools cant open and save the global.gxt german version.

When i import my txt file german version this error is comming..

Anyone help?
[Neue Bitmap.jpg](https://xentaxbackup.github.io/file/9344_Neue Bitmap.jpg)
## Post #16
- Username: Aurora11
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 16, 2016 4:31 pm
- Post datetime: 2016-02-28T14:46:45+00:00
- Post Title: Re: GTA V (PS3 / XBOX) (*.GXT2)

I am getting Range Check Error. Any ideas how can i fix this? thanks in advice
