## Post #1
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-06T03:03:23+00:00
- Post Title: CABAL .EBM Can't Open 3D model

Some one know tihs ploblem or help 

DeathKnight_boss.7z
[http://www10.zippyshare.com/v/J0s7nWIz/file.html](http://www10.zippyshare.com/v/J0s7nWIz/file.html)
## Post #2
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-08T14:45:53+00:00
- Post Title: CABAL .EBM Can't Open 3D model

bump
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-08T19:18:05+00:00
- Post Title: CABAL .EBM Can't Open 3D model

DeathKnight_boss.png (105.43 KiB) Viewed 271 times


 
search for FF FF FF FF and that will take you to where the models are
the byte after that is the mesh ID
the 2 bytes after that are the number of vertices
the 2 bytes after that you must multiply by 3 to get face count
2 bytes after that are padding and then the vertex block starts

have you tried the cabal scripts here?
[viewtopic.php?p=91804#p91804](http://forum.xentax.com/viewtopic.php?p=91804#p91804)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-08T19:24:45+00:00
- Post Title: CABAL .EBM Can't Open 3D model

@godskin: use a hexeditor to look into that EBM, you'll find the strings 'DDS' and 'DXT1'

delete everything before 'DDS' and save the rest as as whatevername.dds

as simple as that:



DeathNight_Boss-EBM.jpg (47.97 KiB) Viewed 270 times


(There's another two dds contained (DXT3) - but I'll leave that task to be solved by you.  )

edit: upps, seems AceWell was active during my typing
## Post #5
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-08T20:38:28+00:00
- Post Title: CABAL .EBM Can't Open 3D model

> Reply from AceWell
>
> DeathKnight_boss.png
 
search for FF FF FF FF and that will take you to where the models are
the byte after that is the mesh ID
the 2 bytes after that are the number of vertices
the 2 bytes after that you must multiply by 3 to get face count
2 bytes after that are padding and then the vertex block starts

have you tried the cabal scripts here?
viewtopic.php?p=91804#p91804

thx but don't work
## Post #6
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-08T20:42:57+00:00
- Post Title: CABAL .EBM Can't Open 3D model

> Reply from shakotay2
>
> @godskin: use a hexeditor to look into that EBM, you'll find the strings 'DDS' and 'DXT1'

delete everything before 'DDS' and save the rest as as whatevername.dds

as simple as that:
DeathNight_Boss-EBM.jpg
(There's another two dds contained (DXT3) - but I'll leave that task to be solved by you.  )

edit: upps, seems AceWell was active during my typing

this old ebm work on noesis mdf_mamuo.ebm
[http://www117.zippyshare.com/v/FyYTyr9k/file.html](http://www117.zippyshare.com/v/FyYTyr9k/file.html)

cabal korea have protection some .ebm file ??
## Post #7
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-08T20:49:46+00:00
- Post Title: CABAL .EBM Can't Open 3D model

> Reply from godskin
>
> shakotay2 wrote:@godskin: use a hexeditor to look into that EBM, you'll find the strings 'DDS' and 'DXT1'

delete everything before 'DDS' and save the rest as as whatevername.dds

as simple as that:
DeathNight_Boss-EBM.jpg
(There's another two dds contained (DXT3) - but I'll leave that task to be solved by you.  )

edit: upps, seems AceWell was active during my typing 

this old ebm work on noesis mdf_mamuo.ebm
http://www117.zippyshare.com/v/FyYTyr9k/file.html

cabal korea have protection some .ebm file ??

i need new .ebm can open in noesis only  pls share how to fix 

shakotay2 / Acwell 
don't fixed
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-09T04:59:02+00:00
- Post Title: CABAL .EBM Can't Open 3D model

in function noepyCheckType(data) in fmt_CabalOnline_ebm.py add a further idstring:

```
        if idstring not in [0x0003ED03, 0x0003EE03, 0x0003EF03, 0x0003F003, 0x0003F103]:
```

But you won't get too far - the script freezes Noesis then with DeathKnight_boss.EBM because finale00's script can't handle ebms of type 0x0003F103.

So if you want the textures you should try out my method.
## Post #9
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-09T05:28:07+00:00
- Post Title: CABAL .EBM Can't Open 3D model

> Reply from shakotay2
>
> in function noepyCheckType(data) in fmt_CabalOnline_ebm.py add a further idstring:
Code: Select all        if idstring not in [0x0003ED03, 0x0003EE03, 0x0003EF03, 0x0003F003, 0x0003F103]:
But you won't get too far - the script freezes Noesis then with DeathKnight_boss.EBM because finale00's script can't handle ebms of type 0x0003F103.

So if you want the textures you should try out my method.

i added u code
don't work bro
noesis freezy and not reponding after open Deatking

i do not need Texture
i need model + Skeletion + bone
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-09T06:25:39+00:00
- Post Title: CABAL .EBM Can't Open 3D model

> Reply from godskin
>
> noesis freezy and not reponding after open Deatkingyou don't read what other people write, do you?
Yes, it freezes - that's what I wrote.

Also WHY didn't you write that you don't need textures?
I really hate it when people waste my time.

This is the model:



DeathKnight_Boss.jpg (152.69 KiB) Viewed 245 times


Try out hex2obj or let it be.
## Post #11
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-09T06:39:27+00:00
- Post Title: CABAL .EBM Can't Open 3D model

> Reply from shakotay2
>
> godskin wrote:noesis freezy and not reponding after open Deatkingyou don't read what other people write, do you?
Yes, it freezes - that's what I wrote.

Also WHY didn't you write that you don't need textures?
I really hate it when people waste my time.

This is the model:
DeathKnight_Boss.jpg
Try out hex2obj or let it be.
Ok thank you Sorry
can share DeathKnight.obj
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-09T06:56:15+00:00
- Post Title: CABAL .EBM Can't Open 3D model

hex2obj can create obj files from models using H2O files.
In hex2obj:
File open (ebm file)
Open H2O
File SaveAs Mesh

Here's the H2O for the horse - save as txt file and rename it to DN_Horse.H2O for example:

0x236D81 23208
Vb1
32 24
0x209FA1 5743
020000
0x0 255
## Post #13
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-07-09T09:30:53+00:00
- Post Title: CABAL .EBM Can't Open 3D model

Noesis plugin new line: 160 -
            self.inFile.readUShort()
[fmt_CabalOnline_ebm.7z](https://xentaxbackup.github.io/file/11271_fmt_CabalOnline_ebm.7z)
## Post #14
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-09T09:49:40+00:00
- Post Title: CABAL .EBM Can't Open 3D model

> Reply from Szkaradek123
>
> Noesis plugin new line: 160 -
            self.inFile.readUShort()
 thx very much work !!

pls fix 010 Scrtip can't load new ebm


```
// Game: CABAL Online
// File Format: EBM/ECH
// Description: Template for CABAL's model files
//--------------------------------------##
// Author: Yamachi
// Team: The Divinity Project
// Website: http://board.thedivinityproject.com
//--------------------------------------##

#include "Common_Cabal.bt"

//-Local-Variables----------------------

local string estType = "EBM";

local int tex_offsets[256], tex_lengths[256], dds_offsets[256];
local int index = 0;

//-Enumerations-------------------------

typedef enum <uint32> {
    MATERIAL         = 0x41470201,
    MESH             = 0x41470202,
    ARMATURE         = 0x41470203,
    ANIMATION        = 0x41470204,
    INFLUENCE        = 0x41470205,
} CID;      // Chunk ID's

typedef enum <int32> {
    MULTIPLY                = 0x04,
    GRAIN_MERGE             = 0x08,
    HARD_LIGHT              = 0x09,
    MULTIPLY__INVERT_PARENT = 0x0A,
    ODD_FLICKER_EFFECT      = 0x0E,
    BELOW                   = 0x10,
    SCREEN                  = 0x12,
    SOME_PURE_WHITE_THING   = 0x13,
    CHROME                  = 0x18,
} RenderFlag;    // 2nd layer render flag

//-Structures---------------------------

typedef struct {
	uint magic <format=hex>;
	ushort unkus;
	byte model_flag <format=hex>;
    byte alpha_threshold;
    ushort unkus;
	Vector3 bound_min;          // Bounding box lower vertex
	Vector3 bound_max;          // Bounding box upper vertex
	uint scale_percentage;      // Scale of model (default = 100%)
	CID chunk_id <format=hex>;  // ID for the next chunk
} Header;

typedef struct {
    float r, g, b, a;
} RGBA <read=RGBARead, write=RGBAWrite>;

typedef struct {
    RGBA r <hidden=true>;
    ParseRGBA(r);
    RGBA ambient;

    RGBA r <hidden=true>;
    ParseRGBA(r);
    RGBA diffuse;

	RGBA r <hidden=true>;
    ParseRGBA(r);
    RGBA specular;

    RGBA r <hidden=true>;
    ParseRGBA(r);
    RGBA emissive;
    SetBackColor(cNone);

	float power;
} MatProps;     // Material properties

typedef struct {
    ubyte unkba[9];
    int material_index <read=MaterialIndexReadI>;
    Bool is_faceted;
    Vector2 speed;
    RenderFlag render_flags;
} Layer;

typedef struct {
	Text id;
    tex_lengths[index] = id.length;
    tex_offsets[index] = FTell() - id.length;
	uint size;
    dds_offsets[index] = FTell();
	ubyte data[size];
    index++;
} IndexedTexture;

typedef struct {
    MatProps material_properties;
    IndexedTexture texture;
    Layer layer;
} Material;

typedef struct {
    uint count;
    if (count != 0) {
        uint vertex_index[count];
        float weight[count]; }
} InfluenceBone;

typedef struct {
    InfluenceBone influence_for_bone[skeleton.count] <optimize=false>;
} Influence;

typedef struct {
    Text id;
    Matrix world_matrix;
    Matrix local_matrix;
    int root_bone_id;   // Bone to attach mesh to.  Causes entire mesh to "stick" to that bone, moving when it does.
    ubyte material_index <read=MaterialIndexRead>;
    ushort vertex_count;
    ushort face_count;
    Vertex vertices[vertex_count];
    Face faces[face_count];

    /*CID chunk_id;   // INFLUENCE
    if (chunk_id == INFLUENCE) {
        ushort influence_count;
        if (influence_count != 0)
            Influence influences[influence_count] <optimize=false>; }
    else {FSeek(FTell() - 4) ; }*/
    
    // Hopefully this works for all models.  It should do.
    if (vertex_count > 0) {
        CID chunk_id;
        ushort influence_count;
        if (influence_count != 0)
            Influence influences[influence_count] <optimize=false>; }
} Mesh;

typedef struct {
    Text id;
    int parent_bone_index;
    Matrix bone_space_matrix;
    Matrix parent_bone_space_matrix;
} Bone <read=BoneRead>;

typedef struct {
    Text id;
    uint translation_count;
    Translation translations[translation_count] <optimize=false>;
    uint rotation_count;
    Rotation rotations[rotation_count] <optimize=false>;
} Transformation <read=TransformationRead>;

typedef struct {
    Text id;
    ushort count;
    Transformation transformations[count] <optimize=false>;
} Animation <read=AnimationRead>;

typedef struct {
    ushort count;
    local ushort tex_name_lengths[count];
    local short i = 0;
	Material materials[count] <optimize=false>;
    CID chunk_id <format=hex>;
} MT <read=CommentMT>;

typedef struct {
    ushort count;
    Mesh meshes[count] <optimize=false>;
    CID chunk_id <format=hex>;
} GE <read=CommentGE>;

typedef struct {
    ushort count;
    if (count != 0)
        Bone bones[count] <optimize=false>;
    CID chunk_id <format=hex>;
} SK <read=CommentSK>;

typedef struct {
    ushort count;
    if (count != 0)
        Animation animations[count] <optimize=false>;
} AN <read=CommentAN>;

typedef struct {
    local int i;

    for (i = 0; i < 210; i++)
    {
        Colour c <hidden=true>;
        ParseColour(c);
        Colour glow_colour;

        SetBackColor(cNone);
        SetForeColor(cNone);
    }
} GL;

//-Main---------------------------------

FSeek(0);

Header model_header <read=CommentHDR>;

local CID chunk_id = model_header.chunk_id;
local ushort x = 0;

while (x < 4) {
    if (chunk_id == MATERIAL) {
        MT materials_and_textures;
        chunk_id = materials_and_textures.chunk_id;
        x++;
    }
    else if (chunk_id == MESH) {
        GE geometry;
        chunk_id = geometry.chunk_id;
        x++;
    }
    else if (chunk_id == ARMATURE) {
        SK skeleton;
        chunk_id = skeleton.chunk_id;
        x++;
    }
    else if (chunk_id == ANIMATION) {
        AN animations;
        x++;
    }
    else { x = 4; }
}

if (FileSize() - FTell() > 4)
    GL glows;

//-Functions----------------------------

void ParseRGBA(RGBA &r) {
    FSeek(FTell() - 16);
    local float blue = (r.b * 255.0f);
    local float green = (r.g * 255.0f);
    local float red = (r.r * 255.0f);
    local int bc = (int)blue * 0x10000 + (int)green * 0x100 + (int)red;
    SetBackColor(bc);
}

//-Chunk-Descriptors--------------------

string CommentHDR(Header &voi) {
    return ("Unknown values, model flag, bounding box, and following chunk ID.");
}

string CommentMT(MT &voi) {
    return ("Materials and textures.");
}

string CommentGE(GE &voi) {
    return ("Meshes.");
}

string CommentSK(SK &voi) {
    return ("Bones.");
}

string CommentAN(AN &voi) {
    return ("Animation sequences.");
}

//-English------------------------------

string MaterialIndexRead(ubyte i) {
    string name = ReadString(tex_offsets[i]);
    name = SubStr(name, 0, tex_lengths[i]);
    string s;
    SPrintf(s, "%i ( %s )", i, name);
    return s;
}

string MaterialIndexReadI(int i) {
    string name;
    if (i == -1)
        name = "NULL";
    else {
        name = ReadString(tex_offsets[i]);
        name = SubStr(name, 0, tex_lengths[i]); }
    string s;
    SPrintf(s, "%i ( %s )", i, name);
    return s;
}

string AnimationRead(Animation &a) {
    return (a.id.text);
}

string TransformationRead(Transformation &t) {
    string s;
    SPrintf(s, "%s: %s", "Bones", t.id.text);
    return s;
}

string RGBARead(RGBA &r) {
    string s;
    SPrintf(s, "(%f %f %f %f)", r.r, r.g, r.b, r.a);
    return s;
}
void RGBAWrite(RGBA &r, string s ) {
    SScanf(s, "(%f %f %f %f)", r.r, r.g, r.b, r.a);
}

string BoneRead(Bone &b) {
    string s;
    SPrintf(s, "%s", b.id.text);
    return s;
}

```
## Post #15
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-07-11T13:39:00+00:00
- Post Title: CABAL .EBM Can't Open 3D model

Hi godskin
I see your purpose here is only testing scripts. Nice.

What is this ? From which software is it from ? And how it use ?

//--------------------------------------##
// Game: CABAL Online
// File Format: EBM/ECH
// Description: Template for CABAL's model files
//--------------------------------------##
// Author: Yamachi
// Team: The Divinity Project
// Website: [http://board.thedivinityproject.com](http://board.thedivinityproject.com)
//--------------------------------------##
## Post #16
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-11T16:55:56+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

> Reply from Szkaradek123
>
> Hi godskin
I see your purpose here is only testing scripts. Nice.

What is this ? From which software is it from ? And how it use ?

//--------------------------------------##
// Game: CABAL Online
// File Format: EBM/ECH
// Description: Template for CABAL's model files
//--------------------------------------##
// Author: Yamachi
// Team: The Divinity Project
// Website: http://board.thedivinityproject.com
//--------------------------------------##

aredy fixed thx > <
## Post #17
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-11T17:27:48+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

> Reply from Szkaradek123
>
> Hi godskin
I see your purpose here is only testing scripts. Nice.

What is this ? From which software is it from ? And how it use ?

//--------------------------------------##
// Game: CABAL Online
// File Format: EBM/ECH
// Description: Template for CABAL's model files
//--------------------------------------##
// Author: Yamachi
// Team: The Divinity Project
// Website: http://board.thedivinityproject.com
//--------------------------------------##

thx fixd ♥

waiting cabal 2 scrip blender249 ♥♥♥
## Post #18
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2020-08-07T02:26:34+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

ey Hello, Godskin can you upload the script for open the new .ebm files? and for what software it is? Thanks.
## Post #19
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-08-07T15:59:15+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

> Reply from moonpaladin ↑Fri Aug 07, 2020 10:26 am at Fri Aug 07, 2020 10:26 am
>
> 
ey Hello, Godskin can you upload the script for open the new .ebm files? and for what software it is? Thanks.

Hi moonpaladin.

What do you need exactly?  
I recently imported cabal models in 3ds and i found problem I already solved.

The script godskin posted is a template for 010 editor, the purpose of it is edit ebm and ech and make them openable in 3d studio max with fatduck script.

here I attached the newest template I have , in order to modify ebm ech.

Could you attach newest ebm ?
[template.rar](https://xentaxbackup.github.io/file/18570_template.rar)
## Post #20
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2020-08-07T18:46:32+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

ey Hello, thanks for response I'm just using the .ebm script for blender 2.49, cause have not 3d studio, and don't know where are the recent files becauseI just update my CABAL Transcendence (UTS) client and don't have new weapons.
## Post #21
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-08-08T10:58:59+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

I upload it and found new monsters, opened them in 3dsmax without problem.

Anyway this thread is intended to help people with script. If you don't find weapon you should ask on forum dedicated on modding cabal, I'm sorry but i'm not going to spend time on finding a specific weapon
## Post #22
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-19T03:35:31+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

> Reply from Drawing ↑Sat Aug 08, 2020 6:58 pm at Sat Aug 08, 2020 6:58 pm
>
> 
I upload it and found new monsters, opened them in 3dsmax without problem.

Anyway this thread is intended to help people with script. If you don't find weapon you should ask on forum dedicated on modding cabal, I'm sorry but i'm not going to spend time on finding a specific weapon

Hello Drawing, , I found this topic [viewtopic.php?p=91804#p91804](https://forum.xentax.com/viewtopic.php?p=91804#p91804), but as you said that you had some problems, I suppose you edited it a bit, could you share it please? Thank you
## Post #23
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-19T03:54:03+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

This is how it looks when I import a model, the meshes are not seen, plus cannot export and if I tried to import new model, nothing happens, no popup a window, sounds like an error.



MEGAERROR.png (159.67 KiB) Viewed 50 times
## Post #24
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-19T06:37:16+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

> Reply from Drawing ↑Fri Aug 07, 2020 11:59 pm at Fri Aug 07, 2020 11:59 pm
>
> 
moonpaladin wrote: ↑Fri Aug 07, 2020 10:26 am
ey Hello, Godskin can you upload the script for open the new .ebm files? and for what software it is? Thanks.


Hi moonpaladin.

What do you need exactly?  
I recently imported cabal models in 3ds and i found problem I already solved.

The script godskin posted is a template for 010 editor, the purpose of it is edit ebm and ech and make them openable in 3d studio max with fatduck script.

here I attached the newest template I have , in order to modify ebm ech.

Could you attach newest ebm ?

Well, I have been tried for a while but not success, I have downloaded the templates you posted and execute them into the model, it loads the blocks, but don't know what need to modify to it can be loaded in 3dsmax like the old .ebm files, that those loads without problems in the 3dsmax.   Please take a look when you can  ty.

[https://www.mediafire.com/file/6ozlg6m6 ... 4.ebm/file](https://www.mediafire.com/file/6ozlg6m6k5uv73d/bike_444.ebm/file)
## Post #25
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-03-19T10:57:06+00:00
- Post Title: Re: CABAL .EBM Can't Open 3D model

> Reply from moonpaladin ↑Fri Mar 19, 2021 2:37 pm at Fri Mar 19, 2021 2:37 pm
>
> 

Well, I have been tried for a while but not success, I have downloaded the templates you posted and execute them into the model, it loads the blocks, but don't know what need to modify to it can be loaded in 3dsmax like the old .ebm files, that those loads without problems in the 3dsmax.   Please take a look when you can  ty.

https://www.mediafire.com/file/6ozlg6m6 ... 4.ebm/file

FIrst of all for 3dstudio max use this script made by fatduck [http://www.mediafire.com/file/2a6m8nt4k ... t.rar/file](http://www.mediafire.com/file/2a6m8nt4kai8k34/3ds_Max_movement_script.rar/file)
Second to understand what you need to edit with 010 editor see this video, it explain well [https://www.youtube.com/watch?v=0all-pqQm8w](https://www.youtube.com/watch?v=0all-pqQm8w)
