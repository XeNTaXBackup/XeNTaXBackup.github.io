## Post #1
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-09-20T11:35:51+00:00
- Post Title: Kult Heretic Kingdoms .DAT+.IDX

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-09-24T14:04:10+00:00
- Post Title: Kult Heretic Kingdoms .DAT+.IDX

i dont know enough about colors to correct this, but this dumps the 16-bit textures from your samples:

```

open FDDE IDX 0
open FDDE DAT 1

get IMGCOUNT long 0

for i = 0 < IMGCOUNT
  getdstring FNAME 120 0
  get FPOS long 0
  goto FPOS 1
  callfunction writeDat
next i

startfunction writeDat
  get DWIDTH long 1
  get DHEIGHT long 1
  get DUMMY long 1
  get DUMMY long 1

  set IMGSIZE long DWIDTH
  math IMGSIZE *= DHEIGHT
  math IMGSIZE *= 2

  log MEMORY_FILE 0 0

  putvarchr MEMORY_FILE 2 2 short # rgb
  putvarchr MEMORY_FILE 12 DWIDTH short
  putvarchr MEMORY_FILE 14 DHEIGHT short
  putvarchr MEMORY_FILE 16 16 # bytes per pixel (2)
  putvarchr MEMORY_FILE 17 32 # vertical flip descriptor (00vhaaaa)
  savepos CURPOS 1

  append
  log MEMORY_FILE CURPOS IMGSIZE 1 # data is not ARRRRRGG GGGBBBBB (.*8)
  append

  get SIZE asize MEMORY_FILE
  log FNAME 0 SIZE MEMORY_FILE
endfunction

```
## Post #3
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-09-24T15:21:42+00:00
- Post Title: Kult Heretic Kingdoms .DAT+.IDX

Thanks WRS. I've got same bad result with unpacker plugin for Total Commander [http://www.totalcmd.net/plugring/gaup.html](http://www.totalcmd.net/plugring/gaup.html) This unpacker extract files with TGA extension, but it is not tga, neither 32 bit neither 16 bit. I don't know what is - After changing header to tga-header, I see contours and figures, but with wrong colors. Summarizing number of pixels and comparing with file size we get 16 bit per pixels and it is not tga's 16 bit. This is only one good  result
