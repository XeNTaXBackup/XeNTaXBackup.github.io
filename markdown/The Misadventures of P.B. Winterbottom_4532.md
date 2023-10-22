## Post #1
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2010-05-30T16:21:54+00:00
- Post Title: The Misadventures of P.B. Winterbottom

Hello

Can someone make unpacker for this game?

Here is a sample: [http://www.multiupload.com/Y6IVBGPA54](http://www.multiupload.com/Y6IVBGPA54)
And filelist:[http://viewer.zoho.com/docs/waTan](http://viewer.zoho.com/docs/waTan)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T20:34:31+00:00
- Post Title: The Misadventures of P.B. Winterbottom

Rapidshare is forbidden here. Read the rules.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-30T20:37:48+00:00
- Post Title: The Misadventures of P.B. Winterbottom

script for QuickBMS:

```
get MAXOFF asize
for
    savepos MYOFF
    if MYOFF >= MAXOFF
        cleanexit
    endif

    get FILENUM long
    get SIZE long
    get PACKNUM long
    get OFFSET long
    get NAMESZ long
    getdstring NAME NAMESZ

    set PACKNAME string PACKNUM
    string PACKNAME += ".tock"
    open FDSE PACKNAME 1
    log NAME OFFSET SIZE 1
next
```
