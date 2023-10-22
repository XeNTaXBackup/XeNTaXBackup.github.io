## Post #1
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2019-07-01T08:41:03+00:00
- Post Title: [NLTX image] Swizzled 256 index color palette (NSW)

I'm having a bit of trouble ripping images from .NLTX files made from Nippon Ichi Software silimar to .nltx file [here](https://zenhax.com/viewtopic.php?t=8503) but for a different game.

The images are compressed with [ykcmp](https://aluigi.altervista.org/bms/ykcmp.bms) and when extracted gives you a raw headerless image (DDS???)

The other image files the game had, I've manage to rip the textures on the .fad files which is also compressed with ykcmp and most of them are just normal dds image with 256 color + alpha, but on this files I cant seem to rip them properly since most raw texture viewer seems not to handle images with palettes so I can't even use Rawtex or TextureFinder or Kukkii raw image viewer.

I've tried to modify the ykcmp code to decompress the image and make a dds header but i still need to uswizzle these nintendo switch image.

```

goto 0x18
get Width long
get Height long


goto 0x80
idstring "YKCMP_V1"
get DUMMY long  # 4
get ZSIZE long
get SIZE long
savepos OFFSET
math ZSIZE - 20

xmath dataSize "Width * Height"

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\x00\x02\x00\x00\x00\x04\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x20\x00\x00\x00\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"


putVarChr MEMORY_FILE 0xC Width short
putVarChr MEMORY_FILE 0x10 Height short
putVarChr MEMORY_FILE 0x14 dataSize long
putVarChr MEMORY_FILE 0x4C 0x20 long
putVarChr MEMORY_FILE 0x50 0x20 long
putVarChr MEMORY_FILE 0x58 0x8 long
putVarChr MEMORY_FILE 0x6c 0x1000 long

get NAME basename
string NAME p "%s_decompress.dds" NAME

log NAME 0 0x80 MEMORY_FILE
append
clog NAME OFFSET ZSIZE SIZE
append
```


any help is appreciated.




sample files [https://drive.google.com/open?id=1F3JQM ... Pp-8_sFBCr](https://drive.google.com/open?id=1F3JQMOWuOAVJKNvnAwRxmlPp-8_sFBCr)
## Post #2
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2019-07-06T18:51:24+00:00
- Post Title: [NLTX image] Swizzled 256 index color palette (NSW)

This will mostly work (>95% of the files in your archive). Took me a while as I was trying to unswizzle (or undo block linear, whatever it's called by nvidia) palette indexes instead of actual RGBA data.

UPD: implemented YKCMP_V1 decompression in Noesis script
[tex_nltx_v2.zip](https://xentaxbackup.github.io/file/16432_tex_nltx_v2.zip)
## Post #3
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2019-07-08T18:33:32+00:00
- Post Title: [NLTX image] Swizzled 256 index color palette (NSW)

Thank you so much, almost given up on ripping images from these.
