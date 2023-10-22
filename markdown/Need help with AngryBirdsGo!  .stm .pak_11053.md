## Post #1
- Username: sailingjia
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 16, 2013 5:04 pm
- Post datetime: 2013-12-18T03:30:31+00:00
- Post Title: Need help with AngryBirdsGo!  .stm .pak

Hi Guys.

I need a help with extracting .stm and .pak achives from Angry Birds Go!
A 3D racing game.

any help would be appreciate
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-18T09:31:21+00:00
- Post Title: Need help with AngryBirdsGo!  .stm .pak

Done.

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

goto 1
idstring "KPX"
get VERSION long
get FILES long
get NAMESTABLESIZE long

set NAMESTABLEOFFSET FILES
math NAMESTABLEOFFSET *= 32
math NAMESTABLEOFFSET += 48

goto 48

for i = 0 < FILES
    get DUMMY long
    get NULL long
    get SIZE long
    get OFFSET long
    get FLAG long
    get FTIME long
    get ZSIZE long
    get NULL long
    savepos TEMP
	
    goto NAMESTABLEOFFSET
    get NAME string
    savepos NAMESTABLEOFFSET
	
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET SIZE ZSIZE
    endif
	
    goto TEMP
next i
```
## Post #3
- Username: sailingjia
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 16, 2013 5:04 pm
- Post datetime: 2013-12-19T02:17:59+00:00
- Post Title: Need help with AngryBirdsGo!  .stm .pak

> Reply from Ekey
>
> Done.
Code: Select all# Angry Birds Go! (Android)(PAK format)
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

goto 1
idstring "KPX"
get VERSION long
get FILES long
get NAMESTABLESIZE long

set NAMESTABLEOFFSET FILES
math NAMESTABLEOFFSET *= 32
math NAMESTABLEOFFSET += 48

goto 48

for i = 0 < FILES
    get DUMMY long
    get NULL long
    get SIZE long
    get OFFSET long
    get FLAG long
    get FTIME long
    get ZSIZE long
    get NULL long
    savepos TEMP
	
    goto NAMESTABLEOFFSET
    get NAME string
    savepos NAMESTABLEOFFSET
	
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET SIZE ZSIZE
    endif
	
    goto TEMP
next i

thx Ekey, that's great help for me, only .stm fileformat to go
## Post #4
- Username: sailingjia
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 16, 2013 5:04 pm
- Post datetime: 2013-12-19T04:08:43+00:00
- Post Title: Need help with AngryBirdsGo!  .stm .pak

> Reply from sailingjia
>
> Ekey wrote:Done.
Code: Select all# Angry Birds Go! (Android)(PAK format)
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

goto 1
idstring "KPX"
get VERSION long
get FILES long
get NAMESTABLESIZE long

set NAMESTABLEOFFSET FILES
math NAMESTABLEOFFSET *= 32
math NAMESTABLEOFFSET += 48

goto 48

for i = 0 < FILES
    get DUMMY long
    get NULL long
    get SIZE long
    get OFFSET long
    get FLAG long
    get FTIME long
    get ZSIZE long
    get NULL long
    savepos TEMP
	
    goto NAMESTABLEOFFSET
    get NAME string
    savepos NAMESTABLEOFFSET
	
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET SIZE ZSIZE
    endif
	
    goto TEMP
next i

thx Ekey, that's great help for me, only .stm fileformat to go
hi Ekey, i test this bms, it can extract textures.pak well, but when i extract model.pak,it failed.it seens they pak the models using different mothed, can you fix it.
btw  set NAMESTABLEOFFSET FILES is it means: int NAMESTABLEOFFSET = ftell(fp); ?

Update:

i modify
math NAMESTABLEOFFSET += 48
goto 48
with
math NAMESTABLEOFFSET += 80
goto 80

it's worked, so there only *.stm fileformat to go. anyone can help?
