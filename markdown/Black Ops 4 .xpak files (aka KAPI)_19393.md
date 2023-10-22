## Post #1
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2019-01-26T16:40:34+00:00
- Post Title: Black Ops 4 .xpak files (aka KAPI)

I'm quite surprised this topic is still not in the forum since the game was released for 3+ months already.

So the game contains a lot of .xpak files which are known as KAPI file storages. The old script that was used for Black Ops 3, i.e. [http://aluigi.org/bms/cod_kapi.bms](http://aluigi.org/bms/cod_kapi.bms), seem to be a little outdated with BO4 as some xpax files have new flag 0x08. A quick look says that only big files can have this flag.

Uploaded a few samples. `core_common.xpak` file has new 0x08 flag, others seem to be fine.

Samples link: [http://www.mediafire.com/file/h8kmr3fna ... k.zip/file](http://www.mediafire.com/file/h8kmr3fnaljoofh/bo4xpak.zip/file)
## Post #2
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2019-02-26T05:55:24+00:00
- Post Title: Black Ops 4 .xpak files (aka KAPI)

So yesterday I decided to look again into this. Here is what I was able to figure out:

KAPI version is 11. Well, that's easy to find.

And here are a few other things I noticed:

- Every file with KAPI header contained 4 definitions of file data:

1. Files data (encrypted/compressed/whatnot)
2. Some meta-data(?) probably. 3x u64, first one is UUID, the other two I couldn't figure out.
3. File indices (from what I noticed - list of 8 byte UUIDs)
4. Text description of files

- Most of the files have unknown chunk flag 0x8
- Text description of files is file UUID + string of meta-data

Files content can be matched with text meta-data based on UUID but that's the case if files data in file is in the same order as UUIDs from 3rd definition. Maybe 2nd definition contains order information based on offsets.

Here is a bms script to extract only files data and 010Editor template for those curious. I will try to finish the latter to parse other definitions.

The bms script is based on [cod_kapi.bms](https://zenhax.com/viewtopic.php?t=1723) script by aluigi which didn't work with v11.

[@aluigi](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=889), might you please look into this? Your script tells to contact you with unknown flags 

cod_bms_v11.bms

```
get ZERO short
get VER short

if VER > 10
    get DUMMY longlong
    get KAPI_SIZE longlong
    
    #for SECTION = 0
        get FILES longlong
        get OFFSET longlong
        get SIZE longlong
        
        if OFFSET == 0 || OFFSET u> KAPI_SIZE
            break
        endif
        
        savepos SECTION_OFF
        goto OFFSET
        
        for i = 0 < FILES
            savepos OFFSET
            get CHUNKS long
            get DUMMY long
            
            if CHUNKS u< 0xffff
                if CHUNKS == 0xa7a7a7a7
                    break
                endif
                
                set FILESIZE long 0
                
                for c = 0 < CHUNKS
                    get CHUNK_META long
                    
                    xmath FILESIZE "FILESIZE + (CHUNK_META & 0x00FFFFFF)"
                next c
                
                padding 128
                savepos CHUNKS_OFFSET
                print "Offset %CHUNKS_OFFSET|X%"
                log "" CHUNKS_OFFSET FILESIZE
                
                goto FILESIZE 0 SEEK_CUR
                padding 128
            endif
        next i

        goto SECTION_OFF
    #next SECTION

endif

```


010Editor template that parses entire file:

```
//--- 010 Editor v9.0 Binary Template
//
//      File: 
//   Authors: 
//   Version: 
//   Purpose: 
//  Category: 
// File Mask: 
//  ID Bytes: 
//   History: 
//------------------------------------------------

local char KAPI_HEADER[4] = "KAPI";

uint Normalize(uint value) {
    return Ceil(value / 128.0) * 128;
}

struct KapiFile {
    struct KapiFileData (uint chunks) {
        local int c;
        local uint chunk_size;
        local uint filesize = 0;
        local int chunk_flags;
        
        for (c = 0; c < chunks; c++) {
            uint chunk_meta <bgcolor=0x00FF00, name="Chunk Meta">;
            chunk_size = chunk_meta & 0x00FFFFFF;
            chunk_flags = (chunk_meta & 0xFF000000) >> 24;
            Assert(chunk_flags == 0 || chunk_flags == 8 || chunk_flags == 0xCF, "Chunk flag is not 0, 8 or 0xCF!");
            filesize += chunk_size;
        }
        
        FSeek(foffset + 0x80);
        
        byte contents[Normalize(filesize)] <bgcolor=0x00FF00, name="Contents">;
    };
    
    local uint foffset = FTell();
    uint64 chunks <bgcolor=0x00FF00, name="Chunks Count">;
    
    if (chunks < 0xFFFF) {
        if (chunks == 0xA7A7A7A7A7A7A7A7) {
            break;
        }
        KapiFileData filedata(chunks) <name="File Data">;
    }
};

struct KapiFiles(uint64 files_count) {
    local uint i;
    for (i = 0; i < files_count; i++) {
        KapiFile file <name="File">;
    }
};

struct KapiMeta(uint64 files_count) {
    struct KapiFileMeta {
        uint64 id <bgcolor=0x00FF00, name="ID">;
        uint64 no_idea1 <bgcolor=0x0000FF>;
        uint64 no_idea2 <bgcolor=0x0000FF>;
    };
    
    local uint i;
    for (i = 0; i < files_count; i++) {
        KapiFileMeta meta <name="Meta">;
    }
};

struct KapiIndices(uint64 files_count) {
    // files_count can be many times bigger than in KapiFiles
    local uint i;
    for (i = 0; i < files_count; i++) {
        uint64 id <bgcolor=0x00FF00, name="ID">;
    }
};

struct KapiText(uint64 files_count) {
    struct KapiFileDesc {
        uint64 id <bgcolor=0x00FF00, name="ID">;
        uint64 text_length <bgcolor=0x00FF00, name="Text Length">;
        char text[text_length] <bgcolor=0x00FF00>;
    };
    local uint i;
    for (i = 0; i < files_count; i++) {
        KapiFileDesc file_desc <bgcolor=0x00FF00, name="File Desc">;
    }
};

struct KapiBlock(int type) {
    uint64 files_count <bgcolor=0x00FF00, name="Files Count">;
    uint64 offset <bgcolor=0x00FF00, name="Offset">;
    uint64 size <bgcolor=0x00FF00, name="Data Size">;
    
    if (offset == 0 || size == 0 || offset > kapisize) {
        break;
    }
    
    local uint fpos = FTell();
    FSeek(offset);
    
    switch (type) {
        case 1: KapiFiles files(files_count); break;
        case 2: KapiMeta meta(files_count); break;
        case 3: KapiIndices indices(files_count); break;
        case 4: KapiText text_index(files_count); break;
    }
    
    FSeek(fpos);
};

struct KapiData {
    uint64 files <bgcolor=0x00FF00, name="Files Count">;
    uint64 offset <bgcolor=0x00FF00, name="Offset">;
    uint64 size <bgcolor=0x00FF00, name="Data Size">;
};

struct KAPI11 {
    uint64 dummy <bgcolor=0x0000FF>;
    uint64 kapisize <bgcolor=0x00FF00>;
    
    KapiBlock block(1);
    KapiBlock block(2);
    KapiBlock block(3);
    KapiBlock block(4);
};

struct {
    uchar signature[4] <bgcolor=0x00FF00, name="Signature">;
    Assert(signature == KAPI_HEADER, "Wrong file format!");
    ushort zero <bgcolor=0x00FF00>;
    ushort version <bgcolor=0x00FF00, name="Version">;
    
    if (version > 10) {
        KAPI11 kapi;
    }
} file <name="KAPI">;

```
