## Post #1
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2015-01-20T10:26:36+00:00
- Post Title: Resident Evil HD REMASTER PC

Help extract the files from the archive of the ARC  and Language file edit.


[https://www.dropbox.com/s/kiqu82bt3asem ... g.arc?dl=0](https://www.dropbox.com/s/kiqu82bt3asemud/subscr_eng.arc?dl=0)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-01-20T12:55:56+00:00
- Post Title: Resident Evil HD REMASTER PC

This is the relevant information needed for extracting the archive:



screenshot.png (39.4 KiB) Viewed 753 times


The two files inside the archive are zlib-compressed (indicated by 78 9C / xœ).
To decompress them, simply add the extension .zlib to the filename and drag & drop the files onto the application zdrop.exe: [http://www.mediafire.com/download/1adck ... /zdrop.zip](http://www.mediafire.com/download/1adckp30kk3btdb/zdrop.zip)
The uncompressed files are some sort of texture files, which I don't know how to handle.
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-01-20T13:02:37+00:00
- Post Title: Resident Evil HD REMASTER PC

This ARC file contains only 2 textures.
You can use Luigi's QBMS script for extracting them: [http://aluigi.altervista.org/papers/bms/dmc4.bms](http://aluigi.altervista.org/papers/bms/dmc4.bms)

sub_file_00_ID_HQ = 2048 x 1024, no mipmap
sub_status_00_ID_HQ = 2048 x 2048, no mipmap

But I don't know what is the pixel format. You can use DXT5, but they will be greenish.
Ex.

[](http://www.fastimages.eu/?v=substatus0.jpg)
## Post #4
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-01-21T02:04:05+00:00
- Post Title: Resident Evil HD REMASTER PC

> Reply from MuratG
>
> Help extract the files from the archive of the ARC  and Language file edit.


https://www.dropbox.com/s/kiqu82bt3asem ... g.arc?dl=0

You can use ARC Tool to unpack and repack *.arc file. But need convert *.tex to dds and compile *.gmd to translate:



*.tex from your file: [https://www.dropbox.com/s/9619rdolyniao ... e.rar?dl=0](https://www.dropbox.com/s/9619rdolyniaomo/Resident%20Evil%20Remaster%20Texture.rar?dl=0)
## Post #5
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-01-21T03:28:46+00:00
- Post Title: Resident Evil HD REMASTER PC

> Reply from merlinsvk
>
> This ARC file contains only 2 textures.
You can use Luigi's QBMS script for extracting them: http://aluigi.altervista.org/papers/bms/dmc4.bms

sub_file_00_ID_HQ = 2048 x 1024, no mipmap
sub_status_00_ID_HQ = 2048 x 2048, no mipmap

But I don't know what is the pixel format. You can use DXT5, but they will be greenish.
Ex.

Could you write a script (convert .tex to dds and dds2tex)?
Here is example file: 

 tex example.rar
(188.59 KiB) Downloaded 87 times

 (512x512)
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-01-21T08:09:08+00:00
- Post Title: Resident Evil HD REMASTER PC

I tried, but there is no width and height written in TEX header, so I think the textures has pre-defined formats (by looking on offset 0xB in .tex file). Something like 0x20 = 2048x1024, 0x40 = 2048x2048 and so on. 

But I still don't know the correct pixel format. Maybe it's DirectX 11 texture.
## Post #7
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-01-23T02:32:52+00:00
- Post Title: Resident Evil HD REMASTER PC

> Reply from merlinsvk
>
> I tried, but there is no width and height written in TEX header, so I think the textures has pre-defined formats (by looking on offset 0xB in .tex file). Something like 0x20 = 2048x1024, 0x40 = 2048x2048 and so on. 

But I still don't know the correct pixel format. Maybe it's DirectX 11 texture.

Maybe can help: 

> RE5 header:
>
> 4 bytes - magic
>
> 4 bytes - unknown1
>
> 4 bytes - unknown2
>
> 2 bytes - width
>
> 2 bytes - height
>
> 1 byte - tex type
>
> 
>
> Tex types:
>
> 0x52 = DXT1
>
> 0x54 = DXT5
>
> 0x7B = DXT5a
>
> 0x7C = CTX1
>
> 0x86 = ARGB
>
> 
>
> RE6 header:
>
> 4 bytes - magic
>
> 4 bytes - unknown
>
> 3 bytes - resolution
>
> 1 byte - mip count
>
> 2 bytes - unknown
>
> 1 byte - tex type
>
> 
>
> Tex types:
>
> 0x14 = DXT1
>
> 0x18 = DXT5
>
> 0x19 = DXT5a
>
> 0x1E = CTX1
## Post #8
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-01-25T02:29:02+00:00
- Post Title: Resident Evil HD REMASTER PC

Has anyone bothered to update arctool to work for this? If not i can prob do so soon
## Post #9
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2015-01-25T06:53:35+00:00
- Post Title: Resident Evil HD REMASTER PC

> Reply from cra0
>
> Has anyone bothered to update arctool to work for this? If not i can prob do so soon
Arctool does not work with TEX-files.
## Post #10
- Username: Omission7x
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Nov 15, 2014 4:15 pm
- Post datetime: 2015-01-25T09:31:56+00:00
- Post Title: Resident Evil HD REMASTER PC

Has anyone checked if there were more in engine assets of the mansion left in the game's code? When the remaster was first debuted capcom used real time assets rendered in the MT engine to show off the mansion. [http://images.gamersyde.com/image_resid ... 1_0002.jpg](http://images.gamersyde.com/image_resident_evil-25838-3041_0002.jpg)

I was wondering why this was scrapped. The only explanation capcom gave was not that the technology wasn't capable, but that they didn't want players to see more than was originally intended. They said this would lead to reveals.

Problem is static backdrops and HD rendered 3d objects do also lead to reveals. puzzles, characters, and objects are not that difficult to identify anymore. Anyways, it seems like a missed opportunity. Maybe someone could be able to salvage the assets, or at least find a way to let modders create level assets into the game.
## Post #11
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-01-25T12:00:04+00:00
- Post Title: Resident Evil HD REMASTER PC

> Reply from LinkOFF
>
> cra0 wrote:Has anyone bothered to update arctool to work for this? If not i can prob do so soon
Arctool does not work with TEX-files.

most likely they changed the format a bit attach some samples and let me take a look for you
## Post #12
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2015-01-25T13:22:13+00:00
- Post Title: Resident Evil HD REMASTER PC

> Reply from cra0
>
> LinkOFF wrote:cra0 wrote:Has anyone bothered to update arctool to work for this? If not i can prob do so soon
Arctool does not work with TEX-files.

most likely they changed the format a bit attach some samples and let me take a look for you
[https://www.dropbox.com/s/2kefyryvmy0m2 ... P.zip?dl=0](https://www.dropbox.com/s/2kefyryvmy0m2r0/GUIIcon_NOMIP.zip?dl=0)
## Post #13
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-01-26T07:58:48+00:00
- Post Title: Resident Evil HD REMASTER PC

> Reply from LinkOFF
>
> 
https://www.dropbox.com/s/2kefyryvmy0m2 ... P.zip?dl=0

tex format not that hard

```
//
// Format: Capcom RE HD Texture
// Author: Cra0kalo
// Author Site: dev.cra0kalo.com
//--------------------------------------

//*Data Info*
//BigEndian();

//Defines
typedef  float vec2[2];
typedef  float vec3[3];
typedef  string asciiz;
typedef  char  magic4[4];
typedef int bool;
#define true  1
#define false 0

enum <byte> tex_format
{
    DXT_1_a    = 0x13, // i think
    DXT_1      = 0x14,
    ARGB8888   = 0x28,
    DXT_5      = 0x31
};


typedef struct
{
    uint16  key;
    uint16  Var;
} tex_mipTable;

typedef struct
{
    magic4      fmtMagic;
    uint16      fmt_varA;
    uint16      fmt_varB;
    byte        fmt_mipCount;
    byte        unk_bA;
    byte        unk_bB;
    byte        unk_bc;
    
    byte        unk_varA;
    tex_format  fmt_textype;
    byte        unk_varC;
    byte        unk_varD;

    //read each mip block thing whatever the fuck this is
    local int x;
    for(x = 0; x < fmt_mipCount; x++)
    {
        tex_mipTable    curMip;
    }

    
} tex_head;



typedef struct
{
    byte    texData[4];
} tex_data;


//File begin
tex_head    header;

```


010 editor template

To calculate the byte size you just do something like this
pitch As Integer = ((width + 3) \ 4) * ((height + 3) \ 4) * ((resolution + 3) \ 4)

Anyhow the Arctool seems to work with RE HD so i don't see any need to make another tool
## Post #14
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-26T08:06:47+00:00
- Post Title: Resident Evil HD REMASTER PC

2 things i cannot see dimensions of the texture in your template(cannot test im at work). Also if you doing this for X360, all texture dimensions need to be possible divided by 128, this is the common rule for most textures for X360 games. this is just a tip
## Post #15
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-01-26T08:10:23+00:00
- Post Title: Resident Evil HD REMASTER PC

> Reply from michalss
>
> 2 things i cannot see dimensions of the texture in your template(cannot test im at work). Also if you doing this for X360, all texture dimensions need to be possible divided by 128, this is the common rule for most textures for X360 games. this is just a tip
Yeah I have no idea where they store the dimentions its prob in the header somewhere but not stored as a uint8 16 or 32
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-26T09:41:27+00:00
- Post Title: Re: Resident Evil HD REMASTER PC

> Reply from cra0
>
> michalss wrote:2 things i cannot see dimensions of the texture in your template(cannot test im at work). Also if you doing this for X360, all texture dimensions need to be possible divided by 128, this is the common rule for most textures for X360 games. this is just a tip 
Yeah I have no idea where they store the dimentions its prob in the header somewhere but not stored as a uint8 16 or 32

I will have a look it can be wide bit-shifted somewhere, not sure or even not there at all  To be hones with RE games i always did simple procedure mistake/correct sort of thing... It is much faster then look for correct dimensions in binary for most cases
## Post #17
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2015-01-26T09:56:01+00:00
- Post Title: Re: Resident Evil HD REMASTER PC

Width\Height store in 3 bytes in header 09-0B, 12 bit on each value. But also need use multiplier for this values to find out real texture size, in some case it's width*2, height*4, some width*4 height*2, other width*2 height*2, i don't know how proper figure out this multipliers
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-28T17:35:19+00:00
- Post Title: Re: Resident Evil HD REMASTER PC

> Reply from merlinsvk
>
> You can use DXT5, but they will be greenish.
Ex.How did you get the details from sub_status_00_ID_HQ raw file? edit: ok, got the details with DXT11, BC5UNORM (format typeID: 0x2B?) but still not nice



sub_status_00_ID_HQ-missDetails.JPG (87.71 KiB) Viewed 303 times



(Using a fake DDS header I'm going to change the bitmasks in DDS_PIXELFORMAT (or the dwCaps DWORD in the DDS_HEADER structure) but it's a little bit tedious trying out the various possibilities.)
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-28T22:54:32+00:00
- Post Title: Re: Resident Evil HD REMASTER PC

format description from cra0 (thx  ) makes sense (GUIIcon_NOMIP.tex):



GUIIcon_NOMIP.tex.JPG (43.25 KiB) Viewed 286 times



though I feel I'm missing something.

This is the header:

```

00000  54 45 58 00 9D 20 00 20  01 40 00 08 01 28 01 00   TEX
```
where the texture type is given at 0x0D: 0x28
## Post #20
- Username: reaccount
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 08, 2016 10:11 am
- Post datetime: 2016-07-08T02:18:49+00:00
- Post Title: Re: Resident Evil HD REMASTER PC

> Reply from shakotay2
>
> merlinsvk wrote:You can use DXT5, but they will be greenish.

(Using a fake DDS header I'm going to change the bitmasks in DDS_PIXELFORMAT (or the dwCaps DWORD in the DDS_HEADER structure) but it's a little bit tedious trying out the various possibilities.)
I've been trying to figure out how to edit the colors of these files for a while now, but I'm out of my depth. Any progress on making those textures not look green and purple? When you say that it's tedious trying out the various possibilities, is there something I can do in a program or whatever if I've got the time?
## Post #21
- Username: Big Boss
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 31, 2020 9:10 am
- Post datetime: 2020-05-19T21:55:25+00:00
- Post Title: Re: Resident Evil HD REMASTER PC

Please help me, I have a problem, I extract the textures from the RE HD, and the RE0 HD Xbox 360 without problems, however, when I reimport, even without being edited, those with _MM.TEX, are buggy, that in the Xbox 360 version, they extract in .TGA, and are reimported without problems, with the exception of those with _MM.TGA, when they are reimported, they bug, break, and when you put them in the game, it gets buggy, or it extracts again it gets buggy, even if it doesn't edit them, extract them and reimport them, they bug, break, blur, I don't know what to do, .TXT file of them, when extracted are as follows:                            TEX                            
                           Format = DXT5A                            
                           Mips = 8                            
                           Textype = 25 
The sizes vary for each texture, how can I solve this problem? Can someone help me? I'm just having problems with this type !, the others are normal, can someone help me?
## Post #22
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2020-06-11T01:24:33+00:00
- Post Title: Re: Resident Evil HD REMASTER PC

> when I reimport, even without being edited, those with _MM.TEX, are buggy,

The reason is probably texture swizzling, or the 'greenish/pinkish' normal map textures. Basically the game swaps the RGB channels of the textures, to GRB or something. That's why they look greenish on your 3d program.

Noesis has a functionality for texture swizzling, I remember being helped by Mr. Adults way back. You can also try swapping the channels in a photo editor program that can read DSS, e.g. photoshop + nvidia plugins  or GIMP + plugin.
