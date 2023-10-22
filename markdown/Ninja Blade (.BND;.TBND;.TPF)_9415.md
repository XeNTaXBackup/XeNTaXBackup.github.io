## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-06T16:21:59+00:00
- Post Title: Ninja Blade (*.BND;*.TBND;*.TPF)

For Archives

```
#
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "BND"

goto 0xC
get TABLEOFFSET long
get FILES long
goto 0x20

for i = 0 < FILES
    get DUMMY long
    get ZSIZE long
    get OFFSET long
    get NULLS long
    get NAMEOFFSET long
    get SIZE long
    savepos TEMP
    goto NAMEOFFSET
    get NAME string
if ZSIZE == SIZE
    log NAME OFFSET SIZE
else
    clog NAME OFFSET ZSIZE SIZE
endif
    goto TEMP
next i
```


For Textures

```
#
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "TPF\x00"

#get NAME BASENAME
get SIZE long
get FILES long
get DUMMY long
get OFFSET long
get ZSIZE long
get DUMMY long
get NAMEOFF long
goto NAMEOFF
get NAME string
string NAME + .dds
log NAME OFFSET SIZE
```
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2015-12-16T18:04:06+00:00
- Post Title: Ninja Blade (*.BND;*.TBND;*.TPF)

Sorry to interrupt but I dared to edit tpf script to extract all textures in tpf container.

```

#get NAME BASENAME
get SIZE long
get FILES long

for i = 0 < FILES
  get DUMMY long
  get OFFSET long
  get ZSIZE long
  get DUMMY long
  get NAMEOFF long
  savepos base
  goto NAMEOFF
  get NAME string
  string NAME + .dds
  log NAME OFFSET ZSIZE
  goto base
next i  
```


ALSO: If you want extract map bnk file you need to add "endian big" to script, like :

```

endian big

goto 0xC

...

```
