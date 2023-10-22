## Post #1
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2010-06-20T10:01:08+00:00
- Post Title: Doom 2 XBOX Live

Can someone try and analyse the file format for this archive?
Looking at it with a hex editor it seems quite simple, however I don't know the first thing about reversing file types =[

[Link Removed Now That Filetype is Posted]
doom2.disk
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-20T12:37:07+00:00
- Post Title: Doom 2 XBOX Live

script for QuickBMS:

```
if SIGN == "KIWAD"
    comtype zlib_noerror
    get DUMMY long
    get FILES long
    for i = 0 < FILES
        get OFFSET long
        get SIZE long
        get ZSIZE long
        get ZIP byte
        get CRC long
        get NAMESZ long
        getdstring NAME NAMESZ
        if ZIP == 0
            log NAME OFFSET SIZE
        else
            clog NAME OFFSET ZSIZE SIZE
        endif
    next i
else
    endian big
    get FILES long
    math BASE_OFF = FILES
    math BASE_OFF *= 0x48
    math BASE_OFF += 8
    for i = 0 < FILES
        getdstring NAME 0x40
        get OFFSET long
        get SIZE long
        math OFFSET += BASE_OFF
        log NAME OFFSET SIZE
    next i
endif
```

(updated for supporting the KIWAD archives)
## Post #3
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2010-06-21T10:20:21+00:00
- Post Title: Doom 2 XBOX Live

Thanks, you are the best
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-26T22:51:41+00:00
- Post Title: Doom 2 XBOX Live

an user made me notice the existence of some KIWAD archives but I don't know if they are for Doom 2 Xbox.
anyway I have edited the previous script for supporting also them
## Post #5
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2010-07-22T06:11:47+00:00
- Post Title: Doom 2 XBOX Live

Don't think there is any KIWAD files, but now with the new script it fails to extract the original archive 

New:

```
QuickBMS generic files extractor 0.4.5
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select the BMS script or plugin to use
- select the input archives/files to extract, type "" for whole folder and subfo
lders
- select the output folder where extracting the files
- open input file C:\584109B6\000D0000\Extracted\doom
2.disk
- open script C:\584109B6\000D0000\Extracted\doom2.bms
- set output folder C:\584109B6\000D0000\Extracted\doom2.disk_extract

  offset   filesize   filename
------------------------------
  9d191a9f 1095583034 \assets\xui.xzp

Error: incomplete input file number 0, can't read 1095583034 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted


Press RETURN to quit

```
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-05-11T05:19:51+00:00
- Post Title: Doom 2 XBOX Live

Does anyone save .disk unpacker - [http://www.se7ensins.com/forums/threads ... ker.81332/](http://www.se7ensins.com/forums/threads/doom-disk-unpacker.81332/) ?
