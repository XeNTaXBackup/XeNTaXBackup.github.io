## Post #1
- Username: Arcalane
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 11, 2009 10:01 pm
- Post datetime: 2012-01-18T07:13:13+00:00
- Post Title: Warhammer 40,000: Space Marine .PCK Files

These files appear to contain a number of .wav files when scanned with certain applications, but extracted files are possibly encoded and unplayable, usually coming out as a mess of static.

[This zip file](http://www.mediafire.com/download.php?jov3i6fm5giupb1) contains four such .pck files, should anyone want to take a crack at figuring them out. Ultimate goal would be extracting the music since it seems to use the same archive and format.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-18T12:05:46+00:00
- Post Title: Warhammer 40,000: Space Marine .PCK Files

```
# script for QuickBMS http://quickms.aluigi.org

math DIDX_OFF  = 0
math DIDX_SIZE = 0
math DATA_OFF  = 0
get PCK_SIZE asize
do
    getdstring SIGN 4
    get SIZE long
    savepos OFFSET
    if SIGN == "DIDX"
        math DIDX_OFF = OFFSET
        math DIDX_SIZE = SIZE
    elif SIGN == "DATA"
        math DATA_OFF = OFFSET
    endif
    math OFFSET += SIZE
    goto OFFSET
while OFFSET < PCK_SIZE

goto DIDX_OFF
math FILES = DIDX_SIZE
math FILES /= 12
for i = 0 < FILES
    get CRC long
    get OFFSET long
    get SIZE long
    math OFFSET += DATA_OFF
    log "" OFFSET SIZE
next i
```
## Post #3
- Username: Arcalane
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 11, 2009 10:01 pm
- Post datetime: 2012-01-18T12:25:30+00:00
- Post Title: Warhammer 40,000: Space Marine .PCK Files

Everything extracts alright, and it looks like the files can be rendered into playable .ogg files using [hcs' ww2ogg](http://hcs64.com/vgm_ripping.html) app.

Thanks!
## Post #4
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-09-20T17:55:21+00:00
- Post Title: Warhammer 40,000: Space Marine .PCK Files

Script dont work on the big files - extracts only small files from big .pcks(in_game_default, music_01).

WAVE Scanner from here [viewtopic.php?f=13&p=74664#p74664](http://forum.xentax.com/viewtopic.php?f=13&p=74664#p74664) - extract all WAVEfmt data, but some music is cut to pieces, and ww2ogg decode with "scratches".
