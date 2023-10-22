## Post #1
- Username: freight
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 26, 2012 3:47 am
- Post datetime: 2013-01-08T11:21:16+00:00
- Post Title: Dai-2-Ji Super Robot Taisen OG  .pack file

Hi everyone. I'm Freight, nice to meet you all.
I open this thread to ask for help with extract voice file of Dai-2-Ji Super Robot Taisen OG(PS3).

This voice file seems an aggregate of .msf file, and this file is consutituted recurrence of the header "WMSF" and "MSFC".
Is there any way to extract .msf file from this .pack file? Please give me some advise for this problem.
[0002.pack.jpg](https://xentaxbackup.github.io/file/6118_0002.pack.jpg)
## Post #2
- Username: freight
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 26, 2012 3:47 am
- Post datetime: 2013-01-08T13:26:58+00:00
- Post Title: Dai-2-Ji Super Robot Taisen OG  .pack file

Now I found this cord work

```
string BNAME += "_"
set OFFSET 0
set SEARCH OFFSET
math SEARCH += 3
set QUIT 0
for i = 1
   goto SEARCH
   FindLoc SIZE string "MSF" 0 ""
   if SIZE == ""
      get SIZE asize
      set QUIT 1
   endif
   math SIZE -= OFFSET
   set NAME BNAME
   string NAME += i
   log NAME OFFSET SIZE
   if QUIT != 1
      math OFFSET += SIZE
      set SEARCH OFFSET
      math SEARCH += 8 # needs to be the lengh of the search string
   else
      cleanexit
   endif
next i
```


And then, I got some file with header "MSFC".
Is there any script for quickbms to decode this msf file to playable file?
[001.jpg](https://xentaxbackup.github.io/file/6119_001.jpg)
