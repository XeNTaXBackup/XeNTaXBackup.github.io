## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-08-01T01:30:42+00:00
- Post Title: [Request] Tantra 2 .Dat files

Ok this its Tantra 2 files samples in the repository, hope somebody can take a view, the models and textures are stored in big .DAT files but i upload a little .DAT file. thanks.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-01T07:50:57+00:00
- Post Title: [Request] Tantra 2 .Dat files

it uses lzma compression but the dat files are encrypted probably with aes or another block cipher:

```
get EXT extension
if EXT == "dat"
    print "encryption not supported"
elif EXT == "ccdat"
    print "encryption not supported"
else
    get SIZE long
    savepos OFFSET
    get ZSIZE asize
    math ZSIZE -= OFFSET
    get NAME filename
    string NAME += "_unpacked"
    clog MEMORY_FILE OFFSET ZSIZE SIZE
    filexor 0x10
    log NAME 0 SIZE MEMORY_FILE
    filexor 0
endif
```
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-08-01T18:10:31+00:00
- Post Title: [Request] Tantra 2 .Dat files

> Reply from aluigi
>
> it uses lzma compression but the dat files are encrypted probably with aes or another block cipher:
Code: Select allcomtype lzma
get EXT extension
if EXT == "dat"
    print "encryption not supported"
elif EXT == "ccdat"
    print "encryption not supported"
else
    get SIZE long
    savepos OFFSET
    get ZSIZE asize
    math ZSIZE -= OFFSET
    get NAME filename
    string NAME += "_unpacked"
    clog MEMORY_FILE OFFSET ZSIZE SIZE
    filexor 0x10
    log NAME 0 SIZE MEMORY_FILE
    filexor 0
endif

.Dat its the models and textures,
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-02T13:13:48+00:00
- Post Title: [Request] Tantra 2 .Dat files

[this](http://www.tantraonline.ph) game right ?
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-08-02T19:23:32+00:00
- Post Title: [Request] Tantra 2 .Dat files

> Reply from Ekey
>
> this game right ?

yes but Tantra 2, new version, that its the samples i uploaded, and .DAT have models.DAT, Textures.DAT.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-02T19:47:44+00:00
- Post Title: [Request] Tantra 2 .Dat files

> Reply from Rimbros
>
> yes but Tantra 2, new version
Where download full client ?
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-08-04T17:06:37+00:00
- Post Title: [Request] Tantra 2 .Dat files

> Reply from Ekey
>
> Rimbros wrote:yes but Tantra 2, new version
Where download full client ?here you have client 

[《密传2》Download Client](http://download.ccjoy.com/mz/client/MZ2_Install_Full_4203.exe)

ok here samples of model,textures,sounds 

[Tantra 2 Archive Research Model](http://www.mediafire.com/download.php?i5051g86ci1nu5b)
[Tantra 2 Archive Research Texture](http://www.mediafire.com/download.php?nxz77b5ovlit1yb)
[Tantra 2 Archive Research Sounds](http://www.mediafire.com/download.php?h038t09r6bc31wt)
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-04T22:30:14+00:00
- Post Title: [Request] Tantra 2 .Dat files

File table where contained info about size , offset .ect. in SQL file (Compressed and XORed). In DAT files Only Compressed

launcherui.sql 

Info begin at 0xA offset

for launchercfg/patchui/bg.png



```
Uncompressed Size - 743460 (0xB5824)
Compressed Size - 741034 (0xB4EAA)
```

[http://www.mediafire.com/?85ua969igt91pjr](http://www.mediafire.com/?85ua969igt91pjr)

```

for
    4 Bytes - File Offset
    4 Bytes - Uncompressed Size
    4 Bytes - Compressed Size
    8 Bytes - LZMAProp
    String (0x100) - FileName
next
```


Parsing unpacked SQL something like that  

```

for i = 0
    get OFFSET long
    get SIZE long
    get ZSIZE long
    get LZMAPROP longlong
    getdstring NAME 0x100
    //log NAME 0 0
    print "%NAME%"
next i
```

_microclienturl.sql files game not using.
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-08-06T06:29:40+00:00
- Post Title: [Request] Tantra 2 .Dat files

Lol, hope. Thanks ekey hope u càn made a working inpack for .DAT files or this info help to aluigui to made a goog .dat unpacker. Thanks Man.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-06T13:17:13+00:00
- Post Title: [Request] Tantra 2 .Dat files

Approximately should look like this

```

comtype lzma86head

goto 0xA

for i = 0
    get OFFSET long 0
    get SIZE long 0
    get ZSIZE long 0
    get LZMAPROP longlong 0
    getdstring NAME 0x100 0
    clog NAME OFFSET ZSIZE SIZE
next i
```


But doesn't work.

```
- open input file D:\Tantra2_Build_4203\launchercfg\launcherui.sql_unpacked
  0011d1ad 64566      launchercfg/patchui/btn_hot.bmp

Error: incomplete input file number 0, can't read 12719 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted

Press RETURN to quit
```


I do not know why
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-08-07T08:17:04+00:00
- Post Title: [Request] Tantra 2 .Dat files

Maybe aluigui càn tell u why
