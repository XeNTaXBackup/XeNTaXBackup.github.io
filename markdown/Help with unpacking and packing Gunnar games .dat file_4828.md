## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-07-31T05:24:34+00:00
- Post Title: Help with unpacking and packing Gunnar games .dat file

I want to unpack Hidden Mysteries: The Fateful Voyage - Titanic 's .dat files.
I have looked this thread 
[viewtopic.php?f=10&t=3423](http://forum.xentax.com/viewtopic.php?f=10&t=3423)
But the file format is a bit different. Any one can make a unpacker and packer for it?
Attach file is a sample,and the Gunnar games's game list is here.
Thanks.
[http://www.mobygames.com/browse/games/g ... ist-games/](http://www.mobygames.com/browse/games/gunnar-games-inc/developed-by/list-games/)
[text.rar](https://xentaxbackup.github.io/file/3278_text.rar)
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-07-31T08:25:43+00:00
- Post Title: Help with unpacking and packing Gunnar games .dat file

Here 's a QuickBMS script for the 'text.dat' file:

```
# script created by The Bacter
get FILES long
getdstring DUMMY 0x1C
for i = 0 < FILES
    getdstring NAME 0x100
    get OFFSET long
    get SIZEX long              # size aligned to 0x20 boundary
    get SIZE long
    getdstring DUMMY 0x14
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-07-31T14:16:01+00:00
- Post Title: Help with unpacking and packing Gunnar games .dat file

Very thanks , unpack successfully.
But i tested, i think this game need a packer for repacking the .dat file.
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-07-31T16:13:20+00:00
- Post Title: Help with unpacking and packing Gunnar games .dat file

Here is a simple .DAT Maker+Extractor+Replacer util. Test version!
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-08-01T03:19:11+00:00
- Post Title: Help with unpacking and packing Gunnar games .dat file

Very thanks!
Now i can translate it into chinese.
[titanic.JPG](https://xentaxbackup.github.io/file/3286_titanic.JPG)
## Post #6
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2011-01-14T01:10:12+00:00
- Post Title: Help with unpacking and packing Gunnar games .dat file

Hi,bacter

Can you make a update for game Elizabeth Find MD - Diagnosis Mystery?
## Post #7
- Username: xyu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 15, 2014 10:29 pm
- Post datetime: 2021-12-10T01:05:05+00:00
- Post Title: Help with unpacking and packing Gunnar games .dat file

> Reply from bacter ↑Sun Aug 01, 2010 12:13 am at Sun Aug 01, 2010 12:13 am
>
> 
Here is a simple .DAT Maker+Extractor+Replacer util. Test version!

Any chance to reupload a packer tool?
