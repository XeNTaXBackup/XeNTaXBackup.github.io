## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-17T19:35:24+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-17T20:05:50+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

Really interesting! The seem to use xmbs like Ensemble Studios.  Gotta investigate this further.
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-17T21:09:27+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

Founded tool for extracting files 
[GRAWbundle-readerv1.0.zip](https://xentaxbackup.github.io/file/1273_GRAWbundle-readerv1.0.zip)
## Post #4
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-19T10:54:09+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

Tool crashes for me when i select some file 

Already finished my own tool and its works perfect  but I want to code packing abilities for it, so it will be available soon on my blog
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-20T18:33:23+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

Could you upload some of those xmbs and xmls?
Would be really interesting to have a look at them.

Edit: With some I mean as much as possible
## Post #6
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-07-20T22:02:36+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

> Reply from itg
>
> Tool crashes for me when i select some file 

Already finished my own tool and its works perfect  but I want to code packing abilities for it, so it will be available soon on my blog

Do you think you can write a tool for ubisofts SS0 files or any SS with a number after them?
## Post #7
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-21T05:33:56+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

itg - Where i can download  ?
## Post #8
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-22T17:37:41+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

Just back from the weekend vacation   

I'll continue coding asap.
## Post #9
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-22T21:51:25+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

itg - Waiting release
## Post #10
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-23T10:50:23+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

> Reply from KorNet
>
> itg - Waiting release

Check my blog 

I have tested tool on patch.bundle, and game works good after repack 
If some one will test it on quick.bundle let me know
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-23T11:11:33+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

Could you also post the format specifications for bundle files?
## Post #12
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-23T13:14:05+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

> Reply from Rheini
>
> Could you also post the format specifications for bundle files?

No, what for?
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-23T15:30:18+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

> Reply from itg
>
> Rheini wrote:Could you also post the format specifications for bundle files?
No, what for?
To contribute to the accumulated format knowledge and keep other tool designers from reinventing the wheel?
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-23T17:58:19+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

> Reply from itg
>
> Rheini wrote:Could you also post the format specifications for bundle files?

No, what for?

Because this site is about sharing knowledge?
## Post #15
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-24T21:07:29+00:00
- Post Title: Ghost Recon Advanced Warfighter 2 *.bundle

I hope I wrote understandable 

```

///
/// Header
///

DWORD: Header		//BNDL
DWORD: Version		//0x02
ULONG: TOC size		//0x021F6

///
/// TOC markers
///

01 - file name
0101 - dir
02 - file info
03 - move to parent dir


00000010 0101 6461 7461 0001 0161 6E69 6D73 0001 ..data...anims..
00000020 0167 686F 7374 0002 FCBD 1C02 0000 0000 .ghost..........
00000030 823D 7000 0167 686F 7374 5F6D 6163 6869 .=p..ghost_machi
00000040 6E65 2E78 6D62 00                       ne.xmb.         

string		filename = data/anims/ghost/ghost_machine.xmb
ulong		offset = 0x021cbdfc
DWORD		filesize = 0x0703D82


000001C5 0301 0167 7569 0002 308A 2E01 0000 0000 ...gui..0.......
000001D5 52D7 0200 0161 6C65 7274 2E78 6D62 00   R....alert.xmb. 

03 0101 - go to the parent dir and enter gui

string		filename = data/gui/ghost_machine.xmb
ulong		offset = 0x012E8A30
DWORD		filesize = 0x02D752
```
## Post #16
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-24T21:18:51+00:00
- Post Title: 

Thank you 
Clearly understandable.
