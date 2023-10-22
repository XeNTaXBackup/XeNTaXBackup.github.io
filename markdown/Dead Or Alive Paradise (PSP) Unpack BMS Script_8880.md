## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-05-03T12:10:52+00:00
- Post Title: Dead Or Alive Paradise (PSP) Unpack BMS Script

As someone ask me for that, I just share it with you all!
Enjoy!

```
# by Fatduck   Mar2010
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get DOAPEXT extension
if DOAPEXT != "bin"
    open FDDE bin 0
endif
open FDDE arc 1
comtype gzip
idstring "PAA\0" 0
get DUMMY long 0
get NUMRES long 0
get OFSIDXTBL long 0
get OFSPOS long 0
goto OFSIDXTBL 0
savepos INDEXPOS 0
for i = 1 to NUMRES do 
   goto INDEXPOS 0
   get NAMEPOS long 0
   get RESSIZE long 0
   get UKN02 long 0
   get UKN03 long 0
   savepos INDEXPOS 0
   goto OFSPOS 0
   get OFSRES long 0
   savepos OFSPOS 0
   goto NAMEPOS 0
   get RESNAME string 0
   goto OFSRES 1
   get TESTGZ threebyte 1
   if TESTGZ == 0x88B1F then 
      clog RESNAME OFSRES RESSIZE RESSIZE 1
   else
      log RESNAME OFSRES RESSIZE 1
   endif
next i
```
## Post #2
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-05-04T20:56:01+00:00
- Post Title: Dead Or Alive Paradise (PSP) Unpack BMS Script

THANK YOU! I've been looking for something to unpack my copy of DOAP for about a year now!  

Now if only Noesis could actually view these files...
## Post #3
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-05T04:25:39+00:00
- Post Title: Dead Or Alive Paradise (PSP) Unpack BMS Script

Lol the script is inside of fatduck tools.
