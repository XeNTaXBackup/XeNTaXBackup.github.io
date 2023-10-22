## Post #1
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-01-15T20:03:48+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

Tales of the tools
=============

A bunch of tools for different file formats of the "Tales of" franchise.

See source and file format specs:
[Tales of the tools](http://www.github.com/0xFAIL/Tales-of-the-Tools)



Supported games:

Tales of Symphonia
[DAT_split](https://github.com/0xFAIL/Tales-of-the-Tools/downloads)
Tales of Xillia (currently only one file format description)
Tales of the World: Radiant Mythology
ARC extractor
Viewers for DGN, TXL, NOD, PPT (unfinished)
Viewer for EZTEXT files

Will update this post as changes happen. For a TODO list see the repository itself and click on the TODO file. (will be opened in the browser)

You can participate too (see the DOC folders of the tools for an example)
the repository is open to everybody.

Edit: Bonus l in the link removed, thanks evin.
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-01-16T08:43:23+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

Error 404

At the end of the link is a bonus "l": Tales-of-the-Toolsl
## Post #3
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-02-03T11:22:47+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

Added new tools and executables

-New project DAT_split
-Executables for EZBIND_extract, EZTEXT_extract and DAT_split
## Post #4
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2012-02-24T19:02:49+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

I checked out your tool and got some ppt and an mdl file. How do I convert these to something that Noesis or Blender can open?

Thanks.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-24T22:37:06+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

I would like some tales models.
## Post #6
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2012-02-25T02:53:00+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

Here.  
Link Removed
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T03:24:13+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

That one uses a chunk-based format.
That should be enough to parse the entire file.

The chunk size includes the chunk ID as well as the size.

Starts with the header chunk with ID "MDL\x00" of 44 bytes, followed by numeric chunk ID's. Header includes counts like bone count, mesh count, and whatever other counts.

1 don't know
2 don't know
3 contains a bunch of bone structs
256 is likely the meshes, and may contain sub chunks.

Is it Tales of the World? (based on ezbind tag from the docs)
## Post #8
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2012-02-25T06:09:25+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

Yes, they are from the first Tales of the World game.

EDIT: So how am I suppose to use the information you provided? I know little to nothing about hex editing.  

P.S. I have HxD hex editor.
## Post #9
- Username: StorMyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 21, 2011 6:35 pm
- Post datetime: 2012-04-07T00:35:41+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

Quick question since you happen to have worked a lot on ToS PS2, do you happen to know where the 3D files are ?
I'm still not good with that so...
## Post #10
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-01-03T03:37:24+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

Anyone have the links to these? There is only the source and I have no idea how to compile. I need to tools for Tales of the World Radiant Mythology 3.
## Post #11
- Username: sidhi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 10, 2013 11:35 pm
- Post datetime: 2013-05-12T22:25:14+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

> Reply from 0xFAIL
>
> Tales of the tools
=============

A bunch of tools for different file formats of the "Tales of" franchise.

See source and file format specs:
Tales of the tools



Supported games:

Tales of Symphonia
DAT_split
Tales of Xillia (currently only one file format description)
Tales of the World: Radiant Mythology
ARC extractor
Viewers for DGN, TXL, NOD, PPT (unfinished)
Viewer for EZTEXT files

Will update this post as changes happen. For a TODO list see the repository itself and click on the TODO file. (will be opened in the browser)

You can participate too (see the DOC folders of the tools for an example)
the repository is open to everybody.

Edit: Bonus l in the link removed, thanks evin.

Your links from github are down.... 

But I use git from your repo : 
```
git clone https://github.com/0xFAIL/reverse-engineering.git
```


Does all of the tales "rb scripts" in there ? 

Can I build it with ORCA (One Click Ruby Application) ?
## Post #12
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-06-25T04:31:15+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

The link for the .arc extractor doesn't work, and i cant find it on your account. The current script that I have doesn't work, it keeps giving me this error. Could I possibly have the one that you had posted here?
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-06-25T17:38:38+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

> Reply from anime663
>
> The link for the .arc extractor doesn't work, and i cant find it on your account...
[http://www.mechanical.co.at/0xFAIL/file ... index.html](http://www.mechanical.co.at/0xFAIL/files/packages/index.html)
[https://github.com/0xFAIL/reverse-engin ... logy%201-3](https://github.com/0xFAIL/reverse-engineering/tree/master/tools/Tales%20of%20the%20World%20Radiant%20Mythology%201-3)
## Post #14
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-06-25T18:09:11+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

> Reply from AceWell
>
> 
http://www.mechanical.co.at/0xFAIL/file ... index.html
https://github.com/0xFAIL/reverse-engin ... logy%201-3

Thank you!
## Post #15
- Username: sieghartx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 08, 2015 4:15 pm
- Post datetime: 2015-12-08T08:19:17+00:00
- Post Title: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

> Reply from 0xFAIL
>
> Tales of the tools
=============

A bunch of tools for different file formats of the "Tales of" franchise.

See source and file format specs:
Tales of the tools



Supported games:

Tales of Symphonia
DAT_split
Tales of Xillia (currently only one file format description)
Tales of the World: Radiant Mythology
ARC extractor
Viewers for DGN, TXL, NOD, PPT (unfinished)
Viewer for EZTEXT files

all link is down. including the one posted by 2 post above me..
## Post #16
- Username: weirdalsuperfan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 23, 2019 5:54 pm
- Post datetime: 2019-07-01T18:23:55+00:00
- Post Title: Re: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

So are these tools just gone forever...?
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2023-05-16T03:06:14+00:00
- Post Title: Re: [PS2/3, PSP, GC, XBox 360] "Tales of" the tools

close as i could get to these tools again   
[https://web.archive.org/web/20130514200 ... ngineering](https://web.archive.org/web/20130514200045/https://github.com/0xFAIL/reverse-engineering)
[https://web.archive.org/web/20150710010 ... ls?slide=1](https://web.archive.org/web/20150710010038/https://github.com/0xFAIL/reverse-engineering/tree/master/tools?slide=1)
