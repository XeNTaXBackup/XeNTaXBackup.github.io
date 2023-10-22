## Post #1
- Username: 194klakla
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Apr 28, 2013 1:18 pm
- Post datetime: 2013-05-20T16:00:57+00:00
- Post Title: [Help]LuaQ File

Hi, someone know how to decode this LuaQ file?
[http://www.sendspace.com/file/jw7zrn](http://www.sendspace.com/file/jw7zrn)

This is a .Lua file from the game Grand Chase, i already tried use LuaDec and another tools for LuaQ decode, but i havent sucesss.

someone can help-me with this? :/


Thanks All.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-20T22:22:28+00:00
- Post Title: [Help]LuaQ File

Try Chunkspy.lua (usage is: lua ChunkSpy.lua sameimageindex.lua -o sample.lst)

output is

```
00000C                     ** function [0] definition (level 1)
                           ** start of function **
00000C  00000000           string size (0)
                           source name: (none)
000010  00000000           line defined (0)
000014  00000000           last line defined (0)
000018  00                 nups (0)
000019  00                 numparams (0)
00001A  02                 is_vararg (2)
00001B  35                 maxstacksize (53)
                           * code:
00001C  1E140200           sizecode (136222)
000020  0A008034           [000001] newtable   0   105 0    ; array=36864, hash=0
000024  4A000001           [000002] newtable   1   2   0    ; array=2, hash=0
000028  81400000           [000003] loadk      2   1        ; 2310
00002C  C1800000           [000004] loadk      3   2        ; 2290
000030  62400001           [000005] setlist    1   2   1    ; index 1 to 2
000034  8A000001           [000006] newtable   2   2   0    ; array=2, hash=0
000038  C1C00000           [000007] loadk      3   3        ; 2940
00003C  01810000           [000008] loadk      4   2        ; 2290
...
06480C  624C0001           [102908] setlist    49  2   1    ; index 1 to 2
064810  8A0C0001           [102909] newtable   50  2   0    ; array=2, hash=0
064814  C10C5125           [102910] loadk      51  38212    ; 864340
064818  010D4F25           [102911] loadk      52  38204    ; 864220
06481C  A24C0001           [102912] setlist    50  2   1    ; index 1 to 2

```


ends up with this error message: ChunkSpy.lua:840: attempt to perform arithmetic on local 'c' (a string value)

edit: ok, the output doesn't fit. might be a matter of wrong codepage/charset?
## Post #3
- Username: 194klakla
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Apr 28, 2013 1:18 pm
- Post datetime: 2013-05-21T02:23:15+00:00
- Post Title: [Help]LuaQ File

Thanks, but...
here the same file (but much more older) without Lua5 compress:
[http://www.sendspace.com/file/34kvm9](http://www.sendspace.com/file/34kvm9)


I really need of the new sameimageindex becuase have a lot new strings :/


Thanks again.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-21T11:50:12+00:00
- Post Title: [Help]LuaQ File

Did you try ChunkSpy?

(The decompiled result in my previous post might be wrong only because of my not fitting codepage.)
## Post #5
- Username: 194klakla
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Apr 28, 2013 1:18 pm
- Post datetime: 2013-05-21T18:22:18+00:00
- Post Title: [Help]LuaQ File

Yes, i tried.
But the chunkspy generate a new file in blank

=/
