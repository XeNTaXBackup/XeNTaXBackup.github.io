## Post #1
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-11-14T08:33:39+00:00
- Post Title: The Evil Within (*.bimage) HELP

Hi 
first i knew there is thread about game and  .bimage textures

but i tried everything (script,GIMP, And edit by hex, etc...) 

and result damage textures and i cant convert to DDS

HERE SOME SAMPLES FILES

[https://mega.nz/#!yNElAARC!eKsH4SchDiGK ... 4qdSItoCdw](https://mega.nz/#!yNElAARC!eKsH4SchDiGKEfntwTNRo0qPWp2MiCRY74qdSItoCdw)


And also i tried MerlinSVK script and still no result
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-14T12:06:59+00:00
- Post Title: The Evil Within (*.bimage) HELP

here is a Noesis python script to open your bimage samples  
*updated Nov 19, 2016*


 tex_TheEvilWithin_bimage.zip
(768 Bytes) Downloaded 86 times


supports dxt1, dxt5 and rgba2222


and here is a modified bms script that can change your dxt1 and dxt5 
bimage samples to dds if you choose to use this instead  

```
#http://forum.xentax.com/viewtopic.php?p=107348#p107348

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\xDD\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

get NAME basename
string NAME + ".dds"
get HNAME basename
string HNAME + ".header"

endian big
goto 0x10
get WIDTH long
    print "%WIDTH% width"
get HEIGHT long
    print "%HEIGHT% height"
goto 0x24
get IMGFMT byte
goto 0x3e
get SIZE long
    print "%SIZE% SIZE"
savepos OFFSET
    print "%OFFSET% end of header"
endian little
log HNAME 0x0 OFFSET   # save header for backward conversion

if IMGFMT == 0xa
	IMGFMT = 0x31 #dxt1
elif IMGFMT == 0xb
	IMGFMT = 0x35 #dxt5
endif

putVarChr MEMORY_FILE 0XC HEIGHT long #AAAAAAAA
putVarChr MEMORY_FILE 0x10 WIDTH long #BBBBBBBB
putVarChr MEMORY_FILE 0x14 SIZE long #CCCCCCCC
putVarChr MEMORY_FILE 0x57 IMGFMT byte #DD

append
log MEMORY_FILE OFFSET SIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0x0 DDSSIZE MEMORY_FILE
```
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-11-17T19:39:57+00:00
- Post Title: The Evil Within (*.bimage) HELP

hey, AceWell, nice work!

Can you look at this samples: [http://www.mediafire.com/file/7qyxo577o ... ples_am.7z](http://www.mediafire.com/file/7qyxo577o3boz7t/the_evil_within_tex_samples_am.7z)

your tools doesn't work for me :/
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-18T04:08:18+00:00
- Post Title: The Evil Within (*.bimage) HELP

okay i updated both the Noesis python script and the bms script to support dxt1
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-11-18T09:47:55+00:00
- Post Title: The Evil Within (*.bimage) HELP

> Reply from AceWell
>
> okay i updated both the Noesis python script and the bms script to support dxt1it works great, thank you! I will test the rest textures when I get home.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-11-18T21:31:20+00:00
- Post Title: The Evil Within (*.bimage) HELP

Hey, AceWell, works great! Only this textures are not working so far:
[http://www.mediafire.com/file/qei3d7dyb ... texture.7z](http://www.mediafire.com/file/qei3d7dybgcbu82/the_evil_within_tex_samples_texture.7z)

can you look at them?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-19T10:19:22+00:00
- Post Title: The Evil Within (*.bimage) HELP

okay i updated the Noesis python script to open rgba2222 textures  
i didn't do anything with the bms script this time because i don't know
how to convert raw image data with it.
