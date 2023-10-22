## Post #1
- Username: IIVEnnEII
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 03, 2009 7:27 pm
- Post datetime: 2009-05-02T21:14:49+00:00
- Post Title: [Xbox 360]Tom Clancy´s HAWX - filelist.lst

HeyHo

Its me again ...
I allready talked to Silver about my Problem, but we found no solution for my problem ...

OK, there are 2 files I need to work with.
"bigfile.bin" - Where are all files stored in. No compression, no Header. Only the files.
"filelist.lst" - This is the FileTable for "bigfile.bin".
That is the format I found out till now:

```
Unknown - int[2]
Unknown - int[2]
FileName - (NullTerminated)String[]
```


Here an example:

```
4F F6 E8 E4 00 00 14 3F 57 69 6E 67 20 6C 65 61 64 65 72 2E 70 6E 67 00                  O......?Wing leader.png.
```


I open "bigfile.bin", go to Offset 4ff6e8e4 and there it is, a normal PNG file.
I try to select the Block-Length 143f but it just select about the half of the file.
The Actual Length is 3032.

So ... someone got a idea ?

Here the filelist.lst:
[DOWNLOAD](http://www.nit.rogeno.us/images/filelist.lst)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-02T21:47:09+00:00
- Post Title: [Xbox 360]Tom Clancy´s HAWX - filelist.lst

can you post the first and last 10mb or so of the file.
If the files are not compressed or anything you can use jaeder naub to extract them.
## Post #3
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-05-03T07:04:39+00:00
- Post Title: [Xbox 360]Tom Clancy´s HAWX - filelist.lst

Already worked this out awhile ago.

[http://svn.slurm.us/public/hawx/trunk/G ... xtractBig/](http://svn.slurm.us/public/hawx/trunk/Gibbed.Firehawk.ExtractBig/)
## Post #4
- Username: IIVEnnEII
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 03, 2009 7:27 pm
- Post datetime: 2009-05-03T09:01:15+00:00
- Post Title: [Xbox 360]Tom Clancy´s HAWX - filelist.lst

Damn xP
Ok, thank you.

Looks like I dont have to work on this.
