## Post #1
- Username: Aegrus
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-08-20T21:51:23+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

Here is a quikbms script for this game
[ff0.zip](https://xentaxbackup.github.io/file/9597_ff0.zip)
## Post #2
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-08-21T04:15:10+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

Great work  Can you please also create a script for movie files (.hxmf) of this game ? And BTW, why some or many of the files extracted are of 0 bytes ? I have all the pack files at one place.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-08-21T09:19:04+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

Its a bug in quickbms.
hit r to rename files instead of skipping them.
## Post #4
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-08-21T10:40:06+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

> Reply from chrrox
>
> Its a bug in quickbms.
hit r to rename files instead of skipping them.

Yes I know but still some files like "alb03_05.bin", "alb07_01.bin", "ale01_02.bin" etc.. inside "JP\bg\bin" folder are extracted as 0 bytes and during extraction there's no option for replace or rename for those files.
## Post #5
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2015-08-21T16:41:54+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

ShivShubh, quite a few entrys in the .fsd file have 0 sizes.  Not sure if they are further down in the package under the same name with a valid size, but if they have a 0 size in the fsd, its possible only their name and the blank fsd entry are still there, just not the file data.

Ker-schploink!
[](https://i.gyazo.com/ea91a6d00a109216deddb00052fe14a3.png)

Here is the layout I see so far:

```
// File: Final Fantasy Type-0 HD Model Binary Template
// Author: Echelo
// Revision: 0.06 info only
//--------------------------------------

local int i;
local int j;
LittleEndian();

struct MODEL_FILE
{
    struct MODEL_HEADER
    {
        uint unknown01 <bgcolor=0x0000FF>;
        uint unknown02 <bgcolor=0x0000FF>;
        uint vertexInfoPointer1 <bgcolor=0x00FF00>;
        uint unknown04 <bgcolor=0x0000FF>;
        ushort count02 <bgcolor=0xFFCC00>;
        ushort count01 <bgcolor=0xFFCC00>;
        ushort materialCount <bgcolor=0xFFCC00>;
        ushort textureCount <bgcolor=0xFFCC00>;
        ushort count06 <bgcolor=0xFFCC00>;
        ushort count05 <bgcolor=0xFFCC00>;
        ushort count07 <bgcolor=0xFFCC00>;
        ushort count08 <bgcolor=0xFFCC00>;
        uint64 address01 <bgcolor=0xFF8800>;
        uint64 materialInfoAddress <bgcolor=0xFF8800>;
        uint64 textureInfoAddress <bgcolor=0xFF8800>;
        uint64 address04 <bgcolor=0xFF8800>;
        uint64 address05 <bgcolor=0xFF8800>;
        uint64 address06 <bgcolor=0xFF8800>;
        uint64 address07 <bgcolor=0xFF8800>;
        uint64 vertexInfoPointer2 <bgcolor=0x00FF00>;
        uint64 address09 <bgcolor=0xFF8800>;
        uint64 address10 <bgcolor=0xFF8800>;
        uint64 address11 <bgcolor=0xFF8800>;
        uint64 address12 <bgcolor=0xFF8800>;
        uint64 address13 <bgcolor=0xFF8800>;
        uint64 address14 <bgcolor=0xFF8800>;
        uint64 address15 <bgcolor=0xFF8800>;
        uint64 address16 <bgcolor=0xFF8800>;
        uint unknown05 <bgcolor=0x0000FF>;
        ushort modelCount <bgcolor=0x00FF00>;
        ushort unknown06 <bgcolor=0x0099FF>;
        uint unknown07 <bgcolor=0x0000FF>;
        ushort unknown08 <bgcolor=0x0000FF>;
        ushort unknown09 <bgcolor=0x0000FF>;
    } modelHeader;

    if (modelHeader.count01 != 0)
    {
        
        FSeek(modelHeader.address01);
        struct TABLE_01
        {
            for (i = 0; i < modelHeader.count01; i++)
            {
                struct TABLE_01_ENTRY
                {
                    uint unknown01;
                    uint unknown02;
                    uint unknown03;
                    uint unknown04;
                } table01Entry;
            }
        } table01 <bgcolor=0x0099FF>;
    }

    if (modelHeader.materialCount != 0)
    {
        FSeek(modelHeader.materialInfoAddress);
        struct MATERIAL_INFO_TABLE
        {
            for (i = 0; i < modelHeader.materialCount; i++)
            {
                struct MATERIAL_INFO_ENTRY
                {
                    ushort diffuseMapIndex;
                    ushort normalMapIndex;
                    ushort specularMapIndex;
                    ushort unknown04;
                    ushort unknown05;
                    ushort unknown06;
                    ushort unknown07;
                    ushort unknown08;
                    ushort unknown09;
                    ushort unknown10;
                    ushort unknown11;
                    ushort unknown12;
                    ushort unknown13;
                    ushort unknown14;
                    ushort unknown15;
                    ushort unknown16;
                    ushort unknown17;
                    ushort specularLevelMapIndex; //not sure what kind of map this is ??
                    ushort unknown19;
                    ushort unknown20;
                    ushort unknown21;
                } materialInfoEntry;
            }
        } materialInfoTable <bgcolor=0x00FF00>;
    }

    if (modelHeader.textureCount != 0)
    {
        FSeek(modelHeader.textureInfoAddress);
        struct TEXTURE_INFO_TABLE
        {
            for (i = 0; i < modelHeader.textureCount; i++)
            {
                struct TEXTURE_INFO_ENTRY
                {
                    ushort textureWidth;
                    ushort textureHeight;
                    uint textureSize;
                    uint textureAddress;
                    uint unknown04;
                } textureInfoEntry;
            }
        } textureInfoTable <bgcolor=0x00FF00>;
    }

    if (modelHeader.count05 != 0)
    {
        FSeek(modelHeader.address05);
        struct TABLE_05
        {
            for (i = 0; i < modelHeader.count05; i++)
            {
                struct TABLE_05_ENTRY
                {
                    float unknown01;
                    float unknown02;
                    float unknown03; //?? not sure if float as only seen null here
                    byte unknown04;
                    byte unknown05;
                    byte unknown06;
                    byte unknown07;
                } table05Entry;
            }
        } table05 <bgcolor=0x0099FF, comment="fvf table?">;
    }

    if (modelHeader.address06 != 0)
    {
        FSeek(modelHeader.address06);
        struct TABLE_06
        {
            uint unknown01;
            float unknown02;
            float unknown03;
            float unknown04;
            ushort unknown05;
            ushort unknown06;
            uint unknown07;
            uint unknown08;
            uint unknown09;
            uint unknown10;
            uint unknown11;
            float boundingBoxCornerA_xPosition;
            float boundingBoxCornerA_yPosition;
            float boundingBoxCornerA_zPosition;
            float boundingBoxCornerB_xPosition;
            float boundingBoxCornerB_yPosition;
            float boundingBoxCornerB_zPosition;
            uint unknown12;
            uint unknown13;
            uint unknown14;
            uint unknown15;
        } table06 <bgcolor=0x0099FF>;
    }

    if (modelHeader.address07 != 0)
    {
        FSeek(modelHeader.address07);
        struct TABLE_07
        {
            uint unknown01;
            uint unknown02;
            uint unknown03;
            uint unknown04;
            uint unknown05;
            uint unknown06;
            uint unknown07;
            ushort unknown08;
        } table07 <bgcolor=0x0000FF>;
    }

    if (modelHeader.address13 != 0)
    {
        FSeek(modelHeader.address13);
        ushort unknownA;
        ushort table13_count;
        struct TABLE_13
        {
            for (i = 0; i < table13_count; i++)
            {
                struct TABLE_13_ENTRY
                {
                    ushort index;
                } table13Entry;
            }
        } table13 <bgcolor=0x00FFFF>;
    }

    if (modelHeader.vertexInfoPointer1 != 0)
    {
        FSeek(modelHeader.vertexInfoPointer1);
        if (modelHeader.modelCount == 0)
        {
            uint vertexInfoAddress;
            uint vertexInfoCount;
            ushort vertexInfoStride;
            ushort unknown01;
            uint unknown02;
            uint unknown03;
            uint unknown04;
            uint unknown05;
            uint unknown06;
            uint unknown07;
            uint unknown08;
            uint unknown09;
            uint unknown10;
            uint meshPartCount;
        
            /*for (i = 0; i < meshPartCount; i++)
            {
                struct FACE_GROUP_INFO
                {
                    uint faceIndexCountA <bgcolor=0xFFCC00>;
                    uint faceIndexCountB <bgcolor=0xFFCC00>;
                    byte unknownF01 <bgcolor=0x0000FF>;
                    byte unknownF02 <bgcolor=0x0000FF>;
                    byte materialIndex <bgcolor=0xFF00AA>;
                    byte unknownF03 <bgcolor=0x0000FF>;
        
                    struct FACE_GROUP
                    {
                        for (j = 0; j < (faceIndexCountA / 3); j++)
                        {
                            struct FACE_ENTRY
                            {
                                uint triangleIndex0;
                                uint triangleIndex1;
                                uint triangleIndex2;
                            } faceEntry;
                        }
                    } faceGroup;
                    
                } faceGroupInfo <bgcolor=0x879E2B>;
            }
        
            FSeek(vertexInfoAddress);
            struct VERTEX_INFO_ENTRYS
            {
                for (i = 0; i < vertexInfoCount; i++)
                {
                    struct VERTEX_INFO_ENTRY
                    {
                        if (vertexInfoStride == 0x44)
                        {
                            float xPosition;
                            float yPosition;
                            float zPosition;
                            byte unknown01;
                            byte unknown02;
                            byte unknown03;
                            byte unknown04;
                            byte unknown05;
                            byte unknown06;
                            byte unknown07;
                            byte unknown08;
                            uint unknown09;
                            uint unknown10;
                            uint unknown11;
                            uint unknown12;
                            uint unknown13;
                            uint unknown14;
                            byte unknown15;
                            byte unknown16;
                            byte unknown17;
                            byte unknown18;
                            float tu;
                            float tv;
                            float tu1;
                            float tv1;
                            float tu2;
                            float tv2;
                        }
                    } vertexInfoEntry;
                }
            } vertexInfoEntrys <bgcolor=0xFF3300>;*/
        }
        else
        {
            struct MODEL_INFO_ADDRESSES
            {
                for (i = 0; i < modelHeader.modelCount; i++)
                {
                    struct MODEL_ADDRESS
                    {
                        uint64 address;
                    } modelAddress;
                }
            } modelInfoAddresses <bgcolor=0x33FF00>;

            struct MODEL_INFO_ENTRYS
            {
                for (i = 0; i < modelHeader.modelCount; i++)
                {
                    FSeek(modelInfoAddresses.modelAddress[i].address);
                    struct MODEL_INFO_ENTRY
                    {
                        uint vertexInfoAddress;
                        uint vertexInfoCount;
                        ushort vertexInfoStride;
                        ushort unknown01;
                        uint unknown02;
                        uint unknown03;
                        uint unknown04;
                        uint unknown05;
                        uint unknown06;
                        uint unknown07;
                        uint unknown08;
                        uint unknown09;
                        uint unknown10;
                        uint meshPartCount;
                    } modelInfoEntry;
                }
            } modelInfoEntrys <bgcolor=0xCC8800>;
        }
    }
} modelFile;

```
[/size]
[fftype0hd_model_structure.zip](https://xentaxbackup.github.io/file/9611_fftype0hd_model_structure.zip)
## Post #6
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-08-23T07:10:27+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

Can anyone tell me what's the differences between normal and 4 GB version of QuickBMS ? cause with 4 GB edition, it gives error at some point while importing, but with normal edition it works fine, this also happened with some other games. So wanted to know if it will cause any problems or not by using normal edition of QuickBMS on this game files, and yes some files are larger than 2 GB in this game.
## Post #7
- Username: Aegrus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 23, 2015 4:04 pm
- Post datetime: 2015-08-26T12:14:28+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

Unless I'm seriously misunderstanding (I apologize, I'm new to this) this is a script for extracting models.  (people are probably looking at me and saying 'derp' right now, sorry again).  Is there any way I can extract textures?  I'm not able to find many non-corrupted ones when I extract with this script.
## Post #8
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-08-26T19:01:42+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

This just unpacks the main packages. Don't have a way to extract usable models or textures afaik.

Edit. Didn't notice the edited post above. Haven't been able to test it.
## Post #9
- Username: Clixias
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 26, 2015 9:28 pm
- Post datetime: 2015-08-26T19:18:45+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

> Reply from Aegrus
>
> Unless I'm seriously misunderstanding (I apologize, I'm new to this) this is a script for extracting models.  (people are probably looking at me and saying 'derp' right now, sorry again).  Is there any way I can extract textures?  I'm not able to find many non-corrupted ones when I extract with this script.

It will extract all files within the .pac file you chose.It will take a long time depending on your computer.

Also, does anyone know in which pack.pac the texture files are located and, if so , in which format?
## Post #10
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2015-08-28T18:26:03+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

Is there any way to decrypt option file?I think the *.bin file is encrypted and it's not using usual *.ini or *.cfg to change custom resolution manually
## Post #11
- Username: amido
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 30, 2015 11:43 am
- Post datetime: 2015-08-30T03:54:51+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

any way to compress back after change any model? in this script i can change doors style and compress back to game? =o


*sorry for bad english, not is my mother language*
## Post #12
- Username: ayuanx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 13, 2014 7:23 pm
- Post datetime: 2015-09-12T11:51:22+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

The script is buggy. Certain files have completely wrong data. It's not encryption since some files with the same extension name are correct.
## Post #13
- Username: ayuanx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 13, 2014 7:23 pm
- Post datetime: 2015-09-12T11:58:50+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

> Reply from aagems
>
> Is there any way to decrypt option file?I think the *.bin file is encrypted and it's not using usual *.ini or *.cfg to change custom resolution manually

Forget about that. It doesn't store screen resolution height/width in the option file.
There is only a template value in option file for screen resolution: 0 for 1280x720; 1 for 1920x1080.
You can't customize resolution by modifying option file.
## Post #14
- Username: ayuanx
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 13, 2014 7:23 pm
- Post datetime: 2015-09-13T16:00:32+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

Final Fantasy Type-0 HD PC Decryptor + Encryptor
By AyuanX, v1.0, 2015-09-14

Usage: FFType0HD_Cryptor.exe [-d] [-e] INPUT_FILE [OUTPUT_FILE]
   -d                    (Decryption)
   -e                    (Encryption)
   OUTPUT_FILE   (Optional, can be omitted)

Examples:
   FFType0HD_Cryptor.exe -d EPSC01.hxmf
   FFType0HD_Cryptor.exe -e TYPE0SYS.BIN

PS:
There are two kinds of files that are encrypted in FFType-0 HD PC:
A) All save data files (e.g. TYPE0SYS.BIN / TYPE0DAT.BIN)
    They are meaningful binary files after decryption.

