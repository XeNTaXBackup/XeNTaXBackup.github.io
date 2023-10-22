## Post #1
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2015-04-18T06:48:20+00:00
- Post Title: Mortal Kombat X .xxx

I can't unpack .xxx files using Umodel. Can anyone help?

Sample: [http://rghost.ru/7QJSLTyFn](http://rghost.ru/7QJSLTyFn)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-19T07:00:33+00:00
- Post Title: Mortal Kombat X .xxx

MKX .xxx unpacker. Experimental tools, 64 bit only. No error handling, no help. Here's what you can do with it:

1. unpack xxx file 

mk10_xxx_packer [xxx name]

It will make unpacked .xxx.u file. If the file is already unpacked, it will crash. At least sound .xxx are not packed at all.

2. list the contents of unpacked file

mk10_xxx [xxx name] [filter]

It will make 3 text files with imports, exports, names. Also it will make .bat file to extract all files from the package. Extra "filter" parameter may be used to list only files having particular text in its NAME (not extension).
- Exports are just a list of files contained in the package. Notice some of them may be equal.
- Imports may be wrong, I'm not too familiar with it.
- Names are essential if you plan to do anything with the contents, because all unreal formats depend on these package-dependent names.

3. extract the files

Just run "cut.bat" to extract all the files. You can also edit the file all you want. In case some files have same names, they will be overwritten. I have no time to deal with this (duplicates) yet.
[mk10_xxx.rar](https://xentaxbackup.github.io/file/9063_mk10_xxx.rar)
## Post #3
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-04-19T07:31:26+00:00
- Post Title: Mortal Kombat X .xxx

Dunno what kind of progress gildor is making (if any as it didn't seem like he had time to work on MKX atm) but you might as well upload your tool.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-19T13:16:18+00:00
- Post Title: Mortal Kombat X .xxx

Ok, tools uploaded. Have fun 

It is strange, but many .xxx files have strange (encrypted?) part in the beginning. Different size, but all about 32k. Interesting that first 31184 bytes of those are the same for all .xxx files. It doesn't affect the unpacking process, but what could that be? Any ideas?
## Post #5
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2015-04-19T15:21:19+00:00
- Post Title: Mortal Kombat X .xxx

Very useful tool. I wonder is there a way of converting the Texture2D files to a readable TGA/DDS. Same with the SkeletalMesh files converting them to psk.
## Post #6
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2015-04-19T20:13:50+00:00
- Post Title: Mortal Kombat X .xxx

Textures in archives very strange: [http://rghost.ru/6MDhfsMkX](http://rghost.ru/6MDhfsMkX)
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-04-22T13:32:48+00:00
- Post Title: Mortal Kombat X .xxx

not strange at all. those images you think are DXT5 with blocks swizzled are actually BC7.
[http://snag.gy/g4qlM.jpg](http://snag.gy/g4qlM.jpg)

model format is similar to injustice. i'm sure gildor will support it soon.
[http://snag.gy/Eeure.jpg](http://snag.gy/Eeure.jpg)
## Post #8
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2015-04-23T16:45:55+00:00
- Post Title: Mortal Kombat X .xxx

@ howfie what program do u use to view/edit? the dds bc7
also can u provide the actual bc7 dds and or atleast the header from a bc7
i read somewhere (iirc in the mw thread)the header has an addiditional 20 bytes
## Post #9
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2015-04-23T18:39:43+00:00
- Post Title: Mortal Kombat X .xxx

> Reply from howfie
>
> not strange at all. those images you think are DXT5 with blocks swizzled are actually BC7.
http://snag.gy/g4qlM.jpg

model format is similar to injustice. i'm sure gildor will support it soon.
http://snag.gy/Eeure.jpg

hey man, I would also like to know how you reversed it back to .dds format. I am close, and was able to dump them into these files using tools: 
"image0.Texture2D" but I am guessing It's a headerless BC7 file?
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-04-23T22:48:28+00:00
- Post Title: Mortal Kombat X .xxx

I wrote code to convert BC7 stream to RGBA format. Notice I use a function called "AVPCL::decompress" to decompress BC7 blocks to RGBA format. That function comes from a C++ library written by some dude from NVIDIA named Walter Donovan who wrote the BC6 specification. You can download the library [here](https://code.google.com/p/nvidia-texture-tools/downloads/detail?name=bc7_export.zip&can=2&q=).

You can also use Noesis if you like Python.

```
#define MK_ARGB 0x01
#define MK_DXT1 0x02
#define MK_DXT3 0x03
#define MK_DXT5 0x04
#define MK_ATI2 0x05
#define MK_BC7  0x06

struct MKTEXTURE2D {
 STDSTRING filename;
 uint32 offset; // offset to data
 uint32 dx;
 uint32 dy;
 uint32 format;
};

bool MKK_ProcessTexture2D(const MKTEXTURE2D& info)
{
 // Typically, Texture2D files contain 0x20 bytes directly before the texture data that has the
 // size of the data and an identifier. Width and height are typically displayed at the top.

 // open file
 using namespace std;
 ifstream ifile(info.filename.c_str(), ios::binary);
 if(!ifile) return error("Failed to open file.");

 // filename properties
 STDSTRING pathname = GetPathnameFromFilename(info.filename.c_str()).get();
 STDSTRING shrtname = GetShortFilenameWithoutExtension(info.filename.c_str()).get();

 // determine size of data
 uint32 datasize = 0;
 switch(info.format) {
   case(MK_RGBA) : datasize = UncompressedDDSFileSize(info.dx, info.dy, 0, 32); break;
   case(MK_ARGB) : datasize = UncompressedDDSFileSize(info.dx, info.dy, 0, 32); break;
   case(MK_DXT1) : datasize = DXT1Filesize(info.dx, info.dy, 0); break;
   case(MK_DXT3) : datasize = DXT3Filesize(info.dx, info.dy, 0); break;
   case(MK_DXT5) : datasize = DXT5Filesize(info.dx, info.dy, 0); break;
   case(MK_ATI2) : datasize = ATI2Filesize(info.dx, info.dy, 0); break;
   case(MK_BC7)  : datasize = GetBC7DataSize(info.dx, info.dy, 0); break;
   default : return error("Format not supported.", __LINE__);
  }

 // seek data
 ifile.seekg(info.offset);
 if(ifile.fail()) return error("Seek failure.", __LINE__);

 // read data
 boost::shared_array<char> data(new char[datasize]);
 ifile.read(data.get(), datasize);
 if(ifile.fail()) return error("Read failure.", __LINE__);

 // create DDS header
 DDS_HEADER ddsh;
 switch(info.format) {
   case(MK_RGBA) : CreateR8G8B8A8DDSHeader(info.dx, info.dy, 0, FALSE, &ddsh); break;
   case(MK_ARGB) : CreateA8R8G8B8DDSHeader(info.dx, info.dy, 0, FALSE, &ddsh); break;
   case(MK_DXT1) : CreateDXT1Header(info.dx, info.dy, 0, FALSE, &ddsh); break;
   case(MK_DXT3) : CreateDXT3Header(info.dx, info.dy, 0, FALSE, &ddsh); break;
   case(MK_DXT5) : CreateDXT5Header(info.dx, info.dy, 0, FALSE, &ddsh); break;
   case(MK_ATI2) : CreateATI2Header(info.dx, info.dy, 0, FALSE, &ddsh); break;
   case(MK_BC7)  : CreateR8G8B8A8DDSHeader(info.dx, info.dy, 0, FALSE, &ddsh); break;
   default : return error("Format not supported.", __LINE__);
  }

 // save DDS file
 STDSTRINGSTREAM ss;
 ss << pathname << shrtname << TEXT(".dds");
 if(info.format == MK_BC7)
   {
    // block properties
    const unsigned int blocksize = 16;
    const unsigned int block_dx = 4;
    const unsigned int block_dy = 4;
   
    // compute expected size
    unsigned int block_rows = std::max((DWORD)1, (DWORD)((info.dy + 3)/4));
    unsigned int block_cols = std::max((DWORD)1, (DWORD)((info.dx + 3)/4));
    unsigned int n_blocks = block_rows*block_cols;
    unsigned int expected_size = blocksize*n_blocks;
    if(expected_size < datasize) return false;
   
    // create RGBA data
    uint32 outpitch = 4*info.dx;
    uint32 outsize = outpitch*info.dy;
    boost::shared_array<char> outdata(new char[outsize]);
   
    // premultiplied
    uint32 left_offset[4] = { 0, outpitch, 2*outpitch, 3*outpitch };
   
    // for each block
    const char* block = data.get();
    Tile t(4, 4);
    for(uint32 i = 0; i < n_blocks; i++)
       {
        // decompress
        AVPCL::decompress(&block[0], t);
   
        // now map data to RGBA image
        uint32 base_x = (i % block_cols) * block_dx;
        uint32 base_y = (i / block_cols) * block_dy;
        uint32 base_index = 4*(info.dx*base_y + base_x);

        // convert char* to unsigned char* so we can assign 0 to 255 to items
        unsigned char* ptr = reinterpret_cast<unsigned char*>(outdata.get());

        // row1
        uint32 offset = base_index;
        ptr[offset++] = (uint08)t.data[0][0].Z();
        ptr[offset++] = (uint08)t.data[0][0].Y();
        ptr[offset++] = (uint08)t.data[0][0].X();
        ptr[offset++] = (uint08)t.data[0][0].W();
        ptr[offset++] = (uint08)t.data[0][1].Z();
        ptr[offset++] = (uint08)t.data[0][1].Y();
        ptr[offset++] = (uint08)t.data[0][1].X();
        ptr[offset++] = (uint08)t.data[0][1].W();
        ptr[offset++] = (uint08)t.data[0][2].Z();
        ptr[offset++] = (uint08)t.data[0][2].Y();
        ptr[offset++] = (uint08)t.data[0][2].X();
        ptr[offset++] = (uint08)t.data[0][2].W();
        ptr[offset++] = (uint08)t.data[0][3].Z();
        ptr[offset++] = (uint08)t.data[0][3].Y();
        ptr[offset++] = (uint08)t.data[0][3].X();
        ptr[offset]   = (uint08)t.data[0][3].W();
   
        // row2
        offset = base_index + left_offset[1];
        ptr[offset++] = (uint08)t.data[1][0].Z();
        ptr[offset++] = (uint08)t.data[1][0].Y();
        ptr[offset++] = (uint08)t.data[1][0].X();
        ptr[offset++] = (uint08)t.data[1][0].W();
        ptr[offset++] = (uint08)t.data[1][1].Z();
        ptr[offset++] = (uint08)t.data[1][1].Y();
        ptr[offset++] = (uint08)t.data[1][1].X();
        ptr[offset++] = (uint08)t.data[1][1].W();
        ptr[offset++] = (uint08)t.data[1][2].Z();
        ptr[offset++] = (uint08)t.data[1][2].Y();
        ptr[offset++] = (uint08)t.data[1][2].X();
        ptr[offset++] = (uint08)t.data[1][2].W();
        ptr[offset++] = (uint08)t.data[1][3].Z();
        ptr[offset++] = (uint08)t.data[1][3].Y();
        ptr[offset++] = (uint08)t.data[1][3].X();
        ptr[offset]   = (uint08)t.data[1][3].W();
   
        // row3
        offset = base_index + left_offset[2];
        ptr[offset++] = (uint08)t.data[2][0].Z();
        ptr[offset++] = (uint08)t.data[2][0].Y();
        ptr[offset++] = (uint08)t.data[2][0].X();
        ptr[offset++] = (uint08)t.data[2][0].W();
        ptr[offset++] = (uint08)t.data[2][1].Z();
        ptr[offset++] = (uint08)t.data[2][1].Y();
        ptr[offset++] = (uint08)t.data[2][1].X();
        ptr[offset++] = (uint08)t.data[2][1].W();
        ptr[offset++] = (uint08)t.data[2][2].Z();
        ptr[offset++] = (uint08)t.data[2][2].Y();
        ptr[offset++] = (uint08)t.data[2][2].X();
        ptr[offset++] = (uint08)t.data[2][2].W();
        ptr[offset++] = (uint08)t.data[2][3].Z();
        ptr[offset++] = (uint08)t.data[2][3].Y();
        ptr[offset++] = (uint08)t.data[2][3].X();
        ptr[offset]   = (uint08)t.data[2][3].W();
   
        // row4
        offset = base_index + left_offset[3];
        ptr[offset++] = (uint08)t.data[3][0].Z();
        ptr[offset++] = (uint08)t.data[3][0].Y();
        ptr[offset++] = (uint08)t.data[3][0].X();
        ptr[offset++] = (uint08)t.data[3][0].W();
        ptr[offset++] = (uint08)t.data[3][1].Z();
        ptr[offset++] = (uint08)t.data[3][1].Y();
        ptr[offset++] = (uint08)t.data[3][1].X();
        ptr[offset++] = (uint08)t.data[3][1].W();
        ptr[offset++] = (uint08)t.data[3][2].Z();
        ptr[offset++] = (uint08)t.data[3][2].Y();
        ptr[offset++] = (uint08)t.data[3][2].X();
        ptr[offset++] = (uint08)t.data[3][2].W();
        ptr[offset++] = (uint08)t.data[3][3].Z();
        ptr[offset++] = (uint08)t.data[3][3].Y();
        ptr[offset++] = (uint08)t.data[3][3].X();
        ptr[offset]   = (uint08)t.data[3][3].W();
   
        // move to next block
        block += blocksize;
       }

    SaveDDSFile(ss.str().c_str(), ddsh, outdata, outsize);
   }
 else
    SaveDDSFile(ss.str().c_str(), ddsh, data, datasize);

 return true;
}

```
## Post #11
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2015-04-24T05:37:21+00:00
- Post Title: Mortal Kombat X .xxx

Thanks for your script man, awesome stuff. I saved it as a .bms but quick BMS didn't seem to like it, tried putting it in with the BC7 Extractor scripts no go. I am trying to rip the Texure2D files from PC. Tried it on the file LoadScreen_TYM_TinLion.XXX extracted Texture2D files) and Char_Kitana_Diff.XXX (Extracted Texture2D file, the same one you used to make the .DDS texture)
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-04-24T08:03:26+00:00
- Post Title: Mortal Kombat X .xxx

btw, a guy pmed me on gildor's forum saying he had models for mkx all figured out using his noesis script, so if he's cool ya'll should be getting your models and textures soon. i think zaramot was also interested in doing a script. gildor said he'd still try too. so patience and time.

now i know you texture modders are here so if you know c++ (not quickbms), i have given you enough info on how to convert bc7 to rgba, which you can take into photoshop and edit, and then use the nvidia texture tools library i used to compress rgba back to bc7, for which you can paste back into the Texture2D.
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-04-24T12:16:10+00:00
- Post Title: Mortal Kombat X .xxx

Yes, Howfie you're right I'm doing script right now, going to finish and post it here. Unless, you want to do this too? You was first and did an awesome job!:)
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-04-24T16:30:47+00:00
- Post Title: Mortal Kombat X .xxx

nope! it's all yours max_shift  ! i just wanted one model hehehe.
## Post #15
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2015-04-25T07:05:32+00:00
- Post Title: Mortal Kombat X .xxx

> Reply from howfie
>
> btw, a guy pmed me on gildor's forum saying he had models for mkx all figured out using his noesis script, so if he's cool ya'll should be getting your models and textures soon. i think zaramot was also interested in doing a script. gildor said he'd still try too. so patience and time.

now i know you texture modders are here so if you know c++ (not quickbms), i have given you enough info on how to convert bc7 to rgba, which you can take into photoshop and edit, and then use the nvidia texture tools library i used to compress rgba back to bc7, for which you can paste back into the Texture2D.

Ahh sweet thanks man, sorry I thought it was a BMS script. my knowledge of C++ is zero so I guess I will wait it out, but thanks for all you research on this format  (Any everone else too including gildor)
## Post #16
- Username: MusicNerd
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 14, 2011 2:48 pm
- Post datetime: 2015-05-10T23:02:24+00:00
- Post Title: Re: Mortal Kombat X .xxx

> Reply from zaramot
>
> Yes, Howfie you're right I'm doing script right now, going to finish and post it here. Unless, you want to do this too? You was first and did an awesome job!:)

Hiya, was wondering if there was any progress with that script? I tried to execute / compile howfie's c++ script online but just errors. :/
## Post #17
- Username: sonvedita
- Rank: n00b
- Number of posts: 13
- Joined date: Tue May 14, 2019 4:34 am
- Post datetime: 2019-07-17T02:59:13+00:00
- Post Title: Re: Mortal Kombat X .xxx

how to import mesh.ascii file into blender or 3ds max
## Post #18
- Username: sonvedita
- Rank: n00b
- Number of posts: 13
- Joined date: Tue May 14, 2019 4:34 am
- Post datetime: 2019-10-17T19:52:04+00:00
- Post Title: Re: Mortal Kombat X .xxx

do the procedure more when i click the bat it does the process more when it finishes creates an empty folder help
