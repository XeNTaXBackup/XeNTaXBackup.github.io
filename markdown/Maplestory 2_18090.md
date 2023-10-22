## Post #1
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-13T04:18:55+00:00
- Post Title: Maplestory 2

Been digging into the closed beta lately and I have yet to see one central cohesive place where anyone is documenting any of their efforts so in hopes of starting some cohesive efforts before I have to divide myself away for finals. Hoping someone can pick things up with this info. Open to more questions as well.

At the moment the best IDA pro databases you can make for yourself are by suspending Maplestory2.exe and opening the process in IDA Pro to do a live analysis and eventually saving your database once you've analyzed enough of the relevant modules(such as kernel32 and mfc90) or else you'll run into calls into import pools that lead to seemingly random addresses(be sure to analyse the mfc90 and kernel32 modules and so forth before saving your database as there are no IATs).

Here are some links. Note that these are transfer.sh links that will expire in about 2 weeks.

[https://transfer.sh/157KM2/Library.m2h](https://transfer.sh/157KM2/Library.m2h)
[https://transfer.sh/f3m0i/Library.m2d](https://transfer.sh/f3m0i/Library.m2d)
[https://transfer.sh/KRGUE/Movie.m2h](https://transfer.sh/KRGUE/Movie.m2h)
[https://transfer.sh/bXdPg/Movie.m2d](https://transfer.sh/bXdPg/Movie.m2d)
[https://transfer.sh/fEmN3/Shaders.m2h](https://transfer.sh/fEmN3/Shaders.m2h)
[https://transfer.sh/Aaqw2/Shaders.m2d](https://transfer.sh/Aaqw2/Shaders.m2d)
[https://transfer.sh/Tw455/asset-web-metadata.m2h](https://transfer.sh/Tw455/asset-web-metadata.m2h)
[https://transfer.sh/jR3Ak/asset-web-metadata.m2d](https://transfer.sh/jR3Ak/asset-web-metadata.m2d)

Archives come in couples of "m2h" and "m2d" files such that there is a "Header" and the Data that the header is binded to. Format is different depending on the 4-byte header as well as the size of the headers which I have yet to map out fully due to vtable hell but the sizes are all determinant.

Magic - Size
---------------
MS2F - 0x3C
NS2F - 0x34
OS2F - 0x38
PS2F - 0x38
After these 4 bytes is the header bytes. And then followed by a base64 stream:


I've traced enough to get several of the XOR keys and the pools of 128 AES Keys and Initialization Vectors which it seems to select at run time.


The game uses CryptoPP as its encryption middleware and exposes plenty of strings and RTTI symbols to find out where things are at. The above disassembly is CryptoPP's usual Source-Sink pattern of decrypting a stream concisely:



In the above pic you'll see it setting up a string source, base64 decoder, some decryptor, and a string sink and a call to what turns out to be [SetKeyWithIV](https://github.com/weidai11/cryptopp/blob/7c1d296283fab97a2a5d34445b8c4adca0b9ea0e/cryptlib.h#L664) where it picks from a "vault" of 128 possible(the `& 0x7F` is the same as a `% 128`) 32-byte(256 bit) keys and a 16-byte(128 bit) initialization vector. The way it selects one of these 128 keys is based on one of the fields of the header(Internally named 'PackFileHeaderVer1' for the 'MS2F' files) using the 64-bit integer at 0x24. After the initial base64-decoding. The stream is optionally decrypted with a xor pad and decompressed using [zlib](https://www.zlib.net/manual.html)'s "inflate".

Here's all the keys.

[https://transfer.sh/CFU1d/MS2FIVVault.bin](https://transfer.sh/CFU1d/MS2FIVVault.bin)
[https://transfer.sh/njxur/MS2FKeyVault.bin](https://transfer.sh/njxur/MS2FKeyVault.bin)

[https://transfer.sh/gRr2l/NS2FXORKey.bin](https://transfer.sh/gRr2l/NS2FXORKey.bin)
[https://transfer.sh/q6k2p/OS2FXORKey.bin](https://transfer.sh/q6k2p/OS2FXORKey.bin)
[https://transfer.sh/NhpYd/PS2FXORKey.bin](https://transfer.sh/NhpYd/PS2FXORKey.bin)
[https://transfer.sh/PqM52/MS2FXORKey.bin](https://transfer.sh/PqM52/MS2FXORKey.bin)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-05-13T10:49:33+00:00
- Post Title: Maplestory 2

Do you have EN CBT client?
## Post #3
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-14T07:11:11+00:00
- Post Title: Maplestory 2

> Reply from Ekey
>
> Do you have EN CBT client?
Here's all the client data for the english closed beta.
[https://mega.nz/#!eK4T3LbL!ejsWFNipuow1 ... P0mbXxMJyI](https://mega.nz/#!eK4T3LbL!ejsWFNipuow1WK3PUzSTtTsCpBafGIFk9P0mbXxMJyI)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-05-14T11:43:10+00:00
- Post Title: Maplestory 2

Thanks for client. As I see for NS2F, OS2F and PS2F keys and vectors are generated individually.

```
{
  switch ( a1 )
  {
    case 0x4632534D:
      return sub_49FBF0(a2, a3, a4, a5);
    case 0x4632534E:
      return sub_49FE20(a2, a3, a4, a5);
    case 0x4632534F:
      return sub_4A0050(a2, a3, a4, a5);
    case 0x46325350:
      return sub_4A0280(a2, a3, a4, a5);
  }
  return 0;
}
```


MS2F (Static keys)



NS2F (Dynamic keys)



OS2F (Dynamic keys)



PS2F (Dynamic keys)



That keys generates this call int sub_48EED0() or it's more like pointers



Seems j_mfc90_265 is a malloc.

```
buffer = (char*) malloc (512);
```
## Post #5
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-14T19:24:11+00:00
- Post Title: Maplestory 2

I noticed these too. It generates the other keys based on some xoring of the static MS2F keys and the associated static XorKey for the NS2F and so forth though I did not find any files that used these headers. They are allocated on the heap and will have to be dumped at runtime if we want them.

I made a megafolder with the keys and client.

[https://mega.nz/#F!DbxEAL5S!MvLhvAcyusMF4kp6_qBXYA](https://mega.nz/#F!DbxEAL5S!MvLhvAcyusMF4kp6_qBXYA)

I was in the middle of mapping out the vtables and logic for MS2F files(Internally called PackFileHeaderVer1) before I had to part. This is what I got in my little utility library before I had to part with my main workstation.

```
MapleStory2.exe:015CC9DC ; const PackFileStream<class CPackStreamVer1>::`vftable'
MapleStory2.exe:015CC9DC ??_7?$PackFileStream@VCPackStreamVer1@@@@6B@ dd offset sub_579430
MapleStory2.exe:015CC9DC                                         ; DATA XREF: CPackStreamVer1_Ctor+27↑o
MapleStory2.exe:015CC9E0 dd offset ??_R4?$PackFileStream@VCPackStreamVer1@@@@6B@_0 ; const PackFileStream<CPackStreamVer1>::`RTTI Complete Object Locator'
MapleStory2.exe:015CC9E4 ; CPackStreamVer1Vtable PackFileStream<CPackStreamVer1>::`vftable'
MapleStory2.exe:015CC9E4 ??_7?$PackFileStream@VCPackStreamVer1@@@@6B@_0 CPackStreamVer1Vtable <offset CPackStreamVer1Vtable__Dtor, \
MapleStory2.exe:015CC9E4                                         ; DATA XREF: CPackStreamVer1_Ctor+21↑o
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__GetHeaderSize, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__GetBufferPtr, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_C, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__GetCompressedSize?,\
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_14, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__GetLength?, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__GetVersion?, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_20, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_24, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__SetMagic, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_2C, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_30, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_34, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_38, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_3C, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_40, \
MapleStory2.exe:015CC9E4                        offset CPackStreamVer1Vtable__field_44>
```


The header structures do not consider the 4 Magic bytes.

```
{
public:
        Util::Field<0x00, std::uint32_t> Unknown00;
        Util::Field<0x04, std::uint64_t> Unknown04;
        Util::Field<0x0C, std::uint64_t> Unknown0C; // Compressed Size?
        Util::Field<0x14, std::uint64_t> Unknown14;
        Util::Field<0x1C, std::uint64_t> Unknown1C; // Size?
        Util::Field<0x24, std::uint64_t> Unknown24; // Version?
        Util::Field<0x2C, std::uint32_t> Unknown2C;
        Util::Field<0x30, std::uint32_t> Unknown30;
        Util::Field<0x34, std::uint64_t> Unknown34;

private:
        Util::Padding<0x3C> Pad;
};
```


The "version" flag(named it that might it's above 128 at times and probably means something other than just a straight up "KeyIndex") might be what is used to determine which of the 128 keys that it uses from the Key/IV LUT(after a % 128) from what I've seen.

Here's the full decryption pseudo code which i made some guesses for.

```
  PackFile = PackFile_1;
  Length = 0;
  this[24] = 0;
  v8 = PackFile->vtable->GetLength_(PackFile);
  mfc_Alloc_0(v8);
  Buffer = v9;
  v32 = v9;
  Size = (PackFile->vtable->GetLength_)(PackFile, &Length, 0);
  ReadFile(FileHandle, Buffer, Size, BytesRead, Overlapped);
  IsCompressedFunc? = PackFile->vtable->GetCompressedSize_;
  PackFile_1 = 0;
  if ( !(*(IsCompressedFunc?(PackFile, &FileHandle) + 3) & 1) )
  {
    KeyIndex_1 = PackFile->vtable->GetVersion_(PackFile);
    v14 = (*(*CFileSystem[55] + 8))(            // AES decrypt
            CFileSystem[57],
            Buffer,
            Length,
            &PackFile_1,
            KeyIndex_1);
    if ( v14 && PackFile_1 )
    {
      mfc90_free(v32);
      v32 = 0;
      goto LABEL_7;
    }
LABEL_32:
    mfc90_free(v32);
    return 0;
  }
  KeyIndex = PackFile->vtable->GetVersion_(PackFile);
  v14 = (*(*CFileSystem[56] + 8))(              // Xor Decrypt
          CFileSystem[57],
          Buffer,
          Length,
          &PackFile_1,
          KeyIndex);
  if ( !v14 || !PackFile_1 )
    goto LABEL_32;
LABEL_7:
  if ( v14 != PackFile->vtable->GetVersion_(PackFile) || v16 )
  {
    if ( v32 )
    {
      mfc90_free(v32);
      return 0;
    }
    return 0;
  }
  if ( *PackFile->vtable->GetCompressedSize_(PackFile, &FileHandle) )// Compression
  {
    v21 = Compressed;
    v22 = 0;
    CFileSystem[26] = *a4;
    CFileSystem[27] = v21;
    if ( v21 )
    {
      while ( 1 )
      {
        if ( !CFileSystem[24] )
        {
          v23 = Length;
          v24 = PackFile_1 + v22;
          v22 += Length;
          v25 = CFileSystem[38] < Length;
          CFileSystem[38] -= Length;
          CFileSystem[23] = v24;
          CFileSystem[24] = v23;
          CFileSystem[39] -= v25;
        }
        if ( *(CFileSystem + 19) )
          v26 = 0;
        else
          v26 = 4;
        v27 = zlib_inflate(CFileSystem + 23, v26);
        if ( v27 == -5 )
        {
          mfc90_free(PackFile_1);
          return 0;
        }
        if ( v27 )
          break;
        if ( !CFileSystem[27] )
        {
          mfc90_free(PackFile_1);
          return 0;
        }
      }
      if ( v27 == 1 )
      {
        *a6 = Compressed - CFileSystem[27];
        goto LABEL_28;
      }
      mfc90_free(PackFile_1);
      result = 0;
    }
    else
    {
      v28 = a6;
      v29 = HIDWORD(Compressed);
      *a6 = Compressed;
      v28[1] = v29;
LABEL_28:
      mfc90_free(PackFile_1);
      result = 1;
    }
  }
  else
  {
    v18 = *(CFileSystem + 19) - Length;
    if ( v18 >= 0 )
    {
      *(CFileSystem + 19) = v18;
    }
    else
    {
      CFileSystem[38] = 0;
      CFileSystem[39] = 0;
    }
    v19 = a6;
    a6[1] = 0;
    v20 = a4;
    *v19 = v14;
    j_msvcr90_memcpy(*v20, PackFile_1, v14);
    mfc90_free(PackFile_1);
    result = 1;
  }
  return result;

```
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-05-14T21:14:35+00:00
- Post Title: Maplestory 2

> Reply from DEElekgolo
>
> I did not find any files that used these headers
Xml.m2h used NS2F. About headers: is not to hard

```
{
   uint64_t   dwMagic;
};

struct MS2FSubHeader
{
   uint64_t   dwTOCZSize; //compressed size (zlib) also it's a KeyIndex
   uint64_t   dwTOCESize; //encoded size
   uint64_t   dwFileListSize;  //uncompressed size
   uint64_t   dwFileListZSize;  //compressed size (zlib) also it's a KeyIndex
   uint64_t   dwFileListESize; //encoded size
   uint64_t   dwTotalFiles;
   uint64_t   dwTOCSize; //uncompressed size
};

struct NS2FSubHeader
{
   uint32_t   dwTotalFiles;
   uint64_t   dwTOCZSize; //compressed size (zlib) also it's a KeyIndex
   uint64_t   dwTOCESize; //encoded size
   uint64_t   dwTOCSize; //uncompressed size
   uint64_t   dwFileListZSize; //compressed size (zlib) also it's a KeyIndex
   uint64_t   dwFileListESize; //encoded size
   uint64_t   dwFileListSize; //uncompressed size
};
```


Example on asset-web-metadata file:

1) Read data by dwFileListESize = 340 bytes
2) Decode and decrypt by Base64 + AES and you got size equal dwFileListZSize = 254 bytes
3) Decompress it (dwFileListSize = 480 bytes) and we got list of filenames like

```
2,awebckpt.nt
3,awebinst.nt
4,canonical.nt
5,cn.nt
6,dds.nt
7,emergent-flat-model.nt
8,emergent-world.nt
9,enums.nt
10,fx-shader-compiled.nt
11,gamebryo-animation.nt
12,gamebryo-scenegraph.nt
13,gamebryo-sequence-file.nt
14,image.nt
15,kr.nt
16,llid.nt
17,logpath.nt
18,lua-behavior.nt
19,model.nt
20,name.nt
21,nuts.nt
22,png.nt
23,precache.nt
24,relpath.nt
25,script.nt
26,shader.nt
27,soup.nt
28,x-shockwave-flash.nt
29,x-world.nt

```


Repeat for TOC table

1) Read data by dwTOCESize = 756 bytes
2) Decode and decrypt by Base64 + AES and you got size equal dwTOCZSize = 565 bytes
3) Decompress it (dwTOCSize = 1392 bytes) and we got table of contents (see attach)

```
{
   uint32_t   dwNull;
   uint32_t   dwFileID; //equal to the number from the filelist
   uint64_t   dwUnknown; //dunno what this (flags ?) : always 0xEE000009
   uint64_t   dwOffset;
   uint64_t   dwESize; //encoded size
   uint64_t   dwZSize; //compressed size
   uint64_t   dwSize; //uncompressed size
};

```

[asset-web-metadata_tables.rar](https://xentaxbackup.github.io/file/14363_asset-web-metadata_tables.rar)
## Post #7
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-15T00:39:20+00:00
- Post Title: Maplestory 2

Looks solid!
Can't wait to dive in once I get back and I can make a little general purpose extractor.
Looks like repackaging is even possible. Back when this was a Korea-only game some others had made an English translation patch I believe that involved edits to the m2h and m2d files.
## Post #8
- Username: Ewol
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 16, 2018 9:55 pm
- Post datetime: 2018-05-16T14:27:03+00:00
- Post Title: Maplestory 2

Keep us updated on the extractor. 

I spent all night trying to figure out how to get into those files, but it's quite clearly way above my head.
## Post #9
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-17T07:04:34+00:00
- Post Title: Maplestory 2

Wedged in some time to make a quick little decryptor. Can fully open MS2F m2h/m2d files and read/decrypt file data. Hoping to aim it to fully "mounting" the Data folder and recreating the internal virtual file system that "CFileSystem" implements






ATM I don't have the keys for N/O/PS2F files as they are generated at runtime as a multidimensional array though the generation for the keys can be pretty trivially recreated.

Some xoring and swizzling to the effect of:

Which is a ( (i + 5 ) % 8 ) offset from the XOR key lookup. Would probably be much quicker to dump the multidimensional array from memory( which is a pointer to 512 bytes which is 128 pointers to the keys and IVs and such ).

Since the beta is over it might be harder to do some runtime analysis to dump the keys from memory but running the exe directly unpacks it enough that it can be derived. Something I don't have the time atm for but would allow for `NS2F` files and such to be handled.
## Post #10
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-17T09:16:43+00:00
- Post Title: Maplestory 2

some dumps from Image.m2h/m2d
## Post #11
- Username: Ewol
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 16, 2018 9:55 pm
- Post datetime: 2018-05-17T10:33:05+00:00
- Post Title: Maplestory 2

Will you be sharing the tool once it's ready?
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-05-17T12:48:43+00:00
- Post Title: Maplestory 2

Looks good, keep going
## Post #13
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-18T03:29:58+00:00
- Post Title: Maplestory 2

> Reply from Ewol
>
> Will you be sharing the tool once it's ready?
Sure. Though I am developing this remotely in a linux environment(compatible with windows but will involve some hoop-jumping to get it to build. Uses CMake and CryptoPP).
I can post the source code once its ready for the public and I can just post a fully dumped version of the game for all to pick through.

At the moment I just need to find time to get NS2F and O/PS2F keys to get my program to recursively dump and flatten out all possible m2h/m2d files it runs into.
## Post #14
- Username: Miyu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 03, 2016 6:39 pm
- Post datetime: 2018-05-22T21:55:17+00:00
- Post Title: Maplestory 2

I uploaded the tools and library that I created when I made the english patches. There is an extractor and a creator tool on my github: [https://github.com/Miyuyami/MS2Tools](https://github.com/Miyuyami/MS2Tools).
Both of them use the library I created which is here: [https://github.com/Miyuyami/MS2Lib](https://github.com/Miyuyami/MS2Lib). This is where you can also find the NS2F, OS2F and PS2F IV and Key pairs that are missing from this thread.

I hope that those tools are not too scuffed/broken and that will help the people interested in this.
## Post #15
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-26T11:48:42+00:00
- Post Title: Maplestory 2

Been updating my tool a bit with some of the internal structures and the elusive OS2F/PS2F ones while I can.

I updated the mega folder with all the keys as well as a fully dumped and "flattened" version of the CBT files for anyone browsing this thread to poke through(MapleStory2-CBT-May18-Dumped.zip ~12GB) Each m2h/m2d pair has a folder by the same name created with the entire runtime virtual file system flattened out.

[https://mega.nz/#F!DbxEAL5S!MvLhvAcyusMF4kp6_qBXYA](https://mega.nz/#F!DbxEAL5S!MvLhvAcyusMF4kp6_qBXYA)

```

Dump
└── MapleFiles
    ├── appdata
    │   ├── BlackCipher
    │   ├── Custom
    │   │   ├── Cube
    │   │   └── Equip
    │   ├── Data
    │   │   ├── lua
    │   │   │   └── Precompiled
    │   │   ├── Resource
    │   │   │   ├── asset-web-config
    │   │   │   ├── asset-web-metadata
    │   │   │   ├── Exported
    │   │   │   ├── gfx
    │   │   │   ├── Gfx
    │   │   │   ├── Image
    │   │   │   ├── Library
    │   │   │   ├── Model
    │   │   │   ├── Movie
    │   │   │   ├── PrecomputedTerrain
    │   │   │   └── Shaders
    │   │   ├── Shaders
    │   │   │   └── PreGenerated
    │   │   ├── Sound
    │   │   └── Xml
    │   │       ├── achieve
    │   │       ├── additionaleffect
    │   │       ├── camera
    │   │       ├── effect
    │   │       ├── emotion
    │   │       ├── excel
    │   │       ├── exportedugcmap
    │   │       ├── groundeffect
    │   │       ├── item
    │   │       ├── itemoption
    │   │       ├── itempreset
    │   │       ├── map
    │   │       ├── mapxblock
    │   │       ├── masteryhomemade
    │   │       ├── musicscore
    │   │       ├── npc
    │   │       ├── object
    │   │       ├── pet
    │   │       ├── quest
    │   │       ├── riding
    │   │       ├── script
    │   │       ├── skill
    │   │       ├── string
    │   │       ├── table
    │   │       ├── trigger
    │   │       ├── ugcmap
    │   │       └── ui
    │   ├── locales
    │   ├── Microsoft.VC90.CRT
    │   └── Microsoft.VC90.MFC
    └── patchdata

```


[Also here's a full list of banned words for the English CBT for kicks](https://pastebin.com/raw/Q7XcYFMn)
## Post #16
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-27T02:33:03+00:00
- Post Title: Re: Maplestory 2

Nif models are able to be opened and exportedin [Noesis](http://www.richwhitehouse.com/index.php?content=inc_projects.php&showproject=91).
## Post #17
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-05-30T18:17:52+00:00
- Post Title: Re: Maplestory 2

Put all my code up on github.

Includes an expander and a flattener and works for all four file PackStream versions, including the elusive OS2F/PS2F.

[https://github.com/Wunkolo/Maple2Tools](https://github.com/Wunkolo/Maple2Tools)

For reader's sake here's all the mapped out structures:

```
{
public:
	std::uint32_t Pad;                    // Always zero

	std::uint64_t FATCompressedSize;      // DEFLATE length
	std::uint64_t FATEncodedSize;         // Base64 length

	std::uint64_t FileListSize;           // Uncompressed size
	std::uint64_t FileListCompressedSize; // DEFLATE length
	std::uint64_t FileListEncodedSize;    // Base64 length

	std::uint64_t TotalFiles;             // Total Files
	std::uint64_t FATSize;                // Uncompressed size
};
static_assert(
	sizeof(PackStreamVer1) == 0x3C,
	"sizeof(PackStreamVer1) != 0x3C"
);

struct PackStreamVer2 // NS2F
{
public:
	std::uint32_t TotalFiles;             // Total Files

	std::uint64_t FATCompressedSize;      // DEFLATE length
	std::uint64_t FATEncodedSize;         // Base64 length
	std::uint64_t FATSize;                // Uncompressed size

	std::uint64_t FileListCompressedSize; // DEFLATE length
	std::uint64_t FileListEncodedSize;    // Base64 length
	std::uint64_t FileListSize;           // Uncompressed size
};
static_assert(
	sizeof(PackStreamVer2) == 0x34,
	"sizeof(PackStreamVer2) != 0x34"
);

struct PackStreamVer3 // OS2F/PS2F
{
	std::uint32_t TotalFiles;             // Total Files
	std::uint32_t Pad;                    // Always Zero

	std::uint64_t FATCompressedSize;      // DEFLATE length
	std::uint64_t FATEncodedSize;         // Base64 length

	std::uint64_t FileListCompressedSize; // DEFLATE length
	std::uint64_t FileListEncodedSize;    // Base64 length
	std::uint64_t FileListSize;           // Uncompressed size

	std::uint64_t FATSize;                // Uncompressed size
};
static_assert(
	sizeof(PackStreamVer3) == 0x38,
	"sizeof(PackStreamVer3) != 0x38"
);

// Haven't verified these myself.
enum class CompressionType : std::uint32_t
{
	Deflate = 0xEE000009,
	Png     = 0xEE000000,
	Usm     = 0xFF000000
};

struct PackFileHeaderVer1 // MS2f
{
public:
	std::uint32_t Pad1;
	std::uint32_t FileIndex;
	CompressionType Compression;
	std::uint32_t Pad2;
	std::uint64_t Offset;
	std::uint64_t EncodedSize;
	std::uint64_t CompressedSize;
	std::uint64_t Size;
};
static_assert(
	sizeof(PackFileHeaderVer1) == 0x30,
	"sizeof(PackFileHeaderVer1) != 0x30"
);

struct PackFileHeaderVer2 // NS2F
{
public:
	CompressionType Compression;
	std::uint32_t FileIndex;
	std::uint32_t EncodedSize;
	std::uint64_t CompressedSize;
	std::uint64_t Size;
	std::uint64_t Offset;
};
static_assert(
	sizeof(PackFileHeaderVer2) == 0x24,
	"sizeof(PackFileHeaderVer2) != 0x24"
);

struct PackFileHeaderVer3 // OS2F/PS2F
{
public:
	CompressionType Compression;
	std::uint32_t FileIndex;
	std::uint32_t EncodedSize;
	std::uint32_t Pad;
	std::uint64_t CompressedSize;
	std::uint64_t Size;
	std::uint64_t Offset;
};
static_assert(
	sizeof(PackFileHeaderVer3) == 0x28,
	"sizeof(PackFileHeaderVer3) != 0x28"
);
```
## Post #18
- Username: Mikuhl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 11, 2018 2:43 am
- Post datetime: 2018-10-10T18:47:52+00:00
- Post Title: Re: Maplestory 2

The game has released today, October 10th. I would love to see more research. Looking to build a companion app.
## Post #19
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-10-11T02:38:34+00:00
- Post Title: Re: Maplestory 2

Can confirm that my dumper still works with public release of the game.

Though there are these"m2u" files though that are used for user-generated content. I'll poke around the .exe for some info.

[https://ugc.maplestory2.nexon.net/item/ ... 105471.m2u](https://ugc.maplestory2.nexon.net/item/e9/c5/11850008/e9c5f2e3-adda-4cf4-9fa8-94557f4d2837-2917649771394105471.m2u)
## Post #20
- Username: Mikuhl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 11, 2018 2:43 am
- Post datetime: 2018-10-11T03:13:28+00:00
- Post Title: Re: Maplestory 2

Possible constants from decompiling the luapack.o?
## Post #21
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-10-11T07:50:15+00:00
- Post Title: Re: Maplestory 2

> Reply from DEElekgolo
>
> Can confirm that my dumper still works with public release of the game.

Though there are these"m2u" files though that are used for user-generated content. I'll poke around the .exe for some info.

https://ugc.maplestory2.nexon.net/item/ ... 105471.m2u

Turns out to just be a simple zlib compression on a DDS texture.
## Post #22
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-10-12T06:54:17+00:00
- Post Title: Re: Maplestory 2

Here's a bunch of UGC meshes that should make skinning and such a lot easier
[https://www.mediafire.com/file/d40pdpb9 ... .11.18.zip](https://www.mediafire.com/file/d40pdpb9bs54a6j/ugc_meshes+10.11.18.zip)
## Post #23
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-10-14T21:33:50+00:00
- Post Title: Re: Maplestory 2

> Reply from DEElekgolo
>
> DEElekgolo wrote:Can confirm that my dumper still works with public release of the game.

Though there are these"m2u" files though that are used for user-generated content. I'll poke around the .exe for some info.

https://ugc.maplestory2.nexon.net/item/ ... 105471.m2u

Turns out to just be a simple zlib compression on a DDS texture.

Turns out this vulnerability on Nexon's part is the cause of a lot of the UGC theft that has been going on lately. Where people are very easily able to just sniff an m2u url and decompress it to steal each other's textures.
Hope Nexon cleans this up at some point in the future. I won't be focusing on UGC stuff.
## Post #24
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2018-10-23T03:45:57+00:00
- Post Title: Re: Maplestory 2

This is pretty awesome except for the fact there's no compiled Windows build and I can't for the life of me figure out how to compile it myself...
## Post #25
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-10-26T06:20:23+00:00
- Post Title: Re: Maplestory 2

> Reply from Doctor Loboto
>
> This is pretty awesome except for the fact there's no compiled Windows build and I can't for the life of me figure out how to compile it myself...

Just added a precompiled windows build:
[https://github.com/Wunkolo/Maple2Tools/ ... s/tag/v1.0](https://github.com/Wunkolo/Maple2Tools/releases/tag/v1.0)
## Post #26
- Username: jjlovemaple
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 28, 2018 3:00 pm
- Post datetime: 2018-11-28T07:13:13+00:00
- Post Title: Re: Maplestory 2

Thank you for your amazing tool! May I ask what tool/software do you use to show the animation? I was trying to export the nif files to obj files for blender, but the texture information was completely lost (I think) let alone skeleton/bones. 

Thanks again
## Post #27
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2018-11-28T07:56:22+00:00
- Post Title: Re: Maplestory 2

[Noesis!](http://www.richwhitehouse.com/index.php?content=inc_projects.php&showproject=91)
I exported an FBX from it which maintains the rigging and bones
## Post #28
- Username: jjlovemaple
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 28, 2018 3:00 pm
- Post datetime: 2018-11-28T16:09:41+00:00
- Post Title: Re: Maplestory 2

> Reply from DEElekgolo
>
> Noesis!
I exported an FBX from it which maintains the rigging and bones

thank you so much! when I try to import fbx to blender 2.79, it said blender only support fbx version more than 7000 while the fbx version I import is 6100. Shall I just abandon this blender?
## Post #29
- Username: jjlovemaple
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 28, 2018 3:00 pm
- Post datetime: 2018-11-29T16:35:24+00:00
- Post Title: Re: Maplestory 2

> Reply from jjlovemaple
>
> DEElekgolo wrote:Noesis!
I exported an FBX from it which maintains the rigging and bones

thank you so much! when I try to import fbx to blender 2.79, it said blender only support fbx version more than 7000 while the fbx version I import is 6100. Shall I just abandon this blender?

I think I find a solution, all you need is autodesk fbxconverter to convert the 6100 version fbx files, then blender can read the bones, but still lost texture info for some reasons.
## Post #30
- Username: MissNya
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 02, 2018 12:05 am
- Post datetime: 2018-12-02T01:55:53+00:00
- Post Title: Re: Maplestory 2

Hiya, I just wanted to say thanks a lot for making this tool! I've got a question about some of the animations; I've been using Noesis to preview a few things and I've noticed that some animations will either play like they do in game, or just slightly wiggle around while t-posed. Is there something else I need to do to get them to animate properly or another program besides Noesis I should be using?
## Post #31
- Username: Lolypoppy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 27, 2019 1:04 am
- Post datetime: 2019-07-26T17:06:19+00:00
- Post Title: Re: Maplestory 2

Hello ,

Is it possible to share the FBX file here please ? . I'm looking for a chibi dummy like this to use it in Clip studio as a model .

Thank you so much
## Post #32
- Username: Lolypoppy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 27, 2019 1:04 am
- Post datetime: 2019-07-26T17:07:18+00:00
- Post Title: Re: Maplestory 2

> Reply from DEElekgolo ↑Wed Nov 28, 2018 3:56 pm at Wed Nov 28, 2018 3:56 pm
>
> 
Noesis!
I exported an FBX from it which maintains the rigging and bones

Can you share the FBX file here please ? thank you
