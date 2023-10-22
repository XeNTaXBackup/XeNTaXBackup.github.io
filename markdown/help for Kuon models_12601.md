## Post #1
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2015-02-13T23:27:14+00:00
- Post Title: help for Kuon models

I want ask if its possible unpack and extract models by ps2 game Kuon ( [http://kuongame.wikia.com/wiki/Kuon_(%E ... Game_Wikia](http://kuongame.wikia.com/wiki/Kuon_%28%E4%B9%9D%E6%80%A8%29_Game_Wikia)) , the files are .irx.

in DVD the files are in attached picture here
[files.png](https://xentaxbackup.github.io/file/8661_files.png)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-02-13T23:31:48+00:00
- Post Title: help for Kuon models

irx is a dll its not that file look for a larger file.
## Post #3
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2015-02-13T23:39:57+00:00
- Post Title: help for Kuon models

maybe that models can be packed in other files of DVD too
[FILES2.png](https://xentaxbackup.github.io/file/8662_FILES2.png)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-02-14T03:30:34+00:00
- Post Title: help for Kuon models

I would say all.bnd
## Post #5
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2015-02-16T09:13:45+00:00
- Post Title: help for Kuon models

I tyed to find ways to open bnd files but no results, there are extractors to get models by bnd files ?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-02-16T12:27:57+00:00
- Post Title: help for Kuon models

think of the .bnd file as a zip file. it contains many smaller files.
I would need the first and last 10mb of the file to help you.
## Post #7
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2015-02-18T01:17:23+00:00
- Post Title: help for Kuon models

what mb you need of files ? can I send you files someway ?
## Post #8
- Username: swosho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-02-22T16:26:56+00:00
- Post Title: help for Kuon models

```
#by chrrox
#quickbms script
goto 0xC
get FILES long
savepos TMP
for i = 0 < FILES
goto TMP
get ID long
get OFFSET long
get SIZE long
get NOFF long
savepos TMP
goto NOFF
get NAME string
log NAME OFFSET SIZE
next i
```
