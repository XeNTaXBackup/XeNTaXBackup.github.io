## Post #1
- Username: Deko
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 03, 2012 7:36 am
- Post datetime: 2015-01-30T02:26:50+00:00
- Post Title: Hyperdimension Neptunia Rebirth 1 PC Files

The game just released on pc today on steam. 

Could anyone please help me decrypt the .pac format? Their is so much new content that needs to be seen, and if possible, mods.


.pac File: [https://mega.co.nz/#!DAxzEChY!EyVRgHo9l ... kiPdUqmdrQ](https://mega.co.nz/#!DAxzEChY!EyVRgHo9lGX0WawZpXz71rXrTaZ_z7AArkiPdUqmdrQ)

Their seems to be .tid files inside. You can see by opening it in hex editor.
## Post #2
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-02-01T01:20:52+00:00
- Post Title: Hyperdimension Neptunia Rebirth 1 PC Files

I can't offer any help (other than sharing files and testing) but I'd be interested in tools for Neptunia.
## Post #3
- Username: devilkkw
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Mar 10, 2013 4:21 pm
- Post datetime: 2015-02-03T00:52:15+00:00
- Post Title: Hyperdimension Neptunia Rebirth 1 PC Files

file header are DW_PACK.
After comtype scan i get these resulst: COMP_UNKNOWN10;

Also,in the pac file are include TID,ISM,BIN,CL3,ANM,ACB.

Now im studying how EXE file load these file
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-04T13:20:45+00:00
- Post Title: Hyperdimension Neptunia Rebirth 1 PC Files

number of files in pac at 0x0C: 35h = 53

files
1. apply\005\main.cl3
2. database\stitem05.gbin
3. dlc005.txt
4. model\chara\005\texture\004\base_00.tid
5. model\chara\005\texture\004\body_c.tid
...
51. model\chara\005\texture\008\mouth_00.tid
52. model\chara\005\texture\008\pupil_00.tid
53. model\chara\005\texture\008\toon_shadow.tid

TOC (start: 0x14)

offset to be added to start of file data: 0x3BB4

00 00 00 00, file_number, compressed size+0x1C, uncompr size?, 01 00 00 00, start of compr file data 
(file name (after file number) not printed)

```
00 00 00 00  01 00 00 00  27 03 00 00  80 08 00 00  01 00 00 00  BA 01 00 00  
00 00 00 00  02 00 00 00  EB 00 00 00  F5 00 00 00  01 00 00 00  E1 04 00 00  
00 00 00 00  03 00 00 00  8D 5E 00 00  80 80 00 00  01 00 00 00  CC 05 00 00  
00 00 00 00  04 00 00 00  6C AC 01 00  80 00 02 00  01 00 00 00  59 64 00 00  
00 00 00 00  05 00 00 00  BE 2A 00 00  80 00 01 00  01 00 00 00  C5 10 02 00  
00 00 00 00  06 00 00 00  7E 1A 00 00  80 80 00 00  01 00 00 00  83 3B 02 00  
00 00 00 00  07 00 00 00  24 90 00 00  80 00 01 00  01 00 00 00  01 56 02 00  
00 00 00 00  08 00 00 00  73 6F 01 00  80 00 02 00  01 00 00 00  25 E6 02 00  
00 00 00 00  09 00 00 00  C2 6A 00 00  80 80 00 00  01 00 00 00  98 55 04 00  
00 00 00 00  0A 00 00 00  6D 3C 00 00  80 00 01 00  01 00 00 00  5A C0 04 00  
00 00 00 00  0B 00 00 00  D9 14 00 00  80 40 00 00  01 00 00 00  C7 FC 04 00  
00 00 00 00  0C 00 00 00  D7 00 00 00  80 01 00 00  01 00 00 00  A0 11 05 00  
00 00 00 00  0D 00 00 00  8D 5E 00 00  80 80 00 00  01 00 00 00  77 12 05 00  
00 00 00 00  0E 00 00 00  5A AB 01 00  80 00 02 00  01 00 00 00  04 71 05 00  
00 00 00 00  0F 00 00 00  BE 2A 00 00  80 00 01 00  01 00 00 00  5E 1C 07 00  
00 00 00 00  10 00 00 00  7E 1A 00 00  80 80 00 00  01 00 00 00  1C 47 07 00  
00 00 00 00  11 00 00 00  24 90 00 00  80 00 01 00  01 00 00 00  9A 61 07 00  
00 00 00 00  12 00 00 00  73 6F 01 00  80 00 02 00  01 00 00 00  BE F1 07 00  
00 00 00 00  13 00 00 00  C2 6A 00 00  80 80 00 00  01 00 00 00  31 61 09 00  
00 00 00 00  14 00 00 00  6D 3C 00 00  80 00 01 00  01 00 00 00  F3 CB 09 00  
00 00 00 00  15 00 00 00  D9 14 00 00  80 40 00 00  01 00 00 00  60 08 0A 00  
00 00 00 00  16 00 00 00  D7 00 00 00  80 01 00 00  01 00 00 00  39 1D 0A 00  
00 00 00 00  17 00 00 00  8D 5E 00 00  80 80 00 00  01 00 00 00  10 1E 0A 00  
00 00 00 00  18 00 00 00  87 AC 01 00  80 00 02 00  01 00 00 00  9D 7C 0A 00  
00 00 00 00  19 00 00 00  BE 2A 00 00  80 00 01 00  01 00 00 00  24 29 0C 00  
00 00 00 00  1A 00 00 00  7E 1A 00 00  80 80 00 00  01 00 00 00  E2 53 0C 00  
00 00 00 00  1B 00 00 00  24 90 00 00  80 00 01 00  01 00 00 00  60 6E 0C 00  
00 00 00 00  1C 00 00 00  73 6F 01 00  80 00 02 00  01 00 00 00  84 FE 0C 00  
00 00 00 00  1D 00 00 00  C2 6A 00 00  80 80 00 00  01 00 00 00  F7 6D 0E 00  
00 00 00 00  1E 00 00 00  6D 3C 00 00  80 00 01 00  01 00 00 00  B9 D8 0E 00  
00 00 00 00  1F 00 00 00  D9 14 00 00  80 40 00 00  01 00 00 00  26 15 0F 00  
00 00 00 00  20 00 00 00  D7 00 00 00  80 01 00 00  01 00 00 00  FF 29 0F 00  
00 00 00 00  21 00 00 00  8D 5E 00 00  80 80 00 00  01 00 00 00  D6 2A 0F 00  
00 00 00 00  22 00 00 00  2D AC 01 00  80 00 02 00  01 00 00 00  63 89 0F 00  
00 00 00 00  23 00 00 00  BE 2A 00 00  80 00 01 00  01 00 00 00  90 35 11 00  
00 00 00 00  24 00 00 00  7E 1A 00 00  80 80 00 00  01 00 00 00  4E 60 11 00  
00 00 00 00  25 00 00 00  24 90 00 00  80 00 01 00  01 00 00 00  CC 7A 11 00  
00 00 00 00  26 00 00 00  73 6F 01 00  80 00 02 00  01 00 00 00  F0 0A 12 00  
00 00 00 00  27 00 00 00  C2 6A 00 00  80 80 00 00  01 00 00 00  63 7A 13 00  
00 00 00 00  28 00 00 00  6D 3C 00 00  80 00 01 00  01 00 00 00  25 E5 13 00  
00 00 00 00  29 00 00 00  D9 14 00 00  80 40 00 00  01 00 00 00  92 21 14 00  
00 00 00 00  2A 00 00 00  D7 00 00 00  80 01 00 00  01 00 00 00  6B 36 14 00  
00 00 00 00  2B 00 00 00  8D 5E 00 00  80 80 00 00  01 00 00 00  42 37 14 00  
00 00 00 00  2C 00 00 00  2F AB 01 00  80 00 02 00  01 00 00 00  CF 95 14 00  
00 00 00 00  2D 00 00 00  BE 2A 00 00  80 00 01 00  01 00 00 00  FE 40 16 00  
00 00 00 00  2E 00 00 00  7E 1A 00 00  80 80 00 00  01 00 00 00  BC 6B 16 00  
00 00 00 00  2F 00 00 00  24 90 00 00  80 00 01 00  01 00 00 00  3A 86 16 00  
00 00 00 00  30 00 00 00  73 6F 01 00  80 00 02 00  01 00 00 00  5E 16 17 00  
00 00 00 00  31 00 00 00  C2 6A 00 00  80 80 00 00  01 00 00 00  D1 85 18 00  
00 00 00 00  32 00 00 00  6D 3C 00 00  80 00 01 00  01 00 00 00  93 F0 18 00  
00 00 00 00  33 00 00 00  D9 14 00 00  80 40 00 00  01 00 00 00  00 2D 19 00  
00 00 00 00  34 00 00 00  D7 00 00 00  80 01 00 00  01 00 00 00  D9 41 19 00  
```


The 28 bytes headers of the compressed file data:
1. 34120000 01000000 00000200 1C000000 00060000 9E010000 00000000
2. 34120000 01000000 00000200 1C000000 80080000 0B030000 00000000
3. 34120000 01000000 00000200 1C000000 F5000000 CF000000 00000000

where the bold DWs are the compressed file sizes (the prev. DW hopefully the uncompressed size).
For example: 19E = 1BA -1C
uncompr. size: 0x600?
## Post #5
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-02-12T04:20:46+00:00
- Post Title: Hyperdimension Neptunia Rebirth 1 PC Files

Any progress on tools/scripts/etc? The thread has a lot of views so there's definitely a good amount of interest in the game. It's also confirmed that the second game is getting a release. Maybe they'll run on the same/similar engines?
