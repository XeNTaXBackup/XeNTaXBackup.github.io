## Post #1
- Username: nightland18
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 09, 2016 3:59 pm
- Post datetime: 2017-04-02T15:40:34+00:00
- Post Title: what is systax for this program?

```
# 
# Written by Ekey (h4x0r) / thx Haoose
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate_noerror
open FDDE "tab" 0
open FDDE "arc" 1

get FILES asize
get ALIGN long
get ADDITIONAL long

if ADDITIONAL >= 0
for i = 0 < ADDITIONAL
   get IHASH long
   get ITYPE long
   savepos ITEMP
   if ITYPE == 2
      math ITEMP += 16
   elif ITYPE == 3
      math ITEMP += 24
   elif ITYPE == 4
      math ITEMP += 32
   elif ITYPE == 5
      math ITEMP += 40
   else
      print "Unsupported type %ITYPE%"
     cleanexit
   endif
   goto ITEMP
next i

savepos CUROFFSET
math FILES -= CUROFFSET
math FILES /= 16

for i = 0 < FILES
   get HASH long   
   get OFFSET long
   get ZSIZE long
   get SIZE long
   string NAME p= "%08X" HASH
   if ZSIZE == SIZE
      log NAME OFFSET SIZE 1
   else
      clog NAME OFFSET ZSIZE SIZE 1
   endif
next i
```

what is the systax, struct, for this program language? what is ZSIZE, OFFSET, ITEMP? where i find data doc to learn write this script language just like tutorialpoint.com?how to use quickbms language keyword?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2017-04-02T16:06:07+00:00
- Post Title: what is systax for this program?

There is what looks to be fairly comprehensive documentation at [http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt), and you may be interested in some of the other resources linked from [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm) as well.
## Post #3
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2017-04-10T01:17:08+00:00
- Post Title: what is systax for this program?

Removed.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2017-04-10T05:01:09+00:00
- Post Title: what is systax for this program?

Thanks for the heads-up, though unfortunately it came too late to save me the trouble of responding to his PMs...
