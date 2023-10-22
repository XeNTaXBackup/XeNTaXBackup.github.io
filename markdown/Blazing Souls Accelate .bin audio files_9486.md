## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-15T16:36:47+00:00
- Post Title: Blazing Souls Accelate .bin audio files

hey guys sorry for flooding the site if asking for help but this will be my ask file 

its a bin file and in HxD it shows its a VAG or VAGp not sure if the p counts (this is a psp game) not sure if i can upload the file if i can can someone tell me and if anyone can help that would be very nice if needed i will send the files to the person thats willling to look into it
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-17T16:59:49+00:00
- Post Title: Blazing Souls Accelate .bin audio files

```
# Script for QuickBMS by WRS (XeNTaX.com)

get tsize asize
savepos fpos

for #i = 0
  if fpos = tsize
    cleanexit
  endif
  
  getdstring ftype 4
  
  if ftype = "VAGp"
    endian big
    getdstring ignored 8
    get fsize long
    getdstring ignored 16
    #getdstring fname 16
	#string fname += ".vag" ## too many duplicates
	
    math fsize += 48
  elif ftype = "RIFF"
    endian little
	get fsize long
	
	math fsize += 8
  else
    print "ERROR: Unsupported type %ftype%"
	cleanexit
  endif

  log "" fpos fsize

  math fpos += fsize
  math fpos x= 0x800 # alignment
  goto fpos
next #i

```

edit

i have no idea if the .vag files are a standard format, but a bit of googling came up with : [http://code.google.com/p/psxsdk/source/ ... /vag2wav.c](http://code.google.com/p/psxsdk/source/browse/trunk/psxsdk/tools/vag2wav.c)
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-18T00:35:31+00:00
- Post Title: Blazing Souls Accelate .bin audio files

> Reply from WRS
>
> Code: Select all# BIN extractor for xx (ouputs WAV/ADPCM VAG)
# Script for QuickBMS by WRS (XeNTaX.com)

get tsize asize
savepos fpos

for #i = 0
  if fpos = tsize
    cleanexit
  endif
  
  getdstring ftype 4
  
  if ftype = "VAGp"
    endian big
    getdstring ignored 8
    get fsize long
    getdstring ignored 16
    #getdstring fname 16
	#string fname += ".vag" ## too many duplicates
	
    math fsize += 48
  elif ftype = "RIFF"
    endian little
	get fsize long
	
	math fsize += 8
  else
    print "ERROR: Unsupported type %ftype%"
	cleanexit
  endif

  log "" fpos fsize

  math fpos += fsize
  math fpos x= 0x800 # alignment
  goto fpos
next #i

edit 

i have no idea if the .vag files are a standard format, but a bit of googling came up with : http://code.google.com/p/psxsdk/source/ ... /vag2wav.c the vag are standard  i just have to find a riff wav to wav converter