B) All pre-rendered movie files (e.g. *.hxmf)
    They are standard MP4/H264 files after decryption.

PPS:
This tool is capable to encrypt modified files back to the game.
This is a command-line tool.
Both x86 and x64 versions are provided.
Minimum operating system: Windows Vista and later, up to Windows 10.

Alternative download:
[https://ayuanx.wordpress.com/2015/09/14 ... d-cryptor/](https://ayuanx.wordpress.com/2015/09/14/fftype0hd-cryptor/)
[FFType0HD_Cryptor.7z](https://xentaxbackup.github.io/file/9731_FFType0HD_Cryptor.7z)
## Post #15
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2015-09-26T08:31:19+00:00
- Post Title: FINAL FANTASY TYPE-0 HD PC

Wonderful, thanks for the tools
## Post #16
- Username: Romangelo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 09, 2011 5:30 pm
- Post datetime: 2015-11-20T12:45:53+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

Can anyone tell me how to extract PNG files (for user interface images) from those files? I think they're in .bin format.

need some images for my website works.
## Post #17
- Username: NovaChrystalia
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 16, 2015 9:26 am
- Post datetime: 2015-12-16T01:34:16+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

I'm new to this, but I want to ask is there anyway I could change the text of the game, or could someone please tell me the right direction I need to follow? I wanted to do a fan translation in my native language. Thanks!
## Post #18
- Username: NovaChrystalia
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 16, 2015 9:26 am
- Post datetime: 2016-01-22T02:43:33+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

I'm willing to pay for anyone that can help me with this. Not a whole lot much but if I can afford I'll probably do.
Currently I use the above script to extract the game files but I have no idea how I can view at least the png files, which is icons/menu/interface images.
## Post #19
- Username: Hyder61112
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 04, 2016 4:37 am
- Post datetime: 2016-08-26T07:55:32+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

> Reply from NovaChrystalia
>
> I'm willing to pay for anyone that can help me with this. Not a whole lot much but if I can afford I'll probably do.
Currently I use the above script to extract the game files but I have no idea how I can view at least the png files, which is icons/menu/interface images.

Try To Use "console texture explorer (psp/ps2)" its hard to use. but may help.

> Reply from NovaChrystalia
>
> I'm new to this, but I want to ask is there anyway I could change the text of the game, or could someone please tell me the right direction I need to follow? I wanted to do a fan translation in my native language. Thanks!
hex editor can absolutely do that.

> Reply from Romangelo
>
> Can anyone tell me how to extract PNG files (for user interface images) from those files? I think they're in .bin format.

need some images for my website works.
Try To Use "console texture explorer (psp/ps2)" its hard to use. but may help
## Post #20
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2016-09-23T13:16:47+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

Is there a script for the models?
## Post #21
- Username: Hyder61112
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 04, 2016 4:37 am
- Post datetime: 2016-11-21T07:54:00+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

> Reply from Casedey
>
> Is there a script for the models?
Explain Your Goal & i'll try to help. email me on [hyder61112@gmail.com](mailto:hyder61112@gmail.com)
## Post #22
- Username: youarebritish
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 30, 2015 4:23 am
- Post datetime: 2017-03-03T08:25:21+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

Sorry to bump this, but has anyone managed to get the model extraction script working? I keep getting the error "*ERROR Line 150: Template passed end of file at variable 'unknown01'. 
" I've tried it even on p_sword_hi, which was shown extracted in the post with it, but no luck. :/
## Post #23
- Username: IcicleWater
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 04, 2017 12:27 am
- Post datetime: 2017-04-04T07:00:28+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

Excuse me, I have already extracted the pac files, but where are the models? I think that maybe the models are in bin files, but how to import it into 3dsmax? I'm new here...
## Post #24
- Username: IcicleWater
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 04, 2017 12:27 am
- Post datetime: 2017-04-06T06:47:50+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

> Reply from EcheloCross
>
> ShivShubh, quite a few entrys in the .fsd file have 0 sizes.  Not sure if they are further down in the package under the same name with a valid size, but if they have a 0 size in the fsd, its possible only their name and the blank fsd entry are still there, just not the file data.

Ker-schploink!


Here is the layout I see so far:
Code: Select all//--------------------------------------
// File: Final Fantasy Type-0 HD Model Binary Template
// Author: Echelo
// Revision: 0.06 info only
//--------------------------------------

local int i;
local int j;
LittleEndian();

struct MODEL_FILE
{
    struct MODEL_HEADER
    {
        uint unknown01 <bgcolor=0x0000FF>;
        uint unknown02 <bgcolor=0x0000FF>;
        uint vertexInfoPointer1 <bgcolor=0x00FF00>;
        uint unknown04 <bgcolor=0x0000FF>;
        ushort count02 <bgcolor=0xFFCC00>;
        ushort count01 <bgcolor=0xFFCC00>;
        ushort materialCount <bgcolor=0xFFCC00>;
        ushort textureCount <bgcolor=0xFFCC00>;
        ushort count06 <bgcolor=0xFFCC00>;
        ushort count05 <bgcolor=0xFFCC00>;
        ushort count07 <bgcolor=0xFFCC00>;
        ushort count08 <bgcolor=0xFFCC00>;
        uint64 address01 <bgcolor=0xFF8800>;
        uint64 materialInfoAddress <bgcolor=0xFF8800>;
        uint64 textureInfoAddress <bgcolor=0xFF8800>;
        uint64 address04 <bgcolor=0xFF8800>;
        uint64 address05 <bgcolor=0xFF8800>;
        uint64 address06 <bgcolor=0xFF8800>;
        uint64 address07 <bgcolor=0xFF8800>;
        uint64 vertexInfoPointer2 <bgcolor=0x00FF00>;
        uint64 address09 <bgcolor=0xFF8800>;
        uint64 address10 <bgcolor=0xFF8800>;
        uint64 address11 <bgcolor=0xFF8800>;
        uint64 address12 <bgcolor=0xFF8800>;
        uint64 address13 <bgcolor=0xFF8800>;
        uint64 address14 <bgcolor=0xFF8800>;
        uint64 address15 <bgcolor=0xFF8800>;
        uint64 address16 <bgcolor=0xFF8800>;
        uint unknown05 <bgcolor=0x0000FF>;
        ushort modelCount <bgcolor=0x00FF00>;
        ushort unknown06 <bgcolor=0x0099FF>;
        uint unknown07 <bgcolor=0x0000FF>;
        ushort unknown08 <bgcolor=0x0000FF>;
        ushort unknown09 <bgcolor=0x0000FF>;
    } modelHeader;

    if (modelHeader.count01 != 0)
    {
        
        FSeek(modelHeader.address01);
        struct TABLE_01
        {
            for (i = 0; i < modelHeader.count01; i++)
            {
                struct TABLE_01_ENTRY
                {
                    uint unknown01;
                    uint unknown02;
                    uint unknown03;
                    uint unknown04;
                } table01Entry;
            }
        } table01 <bgcolor=0x0099FF>;
    }

    if (modelHeader.materialCount != 0)
    {
        FSeek(modelHeader.materialInfoAddress);
        struct MATERIAL_INFO_TABLE
        {
            for (i = 0; i < modelHeader.materialCount; i++)
            {
                struct MATERIAL_INFO_ENTRY
                {
                    ushort diffuseMapIndex;
                    ushort normalMapIndex;
                    ushort specularMapIndex;
                    ushort unknown04;
                    ushort unknown05;
                    ushort unknown06;
                    ushort unknown07;
                    ushort unknown08;
                    ushort unknown09;
                    ushort unknown10;
                    ushort unknown11;
                    ushort unknown12;
                    ushort unknown13;
                    ushort unknown14;
                    ushort unknown15;
                    ushort unknown16;
                    ushort unknown17;
                    ushort specularLevelMapIndex; //not sure what kind of map this is ??
                    ushort unknown19;
                    ushort unknown20;
                    ushort unknown21;
                } materialInfoEntry;
            }
        } materialInfoTable <bgcolor=0x00FF00>;
    }

    if (modelHeader.textureCount != 0)
    {
        FSeek(modelHeader.textureInfoAddress);
        struct TEXTURE_INFO_TABLE
        {
            for (i = 0; i < modelHeader.textureCount; i++)
            {
                struct TEXTURE_INFO_ENTRY
                {
                    ushort textureWidth;
                    ushort textureHeight;
                    uint textureSize;
                    uint textureAddress;
                    uint unknown04;
                } textureInfoEntry;
            }
        } textureInfoTable <bgcolor=0x00FF00>;
    }

    if (modelHeader.count05 != 0)
    {
        FSeek(modelHeader.address05);
        struct TABLE_05
        {
            for (i = 0; i < modelHeader.count05; i++)
            {
                struct TABLE_05_ENTRY
                {
                    float unknown01;
                    float unknown02;
                    float unknown03; //?? not sure if float as only seen null here
                    byte unknown04;
                    byte unknown05;
                    byte unknown06;
                    byte unknown07;
                } table05Entry;
            }
        } table05 <bgcolor=0x0099FF, comment="fvf table?">;
    }

    if (modelHeader.address06 != 0)
    {
        FSeek(modelHeader.address06);
        struct TABLE_06
        {
            uint unknown01;
            float unknown02;
            float unknown03;
            float unknown04;
            ushort unknown05;
            ushort unknown06;
            uint unknown07;
            uint unknown08;
            uint unknown09;
            uint unknown10;
            uint unknown11;
            float boundingBoxCornerA_xPosition;
            float boundingBoxCornerA_yPosition;
            float boundingBoxCornerA_zPosition;
            float boundingBoxCornerB_xPosition;
            float boundingBoxCornerB_yPosition;
            float boundingBoxCornerB_zPosition;
            uint unknown12;
            uint unknown13;
            uint unknown14;
            uint unknown15;
        } table06 <bgcolor=0x0099FF>;
    }

    if (modelHeader.address07 != 0)
    {
        FSeek(modelHeader.address07);
        struct TABLE_07
        {
            uint unknown01;
            uint unknown02;
            uint unknown03;
            uint unknown04;
            uint unknown05;
            uint unknown06;
            uint unknown07;
            ushort unknown08;
        } table07 <bgcolor=0x0000FF>;
    }

    if (modelHeader.address13 != 0)
    {
        FSeek(modelHeader.address13);
        ushort unknownA;
        ushort table13_count;
        struct TABLE_13
        {
            for (i = 0; i < table13_count; i++)
            {
                struct TABLE_13_ENTRY
                {
                    ushort index;
                } table13Entry;
            }
        } table13 <bgcolor=0x00FFFF>;
    }

    if (modelHeader.vertexInfoPointer1 != 0)
    {
        FSeek(modelHeader.vertexInfoPointer1);
        if (modelHeader.modelCount == 0)
        {
            uint vertexInfoAddress;
            uint vertexInfoCount;
            ushort vertexInfoStride;
            ushort unknown01;
            uint unknown02;
            uint unknown03;
            uint unknown04;
            uint unknown05;
            uint unknown06;
            uint unknown07;
            uint unknown08;
            uint unknown09;
            uint unknown10;
            uint meshPartCount;
        
            /*for (i = 0; i < meshPartCount; i++)
            {
                struct FACE_GROUP_INFO
                {
                    uint faceIndexCountA <bgcolor=0xFFCC00>;
                    uint faceIndexCountB <bgcolor=0xFFCC00>;
                    byte unknownF01 <bgcolor=0x0000FF>;
                    byte unknownF02 <bgcolor=0x0000FF>;
                    byte materialIndex <bgcolor=0xFF00AA>;
                    byte unknownF03 <bgcolor=0x0000FF>;
        
                    struct FACE_GROUP
                    {
                        for (j = 0; j < (faceIndexCountA / 3); j++)
                        {
                            struct FACE_ENTRY
                            {
                                uint triangleIndex0;
                                uint triangleIndex1;
                                uint triangleIndex2;
                            } faceEntry;
                        }
                    } faceGroup;
                    
                } faceGroupInfo <bgcolor=0x879E2B>;
            }
        
            FSeek(vertexInfoAddress);
            struct VERTEX_INFO_ENTRYS
            {
                for (i = 0; i < vertexInfoCount; i++)
                {
                    struct VERTEX_INFO_ENTRY
                    {
                        if (vertexInfoStride == 0x44)
                        {
                            float xPosition;
                            float yPosition;
                            float zPosition;
                            byte unknown01;
                            byte unknown02;
                            byte unknown03;
                            byte unknown04;
                            byte unknown05;
                            byte unknown06;
                            byte unknown07;
                            byte unknown08;
                            uint unknown09;
                            uint unknown10;
                            uint unknown11;
                            uint unknown12;
                            uint unknown13;
                            uint unknown14;
                            byte unknown15;
                            byte unknown16;
                            byte unknown17;
                            byte unknown18;
                            float tu;
                            float tv;
                            float tu1;
                            float tv1;
                            float tu2;
                            float tv2;
                        }
                    } vertexInfoEntry;
                }
            } vertexInfoEntrys <bgcolor=0xFF3300>;*/
        }
        else
        {
            struct MODEL_INFO_ADDRESSES
            {
                for (i = 0; i < modelHeader.modelCount; i++)
                {
                    struct MODEL_ADDRESS
                    {
                        uint64 address;
                    } modelAddress;
                }
            } modelInfoAddresses <bgcolor=0x33FF00>;

            struct MODEL_INFO_ENTRYS
            {
                for (i = 0; i < modelHeader.modelCount; i++)
                {
                    FSeek(modelInfoAddresses.modelAddress[i].address);
                    struct MODEL_INFO_ENTRY
                    {
                        uint vertexInfoAddress;
                        uint vertexInfoCount;
                        ushort vertexInfoStride;
                        ushort unknown01;
                        uint unknown02;
                        uint unknown03;
                        uint unknown04;
                        uint unknown05;
                        uint unknown06;
                        uint unknown07;
                        uint unknown08;
                        uint unknown09;
                        uint unknown10;
                        uint meshPartCount;
                    } modelInfoEntry;
                }
            } modelInfoEntrys <bgcolor=0xCC8800>;
        }
    }
} modelFile;
[/size]
Excuse me， how did you extract the model of queen？I have already extracted the pac files,but how to import the bin files into 3dsmax?
## Post #25
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-11-10T00:01:22+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

So I wanted to attempt at writing a script for the models, but saw that the .bin files could be an archive rather than a model file. I tried the .bin Noesis script for FF13 in case the format was the same but it doesn't work. Would anyone know how to extract the .bin files? The decryptor doesn't make Noesis work with them either.

Here is a sample file if someone wants to take a look:
[https://drive.google.com/file/d/11T-EAT ... sp=sharing](https://drive.google.com/file/d/11T-EATp__vBZ6wSc88Lych9GiS0fHgyI/view?usp=sharing)
## Post #26
- Username: NovaChrystalia
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 16, 2015 9:26 am
- Post datetime: 2018-01-21T08:43:09+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

This is a reply from EcheloCross to me when I asked him how could he open the model in a 3d application, if someone needs it:

> if you convert that binary template to any language most of the work is done. The models are grouped into separate meshes inside the model files, the textures reside near the end of the file and their info is in the toc. They're dx10 textures so I had to convert them with texconv after extracting them. Then I wrote all the vertex, uv, and face info to a .obj and referenced the textures in a .mtl. There are also material definitions in the file telling which texture to use for each group of faces.
## Post #27
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2018-01-22T19:33:00+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

Unfortunately that doesn't help on the encryption. Can't get anything until the files are decrypted.
## Post #28
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-23T06:39:36+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

> Reply from TRDaz
>
> Here is a sample file if someone wants to take a look:
https://drive.google.com/file/d/11T-EAT ... sp=sharing
looks compressed, this bms script will decompress it  

```

comtype unzip_dynamic
get NAME basename
get EXT extension
string NAME + _decomp.
string NAME + EXT
get ZSIZE asize
clog NAME 0x0 ZSIZE ZSIZE

```

i see some indices and vertex blocks and dx10 textures so it looks correct to me
## Post #29
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-03-05T03:34:34+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

Using Ravioli Tools, I was able to find a few of the English voice files in the .pac's, but when I used quickbms and the .BMS file to extract them, I got the Japanese voice files (entirely). I tried overwriting and renaming but got no success. I need both languages for the sake of comparison and other reasons. Is there something I am missing in order to get the English versions of the voice files?

BTW, the files are .scd, which are convertible in foobar2000, but even that is nothing compared to what I want.
## Post #30
- Username: NovaChrystalia
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 16, 2015 9:26 am
- Post datetime: 2018-05-02T10:18:02+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

> Reply from TRDaz
>
> Unfortunately that doesn't help on the encryption. Can't get anything until the files are decrypted.
Did you try AceWell's script?
I wanted to play around with the models too but still haven't find a way to open them in 3dsmax or any 3d application... I hope you still want to write the script for extracting these models!
## Post #31
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-17T20:58:47+00:00
- Post Title: Re: FINAL FANTASY TYPE-0 HD PC

Added a module to my tool UniViewer for loading the models of this game : [viewtopic.php?p=147580#p147580](http://forum.xentax.com/viewtopic.php?p=147580#p147580)
