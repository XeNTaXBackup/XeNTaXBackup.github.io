## Post #1
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-12-17T22:10:32+00:00
- Post Title: QuickBMS help

How would I copy the contents of MEMORY_FILE to a file on disk ("decompressed.dat")?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-18T00:12:02+00:00
- Post Title: QuickBMS help

log NAME 0 SIZE MEMORY_FILE
## Post #3
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-12-18T00:22:02+00:00
- Post Title: QuickBMS help

> Reply from chrrox
>
> log NAME 0 SIZE MEMORY_FILE
How would I get the total size of MEMORY_FILE?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-18T03:07:46+00:00
- Post Title: QuickBMS help

get size asize 1
or whatever number the memory file is.
why not just post your script and the file?
but you should already have the size of the memory file when you put it there int he first place.
## Post #5
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-12-18T03:38:12+00:00
- Post Title: QuickBMS help

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-18T12:37:36+00:00
- Post Title: QuickBMS help

i don't see any names in the file if you want a much easier way to extract them use offzip
here are the commands
for a single file output do
offzip.exe -a -1 c:\file.zlib c:\outFolder 0x0
for each zlib piece seperate
offzip.exe -a -c:\file.zlib c:\outFolder 0x0
## Post #7
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-12-18T21:01:59+00:00
- Post Title: QuickBMS help

> Reply from chrrox
>
> i don't see any names in the file if you want a much easier way to extract them use offzip
here are the commands
for a single file output do
offzip.exe -a -1 c:\file.zlib c:\outFolder 0x0
for each zlib piece seperate
offzip.exe -a -c:\file.zlib c:\outFolder 0x0
ah, forgot about offzip. thanks
