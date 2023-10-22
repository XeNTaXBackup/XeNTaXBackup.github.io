## Post #1
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-08-08T19:15:31+00:00
- Post Title: Codename: Panzer Cold War [PC] *.bin

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: maluc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 08, 2010 1:03 pm
- Post datetime: 2010-08-08T21:27:11+00:00
- Post Title: Codename: Panzer Cold War [PC] *.bin

Wrong file?
No archive.
isxbb.dll
Cut "idska32...&}zlb.".
## Post #3
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-08-08T23:47:13+00:00
- Post Title: Codename: Panzer Cold War [PC] *.bin

Oops forgot to post that this is the first 1mb of a 1.5gb file
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-09T03:57:07+00:00
- Post Title: Codename: Panzer Cold War [PC] *.bin

That's an Inno Setup package file. There must be a  setup.exe file with that .bin file!
So you have two chance:
- The usual way: run the setup.exe
- The other way: download and use the Inno Setup Unpacker from this place: [http://innounp.sourceforge.net/](http://innounp.sourceforge.net/)
## Post #5
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-08-09T10:42:02+00:00
- Post Title: Codename: Panzer Cold War [PC] *.bin

I installed the files and found a quickbms script that extracts the .pak files. Thanks aluigi;).

For anyone else here it is:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

filerot 0xbd

goto -4
get VER long
goto -8
get INFO_SIZE long
goto -12
get FILES long

get INFO_OFF asize
math INFO_OFF -= 8
math INFO_OFF -= INFO_SIZE
goto INFO_OFF

get FOLDERS long
for j = 0 < FOLDERS
    get NAMESZ short
    getdstring NAME NAMESZ
    get FILES long

    for i = 0 < FILES
        get NAMESZ short
        getdstring NAME NAMESZ
        get OFFSET long
        get DUMMY long
        get ZSIZE long
        get TYPE long
        getdstring TIMESTAMP 8
        get SIZE long

        if TYPE == 1
            log NAME OFFSET SIZE
        elif TYPE == 2
            clog NAME OFFSET ZSIZE SIZE
        elif TYPE == 3
            # nothing, it's a folder
        else
            print "unknown type %TYPE%"
            cleanexit
        endif
    next i
next j

```
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-08-09T10:45:13+00:00
- Post Title: Codename: Panzer Cold War [PC] *.bin

You can also use Universal Extractor for unpacking various installers
[http://legroom.net/software/uniextract](http://legroom.net/software/uniextract)
