## Post #1
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-05-08T14:59:15+00:00
- Post Title: Warlock -Master of Arcane (.pack)

All parts of the game are packed into .pack files. Mostly in the 717MB d100.pack.
The game is from Ino-Co Plus. No idea if they ever made a game before using the same format.

Edit: They made Majesty 2, I don't know if that helps.
## Post #2
- Username: go581
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 03, 2010 10:02 pm
- Post datetime: 2012-05-16T13:30:51+00:00
- Post Title: Warlock -Master of Arcane (.pack)

open pack files
[this](http://forum.paradoxplaza.com/forum/showthread.php?607934-Extracting-Art-and-sound-from-Pack-files&p=13827003&viewfull=1#post13827003)



but, how to repack ?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-16T15:10:50+00:00
- Post Title: Warlock -Master of Arcane (.pack)

if the following script works for the extraction you can reuse it for the reinjection job too:

```
get VER long
for i = 0 < FILES
    get NAME string
    get SIZE long
    get ZSIZE long
    get OFFSET long
    getdstring EXTRA 8
    get ZIP long
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
if it doesn't work send me a pm with the first 10mb of the archive
## Post #4
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2012-08-05T09:42:38+00:00
- Post Title: Warlock -Master of Arcane (.pack)

> Reply from aluigi
>
> if the following script works for the extraction you can reuse it for the reinjection job too:
Code: Select allget FILES long
get VER long
for i = 0 < FILES
    get NAME string
    get SIZE long
    get ZSIZE long
    get OFFSET long
    getdstring EXTRA 8
    get ZIP long
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next iif it doesn't work send me a pm with the first 10mb of the archive
the script doesn't work, it shows an error like this

But I don't know how to get first 10 MB to send you
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T11:32:34+00:00
- Post Title: Warlock -Master of Arcane (.pack)

Done. Fixed script

```
get VER long
for i = 0 < FILES
    getdstring NAME 0x80
    get SIZE long
    get ZSIZE long
    get OFFSET long
    getdstring EXTRA 0xc
    get ZIP long
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
