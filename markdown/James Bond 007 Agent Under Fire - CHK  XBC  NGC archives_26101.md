## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-12-20T11:01:17+00:00
- Post Title: James Bond 007: Agent Under Fire - CHK / XBC / NGC archives

As for the PS2 version it uses .CHK files which is stored in ACTDATA.VIV.
As for the XBOX version it uses .XBC files.
As for the GameCube version it uses .NGC files.

Are there programs to unpack archives for all versions of James Bond 007: Agent Under Fire?

James Bond 007: Everything or Nothing uses the same format.

Samples:
[https://mega.nz/folder/Ua5jDIBJ#jt3geUN0vl-VY1tiIafvag](https://mega.nz/folder/Ua5jDIBJ#jt3geUN0vl-VY1tiIafvag)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-12-20T14:09:47+00:00
- Post Title: James Bond 007: Agent Under Fire - CHK / XBC / NGC archives

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
#
# initially coded by Alugi, further documentation of .chk file and expansion of functionality by N/A

set INCLUDEARCHIVENAME 0 //boolean to avoid name conflicts if unpacking 2 or more .chk files

comtype dk2 //quickbms.txt doesn't list ea type, I tried dk2 from on quickbms.txt comments, did a byte-by-byte comparison, identical.
get DUMMY long
if DUMMY > 0xffff
    endian big
endif
get DUMMY long
get TABLEWIDTH long //possibly clarified width of table throughout file.
get DATSTREAMCOUNT long //clarified purpose of integer
get OFFSET long 
get XFILES long 
math TMP = XFILES
math TMP *= TABLEWIDTH
math OFFSET += TMP
for i = 0 < DATSTREAMCOUNT
    get fileTablePtr long //abs offset of first table pointer.
    get filesInStream long //number of files in each stream
    get XSIZE long
    get SIZE long
    get ZERO long
    get FLAGS long
    math OFFSET x= 0x800
    putvarchr MEMORY_FILE XSIZE 0  //allocates internal memory
    if FLAGS & 0x04000000 //little end
        clog MEMORY_FILE OFFSET SIZE XSIZE
    elif FLAGS & 0x00000400 //big end
        clog MEMORY_FILE OFFSET SIZE XSIZE
    else
        log MEMORY_FILE OFFSET SIZE
    endif
    savepos dataStreamTablePtr 0 //saves pointer to revert to after finish parsing datastream
    goto fileTablePtr 0
    for j = 0 < filesInStream
        getdstring NAME 8 0 //gets filename
        //assembles filename to export, to prevent naming conflicts with 2 or more .chk files
        if INCLUDEARCHIVENAME > 0
            get ChkFN BASENAME 0
            String EXPNAME = ChkFN
            String EXPNAME + "."
            String EXPNAME + NAME
        else
            String EXPNAME = NAME
        endif
        get DUMMY long 0 
        get DUMMY long 0 //value = compressed file size it seems
        get FILEOFFSET long 0
        get FILESIZE long 0
        log EXPNAME FILEOFFSET FILESIZE -1
    next j
    goto dataStreamTablePtr 0 
    //no need to keep fileTablePtr as next dataStream gives the offset for the first file in next data stream.
    math OFFSET += SIZE
next i
```


try this
## Post #3
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-12-26T23:20:22+00:00
- Post Title: James Bond 007: Agent Under Fire - CHK / XBC / NGC archives

Please keep this thread updated, there's barely anything known about the old EA game Bond formats. What are you hoping to be able to rip from these games by the way? Maybe I can try helping
## Post #4
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-12-28T10:27:08+00:00
- Post Title: James Bond 007: Agent Under Fire - CHK / XBC / NGC archives

> Reply from AxelNoir ↑Tue Dec 27, 2022 7:20 am at Tue Dec 27, 2022 7:20 am
>
> 
Please keep this thread updated, there's barely anything known about the old EA game Bond formats. What are you hoping to be able to rip from these games by the way? Maybe I can try helping

I managed to rip 3D models and other data from CHK files from James Bond 007: Agent Under Fire, but this script won't work for this game.

```
- select input archives/files, type * for the whole folder and subfolders
- select output folder where extracting files
- open input file C:\Users\PC\Desktop\hex2obj\chk\alp1_1.chk
- open script C:\Users\PC\Desktop\hex2obj\007agentunderfire.bms
- set output folder C:\Users\PC\Desktop\hex2obj\chk

  offset   filesize   filename
--------------------------------------

Error: offset in PutVarChr (0xff414c42) is negative

Last script line before the error or that produced the error:
  29  putvarchr MEMORY_FILE XSIZE 0  //allocates internal memory
  coverage file 0     0%   48         12279456   . offset 00000030

Press ENTER or close the window to quit
```
## Post #5
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-12-28T14:11:32+00:00
- Post Title: James Bond 007: Agent Under Fire - CHK / XBC / NGC archives

> Reply from mrmaller1905 ↑Wed Dec 28, 2022 6:27 pm at Wed Dec 28, 2022 6:27 pm
>
> 
I managed to rip 3D models and other data from CHK files from James Bond 007: Agent Under Fire, but this script won't work for this game.

Can I ask how you did? Did you use Ninja Ripper or something or extract from the files directly? Are you able to share this in private?
## Post #6
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-01-02T09:15:22+00:00
- Post Title: James Bond 007: Agent Under Fire - CHK / XBC / NGC archives

> Reply from AxelNoir ↑Wed Dec 28, 2022 10:11 pm at Wed Dec 28, 2022 10:11 pm
>
> 
Can I ask how you did? Did you use Ninja Ripper or something or extract from the files directly? Are you able to share this in private?

I tried but the problem is that Ninja Ripper doesn't work for emulators. I didn't extract them directly.
