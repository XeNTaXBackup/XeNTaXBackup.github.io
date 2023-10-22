## Post #1
- Username: Lys
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-07T16:58:20+00:00
- Post Title: No More Heroes: Heroes' Paradise

Here is a texture extractor and converter i made for the Japanese version of this game.
I will work on a model converter with bones next.
Run this on the file PS3_TEXTURES.FPD

```
endian big
for i
findloc start string \x02\x01\x00\xFF
goto start
get null long
get size long
math size + 0x40
set name i
string name + .tex
log name start size
math start + size
goto start
next i

```


this will extract the tex files.
now this next script converts those to dds

```
endian big
get name basename
string name + .dds
get size asize
set size2 size
math size2 - 0x80
goto 0x20
get width short
get height short
goto 0x18
get type byte
endian little
if type == 0x86
putVarChr MEMORY_FILE 0x57 0x31 byte
endif
if type == 0x87
putVarChr MEMORY_FILE 0x57 0x33 byte
endif
if type == 0x88
putVarChr MEMORY_FILE 0x57 0x35 byte
endif
putVarChr MEMORY_FILE 0xC height short
putVarChr MEMORY_FILE 0x10 width short
append
log MEMORY_FILE 0x80 size2
append
log name 0 size MEMORY_FILE

```


[1222.png](https://xentaxbackup.github.io/file/4213_1222.png)
## Post #2
- Username: sal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 11, 2011 5:01 pm
- Post datetime: 2011-10-09T08:59:13+00:00
- Post Title: No More Heroes: Heroes' Paradise

Very impressive, good work !
## Post #3
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-06-24T05:30:26+00:00
- Post Title: No More Heroes: Heroes' Paradise

Where is the PS3_TEXTURES.FPD???
## Post #4
- Username: Lys
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 08, 2015 7:16 pm
- Post datetime: 2020-08-04T01:13:03+00:00
- Post Title: No More Heroes: Heroes' Paradise

> Reply from qs12 ↑Wed Jun 24, 2020 1:30 pm at Wed Jun 24, 2020 1:30 pm
>
> 
Where is the PS3_TEXTURES.FPD???

It's in the USRDIR folder of the Japanese version.

Folder structure went something like BLJS10072 > PS3_GAME > USRDIR > PS3_Textures.FPD
