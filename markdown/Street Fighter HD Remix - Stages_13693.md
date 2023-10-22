## Post #1
- Username: Parse
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 17, 2015 10:52 pm
- Post datetime: 2015-12-17T15:01:19+00:00
- Post Title: Street Fighter HD Remix - Stages

Hi all,

Spent days trying to view these images from Super Street Fighter 2 T HD Remix from X360/PS3.

These files are .bin and are stage files.

Can you please help??

[http://www.mediafire.com/download/c4brr ... Sample.zip](http://www.mediafire.com/download/c4brr68fnox24r1/SSF2HD_Sample.zip)
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-12-18T10:17:03+00:00
- Post Title: Street Fighter HD Remix - Stages

This script only extracts the casino texture properly, but I already feel like I spent way too much time on this. Also I don't see any texture format indicator, though I might be missing something stupidly obvious. If someone feels like picking this script up feel free to do so.

```

idstring "SG28XT03"

get DUMMY long
get DUMMY long # file size - part of header
get DUMMY long # same as above
get NAME  string
get DUMMY short # 0x0a - compression type ?? (nope)
get dwPitch  long
get dwWidth  short
get dwHeight short
get DUMMY long
get DUMMY short 

#reverselong dwPitch
#reverseshort dwWidth
#reverseshort dwHeight
string NAME += ".dds"

savepos OFFSET
get asize asize
xmath SIZE "asize - OFFSET"
set MEMORY_FILE ALLOC 128
log MEMORY_FILE2 OFFSET SIZE

callfunction buildDDS

get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE

startfunction BuildDDS
   
    #math dwFourCC = 0x31545844 # "DXT1"
    #xmath dwPitch "dwWidth * dwHeight * 8 / 16"
	
	math dwFourCC = 0x33545844 # "DXT5"
	xmath dwPitch "dwWidth * dwHeight * 16 / 16"

	set dwMipMaps 1
    math dwFlags = 0x1007
    math dwCaps  = 0x1000

    math dwFlags += 0x80000
    math dwFlags2 = 0x04

    #log MEMORY_FILE 0 128
    put 0x20534444 long MEMORY_FILE # "DDS "
    put 0x7C       long MEMORY_FILE
    put dwFlags    long MEMORY_FILE
    put dwHeight   long MEMORY_FILE
    put dwWidth    long MEMORY_FILE
    put dwPitch    long MEMORY_FILE
    put 0x00       long MEMORY_FILE
    put dwMipMaps  long MEMORY_FILE

    goto 44 MEMORY_FILE SEEK_CUR

    put 0x20      long MEMORY_FILE
    put dwFlags2  long MEMORY_FILE
    put dwFourCC  long MEMORY_FILE

    goto 20 MEMORY_FILE SEEK_CUR
    put dwCaps long MEMORY_FILE
	goto 0 MEMORY_FILE SEEK_END
	
	xmath SIZE2 "SIZE / 2"
	
    #append
    #log MEMORY_FILE 0 SIZE MEMORY_FILE2
	for i = 0 < SIZE2
		get UNK1 short MEMORY_FILE2
		reverseshort UNK1
		put UNK1 short MEMORY_FILE
	next i
    #append
endfunction
```
## Post #3
- Username: Parse
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 17, 2015 10:52 pm
- Post datetime: 2015-12-18T12:17:01+00:00
- Post Title: Street Fighter HD Remix - Stages

Thaks a lot for this!

It's an awesome start.

I'm extracting so that I could make stages and characters for MUGEN. All that is missing are the effects and stage files.

If someone can help please pick this up. Thank you.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-18T18:07:21+00:00
- Post Title: Street Fighter HD Remix - Stages

> Reply from barti
>
> This script only extracts the casino texture properly, but I already feel like I spent way too much time on this.yeah, I know that feeling...  
I patched your script for another texture, 0526c800.dat

get dwPitch  long
#get dwWidth  short
#get dwHeight short
#get DUMMY long
#get DUMMY short
math dwPitch = 512
math dwWidth = 1024
math dwHeight = 512
goto 0x2F

Probably works for this one only
plus the resulting dds has to be loaded into TextureFinder because it's not loadable other than in DXTBmp for example.



0526c800_dat.JPG (141.11 KiB) Viewed 72 times


You could use goto 0x29 (instead of 0x2F) to get a loadable dds file which looks correct in DXTBmp
but shows some annoying scan or interleave lines in the DirectX Texture Tool and IrfanView.
## Post #5
- Username: Parse
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 17, 2015 10:52 pm
- Post datetime: 2015-12-19T19:38:02+00:00
- Post Title: Street Fighter HD Remix - Stages

Thank you both.

With the combination of the scripts + texture finder + editing, I could extract all of it. Only the alpha channel that didn't go well.

It's a shame they used dds to compress sprites. Most of them show heavy compression artifacts.

Edit: It looks like Alpha Channel is still compressed. Of course I could cut all images with gimp, but if you could help with a script to solve this, it would be great.
