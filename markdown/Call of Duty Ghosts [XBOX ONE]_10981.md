## Post #1
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2013-11-23T11:12:12+00:00
- Post Title: Call of Duty: Ghosts [XBOX ONE]

Hello. With start x-one famous xbox hacker c4eva did dump image from new BD

> XG4=XboxGamedisc4 – Bluray Disc Type Identifier from PIC (Permanent Information and Control data zone) on the disc!
>
> CoD Ghosts psn layer 0 start/end: 0x 00100000/00ad7f1e (00ad7f1e-00100000) 1=9d7f1f sectors *0800=4ebf8f800 (21,138,831,360 bytes)
>
> CoD Ghosts psn layer 1 start/end: 0x 015280e0/01effffe (01effffe-015280e0) 1=9d7f1f sectors – same as layer 0 *0800=4ebf8f800 (21,138,831,360 bytes)
>
> The disc is made up of one metadata folder with some pics and one package1.xvc file of 41,285,020 KB length
package1.xvc likely encrypted. I am upload some files from metadata and part file package1.xvc 

 cod_ghosts_xbox_one.7z
(99.98 KiB) Downloaded 36 times


Anyone has any ideas how to decrypted this file?
[https://wiki.archlinux.org/index.php/xen](https://wiki.archlinux.org/index.php/xen)
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-23T14:47:31+00:00
- Post Title: Call of Duty: Ghosts [XBOX ONE]

I think this gonna be impossible without debug console but i could be wrong
## Post #3
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2013-11-23T15:57:51+00:00
- Post Title: Call of Duty: Ghosts [XBOX ONE]

> Reply from michalss
>
> I think this gonna be impossible without debug console but i could be wrong
Hello michalss  
Yes, not a simple task. Structure is not yet studied. I think need to dig in the direction Linux - XEN (is the basis for xbox one - paravirtualization, several OS on one CPU). Source code there is kernel Linux, and now i trying deal in it.
## Post #4
- Username: dezmand07
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 24, 2011 2:22 pm
- Post datetime: 2013-11-23T19:10:57+00:00
- Post Title: Call of Duty: Ghosts [XBOX ONE]

From 0х9000 to 0хDFFEF are the 214 sectors by 0xFF0 (4080 bytes) separated by a 0x10 (16 bytes null). Moreover there is another sector in the begining - from 0x7000 to 0х7FEF.
## Post #5
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2013-11-24T17:26:17+00:00
- Post Title: Call of Duty: Ghosts [XBOX ONE]

I would assume this is a new fileformat from Microsoft. As their SystemUpdates use the same container. If history proves to be right, this files are encrypted (if not fully, at least partially) and the keys has to leak from somewhere (xdk, exploit?)?
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-24T17:46:04+00:00
- Post Title: Call of Duty: Ghosts [XBOX ONE]

> Reply from peshkohacka
>
> I would assume this is a new fileformat from Microsoft. As their SystemUpdates use the same container. If history proves to be right, this files are encrypted (if not fully, at least partially) and the keys has to leak from somewhere (xdk, exploit?)?

Actually agree on this 100%. It wont be easy to crack this beast
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-24T18:21:17+00:00
- Post Title: Call of Duty: Ghosts [XBOX ONE]

This is the same as 3ds until there is a kernel exploit there wont be any way to extract this.
