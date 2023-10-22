## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-05T18:04:30+00:00
- Post Title: Warkeepers (*.RESOURCES)

Site : [here](http://warkeepers.com)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "dS.resources"
get FILES long
goto 0x14
get TABLEOFFSET long
get TABLEZSIZE long
get TABLESIZE long
savepos PTEMP

if TABLEZSIZE == TABLESIZE
        callfunction UNPACK 1
    else
        clog MEMORY_FILE PTEMP TABLEZSIZE TABLESIZE
        callfunction UNPACK_COMPRESSED 1
endif

startfunction UNPACK
for i = 0 < FILES
    get NAME string
    savepos OFFNAMES
    goto TABLEOFFSET
    get ZSIZE long
    get OFFSET long
    get TYPE long
    get SIZE long
    get DUMMY long # DATE YY
    get DUMMY long # DATE NN
    get DUMMY long # DATE MM
    get DUMMY long # TIME HH
    get DUMMY long # TIME MM 
    get DUMMY long # TIME SS
    savepos TEMP

    if ZSIZE == SIZE
        filexor "\x55"
        log NAME OFFSET SIZE
        filexor ""
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
	
    math TABLEOFFSET = TEMP
    goto OFFNAMES
next i
endfunction

startfunction UNPACK_COMPRESSED
for i = 0 < FILES
    get NAME string MEMORY_FILE
    savepos OFFNAMES MEMORY_FILE
    goto TABLEOFFSET
    get ZSIZE long
    get OFFSET long
    get TYPE long
    get SIZE long
    get DUMMY long # DATE YY
    get DUMMY long # DATE NN
    get DUMMY long # DATE MM
    get DUMMY long # TIME HH
    get DUMMY long # TIME MM 
    get DUMMY long # TIME SS
    savepos TEMP

    if ZSIZE == SIZE
        filexor "\x55"
        log NAME OFFSET SIZE
        filexor ""
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
	
    math TABLEOFFSET = TEMP
    goto OFFNAMES
next i
endfunction
```
