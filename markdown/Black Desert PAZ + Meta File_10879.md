## Post #1
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-15T17:25:42+00:00
- Post Title: Black Desert PAZ + Meta File

All you need is in Thread!
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-16T23:16:27+00:00
- Post Title: Black Desert PAZ + Meta File

Edited: Info deleted! Desire of developers!
## Post #3
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-17T04:11:18+00:00
- Post Title: Black Desert PAZ + Meta File

See End
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T06:07:12+00:00
- Post Title: Black Desert PAZ + Meta File

Same key.

directory table (begin offset 0x8A0568 (9047072), 78640 bytes) (first dword is table size)
file names table (begin offset 0x8B389C (9125716), 6458224 bytes) (first dword is table size)
## Post #5
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-17T06:13:52+00:00
- Post Title: Black Desert PAZ + Meta File

Oh not saw your post, sorry. I updated my one. Can you double check?
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T06:32:25+00:00
- Post Title: Black Desert PAZ + Meta File

> Reply from ehnoah
>
> Hey Ekey thanks!

I tried to decrypt *.Meta with following script:
Code: Select allencryption aes_128_cbc "\xF3\xA1\x0D\xF2\x47\xCC\x30\xC5\xEB\x11\x12\xAE\x07\x01\x52\x13" "" 0
get SIZE asize
log "dump.dat" 0 SIZE

Wrong I guess? Can you tell me where you got the Key? Or tell me if Key changes every patch?

