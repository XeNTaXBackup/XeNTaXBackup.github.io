## Post #1
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-01-31T04:53:39+00:00
- Post Title: Help with Raven's Cry - .WD/.IDX archives !

Raven's Cry just came out on PC platform yesterday and it has the same .wd archives for textures and .idx/.idx.asncdat archives for sound data. 

I have tried extracting the archives with Two Worlds 2 tools and QuickBMS script created by Ekey but they aren't working with Raven's Cry archives   

Can anyone please recreate the quickbms script for .wd and .idx/.idx.asncdat file format of Raven's Cry for extracting and repacking archives
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-31T08:42:49+00:00
- Post Title: Help with Raven's Cry - .WD/.IDX archives !

And where samples?
## Post #3
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-01-31T10:31:25+00:00
- Post Title: Help with Raven's Cry - .WD/.IDX archives !

> Reply from Ekey
>
> And where samples?

Sorry, here are the samples :-

```
http://www.solidfiles.com/d/03eef28e51/physic.7z

.idx archive:
http://www.solidfiles.com/d/1523b7b9bb/sounddata.7z
```


Hope you make quickbms script with repack function for the two file format of the game
## Post #4
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2015-01-31T15:56:19+00:00
- Post Title: Help with Raven's Cry - .WD/.IDX archives !

for wd

```
get dirname basename
goto 0x24
get arcnamelen long
getdstring arcname arcnamelen
get dummy long
get filetablezsize long
savepos offset
clog MEMORY_FILE offset filetablezsize 0x10000000

get files long MEMORY_FILE

for i = 0 < files
get filenamelen byte MEMORY_FILE
getdstring name filenamelen MEMORY_FILE
get dummy byte MEMORY_FILE
get offset longlong MEMORY_FILE
get zsize long MEMORY_FILE
get size longlong MEMORY_FILE


set fullname = dirname
string fullname + "/"
string fullname + name
clog fullname offset zsize size
next i

```
## Post #5
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2015-01-31T16:05:04+00:00
- Post Title: Help with Raven's Cry - .WD/.IDX archives !

Sounds in OGG format (.asncdat files)
## Post #6
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-01-31T16:59:16+00:00
- Post Title: Help with Raven's Cry - .WD/.IDX archives !

Thanks, thief1987 for the help    Hope someone creates for .idx as well
## Post #7
- Username: AdrianWojnicki
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 18, 2017 9:41 pm
- Post datetime: 2017-04-01T17:51:03+00:00
- Post Title: Help with Raven's Cry - .WD/.IDX archives !

Hey. Hmmm is it possible to unpack Two Worlds 1 .wd files with QuickBMS too? Tried with Two Worlds 2 commands - not works too.

Ye I know there is a tool WdPackager - but it's impossible to run it on 64bit.

Example .wd files:

```
http://www.mediafire.com/file/mmsdzm94prh8qgy/TW1_WD_EXAMPLES.rar
```


Thank You!
