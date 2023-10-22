## Post #1
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2011-11-08T19:39:35+00:00
- Post Title: The Godfather(.Str)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2011-11-23T15:12:52+00:00
- Post Title: The Godfather(.Str)

Anybody??
## Post #3
- Username: Layer
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Feb 19, 2011 5:53 am
- Post datetime: 2011-11-23T15:26:31+00:00
- Post Title: The Godfather(.Str)

Have you tried AphaTwentyThree's QuickBMS script to extract .xa from .str ?

```
get FSIZE asize
set OFFSET 0
append
DO
   set IDENT OFFSET
   math IDENT += 0x12
   goto IDENT
   get DAT byte
   if DAT == 100 # audio marker
      log MEMORY_FILE OFFSET 0x930
   endif
   math OFFSET += 0x930
WHILE OFFSET < FSIZE
get SIZE asize MEMORY_FILE
set RIFFSIZE SIZE
math RIFFSIZE -= 8
set DSIZE SIZE
math DSIZE -= 0x2c
putVarChr MEMORY_FILE 0x04 RIFFSIZE long
putVarChr MEMORY_FILE 0x28 DSIZE long
get NAME basename
string NAME += ".xa"

log NAME 0 SIZE MEMORY_FILE
```


If you want to edit something in the file, maybe a simple hex editor could help.
## Post #4
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2011-11-23T15:35:38+00:00
- Post Title: The Godfather(.Str)

I'm not tried,can you create bms with this code?
Because I cant ...
And can i repack files with this code?
## Post #5
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2011-11-23T15:41:50+00:00
- Post Title: The Godfather(.Str)

Layer ?
## Post #6
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2011-11-23T16:02:48+00:00
- Post Title: The Godfather(.Str)

How can i use this code ?
## Post #7
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2011-11-23T16:18:02+00:00
- Post Title: The Godfather(.Str)

pfffff Please someone help me!!!!!!
## Post #8
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2011-11-24T05:42:57+00:00
- Post Title: The Godfather(.Str)

open notepad/editor and paste the code in there, save the file. rename the extension from txt to bms and start QuickBMS. Select this file, when you are prompted.
## Post #9
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2011-11-25T16:37:24+00:00
- Post Title: The Godfather(.Str)

How can I repack ?
## Post #10
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-06-22T09:37:02+00:00
- Post Title: The Godfather(.Str)

i look for extract sound from .exa from the one and two 
if someone have any idea is welcome
## Post #11
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-06-25T01:01:42+00:00
- Post Title: The Godfather(.Str)

> Reply from turkgamer
>
> How can i use this code ?
Forget it.
It extracts audio files directly from memory.
The texts are located in two different str files.
