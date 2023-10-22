## Post #1
- Username: ytuD fo llaC
- Rank: beginner
- Number of posts: 23
- Joined date: Mon May 24, 2021 10:32 am
- Post datetime: 2021-08-10T23:59:52+00:00
- Post Title: [DS] Hayarigami (.tx2 file)

I am having trouble finding a way to extract decrpyt the game's .tx2 files. If anyone can help me that would be much appreciated

Example files
[https://www.mediafire.com/file/6fvcgaav ... d.zip/file](https://www.mediafire.com/file/6fvcgaavg5sj2p1/g2d.zip/file)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-11T14:09:27+00:00
- Post Title: [DS] Hayarigami (.tx2 file)

Whole TX2 file is compressed with NitroSDK compression, so you need to decompress it first.
Here is the script:

```
# Creation Date: 11.08.2021

comtype NitroSDK
get ZSIZE asize
set SIZE long 0

math SIZE = ZSIZE
math SIZE *= 20

get NAME basename
string NAME + "_new.decompressed"
clog NAME 0 ZSIZE SIZE
```


Then you can load output file in some tile editor and edit it as you wish.
I got some results in TiledGGD:
[https://i.imgur.com/HSxgozX.png](https://i.imgur.com/HSxgozX.png)
[https://i.imgur.com/8E0q7Z1.png](https://i.imgur.com/8E0q7Z1.png)

Here is also my article about this file format [http://wiki.xentax.com/index.php/Nitro_ ... Tiles_NCGR](http://wiki.xentax.com/index.php/Nitro_Character_Tiles_NCGR)

TX2 file is really a combination of a few NDS standard files:
- Nitro Character Tiles (RGCN and RAHC chunks)
- Nitro Color Palette (RLCN and TTLP chunks)
- Nitro OBJ Metatile Cells (RECN and KBEC chunks)
- ?? (LBAL chunk)

so you could probably write some tool or script to automate extraction to separate files.
## Post #3
- Username: ytuD fo llaC
- Rank: beginner
- Number of posts: 23
- Joined date: Mon May 24, 2021 10:32 am
- Post datetime: 2021-08-12T01:02:11+00:00
- Post Title: [DS] Hayarigami (.tx2 file)

Thank you
