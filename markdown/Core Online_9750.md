## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-16T22:07:19+00:00
- Post Title: Core Online

Here is the game core online the archives look xored.
client download
[http://download.entwell.com/download/fg ... loader.exe](http://download.entwell.com/download/fgt/client/CoreDownloader.exe)
website
[http://www.coreonline.co.kr/main.do](http://www.coreonline.co.kr/main.do)

if you just want the main exe's to get the xor key pm me for a sample.


incomplete quickbms script.
will extract and decrypt uncompressed files.

```
idstring "MFFP"
get null long
get files long
for i = 0 < files
get MFFC long
get null long
get zsize long
get size long
get unk long
getdstring null 0x10
get nsize short
get unk1 short
getdstring name nsize
savepos offset
if zsize == size
filexor "0xF0 0x2E 0xAA 0x3C 0xE4 0xCD 0x11 0x89 0xD1 0xA5 0x45 0xAF 0xC3 0x43 0x52 0x4A 0xA3 0xBE 0x6C 0x82 0xFE 0xF1 0x31 0x63 0x2F 0x39 0xCF 0xA1 0xFA 0xDC 0xF0 0x2E 0xAA 0x3C 0xE4 0xCD 0x11 0x89 0xD1 0xA5 0x45 0xAF 0xC3 0x43 0x52 0x4A 0xA3 0xBE 0x6C 0x82 0xFE 0xF1 0x31 0x63 0x2F 0x39 0xCF 0xA1 0xFA 0xDC"
log name offset zsize
filexor ""
endif
math offset + zsize
goto offset
next i

```
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-17T01:34:04+00:00
- Post Title: Core Online

the filelist is currently offline (CoreDownloader.ini)
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-17T02:24:05+00:00
- Post Title: Core Online

here are direct links
[http://download.entwell.com/download/fg ... /setup.exe](http://download.entwell.com/download/fgt/client/setup.exe)
[http://download.entwell.com/download/fg ... /setup.ini](http://download.entwell.com/download/fgt/client/setup.ini)
[http://download.entwell.com/download/fg ... 0x0412.ini](http://download.entwell.com/download/fgt/client/0x0412.ini)
[http://download.entwell.com/download/fg ... Online.msi](http://download.entwell.com/download/fgt/client/CoreOnline.msi)

[http://download.entwell.com/download/fg ... /Data1.cab](http://download.entwell.com/download/fgt/client/Data1.cab)
[http://download.entwell.com/download/fg ... Data12.cab](http://download.entwell.com/download/fgt/client/Data12.cab)
[http://download.entwell.com/download/fg ... /Data2.cab](http://download.entwell.com/download/fgt/client/Data2.cab)
[http://download.entwell.com/download/fg ... Data21.cab](http://download.entwell.com/download/fgt/client/Data21.cab)
[http://download.entwell.com/download/fg ... /Data3.cab](http://download.entwell.com/download/fgt/client/Data3.cab)
[http://download.entwell.com/download/fg ... Data31.cab](http://download.entwell.com/download/fgt/client/Data31.cab)
[http://download.entwell.com/download/fg ... /Data4.cab](http://download.entwell.com/download/fgt/client/Data4.cab)
[http://download.entwell.com/download/fg ... Data41.cab](http://download.entwell.com/download/fgt/client/Data41.cab)
[http://download.entwell.com/download/fg ... /Data5.cab](http://download.entwell.com/download/fgt/client/Data5.cab)
[http://download.entwell.com/download/fg ... Data51.cab](http://download.entwell.com/download/fgt/client/Data51.cab)
[http://download.entwell.com/download/fg ... /Data6.cab](http://download.entwell.com/download/fgt/client/Data6.cab)
[http://download.entwell.com/download/fg ... Data61.cab](http://download.entwell.com/download/fgt/client/Data61.cab)
[http://download.entwell.com/download/fg ... /Data7.cab](http://download.entwell.com/download/fgt/client/Data7.cab)
[http://download.entwell.com/download/fg ... Data71.cab](http://download.entwell.com/download/fgt/client/Data71.cab)
[http://download.entwell.com/download/fg ... /Data8.cab](http://download.entwell.com/download/fgt/client/Data8.cab)
[http://download.entwell.com/download/fg ... Data81.cab](http://download.entwell.com/download/fgt/client/Data81.cab)
[http://download.entwell.com/download/fg ... /Data9.cab](http://download.entwell.com/download/fgt/client/Data9.cab)
[http://download.entwell.com/download/fg ... Data91.cab](http://download.entwell.com/download/fgt/client/Data91.cab)
[http://download.entwell.com/download/fg ... Data10.cab](http://download.entwell.com/download/fgt/client/Data10.cab)

edit. they must of removed the links after they saw i downloaded them? lol
## Post #4
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2012-10-18T06:38:24+00:00
- Post Title: Core Online

i cannot find the xor keys, just first four.   

```

typedef struct ( uint32 size )
{
    char                mData[ size ] ;

} BINData < bgcolor = cLtAqua , read = ReadBINData > ;

string ReadBINData( BINData& data )
{
    string s = "(no data)" ;

    char fourCC[5] ;
    fourCC[0] = data.mData[0] ^ 0xF0 ;
    fourCC[1] = data.mData[1] ^ 0x2E ;
    fourCC[2] = data.mData[2] ^ 0xAA ;
    fourCC[3] = data.mData[3] ^ 0x3C ;
    fourCC[4] = 0 ;

    SPrintf( s , "( %s )" ,
        fourCC
        ) ;
    return s ;
}


//------------------------------------------------------------------------

typedef struct
{
    char                mFourCC[4] ;                ///< "MFFC"
    uint32              mZero ;
    uint32              mSize ;
    uint32              mUncompressedSize ;
    uint32              mType ;                     ///< 1 for normal, 

    uint32              mUnknown1[2] ;
    uint32              mUnknown2[2] ;
    
    uint16              mNameSize ;
    uint16              mPadding ;
    char                mName[mNameSize] ;

    BINData             mData( mSize ) ;            ///< encrypted


} BINChunk < bgcolor = cLtPurple , read = ReadBINChunk > ;

string ReadBINChunk( BINChunk& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( %d )( %s )( %s )" ,
        data.mType ,
        data.mFourCC ,
        data.mName
        ) ;
    return s ;
}

//------------------------------------------------------------------------

/**
    archive file header
*/
typedef struct
{
    char                mFourCC[4] ;            ///< "MFFP"
    uint32              mZero ;
    uint32              mChunkCount ;

    local uint32 i=0 ;
    for ( i=0 ; i < mChunkCount ; ++i )
    {
        BINChunk        mChunkArray ;
    }

} BINHeader < bgcolor = cLtGray , read = ReadBINHeader > ;

string ReadBINHeader( BINHeader& header )
{
    string s = "(no data)" ;
    SPrintf( s , "( %s )( Chunks : %d )" ,
        header.mFourCC ,
        header.mChunkCount
        ) ;
    return s ;
}

//////////////////////////////////////////////////////////////////////////

LittleEndian() ;
//BigEndian() ;

BINHeader               gHeader ;




```
## Post #5
- Username: Ekey
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-18T19:44:14+00:00
- Post Title: Core Online

this is the one key you found part of.

```
F02EAA3CE4CD1189D1A545AFC343524AA3BE6C82FEF131632F39CFA1FADCF02EAA3CE4CD1189D1A545AFC343524AA3BE6C82FEF131632F39CFA1FADC
```


the compression is unkown.
I have found it decodes the first part of the file correctly but then has problems using this compression in quickbms.
COMP_COMPRLIB_RLE3, // scan 230

these other compressions produce somewhat close results also
    COMP_COMPRLIB_RLE1,
    COMP_COMPRLIB_RLE2,

I will upload the client tomorrow so people can have a look.

Game client 10 parts
[http://www.sendspace.com/file/fcfvsh](http://www.sendspace.com/file/fcfvsh) - part1
[http://www.sendspace.com/file/0aii63](http://www.sendspace.com/file/0aii63) - part2
[http://www.sendspace.com/file/6uzqua](http://www.sendspace.com/file/6uzqua) - part3
[http://www.sendspace.com/file/qqx8vs](http://www.sendspace.com/file/qqx8vs) - part4
[http://www.sendspace.com/file/fjqxbz](http://www.sendspace.com/file/fjqxbz) - part5
[http://www.sendspace.com/file/ax99es](http://www.sendspace.com/file/ax99es) - part6
[http://www.sendspace.com/file/1vm45y](http://www.sendspace.com/file/1vm45y) - part7
[http://www.sendspace.com/file/422lgf](http://www.sendspace.com/file/422lgf) - part8
[http://www.sendspace.com/file/u16fqg](http://www.sendspace.com/file/u16fqg) - part9
[http://www.sendspace.com/file/nshu1f](http://www.sendspace.com/file/nshu1f) - part10
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-20T18:20:31+00:00
- Post Title: Core Online

Thanks for sharing. Compressed files you mean textures or what ?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-20T18:52:50+00:00
- Post Title: Core Online

the files where zsize != size.
the compression is not known can you post the decompression routine.
my script only extracts uncompressed things where the zip size == decompressed size.
just let me know if any more information is needed i can give specifics.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-20T20:55:01+00:00
- Post Title: Core Online

Ok decompression algo i found.

```
{
  unsigned int result;
  int v4;
  int v5;
  char v6;
  char v7;
  int v8;
  __int16 v9;
  int v10;
  char v11;
  int v12;
  char v13;
  signed int v14;
  __int16 v15;
  int v16;
  char v17[4096];
  int v19;
  int v20;

  v4 = szInBuf;
  v5 = 0;
  memset(v17, 0, 0x1000u);
  result = 0;
LABEL_2:
  v6 = *(BYTE *)v4;
  v15 = *(BYTE *)v4++;
  v16 = 0;
  while ( v6 >= 0 )
  {
    v13 = *(BYTE *)v4;
    if ( szUncompressedSize > result )
    {
      *(BYTE *)(szOutBuf + result++) = v13;
      v17[(signed __int16)v5] = v13;
      v5 = (v5 + 1) & 0xFFF;
      v14 = 1;
    }
    else
    {
      v14 = 0;
    }
    ++v4;
    if ( !v14 )
      return 0;
LABEL_13:
    v6 = 2 * v15;
    v15 *= 2;
    ++v16;
    if ( v16 == 8 )
      goto LABEL_2;
  }
  v7 = *(BYTE *)v4;
  if ( !*(BYTE *)v4 )
    return result;
  v9 = 16 * (256 - (unsigned __int8)(v7 & 0xF0)) - *(BYTE *)(v4 + 1);
  v10 = (v7 & 0xF) + 2;
  v8 = (unsigned __int16)v10;
  v4 += 2;
  v20 = v4;
  if ( !(WORD)v10 )
    goto LABEL_13;
  while ( 1 )
  {
    v12 = (signed __int16)v5;
    v11 = v17[((signed __int16)v5 + v9) & 0xFFF];
    if ( szUncompressedSize <= result )
      return 0;
    *(BYTE *)(szOutBuf + result) = v11;
    --v8;
    ++result;
    v5 = (v5 + 1) & 0xFFF;
    v17[v12] = v11;
    if ( !(WORD)v8 )
    {
      v4 = v20;
      goto LABEL_13;
    }
  }
}
```


For compressed files used fist decompression and after xor. Seems somewhere I have seen it this func.

Edited: Key only = 30 bytes 

F02EAA3CE4CD1189D1A545AFC343524AA3BE6C82FEF131632F39CFA1FADCF02EAA3CE4CD1189D1A545AFC343524AA3BE6C82FEF131632F39CFA1FADC

```
		0xF0, 0x2E, 0xAA, 0x3C, 0xE4, 0xCD, 0x11, 0x89, 0xD1, 0xA5,
		0x45, 0xAF, 0xC3, 0x43, 0x52, 0x4A, 0xA3, 0xBE, 0x6C, 0x82,
		0xFE, 0xF1, 0x31, 0x63, 0x2F, 0x39, 0xCF, 0xA1, 0xFA, 0xDC};
```
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-21T01:30:50+00:00
- Post Title: Core Online

Here tool and dll for test.

```
        COTestDecompress <inFILE> <outFILE> <uSize>

[Example]
        COTestDecompress ability.xml ability.xml.unc 3210308
```


Examples files and source's (c++) included. >>[COTestDecompress](http://www.sendspace.com/file/rfiva1)<< and Library >>[COLib](http://www.sendspace.com/file/hdz4j3)<<

```
unsigned int __cdecl CO_Decompress(int szOutBuf, unsigned int szUncompressedSize, int szInBuf)
```
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-21T15:09:11+00:00
- Post Title: Core Online

Bin Unpacker.

```
        COBINExtract <inFile>

[Example]
        COBINExtract Cvs.bin
```


Have fun 
[COBINExtract_0.1.rar](https://xentaxbackup.github.io/file/5910_COBINExtract_0.1.rar)
## Post #11
- Username: pixellegolas
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-21T17:01:44+00:00
- Post Title: Core Online

very cool should have models soon.
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-21T17:17:30+00:00
- Post Title: Core Online

Models looks like awesome. You are fast
## Post #13
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-10-22T09:59:10+00:00
- Post Title: Core Online

Together we are strong and nothing cant be converted
## Post #14
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2012-10-22T15:31:37+00:00
- Post Title: Core Online

Thanks for sharing client files, how did you extract the models? Have you managed to find texture files and bone data?
## Post #15
- Username: Diol
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 05, 2017 6:37 am
- Post datetime: 2019-04-30T04:28:27+00:00
- Post Title: Core Online

Hello!
I'm really interested in getting the client file from this game, all the links are dead
Is it possible to share it again? Much appreciated!!
