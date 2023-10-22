## Post #1
- Username: hsb083
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 03, 2013 5:49 am
- Post datetime: 2013-01-02T22:20:42+00:00
- Post Title: how to extract .fpg  file - SSF2 Turbo Hd Remix ?

Sorry if this has been asked before, I'm new
I want to extract this archive
when I try to to extract the flog_ps3.fpg archive i get "QBMS: failed to produce list"
I used this script 

```
#
# supported games:
# - Super Puzzle Fighter II Turbo - HD Remix (XBLA)
# - Super Street Fighter II Turbo - HD Remix (XBLA)
#
# (c) 2012-04-04 by AlphaTwentyThree of XeNTaX

include "func_getTYPE.bms"
idstring "30GF"
get FILES long
goto 0x800
for i = 1 <= FILES
   get NAME_CRC long
   string NAME_CRC p= "%08x" NAME_CRC
   get OFFSET long
   get SIZE long
   get ZSIZE long
   if SIZE == ZSIZE
      putVarChr MEMORY_FILE SIZE 0
      log MEMORY_FILE 0 0
      log MEMORY_FILE OFFSET SIZE
   else
      putVarChr MEMORY_FILE ZSIZE 0
      log MEMORY_FILE 0 0
      clog MEMORY_FILE OFFSET SIZE ZSIZE
      set SIZE ZSIZE
   endif
   callfunction getTYPE 1
   if ZNAME != ""
      set NAME ZNAME
   else
      get NAME basename
      string NAME += "_0x"
      string NAME += NAME_CRC
   endif
   string NAME += EXT
   log NAME 0 SIZE MEMORY_FILE
next i
```


where can i find func_getTYPE.bms that will work with this 
archive ?
sorry noobness
any help is appreciated
thanks
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-01-03T07:24:12+00:00
- Post Title: how to extract .fpg  file - SSF2 Turbo Hd Remix ?

[viewtopic.php?f=13&p=69577#p69577](http://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577) maybe?
## Post #3
- Username: hsb083
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 03, 2013 5:49 am
- Post datetime: 2013-01-03T17:43:36+00:00
- Post Title: how to extract .fpg  file - SSF2 Turbo Hd Remix ?

thanks for the link
I tried running the script through quickbms directly-- when I extract
I get 6000 + small files with numbers for extensions
for example "flog_ps3_0x000d97e4.53473238" or
"flog_ps3_0x0b689cd2.53473238"
I dont think it extracted right
Anyone know how to extract with 3 letter extensions ?
when I try to to extract in multiex commander I still get
"QBMS: failed to produce list!"
Any ideas ?
