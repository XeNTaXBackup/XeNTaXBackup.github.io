## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-18T06:56:31+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

Hi all,

Can anyone have a look on this format please. It seems a new Unreal Engine format. I believe in there are all texts and etc.... Files are from X360 version. I would like to extract the files and of possible also repack if anyone is interest and willing to help.



I can upload it elsewhere if you like...

```
http://rapidshare.com/files/3819558021/28CCF006_LOC_INT.wad
http://www.fileserve.com/file/Wp5cHEF
http://www.sendspace.com/file/hi6t6t

```


Thank you
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-19T10:58:40+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

anyone pls ?
## Post #3
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2011-10-21T12:08:46+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

```
IDString "WWAD"
Get DUMMY long # version?
Get FILES long
Get HDR_OFFSET long
Get HDR_SIZE long
Get DATA_OFFSET long
Get DATA_SIZE long
For I = 0 < FILES
 Get FILE_HASH long
 Get FILE_SIZE long
 Get FILE_OFFSET long
 String FILE_NAME p= "%08X.bin" FILE_HASH
 Log FILE_NAME FILE_OFFSET FILE_SIZE
Next I
```

there are no filenames stored in .wad, only id/hash, so names will be like "FB567200.bin".
it seems that files extracted from your .wad are XMAs with RIFX header.
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-21T13:12:37+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

great gonna test it. Do you want some other file? Might there will be store filenames ..

EDIT: 
Checked the ISO again but there is not any file what could contains filenames 

BTW did u find any file what could containts TEXTS and fonts please ?

EDIT2:
Checked iso again and found out that there is a Folder Call SFX what contains only hashfilenames, so it is very strange.
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-21T13:43:49+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

Can you also please have a look on how to decompress/unpack the RIFX formats ? I was not able to find any readable text in this bin files.
## Post #6
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2011-10-21T14:44:19+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

rifx is a media container, with (in this case) xma encoded audio. there are threads about this type of files on this forum, use search.
it's definitely no text in this files. maybe in other wads.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-21T16:33:48+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

> Reply from Axsis
>
> rifx is a media container, with (in this case) xma encoded audio. there are threads about this type of files on this forum, use search.
it's definitely no text in this files. maybe in other wads.

Thx for help i need find text anyway.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-21T16:45:10+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

Finally find the text. Thx for help 

Can you please also have a look on this file, if you find some time?

```
http://dl.dropbox.com/u/38234344/BmGame.xxx

```


Thank you
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-22T20:17:29+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

Please anyone help with XXX files. It is Unreal engine and used on most commond games like Batman AC, Homefront, etc... It also must containts text..
## Post #10
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-10-22T21:33:12+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

If you're interested in PC version, maybe I can help you out to extract and repack texts. But only texts.

If consoles version, I can't help, cause consoles version are Big Endian and my tool doesn't works.
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-23T07:58:46+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

> Reply from Herdell
>
> If you're interested in PC version, maybe I can help you out to extract and repack texts. But only texts.

If consoles version, I can't help, cause consoles version are Big Endian and my tool doesn't works.

Thx for help, I would need it for console. Is that tool you have containts also source please ? Big Endianes is only byte reversed little endian, so it should not be that hard to revers it in my opinion, but i could be wrong. Can you please have a look up it if you can? 

Thank you
## Post #12
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2011-11-27T08:39:11+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

I need the PC text, so if you can please extract it.
## Post #13
- Username: static77
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 20, 2012 1:37 pm
- Post datetime: 2012-08-22T10:08:09+00:00
- Post Title: Batman Arkham City Wav/XXX Repacker/Unpacker

> Reply from Herdell
>
> If you're interested in PC version, maybe I can help you out to extract and repack texts. But only texts.

If consoles version, I can't help, cause consoles version are Big Endian and my tool doesn't works.
Is there any program to extract/repack texts? I would like to edit localization.
