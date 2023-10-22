## Post #1
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2007-05-20T16:33:41+00:00
- Post Title: Lost Planet (PC) unpacker

Hi
Does anybody know about unpacker for Lost Planet game (PC version)?

Developer: Capcom
Demo is avaiable here:

```
http://www.gamespot.com/news/6170818.html
```


There are several .arc files - 35 MB to 90 MB
Screen included

Besides of it, there are several other files like 
.tex - probably textures
.msg - texts from game

Is any tool for these files too?
[LOST_PLANET.jpg](https://xentaxbackup.github.io/file/1169_LOST_PLANET.jpg)
## Post #2
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-05-20T17:05:46+00:00
- Post Title: Lost Planet (PC) unpacker

yes, I looked at .arc format, quite simple to understand, it packed with zlib.
Ill make tool soon for it.
Here is example of file format.

If someone figure out "unknown1" value, let me know 
[lp.arc.gif](https://xentaxbackup.github.io/file/1170_lp.arc.gif)
## Post #3
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2007-05-24T19:41:01+00:00
- Post Title: Lost Planet (PC) unpacker

Great job....

Thanks you much
Your tool works fine...
## Post #4
- Username: nerdcore
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 03, 2007 6:24 pm
- Post datetime: 2007-05-26T06:31:47+00:00
- Post Title: Lost Planet (PC) unpacker

here is a simple in VB written extractor to extract those arc files, its not made by me.
and its not an decompressor.

you can use some zlib tools to decompress the extracted files

btw: unk1 means the filetype (extension)
[LP_ARC_extract.rar](https://xentaxbackup.github.io/file/1188_LP_ARC_extract.rar)
## Post #5
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-05-26T16:12:30+00:00
- Post Title: Lost Planet (PC) unpacker

> Reply from nerdcore
>
> here is a simple in VB written extractor to extract those arc files, its not made by me.
and its not an decompressor.

you can use some zlib tools to decompress the extracted files

btw: unk1 means the filetype (extension)

ye I was thinking about that, but its some hash of extension need to know hash table of all extensions.
## Post #6
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-06-30T01:43:29+00:00
- Post Title: Lost Planet (PC) unpacker

How do i extract the music files?
