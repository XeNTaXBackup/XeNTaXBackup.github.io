## Post #1
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2019-01-03T18:32:12+00:00
- Post Title: Child of Eden BGSQ and SREQ (.dat) archives

Hello there!

I've been doing some digging into Child of Eden's 3D models- they seem to use some sort of compression that starts with the file header "BGSQ", has anyone seen anything like these before?

I'll send a few examples of these- it looks like it could also be an archive with models inside.
In addition, it seems the one other file format used in CoE is SREQ, which seems to be for sound effects and music (which this game has plenty of!) Looks to be another kind of archive
Included those in the link as well now, under a separate folder.

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/17HsFt0-AhEhVanrUDfxVjb6h_88gUT7q?usp=sharing)
## Post #2
- Username: zefie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 27, 2020 2:45 pm
- Post datetime: 2020-10-27T06:56:05+00:00
- Post Title: Child of Eden BGSQ and SREQ (.dat) archives

I know this is a super late reply, but in case anyone else is curious about this too, since I couldn't find anything, I made a SREQ extractor script for QuickBMS. (my first BMS script!)

I only really tested it on the "reqBGM.bin" files from "stage\<stagename>\area\area<number>\common\sound" but may work on other SREQ. Not sure if I am doing it 100% proper but it got me the files I needed.

Tested on both Xbox 360 version and PS3 version.

```

idstring "SREQ"

get FileCount LONG
get BaseOffset LONG
set AllFileLength 0

for x = 0 < FileCount
GetDString Name 0xF0
get Size LONG
get DUMMY LONG
math Offset = BaseOffset
math Offset += AllFileLength
math AllFileLength += Size
log Name Offset Size
next x

```


As for BGSQ, unfortunately I am only interested in the audio, so I did not poke at that.
