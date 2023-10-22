## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-25T19:45:07+00:00
- Post Title: Milestone MIX files extractor with SBK X Superbike World Cha

I tried to use this tool with SBK X Superbike World Championship, but i gives an error when i try to unpack:

> Milestone MIX files extractor 0.1.2
>
> by Luigi Auriemma
>
> e-mail: aluigi@autistici.org
>
> web:    aluigi.org
>
> 
>
> - open MUSIC.MIX
>
> 
>
>   offset   zipsize  filesize filename
>
> ---------------------------------------
>
>   00000020 0000025d 0000207c MUSIC\JUKEBOX.BML
>
> 
>
> Error: wrong lzw output size (75 instead of 8316)
I atttach a small sample file
[MUSIC.rar](https://xentaxbackup.github.io/file/3071_MUSIC.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-25T20:35:31+00:00
- Post Title: Milestone MIX files extractor with SBK X Superbike World Cha

seems they have simply replaced lzw with deflate.
can you upload a full file? one of those small
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-25T22:23:55+00:00
- Post Title: Milestone MIX files extractor with SBK X Superbike World Cha

Sure, no problem, here is a big file
[PADDOCK_SHOW.rar - 16.72MB](http://www.zshare.net/download/76512202bf416978/)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-26T08:20:36+00:00
- Post Title: Milestone MIX files extractor with SBK X Superbike World Cha

released the new msmixet tool:
[http://aluigi.org/papers.htm#msmixext](http://aluigi.org/papers.htm#msmixext)
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-26T12:07:37+00:00
- Post Title: Milestone MIX files extractor with SBK X Superbike World Cha

Thanks!! the decompression works like a charm!!
## Post #6
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-06-03T00:16:21+00:00
- Post Title: Milestone MIX files extractor with SBK X Superbike World Cha

And repack?
I would create MODs but the engine does not read the files from the extracted folder.
## Post #7
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2015-05-10T13:46:20+00:00
- Post Title: Milestone MIX files extractor with SBK X Superbike World Cha

Is anyone else having issues extracting RIDE\Bikes\procirc.mix?
I get msmixext.exe has stopped working

> Problem signature:
>
>   Problem Event Name:	APPCRASH
>
>   Application Name:	msmixext.exe
>
>   Application Version:	0.0.0.0
>
>   Application Timestamp:	4fbaadce
>
>   Fault Module Name:	StackHash_9b42
>
>   Fault Module Version:	0.0.0.0
>
>   Fault Module Timestamp:	00000000
>
>   Exception Code:	c0000005
>
>   Exception Offset:	ffffffff
>
>   OS Version:	6.1.7601.2.1.0.256.48
>
>   Locale ID:	1033
>
>   Additional Information 1:	9b42
>
>   Additional Information 2:	9b42de1f7d76d3a52b54558271dd0da7
>
>   Additional Information 3:	fea6
>
>   Additional Information 4:	fea6605e54a7cc58404fd8dcbca77e1e

Other files work fine.
