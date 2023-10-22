## Post #1
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2021-08-28T20:27:41+00:00
- Post Title: The Outforce .OPF file

Hello everybody!

I need a little help. There's a game named The Outforce, it was developed by O3 Games, now Starbreeze Studios.

There is a file named "PackedProject.OPF" this is the main project file that contains the assets (3D model files, textures, animations, sounds, etc.)

I can unpack this file with Watto's game extractor, but cannot repack it, because it contains files like: .CBaseClass, CGridMember, CUnit,CWeaponUnit, .UNKNOWN thats file structure is unknown... 

The whole .OPF file is less than 9 MB.

TODO: make a program that can unpack and repack .OPF file and fileformats I mentioned above.

link to download .OPF file: [https://www.moddb.com/games/the-outforc ... kedproject](https://www.moddb.com/games/the-outforce/downloads/packedproject)

Further info about file format: [http://www.watto.org/specs.html?specs=A ... F_OUTFORCE](http://www.watto.org/specs.html?specs=Archive_OPF_OUTFORCE)

I'm looking forward to your help and your positive response.

Moddb: [https://www.moddb.com/games/the-outforce/downloads](https://www.moddb.com/games/the-outforce/downloads)

Discord: [https://discord.com/invite/7RbzqN9](https://discord.com/invite/7RbzqN9)

Krisztian.
## Post #2
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2022-07-29T15:39:48+00:00
- Post Title: The Outforce .OPF file

Hi there!

I really need some help. 

There is a game named "The Outforce", it has a "packedproject.opf" file, which is a binary data container, so it contains assets, 3d model files, textures. 
I can unpack the whole .OPF file, but there are some fileformats thats structures are unknown for .CBaseClass .CGridMember, CUnit .CWeaponUnit. So, these fileformats structure are unknown, so I can not make an unpacker-repacker, only unpacker... 

[http://www.watto.org/specs.html?specs=A ... F_OUTFORCE](http://www.watto.org/specs.html?specs=Archive_OPF_OUTFORCE)

I have opened the game exe file with IDA view, and regarding the .opf file and fileformats I mentioned above I have found this (picture). Unfortunately, I'm not an expert in assembly, so I can not write assembly codes back to C++ :'( 

[https://i.kek.sh/GS54S13BZSL.jpg](https://i.kek.sh/GS54S13BZSL.jpg) 
[https://i.kek.sh/X58RsF7MhfQ.jpg](https://i.kek.sh/X58RsF7MhfQ.jpg)
[https://i.kek.sh/u5vDM79BccH.jpg](https://i.kek.sh/u5vDM79BccH.jpg)
[https://i.kek.sh/wMwsLIeTUrP.jpg](https://i.kek.sh/wMwsLIeTUrP.jpg)
[https://i.kek.sh/Cn3NeBy2hAe.jpg](https://i.kek.sh/Cn3NeBy2hAe.jpg)
[https://i.kek.sh/BhCvPcr5P72.jpg](https://i.kek.sh/BhCvPcr5P72.jpg)
[https://i.kek.sh/o3XPZupCdJQ.jpg](https://i.kek.sh/o3XPZupCdJQ.jpg)
[https://i.kek.sh/slUgtPmEddj.jpg](https://i.kek.sh/slUgtPmEddj.jpg)
[https://i.kek.sh/GS54S13BZSL.jpg](https://i.kek.sh/GS54S13BZSL.jpg)

I just want to make a program that can read PackedProject.OPF file, unpack its content, unpack fileformat's content (as mentioned above), then after modification repack it to PackedProject.OPF. The OPF file is NOT CRC protected ( so changing filesize is not count)!

Thank you very much in advance
## Post #3
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2022-07-29T16:05:51+00:00
- Post Title: The Outforce .OPF file

ups, I forget to add this:

For Opening such files, de devs used fileapi. h (ReadFile, GetFileSize, SetfilePointer, WriteFile). 

                                                            // FILEAPI.H
BOOL    ReadFile (HANDLE hFile, LPVOID lpBuffer, DWORD nNumberOfBytesToRead, LPDWORD nNumberOfBytesRead, LPOVERLAPPED lpOverlapped);
DWORD   GetFileSize(HANDLE hFile, LPDWORD lpFileSizeHeigh);
DWORD   SetFilePointer(HANDLE hFile, LONG lDistanceToMove, PLONG lpDistanceToMoveHigh, DWORD dwMoveMethod);
BOOL    WriteFile(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesWritten, LPOVERLAPPED lpOverlapped);


/*
offsets: 
*/

offset aSPackedproject; 	"%s\\PackedProject.OPF
offset aOutforcePacked; 	"Outforce Packed Content
offset aProject; 		"Project"
offset aEventDescs;		"Event Descs" 

offset 	FileName

offset aCbaseclass		;"CBaseClass"
offset aCunit			;"CUnit"
offset aCgridmember	;"CGridMember"
offset aCunitweapon		;"CUnitWeapon"
## Post #4
- Username: Winters
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-29T18:07:47+00:00
- Post Title: The Outforce .OPF file

I have this game, but I can't see any OPF files in game's directory after installing the game. I can see only BOX archives.
Do I need to apply some patches? My version of the game is 1.0.0.0.
What path is correct for this file?

In short - what is this file and how did you get it?
## Post #5
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2022-07-29T18:11:19+00:00
- Post Title: The Outforce .OPF file

Thank you very much for your comment! 

This .opf file was pulled out (unpacked) from Content.box with Watto's game extractor.


You can download it from Moddb site that way created by me: [https://www.moddb.com/games/the-outforc ... kedproject](https://www.moddb.com/games/the-outforce/downloads/packedproject)

here's the unpacked one: [https://www.moddb.com/games/the-outforc ... projectopf](https://www.moddb.com/games/the-outforce/downloads/unpacked-packedprojectopf)
## Post #6
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2022-07-30T19:14:26+00:00
- Post Title: The Outforce .OPF file

Not only unknown structures is trouble. Researched data also providing surprises. IMAGE blocks structure in OPF file from moddb not fit to specification from watto site. Seems like its have additional unknown 4 byte value after height, and 66 unknown bytes instead 74. 

```
    uint16 length;
    if( length ) char name[length];
};

struct HEADER {
    char signature_string[23];
    uint32 version;
    NAME project_name;
    NAME developer_name;
    NAME email;
    uint32 description_length;
    if( description_length )
        char description[description_length];

    uint16 unknown;
    uint32 unknown;
    uint32 unknown;
    
};

struct RGBA {
    ubyte r, g, b, a;
};

struct IMAGE {
    NAME filename;
    NAME source_path;
    NAME drive;
    uint32 width, height, unk1, red_bits, green_bits, blue_bits, alpha_bits; // new unk1 value
    uint32 unknown;
    uint32 unknown;
    uint32 unknown;

    ubyte unknown_bytes[66]; //instead 74
    
    uint32 num_colors[2];
    if( num_colors[0] )
        RGBA rgba[num_colors[0]];
    uint32 size_of_data;
    if( size_of_data )
        char data[size_of_data];
};


HEADER header;
uint32 num_images;
if( num_images )
    IMAGE image[num_images] <optimize=false>;
```


Also sometimes after JPEG data some unknown data is coming.
E.g. after 58th image block - "Effect_MIRANDA_Cloud" coming 10241 additional unknown bytes. Where stored or how calculate size of this data is'nt clear.
## Post #7
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2022-07-30T20:17:06+00:00
- Post Title: The Outforce .OPF file

Hi it is because I have sent .opf file from the demoversion of the game, not the full version. Full version can be downloaded from Moddb.

All I want to know, how to make a C++ program that can load, read this file and unpack its content and then (using assembly source) to determine the file structure for other fileformats such as .CBaseClass CGridMember CUnit CWeaponUnit
## Post #8
- Username: Winters
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Dec 17, 2017 3:28 am
- Post datetime: 2022-12-10T21:08:54+00:00
- Post Title: The Outforce .OPF file

> Reply from ikskoks ↑Sat Jul 30, 2022 2:07 am at Sat Jul 30, 2022 2:07 am
>
> 
I have this game, but I can't see any OPF files in game's directory after installing the game. I can see only BOX archives.
Do I need to apply some patches? My version of the game is 1.0.0.0.
What path is correct for this file?

In short - what is this file and how did you get it?
Hello! 

I just asked Watto to help me in this fileformat, so he updated he's software, the Game Extractor: [http://www.watto.org/game_extractor.html](http://www.watto.org/game_extractor.html) This can handle any .box files (reading, writing, renaming, replacing) as well as unpack, but not repack the PackedProject.opf file that contains the game assets.

I also have the 543 console commands, and now I'm working on a map editing tutorial, and my first mode for the game, the CES (Conflict in the Epsilon System).

I added some new loading screens (images), 2 maps (one from the demo game, and I converted a singleplayer map to skirmish), fixed a bug, etc etc. and started to redesign/improving the Gui.

Now I'm interested in an unpacker-repacker for the .opf file.


I started to build a community for The Outorce years ago:

Discord: [https://discord.com/invite/7RbzqN9](https://discord.com/invite/7RbzqN9) 
Moddb: [https://www.moddb.com/games/the-outforce](https://www.moddb.com/games/the-outforce)

Now you can buy the full version of the game (digital version) at: [https://www.zoom-platform.com/product/the-outforce](https://www.zoom-platform.com/product/the-outforce) it's unavailable now, because it will be updated. This version works well in full/widescreen on modern OS like windows 10/11 with out any issues!
