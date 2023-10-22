## Post #1
- Username: freight
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 26, 2012 3:47 am
- Post datetime: 2014-04-10T10:52:42+00:00
- Post Title: Dai-3-ji super robot taisen Z voice file

Hi everyone. I'm Freight, nice to meet you all.
I open this thread to ask for help with extract voice file of dai-3-ji super robot taisen Z(PS3).

This voice file seems an aggregate of .hca file, and this file is consutituted recurrence of the header "HCA".
Is there any script for quickbms to extract .hca file from this .xfbin file? Please give me some advise for this problem.
[無題.jpg](https://xentaxbackup.github.io/file/7191_無題.jpg)
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-04-11T18:00:55+00:00
- Post Title: Dai-3-ji super robot taisen Z voice file

Try removing the first 16 bytes? everything before HCA. then use hca2wav.
## Post #3
- Username: freight
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 26, 2012 3:47 am
- Post datetime: 2014-04-13T13:51:18+00:00
- Post Title: Dai-3-ji super robot taisen Z voice file

Thanks lot!

Now I got .hca file by this cord.

```
string BNAME += "_"
set OFFSET 0
set SEARCH OFFSET
math SEARCH += 3
set QUIT 0
for i = 1
   goto SEARCH
   FindLoc SIZE string "HCA" 0 ""
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


and then, CriAtomplayer work.
