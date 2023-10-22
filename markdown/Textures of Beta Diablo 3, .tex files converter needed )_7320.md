## Post #1
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-08T08:44:34+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

Hi guys,

here is some samples of Diablo 3 textures files.

Could someone take a look and find a way to convert this .tex (textures files) into dds or tga files ?

Thanks.

file : [http://dl.free.fr/q1mpHIHGZ/D3_sample.rar](http://dl.free.fr/q1mpHIHGZ/D3_sample.rar)
## Post #2
- Username: aquarius
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 06, 2010 1:53 am
- Post datetime: 2011-09-08T09:43:05+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

> Reply from Tabris
>
> Hi guys,

here is some samples of Diablo 3 textures files.

Could someone take a look and find a way to convert this .tex (textures files) into dds or tga files ?

Thanks.

file : http://dl.free.fr/q1mpHIHGZ/D3_sample.rar
## Post #3
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-08T12:14:30+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

I've tried severals "Tex to tga" converters, and for now.. nothing
## Post #4
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-08T12:25:31+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

> Reply from Tabris
>
> I've tried severals "Tex to tga" converters, and for now.. nothing
open file via F3 in total commander and you will see that its not normal texture but just container. Second half of file looks like it contains small data streams but i didnt found what format it is or how it is xored bcause im short of time
## Post #5
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-08T14:35:03+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

I don't have Total commander   .

Here is a new package made from new assets of the lastest patch : [http://dl.free.fr/muRbxNBnU/afterpatch.rar](http://dl.free.fr/muRbxNBnU/afterpatch.rar)
## Post #6
- Username: noopic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 08, 2011 11:43 pm
- Post datetime: 2011-09-08T15:50:32+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

SirLoon, I also can not find that kind of format. The only thing that I realized that some blocks are repeated at intervals of 48 characters. I understand that in this container are the TGA data files and maybe even some information. Perhaps in archives.
## Post #7
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-08T16:29:04+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

> Reply from noopic
>
> SirLoon, I also can not find that kind of format. The only thing that I realized that some blocks are repeated at intervals of 48 characters. I understand that in this container are the TGA data files and maybe even some information. Perhaps in archives.
i already tryed tga files and it doesnt works. first block is kinda weird it looks to be identical to headers of next blocks
## Post #8
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-09-08T17:28:19+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

this is Diablo III's new format, the first 40 byte ("DEADBEEF" header) is just a generic header, 
after that comes data that is unique to every filetype, but normaly an offset table follows
the game uses file ext to find out how to read the file, 

tex files are container, 
a simple bms script to extract raw data: (still not readable, but better to analys)

```
get numFiles long

for x = 0 to numFiles
get Offset long
get Size long

math Offset += 16

set Name x
string Name += ".tex"

log Name Offset Size

next x
```
## Post #9
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-08T19:04:02+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

The files you're talking about, could that be these list files ?

[http://dl.free.fr/viwQRMCWy](http://dl.free.fr/viwQRMCWy)
## Post #10
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-08T19:23:21+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

> Reply from Falo
>
> this is Diablo III's new format, the first 40 byte ("DEADBEEF" header) is just a generic header, 
after that comes data that is unique to every filetype, but normaly an offset table follows
the game uses file ext to find out how to read the file, 

tex files are container, 
a simple bms script to extract raw data: (still not readable, but better to analys)
Code: Select allgoto 0x34
get numFiles long

for x = 0 to numFiles
get Offset long
get Size long

math Offset += 16

set Name x
string Name += ".tex"

log Name Offset Size

next x
you extracted one capsule but you need extract rest. find offset 0x12368 and its start of header of some file which looks xored, there are many of them
## Post #11
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-09-08T23:42:06+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

> Reply from Tabris
>
> The files you're talking about, could that be these list files ?

http://dl.free.fr/viwQRMCWy
nope, that's filelists, i'm not talking about the mpq's, every file inside the D3 MPQ's has the DEADBEEF header.

> Reply from SirLoon
>
> you extracted one capsule but you need extract rest. find offset 0x12368 and its start of header of some file which looks xored, there are many of them

there is no xored part ? your offset 0x12368 points directly into the raw textures

*.tex files are:
- 0xDEADBEEF header
- offset table (if more then 1 file, then every other file is a mip-map)
- original file names (before converting to *.tex) & some unknown data
- raw textures

the script extracts only the raw image (RGB8888), this is already viewable with texturefinder, 
we need to find out what the unknown data is to extract real images.

i just don't really care about textures to do that, i'm more for 3D Models ^^
[](http://www.imagebanana.com/view/fmh9fq4k/trDun_Crypt_Skeletal_Throne.jpg)
## Post #12
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-09T06:04:05+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

Nice how did you do that ? take a look on their 3d models could also be interesting
## Post #13
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-09T06:57:04+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

> Reply from Falo
>
> Tabris wrote:The files you're talking about, could that be these list files ?

http://dl.free.fr/viwQRMCWy
nope, that's filelists, i'm not talking about the mpq's, every file inside the D3 MPQ's has the DEADBEEF header.
SirLoon wrote:you extracted one capsule but you need extract rest. find offset 0x12368 and its start of header of some file which looks xored, there are many of them

there is no xored part ? your offset 0x12368 points directly into the raw textures

*.tex files are:
- 0xDEADBEEF header
- offset table (if more then 1 file, then every other file is a mip-map)
- original file names (before converting to *.tex) & some unknown data
- raw textures

the script extracts only the raw image (RGB8888), this is already viewable with texturefinder, 
we need to find out what the unknown data is to extract real images.

i just don't really care about textures to do that, i'm more for 3D Models ^^
i know about deadbeef, thats from diablo since 1.10 patch, but i dont know structure of tex file
## Post #14
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-09T09:06:57+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: anhhungmeo1234
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Aug 15, 2010 4:48 pm
- Post datetime: 2011-09-09T11:44:04+00:00
- Post Title: Textures of Beta Diablo 3, ".tex" files converter needed :)

Hey Falo! How to extract D3's mpq and how to open model of diablo 3
## Post #16
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-09T14:08:53+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from anhhungmeo1234
>
> Hey Falo! How to extract D3's mpq and how to open model of diablo 3

to extract it's pretty simple, you just need this : 

[http://www.zezula.net/en/mpq/download.html](http://www.zezula.net/en/mpq/download.html)

But to convert it into .obj files, I don't know, I'm waiting like you the answer of Falo
## Post #17
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-09-09T16:22:52+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

- extract "CoreData.mpq\PhysMesh\*.phm"

use this 010 Editor Script:

```
//--- 010 Editor v3.2.1 Binary Template
//
// File: Diablo III *.phm
// Author: Falo
// Revision: 1.0
//--------------------------------------
struct{
    ubyte DEADBEEF[16];
    uint unk1[5];
    int ofsMeshHeader;
    int sizeMeshHeader;

    if(ofsMeshHeader)
    {
        FSeek(ofsMeshHeader + 16);
        struct MESHHEADER meshheader;
    }
}HEADER;

struct MESHHEADER{
    float unk1[18];
    int unk2;
    int numVerts;
    int numFaces;
    int unk3;
    int unk4;
    int unk5;
    int ofsVerts;
    int sizeVerts;
    int ofsFaces;
    int sizeFaces;
    int ofsUnk1;
    int sizeUnk1;
    int ofsUnk2;
    int sizeUnk2;
    int ofsUnk3;
    int sizeUnk3;

    struct{
        FSeek(ofsVerts+16);
        struct FLOAT3 vert[numVerts]<optimize=false>;
    }Vertices;

    struct{
        FSeek(ofsFaces+16);
        struct FACE3 face[numFaces]<optimize=false>;
    }Faces;

    struct{
        FSeek(ofsUnk2+16);
        int test2;
    }Unk2;

    struct{
        FSeek(ofsUnk1+16);
        int test1;
    }Unk1;
};

struct FLOAT3{
    float x;
    float y;
    float z;
    Printf("v %f %f %f\n",x,y,z);
};

struct FACE3{
    int f1;
    int f2;
    int f3;
    int unk1;
    int unk2;
    int unk3;
    int unk4;
    Printf("f %d %d %d\n",f1+1,f2+1,f3+1);
};
```
## Post #18
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-09T23:04:02+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

I'm very sorry about that, but I'm a big noob in script and stuff...

I've copied/paste your script into a .bms file, run it in MultiEx commander then choose a .phm file to extract.

And this message appear :

"Multiex 3 could not process, error :18"

Am I doing it in a wrong way ?
## Post #19
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-09-10T02:45:43+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Tabris
>
> I'm very sorry about that, but I'm a big noob in script and stuff...
I've copied/paste your script into a .bms file, run it in MultiEx commander then choose a .phm file to extract.

It's not a bms script, it's a 010 Editor Binary Template, you need 010 Editor for it,
it's a quick written c script, anyone can use the infos to make an exporter tool.
## Post #20
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-10T09:18:37+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Falo
>
> Tabris wrote:I'm very sorry about that, but I'm a big noob in script and stuff...
I've copied/paste your script into a .bms file, run it in MultiEx commander then choose a .phm file to extract.

It's not a bms script, it's a 010 Editor Binary Template, you need 010 Editor for it,
it's a quick written c script, anyone can use the infos to make an exporter tool.
for meshes it works, for scenes dont, but they look like same type with just different header
btw i didnt knew that 010 editor got such interesting features
## Post #21
- Username: anhhungmeo1234
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Aug 15, 2010 4:48 pm
- Post datetime: 2011-09-10T09:24:31+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

where are character's model ?
## Post #22
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-10T09:55:04+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from anhhungmeo1234
>
> where are character's model ?
ClientData.mpq Appearance maybe, im not sure with that
## Post #23
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-10T14:29:06+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

i found maybe vertices in scenes but im not sure so dont kill me if im wrong 
Scenes/trOut_Sub80x80_Fields_CaveEntranceC.scn vertices start at 266c h. But i cant find any face definition. can anybody correct me if im wrong?

here is extracted file, but as i said i cant find faces  i dont know where open it without them
[export.zip](https://xentaxbackup.github.io/file/4703_export.zip)
## Post #24
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-11T12:08:56+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Falo
>
> - extract "CoreData.mpq\PhysMesh\*.phm"

Aren't those only the collision meshes for the physics simulation? From what I've seen the interesting stuff is in the .app files.
## Post #25
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-09-11T14:13:49+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from BoyC
>
> Falo wrote:- extract "CoreData.mpq\PhysMesh\*.phm"

Aren't those only the collision meshes for the physics simulation? From what I've seen the interesting stuff is in the .app files.
all mesh, try trDun_StartScreen.phm this one looks great
## Post #26
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-09-11T16:34:55+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

working on it:
[](http://www.imagebanana.com/view/3475dzf8/Monk_Male.jpg)
## Post #27
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-11T16:39:24+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Falo
>
> working on it:
Oh I see you export into a format you can read with DE. Nice.
I checked out the 010 editor and man I've been looking for something like that binary template stuff for AGES.
I started working on the .app files as well, could you drop your current script in here for comparison?
## Post #28
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-09-11T17:00:11+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

[](http://www.imagebanana.com/view/7vp8tp1w/Monk_Male2.jpg)

it's not a finished script:

//edit:
Update to v1.11, uv working, some bugfix

```
//--- 010 Editor v3.2.1 Binary Template
//
// File: Diablo III *.app
// Author: Falo
// Revision: 1.11
//--------------------------------------
local int tempface=0, tempgroup=0;

struct{
    ubyte DEADBEEF[16];
    uint unk1[5];
    int numBones;
    int ofsBones;
    int sizeBones;
    int unk2[30];
    int numMats;
    int ofsMaterial;
    int sizeMaterial;

    if(ofsBones)
    {
        struct{
            FSeek(ofsBones + 16);
            struct BONE bone[numBones]<optimize=false>;
        }Bones;
    }

    Printf("mtllib default.mtl\n");
    if(ofsMaterial)
    {
        struct{
            FSeek(ofsMaterial + 16);
            struct MATERIAL material[numMats]<optimize=false>;
        }Mats;
    }
}HEADER;

struct BONE{
    char Name[64];
    int parent_id;
    float unk1[34];
    int unk2[7];
    int unk3;
    //Printf("%d;%s\n",parent_id,Name);
};

struct MATERIAL{
    local int ftemp;
    int unk1;
    int numVerts;
    int ofsVerts;
    int sizeVerts;
    int unk2;
    int ofsNormals;
    int sizeNormals;
    int unk3;
    int numFaces;
    int ofsFaces;
    int sizeFaces;

    int unk5[7];

    char name1[128];
    char name2[128];
    float funk1[11];

    ftemp = FTell(); // save position for later
    
    if(ofsVerts)
    {
        struct{
            FSeek(ofsVerts + 16);
            struct VERTEX vert[numVerts]<optimize=false>;
        }Verts;
    }

    if(ofsNormals)
    {
        struct{
            FSeek(ofsNormals + 16);
            struct NORMAL normal[numVerts]<optimize=false>;
        }Normals;
    }

    Printf("g Mesh%03d_%s\n",tempgroup,name1);
    Printf("usemtl %s\n",name1);
    if(ofsFaces)
    {
        struct{
            FSeek(ofsFaces + 16);
            struct FACE face[numFaces/3]<optimize=false>;
        }Faces;
    }

    tempface += numVerts;
    tempgroup++;
    FSeek(ftemp); // restore position, next mesh
};

struct VERTEX{
    local float tu,tv;
    float x;
    float y;
    float z;
    int unk1;
    int unk2;
    int unk3;
    ushort texu;
    ushort texv;
    int unk3[4];

    tu = texu;
    tv = texv;
    tu -= 32767;
    tv -= 32767;
    tu /= 512;
    tv /= 512;
    tv *= -1;
    tv += 1;
    Printf("v %f %f %f\n",x,y,z);
    Printf("vt %f %f\n",tu,tv);
};

struct NORMAL{
    int unk1;
    float unk2;
    int unk3;
    float unk4;
    int unk5;
    float unk6;
    //Printf("vn %f %f %f\n",unk2,unk4,unk6);
};

struct FACE{
    ushort f1;
    ushort f2;
    ushort f3;
    Printf("f %d/%d/%d %d/%d/%d %d/%d/%d\n",
        tempface+f1+1,tempface+f1+1,tempface+f1+1,
        tempface+f2+1,tempface+f2+1,tempface+f2+1,
        tempface+f3+1,tempface+f3+1,tempface+f3+1);
};
```
## Post #29
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-11T18:24:43+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Very nice, that helps a lot in figuring out how to use the script.
What I found is that the constant header seems to be 1576 bytes long with the first of the referenced data beginning right after that at 0x628h. There is a second reference to a material data array at 0x5C4h (3 integers like the others), that points to the first array after the header. I'll post my script once it's at a comparable level to yours.
## Post #30
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-09-11T19:15:35+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

after some more work, got uv working, i dumped the textures with 3D Ripper DX,
[](http://www.imagebanana.com/view/5hmsq5i8/Monk_Male_tex.jpg)
## Post #31
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-11T20:37:50+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

I think what you labelled as normals might actually be blendweights for the bones per vertex and the normals binormals and tangents are stored 1 byte per axis in the vertex declaration.

EDIT:
Actually seems to be 3 sets of blendweights per vertex, 8 bytes each. First byte is the bone ID, still working on the rest.
## Post #32
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-11T21:12:17+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

EDIT: Moved to the [appropriate thread](http://forum.xentax.com/viewtopic.php?f=16&t=7337)
## Post #33
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-13T08:19:55+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Hello, I and newbie to this. Please show me how to use these script. I have 010 editor but don't know how to use. Please help me. Thank you very much!
## Post #34
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-13T13:54:02+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

EDIT: Moved to the [appropriate thread](http://forum.xentax.com/viewtopic.php?f=16&t=7337)
## Post #35
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-13T15:32:06+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Thank you BoyC but I still get some trouble:
1. When I open file .phm and use your script as template, I press F5 to Run and it said *ERROR Line 28: Template passed end of file at variable 'unk2'. 

2. I have no idea about "copy/paste the output into a .obj file (skip the first line)"
    I tried to copy it to notepad and save as .obj but it made nothing.

I already have Deep Exploration and 3DS max waiting for import model and texture to it 
Looking forward to your reply, BoyC !
## Post #36
- Username: afrokid
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 11, 2011 5:20 pm
- Post datetime: 2011-09-13T15:33:21+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Comment Removed.
## Post #37
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-13T17:40:38+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

This script is for parsing the appearance (.app) files
## Post #38
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-13T17:47:08+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Hey guys, I'm new here but not new to 101 editor (I actually have a brought version!)

I've made progress on all the diablo files (which I'm willing to share ofc!) but I'm not very good with graphics. I don't want the 3d models (way above my station) but the icons would be cool!

Can anyone help?

p.s I can help with some of the header file. @ 16[10h] you have the int BlizzardInternalFileNumber I believe  and the 4h value is the file version (100% sure, at least it is for the other datafiles, not 100% about the .tex)

So if anyone could help me that would be awesome!

Here's a tempalte to get strings I made. It's really rough and prob over-complex but just to give something before requesting ^,^

```
//--- 010 Editor v3.0.1 Binary Template
//
// Author: MrRawr
// Revision: 1.0
// Purpose: Extract Most strings from Diablo3 text files
//--------------------------------------
local string title = "Items";
//local int fileHeader = FileNew();
local int fileItems = FileNew();
char type[4];
int version;
char empty[8];
int BlizzardFileNumber;
char empty2[8];
int dunno1;
int dunno2;
int dunno3;
int dunno4;
FPrintf( fileItems, "version,%i\n", version);
typedef struct {
    int stringPosition;
    int stringLength;
    int terminator;
    int blank;
} StringData;
local int searchHeader = 1;
struct Item{
    //FPrintf( fileHeader, "item");
    local int notTerminated;
    local int notEmpty;
    do {
        StringData stringData;
        //FPrintf( fileHeader, ",%i,%i", stringData.stringPosition, stringData.stringLength);
        notTerminated = stringData.terminator;
        notEmpty = stringData.stringLength;
    } while ( notTerminated == 0 && notEmpty > 0 );
    if ( notTerminated == -1 ) {
        StringData stringFiller;
        if ( stringFiller.terminator > 0 ) {
            searchHeader = 0;
            FSkip(-8);
        } 
    }
    else {
        int blank;
        if ( notTerminated > 1 ) {
            searchHeader = 0;
            FSkip(-12);
        }
        else if ( blank > 0 ) {
            FSkip(-4);
        }
    }
    //FPrintf( fileHeader, "\n");
};

do {
    Item item;
} while ( searchHeader == 1 );

//2290

local int i;
local int y;
local int length;
local int infoSize;
local int temp;
struct ItemInfo {
    infoSize = 0;
    while ( exists(item[i].stringData[y]) ) {
        length = item[i].stringData[y].stringLength;
        if ( length > 0 ) {
            if ( y == 0 ) {
                char itemCode[length];
                infoSize += sizeof(itemCode);
                if ( (length%8) > 0 ) {
                    char itemCodeFiller[8-(length%8)];
                    infoSize += sizeof(itemCodeFiller);
                }
                FPrintf( fileItems, ",%s", itemCode);
            }
            else if ( y == 1 ) {
                char itemType[length];
                infoSize += sizeof(itemType);
                if ( (length%8) > 0 ) {
                    char itemTypeFiller[8-(length%8)];
                    infoSize += sizeof(itemTypeFiller);
                }
                FPrintf( fileItems, ",%s", itemType);
            }
            else if ( y == 2 ) {
                char itemName[length];
                infoSize += sizeof(itemName);
                if ( (length%8) > 0 ) {
                    char itemNameFiller[8-(length%8)];
                    infoSize += sizeof(itemNameFiller);
                }
                FPrintf( fileItems, ",%s",  itemName);
            }
        }
        y++;
    }
};
i = 0;
while( exists(item[i]) ) {
    y = 0;
    FPrintf( fileItems, "itemInfo");
    ItemInfo itemInfo;
    if ( infoSize > 0 ) {
        FSkip(8-(infoSize%8));
    }
    FPrintf( fileItems, "\n");
    i++;
}
```
## Post #39
- Username: afrokid
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 11, 2011 5:20 pm
- Post datetime: 2011-09-13T17:48:50+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Edit: Nvm found them
## Post #40
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-13T17:56:07+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from npd2006
>
> Thank you BoyC but I still get some trouble:
1. When I open file .phm and use your script as template, I press F5 to Run and it said *ERROR Line 28: Template passed end of file at variable 'unk2'. 

2. I have no idea about "copy/paste the output into a .obj file (skip the first line)"
    I tried to copy it to notepad and save as .obj but it made nothing.

I already have Deep Exploration and 3DS max waiting for import model and texture to it 
Looking forward to your reply, BoyC !
BoyC please help me !!!
## Post #41
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-13T17:57:51+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

you're running it on the wrong file  some .tex are for icons. The template given to you is for the 3d model textures
## Post #42
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-13T18:05:14+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from MrRawr
>
> you're running it on the wrong file  some .tex are for icons. The template given to you is for the 3d model textures
So, what kind of filetype should I use?
and how about the "copy/paste the output into a .obj file (skip the first line) ?" I don't get it.
## Post #43
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-13T18:07:19+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from npd2006
>
> MrRawr wrote:you're running it on the wrong file  some .tex are for icons. The template given to you is for the 3d model textures
So, what kind of filetype should I use?
and how about the "copy/paste the output into a .obj file (skip the first line) ?" I don't get it.
They're also .tex, but you need to have the right ones. Ones named 2DCrossbows or something will be icons 

I believe he's talking about c for the other bit. But I'm just a noob when it comes to this sorta stuff.
## Post #44
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-13T18:37:02+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> They're also .tex, but you need to have the right ones. Ones named 2DCrossbows or something will be icons
I had already done extract the obj files. But I still have problem with the texture. I test file .tex with your template but most of it have this error *WARNING Line 104: Empty structure. and no output.
But thank you anyway
## Post #45
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-13T18:43:45+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

I think this thread has become a bit too confusing with .tex .phm and .app files all being discussed in it. From now on I'll be posting the .app model file research to the [appropriate thread](http://forum.xentax.com/viewtopic.php?f=16&t=7337).
## Post #46
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-13T19:18:49+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Hmm OK. Well can anyone help with the 2D tex files which store the tga stuff?
## Post #47
- Username: plash
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 14, 2011 7:56 pm
- Post datetime: 2011-09-13T22:06:10+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

..Back on topic, others and myself have been working on .tex. See [here](http://173.0.52.202/formats/tex/).

The pixel formats are run through a table to get the corresponding D3DFORMAT. For example, PF 4 is D3DFMT_A1R5G5B5.

Working on the pixel formats at the moment. I'll have DXT# working hopefully by the end of the day.

EDIT: Also: as with PF9 (DXT1), the components for the data are often separated.

EDIT: Someone has handled everything except for cubemaps; expect a tool soon. The spec will be updated once I am able to see the code.
## Post #48
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-14T17:14:43+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Any idea about the textures, MrRawr ?
## Post #49
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-14T18:07:38+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

getting there, give me 30 mins...
## Post #50
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-14T18:53:24+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Got all the data extracted but need to make them into images now. Grr.. taking longer than I want!

edit: got guests around so I have to bail. for a few hours Anyone good at converting the binaries into actual images?
## Post #51
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-14T20:18:09+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from MrRawr
>
> Got all the data extracted but need to make them into images now. Grr.. taking longer than I want!

edit: got guests around so I have to bail. for a few hours Anyone good at converting the binaries into actual images?

Sure just slap a tga header before the data. 18 bytes:

```
{
    byte  identsize;          // size of ID field that follows 18 byte header (0 usually)
    byte  colourmaptype;      // type of colour map 0=none, 1=has palette
    byte  imagetype;          // type of image 0=none,1=indexed,2=rgb,3=grey,+8=rle packed

    short colourmapstart;     // first colour map entry in palette
    short colourmaplength;    // number of colours in palette
    byte  colourmapbits;      // number of bits per palette entry 15,16,24,32

    short xstart;             // image x origin
    short ystart;             // image y origin
    short width;              // image width in pixels
    short height;             // image height in pixels
    byte  bits;               // image bits per pixel 8,16,24,32
    byte  descriptor;         // image descriptor bits (vh flip bits)
    
    // pixel data follows header
    
} TGA_HEADER
```
## Post #52
- Username: Necrolis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2011 4:06 am
- Post datetime: 2011-09-14T20:26:39+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

enjoy (and give some feedback too!): [http://diablo3dev.com/w/D3TexConv](http://diablo3dev.com/w/D3TexConv)
## Post #53
- Username: Fiel
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Dec 17, 2007 1:29 am
- Post datetime: 2011-09-14T21:32:10+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Excellent tool!

You said you needed to know which files have mipmaps and which do not based upon the value at offset 44. Here are all of the files in which offset 44 does not have a 1:

```
0x6 - arcaneTorrent_irrad.tex
0x6 - bronze_irradiance.tex
0x6 - CharacterSelect_IrradianceMap.tex
0x6 - dead_irradiance.tex
0x6 - Demon_Irradiance.tex
0x6 - ElmentalArrow_SkullIrradiance.tex
0x6 - Ghost_irrad.tex
0x6 - gold_irradiance.tex
0x6 - healthOrb_irradiance.tex
0x6 - HellIrradiance.tex
0x6 - Holy_irrad.tex
0x6 - iceShard_irradiance.tex
0x6 - irradiance.tex
0x6 - irradiance_dialogue.tex
0x6 - manaOrb_irradiance.tex
0x6 - neutral_unlit_irradiance.tex
0x6 - Selection_Hostile_Irradiance.tex
0x6 - Selection_Irradiance.tex
0x6 - silver_irradiance.tex
0x6 - trOutIrrad.tex

```


Output to PNG would be excellent.

EDIT:

The program crashes on these files:

2DInventoryCharms.tex
2DInventoryHammers.tex
2DInventoryMightyWeapon_2H.tex
2DInventoryPvPItem.tex
2DMapTower.tex
2DUIDebug.tex
2DUIEndScreen.tex

There are more, but that's all I'll list now.
## Post #54
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-15T03:21:09+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> enjoy (and give some feedback too!): http://diablo3dev.com/w/D3TexConv
I tested it, some textures extracted successfully, but these texture, I guess it doesn't have an display icon
_01sun.tex
_2DBusy_Hourglass.tex
_2DMapCryptDungeon.tex
_2DUI_Bnet_CampaignSearching.tex
_a1dun_Cath_chest.tex
_a2dun_Zolt_Dust_Spike.tex

And the rest files, maybe the main texture which are diffuse, specular, normal maps are failed
_a1dun_caves_Boulders_A_diff.tex
_a1dun_Leoric_Dirt_01.tex
_a2Dun_Cave_Flooded_E_01_worldMask.tex
_Barb_F_Hair_diff.tex
_DH_F_CLS_HVY_norm_base_A_diff.tex
_DH_F_CLS_HVY_norm_base_A_spec.tex
_Fetish_skeleton_A_diff.tex
_Helm_DHF_nightmare_base_02a_spec.tex
## Post #55
- Username: Necrolis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2011 4:06 am
- Post datetime: 2011-09-15T05:34:36+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Thanks for the feedback guys , I'll get onto fixing it now

> Reply from Fiel
>
> 
Output to PNG would be excellent.I'll get round to more output formats when the core is done

EDIT:
Crash on DXT1 files is solved (was me using the wrong size var -.-).

> Reply from npd2006
>
> 
I tested it, some textures extracted successfully, but these texture, I guess it doesn't have an display iconthey extract & view fine here, maybe your viewer is not up to scratch? (I'm using the MS DirectX Texture Viewer)

EDIT2:
Got mip mapped decoding in, gonna upload a new version now 
made my original mip decoding code faster, but it seems D3 stores
zero sized miplevel, so the mip count is not to be fully trusted!

EDIT3: version 0.7 is live: [http://diablo3dev.com/w/D3TexConv](http://diablo3dev.com/w/D3TexConv)
## Post #56
- Username: Fiel
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Dec 17, 2007 1:29 am
- Post datetime: 2011-09-15T07:13:00+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Necrolis
>
> EDIT:
Crash on DXT1 files is solved (was me using the wrong size var -.-).

Thanks for the heads up. I made the change in the source code and it's working beautifully.

> Reply from Necrolis
>
> they extract & view fine here, maybe your viewer is not up to scratch? (I'm using the MS DirectX Texture Viewer)

The DDS viewing works fine for me on those files. I think he needs a better DDS viewer.

Also, even after that source code change, there are still some files causing the program to crash:

arrow_poison.tex
BossWindow_middle.tex
Portal_Lightrays.tex
shoulderPads_barbF_nightmare_base_02a_TintMask.tex
shoulderPads_monkF_nightmare_base_01A_TintMask.tex
twoHandedSword_norm_unique_08_spec.tex
## Post #57
- Username: Necrolis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2011 4:06 am
- Post datetime: 2011-09-15T07:53:32+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Fiel
>
> 
Also, even after that source code change, there are still some files causing the program to crash:

arrow_poison.tex
BossWindow_middle.tex
Portal_Lightrays.tex
shoulderPads_barbF_nightmare_base_02a_TintMask.tex
shoulderPads_monkF_nightmare_base_01A_TintMask.tex
twoHandedSword_norm_unique_08_spec.texversion 0.7 no longer crashes on those files, however, some (like BossWindow_middle.tex) aren't DXTn files, so I need to add DDS header writinf for those quick

EDIT: v0.8 is out, will decode A8R8G8B8 files, just note D3 has some non-square, non-power-of-2 textures in this format (BossWindow_middle.tex), which will explode on some viewers (like MS's one)
## Post #58
- Username: Fiel
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Dec 17, 2007 1:29 am
- Post datetime: 2011-09-15T09:08:13+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Necrolis
>
> Fiel wrote:
Also, even after that source code change, there are still some files causing the program to crash:

arrow_poison.tex
BossWindow_middle.tex
Portal_Lightrays.tex
shoulderPads_barbF_nightmare_base_02a_TintMask.tex
shoulderPads_monkF_nightmare_base_01A_TintMask.tex
twoHandedSword_norm_unique_08_spec.texversion 0.7 no longer crashes on those files, however, some (like BossWindow_middle.tex) aren't DXTn files, so I need to add DDS header writinf for those quick

EDIT: v0.8 is out, will decode A8R8G8B8 files, just note D3 has some non-square, non-power-of-2 textures in this format (BossWindow_middle.tex), which will explode on some viewers (like MS's one)

I upgraded to 0.8 and I'm still crashing on all of the same files. I really do like the improved atlases.
## Post #59
- Username: Necrolis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2011 4:06 am
- Post datetime: 2011-09-15T09:20:54+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Fiel
>
> I upgraded to 0.8 and I'm still crashing on all of the same files. I really do like the improved atlases.odd(I know the first two files work fine now...), I'll do a more indepth look when I get back from uni later. one thing though, is the crash an assertion or just the program freezing with an access violation?
## Post #60
- Username: Fiel
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Dec 17, 2007 1:29 am
- Post datetime: 2011-09-15T09:24:41+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Necrolis
>
> odd(I know the first two files work fine now...), I'll do a more indepth look when I get back from uni later. one thing though, is the crash an assertion or just the program freezing with an access violation?

It throws two exceptions every time. First exception is a Buffer Overflow Exception, and then it's Appcrash. I'll run it through MSVC++ to see what's up.

EDIT: Ran it through the MSVC++ debugger and it exited without any exceptions. wtf...

EDIT #2: My error. The program is fine. It was a problem with the script I use that feeds d3texconv with all the files. I tried to feed it a file that didn't exist.

EDIT #3: Good news everyone! I just fed this program every single tex file and they all passed without any crashes.
## Post #61
- Username: Necrolis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2011 4:06 am
- Post datetime: 2011-09-15T09:39:43+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from Fiel
>
> EDIT #3: Good news everyone! I just fed this program every single tex file and they all passed without any crashes.rofl, well, I'll still add in a check for file existence then
## Post #62
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-15T10:14:01+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

fantastic work  I need to learn about file headers and I could've helped
## Post #63
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-15T11:43:47+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

OK, the next step is to process the image with the map and separate it!
## Post #64
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-15T12:12:20+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Do we know how they are referencing the texture files from elsewhere? It'd be quite helpful for the mesh research.
## Post #65
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-15T12:24:36+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

depends. I think it's all loaded into memory for performance (once needed the map is loaded into memory and referenced from there)

guesswork
## Post #66
- Username: Necrolis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2011 4:06 am
- Post datetime: 2011-09-15T13:40:47+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from MrRawr
>
> guessworkdebugger 
> Reply from MrRawr
>
> OK, the next step is to process the image with the map and separate it!if you mean split it into the individual sections that make up the atlas, then that would need an external DXTn lib (like nVidia's) or use of DX/OGL, imo its easier to use nVidia's Texture Tools and just slice up the DDS in Photoshop

> Reply from BoyC
>
> Do we know how they are referencing the texture files from elsewhere? It'd be quite helpful for the mesh research.they use shortened internal names(those from the atlas most of the time) in a bevy of files to reference stuff (I haven't looked too deeply into that part), at runtime the references are held via the SNO chain and the D3D texture handle is stored in the header of the tex file in memory.
## Post #67
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-15T15:11:48+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

that, or find the internal references...
## Post #68
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-15T15:34:37+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

There seems to be no reference in the .gam to any image and it would be very hap-hazzard of blizzard to do a conversion of the name (which I assume ofc they did not.)

So unless there is a file i'm missing I'm stuck :\
## Post #69
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-09-16T06:10:29+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Hello everyone,
anyone made a progress towards .gam files yet ?
## Post #70
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-09-17T02:33:24+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

.tex files are referenced via the first UInt32 after the 16 byte header. You can see this reference from the .app files in a section that is referenced from the materials
## Post #71
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-19T10:27:14+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

That Number is the File number, the reference is from the .app which is referenced from the materials!? ahhh god damn it. So the files I was missing was the app!!!!

God damn it to hell. Thanks Nicoli.
## Post #72
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-19T10:52:21+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

There seems to be even more to it than that - from what I've managed to piece together in my limited free time was that actor files are the big boss - they describe the look and animations of a set piece, possibly even more. For example the dye actor files are virtually the same, they reference the same appearance file, and it seems like their color (or possibly their texture) is described in the actor file.
However some app files aren't referenced by actor files, map pieces for example.
Actor files also reference animation sets which in turn reference animations. Not sure where the materials fit in to all this yet, but I didn't find any references between appearance and materials yet.
## Post #73
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-19T12:49:15+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from BoyC
>
> There seems to be even more to it than that - from what I've managed to piece together in my limited free time was that actor files are the big boss - they describe the look and animations of a set piece, possibly even more. For example the dye actor files are virtually the same, they reference the same appearance file, and it seems like their color (or possibly their texture) is described in the actor file.
However some app files aren't referenced by actor files, map pieces for example.
Actor files also reference animation sets which in turn reference animations. Not sure where the materials fit in to all this yet, but I didn't find any references between appearance and materials yet.

I'm in the same boat. The reference between the .gam and the .app isn't there. they're close but not exact (for example file numbers 82625 = 82626 ) which to me isn't right (the others flux too).

Actor files are the big boss eh? I'll look at them now too

edit: actor files are empty  yo
## Post #74
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-19T13:10:39+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Wow, OK well I've found out that my MPQ extractor failed on me... so I only had half the data! Go me! Brick wall and my head...

Anyway, I might actually make progress today... I feel like crying lol
## Post #75
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-19T15:05:17+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

so that file references is 100% the acr reference but how we get from the acr to the tex is another matter...

anyone made progress on the acr files?
## Post #76
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-19T17:40:46+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Made a lot of progress but need to take a break. Got quite a bit of notes prob have something tomorrow.
## Post #77
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-20T13:46:30+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Hey guys, well I found the link between .gam > .acr > .app > .tex

So I can pull out the 3d models and skin them etc, what I can't do is the (prob) easiest task of all... linking the 2d Inventory Icons to the items!

Not like it matters much but it feels weird that this is the only thing I can't figure out >.<

Anyone got that piece?
## Post #78
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-20T15:53:02+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

done it. cleaning up now. It's a lot quieter here than expected
## Post #79
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-20T16:30:25+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Thank you MrRawr for your work. I am appreciate that! I used it to extract many textures and all successfully.
## Post #80
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-20T17:13:00+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

As much as I'd love to take credit for such a feat I think that was Boyc stuff 

But so long as we all help each other the world goes round
## Post #81
- Username: afrokid
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 11, 2011 5:20 pm
- Post datetime: 2011-09-21T17:53:33+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

great work so far guys, ive been watching your progress since you started and im impressed 

i was wondering if anyone has any idea how to convert the .fnt files over to something like .ttf maybe?
## Post #82
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-09-21T22:53:17+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Anyone can point me wheres the reference between *.app and *.tex files please?
The # (first uint after 16 byte header) isnt referenced anywhere in .app, also if anyone have any though about how item names (from _atlas) connected to .app? Wheres the pointer to name?  Thanks.
## Post #83
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-22T21:47:41+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from afrokid
>
> great work so far guys, ive been watching your progress since you started and im impressed 

i was wondering if anyone has any idea how to convert the .fnt files over to something like .ttf maybe?
I'm not in that area of the files atm sorry mate
## Post #84
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-09-23T09:01:57+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from afrokid
>
> great work so far guys, ive been watching your progress since you started and im impressed 

i was wondering if anyone has any idea how to convert the .fnt files over to something like .ttf maybe?
Well, you can just search google for that fonts, all of them available for download around 
Sometimes its called DIABLO_L or Diablo Light.
Also check out a Booter font.
Tried just renaming extension ?:P
## Post #85
- Username: afrokid
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 11, 2011 5:20 pm
- Post datetime: 2011-09-23T09:31:14+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from InsaneXo
>
> afrokid wrote:great work so far guys, ive been watching your progress since you started and im impressed 

i was wondering if anyone has any idea how to convert the .fnt files over to something like .ttf maybe?
Well, you can just search google for that fonts, all of them available for download around 
Sometimes its called DIABLO_L or Diablo Light.
Also check out a Booter font.
Tried just renaming extension ?:P

yeah ive tried turing it to a .otf or .ttf but niether work.

i opened it up with 010 and found the url [http://www.emigre.com/](http://www.emigre.com/) in it and found [http://www.emigre.com/EF.php?fid=95](http://www.emigre.com/EF.php?fid=95) on that site so im using that one now 
thanks
## Post #86
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-09-27T09:22:06+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Since Falo released his AWSOME script for 010 Editor, I managed to figure it out and pass it into C# .NET 3.5 and made a tool of it.

You can download the tool from my site [http://tinyurl.com/griffonstudios](http://tinyurl.com/griffonstudios).

How it works. 2 Ways
1. Convert 1 app file to OBJ
 - in the commande line
 - c:\>D3AppConvert2Obj.exe -f [app filename]
 - this converts the app file to an obj file.

2. Convert all app files in a directory to OBJ
 - in the command line
 - c:\>D3AppConvert2Obj.exe -d [valid directory were you extracted all the app files]
 - this will convert all the .app files to OBJ

I extracted all the app file to a folder and converted them all at once, this took about 20 minutes
I haven't found a OBJ that didn't work yet
I added some comments to the obj files, such as BONE information

Thanks to Falo   

and have fun with it

Cheers
T.
## Post #87
- Username: Dsummit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 24, 2011 11:07 pm
- Post datetime: 2011-09-28T22:02:44+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from TaylorMouse
>
> Since Falo released his AWSOME script for 010 Editor, I managed to figure it out and pass it into C# .NET 3.5 and made a tool of it.

You can download the tool from my site http://tinyurl.com/griffonstudios.

How it works. 2 Ways
1. Convert 1 app file to OBJ
 - in the commande line
 - c:\>D3AppConvert2Obj.exe -f [app filename]
 - this converts the app file to an obj file.

2. Convert all app files in a directory to OBJ
 - in the command line
 - c:\>D3AppConvert2Obj.exe -d [valid directory were you extracted all the app files]
 - this will convert all the .app files to OBJ

I extracted all the app file to a folder and converted them all at once, this took about 20 minutes
I haven't found a OBJ that didn't work yet
I added some comments to the obj files, such as BONE information

Thanks to Falo   

and have fun with it

Cheers
T.

Whoa awesome, thanks to Falo and thanks to you for the nice tool!

I have a question though, are the materials supposed to be included in it? There seems to be references to external files, or am I supposed to extract something else from the mpqs?

Opened in Deep Exploration (takes like 15 min to open...) and I get nothing (though I'm a total noob with DE so I don't know). Worked in Blender but no materials. 3DS Max gives me errors. I'll probably try Unity later.
## Post #88
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-09-29T08:57:59+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Thnx!

The references of Materials, are indeed references to other files, but not the .TEX files, there are files in the MPQ ClientData.mpq, folder Material, and have the extension .mat, but I can't seem to figure out how it works... maybe something for Falo 

Anyway, there are some models like Adria.app, her texture can be found easely, but you need to do this manually, for now.

T.
## Post #89
- Username: Dsummit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 24, 2011 11:07 pm
- Post datetime: 2011-09-29T16:24:49+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from TaylorMouse
>
> Thnx!

The references of Materials, are indeed references to other files, but not the .TEX files, there are files in the MPQ ClientData.mpq, folder Material, and have the extension .mat, but I can't seem to figure out how it works... maybe something for Falo 

Anyway, there are some models like Adria.app, her texture can be found easely, but you need to do this manually, for now.

T.

Cheers thanks!

BoyC said he got them with 3D Ripper DX earlier in this topic, so I guess that's another option if we have beta access or we can use the sandbox.
## Post #90
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-09-30T05:51:22+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

You do not need to use the RipperDX you can convert the .tex files using the texconvertor that was posted in one of the earlier posts

[http://diablo3dev.com/w/D3TexConv](http://diablo3dev.com/w/D3TexConv) 

I also wrote a bat file with the tex files to convert all of them in one batch, I still had to keep the enter pressed but in 20 min, all was converted

T.
## Post #91
- Username: Dsummit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 24, 2011 11:07 pm
- Post datetime: 2011-09-30T06:35:59+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Yes but didn't you say the materials were .mat files? Anyway I'll try looking deeper in the files when I have more time.
## Post #92
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-01T18:30:20+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Yes, but I mean that the Mat file, that is referenced in the App file,  probably indicates which texture to use on the model. That texture is just an image stored as .tex file, an that .tex file can be converted to dds file by this tool

Hope I make any sence?

T.
## Post #93
- Username: afrokid
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 11, 2011 5:20 pm
- Post datetime: 2011-10-03T05:28:19+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

i've been playing around with the program and i cannot figure out how to get it to work   

i put the -d [directory] in but it keeps saying that the place its in cannot be found?
## Post #94
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-06T19:29:34+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Greetings,

I've downloaded the D3Appconverter of TaylorMouse, and downloaded the client of the Beta.

How can I get models with textures (which I can load to a 3d Framework like Away3D or Alternativa3D)?

Thanks for your help!

BR,
Monguron
## Post #95
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-07T11:31:14+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

1. Download the MPQ extractor
2. Extract all app files from the archive into a folder, exaple in the c:\temp\extracted\, just make sure the files are all put into this folder
3. Download my app and put it in the c:\temp\extracted\ folder
4. Open a cmd window and browse to the c:\temp\extracted\ folder
5. Run the following command : ( this can take up to 40 minutes )

```
D3Appconverter.exe -d "c:\temp\extracted\"
```


6. Download the D3TexConv.exe 
7. Extract the tex files with the MPQ extractor
8. COnvert the tex files with the D3TexConv.exe to dds
9. Open up Max
10.Import the obj file that you want, open the material editor and find the matching texture

T.
## Post #96
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-07T15:23:10+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Hey!

Thanks for the details.
## Post #97
- Username: afrokid
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 11, 2011 5:20 pm
- Post datetime: 2011-10-08T07:32:24+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

i tried that but it comes up saying 

```
'D3AppConvert2Obj.exe' is not recognized as an internal or external command,
operable program or batch file.
```


Edit: after i posted this i realised it should of been 
```
C:\Users\Afrokid\Desktop\Appearance\D3AppConvert2Obj.exe -d "C:\Users\Afrokid\Desktop\Appearance"
```


working beautifully, thanks
## Post #98
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-08T10:30:06+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Hi,

It's not working for me.

I've performed these steps:

> 1) I've made a folde C:\temp\extracted
>
> 2) I copied Adria.app and D3AppConvert2Obj.exe into this folder
>
> 3) I've run C:\temp\extracted\D3AppConvert2Obj.exe -d "C:\temp\extracted\"

No failure message, but nothing happens.
What did I do wrong?
## Post #99
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-08T10:33:56+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Hmm now it's working, that I've put an Appearance folder into the extracted folder, and copied all the files there
## Post #100
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-08T20:41:03+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from TaylorMouse
>
> T.
Doesn't works for straight .obj > .max conversion 
Atleast for 12' Design.
Requires some heavy conversion trixx
## Post #101
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-09T11:22:58+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

What do you mean, "..requires some serious conversion trix..." ?

T.
## Post #102
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-10T07:36:44+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from TaylorMouse
>
> What do you mean, "..requires some serious conversion trix..." ?

T.
If you import an .obj from your app straight into Studio or even DE, verticles are calculated incorrectly, well atleast for me.
For me it worked with Blender > Studio combo, so i had to import model into Blender first and than export it to Autodesk FBX so all verticles are calculated correctly and all UVMapping are correct (.obj > blender > .obj > studio does work)
The only working combo i found for myself is .obj > Blender > .fbx > Studio > .obj > My Render Engine
## Post #103
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-10T20:34:19+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Insane,

[join us on this thread: http://forum.xe ... 7&start=45](join%20us%20on%20this%20thread:%20http%3A//forum.xentax.com/viewtopic.php?f=16&t=7337&start=45)

Just discussing model topics ... as I also had (I'm still having) problems with opening the 3D models.
## Post #104
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-05-19T12:38:53+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

I didn't know if I should start a new thread, or resurrect this old one, but anyways; The retail version of Diablo 3 .tex files cannot seem to be opened by D3TexConv_v0.9:

I get "Invalid Texture or Surface (SNO Header Mismatch)"

Is anyone working on a new Diablo 3 .tex texture converter?  PM me as required, thanks.
## Post #105
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2012-05-19T15:02:27+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Actually, it still works.

Just open the .tex file using a Hex Editor, you should see (ï¾.Þ-) just change it to (ï¾.Þ+).
Their values in Hex are (EF BE AD DE 2D) to (EF BE AD DE 2B).
## Post #106
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-05-20T04:26:07+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Thanks windfury, that works!
## Post #107
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-05-20T10:35:24+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Oke, nice solution, but I don't want to change each tex file manually,
is there a way to do this, all at once?

More on the question, is there ANY one that gets to compile the code from the D3TexConv_v0.9 source code??

Cause I can't, I'm more of a C# person, no clue how to compile this in C++ in Visual Studio 2010   

Thnx
T.
## Post #108
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-05-20T12:25:05+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Sadly, I'm not a programmer, but thanks to windfury I did come up a ridiculously circuitous method that works for me:
I use XVI32 Hex editor. Make sure you back up your files as using a hex editor can royally screw them. Not my fault if this happens, use at your own risk.

1. I make the following script for XVI32 in Notepad:

ADR 0
REPLACE EF BE AD DE 2D BY EF BE AD DE 2B

and save it in my extracted Diablo 3 textures folder as texture.xsc. It doesn't really matter where you save it, so long as you get the path right in your batch file.

2. I make the following batch file and save it in my extracted Diablo 3 textures folder (which in this example for me is C:\GAMEDATA\DIABLOIII\WORK\TEST\). Of course, you will have to update your paths to XVI32.exe and texture.xsc:

@for /f "tokens=*" %%a in ('dir /b *.tex') do ( "E:\APPLICATIONS\HEX EDITOR XVI32\xvi32_2.51\xvi32.exe" %%a /S="C:\GAMEDATA\DIABLOIII\WORK\TEST\texture.xsc" )

3. I run the batch file and watch the magic. 
EDIT: Took me about 40 minutes to do all of the files. Effective...but not efficient. Also, it doesn't like spaces in the .tex file name. There are only a few, but add an underscore or something or you'll have to watch the whole thing.

4. I use D3TexConv_v0.9 to convert the files. So far they all seem to work.

Good luck!
## Post #109
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-05-20T14:06:36+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Zardalu thnx man

in the mean time I came up with some c# code 

```
            string file = @"2DInventoryBelts.tex";

            using(BinaryReader br = new BinaryReader(File.Open(file, FileMode.Open)))
            {
                byte[] header = br.ReadBytes(4);
                int nbrBytes = (int)br.BaseStream.Length;

                byte change = br.ReadByte(); // is 45, change to 43

                using (BinaryWriter bw = new BinaryWriter(File.Create(file.Replace(".tex","CON.tex"))))
                {
                    byte newByte = (byte)43;

                    bw.Write(header);
                    bw.Write(newByte);
                    bw.Write(br.ReadBytes(nbrBytes-5));


                    bw.Close();
                }


                br.Close();
            }


```


I put a looping around it so it does this for all the tex at the same time and I added a Process.Start(...) so it immediatly converts it to DDS.

Cheers

T.
## Post #110
- Username: Orvid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 18, 2012 2:20 am
- Post datetime: 2012-05-21T00:43:29+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Who says you need to re-compile it? Open the .exe in a hex editor and change the byte at offset 0x1487 from 2B to 2D.
## Post #111
- Username: dilbertgod
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 24, 2012 12:36 pm
- Post datetime: 2012-05-24T04:38:01+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Is it possible to convert an altered .dds / .txt file back into a diablo3 .tex file, or has a converter not been released for such a thing?
## Post #112
- Username: Necrolis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 15, 2011 4:06 am
- Post datetime: 2012-05-30T10:38:02+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

> Reply from dilbertgod
>
> Is it possible to convert an altered .dds / .txt file back into a diablo3 .tex file, or has a converter not been released for such a thing?there is no converter that I know of, I was planning to make one, but unfortunately I've been totally swamped with work and university (hence why the tool also hasn't been updated to remove the 0x2D check, which is incorrect, as its the SNO version).

> Reply from TaylorMouse
>
> Oke, nice solution, but I don't want to change each tex file manually,
is there a way to do this, all at once?

More on the question, is there ANY one that gets to compile the code from the D3TexConv_v0.9 source code??

Cause I can't, I'm more of a C# person, no clue how to compile this in C++ in Visual Studio 2010Its actually written for code::blocks, here is an updated version + source: [D3TexConv 0.9b](http://www38.zippyshare.com/v/29977667/file.html).
it removes the retarded version check, plus now all files it creates will be outputted to a folder called D3TexConv in the same folder as the file it just converted.
## Post #113
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-06-04T16:31:17+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Anyone figured out the bones on the models yet?

Or did I passed over it somewhere?

T.
## Post #114
- Username: youseesee3
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 09, 2012 9:07 pm
- Post datetime: 2012-06-09T13:09:53+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

working on it:
## Post #115
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2018-10-11T22:09:54+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

The current version of diablo3 (2.6.1 / 2018) has some textures in a new format.
The D3TexConv tool isn't able to convert format 0x2B (=43) for example a2dun_zolt_floor_design_B_autoNM.tex.
Does anyone have an idea what an *autoNM file stores - or how to get them to convert ?

I mean, a first guess would be NormalMap but those are  already stored in *_norm files.
## Post #116
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-12T02:06:25+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

what's this love for the dead beef? upload a sample then. done [that other one](https://zenhax.com/viewtopic.php?f=7&t=4389) already. i might just add to it.
## Post #117
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2018-10-12T06:10:05+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Spare time project which I picked up again for fun. Back in 2014 or so had an importer working and was able to get keyframes and decided to finish it up a bit and get the code for interpolation working. Wanted to see if the fileformat of the meshes/animations changed so grabbed the current version, and noticed the new textureformat, so yeah... here's a link with some sample files [https://www.dropbox.com/s/3lt4qzcop2w1o ... M.zip?dl=0](https://www.dropbox.com/s/3lt4qzcop2w1odi/d3_autoNM.zip?dl=0)

I'll check out your post and adjust D3TexConv to see if anything else is missing. 

Many url's with developer info on D3 are dead now, unfortunately.  
So cool that someone is still active, didn't expect that.
## Post #118
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-12T14:42:24+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

i'm not exactly active on this d3 thing. just picked up the file puzzle on zenhax. and well... those samples seem to be bc6h format. i've never seen the pattern really, but i can spot half float data. will update when i got it. i won't update the d3texconv tho. i can't read this decode code. seems nonsense to me. done it my way. easy. gotta rewrite the bms to output into the dx10 dds format tho. 

edit: i was wrong. nothing half about it. just DXTn normal maps. 
[d3_tex2dds_v3+.rar](https://xentaxbackup.github.io/file/15010_d3_tex2dds_v3+.rar)
## Post #119
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2018-10-12T18:43:13+00:00
- Post Title: Re: Textures of Beta Diablo 3, ".tex" files converter needed

Oh nicey, thanks! 

Didn't know bms, good to know for future use. 
Attached the old D3TexConv-tool revived and updated to a sparkly fresh v0.91...
[D3TexConv v0.91.zip](https://xentaxbackup.github.io/file/15014_D3TexConv v0.91.zip)
