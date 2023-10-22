## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-06-09T01:58:09+00:00
- Post Title: Shin! Koihime Musou 2D fighter thing

This game is so awesome lol
[http://www.youtube.com/watch?v=p78ZMu2J9sY](http://www.youtube.com/watch?v=p78ZMu2J9sY)

Anyways I believe the data files are encrypted.



I've uploaded what is probably the file table.

Here's some headers for the files: [http://www.mediafire.com/download/kuyc8 ... /data2.zip](http://www.mediafire.com/download/kuyc86670yl7i07/data2.zip)

[http://koihi.me/pc_index.html](http://koihi.me/pc_index.html)
[data.zip](https://xentaxbackup.github.io/file/6459_data.zip)
## Post #2
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T02:18:04+00:00
- Post Title: Shin! Koihime Musou 2D fighter thing

here is the xor key

```
FF FE FD FC 0F 1F 2F
```



LOl this is a mugen file
## Post #3
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T11:38:42+00:00
- Post Title: Shin! Koihime Musou 2D fighter thing

Here is the bms for these files.

```
#真・恋姫†夢想　～乙女対戦★三国志演義～
open FDSE data.adr
set key "0xFF 0xFE 0xFD 0xFC 0x0F 0x1F 0x2F"
get size asize
filexor key
log MEMORY_FILE 0 size
filexor ""
get files long MEMORY_FILE
get bins long MEMORY_FILE
for i = 0 < bins
get name string MEMORY_FILE
putarray 0 i name
next i
for i = 0 < files
get NAME string MEMORY_FILE
get OFFSET long MEMORY_FILE
math OFFSET * 0x800
get SIZE long MEMORY_FILE
get TMP long MEMORY_FILE
getarray FILE 0 TMP
open FDSE FILE 1
filexor key OFFSET 1
log NAME OFFSET SIZE 1
filexor ""
next i

```

The character sprites are swizzled but the rest of the files are fine. looks like a fairly simple swizzle.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-06-09T12:49:37+00:00
- Post Title: Shin! Koihime Musou 2D fighter thing

Ah that's how you work with multiple files and filexor
## Post #5
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2013-06-13T14:29:12+00:00
- Post Title: Shin! Koihime Musou 2D fighter thing

I'll start working on fixing the sprites.
## Post #6
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2013-06-15T22:12:27+00:00
- Post Title: Shin! Koihime Musou 2D fighter thing

Ok so each tile sheet is actually four 8bit indexed sheets in one, just access a different color channel to get to them.
The palette file contains one complete 256 color palette per row, just take the colors as they are.

The SPR file contains axis data and data on how to put together the sprite tiles.

Header (8 Bytes)
4 bytes - Number of sheets
4 bytes - Number of sprites

Sprite Header (20 Bytes)
2 bytes - Group# (will explain later)
2 bytes - Spr# (will explain later)
2 bytes - Width in tiles
2 bytes - Height in tiles
2 bytes - X Axis
2 bytes - Y Axis
2 bytes - Sprite width (tile width * 32)
2 bytes - Sprite height (tile height * 32)
2 bytes - Number of tiles in this sprite
2 bytes - Palette# (Which row to use in the palette file)

Sprite Data (8 bytes per tile)
2 bytes - Sheet#
1 byte - Tile#
1 byte - Channel# (0-3, the order being ARGB)
2 bytes - Tile position X
2 bytes - Tile position Y
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-15T23:57:13+00:00
- Post Title: Shin! Koihime Musou 2D fighter thing

Nice job that makes sense.
i saw the textures were aligned by multiples of 32 that makes sense.
