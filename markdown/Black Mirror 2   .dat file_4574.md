## Post #1
- Username: SCGame
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Jul 13, 2009 8:41 am
- Post datetime: 2010-06-08T03:33:47+00:00
- Post Title: Black Mirror 2   .dat file

There is a sample
please help, thanks
[cursor2.rar](https://xentaxbackup.github.io/file/3120_cursor2.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-08T08:01:57+00:00
- Post Title: Black Mirror 2   .dat file

script for [QuickBMS](http://aluigi.org/quickbms):

```
for OFFSET = 0 < DAT_SIZE
    get NAMESZ long
    if NAMESZ == 0
        cleanexit
    endif
    getdstring NAME NAMESZ
    get SIZE long
    savepos OFFSET
    log NAME OFFSET SIZE
    math SIZE += 20
    math OFFSET += SIZE
    goto OFFSET
next
```
note that the last part of the file (from 0x50123) is composed by some info like some text and the dds image of a pointer that will not be extracted because don't follow the general file format of the rest of the archive
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-06-14T22:55:27+00:00
- Post Title: Black Mirror 2   .dat file

^ While this script works on a sample SCGame provided, it doesn't work with other DAT files which contain main graphic data such as backgrounds. 

For example Ruins.dat, it extracts a "Ruins" file from it without any extension and that's all. The resulting file is slightly smaller in size. No subfolders or TGA files like it did for a sample cursor2.DAT. Though it can be seen via Hex editor that there are some TGA files inside. Maybe some further extraction method can be applied? 

Here's a Ruins.DAT file 
[https://mega.co.nz/#!jIkAyRLK!lNjPFcyFt ... UHicSY-Ru0](https://mega.co.nz/#!jIkAyRLK!lNjPFcyFtiv_CVV_GF2A9pEkbMbFjmiQOUHicSY-Ru0)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-23T10:06:37+00:00
- Post Title: Black Mirror 2   .dat file

> Reply from MiLØ
>
> Though it can be seen via Hex editor that there are some TGA files inside. Maybe some further extraction method can be applied?Maybe. But who will?
There are only 32x .tga strings contained but a whole bunch of "dds".

I checked the one at 0x1C80E up to 0x21C891:



ruins.JPG (118.2 KiB) Viewed 92 times
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-06-23T13:38:22+00:00
- Post Title: Black Mirror 2   .dat file

man this game is old but this is great news i would love to see this game cracked open
## Post #6
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-06-27T20:55:22+00:00
- Post Title: Black Mirror 2   .dat file

> Reply from shakotay2
>
> There are only 32x .tga strings contained but a whole bunch of "dds".

I checked the one at 0x1C80E up to 0x21C891
This went right over my head, no idea what it means  
But kudos to you for achieving that result... with whatever you did.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-28T06:33:16+00:00
- Post Title: Black Mirror 2   .dat file

> Reply from MiLØ
>
> This went right over my head, no idea what it meansThe mentioned data block has to be exported as a binary file and named as anyname.dds. Just simple as this.
