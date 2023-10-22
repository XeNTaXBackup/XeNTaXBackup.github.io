## Post #1
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2011-01-17T16:35:27+00:00
- Post Title: PS3 Atelier Totori .pf files

Earlier on I was able to convert all .msf files using alphatwentythree's "MSF2AT3, rev. 2011-10-29" script for all of PS3 Atelier Totori's SE folder. However, there was one more folder, named "voice" that contained two file types: .fp and .sif. 

For shites and giggles, I ran the one of the larger .fp files (103MB) with the previously mentioned script, and it worked perfectly fine. But as I tried them on the smaller .fp files, they didn't work. Header says they're mp3, but they're multiple mp3 mushed together. The .sif file in the same folder has a corresponding file name and it seems to act like a cue sheet(?). 

For instance, there's a "v15000.fp" file as well as a "v15000.sif" file. The sif file will say something like:(inc WALL OF TEXT, sorry)
```
Data :
 31 30 30 30 2C 09 09 2F 2A 20 70 61 63 6B 20 66      1000,  /* pack f
 69 6C 65 20 6E 75 6D 20 2A 2F 0D 0A 30 2C 09 31      ile num */  0, 1
 35 30 34 2C 09 2F 2A 20 6F 66 66 73 65 74 2C 20      504, /* offset, 
 73 69 7A 65 2C 20 31 35 30 30 30 2F 31 35 30 30      size, 15000/1500
 30 2E 6D 73 66 20 2A 2F 0D 0A 31 2C 09 31 35 30      0.msf */  1, 150
 34 2C 09 2F 2A 20 6F 66 66 73 65 74 2C 20 73 69      4, /* offset, si
 7A 65 2C 20 31 35 30 30 30 2F 31 35 30 30 31 2E      ze, 15000/15001.
 6D 73 66 20 2A 2F 0D 0A 32 2C 09 31 35 30 34 2C      msf */  2, 1504,
 09 2F 2A 20 6F 66 66 73 65 74 2C 20 73 69 7A 65       /* offset, size
 2C 20 31 35 30 30 30 2F 31 35 30 30 32 2E 6D 73      , 15000/15002.ms
 66 20 2A 2F 0D 0A 33 2C 09 31 35 30 34 2C 09 2F      f */  3, 1504, /
 2A 20 6F 66 66 73 65 74 2C 20 73 69 7A 65 2C 20      * offset, size, 
 31 35 30 30 30 2F 31 35 30 30 33 2E 6D 73 66 20      15000/15003.msf 
 2A 2F 0D 0A 34 2C 09 31 35 30 34 2C 09 2F 2A 20      */  4, 1504, /* 
 6F 66 66 73 65 74 2C 20 73 69 7A 65 2C 20 31 35      offset, size, 15
 30 30 30 2F 31 35 30 30 34 2E 6D 73 66 20 2A 2F      000/15004.msf */
 0D 0A 35 2C 09 31 35 30 34 2C 09 2F 2A 20 6F 66        5, 1504, /* of
 66 73 65 74 2C 20 73 69 7A 65 2C 20 31 35 30 30      fset, size, 1500
 30 2F 31 35 30 30 35 2E 6D 73 66 20 2A 2F 0D 0A      0/15005.msf */  
 36 2C 09 31 35 30 34 2C 09 2F 2A 20 6F 66 66 73      6, 1504, /* offs
 65 74 2C 20 73 69 7A 65 2C 20 31 35 30 30 30 2F      et, size, 15000/
 31 35 30 30 36 2E 6D 73 66 20 2A 2F 0D 0A 37 2C      15006.msf */  7,
 09 31 35 30 34 2C 09 2F 2A 20 6F 66 66 73 65 74       1504, /* offset
 2C 20 73 69 7A 65 2C 20 31 35 30 30 30 2F 31 35      , size, 15000/15
 30 30 37 2E 6D 73 66 20 2A 2F 0D 0A 38 2C 09 31      007.msf */  8, 1
 35 30 34 2C 09 2F 2A 20 6F 66 66 73 65 74 2C 20      504, /* offset, 
 73 69 7A 65 2C 20 31 35 30 30 30 2F 31 35 30 30      size, 15000/1500
 38 2E 6D 73 66 20 2A 2F 0D 0A 39 2C 09 31 35 30      8.msf */  9, 150
 34 2C 09 2F 2A 20 6F 66 66 73 65 74 2C 20 73 69      4, /* offset, si
 7A 65 2C 20 31 35 30 30 30 2F 31 35 30 30 39 2E      ze, 15000/15009.
 6D 73 66 20 2A 2F 0D 0A 31 30 2C 09 31 35 30 34      msf */  10, 1504
 2C 09 2F 2A 20 6F 66 66 73 65 74 2C 20 73 69 7A      , /* offset, siz
 65 2C 20 31 35 30 30 30 2F 31 35 30 31 30 2E 6D      e, 15000/15010.m
 73 66 20 2A 2F 0D 0A 31 31 2C 09 31 35 30 34 2C      sf */  11, 1504,
 09 2F 2A 20 6F 66 66 73 65 74 2C 20 73 69 7A 65       /* offset, size
 2C 20 31 35 30 30 30 2F 31 35 30 31 31 2E 6D 73      , 15000/15011.ms
 66 20 2A 2F 0D 0A 31 32 2C 09 31 35 30 34 2C 09      f */  12, 1504, 
 2F 2A 20 6F 66 66 73 65 74 2C 20 73 69 7A 65 2C      /* offset, size,
 20 31 35 30 30 30 2F 31 35 30 31 32 2E 6D 73 66       15000/15012.msf
 20 2A 2F 0D 0A 31 33 2C 09 31 35 30 34 2C 09 2F       */  13, 1504, /
 2A 20 6F 66 66 73 65 74 2C 20 73 69 7A 65 2C 20      * offset, size, 
 31 35 30 30 30 2F 31 35 30 31 33 2E 6D 73 66 20      15000/15013.msf 
 2A 2F 0D 0A 31 34 2C 09 31 35 30 34 2C 09 2F 2A      */  14, 1504, /*
 20 6F 66 66 73 65 74 2C 20 73 69 7A 65 2C 20 31       offset, size, 1
 35 30 30 30 2F 31 35 30 31 34 2E 6D 73 66 20 2A      5000/15014.msf *
 2F 0D 0A 31 35 2C 09 31 35 30 34 2C 09 2F 2A 20      /  15, 1504, /* 
 6F 66 66 73 65 74 2C 20 73 69 7A 65 2C 20 31 35      offset, size, 15
 30 30 30 2F 31 35 30 31 35 2E 6D 73 66 20 2A 2F      000/15015.msf */
 0D 0A 31 36 2C 09 31 35 30 34 2C 09 2F 2A 20 6F        16, 1504, /* o
 66 66 73 65 74 2C 20 73 69 7A 65 2C 20 31 35 30      ffset, size, 150
 30 30 2F 31 35 30 31 36 2E 6D 73 66 20 2A 2F 0D      00/15016.msf */ 
 0A 31 37 2C 09 31 35 30 34 2C 09 2F 2A 20 6F 66       17, 1504, /* of
 66 73 65 74 2C 20 73 69 7A 65 2C 20 31 35 30 30      fset, size, 1500
 30 2F 31 35 30 31 37 2E 6D 73 66 20 2A 2F 0D 0A      0/15017.msf */  
 31 38 2C 09 31 35 30 34 2C 09 2F 2A 20 6F 66 66      18, 1504, /* off
 73 65 74 2C 20 73 69 7A 65 2C 20 31 35 30 30 30      set, size, 15000
 2F 31 35 30 31 38 2E 6D 73 66 20 2A 2F 0D 0A 31      /15018.msf */  1
 39 2C 09 31 35 30 34 2C 09 2F 2A 20 6F 66 66 73      9, 1504, /* offs
 65 74 2C 20 73 69 7A 65 2C 20 31 35 30 30 30 2F      et, size, 15000/
 31 35 30 31 39 2E 6D 73 66 20 2A 2F 0D 0A 32 30      15019.msf */  20
 2C 09 31 35 30 34 2C 09 2F 2A 20 6F 66 66 73 65      , 1504, /* offse
 74 2C 20 73 69 7A 65 2C 20 31 35 30 30 30 2F 31      t, size, 15000/1
 35 30 32 30 2E 6D 73 66 20 2A 2F 0D 0A 32 31 2C      5020.msf */  21,
 09 31 35 30 34 2C 09 2F 2A 20 6F 66 66 73 65 74       1504, /* offset

```


Has anyone encountered these before?  I'm attaching the aforementioned two files.
[v15000.zip](https://xentaxbackup.github.io/file/3811_v15000.zip)
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2011-01-18T20:25:38+00:00
- Post Title: PS3 Atelier Totori .pf files

try file splitter by Alpha on a big files(v15000.fp - look likes only a dummy inside),then rename it to *.msf(if they have LAME3.98 log) and try to play in_vgmstream with winamp

```
string BNAME += "_"
set OFFSET 0
set SEARCH OFFSET
math SEARCH += 3
set QUIT 0
for i = 1
   goto SEARCH
   FindLoc SIZE string "MSF" 0 ""
   if SIZE == ""
      get SIZE asize
      set QUIT 1
   endif
   math SIZE -= OFFSET
   set NAME BNAME
   string NAME += i
   log NAME OFFSET SIZE
   if QUIT != 1
      math OFFSET += SIZE
      set SEARCH OFFSET
      math SEARCH += 8 # needs to be the lengh of the search string
   else
      cleanexit
   endif
next i
```
