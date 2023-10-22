## Post #1
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-01-03T05:37:05+00:00
- Post Title: Tales of the World: Radiant Mythology 2 ARC

Format(s): ARC (Containter files) MDL, (Model files), ani (animation files), ppt(textures).
Since I cannot post the file, someone with the game will have to try it, but if I remember, there is some tools to extract the ARC files to get the MDL files which I need.  I hope someone can answer my post.

I know about this ([https://github.com/0xFAIL/reverse-engineering](https://github.com/0xFAIL/reverse-engineering)). This is the source and I have no idea on how to compile ruby source.
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-01-03T10:21:06+00:00
- Post Title: Tales of the World: Radiant Mythology 2 ARC

I had written a bms script to extract this:

```
# by Fatduck   17 Dec 2011
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get ARCSIZE asize
get HDR long
if HDR == 0x08088B1F
   comtype gzip
   goto -4
   get USIZE long
   clog memory_file 0 ARCSIZE USIZE
   CallFunction ExtractEZBIND
elif HDR == 0x49425A45
   log memory_file 0 ARCSIZE
   CallFunction ExtractEZBIND
endif
cleanexit



StartFunction ExtractEZBIND
   get DIR basename
   string DIR += \
   idstring "EZBIND\0\0" memory_file
   get NUMRES long memory_file
   get UNKNOWN long memory_file
   savepos OFSINDEX memory_file

   for i = 0 < NUMRES
      goto OFSINDEX memory_file
      get OFSNAME long memory_file
      get RESSIZE long memory_file
      get OFSRES long memory_file
      get UNKNOWN long memory_file
      savepos OFSINDEX memory_file
      goto OFSNAME memory_file
      get RESNAME string memory_file
      set OUTNMAE = DIR
      string OUTNMAE += RESNAME
      log OUTNMAE OFSRES RESSIZE memory_file
   next i
EndFunction
```
## Post #3
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-01-03T12:11:09+00:00
- Post Title: Tales of the World: Radiant Mythology 2 ARC

Oh, thanks so much! Would it be possible to get models from Tales of The World: Radiant Mythology 3? Just need to find a way to extract them from the BDI file.
## Post #4
- Username: sieghartx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 08, 2015 4:15 pm
- Post datetime: 2015-12-08T08:31:04+00:00
- Post Title: Tales of the World: Radiant Mythology 2 ARC

> Reply from ShinKun
>
> Oh, thanks so much! Would it be possible to get models from Tales of The World: Radiant Mythology 3? Just need to find a way to extract them from the BDI file.

so how do you view the .mdl next?

thanks to fatduck I have now manage to extract .arc but still bump on .mdl
noesis couldn't view them
