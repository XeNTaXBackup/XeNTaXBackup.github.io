## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-07T23:07:23+00:00
- Post Title: Shin Megami Tensei Nocturne compression

I attached a sample file.
[f201_001.7z](https://xentaxbackup.github.io/file/8050_f201_001.7z)
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-11-08T00:06:44+00:00
- Post Title: Shin Megami Tensei Nocturne compression

Doesn't seem compressed. Inside your .7z it's compressed about 1.5:1. It looks most like a mesh. What game is it from?
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-08T11:17:12+00:00
- Post Title: Shin Megami Tensei Nocturne compression

> Reply from GMMan
>
> Doesn't seem compressed. Inside your .7z it's compressed about 1.5:1. It looks most like a mesh. What game is it from?
Shin Megami Tensei Nocturne.
It is compressed apparently, since there's a leftover txt file containing this:

```
f201_001.TBN
f201_001.f2
f201_001.f1

```

But as you said, it's not very well compressed since you can see repeating structures in the file. Maybe it's partially compressed?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-08T12:37:01+00:00
- Post Title: Shin Megami Tensei Nocturne compression

can you post a bunch of small samples need more to see the file structure.
## Post #5
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-08T15:58:03+00:00
- Post Title: Shin Megami Tensei Nocturne compression

> Reply from chrrox
>
> can you post a bunch of small samples need more to see the file structure.
Here ya go, all of the files kinda follow the same structure it seems (not the f1 and f2 files, they're for stage models), except that the LB files seem compressed.
[http://puu.sh/cIfFd.7z](http://puu.sh/cIfFd.7z)
## Post #6
- Username: TGE
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-08T16:49:37+00:00
- Post Title: Shin Megami Tensei Nocturne compression

well quickbms does not find anything that i can see in its currently supported formats.
but the structure is pretty strait forward

01 01 - always this version?
XX XX file id
YY YY YY YY - zip size including header
qq qq qq qq - file extension
zz zz zz zz - uncompressed size

then the data follows.
the data gets aligned after that and then it repeats till you read this
FF 00 00 00 
10 00 00 00 
45 4E 44 30 END0
00 00 00 00
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-09T02:10:11+00:00
- Post Title: Shin Megami Tensei Nocturne compression

if there are only a few models you want you can dump them easily from saved states.

[http://ps23dformat.wikispaces.com/Shin+ ... i+Nocturne](http://ps23dformat.wikispaces.com/Shin+Megami+Tensei+Nocturne)
## Post #8
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-09T12:40:30+00:00
- Post Title: Shin Megami Tensei Nocturne compression

> Reply from chrrox
>
> if there are only a few models you want you can dump them easily from saved states.

http://ps23dformat.wikispaces.com/Shin+ ... i+Nocturne
That ripper doesn't dump even 1 complete mesh. Been working on writing one in MaxScript myself but some of these mesh types seem non-standard.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-09T13:37:33+00:00
- Post Title: Shin Megami Tensei Nocturne compression

If you post the memory dump and what it is a scene of i can help the format look standard for ps2.
## Post #10
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-09T15:15:16+00:00
- Post Title: Shin Megami Tensei Nocturne compression

> Reply from chrrox
>
> If you post the memory dump and what it is a scene of i can help the format look standard for ps2.
Most files aren't compressed actually, only the LB files are.
I'll post some things for you to look at, not everything was documented by me so it might be confusing to read.
For example Flag 7 meshes seem to use some special way of handling the face index.
[http://puu.sh/cJB7e.7z](http://puu.sh/cJB7e.7z)
[PIB dev.7z](https://xentaxbackup.github.io/file/8057_PIB dev.7z)
## Post #11
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-27T01:07:13+00:00
- Post Title: Shin Megami Tensei Nocturne compression

Apparently the original japanese release of the game doesn't have some files compressed.
I figure that these 2 files are identical except one is compressed + extra header and the other isn't.
[http://puu.sh/d6YND.7z](http://puu.sh/d6YND.7z)
## Post #12
- Username: TGE
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-27T02:44:33+00:00
- Post Title: Shin Megami Tensei Nocturne compression

well you should be able to get any decompressed file you want with memory dumps.
[http://www21.big.or.jp/~dram/cheatcode/ps2_smt3.html](http://www21.big.or.jp/~dram/cheatcode/ps2_smt3.html)
Just use gameshark to get the debug console and then use the model viewer.
I tried quickbms and it did not return any results decompression these files.

I found this tool that claims to be an archive extractor.
[dds3ext01.zip](https://xentaxbackup.github.io/file/8147_dds3ext01.zip)
