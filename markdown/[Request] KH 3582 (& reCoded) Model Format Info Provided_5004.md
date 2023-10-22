## Post #1
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-10T21:01:43+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

Hey everyone, I'd really like to be able to view and edit 3D models from Kingdom Hearts: 358/2 Days in a 3D program of my choice. I know of a tool called Consol Tool made by Low Lines that can view them but it doesn't have an export function and there is no easy way to capture the model from his openGL viewer.

He has provided documention on the format though that I am hoping someone here could use to make a simple converter. Perhaps to something like .obj or something else easy to import.

You can find the documentation on the format here: [http://llref.emutalk.net/v2/docs.php?or ... d=bmd0.xml](http://llref.emutalk.net/v2/docs.php?order=&sort=&page=&id=bmd0.xml)

Information on animations that he has so far is also provided here: [http://llref.emutalk.net/v2/docs.php?or ... d=bca0.xml](http://llref.emutalk.net/v2/docs.php?order=&sort=&page=&id=bca0.xml) Though animations are not my goal as I'm trying to get to the stationary models used as the playing area of the game. Though eventually player models and such would be nice as well. Though I would assume if stationary buildings could be converted characters wouldn't be too hard in addition to it.

You can get the raw models here (Note: The models I'm am interested in are in the Mi>Wd folder): [http://www.propl.nl/random/KH3582_Models.zip](http://www.propl.nl/random/KH3582_Models.zip)

Can anyone please help me out? I would be very grateful. This same information may be applicable to other DS game models as well. 

Thank you for any help you can provide me.

Edit: I have more progress on the files of Days and Re:coded thanks to Barubary. I'll post quotes of what he told me about it. I hope this can help you guys figure out this format even further.

> Reply from Barubary
>
> 
- .z files are LZ-compressed files
- .p2 files have the following format:
Code: Select allchar[2] magicHeader; // 'P2'
WORD nFiles; // maybe longer/shorter. MSB flags filenames
QWORD padding;
DWORD dataStart;
WORD offsets[nFiles]; // to get real offset: << 9 + dataStart
WORD padding; // only if nFiles % 2 = 1
DWORD sizesAndFlags[nFiles]; // MSB flags compression
char filenames[8][nFiles]; // length 0 if nFiles & 0x8000 != 0
byte* data; // possibly preceded by padding, so that start matches dataStart
- .pak files have the following format:
Code: Select allchar[4] magicHeader; // 'KAPH'
DWORD padding; // ?
// if any of the offsets below are FFFFFFFF, it is not present
DWORD BCAdataOffset;
DWORD BVAdataOffset;
DWORD BMAdataOffset;
DWORD BTPdataOffset;
DWORD BTAdataOffset;
DWORD unknownOffset1;
DWORD unknownOffset2;
DWORD BMDdataOffset;

each offsets points to data formatted as such:
DWORD one; // always 1? (maybe number of files with this format? never seen something else though)
DWORD fileStart;
DWORD fileLength;
- .p2d / .pobj files have the following format:
Code: Select allchar[4] magicHeader; // 'D2KP'
DWORD padding;
DWORD* FATFolderEntryOffsets; // continues up to first offset. some offsets may be 0xFFFFFFFF

// each FAT Folder entry is formatted as follows:
DWORD numFiles;
DWORD[numFiles] offsets;
DWORD[numFiles] sizes;

// the data follows, possibly preceded by padding.

And how he actually decompressed them with his tools:

> Reply from Barubary
>
> For 358/2 Days (and for my R:c rips) I used an unpacker that could only decompress one specific file or folder at a time, and thus quite unusable for anybody who didn't create the program in the first place. I've now ported it to my more generic unpacker, NinUnpack, which should now be able to unpack all packages in both KH DS games. Drag a folder or a (set of) files on the executable (or use the command line) to unpack the given files. (providing a folder will only unpack the files directly in that folder; it is not recursive)
The game has three pack formats: P2, PK2D an HPAK. The first is just a generic archive file, like NARC but without folders. It has extension .p2 (or sometimes .p2f), but sometimes there is no extension at all for these files. PK2D (extension .D2KP, possibly others as well) only packs 2D graphic files. HPAK (extension .KAPH or .pak) only packs 3D graphic files.

Note that some files are compressed as well (in the normal filesystem, in packs, and I believe also in packs in packs). DSDecmp (or any other decompressor for DS formats) should work on those files (they usually have a .z extension, but sometimes none).
## Post #2
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-09-10T21:25:54+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

If I may, I too would like to add my request to a DX-based viewer with export function or just converter as stated by Zerox. Thanks in advance.
## Post #3
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-09-13T16:57:13+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

zerox can you upload this console tool,since i can;t find a way to download this from anywhere ^^"
## Post #4
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-14T00:25:09+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

Conole Tool is a program being developed by Low Lines. You can get it here in his signature: [http://www.romhacking.net/forum/index.p ... 407.0.html](http://www.romhacking.net/forum/index.php/topic,8407.0.html)

Though as I mentioned there isn't a way to get the models from his viewer (and I'll be honest it's not the best viewer I've ever seen.

For this reason I'd really like some sort of converter to be developed. Or perhaps someone could guide me in how I should start developing this myself. If anyone has such interest please let me know, either here in the thread or pm.
## Post #5
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-14T17:00:52+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

Ah, its Java. No 3d Ripping software works with it :/

So until he makes a windows application, I don't think you'll get them
## Post #6
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-14T21:23:46+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

> Reply from ultimaespio
>
> Ah, its Java. No 3d Ripping software works with it :/

So until he makes a windows application, I don't think you'll get them

Indeed it is. As I mentioned perhaps someone knows how to convert a .jar to a .exe that functions well still. It is also openGL though and he intends to stay with java only because of it's cross-platform ability.
## Post #7
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-10-01T05:04:19+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

I'll see if I can whip anything up. But for the meantime you guys can get [DJ Java Decompiler](http://members.fortunecity.com/neshkov/dj.html) and decompile the jar file. You'll at least be able to see how the application reads the file. Doesn't mean its the right way of reading them, just means it "works".
## Post #8
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-01T13:29:37+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

I was gonna forward you to Modelsresource...but it was you who uploaded it, so...

Apparently I've uploaded models onto there too, but I haven't :S
## Post #9
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-02T15:06:03+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

> Reply from invisghost
>
> I'll see if I can whip anything up. But for the meantime you guys can get DJ Java Decompiler and decompile the jar file. You'll at least be able to see how the application reads the file. Doesn't mean its the right way of reading them, just means it "works".
Awesome this is fantastic news. I tried Java Decompiler and it worked pretty well for getting access to the format information as .j files that could be opened in Notepad. I also posted links to the information he has so far at the top of the thread, as well as sample model files if that helps any.

It's his newest version that displays them at least mostly correct:

[http://llref.emutalk.net/downloads/cons ... _demo2.zip](http://llref.emutalk.net/downloads/console_tool_demo2.zip)

Thank you and good luck. =)

> Reply from ultimaespio
>
> I was gonna forward you to Modelsresource...but it was you who uploaded it, so...

Apparently I've uploaded models onto there too, but I haven't :S

Eh who were you going to send there, who uploaded what? And what do you mean you put models there but you haven't that doesn't make much sense? Besides your name isn't on their forum at all.
## Post #10
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-02T15:15:19+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

I was talking to you. I ripped models years ago on another forum, and someone else has uploaded them to models resource with my name.

[http://www.models-resource.com/submitter/ultima%20espio](http://www.models-resource.com/submitter/ultima%20espio)

And I meant that you were the one who uploaded the Moogle model I was gonna show you
## Post #11
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-02T18:36:22+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

Huh that's odd. They're rules say that no rips will be added unless the original ripper submits them. I guess those might be relics from when they were testing the build of the site and before all the rules were in place.

Ah well. But yeah the XIII Moogle was my rip though it was a pain to do so: [http://www.spriters-resource.com/commun ... ?tid=14817](http://www.spriters-resource.com/community/showthread.php?tid=14817)

This sorta describes my process there.
## Post #12
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-02T19:34:08+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

I'm not really interested in 358 Days ones, a bit too low poly for me 

I'd like to have a look at them though, compare them to other ds models.

Anyway, I recognise some of those members names on that forum. Shadowth117 sounds really familiar...I don't mind about you uploading those models, I was just a bit surprised to find that I was the one who submitted it.
## Post #13
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-10-04T09:03:11+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

But still,its gonna be great if we can extract the model
## Post #14
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-09T03:14:15+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

Hey I bring good news, Kingdom Hearts Re: Coded uses the exact same format so after a converter for this is made we'll have access to two games models!   

Well invisghost, true to your name you've been invisible for a week. Do you got any news for us? Any obstacles you've encountered that perhaps we could help with?
## Post #15
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-10-21T08:05:37+00:00
- Post Title: [Request] KH 358/2 (& re:Coded) Model Format Info Provided

I'd love to get those Aubade z files. I mean I have them, but not in a format my computer can understand. With Crystal Tile, I saw that one of the files, w_.p2 in Roxas's ba folder, had the words Material, MDL, pro_w02, and pro0_trace in it, and since MDL is a common 3D model file type for Kingdom Hearts games, if we could just unpack them somehow then we would probably have the models.
## Post #16
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-29T06:27:56+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

I've added information on the file compression and how to uncompress them thanks to Barubary. Hopefully this will motivate someone with ability to help with this format to look at it.
## Post #17
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-29T07:14:55+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

This is incredibly helpful. Thank you oh so very much. But why are all the mi/mi files in CAKP format? All I could find on CAKP format was at [http://monkeystraducoes.com/projetos/do ... kh3582_doc](http://monkeystraducoes.com/projetos/doku.php/hansen:kh3582_doc) and [http://www.romhacking.trd.br/index.php?topic=4425.105](http://www.romhacking.trd.br/index.php?topic=4425.105) .
## Post #18
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-04T06:27:16+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

Lmao sorry guys I've kinda been swamped with things coming at me from all directions. I've lost my C++ template I was working on for the file format so I'll need to start over, Totally gapped this.   sorry buddies. I'll post stuff as it happens but it might be a week or so since I'm still working on another game's editor atm.
## Post #19
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-12-04T07:22:10+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

I feel as if I've seen a ghost!  It's great to see you again invisghost, I was wondering where you vanished too. I don't know if you already know this but Mr. Adults has made it possible to develop plug-in's for Noesis. As far as I know their C++ based and it may even make your work with this easier.

Anyway I hope the information I've added since your last visit helps out.
## Post #20
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-04T09:45:46+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

Alright so a lil update. I'm still trying to flush out the file format, this is what I've understood so far. I don't know how it stores floats cause its using 2byte floats and there are so many ways they could be using. Once I figure this out I'll move onto making a application around it. More to come another day!   

> Reply from Zerox
>
> I don't know if you already know this but Mr. Adults has made it possible to develop plug-in's for Noesis. As far as I know their C++ based and it may even make your work with this easier.
Eh its a good viewer and all but I im very reluctant to make a plugin for any closed source program. No way to fix the gay issues that arise  

The [010 Editor](http://www.sweetscape.com/010editor/) C++ Template code:

```
struct Nitro3DHeader
{
    char MagicStamp[4];
    int A;
    int FileSize;
    short HeaderSize;
    short NumberOfSections;
    int SectionOffsets[NumberOfSections];
};
// Object Name Structure (Used cause you cant have char [NumOfObjects][16])
struct ObjectName
{
    char Name[16];
};
struct ObjectHeader
{
    byte Dummy;
    byte NumOfObjects;
    short HeaderSize;
    
    // Unknown block
    short UnknownBlockDataSize;
    short UnknownBlockBlockSize;
    int UnknownBlockConstant;
    byte UnknownBlockData[4*NumOfObjects];

    // Offset Block
    short OffsetBlockDataSize;
    short OffsetBlockBlockSize;
    int OffsetBlockObjectOffsets[NumOfObjects];

    // Name Block
    ObjectName Names[NumOfObjects];
};
struct DataBlockHeader
{
    int BlockSize;		
    int BonesOffset;		
    int MaterialsOffset;		
    int PolygonStartOffset;		
    int PolygonEndOffset;		
    byte Unknown;		
    byte Unknown;		
    byte Unknown;		
    byte NumOfObjects;		
    byte NumOfMaterials;		
    byte NumOfPolygons;
    byte Unknown2[6];
    byte Unknown;		
    byte ScaleMode;		
    ushort Unknown;		
    ushort NumOfVertices;		
    ushort NumOfSurfaces;		
    ushort NumOfTriangles;		
    ushort NumOfQuads;		
    short BoundingBoxX;		
    short BoundingBoxY;		
    short BoundingBoxZ;		
    short BoundingBoxWidth;		
    short BoundingBoxHeight;		
    short BoundingBoxDepth;		
    byte RunTimeData[8];
};
struct ObjectData
{
    short TransformationFlags;
    short Padding;		
    // Translation XYZ (If T=0)
    int XValue;		
    int YValue;		
    int ZValue;		
    // Pivot (If P=1)
    short Value1;		
    short Value2;		
    // Scale XYZ (If S=0)
    int XScale;		
    int YScale;		
    int ZScale;		
    // Rotation? (If P=0 & R=0)
    short Value1;		
    short Value2;		
    short Value3;		
    short Value4;		
    short Value5;		
    short Value6;		
    short Value7;		
    short Value8;	
};
struct ModelSection
{
    char MagicStamp[4];
    int SectionSize;

    ObjectHeader ObjHeader;
    
    DataBlockHeader ModelDataHeader;

    ObjectHeader ObjHeader;

    ObjectData ObjData[ObjHeader.NumOfObjects];
};

Nitro3DHeader Header;
local int i<hidden=true> = 0;
for (i =0; i < Header.NumberOfSections; i++)
{
    FSeek(Header.SectionOffsets[i]);
    if (ReadInt(FTell()) == 810304589) // MDL0
        ModelSection MdlSection;
    else
    {
        local string s<hidden=true>;
        local char buf[4]<hidden=true>;
        ReadBytes(buf, FTell(), 4);
        SPrintf(s, "Unsupported section type '%s' at offset %Xh", buf, FTell());
        Warning(s);
    }
}
```
## Post #21
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-12-04T10:41:02+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

> Reply from invisghost
>
> Eh its a good viewer and all but I im very reluctant to make a plugin for any closed source program. No way to fix the gay issues that arise
You have nothing to fear, then. Plugin issues exposed by third party development thus far have not been joyous or homosexual in nature.
## Post #22
- Username: Barubary
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2009 7:21 pm
- Post datetime: 2010-12-04T15:02:42+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

> Reply from invisghost
>
> Alright so a lil update. I'm still trying to flush out the file format, this is what I've understood so far. I don't know how it stores floats cause its using 2byte floats and there are so many ways they could be using. Once I figure this out I'll move onto making a application around it. More to come another day!
I haven't checked myself, but they're probably 1.3.12 fixed-point numbers ('v16') (as suggested [here](http://dev-scene.com/NDS/DOCfixed_point)).
## Post #23
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-04T23:14:09+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

Thanks barubary, turns out you were right. All I have to do to get the float is divide the short by a specific number (in relation to the ScaleMode field).
## Post #24
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-05T22:53:23+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

Another format used in the game is MODS N3. Its a Mobiclip-encoded video file, using an algorithm specifically designed for the DS to increase battery life. If there were some way to play the files directly, even on a DS or DS emulator, one could view the videos before the point in the game when they play. If the 3DS still uses this format, one could view the pre-rendered cutscenes of a game that doesn't already have a Theater Mode. At least one could see the raw videos in their original quality. They're probably encoded from AVIs. You can download the Mobiclip codec, but not the one that plays DS files. Not to turn attention away from the precious BMD0 and MDLX files, which are far more important because the videos are online anyway, but if anyone already has information on how to play these files, that would be helpful.
## Post #25
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-11T22:58:51+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

The format is incorrect.  Fields are out of order and the console tool itself doesn't even load the models right.
## Post #26
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-11T23:21:31+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

What do you mean when you say the console tool isn't loading them right? Is that why there are those misplaced vertices on the models?
## Post #27
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-04T16:24:37+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

Sorry for bumping, but this seemed like the best place to ask.

If 358 days and recoded use the same format, does that mean that you could copy Roxas' data from 358 days and replace Sora's in recoded with it? It would be cool to replace characters and levels.

EDIT: Yes, you can. Ported over Ven (from the cutscene) and it works. Just his arm goes over his head.

No textures though.
## Post #28
- Username: wonka1004
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 20, 2019 9:00 am
- Post datetime: 2019-05-05T02:10:14+00:00
- Post Title: Re: [Request] Converter for KH 358/2 Models Format Info Prov

> Reply from ultimaespio ↑Wed Jan 05, 2011 12:24 am at Wed Jan 05, 2011 12:24 am
>
> 
Sorry for bumping, but this seemed like the best place to ask.

If 358 days and recoded use the same format, does that mean that you could copy Roxas' data from 358 days and replace Sora's in recoded with it? It would be cool to replace characters and levels.

EDIT: Yes, you can. Ported over Ven (from the cutscene) and it works. Just his arm goes over his head.

No textures though.
Do you know how to view .CAKP files from recoded? I want to extract the maps
