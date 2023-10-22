## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-04T10:16:19+00:00
- Post Title: VBS2 / Jcove

before someone asks, I have added support into my [pbo.bms script](http://aluigi.org/papers/bms/pbo.bms) for the encrypted xbo archives used in the game Jcove lite (VBS2 engine).
all these "*bo" archives are used in the games developed by Bohemia Interactive like the ArmA series.

the only thing I still need to implement is support for the compressed files but in all the archives I have seen (arma/arma2 and some of jcove) I have never found them, so if someone has one of them (easy to see because the script will report an error if one file is compressed) I can add this feature too
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-04T16:11:19+00:00
- Post Title: VBS2 / Jcove

after a better search seems that the pbo archives use lzss, so I have updated the script
## Post #3
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-21T20:43:53+00:00
- Post Title: VBS2 / Jcove

Is there a way to get them back to .xbo?
I can pbo them but engine will not read them unless they are encrypted to .xbo.
## Post #4
- Username: rstratton
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 03, 2010 1:47 pm
- Post datetime: 2010-02-22T03:56:26+00:00
- Post Title: VBS2 / Jcove

> Reply from Maddog
>
> Is there a way to get them back to .xbo?
I can pbo them but engine will not read them unless they are encrypted to .xbo.
yes creating .xbo is possible with makepbo and depbo from here
[http://dev-heaven.net/projects/mikero-pbodll/files](http://dev-heaven.net/projects/mikero-pbodll/files)

depbo is a dll file used by all of mikero's tools
## Post #5
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-22T15:51:28+00:00
- Post Title: VBS2 / Jcove

rstratton thanks for tip.
I'm using his tools but didn't know that Mikero went so far with his dll, supporting xbos.
I tried making xbo with latest DePbo.dll but it fails somehow.
