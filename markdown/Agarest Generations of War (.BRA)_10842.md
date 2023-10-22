## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-05T22:34:06+00:00
- Post Title: Agarest: Generations of War (*.BRA)

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate

idstring "PDA\x00"
get VERSION long
get TABLEOFFSET long
get FILES long

goto TABLEOFFSET

for i = 0 < FILES
    get DATETIME longlong
    get ZSIZE long
    get SIZE long
    get NSIZE short
    get UNKNOWN short
    get OFFSET long
    getdstring NAME NSIZE
		
    set COMPRTEST = ZSIZE
    math COMPRTEST -= SIZE
    math ZSIZE -= 16
    math OFFSET += 16
	
    if COMPRTEST == 16
       log NAME OFFSET SIZE
    else
       clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-02-14T21:43:24+00:00
- Post Title: Agarest: Generations of War (*.BRA)

Script also works on .bra file from OMG Zombies. 
Thanks, Ekey
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-07-27T04:48:21+00:00
- Post Title: Agarest: Generations of War (*.BRA)

hey Ekey when unpacking the bigger files there's only 1 file and it doesn't match up to the size on the main file  

(might need to be updated the script) if you need a file i can send you some
