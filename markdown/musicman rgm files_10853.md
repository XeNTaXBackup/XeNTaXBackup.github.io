## Post #1
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-08T08:19:06+00:00
- Post Title: musicman rgm files???

Header: ABCCBFEC ??
Looks compressed？
[http://www52.zippyshare.com/scaled/50685523/file.html](http://www52.zippyshare.com/scaled/50685523/file.html)

could u try to extract the rgm files???
[DatePalm_RT_002.rar](https://xentaxbackup.github.io/file/6686_DatePalm_RT_002.rar)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-08T09:57:01+00:00
- Post Title: musicman rgm files???

Dunno about this file, i have modified script for unpack PCG archives.

```
# 
# Original script for Hot Dance 5 by Fatduck
#
# Modified for MusicMan by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype zlib_noerror

idstring "snail_package"
get VERSION long
get FILES long
get DUMMY long
get TABLESIZE long
getdstring NULLS 32

for i = 0 < FILES
    get NSIZE byte
    get FLAG byte
    if FLAG == 0xFF
        math NSIZE -= 256
        math NSIZE *= -1
    endif
    getdstring NAME NSIZE
    get SIZE long
    getdstring HASH 32
    get OFFSET long
    get ZSIZE long
    getdstring NULLS 72
	
    if ZSIZE == SIZE
       log NAME OFFSET SIZE
    else
       clog NAME OFFSET ZSIZE SIZE
    endif
next i
```


Resources

```
{
   DWORD   pID; //0xABCCBFEC
   SHORT    pUnknown1;
   SHORT    pUnknown2;
   DWORD   pDataOffset;
};

struct DataEntry
{
   DWORD   pUnknown1; //Hash / CRC ???
   DWORD   pCompressedSize;
};

   BYTE {pCompressedSize} - Compressed File Data
```


Compressed data begin with 0x789C. Seems zlib but comtype_scan and offzip give useless results.
## Post #3
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-08T10:51:15+00:00
- Post Title: musicman rgm files???

thx script,but MusicMan file no PCG archives，no snail_package Header。

Game Client Direct link [http://download.mm.d1xn.com/MusicMan_Setup.exe](http://download.mm.d1xn.com/MusicMan_Setup.exe)

here Some samples,wav,ogg,dds,xml
[http://www27.zippyshare.com/v/94646685/file.html](http://www27.zippyshare.com/v/94646685/file.html)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-08T11:24:52+00:00
- Post Title: musicman rgm files???

PCG archives you can found on this path MusicMan\D1XN\Main\
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-09-20T15:59:56+00:00
- Post Title: musicman rgm files???

I think the files are deflate compression but after the header its encrypted.
