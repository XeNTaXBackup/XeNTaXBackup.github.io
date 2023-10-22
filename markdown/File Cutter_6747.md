## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-08T00:58:00+00:00
- Post Title: File Cutter

if you need a filecutter for uploading a small sample of your big archives and files you can use the following script for quickbms that creates 2 files of 1 megabyte each one:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get SIZE asize
math CHUNKSZ = 0x100000
if SIZE <= CHUNKSZ
    cleanexit
endif

math OFFSET = 0
get NAME filename
string NAME += "_"
string NAME += OFFSET
string NAME += "_"
string NAME += SIZE
log NAME OFFSET CHUNKSZ

math OFFSET = SIZE
math OFFSET -= CHUNKSZ
get NAME filename
string NAME += "_"
string NAME += OFFSET
string NAME += "_"
string NAME += SIZE
log NAME OFFSET CHUNKSZ
```

I guess the moderators would like to put it sticky or add it to the help page because many users reported problems with the other existent file cutters so I'm sure this solution will avoid any problem.

let me know any suggestion or improvement
## Post #2
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-12-13T21:06:45+00:00
- Post Title: File Cutter

Or you can use the old FileCutter tool, you can find in the rules, or here.
[FileCutter.zip](https://xentaxbackup.github.io/file/4894_FileCutter.zip)
## Post #3
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-12-18T10:05:59+00:00
- Post Title: File Cutter

FileCutterComplete.zip
(289.67 KiB) Downloaded 136 times



Try this one if the above doesn't work.
## Post #4
- Username: ZanderPander777
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 28, 2019 11:26 pm
- Post datetime: 2019-05-28T15:36:39+00:00
- Post Title: File Cutter

neither of them work
