## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-26T02:56:45+00:00
- Post Title: (PS3) FolkLore

Here is a bms script to extract the bin files.

```
endian big
open FDDE fht_ 0
open FDDE bin_ 1
get files asize
math files / 0x28
for i = 0 < files
getdstring name 0x20
get size long
get offset long
log name offset size 1
next i


```
## Post #2
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2010-10-30T10:02:12+00:00
- Post Title: (PS3) FolkLore

Any sample file?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-30T12:31:21+00:00
- Post Title: (PS3) FolkLore

i am not asking for help i am posting the extractor why would i post a sample file?
## Post #4
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2010-10-31T11:53:54+00:00
- Post Title: (PS3) FolkLore

> Reply from chrrox
>
> i am not asking for help i am posting the extractor why would i post a sample file?

Sorry, I misanderstood your intentions, I though that you wanted an help to convert the extracted game models...
Anyway thanks for the script.....mybe I work too much with my wild imagination.....ehehe  ....bye bye chrrox