(I Uploaded newest files here: http://www.sendspace.com/file/zp94zu) there is no patch till tomorrow)
You try decrypt full meta file. Need only specific blocks. Use like this

```
get DIR_TABLE_SIZE long
savepos DIR_TABLE_OFFSET
encryption aes_128_cbc "\xF3\xA1\x0D\xF2\x47\xCC\x30\xC5\xEB\x11\x12\xAE\x07\x01\x52\x13"
log "DirsTable.dat" DIR_TABLE_OFFSET DIR_TABLE_SIZE
encryption "" ""

goto 0x8B3F60
get NAME_TABLE_SIZE long
savepos NAME_TABLE_OFFSET
encryption aes_128_cbc "\xF3\xA1\x0D\xF2\x47\xCC\x30\xC5\xEB\x11\x12\xAE\x07\x01\x52\x13"
log "NamesTable.dat" NAME_TABLE_OFFSET NAME_TABLE_SIZE
encryption "" ""
```
## Post #7
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2013-10-17T06:51:12+00:00
- Post Title: Black Desert PAZ + Meta File

Don't you know compression type which used in paz , Ekey ?
I extracted dds files in some paz file, but they are compressed.

( Erase .zip extension  )
[4.dds.zip](https://xentaxbackup.github.io/file/6705_4.dds.zip)
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T07:08:07+00:00
- Post Title: Black Desert PAZ + Meta File

I dont know. I can not even upgrade the client lol.

Launcher say me this (XP not supported or???)



But game directly work without any problems, wtf!

[http://imageshack.us/a/img854/6808/zd6v.png](http://imageshack.us/a/img854/6808/zd6v.png)
## Post #9
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2013-10-17T08:09:24+00:00
- Post Title: Black Desert PAZ + Meta File

Where can I download the client?
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T09:13:15+00:00
- Post Title: Black Desert PAZ + Meta File

Edited: Info deleted! Desire of developers!
## Post #11
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-17T09:58:49+00:00
- Post Title: Black Desert PAZ + Meta File

I sent you an PM Ekey, nothing special. Just as note.

Will you finish a Script to extract? 

Because I don't see a way to use the File Tables in Quickbms. My Special wish are the sound files =/

I guess we should open the "Standard Client" without any patches or you don't think so?

@Ekey -> Yes mean not supported XP.

Edit: This should be code for Index or I am wrong?

```
get INDEX_TABLE_SIZE long
savepos INDEX_TABLE_OFFSET
log "IndexTable.dat" INDEX_TABLE_OFFSET INDEX_TABLE_SIZE
encryption "" ""

```
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T11:22:30+00:00
- Post Title: Black Desert PAZ + Meta File

> Reply from ehnoah
>
> I sent you an PM Ekey, nothing special. Just as note.

Will you finish a Script to extract?
Finish script? Huh i'm dont work over it.

> Reply from ehnoah
>
> 
@Ekey -> Yes mean not supported XP.
Strange. Game run without problems.

> Reply from ehnoah
>
> 
Edit: This should be code for Index or I am wrong?
Code: Select allgoto 0x20598
get INDEX_TABLE_SIZE long
savepos INDEX_TABLE_OFFSET
log "IndexTable.dat" INDEX_TABLE_OFFSET INDEX_TABLE_SIZE
encryption "" ""

You read my first post? Encrypted only 2 tables > Directory's and File Name's Table's
## Post #13
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-17T11:28:58+00:00
- Post Title: Black Desert PAZ + Meta File

Yes I try to understand but its pretty hard. So I trough I need run this script to "extract" the File from the File.

For me it looks like META File are 4 Files that need extracted and 2 of them crypted. Can you follow me?

With Script I mean something for Quickbms, I guess Quickbms Script need to read the META Files (the 4 one) 
and then extract all the PAZ or I am wrong?
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T11:52:23+00:00
- Post Title: Black Desert PAZ + Meta File

> Reply from ehnoah
>
> Yes I try to understand but its pretty hard. So I trough I need run this script to "extract" the File from the File.

For me it looks like META File are 4 Files that need extracted and 2 of them crypted. Can you follow me?

With Script I mean something for Quickbms, I guess Quickbms Script need to read the META Files (the 4 one) 
and then extract all the PAZ or I am wrong?
You need read all data from META: PAZ's IDs, Nums, Index for Dirs and file names and ect.

```
{
   DWORD   pPAZHash;	//ID (can be found in index for directories and file names)
   DWORD   pFilesCount;
   DWORD   pUnknown;
};

struct PAZEntry
{
   DWORD   pFileHash;	//ID
   DWORD   pNull;
   DWORD   pFileNum;
   DWORD   pOffset;
   DWORD   pSize;
   DWORD   nSize;		//again size - 16 bytes (additional???)
};
```
## Post #15
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2013-10-17T11:57:44+00:00
- Post Title: Black Desert PAZ + Meta File

i extracted more assets.
waiting for compression type revealed   

i guess it may be LZMA2_86HEAD type
but i failed.

they scrambled first 1 byte, LZMA2DEC Prop byte.
it should be less than 40, but they are always 111 ( 0x6F ).
[BlackDesert.zip](https://xentaxbackup.github.io/file/6706_BlackDesert.zip)
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T12:12:06+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

LOL 10min and launcher work perfect also on XP 

[http://imageshack.us/a/img818/716/0085.png](http://imageshack.us/a/img818/716/0085.png)
## Post #17
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-17T12:39:59+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Time to play Ekey *smile*

PS: I think I am out due I am just simply to dumb to extract files.
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-17T14:02:29+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

I don't understand how to retrieve the offset of the 2 encrypted tables in the meta file
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-17T14:52:21+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

yeah, because the paz table is at offset 0, the index is located after it and can be reached after having read the paz table, but I'm unable to find a way to locate where the other 2 remaining fields start or the size of the index field.

the compression of the files is strange because it looks very simpe (lzss or lzo) but there is something missing.
so I made a simple script to get the nameless files from the paz archives but no idea for the compressed ones:

*edit* removed, use [http://aluigi.org/papers/bms/others/blackdesert.bms](http://aluigi.org/papers/bms/others/blackdesert.bms)
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T15:18:01+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Okay how to:

1) Calc Offset and Size for Index table

IndexOffset = pPAZCount (11050) * 12 = 132600

Ok now we need goto to IndexOffset and get 3 dword's

DWORD pHash //???
DWORD pFilesCount //???
DWORD pIndexSize

pIndexSize = pIndexSize (318374) * 28 = 8914472

```
MUL EDX
```


Next you can see

DWORD (directory table size) : > directory table data
DWORD (name table size) : > name table data
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T16:18:16+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Edited: Info deleted! Desire of developers!
## Post #22
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-17T20:28:16+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

thanks a lot.
I have tried the pseudo code of the sub_41C680 function (with some modification to compile it) and it works, while Decompress doesn't seem stable but after all it's not strictly necessary.

so the only missing thing is the assigning of the filenames to the files, that Index table (the one with 7 entries of 0x1c bytes) is not so clear.
## Post #23
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-17T20:36:35+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

For me you two guys are simply gods. Can't say something else. If I follow your work you done here I just can take my hat. 

So much respect to you guys!
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-17T23:04:50+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

> Reply from aluigi
>
> thanks a lot.
I have tried the pseudo code of the sub_41C680 function (with some modification to compile it) and it works, while Decompress doesn't seem stable but after all it's not strictly necessary.
gj. btw: this algo i ripped from game updater.

Here from game client and it seems they are slightly different

Edited: Info deleted! Desire of developers!
## Post #25
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-18T08:16:59+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

here I have everything except the number of PAZ archive (pPAZFileNum) where is located the file assigned to the filename.

Do we have a full understanding of the index table?
This is what I have for the files linked in the first posts (0 meta and 1/2 paz):

```
    get FOLDER_NUM long # 48c 48c
    get FILE_NUM long   # 9ea5 e18d
    get DUMMY long      # 9ec c20
    get DUMMY long      # 4603c 261cc
    get DUMMY long      # 4a70 1970
    get DUMMY long      # 5f13 2000
```
the hex numbers in the comment are the values of the first and last entry.

Is it possible that pad00000.meta does *not* refer to pad00001.paz and pad00002.paz?
Because I see no relation between the values of meta and the first 2 paz files.
## Post #26
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T10:48:34+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Well here corrected header (8 bytes) and entry (12 bytes) for meta

Edited: Info deleted! Desire of developers!
## Post #27
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2013-10-18T11:20:36+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

PAZ archive has its own string table which is also encrypted with aes_128_cbc like meta file.

```

typedef struct tagPAZChunk
{
    uint32          mChecksum ;
    uint32          mDirectoryNameIndex ;
    uint32          mFileNameIndex ;
    uint32          mOffset ;
    uint32          mSize ;
    uint32          mUncompressedSize ;

    local uint32 bookMark = FTell() ;
    FSeek( mOffset ) ;
    CCData          mData( mSize ) ;
    FSeek( bookMark ) ;

} PAZChunk < bgcolor = cLtRed , read = ReadPAZChunk > ;

string ReadPAZChunk( PAZChunk& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( Name : %d, %d ) ( Offset : %d, Size : %d , %d )" ,
        data.mNameIndex1 , 
        data.mNameIndex2 , 
        data.mOffset , 
        data.mSize , 
        data.mUncompressedSize 
        ) ;
    return s ;
}

//------------------------------------------------------------------------

/**
    Archive Header
*/
typedef struct tagPAZHeader
{
    uint32          mChecksum ;
    uint32          mChunkCount ;
    uint32          mStringTableSize ;

    local uint32 i=0 ;
    for ( i=0 ; i < mChunkCount ; ++i )
    {
        PAZChunk    mChunkArray ;
    }

    CCData          mStringTable( mStringTableSize ) ;


} PAZHeader < bgcolor = cLtGray , read = ReadPAZHeader > ;

string ReadPAZHeader( PAZHeader& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( Checksum : 0x%x )( Chunk Count : %d )" ,
        data.mChecksum ,
        data.mChunkCount
        ) ;
    return s ;
}


//////////////////////////////////////////////////////////////////////////

LittleEndian() ;
//BigEndian() ;

PAZHeader               gHeader ;



```
## Post #28
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-18T11:31:45+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

I guess I have finished the script but I have not tested it because I don't have all the files:

[http://aluigi.org/papers/bms/others/blackdesert.bms](http://aluigi.org/papers/bms/others/blackdesert.bms)

You need the new version of quickbms for using it because I have added the new compression algorithm, I will release the new version in the next hours
Note: in the meantime if you want to check if it work just remove quickbmsver and replace blackdesert with copy in comtype.

The idea of reading the strings directrly from the PAZ archive is very good, now I'm going to test it.
## Post #29
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-18T11:37:11+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

I have checked one of the PAZ file but there is no names table there, just the header, the entries and the content of the files without "empty spaces".
## Post #30
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T12:06:51+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

> Reply from aluigi
>
> I guess I have finished the script but I have not tested it because I don't have all the files:

http://aluigi.org/papers/bms/others/blackdesert.bms

You need the new version of quickbms for using it because I have added the new compression algorithm, I will release the new version in the next hours
Note: in the meantime if you want to check if it work just remove quickbmsver and replace blackdesert with copy in comtype.

The idea of reading the strings directrly from the PAZ archive is very good, now I'm going to test it.
Thanks Luigi  

> Reply from aluigi
>
> I have checked one of the PAZ file but there is no names table there, just the header, the entries and the content of the files without "empty spaces".
In which Paz?
## Post #31
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-18T12:19:14+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

I checked pad00001.paz (and I bet that 2.paz is the same), there is no free space for string tables.
it contains only the files content
## Post #32
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T12:39:00+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

> Reply from aluigi
>
> I checked pad00001.paz (and I bet that 2.paz is the same), there is no free space for string tables.
it contains only the files content
Huh.

I dont know but they contained strings

PAZ00001.PAZ


PAZ00002.PAZ


I calculate strings offset like this: pStringTableOffset := pPAZHeader.dwTotalFiles * 24 + 12;
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T13:20:27+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

btw: aluigi check file and decompression > PAZ02072.PAZ. Contained 2 files. Second file have uncompressed size > 322905704 (321MB). Will it work?

Also some file name encoded by Utf8.
## Post #34
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-18T14:34:23+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

the new version of quickbms is out:
[http://quickbms.aluigi.org](http://quickbms.aluigi.org)

regarding the paz archives I used those posted by ehnoah, and if you sum the offset and size of the last file you reach the end of archive without unused bytes at the end.
maybe it's an old archive and they added the string tables in the new archives?

*edit* I'm rechecking the format, the error is for sure on my side
## Post #35
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-10-18T15:09:17+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

cool, script updated for supporting the handling of both meta and paz archives depending by what the user choice :)
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T15:47:21+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Tested and work perfect. Thanks
## Post #37
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T16:48:07+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

My small variant for PAZ's   ... Thanks to aluigi (Decompression algo) and to MrMoonKr (hint for strings in PAZ's).
## Post #38
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-18T17:13:56+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

You are all gods or you are? 

Time to find Archive with Sound Files =(
## Post #39
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T17:19:04+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

> Reply from ehnoah
>
> You are all gods or you are? 

Time to find Archive with Sound Files =(
Why? Use script for unpack all PAZ's, my tool unpack only single PAZ's (Open script, open meta, select output dir = profit)

[http://aluigi.org/papers/bms/others/blackdesert.bms](http://aluigi.org/papers/bms/others/blackdesert.bms)

PS: Output directory must where are all PAZ's
## Post #40
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-10-18T17:25:18+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Oh not saw this script >.<

Seems I was blind. Thanks. Thousand Kisses to you guys.
## Post #41
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T17:29:40+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Do not forget to update QuickBMS to latest version.
## Post #42
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-18T19:03:31+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Here i update my unpacker, select dir with paz's push extract all and profit 

Download: See below.
## Post #43
- Username: Razor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 10, 2008 5:55 pm
- Post datetime: 2013-10-19T19:18:27+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Thank you both for all your work
## Post #44
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-20T13:47:22+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

Updated again. Fixed problem with extracting large files (example -> PAD02072.PAZ -> on XP Out of memory)  , ugly progress dialog removed, info moved on panel.



Also remind you that there is a great script to extract the files 

[QuickBMS](http://aluigi.altervista.org/quickbms.htm) - version required > 0.5.27
Script: [http://aluigi.org/papers/bms/others/blackdesert.bms](http://aluigi.org/papers/bms/others/blackdesert.bms)

Download: See below
## Post #45
- Username: teoma
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 11, 2009 5:22 pm
- Post datetime: 2013-10-20T16:45:01+00:00
- Post Title: Re: Black Desert Client Research - PAZ + META File

hey Ekey , why when i'm trying to download your PAZ unpacker - it says me -  W32/Induc.A Virus.
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-20T18:04:26+00:00
- Post Title: Re: PAZ + Meta File

Edited: Tool removed from public! Desire of developers!
## Post #47
- Username: teoma
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 11, 2009 5:22 pm
- Post datetime: 2013-10-20T19:56:18+00:00
- Post Title: Re: PAZ + Meta File

Thx, but - how to open model.pac files inside of PAZ + texture and Buildings ?
## Post #48
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-20T22:26:17+00:00
- Post Title: Re: PAZ + Meta File

> Reply from teoma
>
> Thx, but - how to open model.pac files inside of PAZ + texture and Buildings ?
Post your request about 3d models > [here](http://forum.xentax.com/viewforum.php?f=16)
## Post #49
- Username: Rynage
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 31, 2013 9:55 pm
- Post datetime: 2013-11-02T18:25:02+00:00
- Post Title: Re: PAZ + Meta File

Hello,
Wanted to thank everyone who worked to achieve exporting Black Desert models / textures.
I would like to ask if you can work on animations to export ?
This is really important (I can be sure that not only for me).

Thank you,
Rynage!
## Post #50
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-02T19:13:23+00:00
- Post Title: Re: PAZ + Meta File

> Reply from Rynage
>
> Hello,
Wanted to thank everyone who worked to achieve exporting Black Desert models / textures.
I would like to ask if you can work on animations to export ?
This is really important (I can be sure that not only for me).

Thank you,
Rynage!
About 3d/2d models you can ask [here](http://forum.xentax.com/viewtopic.php?f=16&t=10909)
## Post #51
- Username: boltyn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 03, 2013 7:55 pm
- Post datetime: 2013-11-03T14:05:29+00:00
- Post Title: Re: PAZ + Meta File

can't find language file and file with properties of equipments/skills, somebody know where it can be and how to open it?
ps. thx  Ekey for unpacker.
## Post #52
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-03T15:17:59+00:00
- Post Title: Re: PAZ + Meta File

> Reply from boltyn
>
> can't find language file and file with properties of equipments/skills, somebody know where it can be and how to open it?
I guess maybe in XML's or DB..

> Reply from boltyn
>
> ps. thx  Ekey for unpacker.
Наздоровье
## Post #53
- Username: boltyn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 03, 2013 7:55 pm
- Post datetime: 2013-11-03T15:47:40+00:00
- Post Title: Re: PAZ + Meta File

> Reply from Ekey
>
> 
I guess maybe in XML's or DB..
see all files, cant find...
and i cant unpack "pad00000.meta", and dnt know for what it.

> Reply from Ekey
>
> DB..
dnt see any db files.

ps. cant open .bexcel file. he look as some db.
## Post #54
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-03T18:42:01+00:00
- Post Title: Re: PAZ + Meta File

> Reply from boltyn
>
> and i cant unpack "pad00000.meta", and dnt know for what it.
Meta contained info about PAZ files, nothing useful for you. bexcel can be as db.
## Post #55
- Username: boltyn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 03, 2013 7:55 pm
- Post datetime: 2013-11-04T01:16:08+00:00
- Post Title: Re: PAZ + Meta File

> Reply from Ekey
>
>  bexcel can be as db.
was try yo open it about 6 hours, and failed  too bad (
## Post #56
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-04T09:46:51+00:00
- Post Title: Re: PAZ + Meta File

> Reply from boltyn
>
> Ekey wrote: bexcel can be as db.
was try yo open it about 6 hours, and failed  too bad (
Because it's binary file. You can share here maybe someone can convert into readable file. btw why do you need open language? for edit? I mean game don't read files outside archives. 
You need patch meta file for add new CRC for each editable files also we dont have function for compress files, currently game on CBT stage and update client every day, therefore it's bad idea trying edit language
## Post #57
- Username: Rynage
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 31, 2013 9:55 pm
- Post datetime: 2013-11-04T11:38:41+00:00
- Post Title: Re: PAZ + Meta File

> Reply from Ekey
>
> boltyn wrote:Ekey wrote: bexcel can be as db.
was try yo open it about 6 hours, and failed  too bad (
Because it's binary file. You can share here maybe someone can convert into readable file. btw why do you need open language? for edit? I mean game don't read files outside archives. 
You need patch meta file for add new CRC for each editable files also we dont have function for compress files, currently game on CBT stage and update client every day, therefore it's bad idea trying edit language

True, at least when you translate WHOLE game there will be official one.
PS - Ekey, can you check pm please ?
## Post #58
- Username: boltyn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 03, 2013 7:55 pm
- Post datetime: 2013-11-04T11:45:26+00:00
- Post Title: Re: PAZ + Meta File

> Reply from Ekey
>
> Because it's binary file. You can share here maybe someone can convert into readable file. btw why do you need open language? for edit? I mean game don't read files outside archives.
need only for read.
i dnt know how pack it back. If somebody need - i can translate, but cant pack it back, too noob.
## Post #59
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-04T20:02:48+00:00
- Post Title: Re: PAZ + Meta File

> Reply from Rynage
>
> PS - Ekey, can you check pm please ?
PM is empty.

> Reply from boltyn
>
> need only for read.
i dnt know how pack it back. If somebody need - i can translate, but cant pack it back, too noob.
Anyway share bexel's files here.
## Post #60
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-04-20T16:06:25+00:00
- Post Title: Re: PAZ + Meta File

Big Edit:

File Format seems to got changed a bit!

Uploaded 2 Files:

[http://fbe.am/smT](http://fbe.am/smT)
## Post #61
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-21T21:31:25+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Seems key changed. Upload executables (launcher too) with all modules
## Post #62
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-04-21T23:56:50+00:00
- Post Title: Re: Black Desert PAZ + Meta File

[http://fbe.am/snu](http://fbe.am/snu)

All Binarys bin / bin64 + Launcher Stuff.

Thanks Ekey
## Post #63
- Username: archeagejp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 03, 2014 7:27 pm
- Post datetime: 2014-04-22T09:08:02+00:00
- Post Title: Re: Black Desert PAZ + Meta File

none.
## Post #64
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-04-22T11:27:06+00:00
- Post Title: Re: Black Desert PAZ + Meta File

I heard EN TXT is also in, maybe you find a way to call the EN Texts instead of the KR.

Maybe some Launch Command
## Post #65
- Username: Tibald
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 11, 2010 5:30 am
- Post datetime: 2014-04-22T13:39:38+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Ekey tell in what file you find key?
## Post #66
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-22T19:39:49+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Main executable
## Post #67
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-04-22T20:39:28+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Hope Ekey find new Key.

My Problem is mostly, that the exe is crypted,  I think AA was way easier.
## Post #68
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-22T21:13:36+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Now it's not AES. Yep executables packed with Themida as AA
## Post #69
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-04-22T21:41:25+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Ah so they changed the cryption at all?

Yeah but in ArcheAge I know the Offset where the Key is, for BD not 

I tried to search old Key via `HEX Editor in the EXE but not found it =/
## Post #70
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-23T10:39:58+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Edited: Info deleted! Desire of developers!
## Post #71
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-23T15:37:51+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Who can share not updated CBT2 client executable files? I dont have much HDD free space for download setup ^_^
## Post #72
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2014-04-23T16:38:20+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Ekey
>
> Who can share not updated CBT2 client executable files? I dont have much HDD free space for download setup ^_^
here [https://www.dropbox.com/s/28lrvmmj4xnaj ... 20CBT2.zip](https://www.dropbox.com/s/28lrvmmj4xnajbz/Black%20Desert%20CBT2.zip) o(∩_∩)o
## Post #73
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-23T19:04:51+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from yianti
>
> Ekey wrote:Who can share not updated CBT2 client executable files? I dont have much HDD free space for download setup ^_^
here https://www.dropbox.com/s/28lrvmmj4xnaj ... 20CBT2.zip o(∩_∩)o
Thanks, i'll try.
## Post #74
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-04-27T19:18:19+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Seems like it's impossible to open the new files  Good job @ Devs.
## Post #75
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-04-27T20:00:51+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Just take time :_>
## Post #76
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-27T20:32:01+00:00
- Post Title: Re: Black Desert PAZ + Meta File

In WIP guys. It's not so easy
## Post #77
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-04-28T07:28:16+00:00
- Post Title: Re: Black Desert PAZ + Meta File

As i said, I am sure, its freaking hard.
## Post #78
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-04-28T20:27:06+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Nevermind, got it
## Post #79
- Username: OutSide
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 12, 2013 9:39 pm
- Post datetime: 2014-04-28T20:40:12+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Can you tell how?
## Post #80
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-05-03T12:02:53+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Seems to be pretty hard.

Any Progress yet Ekey?
## Post #81
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-03T13:48:44+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Currently nope. Share main executable only if he updated.
## Post #82
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-05-03T14:52:04+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Upgraded Files (actual Patch)

[DOWNLOAD NOW!](http://fbe.am/sDJ)
## Post #83
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-05-07T07:59:33+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Hmm, still nothing? We might should try it on ownedcore
## Post #84
- Username: yukitairo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 14, 2014 9:46 pm
- Post datetime: 2014-05-10T22:38:29+00:00
- Post Title: Re: Black Desert PAZ + Meta File

It works, when you try to update it at first it fails, but just hit the button that's on the lower right:



It'll restart the patching and then you will begin to gain:



Hope this helps
## Post #85
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-05-11T16:04:14+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Beta's over now. If anyone is still working on this, I could upload the most up to date binaries.
## Post #86
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-05-12T12:50:59+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Sectus
>
> Beta's over now. If anyone is still working on this, I could upload the most up to date binaries.

I don't think that anyone is still working on it. It seems to be "uncrackable" for normal people.
## Post #87
- Username: Eleyo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 20, 2012 7:12 pm
- Post datetime: 2014-05-13T14:39:12+00:00
- Post Title: Re: Black Desert PAZ + Meta File

So, bms script and PAZUnpacker_0.4_Rebuilded both don't work now? Downloaded CBT2 client (black_setup_2014-04-19.exe), PAZUnpacker simply freezes, QuickBMS gives "Error: the script uses more array indexes (1922) than supported (1645)"
## Post #88
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-13T19:52:26+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Yep on CBT2 don't work
## Post #89
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-05-21T13:07:34+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Is there anyone who would open the client for money?
## Post #90
- Username: Tibald
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 11, 2010 5:30 am
- Post datetime: 2014-05-29T15:14:24+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Ekey
>
> here CBT2 algo. Currently i have no ideas how to realize.Ekey update please link
## Post #91
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-06-01T08:46:07+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Tibald
>
> Ekey wrote:here CBT2 algo. Currently i have no ideas how to realize.Ekey update please link

Guess his skills are not "high" enough to open the client. Trying to find another one since weeks, but i dont know where and how. I would even pay for it.
## Post #92
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-01T10:28:56+00:00
- Post Title: Re: Black Desert PAZ + Meta File

I'm not even going to do.... I just help to find new algo.
## Post #93
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-19T21:35:18+00:00
- Post Title: Re: Black Desert PAZ + Meta File

W.I.P 



Unpacked content
## Post #94
- Username: OutSide
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 12, 2013 9:39 pm
- Post datetime: 2014-06-20T13:31:36+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Can you share this? Or sell?)
## Post #95
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-20T15:32:19+00:00
- Post Title: Re: Black Desert PAZ + Meta File

It's W.I.P -> Work in Progress!

PS: DataBase Fully Parsed!
## Post #96
- Username: OutSide
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 12, 2013 9:39 pm
- Post datetime: 2014-06-28T18:40:34+00:00
- Post Title: Re: Black Desert PAZ + Meta File

any good news?)
## Post #97
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-06-29T09:06:38+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from OutSide
>
> any good news?)

I think Ekey's progress shown above is really good news
## Post #98
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-29T13:04:12+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Okay. Unpacker for CBT2 is released!

Edited: Tools removed from public! Desire of developers!
## Post #99
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2014-06-29T17:28:14+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Ekey
>
> Okay. Unpacker for CBT2 is released!

Good job  4 u Ekey
## Post #100
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-06-29T17:55:56+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Thanks a lot Ekey =)

Now does anyone still have working links to the client? ><
## Post #101
- Username: PeenusButter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 30, 2014 2:14 am
- Post datetime: 2014-07-05T00:33:45+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from o0Crofty0o
>
> Thanks a lot Ekey =)

Now does anyone still have working links to the client? ><
Yeah, someone posted a torrent on reddit I forgot the link but here's a magnet link to the CB2 client 

magnet:?xt=urn:btih:A634D79A11800935CD46F906EB9C582AD0F9DC01&dn=BlackDesert&tr=http%3a%2f%2fretracker.local%2fannounce
## Post #102
- Username: cga743
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 15, 2014 7:18 pm
- Post datetime: 2014-08-15T11:23:16+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Great ekey.....I have files from   moon blade ol by tencent, i can send you
## Post #103
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-15T11:35:55+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from cga743
>
> Great ekey.....I have files from   moon blade ol by tencent, i can send you
What?
## Post #104
- Username: Nanorat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 16, 2014 12:56 am
- Post datetime: 2014-08-17T19:40:12+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Does anyone still have the files from CBT2? The links on this topic are all dead, and I cant seem to find it anywhere.
## Post #105
- Username: Rynage
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 31, 2013 9:55 pm
- Post datetime: 2014-08-18T08:17:17+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Any news about animation ?
## Post #106
- Username: Timos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 15, 2014 10:12 pm
- Post datetime: 2014-08-24T18:19:43+00:00
- Post Title: Re: Black Desert PAZ + Meta File


## Post #107
- Username: Deadlymice
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 18, 2010 8:10 pm
- Post datetime: 2014-08-26T11:12:00+00:00
- Post Title: Re: Black Desert PAZ + Meta File

The animation format is rather confusing :S
I've spent the day looking at it and I can easily determine the number of bones in the animation and where the blocks of data for each bone is but I have had no luck decyphering the blocks of data.

From what I've gathered so far:

```
0x00000000		char				 fileId[4];         // 50 41 52 20 "PAR "
0x00000004		unsigned_int16	fileVersion;
0x00000006		BYTE				 unknownData[10];

// Animation Details
0x00000010		unsigned_int16	boneCount;
0x00000012		float				animationTime;     // ?? Unsure about this ??
0x00000016		BYTE				 unknownData[4];  // If animationTime isn't correct this might not even be 4 bytes

// Array of Bone Animation Data
0x0000001A	unsigned_int32		boneHash;           // Hash value of bone, can easily get all the locations for these from using the .PAB files for reference
// Unknown layout of bone animation data
// Following data next boneHash is present

```


As for the data in between the boneHash pairs (the hash value for a bone is the start of the data block), the minimum size appears to be 0x3A (58) and I think the next step up size is 0x4E (68)
These blocks seem to be universally starting with the following data:

```

```

And the data "E8 03" appears to pop up a lot during this data, I'm unsure of the significance of this. The data isn't in the same format that it's in in the PAB files and I don't think it's in a 4x3 matrix (the step between 0x3A and 0x4E if representative of another key frame isn't a big enough step for another matrix). I haven't even been able to determine where it indicates what frame or timestep the animation data is for. And given the step sizes I've seen between the data I'm not even sure if they are storing the scale, position & rotation of the bone for each point in time (I'd like to think they aren't using bone scales though but that might just be my feelings on the matter).
I have a bunch of bookmark files that I can upload for hex workshop if anyone is interested.

Incase anyone is curious about the bone (PAB) files, I use the following structure with Hex Workshop (load it and map the BoneFile structure to 0x0 of the file):

```

typedef struct FileHeader
{
	CHAR		fileId[4];
	USHORT	 fileVersion;

	BYTE		unknown[10];
} FileHeader;

typedef struct Matrix4x4
{
	FLOAT 		data[4][4];
} Matrix4x4;

typedef struct Vector3
{
	FLOAT		x;
	FLOAT		y;
	FLOAT		z;
} Vector3;

typedef struct Quaternion
{
	FLOAT		x;
	FLOAT		y;
	FLOAT		z;
	FLOAT		w;
} Quaternion;

typedef struct Bone
{
	ULONG		boneHash;
	BYTE		 boneNameLength;
	CHAR		 boneName[boneNameLength];
	ULONG		boneParent;

	Matrix4x4	 boneMatrix;
	Matrix4x4	 boneMatrixInverse;
	Matrix4x4	 boneLocalMatrix;
	Matrix4x4	 boneLocalMatrixInverse;
	Vector3		boneScale;
	Quaternion	boneRotation;
	Vector3		bonePosition;

	BYTE			unknown[2];
} Bone;

struct BoneFile
{
	FileHeader	   fileHeader;

	USHORT			 boneCount;
	Bone 			  bones[boneCount];
};

```
## Post #108
- Username: mykolag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 7:22 pm
- Post datetime: 2014-09-08T23:13:19+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Thanks works. waiting for CBT3 client
## Post #109
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-09T12:56:46+00:00
- Post Title: Re: Black Desert PAZ + Meta File

If someone got access for CBT3 let me know.
## Post #110
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-09-15T13:15:38+00:00
- Post Title: Re: Black Desert PAZ + Meta File

.
## Post #111
- Username: archeagejp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 03, 2014 7:27 pm
- Post datetime: 2014-09-15T22:34:55+00:00
- Post Title: Re: Black Desert PAZ + Meta File

none.
## Post #112
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2014-09-16T11:01:39+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Ekey's tool works fine for CBT3 as well   

( It would be more better if extraction could be applied to single paz   )
## Post #113
- Username: mykolag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 7:22 pm
- Post datetime: 2014-09-16T15:30:01+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Yes, PAZUnpacker works fine with CBT3.
Unpacked folder has 53,380,549,877 bytes
CBT3 - 6000 paz's files (CBT2 - 8822).
## Post #114
- Username: guardgold
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 17, 2014 6:29 pm
- Post datetime: 2014-09-17T10:54:08+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Ekey
>
> teoma wrote:hey Ekey , why when i'm trying to download your PAZ unpacker - it says me -  W32/Induc.A Virus.
Thanks for reporting. Here i attach new recompiled version and now it's 100% cleared!


Results: here

Thank you!
## Post #115
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2014-09-18T05:36:55+00:00
- Post Title: Re: Black Desert PAZ + Meta File

some normal map textures are mis-extracted.
their fourCC are 0x7C000000, but should be 0x44445320.
## Post #116
- Username: archeagejp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 03, 2014 7:27 pm
- Post datetime: 2014-09-18T08:17:56+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Has anyone ever extracted the client data files(cbt3)?

I extracted the sound files, but it wasn't playable on anything.

The same situation as this topic.
[viewtopic.php?f=17&t=11603](http://forum.xentax.com/viewtopic.php?f=17&t=11603)
## Post #117
- Username: mykolag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 7:22 pm
- Post datetime: 2014-09-18T22:16:04+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from archeagejp
>
> Has anyone ever extracted the client data files(cbt3)?

I extracted the sound files, but it wasn't playable on anything.

The same situation as this topic.
viewtopic.php?f=17&t=11603

Did you apply latest 4 patches?
I think CBT3 client will have more updates sooooon...
## Post #118
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-09-19T11:20:37+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from mykolag
>
> archeagejp wrote:Has anyone ever extracted the client data files(cbt3)?

I extracted the sound files, but it wasn't playable on anything.

The same situation as this topic.
viewtopic.php?f=17&t=11603

Did you apply latest 4 patches?
I think CBT3 client will have more updates sooooon...

How did you extract the CB3 FIles?
## Post #119
- Username: mykolag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 7:22 pm
- Post datetime: 2014-09-19T13:30:50+00:00
- Post Title: Re: Black Desert PAZ + Meta File

You can use PAZUnpacker for CBT3 too.
## Post #120
- Username: janii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 22, 2014 2:52 am
- Post datetime: 2014-09-21T19:04:42+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Hmmm Pazunpacker says "out of memory" after a minute of freeze
What does it mean?

Yup either crashes or I get that error. 
Anything else doesnt happen
## Post #121
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2014-09-28T17:00:48+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Anyone had luck with the Music Files yet?
## Post #122
- Username: webset
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 30, 2014 1:56 am
- Post datetime: 2014-09-30T10:18:02+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Hey guys,
did anybody find database file?
I found just bexcel file (binary), if this is it, do you know how to convert it to readable format (like sql)?
## Post #123
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-30T16:10:46+00:00
- Post Title: Re: Black Desert PAZ + Meta File

bexcel is database
## Post #124
- Username: webset
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 30, 2014 1:56 am
- Post datetime: 2014-09-30T21:17:57+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Ekey
>
> bexcel is database
Yeah, right, but it's a binary file and I have no ideas how to get datas from the file.
## Post #125
- Username: mykolag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 7:22 pm
- Post datetime: 2014-10-13T05:31:41+00:00
- Post Title: Re: Black Desert PAZ + Meta File

The bexcel has easy format. Overall 120 tables.
## Post #126
- Username: Alakazahm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 08, 2014 7:30 pm
- Post datetime: 2014-11-09T09:13:00+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Hello everyone ! 

Thanks to you guys for the unpacker which is great!   

I was trying to find a way to reverse the script to turn games data into PAZ...is it possible?   

Kind regards !
## Post #127
- Username: darsig
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 30, 2010 10:08 pm
- Post datetime: 2014-11-09T13:03:02+00:00
- Post Title: Re: Black Desert PAZ + Meta File

thanks for BD client tools ppl, you work is great.
But is there any chance for working quickbms script? I want to make english patch for client when korean OBT starts and I need to pack XML files back to client somehow after translation is done.
## Post #128
- Username: darsig
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 30, 2010 10:08 pm
- Post datetime: 2014-11-18T09:01:36+00:00
- Post Title: Re: Black Desert PAZ + Meta File

also if any help in reading datasheets.bexcel data? I'm making database of BD and got info only from xml files. "Unpacking" bexcel'll help a lot
## Post #129
- Username: mykolag
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 7:22 pm
- Post datetime: 2014-11-18T13:18:38+00:00
- Post Title: Re: Black Desert PAZ + Meta File

@darsig: You can use [http://form1ca.ru/bdo](http://form1ca.ru/bdo) or [http://blackdesertdatabase.com/](http://blackdesertdatabase.com/) as wiki/database - IMHO, no need to create one more
## Post #130
- Username: gti810
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 14, 2014 12:56 am
- Post datetime: 2014-12-10T05:41:19+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Hello !

This page is KR OBT client download file !

[https://drive.google.com/file/d/0B8Ct98 ... sp=sharing](https://drive.google.com/file/d/0B8Ct98M-Bv0DTWtiakJ6LUhaLXc/view?usp=sharing)
## Post #131
- Username: Deso
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 10, 2014 6:23 pm
- Post datetime: 2014-12-10T10:27:44+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from gti810
>
> Hello !

This page is KR OBT client download file !

https://drive.google.com/file/d/0B8Ct98 ... sp=sharing

The link provided contains the installation file for the launcher which then is used to download the client. However, they have blocked the download for international users.
The workaround is simple though, I personally used OpenVPN with an South Korean IP.

* Connect to a Korean IP
* Launch the downloader.
* Pause the download, disconnect from the VPN
* Continue the download with your regular internet speed (I get a solid 3mb/sec)

I will have a go with the un-packer posted earlier and see if the formats still the same.
## Post #132
- Username: sungchu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 11, 2014 10:17 am
- Post datetime: 2014-12-11T02:19:33+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Ekey
>
> Okay. Unpacker for CBT2 is released!

wow! cool guy..!
## Post #133
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2014-12-11T03:21:55+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Black Desert 2014-12-10  Download 
[http://pan.baidu.com/s/1nt4yqrJ](http://pan.baidu.com/s/1nt4yqrJ)
## Post #134
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2014-12-12T07:24:08+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Ekey's tool works fine for OBT as well   

May i get your source code for the tool or decryption code, Ekey ?
I want to make a viewer which can load assets directly from the archives.
## Post #135
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2014-12-14T00:16:38+00:00
- Post Title: Re: Black Desert PAZ + Meta File

I'll leave this here just in case:

[https://www.youtube.com/watch?v=UPER4ZVKvvk](https://www.youtube.com/watch?v=UPER4ZVKvvk)
## Post #136
- Username: bobdole
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 15, 2014 8:07 am
- Post datetime: 2014-12-15T16:04:35+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Ekey, algorithm please.
## Post #137
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-15T16:08:46+00:00
- Post Title: Re: Black Desert PAZ + Meta File

All posts cleared. Tools and info from public removed! Who already have the tools, please do not share on Public!! Due to [DMCA takedown](http://www.dmca.com/FAQ/What-is-a-DMCA-Takedown) notice received! Desire of developers!

Thank you for understanding!
## Post #138
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-15T18:41:23+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Reversing is happening in here for years and now it need to be wiped, for what reason ? Game files not shared, as far as i understand DMCA notice is only to sharing file, not on tools made by 3th parties? I would like to understand this and im pretty sure everyone else as well. Im sorry but this is absolutely against all what we doing in here. Means from now on if any developer declare Desire of developers! we will drop everything and leave it? Im really surprise and specialy it comes from person like Ekey...  Dont get me wrong, im ok with this i do not even care about this game, i would just like to understand what is going on in here...
## Post #139
- Username: designgears
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2014 4:34 am
- Post datetime: 2014-12-19T16:45:51+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from michalss
>
> Reversing is happening in here for years and now it need to be wiped, for what reason ? Game files not shared, as far as i understand DMCA notice is only to sharing file, not on tools made by 3th parties? I would like to understand this and im pretty sure everyone else as well. Im sorry but this is absolutely against all what we doing in here. Means from now on if any developer declare Desire of developers! we will drop everything and leave it? Im really surprise and specialy it comes from person like Ekey...  Dont get me wrong, im ok with this i do not even care about this game, i would just like to understand what is going on in here...

I have everything that was wiped from the thread, I can repost it.
## Post #140
- Username: zakalla
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 29, 2012 8:08 am
- Post datetime: 2014-12-22T22:02:54+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from designgears
>
> I have everything that was wiped from the thread, I can repost it.
This would be nice, but dev requests... hnnnngh
## Post #141
- Username: VcahwithKud
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jun 26, 2014 12:59 pm
- Post datetime: 2014-12-24T18:17:09+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Ekey
>
> All posts cleared. Tools and info from public removed! Who already have the tools, please do not share on Public!! Due to DMCA takedown notice received! Desire of developers!

Thank you for understanding!

"Tools and info from public removed......." I am looking forward them maybe one year. it's too sad to hear that.
## Post #142
- Username: sfsdf53453
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 30, 2015 6:36 pm
- Post datetime: 2015-09-01T09:05:39+00:00
- Post Title: Re: Black Desert PAZ + Meta File

please some one reupload source code in this thread . even private share or send a hint sould be appreciate .
learning to reverse enginering real file from real game is big rock that i haven't try before .
## Post #143
- Username: roserapple
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 14, 2015 1:29 pm
- Post datetime: 2015-09-13T07:16:48+00:00
- Post Title: Re: Black Desert PAZ + Meta File

I need to make nude patch... T T
## Post #144
- Username: DarknessStorm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 18, 2015 5:39 am
- Post datetime: 2015-10-17T22:08:10+00:00
- Post Title: Re: Black Desert PAZ + Meta File

greetings. can somebody re-share tools from Ekey? (or in pm, if you don't want share in public)
thanks )
## Post #145
- Username: DarknessStorm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 18, 2015 5:39 am
- Post datetime: 2015-10-26T12:56:30+00:00
- Post Title: Re: Black Desert PAZ + Meta File

soo...no one?
## Post #146
- Username: FoxSingle
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 21, 2015 1:32 am
- Post datetime: 2015-10-30T16:21:05+00:00
- Post Title: Re: Black Desert PAZ + Meta File

> Reply from Ekey
>
> Okay. Unpacker for CBT2 is released!

Edited: Tools removed from public! Desire of developers!


Welcome, you can share the tool? Throw a link in PM please)) I would be grateful.
## Post #147
- Username: mrpeter01
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 01, 2015 6:16 pm
- Post datetime: 2015-11-01T10:25:08+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Hopefully anyone can share tools for me . I will use for my private interest without sharing on public. Really appreciate your help ^^ .
## Post #148
- Username: lxxxk
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 02, 2014 1:33 pm
- Post datetime: 2015-11-01T10:56:33+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Useless post why not delete
## Post #149
- Username: JackKnife
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 17, 2016 4:00 am
- Post datetime: 2016-09-16T20:30:13+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Can someone PM me so I can download please? I'd like to use the tools for personal use. Nothing commercial, entirely educational. Please respond with a yes/no answer.

Many thanks!
## Post #150
- Username: hassuny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 27, 2016 4:46 pm
- Post datetime: 2016-09-27T17:20:57+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Do the .pazunpacker exist anymore? if so, could someone please pm me?!
## Post #151
- Username: calypsoup
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Sep 12, 2016 3:51 am
- Post datetime: 2016-09-27T18:32:46+00:00
- Post Title: Re: Black Desert PAZ + Meta File

i really want this tool too ! please someone send me ! i ll use for self use not public
## Post #152
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-01-17T00:55:45+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Any chance of sharing the script info in PM? I have no way of extracting the pac files
## Post #153
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2019-11-06T17:45:40+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Hopefully anyone can share tools for me . I will use for my private interest without sharing on public. Really appreciate your help ^^ .
## Post #154
- Username: ginev
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Feb 15, 2016 6:53 pm
- Post datetime: 2020-01-21T13:38:37+00:00
- Post Title: Re: Black Desert PAZ + Meta File

Can someone update the Blender .pab (static models) script?Because i cannot open some of the models.I can provide you with example .pam model files but i need someone who know ho update the scripts.Someone?
