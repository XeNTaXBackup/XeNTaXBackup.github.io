## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-30T01:21:45+00:00
- Post Title: 5 Street

Here is a Online Dancing game 5 Street Online.
[http://www.5st.com.tw/](http://www.5st.com.tw/)
[](http://xs.to/xs.php?h=xs538&d=09183&f=5st331.jpg)
I have figured out the file format and I have wrote a script that extracts the first file perfectly. I just cannot figure out
how to make it skip a set number of bytes to go to the next file in the archive. I also used a bunch of get dummy commands witch is most likely wrong.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

# get DUMMY long
# get FILES long
goto 61

for i = 0 < 1
    get NAMESZ short
    getdstring NAME NAMESZ
    get SIZE long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get OFFSET long
    get ZSIZE long
    get DUMMY1 string

    clog NAME OFFSET ZSIZE SIZE
next i
```

as you can see i do not understand the dummy function yet.
any help would be great 
here is an archive.
oh is it possible to remove the last 3 of the file name also they add .tx to the end of all files for some reason.

This game uses granny mesh files witch can be converted 
[motive.rar](https://xentaxbackup.github.io/file/2005_motive.rar)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-30T01:43:56+00:00
- Post Title: 5 Street

I figured it out except for removing the last 3 of the file name.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
goto 13
 get DUMMY long
 get FILES long
goto 61

for i = 0 < FILES
    get NAMESZ short
    getdstring NAME NAMESZ
    get SIZE long
    getdstring CRC1 32
    get OFFSET long
    get ZSIZE long
    getdstring NAME1 72

    if SIZE == ZSIZE
    log NAME OFFSET SIZE
    endif

    if ZSIZE < SIZE
    log NAME OFFSET ZSIZE SIZE
    endif
next i
```


the dds files seem to be missing header information. Ill look into it and see if I can figure it out.

edit updated to support un compressed containers also. (music files)

Here is the download to download the game
[http://dler.org/dl.php?id=3183](http://dler.org/dl.php?id=3183)

or

[http://www.onrpg.com/MMO/5-Street](http://www.onrpg.com/MMO/5-Street)
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-04-30T10:16:28+00:00
- Post Title: 5 Street

Basically your format is not 100% correct so you can't get the last files!

```
dword           ver
dword           numRes
dword           ??
dword           TableSize
dword           ofsHeaderSize
...

struct ResIndex {
  byte          stgLen          
  byte          uknFlag         //if this flag is -ve(0xFF), inverse stgLen (256 - stgLen)
  char[stgLen]  ResName
  dword         ResSize
  byte_32       uknKey
  dowrd         ofsRes
  dword         ResSize
  byte_72       pad00
}
```


And since QuickBMS is so fun, here you go! Thanks Luigi

```
# by Fatduck
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "snail_package"
get DUMMY long
get NUMRES long
goto 61

for i = 0 < NUMRES
    get STGLEN byte
    get NEGFLAG byte
    if NEGFLAG == 0xFF
        math STGLEN -= 256
        math STGLEN *= -1
    endif
    getdstring RESNAME STGLEN
    get RESSIZE long
    getdstring STGDUMMY 32
    get OFSRES long
    getdstring STGDUMMY 76
    
    log RESNAME OFSRES RESSIZE
next i
```
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-30T16:42:54+00:00
- Post Title: 5 Street

Thanks for the information fatduck 
Yes this program is a lot of fun to use and is great for extracting files very quick. Thanks to bugtest.
fatduck have you seen this model format anywhere or is it a difficult format to figure out?
