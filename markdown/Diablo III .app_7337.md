## Post #1
- Username: anhhungmeo1234
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Aug 15, 2010 4:48 pm
- Post datetime: 2011-09-11T03:29:55+00:00
- Post Title: Diablo III .app

This is file in Diablo III, i think it's model. File simple:
[http://www.mediafire.com/?5aacnbdea8mbneg](http://www.mediafire.com/?5aacnbdea8mbneg)
## Post #2
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-13T19:41:08+00:00
- Post Title: Diablo III .app

Moving the .app research here from the game archive research forum.

I'll be updating this post as I make progress with the format.
Currently we have vertex, poly, normal, uv, tangent, bitangent and blendweight data mapped properly, there's still some stuff left to decipher.

Update #1: figured out what some of the unknown stuff is for, added hinge points
Update #2: finally found a good lead on the animation data, nothing to see yet, but I updated the script - maybe someone can work on it while I'm away
Update #3: animation stuff might have been a dead end, refactored the script a bit with new names
Update #4: some more refactoring of names as things get more clear

My current 010 editor template for parsing .app files is the following: (the text output in the editor is a wavefront object file that can be loaded into deep exploration for example)

```
//--- 010 Editor v3.2.1 Binary Template
//
// File: Diablo 3 appearance file template
// Author: BoyC
// Revision: v0.37
// Purpose: Analyzing 3D data in Diablo 3
//--------------------------------------

local unsigned int vxcnt=0;
local unsigned int LookCount=0;

struct ChunkData
{
    unsigned int Count<bgcolor=0xff00ff>;
    unsigned int Offset<format=hex,bgcolor=0xff00ff>;
    unsigned int Size<bgcolor=0xff00ff>;
};

struct ChunkHeader
{
    unsigned int h[4];
};

struct BONEDATA //size = 68
{
    unsigned int unk1[4];
    float unk2[3];
    unsigned int unk[3];
    float unk4[7];
};

struct BONE //size = 236
{
    char Name[64];
    int ParentID;
    float unk2[34]; //two matrices plus extra
    ChunkData UnkChunk;
    unsigned int unk[4];
    int unk3;
    Printf("# Bone: %s\n",Name);

    local int pos=FTell();
    FSeek(UnkChunk.Offset+16);
    
    if (UnkChunk.Offset)
    {
        struct 
        {
            BONEDATA bonedata[UnkChunk.Count]<optimize=false>;
        } bonedata<bgcolor=0x00f0a0,comment="Unknown purpose bone data">;        
    }

    FSeek(pos);
}; 

struct VERTEX //size = 44
{
    float x,y,z;
    unsigned char nx,ny,nz,nw;
    int unk3,unk4;
    unsigned short u,v;
    unsigned int unk1;
    char tx,ty,tz,tw;
    char bx,by,bz,bw;
    unsigned int unk2;

    //obj export part
    /**/
    local float ru=u,rv=v,rnx=nx,rny=ny,rnz=nz;
    ru=(ru-32767)/512.0f;
    rv=(rv-32767)/512.0f;
    rnx=(rnx-127)/127.0f;
    rny=(rny-127)/127.0f;
    rnz=(rnz-127)/127.0f;

    Printf("v %f %f %f\n",x,y,z);
    Printf("vt %f %f\n",ru,rv);    
    Printf("vn %f %f %f\n",rnx,rny,rnz);/**/
};

struct TRIINDICES
{
    unsigned short a,b,c;

    //obj export part
    Printf("f %d/%d/%d %d/%d/%d %d/%d/%d\n",vxcnt+a+1,vxcnt+a+1,vxcnt+a+1,vxcnt+b+1,vxcnt+b+1,vxcnt+b+1,vxcnt+c+1,vxcnt+c+1,vxcnt+c+1);
}; //complete

struct BLENDWEIGHT
{
    int BoneID;
    float BoneWeight;
}; //complete

struct BLENDDATA //size = 24
{
    BLENDWEIGHT Weights[3]<optimize=false>;
}; //complete

struct LOOKDATA //size = 248
{
    unsigned int Five;
    int MinusOne;
    unsigned int DataOffset1<format=hex>;
    unsigned int DataSize1;
    unsigned int unk[3];
    float Matrix[16];
    unsigned int unk2[2];
    unsigned int DataOffset2<format=hex>;
    unsigned int DataSize2;
    unsigned int unk3[35];
};

struct SUBOBJECT //size = 140
{
    char Name[128];
    unsigned int Offset,Size,Zero;
    
    local int pos=FTell();
    FSeek(Offset+16);
    
    struct 
    {
        LOOKDATA lookdata[LookCount]<optimize=false>;
    } LookDataList<bgcolor=0x00a0f0,comment="Look Descriptors">;        

    FSeek(pos);
};

struct MESH //size = 372
{
    int unk1;
    ChunkData VertexChunk; //vertex size = 44
    ChunkData WeightChunk; //weight size = 24
    int Zero1;
    ChunkData IndexChunk; // 16bit index buffer for a triangle list
    ChunkData UnknownChunk; // points to an array of chunkdatas, could be anim
    int unk5[4];
    char SubObjectName[128];
    char MeshName[128];
    float funk1[6]; //bounding box? 
    unsigned int Zero2;
    unsigned int unk[4];

    Printf("# unk1: %4d vxcount: %4d\n",unk1,VertexChunk.Count);
    Printf("# mesh %s is part of subobject %s\n",MeshName,SubObjectName);

    local unsigned int Pos=FTell();

    if (VertexChunk.Offset)
    {
        FSeek(VertexChunk.Offset);
        struct 
        {
            ChunkHeader ch;
            VERTEX vx[VertexChunk.Count]<optimize=false>;
        } Vertices;        
    }
    
    if (WeightChunk.Offset)
    {
        FSeek(WeightChunk.Offset);
        struct 
        {
            ChunkHeader ch;
            BLENDDATA w[VertexChunk.Count]<optimize=false>;
        } BlendWeights;        
    }

    if (IndexChunk.Offset)
    {
        FSeek(IndexChunk.Offset);
        struct 
        {
            ChunkHeader ch;
            TRIINDICES w[IndexChunk.Count/3]<optimize=false>;
        } Triangles;        
    }

    FSeek(Pos);
    vxcnt+=VertexChunk.Count;
}; 

struct HARDPOINT //size = 96
{  
    char Name[64];
    int ParentBone;
    float qx,qy,qz,qw; //rotation as a quaternion
    float x,y,z; //position
};

struct COLLISIONOBJ //size = 104
{
    unsigned int x[26];
};

struct NAME
{
    char Name[64];
};

struct 
{
    unsigned int DEADBEEF[8];
    unsigned int Counter1;

    ChunkData BoneChunk; // size = 236
    
    FSeek(FTell()+30*4);

    ChunkData MeshChunk; // size = 372

    FSeek(FTell()+9*4);

    float FloatAray1[4]; //bounding sphere?

    ChunkData CollisionChunk; // size = 104

    FSeek(FTell()+3*4);

    ChunkData HPChunk; // size = 96

    FSeek(FTell()+5*4);

    float One;
    FSeek(FTell()+6*4);

    ChunkData UnkChunk1;

    FSeek(FTell()+4);

    ChunkData UnkChunk2;

    FSeek(FTell()+4);

    ChunkData UnkChunk3;

    FSeek(FTell()+8);

    float FloatArray2[6]; //bounding box?

    FSeek(FTell()+10*4);

    char xobject[256];
    char xobjectpath[256];
    char xmesh[256];
    char xmeshpath[256];

    FSeek(FTell()+4*4);

    unsigned int LookCnt;
    LookCount=LookCnt;

    ChunkData SubObjectChunk; // size = 140

    FSeek(FTell()+4);

    ChunkData LookNameChunk; // size = 64 count = Counter1

    FSeek(FTell()+18*4);

    //previously referenced data starts here, header size is 0x628h

    Printf("# Bone Count: %d\n",BoneChunk.Count);
    Printf("# Mesh Count: %d\n",MeshChunk.Count);
   

    if (BoneChunk.Offset)
    {
        FSeek(BoneChunk.Offset+16);
        struct 
        {
            //ChunkHeader ch;
            BONE bone[BoneChunk.Count]<optimize=false>;
        } Bones<bgcolor=0xa0a0a0,comment="Bone data">;
    }

    if (MeshChunk.Offset)
    {
        FSeek(MeshChunk.Offset+16);
        struct 
        {
            //ChunkHeader ch;
            MESH mesh[MeshChunk.Count]<optimize=false>;
        } Models<bgcolor=0xb0f0b0,comment="Model data">;        
    }

    if (SubObjectChunk.Offset)
    {
        FSeek(SubObjectChunk.Offset+16);
        struct 
        {
            //ChunkHeader ch;
            SUBOBJECT group[SubObjectChunk.Count]<optimize=false>;
        } SubObjects<bgcolor=0xc0c0f0,comment="SubObjects">;        
    }

    if (HPChunk.Offset)
    {
        FSeek(HPChunk.Offset+16);
        struct 
        {
            //ChunkHeader ch;
            HARDPOINT hardpoint[HPChunk.Count]<optimize=false>;
        } HardPoints<bgcolor=0xd0f0f0,comment="These are hardpoints where other models can be attached to this one">;        
    }

    if (CollisionChunk.Offset)
    {
        FSeek(CollisionChunk.Offset+16);
        struct 
        {
            //ChunkHeader ch;
            COLLISIONOBJ Collisions[CollisionChunk.Count]<optimize=false>;
        } CollisionObjects<bgcolor=0xf0e0f0,comment="Seems to be collision mesh data">;        
    }

    if (LookNameChunk.Offset)
    {
        FSeek(LookNameChunk.Offset+16);
        struct 
        {
            NAME Name[LookCount]<optimize=false>;
        } LookNames<bgcolor=0xf0a0a0,comment="Look Names">;                
    }


} HEADER<bgcolor=0xf0f000>;
```
## Post #3
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-13T20:48:34+00:00
- Post Title: Diablo III .app

This post is reserved for images of the best current results.
## Post #4
- Username: Corbo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 14, 2011 5:11 am
- Post datetime: 2011-09-13T21:15:19+00:00
- Post Title: Diablo III .app

You're amazing!
I have no programming knowledge but I will help you in anyway I can, testing, ideas and such.

So far I've tested a few of the characters and they all seem to break, perhaps cause they are rigged? Static models seem to work out the best.
The leah model exports almost perfectly except for some normal issues.
## Post #5
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-13T22:16:25+00:00
- Post Title: Diablo III .app

Well the characters don't actually break. I think the wizard_female.app and the rest of them are actually only the models prepared for the login screen with complete sets of armor. There are several meshes in each file and they are merged together with this method. Once we have all the pieces in place I'll do an exporter to a format that supports multiple models, that should fix this issue.
EDIT:
Same thing happens if you load critters for example - if you check out the wireframe, you can actually see the bone structure inside the animal
## Post #6
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-15T08:39:44+00:00
- Post Title: Diablo III .app

> //--------------------------------------
>
> //--- 010 Editor v3.2.1 Binary Template
>
> //
>
> // File: Diablo 3 appearance file template
>
> // Author: BoyC
>
> // Revision: v0.37
>
> // Purpose: Analyzing 3D data in Diablo 3
>
> //--------------------------------------

With the old version, I can extract the output to obj files, but with your current version (v0.37), I cannot. Is it a test version ??
## Post #7
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-15T09:10:20+00:00
- Post Title: Diablo III .app

Oh sorry the output stuff has been commented out for speedy testing. I've fixed it now but there won't be any difference in the output yet - these are progress updates on mapping the format.
## Post #8
- Username: litaotao
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 15, 2011 9:23 pm
- Post datetime: 2011-09-15T13:42:10+00:00
- Post Title: Diablo III .app

Can anyone put a tool for extract obj?
## Post #9
- Username: afrokid
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 11, 2011 5:20 pm
- Post datetime: 2011-09-16T12:20:31+00:00
- Post Title: Diablo III .app

Edit: Nevermind, was using the wrong files.
## Post #10
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-16T16:08:45+00:00
- Post Title: Diablo III .app

How goes your progress in this department man?

I'm a little stuck over in the .tex / .gam department so I thought I would poke around here
## Post #11
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-17T16:59:42+00:00
- Post Title: Diablo III .app

Your script worked very well BoyC.  Most of mesh are extracted successfully. But when I imported it to Maya it still some trouble:
1. Mesh UV need to be flip Vertical.
2. When I extract the character, they are multiple mesh are in the single object that I was really hard to arrange them.

One more, mesh extracted have problem when import to 3DS max, they look melting. Though they are saved as .obj
## Post #12
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-19T17:41:35+00:00
- Post Title: Diablo III .app

1. Mesh UV need to be flip Vertical.

I'm getting the same.... how do you flip vertical xD
## Post #13
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-19T18:10:56+00:00
- Post Title: Diablo III .app

Replace the line "rv=(rv-32767)/512.0f;" with "rv=1-(rv-32767)/512.0f;"
## Post #14
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-09-20T02:03:47+00:00
- Post Title: Diablo III .app

How about the multiple mesh in one file ?
## Post #15
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-20T08:52:55+00:00
- Post Title: Diablo III .app

> Reply from npd2006
>
> How about the multiple mesh in one file ?
Still working on that but I'm swamped in real life stuff atm.
## Post #16
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-20T15:56:31+00:00
- Post Title: Re: Diablo III .app

Almost done will all the gams. Will be moving over to this area soonish
## Post #17
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-20T16:00:58+00:00
- Post Title: Re: Diablo III .app

> Reply from MrRawr
>
> Almost done will all the gams. Will be moving over to this area soonish
Great, the current script can be found at [http://diablo3dev.com/w/Models](http://diablo3dev.com/w/Models), I basically have the format architectually covered, at least I didn't find any models yet that have unexplored sections - the data in them is a completely different matter tho
## Post #18
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-20T16:13:34+00:00
- Post Title: Re: Diablo III .app

I noticed a few mistakes in some of your earlier stuff, it didn't matter for what you wanted to do (but it did to me) I've not fixed it on your script yet as I was focusing on a different area. I'll ofc upload the bits I changed when I get onto this tomorrow (most likely tomorrow)!
## Post #19
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-20T16:39:29+00:00
- Post Title: Re: Diablo III .app

> Reply from MrRawr
>
> I noticed a few mistakes in some of your earlier stuff, it didn't matter for what you wanted to do (but it did to me) I've not fixed it on your script yet as I was focusing on a different area. I'll ofc upload the bits I changed when I get onto this tomorrow (most likely tomorrow)!
Finally someone to work with
## Post #20
- Username: MrRawr
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Sep 14, 2011 1:37 am
- Post datetime: 2011-09-22T21:50:51+00:00
- Post Title: Re: Diablo III .app

still working on other things, fell ill yesterday  I'll be along soon though
## Post #21
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-09-22T22:03:19+00:00
- Post Title: Re: Diablo III .app

> Reply from MrRawr
>
> still working on other things, fell ill yesterday  I'll be along soon though
Yeah battling the flu myself :\
## Post #22
- Username: Dsummit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 24, 2011 11:07 pm
- Post datetime: 2011-09-24T15:14:00+00:00
- Post Title: Re: Diablo III .app

Sorry for the stupid question, but I don't get how you create the wavefront object file from the 010 template text output.

Great job by the way and thanks for sharing this!

Edit - Sorry figured that stuff was commented out. Still doesn't seems to work in DE but I'll play around with it.
## Post #23
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-05T13:55:23+00:00
- Post Title: Re: Diablo III .app

No one say anything for a long time
## Post #24
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-06T19:22:44+00:00
- Post Title: Re: Diablo III .app

Hello Guys!

I've just received the link to this forum, and I'm very glad to see that some hardcore guys are working on the extraction of Diablo3 models from the client.

What's the status now, how can I help?

Greetings,
Monguron
## Post #25
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-07T05:26:23+00:00
- Post Title: Re: Diablo III .app

Currently BoyC and MrRawr made a 010 editor template which use for extract obj model from .app files.
You can see source code here.
[http://diablo3dev.com/w/Models](http://diablo3dev.com/w/Models)

This template can extract most of .app without problem, accept for the character model, because it contains multiple mesh. So, we should have an multiple mesh exporter to control exporting.
## Post #26
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-07T06:35:29+00:00
- Post Title: Re: Diablo III .app

> Currently BoyC and MrRawr made a 010 editor template which use for extract obj model from .app files.
Ye it's nice. So the item models + textures can be extracted already. Am I right?

The hard task will be to write an app as a wow model viewer, which is able to put the correct size of the armors / weapons onto the chosen characters (barb, wizard, etc...).

> because it contains multiple mesh. So, we should have an multiple mesh exporter to control exporting.
Do we know already how the meshes are linked together? I mean with which method?
## Post #27
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-07T07:02:27+00:00
- Post Title: Re: Diablo III .app

> Ye it's nice. So the item models + textures can be extracted already. Am I right?
Yes, right.

The exporter just can translate from .app file to .obj model. It succeeded with object and weapon but with the character, just 1 file .app contains all armor of a character.
It is an example, you can see.


The exporter now is just a 010 editor template, not a tool yet. We use 010 to compile .app to obj file. You can start develop it to a model viewer

> Do we know already how the meshes are linked together? I mean with which method?
You can ask BoyC for the algorism. I am just a user and tester. But if you need any files to test I can give you.
## Post #28
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-07T07:14:12+00:00
- Post Title: Re: Diablo III .app

> The exporter just can translate from .app file to .obj model.
Cool. Is the texture contained in the .obj file as well, or is it in a separate .mat file, or in any other?

> The exporter now is just a 010 editor template, not a tool yet. We use 010 to compile .app to obj file. You can start develop it to a model viewer
I'm not a professional, but my aim is to write a simple model viewer first in Away3D framework, so it can run under Adobe Flash.

What it should know:

- load the selected .obj file (character / item / etc)
- you can rotate the item
- you can zoom in / out

This would be the first basic version.
## Post #29
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-07T07:22:18+00:00
- Post Title: Re: Diablo III .app

> Cool. Is the texture contained in the .obj file as well, or is it in a separate .mat file, or in any other?
The texture files are the files .TEX, which can be exported by using the tool call D3TexConv. You can download it here
[http://diablo3dev.com/w/D3TexConv](http://diablo3dev.com/w/D3TexConv)

> I'm not a professional, but my aim is to write a simple model viewer first in Away3D framework, so it can run under Adobe Flash.
Use whatever you can. I am appreciate that!
## Post #30
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-07T13:18:59+00:00
- Post Title: Re: Diablo III .app

So it's sure, that we will have all the models in .obj + .tex files.

I'm just asking, cause Away 3D supports almost all major model formats (3ds, dae, obj, etc...), but Alternativa3D supports only .dae (collada) files.
## Post #31
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-10-07T13:24:11+00:00
- Post Title: Re: Diablo III .app

Due to the complexity and uniqueness of the file format a standalone viewer program is the best bet for this. I've worked on things like that before and will look into it when I have the time however I'm quite swamped with real life stuff atm
## Post #32
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-07T14:07:20+00:00
- Post Title: Re: Diablo III .app

What I will try to make in the next days is a simple item loader program, which runs in flash, and can be easily inserted to a site.

To make a complex model viewer, that loads a character, and puts all the armors and weapons on them ... hmm that's a different story.
## Post #33
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2011-10-07T14:28:27+00:00
- Post Title: Re: Diablo III .app

Not to mention the huge number of animations, different death looks etc...
## Post #34
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-07T15:24:31+00:00
- Post Title: Re: Diablo III .app

Correct ...

and the enchants on the weapons (e.g. ice, lightning, etc...)
## Post #35
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-08T13:08:21+00:00
- Post Title: Re: Diablo III .app

This is the action script code under Flex SDK and Away 3D Framework. After I compile it, it opens a 400 x 300 pc flash frame in a html file, and loads an .obj model.


> package
>
> {
>
> 	import away3d.containers.View3D;
>
> 	import away3d.events.LoaderEvent;
>
> 	import away3d.loaders.Loader3D;
>
> 	import away3d.loaders.parsers.Parsers;
>
> 
>
> 	import flash.display.Sprite;
>
> 	import flash.events.Event;
>
> 	import flash.net.URLRequest;
>
> 
>
> 	[SWF(width="400", height="300")]
>
> 	public class GettingStartedWithAway3D extends Sprite
>
> 	{
>
> 		private var _view : View3D;
>
> 		private var _loader : Loader3D;
>
> 
>
> 		public function GettingStartedWithAway3D()
>
> 		{
>
> 			_view = new View3D();
>
> 			_view.backgroundColor = 0xd7d7d7;
>
> 			_view.antiAlias = 4;
>
> 
>
> 			this.addChild(_view);
>
> 			this.addEventListener(Event.ENTER_FRAME, onEnterFrame);
>
> 
>
> 			Parsers.enableAllBundled();
>
> 
>
> 			_loader = new Loader3D();
>
> 			_loader.addEventListener(LoaderEvent.RESOURCE_COMPLETE, onResourceComplete);
>
> 			_loader.addEventListener(LoaderEvent.LOAD_ERROR, onLoadError);
>
> 			_loader.load( new URLRequest('Adria.obj') );
>
> 		}
>
> 
>
> 
>
> 		private function onResourceComplete(ev : LoaderEvent) : void
>
> 		{
>
> 			_loader.removeEventListener(LoaderEvent.RESOURCE_COMPLETE, onResourceComplete);
>
> 			_loader.removeEventListener(LoaderEvent.LOAD_ERROR, onLoadError);
>
> 			_view.scene.addChild(_loader);
>
> 		}
>
> 
>
> 
>
> 		private function onLoadError(ev : LoaderEvent) : void
>
> 		{
>
> 			trace('Could not find', ev.url);
>
> 			_loader.removeEventListener(LoaderEvent.RESOURCE_COMPLETE, onResourceComplete);
>
> 			_loader.removeEventListener(LoaderEvent.LOAD_ERROR, onLoadError);
>
> 			_loader = null;
>
> 		}
>
> 
>
> 
>
> 		private function onEnterFrame(ev : Event) : void
>
> 		{
>
> 			_loader.rotationY = stage.mouseX - stage.stageWidth/2;
>
> 			_view.camera.y = 3 * (stage.mouseY - stage.stageHeight/2);
>
> 			_view.camera.lookAt(_loader.position);
>
> 
>
> 			_view.render();
>
> 		}
>
> 	}
>
> }

The problem is the following:

it loads the some obj files, but when I try it with the Diablo 3 models (Adria.obj or Cain.obj) you cannot see anything.
Is there anyone who is expert in Away 3D  and / or modelling?
## Post #36
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-08T13:44:13+00:00
- Post Title: Re: Diablo III .app

Don't know about Away 3D but I imported Adria model to Maya without any problems.
## Post #37
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-08T14:21:28+00:00
- Post Title: Re: Diablo III .app

GLC player also opened Adria.obj properly...

Beside that how can I convert the .tex files with the D3TexConv.exe?
The wiki page writes drag and drop, but how?
## Post #38
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-08T15:33:40+00:00
- Post Title: Re: Diablo III .app

Drag the .tex file and drop it to D3TexConv.exe
## Post #39
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-08T16:11:33+00:00
- Post Title: Re: Diablo III .app

But how?

I run the .exe file and I get this:

> "We need a file(s) to work with!"

so where to drag and drop the .tex?
## Post #40
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-08T16:17:26+00:00
- Post Title: Re: Diablo III .app

lol, the problem was: Total commander.

Now I have the dds file.
## Post #41
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-08T21:48:07+00:00
- Post Title: Re: Diablo III .app

> Reply from npd2006
>
> Don't know about Away 3D but I imported Adria model to Maya without any problems.

3DS Max 2012 cannot open the ardia.obj.

These are the files I have in one folder:

adria.obj
adria_diff_atlas.txt
adria_spec_atlas.tct
adria_A_diff.dds
adria_A_spec.dds

When I try to import the .obj in +DS Max, I have an error meassage: an mtl file is missing, and two others as well. What else is needed to load the complete model?
## Post #42
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-09T04:18:02+00:00
- Post Title: Re: Diablo III .app

> 3DS Max 2012 cannot open the ardia.obj.
I have same tissue.
You can open it in Maya or Deep Exploration, then export to obj and you can import it to Max (but why don't use maya ?)
File .mtl looks like a header of .obj . It has no .mtl because of the template. I think it's not hard to create one. But it is not important.
## Post #43
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-09T07:02:24+00:00
- Post Title: Re: Diablo III .app

Arghhh ... so 3DS Max cannot open an .obj file, which Maya can. I thought .obj is a standard o_O

Question:

- so which files do I need to see a complete model? (so the dds and the obj is needed, and that's all?)
- I would be glad, if I could find a format, which contains the model and the texture as well in one file.
- do you know a crack for Maya?
## Post #44
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-09T10:39:27+00:00
- Post Title: Re: Diablo III .app

In the standard obj file format you require 3 files, the .obj file, a material file that links the textures with the obj file and the texture file
but
in this case all you need is the obj file and the texture file(s) since we didn't figure out the material file yet. 
So the adria.obj  file requires the Adria_A_diff.dss and the Adria_A_spec.dds file. both files cannot be linked to the obj file when converting from the original .app file (yet) so you need to do this manually

T.
## Post #45
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-09T11:11:02+00:00
- Post Title: Re: Diablo III .app

Ok, it's getting clear then.

For ex.: GLC Player can open the adria.obj, and I see the model without textures.

But both 3DS Max and Maya are not capable to open it, or are they? Perhaps I fucked up something during the importing process.
## Post #46
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-09T11:24:51+00:00
- Post Title: Re: Diablo III .app

Check out this thread

Everything you need 

[viewtopic.php?f=10&t=7320&hilit=010&start=90](http://forum.xentax.com/viewtopic.php?f=10&t=7320&hilit=010&start=90)

T.
## Post #47
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-09T19:24:37+00:00
- Post Title: Re: Diablo III .app

I know that thread, I was commenting in it.

But the models still cannot be loaded in the Maya or 3DS Max.

1) I extracted an .obj file of a weapon with the MQL editor.
2) Imported it to Maya, and the result was: 3-4 lines in the screen, and even not a poligon.

The same happened with 3DS Max.

I wonder how can I load a complete weapon model with textures ... ahhhhhh
## Post #48
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-09T21:11:21+00:00
- Post Title: Re: Diablo III .app

what is the model you are talking about ?

T.
## Post #49
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-10T02:35:16+00:00
- Post Title: Re: Diablo III .app

> But the models still cannot be loaded in the Maya or 3DS Max.
Did you miss something?

I imported them to Maya without any problem. I am using Maya 2011 32 bit.




This is Leoric model I imported it to Maya then export to obj then import to 3ds max. (I can't import it directly to 3ds max, it will become melt down). Everything is fine.
## Post #50
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-10T08:50:09+00:00
- Post Title: Re: Diablo III .app

Same result for me in 3DS Max 2009 / 2010

 

T.
## Post #51
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-10T20:28:02+00:00
- Post Title: Re: Diablo III .app

Hey Guys,

nice pics.

Could you be so kind to describe what did I fuck up? 

1) So I use this: MPQ Editor
2) I go to the folder, where I find Adria.app for example
3) Right click on the file --> extract
4) Now I have the Adria.app
5) I run the converter on the app file, and I receive an Adria.obj

2nd phase

6) I don't remember how I got the .tex file
7) using the text converter.exe --> I got the .dds file, but I also received other files, like .txt and so on.

So which files do I need to be able to open the proper file in Maya?

(see attached pic)

Thanks in advance!
[Untitled-1.jpg](https://xentaxbackup.github.io/file/4762_Untitled-1.jpg)
## Post #52
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-11T05:11:08+00:00
- Post Title: Re: Diablo III .app

> So which files do I need to be able to open the proper file in Maya?

1. For the model:  File -> Import -> Choose file .obj to import to Maya. If you can't import obj to Maya, send me your .obj file.
(example: Adria.obj)
2. For the material: Windows -> Rendering Editor -> Hypershade -> Drag and Drop whatever shader you want to the working area (I usually use Phong shader)-> Double click on the shader to open its attribute -> Open the Color Map (small checker beside Color)-> Choose your .dds file -> Assign shader to object.
(example: Adria_A_diff.dds)

files .txt are just for testing purpose. 

PS: If There's any error, screenshot and post here.
## Post #53
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-11T06:26:19+00:00
- Post Title: Re: Diablo III .app

Hello everyone,
For people having problems with importing models into 3D Studio theres one quick solution:
1) Download Blender (20Mb, Freeware)
2) Import *.obj into Blender
3) Export *.fbx
4) Import *.fbx to 3D Studio
5) ???
6) Profit

I also wonder, how does armor (chest,gloves,boots,legs) model choisen by game engine for HVY/LHT/MED models, is it only one part of model (but how its selected?) or a full model?
i.e. how to determine what model of Monk to use for Chest A aswell Texture.
## Post #54
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-11T08:20:16+00:00
- Post Title: Re: Diablo III .app

> 1) Download Blender (20Mb, Freeware)
>
> 2) Import *.obj into Blender
>
> 3) Export *.fbx
>
> 4) Import *.fbx to 3D Studio
>
> 5) ???
>
> 6) Profit
Great news for Maya user: You are going shortest path   

> also wonder, how does armor (chest,gloves,boots,legs) model choisen by game engine for HVY/LHT/MED models, is it only one part of model (but how its selected?) or a full model?
>
> i.e. how to determine what model of Monk to use for Chest A aswell Texture.

chest/gloves/boots/legs are objects in one files. I meant they are multiple objects in one package .app. They are not naturally merge together in one object. It's merged because of the algorithm of the .app - exporter. That's why we need a multiple mesh exporter.
I guess each part has the ID that can use for choice in game. In same way, textures can assign to the correct parts.
## Post #55
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-11T08:34:08+00:00
- Post Title: Re: Diablo III .app

> 1. For the model: File -> Import -> Choose file .obj to import to Maya. If you can't import obj to Maya, send me your .obj file.
>
> (example: Adria.obj)
>
> 2. For the material: Windows -> Rendering Editor -> Hypershade -> Drag and Drop whatever shader you want to the working area (I usually use Phong shader)-> Double click on the shader to open its attribute -> Open the Color Map (small checker beside Color)-> Choose your .dds file -> Assign shader to object.
>
> (example: Adria_A_diff.dds)
>
> 
>
> files .txt are just for testing purpose.
>
> 
>
> PS: If There's any error, screenshot and post here.

OK, thanks, I will send you the adria.obj in the evening.
## Post #56
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-12T18:54:07+00:00
- Post Title: Re: Diablo III .app

Evening!

When I import the ardia.obj to Maya, it writes this in the output window:

> mental ray for Maya 2012 
>
> mental ray: version 3.9.1.36, Feb  2 2011, revision 138829
>
> Wrong vertex normal index 1 in OBJ file line 595

I've attached the file, so NPD2006 could you check it please.

Also this is a print screen about the model, and how it looks after importing it to Maya.
[adria_maya.jpg](https://xentaxbackup.github.io/file/4767_adria_maya.jpg)
## Post #57
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-12T18:54:48+00:00
- Post Title: Re: Diablo III .app

As you can only attach one file ... here is the adria.obj
[Adria.rar](https://xentaxbackup.github.io/file/4768_Adria.rar)
## Post #58
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-12T19:10:16+00:00
- Post Title: Re: Diablo III .app

Hmm this Blender opens it ... how can I add the textures?

But this Maya problem should be solved still, as I tink that's why I cannot load it to the flash model viewer ...
[adria_blender.jpg](https://xentaxbackup.github.io/file/4769_adria_blender.jpg)
## Post #59
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-12T19:15:55+00:00
- Post Title: Re: Diablo III .app

After exporting the adria.obj from Blender --> Maya opens it, so what I need now is to be able to add textures...

and to find a solution to use a format which contains the textures as well and then I don't have to load the textures separately in the model viewer.
## Post #60
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-13T03:16:32+00:00
- Post Title: Re: Diablo III .app

The problem is Monguron's Adria.obj doesn't have vertex normal. Most of 3D software required vertex has vertex geometry (v), vertex texture (vt) and vertex normal (vn). Fortunately, Blender doesn't require vertex normal to display the mesh.
The reason is TaylorMouse used Falo's template to make a converter, which is not complete yet. I am using BoyC's template, which is fixed it. 
Check the attachments, there are 2 version of Adria.obj using 2 templates. Use notepad to open it.
Look at this picture:


So, TaylorMouse, please update your converter. Thank you!
[Adria compare.rar](https://xentaxbackup.github.io/file/4773_Adria compare.rar)
## Post #61
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-13T08:02:55+00:00
- Post Title: Re: Diablo III .app

Thanks for the info.

Could you please attach BoyC's .exe? So converting the .app files with his program will generate proper .obj files, which we can import to Maya / Blender etc ...

About the textures: so how can I attach them to the meshes? (I'm completely noob related to Maya, Blender, etc...)
In what extension should they exist (.dds, .tga, .tex, etc...)? As far as I know, we also have to convert the tex files to dds or what...
## Post #62
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-13T10:37:59+00:00
- Post Title: Re: Diablo III .app

> ould you please attach BoyC's .exe? So converting the .app files with his program will generate proper .obj files, which we can import to Maya / Blender etc ...
It's not a .exe file. It's a 010 editor template. If you know how to compile it to the .exe file, please do it.

> //--------------------------------------
>
> //--- 010 Editor v3.2.1 Binary Template
>
> //
>
> // File: Diablo 3 appearance file template
>
> // Author: BoyC
>
> // Revision: v0.37
>
> // Purpose: Analyzing 3D data in Diablo 3
>
> //--------------------------------------
>
> 
>
> local unsigned int vxcnt=0;
>
> local unsigned int LookCount=0;
>
> 
>
> struct ChunkData
>
> {
>
>     unsigned int Count<bgcolor=0xff00ff>;
>
>     unsigned int Offset<format=hex,bgcolor=0xff00ff>;
>
>     unsigned int Size<bgcolor=0xff00ff>;
>
> };
>
> 
>
> struct ChunkHeader
>
> {
>
>     unsigned int h[4];
>
> };
>
> 
>
> struct BONEDATA //size = 68
>
> {
>
>     unsigned int unk1[4];
>
>     float unk2[3];
>
>     unsigned int unk[3];
>
>     float unk4[7];
>
> };
>
> 
>
> struct BONE //size = 236
>
> {
>
>     char Name[64];
>
>     int ParentID;
>
>     float unk2[34]; //two matrices plus extra
>
>     ChunkData UnkChunk;
>
>     unsigned int unk[4];
>
>     int unk3;
>
>     Printf("# Bone: %s\n",Name);
>
> 
>
>     local int pos=FTell();
>
>     FSeek(UnkChunk.Offset+16);
>
> 
>
>     if (UnkChunk.Offset)
>
>     {
>
>         struct
>
>         {
>
>             BONEDATA bonedata[UnkChunk.Count]<optimize=false>;
>
>         } bonedata<bgcolor=0x00f0a0,comment="Unknown purpose bone data">;       
>
>     }
>
> 
>
>     FSeek(pos);
>
> };
>
> 
>
> struct VERTEX //size = 44
>
> {
>
>     float x,y,z;
>
>     unsigned char nx,ny,nz,nw;
>
>     int unk3,unk4;
>
>     unsigned short u,v;
>
>     unsigned int unk1;
>
>     char tx,ty,tz,tw;
>
>     char bx,by,bz,bw;
>
>     unsigned int unk2;
>
> 
>
>     //obj export part
>
>     /**/
>
>     local float ru=u,rv=v,rnx=nx,rny=ny,rnz=nz;
>
>     ru=(ru-32767)/512.0f;
>
>     rv=1-(rv-32767)/512.0f;
>
>     rnx=(rnx-127)/127.0f;
>
>     rny=(rny-127)/127.0f;
>
>     rnz=(rnz-127)/127.0f;
>
> 
>
>     Printf("v %f %f %f\n",x,y,z);
>
>     Printf("vt %f %f\n",ru,rv);   
>
>     Printf("vn %f %f %f\n",rnx,rny,rnz);/**/
>
> };
>
> 
>
> struct TRIINDICES
>
> {
>
>     unsigned short a,b,c;
>
> 
>
>     //obj export part
>
>     Printf("f %d/%d/%d %d/%d/%d %d/%d/%d\n",vxcnt+a+1,vxcnt+a+1,vxcnt+a+1,vxcnt+b+1,vxcnt+b+1,vxcnt+b+1,vxcnt+c+1,vxcnt+c+1,vxcnt+c+1);
>
> }; //complete
>
> 
>
> struct BLENDWEIGHT
>
> {
>
>     int BoneID;
>
>     float BoneWeight;
>
> }; //complete
>
> 
>
> struct BLENDDATA //size = 24
>
> {
>
>     BLENDWEIGHT Weights[3]<optimize=false>;
>
> }; //complete
>
> 
>
> struct LOOKDATA //size = 248
>
> {
>
>     unsigned int Five;
>
>     int MinusOne;
>
>     unsigned int DataOffset1<format=hex>;
>
>     unsigned int DataSize1;
>
>     unsigned int unk[3];
>
>     float Matrix[16];
>
>     unsigned int unk2[2];
>
>     unsigned int DataOffset2<format=hex>;
>
>     unsigned int DataSize2;
>
>     unsigned int unk3[35];
>
> };
>
> 
>
> struct SUBOBJECT //size = 140
>
> {
>
>     char Name[128];
>
>     unsigned int Offset,Size,Zero;
>
> 
>
>     local int pos=FTell();
>
>     FSeek(Offset+16);
>
> 
>
>     struct
>
>     {
>
>         LOOKDATA lookdata[LookCount]<optimize=false>;
>
>     } LookDataList<bgcolor=0x00a0f0,comment="Look Descriptors">;       
>
> 
>
>     FSeek(pos);
>
> };
>
> 
>
> struct MESH //size = 372
>
> {
>
>     int unk1;
>
>     ChunkData VertexChunk; //vertex size = 44
>
>     ChunkData WeightChunk; //weight size = 24
>
>     int Zero1;
>
>     ChunkData IndexChunk; // 16bit index buffer for a triangle list
>
>     ChunkData UnknownChunk; // points to an array of chunkdatas, could be anim
>
>     int unk5[4];
>
>     char SubObjectName[128];
>
>     char MeshName[128];
>
>     float funk1[6]; //bounding box?
>
>     unsigned int Zero2;
>
>     unsigned int unk[4];
>
> 
>
>     Printf("# unk1: %4d vxcount: %4d\n",unk1,VertexChunk.Count);
>
>     Printf("# mesh %s is part of subobject %s\n",MeshName,SubObjectName);
>
> 
>
>     local unsigned int Pos=FTell();
>
> 
>
>     if (VertexChunk.Offset)
>
>     {
>
>         FSeek(VertexChunk.Offset);
>
>         struct
>
>         {
>
>             ChunkHeader ch;
>
>             VERTEX vx[VertexChunk.Count]<optimize=false>;
>
>         } Vertices;       
>
>     }
>
> 
>
>     if (WeightChunk.Offset)
>
>     {
>
>         FSeek(WeightChunk.Offset);
>
>         struct
>
>         {
>
>             ChunkHeader ch;
>
>             BLENDDATA w[VertexChunk.Count]<optimize=false>;
>
>         } BlendWeights;       
>
>     }
>
> 
>
>     if (IndexChunk.Offset)
>
>     {
>
>         FSeek(IndexChunk.Offset);
>
>         struct
>
>         {
>
>             ChunkHeader ch;
>
>             TRIINDICES w[IndexChunk.Count/3]<optimize=false>;
>
>         } Triangles;       
>
>     }
>
> 
>
>     FSeek(Pos);
>
>     vxcnt+=VertexChunk.Count;
>
> };
>
> 
>
> struct HARDPOINT //size = 96
>
> { 
>
>     char Name[64];
>
>     int ParentBone;
>
>     float qx,qy,qz,qw; //rotation as a quaternion
>
>     float x,y,z; //position
>
> };
>
> 
>
> struct COLLISIONOBJ //size = 104
>
> {
>
>     unsigned int x[26];
>
> };
>
> 
>
> struct NAME
>
> {
>
>     char Name[64];
>
> };
>
> 
>
> struct
>
> {
>
>     unsigned int DEADBEEF[8];
>
>     unsigned int Counter1;
>
> 
>
>     ChunkData BoneChunk; // size = 236
>
> 
>
>     FSeek(FTell()+30*4);
>
> 
>
>     ChunkData MeshChunk; // size = 372
>
> 
>
>     FSeek(FTell()+9*4);
>
> 
>
>     float FloatAray1[4]; //bounding sphere?
>
> 
>
>     ChunkData CollisionChunk; // size = 104
>
> 
>
>     FSeek(FTell()+3*4);
>
> 
>
>     ChunkData HPChunk; // size = 96
>
> 
>
>     FSeek(FTell()+5*4);
>
> 
>
>     float One;
>
>     FSeek(FTell()+6*4);
>
> 
>
>     ChunkData UnkChunk1;
>
> 
>
>     FSeek(FTell()+4);
>
> 
>
>     ChunkData UnkChunk2;
>
> 
>
>     FSeek(FTell()+4);
>
> 
>
>     ChunkData UnkChunk3;
>
> 
>
>     FSeek(FTell()+8);
>
> 
>
>     float FloatArray2[6]; //bounding box?
>
> 
>
>     FSeek(FTell()+10*4);
>
> 
>
>     char xobject[256];
>
>     char xobjectpath[256];
>
>     char xmesh[256];
>
>     char xmeshpath[256];
>
> 
>
>     FSeek(FTell()+4*4);
>
> 
>
>     unsigned int LookCnt;
>
>     LookCount=LookCnt;
>
> 
>
>     ChunkData SubObjectChunk; // size = 140
>
> 
>
>     FSeek(FTell()+4);
>
> 
>
>     ChunkData LookNameChunk; // size = 64 count = Counter1
>
> 
>
>     FSeek(FTell()+18*4);
>
> 
>
>     //previously referenced data starts here, header size is 0x628h
>
> 
>
>     Printf("# Bone Count: %d\n",BoneChunk.Count);
>
>     Printf("# Mesh Count: %d\n",MeshChunk.Count);
>
> 
>
> 
>
>     if (BoneChunk.Offset)
>
>     {
>
>         FSeek(BoneChunk.Offset+16);
>
>         struct
>
>         {
>
>             //ChunkHeader ch;
>
>             BONE bone[BoneChunk.Count]<optimize=false>;
>
>         } Bones<bgcolor=0xa0a0a0,comment="Bone data">;
>
>     }
>
> 
>
>     if (MeshChunk.Offset)
>
>     {
>
>         FSeek(MeshChunk.Offset+16);
>
>         struct
>
>         {
>
>             //ChunkHeader ch;
>
>             MESH mesh[MeshChunk.Count]<optimize=false>;
>
>         } Models<bgcolor=0xb0f0b0,comment="Model data">;       
>
>     }
>
> 
>
>     if (SubObjectChunk.Offset)
>
>     {
>
>         FSeek(SubObjectChunk.Offset+16);
>
>         struct
>
>         {
>
>             //ChunkHeader ch;
>
>             SUBOBJECT group[SubObjectChunk.Count]<optimize=false>;
>
>         } SubObjects<bgcolor=0xc0c0f0,comment="SubObjects">;       
>
>     }
>
> 
>
>     if (HPChunk.Offset)
>
>     {
>
>         FSeek(HPChunk.Offset+16);
>
>         struct
>
>         {
>
>             //ChunkHeader ch;
>
>             HARDPOINT hardpoint[HPChunk.Count]<optimize=false>;
>
>         } HardPoints<bgcolor=0xd0f0f0,comment="These are hardpoints where other models can be attached to this one">;       
>
>     }
>
> 
>
>     if (CollisionChunk.Offset)
>
>     {
>
>         FSeek(CollisionChunk.Offset+16);
>
>         struct
>
>         {
>
>             //ChunkHeader ch;
>
>             COLLISIONOBJ Collisions[CollisionChunk.Count]<optimize=false>;
>
>         } CollisionObjects<bgcolor=0xf0e0f0,comment="Seems to be collision mesh data">;       
>
>     }
>
> 
>
>     if (LookNameChunk.Offset)
>
>     {
>
>         FSeek(LookNameChunk.Offset+16);
>
>         struct
>
>         {
>
>             NAME Name[LookCount]<optimize=false>;
>
>         } LookNames<bgcolor=0xf0a0a0,comment="Look Names">;               
>
>     }
>
> 
>
> 
>
> } HEADER<bgcolor=0xf0f000>;

> About the textures: so how can I attach them to the meshes? (I'm completely noob related to Maya, Blender, etc...)
About how to attach texture to meshes, I think it's better if you search youtube : Maya Hypershade, Maya Basic,...some kind like that. Very easy to do but difficult to explain.

> In what extension should they exist (.dds, .tga, .tex, etc...)? As far as I know, we also have to convert the tex files to dds or what...
Engine games use .dds, 
3D software use .tga , .psd.... 
Diablo 3 use .tex
When exported they are naturally .dds . Why don't use .dds? 
If you still don't want to use .dds, use photoshop with dds plugin to convert.
## Post #63
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-13T12:05:25+00:00
- Post Title: Re: Diablo III .app

> It's not a .exe file. It's a 010 editor template. If you know how to compile it to the .exe file, please do it.
OK, I don't know how to compile it. Any idea, or should I check on google?

When I export the adria.obj from Blender, it makes an adria.obj and an adria.mtl file. Do we really need this .mtl file, or the .obj + .dds are enough to display a model properly?

The other question is: is there a possibility to export an .obj file from Blender or Maya, which contains the texture as well, and then I don't have to work with two files per model, only with one.

(for ex.: the .awd format can contain a model + the texture)
## Post #64
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-13T12:14:58+00:00
- Post Title: Re: Diablo III .app

> OK, I don't know how to compile it. Any idea, or should I check on google?
Open .app in 010 template. Create new template, paste Boy's template in there. Press F5 to compile .app with template. Copy the output (accept for the first line) to a text file then save as .obj. That's the way I create obj. 
But how to make a .exe converter, ask TaylorMouse. I have no Idea about that.

> When I export the adria.obj from Blender, it makes an adria.obj and an adria.mtl file. Do we really need this .mtl file, or the .obj + .dds are enough to display a model properly?
.mtl file is initialShadingGroup, just .obj+.dds are enough.

> The other question is: is there a possibility to export an .obj file from Blender or Maya, which contains the texture as well, and then I don't have to work with two files per model, only with one.
There is no way to contain texture in .obj.
## Post #65
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-13T14:33:57+00:00
- Post Title: Re: Diablo III .app

I am appreciate if TaylorMouse post the source C# of the AppConverter here.
## Post #66
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-13T16:49:29+00:00
- Post Title: Re: Diablo III .app

Hmm

actual topics:

Good news: I could load your AdriaBoyC file into the flash (without textures yet).

Problems:

1) The Adria BoyC.obj is more than 200 KBytes
after I import it to Blender, and export it again it becomes 150 KBytes. What's happening? Why does it loose info.
The exported file cannot be loaded by my flash application, so it seems it looses the vnormals numbers again.

2) I was checking Maya and Blender tutorials on the net, but there was none, which showed how to import and attach the 2 .dds files to the meshes. Also it's still not sure I can load .dds files in Away3D (the flash library). So I will need to convert them to .png or .jpg.

3) When I open the obj in Maya, and then I try to export it there is no .obj option, just some other formats. Do I have to install a plugin for that?
## Post #67
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-13T17:20:41+00:00
- Post Title: Re: Diablo III .app

> so it seems it looses the vnormals numbers again.
it's true.

> I was checking Maya and Blender tutorials on the net, but there was none, which showed how to import and attach the 2 .dds files to the meshes. Also it's still not sure I can load .dds files in Away3D (the flash library). So I will need to convert them to .png or .jpg.
If we can contact directly, I can use team viewer to do it for you.

> 3) When I open the obj in Maya, and then I try to export it there is no .obj option, just some other formats. Do I have to install a plugin for that?
Maya is not naturally support import, export .obj. You need to go to Windows -> Plugin Manager -> Check the .obj export
## Post #68
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-14T05:24:23+00:00
- Post Title: Re: Diablo III .app

> Reply from Monguron
>
> 
1) The Adria BoyC.obj is more than 200 KBytes
after I import it to Blender, and export it again it becomes 150 KBytes. What's happening? Why does it loose info.
The exported file cannot be loaded by my flash application, so it seems it looses the vnormals numbers again.

read this : [http://en.wikipedia.org/wiki/Wavefront_.obj_file](http://en.wikipedia.org/wiki/Wavefront_.obj_file) maybe this explains why the size can vary,
it is because 3D software such as Blender/ Max / Maya /... probably do not use the same export, since there are more then  1 way to save to an obj file. 
If your read the wiki, you'll see what I mean under the section Vertex/texture-coordinate/normal

Also the textures are not loaded at import time because there is no mtl file written in the process.

The .obj file references a .mtl file which contains the paths and names of the actual used textures.

Hope this helps

T
## Post #69
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-14T09:27:14+00:00
- Post Title: Re: Diablo III .app

Hey Taylor,

So the .mtl is always needed, as it tells the eingine how to apply the textures to the meshes.

If I'm right, this means we need the .obj + .dds textures + .mtl to properly load/show a model in an application.
## Post #70
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-14T12:47:46+00:00
- Post Title: Re: Diablo III .app

2 Monguron:
Yeah you do, but problem is, theres no .mtl for now, i mean theres one but noone hckd it yet.
So the only way to do that, is redo all 4400 .app files 
Well, are you after showing theese models via some 3rd party 3D engine am i right ?
## Post #71
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-14T13:13:49+00:00
- Post Title: Re: Diablo III .app

Hey Insane,

The guys (NPD2006 and Taylor) could open the .obj files, and could attach the textures (.dds) somehow in Maya / Blender.

I could only open the .obj files, so I have basic problems with using Maya and Blender 
I need to understand the basic concept of the texturing methods to be able to make a 3rd party engine.

About the engine:

Check out AWAY3D ([http://www.away3d.com](http://www.away3d.com))
This is an action script library, based on Adobe Flex SDK, and with it we can open Diablo3 3D models, rotate them, zoom, etc... in Flash, so it can be used on the internet without any plugin needed (only the latest Flash Player 11 is needed to run the Away3D 4.0 files).

Can you support somehow? Are you prof. in 3D graphics and programming, cause I'm just a "hobby driver".
## Post #72
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-14T15:52:20+00:00
- Post Title: Re: Diablo III .app

> I need to understand the basic concept of the texturing methods to be able to make a 3rd party engine.

I have already told ya that!

This is the method to assign dds to obj in maya.

> 2. For the material: Windows -> Rendering Editor -> Hypershade -> Drag and Drop whatever shader you want to the working area (I usually use Phong shader)-> Double click on the shader to open its attribute -> Open the Color Map (small checker beside Color)-> Choose your .dds file -> Assign shader to object.
>
> (example: Adria_A_diff.dds)

> Can you support somehow? Are you prof. in 3D graphics and programming, cause I'm just a "hobby driver".
I am not a beginner in 3D graphics, but not a prof., too.  I know a little programming, enough to display a "Hello World" on the console. I really have no idea about AWAY3D or FLEX.
## Post #73
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-14T18:55:18+00:00
- Post Title: Re: Diablo III .app

> Reply from Monguron
>
> Hey Insane,

The guys (NPD2006 and Taylor) could open the .obj files, and could attach the textures (.dds) somehow in Maya / Blender.

I could only open the .obj files, so I have basic problems with using Maya and Blender 
I need to understand the basic concept of the texturing methods to be able to make a 3rd party engine.

About the engine:

Check out AWAY3D (http://www.away3d.com)
This is an action script library, based on Adobe Flex SDK, and with it we can open Diablo3 3D models, rotate them, zoom, etc... in Flash, so it can be used on the internet without any plugin needed (only the latest Flash Player 11 is needed to run the Away3D 4.0 files).. 

Can you support somehow? Are you prof. in 3D graphics and programming, cause I'm just a "hobby driver".

hey there, i am programmer. According to my knowledge of 3d flash frameworks its not that easy for a beginner in game.dev to make it work like an good application. its not hard to do so if you have some experiace, easier to do it in OGL o D3D for me, but i need a web and cba to do an j.applet  

you can just texture a model passing it a correct files, all the UV mapping already done by Blizz guys  texturing is probably an easiest part of all process, eve no shading required
## Post #74
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-14T20:35:06+00:00
- Post Title: Re: Diablo III .app

Hey,

I fonud some examples scripts (for ex. loading an .obj file + mapping, textures, etc...), and I could reach to load a .obj from Diablo3, but without any textures.

The application would be very basic, so it's enough if I can load the .obj + the textures in it, and then rotate and zoom the model.

As you are a porgrammer, what do you think, can we put the code together here, and when it's ready, then we have a Diablo3 model viewer.
The away3d framework makes a lot of thing easily (antialiasing, lighting, etc...), this whole thing I wrote only takes around 40-50 lines of code in actionscript with the away3d library.
## Post #75
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-14T23:01:17+00:00
- Post Title: Re: Diablo III .app

> Reply from Monguron
>
> Hey,

I fonud some examples scripts (for ex. loading an .obj file + mapping, textures, etc...), and I could reach to load a .obj from Diablo3, but without any textures.

The application would be very basic, so it's enough if I can load the .obj + the textures in it, and then rotate and zoom the model.

As you are a porgrammer, what do you think, can we put the code together here, and when it's ready, then we have a Diablo3 model viewer.
The away3d framework makes a lot of thing easily (antialiasing, lighting, etc...), this whole thing I wrote only takes around 40-50 lines of code in actionscript with the away3d library.
Whats the point ?
## Post #76
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-16T09:26:47+00:00
- Post Title: Re: Diablo III .app

This is a sample code in away3D:

> package
>
> {
>
> 	import away3d.containers.View3D;
>
> 	import away3d.debug.AwayStats;
>
> 	import away3d.entities.Mesh;
>
> 	import away3d.events.LoaderEvent;
>
> 	import away3d.lights.PointLight;
>
> 	import away3d.loaders.Loader3D;
>
> 	import away3d.loaders.misc.AssetLoaderContext;
>
> 	import away3d.loaders.parsers.OBJParser;
>
> 	import away3d.materials.BitmapMaterial;
>
> 	import away3d.materials.methods.BasicDiffuseMethod;
>
> 	import away3d.materials.methods.BasicSpecularMethod;
>
> 	import away3d.materials.methods.FresnelSpecularMethod;
>
> 	import away3d.materials.methods.SubsurfaceScatteringDiffuseMethod;
>
> 
>
> 	import flash.display.Sprite;
>
> 	import flash.display.StageAlign;
>
> 	import flash.display.StageScaleMode;
>
> 	import flash.events.Event;
>
> 	import flash.events.KeyboardEvent;
>
> 
>
> 	[SWF(width="1280", height="720", frameRate="60", backgroundColor="0x000000")]
>
> 	public class LoaderOBJTest extends Sprite
>
> 	{
>
> 		private var _view : View3D;
>
> 		private var _loader : Loader3D;
>
> 
>
> 		private var _light : PointLight;
>
> 
>
> 		[Embed(source="/../embeds/head/head.obj", mimeType="application/octet-stream")]
>
> 		private var OBJData : Class;
>
> 
>
> 		[Embed(source="/../embeds/head/Images/Map-COL.jpg")]
>
> 		private var Albedo : Class;
>
> 
>
> 		[Embed(source="/../embeds/head/Images/Map-spec.jpg")]
>
> 		private var Specular : Class;
>
> 
>
> 		[Embed(source="/../embeds/head/Images/Infinite-Level_02_Tangent_NoSmoothUV.jpg")]
>
> 		private var Normal : Class;
>
> 
>
> 		//signature variables
>
> 		private var Signature : Sprite;
>
> 
>
> 		//signature swf
>
> 		[Embed(source="/../embeds/signature_david_head.swf", symbol="Signature")]
>
> 		private var SignatureSwf : Class;
>
> 
>
> 		private var _camController : HoverDragController;
>
> 		private var _count : Number = 0;
>
> 		private var _subsurfaceMethod : SubsurfaceScatteringDiffuseMethod;
>
> 		private var _diffuseMethod : BasicDiffuseMethod;
>
> 		private var _material : BitmapMaterial;
>
> 		private var _fresnelMethod : FresnelSpecularMethod;
>
> 		private var _specularMethod : BasicSpecularMethod;
>
> 
>
> 		public function LoaderOBJTest()
>
> 		{
>
> 			_view = new View3D();
>
> 			_view.antiAlias = 4;
>
> 			this.addChild(_view);
>
> 
>
> 			Signature = Sprite(new SignatureSwf());
>
> 			Signature.y = stage.stageHeight - Signature.height;
>
> 
>
> 			addChild(Signature);
>
> 
>
> 			_light = new PointLight();
>
> 			_light.x = 15000;
>
> 			_light.z = 15000;
>
> 			_light.color = 0xffddbb;
>
> 			_view.scene.addChild(_light);
>
> 			_camController = new HoverDragController(_view.camera, stage);
>
> 			addChild(new AwayStats(_view));
>
> 			initMesh();
>
> 
>
> 			addEventListener(Event.ENTER_FRAME, onEnterFrame);
>
> 			stage.addEventListener(KeyboardEvent.KEY_UP, onKeyUp);
>
> 			stage.scaleMode = StageScaleMode.NO_SCALE;
>
> 			stage.align = StageAlign.TOP_LEFT;
>
> 			stage.addEventListener(Event.RESIZE, onStageResize);
>
> 		}
>
> 
>
> 		private function onStageResize(event : Event) : void
>
> 		{
>
> 			_view.width = stage.stageWidth;
>
> 			_view.height = stage.stageHeight;
>
> 
>
> 			Signature.y = stage.stageHeight - Signature.height;
>
> 		}
>
> 
>
> 		private function initMesh() : void
>
> 		{
>
> 			Loader3D.enableParser(OBJParser);
>
> 
>
> 			_loader = new Loader3D();
>
> 			_loader.addEventListener(LoaderEvent.RESOURCE_COMPLETE, onResourceComplete);
>
> 			_loader.parseData(OBJData, null, new AssetLoaderContext(false));
>
> 			_loader.y = -50;
>
> 			_view.scene.addChild(_loader);
>
> 
>
> 			_material = new BitmapMaterial(new Albedo().bitmapData);
>
> 			_subsurfaceMethod = new SubsurfaceScatteringDiffuseMethod(2048, 2);
>
> 			_diffuseMethod = new BasicDiffuseMethod();
>
> 			_fresnelMethod = new FresnelSpecularMethod(true);
>
> 			_specularMethod = new BasicSpecularMethod();
>
> 			_material.normalMap = new Normal().bitmapData;
>
> 			_material.specularMap = new Specular().bitmapData;
>
> 			_material.lights = [ _light ];
>
> 			_material.gloss = 10;
>
> 			_material.specular = 3;
>
> 			_material.ambientColor = 0x303040;
>
> 			_material.ambient = 1;
>
> 			_subsurfaceMethod.scatterColor = 0xff7733; //0xff9966;
>
> 			_subsurfaceMethod.scattering = .05;
>
> 			_subsurfaceMethod.translucency = 4;
>
> 			_material.diffuseMethod = _subsurfaceMethod;
>
> 			_material.specularMethod = _fresnelMethod;
>
> 		}
>
> 
>
> 		private function onResourceComplete(event : LoaderEvent) : void
>
> 		{
>
> 			var mesh : Mesh;
>
> 			for (var i : int = 0; i < _loader.numChildren; ++i) {
>
> 				mesh = Mesh(_loader.getChildAt(i));
>
> 				mesh.geometry.scale(100);
>
> 				mesh.material = _material
>
> 			}
>
> 		}
>
> 
>
> 		private function onKeyUp(event : KeyboardEvent) : void
>
> 		{
>
> 			_material.diffuseMethod = _material.diffuseMethod == _diffuseMethod ? _subsurfaceMethod : _diffuseMethod;
>
> //            _material.specularMethod = _material.specularMethod == _specularMethod? _fresnelMethod : _specularMethod;
>
> 		}
>
> 
>
> 		private function onEnterFrame(ev : Event) : void
>
> 		{
>
> 			_count += .003;
>
> //			_container.rotationY += .3;
>
> 
>
> 			_light.x = Math.sin(_count) * 150000;
>
> 			_light.y = 1000;
>
> 			_light.z = Math.cos(_count) * 150000;
>
> 
>
> 			_view.render();
>
> 		}
>
> 	}
>
> }

It opens an OBJ file, puts the layers, shaders, textures onto it, and then rotates a light around the object continuously.

We even need no light to add to the file.

Insane: do you have any idea (as a programmer), how to write a code, that is able to open the diablo 3 objects and attach the textures to them. Also the mtl file is needed to be linked somehow, but I have no clue at all.
## Post #77
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-16T16:49:43+00:00
- Post Title: Re: Diablo III .app

> Insane: do you have any idea (as a programmer), how to write a code, that is able to open the diablo 3 objects and attach the textures to them. Also the mtl file is needed to be linked somehow, but I have no clue at all.
Big problem of AWAY 3D is how to read directly from .app and .tex file.
## Post #78
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-16T17:13:38+00:00
- Post Title: Re: Diablo III .app

> Reply from Monguron
>
> This is a sample code in away3D:
It opens an OBJ file, puts the layers, shaders, textures onto it, and then rotates a light around the object continuously.
We even need no light to add to the file.
Insane: do you have any idea (as a programmer), how to write a code, that is able to open the diablo 3 objects and attach the textures to them. Also the mtl file is needed to be linked somehow, but I have no clue at all.
Nothing stops you from texturing it manualy and then feed to away3d.
Or you can write a .dll that reads/converts data from .app and than returns output to away3D core.
Problem is, no one knows SNOs for texture references, or hows its linked to .tex
## Post #79
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-17T11:13:23+00:00
- Post Title: Re: Diablo III .app

We don't have to read from .app files

We do everything as we did:

convert the .app --> we get the .obj (with proper vertexnormals), the .mtl and the .tex files
we convert the .tex to .jpg for example, and then the engine loads them.

I just don't know how to link the .jpg to the .mtl and the .obj in the program. And I didn't receive any answer in the away3D forum.
[http://away3d.com/forum/viewthread/1029/](http://away3d.com/forum/viewthread/1029/)

(so far I could only load an .obj without texture)


another thread regarding the topic:
[http://away3d.com/forum/viewthread/978/](http://away3d.com/forum/viewthread/978/)
## Post #80
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-17T14:09:39+00:00
- Post Title: Re: Diablo III .app

> We don't have to read from .app files
If you just want to read .obj and .jpg, don't wasting time for research diablo 3 data. Because it's general filetype, all 3D graphic software and engine can read it. They are not concern with diablo 3.
## Post #81
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-17T19:23:01+00:00
- Post Title: Re: Diablo III .app

> If you just want to read .obj and .jpg, don't wasting time for research diablo 3 data. Because it's general filetype, all 3D graphic software and engine can read it. They are not concern with diablo 3.

I don't really get what you mean.

If the engine cannot read the .dds, then it must be converted to a general format (e.g. jpg, png, etc...)
## Post #82
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-18T02:41:19+00:00
- Post Title: Re: Diablo III .app

> If the engine cannot read the .dds, then it must be converted to a general format (e.g. jpg, png, etc...)
We should find a way to solve that problem, if there is no way to do that, we need a better engine.

> I don't really get what you mean.
_ filetype .obj and .jpg, .dds are very regular, every 3D software can read it, example: maya, 3ds max, lightwave, blender,....
_ filetype .app and .tex are very special, because they only exist in diablo 3
_ The reason we need a converter is no software can read directly diablo 3 files. That's why we need a converter to convert diablo 3 filetype to regular filetype.
## Post #83
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2011-10-18T04:55:40+00:00
- Post Title: Re: Diablo III .app

get [http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads) and write plugin for it - easy ...
as alternative make temp dir => convert model in temp dir => show as yo wish

P.S. In D3 resources i found trDun_Torch.app WHERE its texture ? I search in mpq with Total Commander through wcx plugin keyword "torch" and no .tex found for this model ...
## Post #84
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-18T05:34:09+00:00
- Post Title: Re: Diablo III .app

> get http://oasis.xentax.com/index.php?content=downloads and write plugin for it - easy ...
>
> as alternative make temp dir => convert model in temp dir => show as yo wish
I'll check it. Did you write any plugin by using it?

> P.S. In D3 resources i found trDun_Torch.app WHERE its texture ? I search in mpq with Total Commander through wcx plugin keyword "torch" and no .tex found for this model ...
texture is in texture.mpq
## Post #85
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-18T06:48:49+00:00
- Post Title: Re: Diablo III .app

> Reply from Monguron
>
> 
Insane: do you have any idea (as a programmer), how to write a code, that is able to open the diablo 3 objects and attach the textures to them. Also the mtl file is needed to be linked somehow, but I have no clue at all.
Ofcourse i do, trivial task, either OpenGL/D3D or even more simplier in Away/Papervision 
I wonder, how you going to link .mtl file if its not exist ?  (as a hint)
You are after using this application for "commercial", e.g. using it out personal website, am i right ?
## Post #86
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2011-10-18T10:05:34+00:00
- Post Title: Re: Diablo III .app

> get http://oasis.xentax.com/index.php?content=downloads and write plugin for it - easy ...
>
> as alternative make temp dir => convert model in temp dir => show as yo wish
>
> I'll check it. Did you write any plugin by using it?
No, program archive come with plugins sources (pluginsource.zip) as example look on quakemd2 
strcpy_s(infOut->pluginDesc, 512, "Quake II MD2 format handler, by Dick.");


> P.S. In D3 resources i found trDun_Torch.app WHERE its texture ? I search in mpq with Total Commander through wcx plugin keyword "torch" and no .tex found for this model ...
>
> texture is in texture.mpq
please say filename for this model from texture.mpq i can't  find it ...
## Post #87
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-18T11:26:49+00:00
- Post Title: Re: Diablo III .app

> Ofcourse i do, trivial task, either OpenGL/D3D or even more simplier in Away/Papervision

For a 3d programmer it might be trivial  ... so you can extend/change the code I wrote in a previous post to load for example the adria.obj + the two textures into the flash framework (in away3D) 

> I wonder, how you going to link .mtl file if its not exist ?  (as a hint)

I saw a .mtl file in my folder, perhaps it was made after I exported the model from Blender. I don't remember.

> You are after using this application for "commercial", e.g. using it out personal website, am i right ?

Yes, I would use the flash in a website.
## Post #88
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-18T11:32:59+00:00
- Post Title: Re: Diablo III .app

> Reply from npd2006
>
> If the engine cannot read the .dds, then it must be converted to a general format (e.g. jpg, png, etc...)

We should find a way to solve that problem, if there is no way to do that, we need a better engine.
I don't really get what you mean.
_ filetype .obj and .jpg, .dds are very regular, every 3D software can read it, example: maya, 3ds max, lightwave, blender,....
_ filetype .app and .tex are very special, because they only exist in diablo 3
_ The reason we need a converter is no software can read directly diablo 3 files. That's why we need a converter to convert diablo 3 filetype to regular filetype.

I don't really see a chance to have an all-in-one program, that can convert the .app files internally and then load them.
So I'm quite sure we will need to convert the apps manually with the converter, and then we can load the .obj files in the "model viewer".
## Post #89
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2011-10-18T20:20:15+00:00
- Post Title: Re: Diablo III .app

fixed version

comare .obj with script output, almost identical ...
[d3app2obj.zip](https://xentaxbackup.github.io/file/4785_d3app2obj.zip)
## Post #90
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-19T04:15:28+00:00
- Post Title: Re: Diablo III .app

> fixed version
>
> 
>
> comare .obj with script output, almost identical ...

Please post the source code here.
## Post #91
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2011-10-19T06:18:14+00:00
- Post Title: Re: Diablo III .app

ppl, how to establish connection with model and textures for creating .mtl file ? 

2 TaylorMouse
for correct formatin decimal numbers witch any locale add this (i had comma separated digits - must be dot) and i think its be base problem with this converter ...

> CultureInfo newCInfo = (CultureInfo)Thread.CurrentThread.CurrentCulture.Clone();
>
> newCInfo.NumberFormat.NumberDecimalSeparator = ".";
>
> Thread.CurrentThread.CurrentCulture = newCInfo;

using System;
using System.Collections.Generic;
using System.Globalization;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading;

namespace d3app2obj
{
	public class Convert
	{
		// Methods
		public static string CharToString(char[] chars)
		{
			string str = "";
			for (int i = 0; i < chars.Length; i++)
			{
				if (chars == '\0')
				{
					return str;
				}
				str = str + chars.ToString();
			}
			return str;
		}

		public static void DiabloIIIAppToObj(string file)
		{
			CultureInfo newCInfo = (CultureInfo)Thread.CurrentThread.CurrentCulture.Clone();
			newCInfo.NumberFormat.NumberDecimalSeparator = ".";
			Thread.CurrentThread.CurrentCulture = newCInfo;


			string str = file.Substring(0, file.Length - 4) + ".obj";
			Console.WriteLine(string.Format("Writing OBJ data to {0}", str));
			int num = 0;
			int num2 = 0;
			long offset = 0L;
			using (TextWriter writer = new StreamWriter(str, false))
			{
				writer.WriteLine(string.Format("# Diablo 3 Appearance (.app) model file exported on {0}", DateTime.Now.ToString("yyyy/MM/ddThh:mm:ss")));
				writer.WriteLine("# Special thanks to Falo");
				writer.WriteLine("# Written in C#.NET by Taylor Mouse");
				writer.WriteLine();
				writer.WriteLine("mtllib default.mtl");
				writer.WriteLine();
				using (BinaryReader reader = new BinaryReader(File.Open(file, FileMode.Open)))
				{
					reader.ReadBytes(0x10);
					for (int i = 0; i < 5; i++)
					{
						reader.ReadUInt32();
					}
					int num5 = reader.ReadInt32();
					int num6 = reader.ReadInt32();
					reader.ReadInt32();
					for (int j = 0; j < 30; j++)
					{
						reader.ReadInt32();
					}
					int num8 = reader.ReadInt32();
					int num9 = reader.ReadInt32();
					reader.ReadInt32();
					writer.WriteLine(string.Format("# numMaterials: {0}", num8));
					writer.WriteLine(string.Format("# numBones: {0}", num5));
					writer.WriteLine("# ParentID\tBone");
					reader.BaseStream.Seek((long)(num6 + 0x10), SeekOrigin.Begin);
					for (int k = 0; k < num5; k++)
					{
						string str2 = CharToString(reader.ReadChars(0x40));
						int num11 = reader.ReadInt32();
						writer.WriteLine(string.Format("# {0}\t\t{1}", num11, str2));
						for (int n = 0; n < 0x22; n++)
						{
							reader.ReadSingle();
						}
						for (int num13 = 0; num13 < 8; num13++)
						{
							reader.ReadInt32();
						}
					}
					writer.WriteLine();
					reader.BaseStream.Seek((long)(num9 + 0x10), SeekOrigin.Begin);
					for (int m = 0; m < num8; m++)
					{
						reader.ReadInt32();
						int num15 = reader.ReadInt32();
						int num16 = reader.ReadInt32();
						reader.ReadInt32();
						reader.ReadInt32();
						int num17 = reader.ReadInt32();
						reader.ReadInt32();
						reader.ReadInt32();
						int num18 = reader.ReadInt32();
						int num19 = reader.ReadInt32();
						reader.ReadInt32();
						for (int num20 = 0; num20 < 7; num20++)
						{
							reader.ReadInt32();
						}
						string str3 = CharToString(reader.ReadChars(0x80));
						string str4 = CharToString(reader.ReadChars(0x80));
						for (int num21 = 0; num21 < 11; num21++)
						{
							reader.ReadSingle();
						}
						offset = reader.BaseStream.Position;
						writer.WriteLine(string.Format("# numVerts: {0}", num15));
						writer.WriteLine(string.Format("# numFaces: {0}", num18));
						reader.BaseStream.Seek((long)(num16 + 0x10), SeekOrigin.Begin);
						for (int num22 = 0; num22 < num15; num22++)
						{
							float num23 = reader.ReadSingle();
							float num24 = reader.ReadSingle();
							float num25 = reader.ReadSingle();

							float nx = reader.ReadByte();
							float ny = reader.ReadByte();
							float nz = reader.ReadByte();
							float nw = reader.ReadByte();

							// reader.ReadInt32();
							reader.ReadInt32();
							reader.ReadInt32();
							float u = reader.ReadUInt16();
							float v = reader.ReadUInt16();


							// writer.WriteLine(string.Format("#debug {0:0.000000} {1:0.000000}", u, v));
							u = (u - 32767) / 512.0f;
							v = 1 - (v - 32767) / 512.0f;


							// ushort num26 = reader.ReadUInt16();
							// ushort num27 = reader.ReadUInt16();
							reader.ReadInt32();
							reader.ReadInt32();
							reader.ReadInt32();
							reader.ReadInt32();


//							float num28 = num26;
//							float num29 = num27;
//							num28 -= 32767f;
//							num29 -= 32767f;
//							num28 /= 512f;
//							num29 /= 512f;
//							num29 *= -1f;
//							num29++;							

							writer.WriteLine(string.Format("v {0:0.000000} {1:0.000000} {2:0.000000}", num23, num24, num25));

//							writer.WriteLine(string.Format("vt {0} {1}", num28, num29));
							writer.WriteLine(string.Format("vt {0:0.000000} {1:0.000000}", u, v));

							nx = (nx - 127) / 127.0f;
							ny = (ny - 127) / 127.0f;
							nz = (nz - 127) / 127.0f;

							writer.WriteLine(string.Format("vn {0:0.000000} {1:0.000000} {2:0.000000}", nx, ny, nz));
						}
						reader.BaseStream.Seek((long)(num17 + 0x10), SeekOrigin.Begin);
						for (int num30 = 0; num30 < num15; num30++)
						{
							reader.ReadInt32();
							reader.ReadSingle();
							reader.ReadInt32();
							reader.ReadSingle();
							reader.ReadInt32();
							reader.ReadSingle();
						}
						writer.WriteLine(string.Format("g {0}", str3));
						writer.WriteLine(string.Format("usemtl {0}", str4));
						reader.BaseStream.Seek((long)(num19 + 0x10), SeekOrigin.Begin);
						for (int num31 = 0; num31 < (num18 / 3); num31++)
						{
							ushort num32 = reader.ReadUInt16();
							ushort num33 = reader.ReadUInt16();
							ushort num34 = reader.ReadUInt16();
							writer.WriteLine(string.Format("f {0}/{1}/{2} {3}/{4}/{5} {6}/{6}/{7}", new object[] { (num + num32) + 1, (num + num32) + 1, (num + num32) + 1, (num + num33) + 1, (num + num33) + 1, (num + num33) + 1, (num + num34) + 1, (num + num34) + 1, (num + num34) + 1 }));
						}
						num += num15;
						num2++;
						reader.BaseStream.Seek(offset, SeekOrigin.Begin);
					}
					reader.Close();
				}
				writer.Close();
			}
		}
	}




	class program
	{
		static void Main(string[] args)
		{
			if(args.Length == 0)
			{
				Console.Write(
				              "Written by Taylor Mouse\nOriginal Script by Falo\nUse with blizzards Diablo III 3D Models\nExtract the .app from the Diablo III MPQ files\nAll models and assets are registered trademarks from Blizzard Ltd. all rights reserved\nThis tool is thereby for studying purposes only and may not be sold!\n\nUsage:\n\n-d [directory] :each valid .app file in the directory will be converted to a .obj file\n-f [filename]  :converts the appearance file .app to a .obj file\n\n(c)2011");
			}
			else
			{
				for(int i = 0; i < args.Length; i++)
				{
					if(args == "-d")
					{
						string path = args[i + 1];
						if(Directory.Exists(path))
						{
							string[] files = Directory.GetFiles(path, "*.app");
							for(int j = 0; j < files.Length; j++)
							{
								if(File.Exists(files[j]))
								{
									Console.WriteLine(string.Format("Converting {0}", files[j]));
									try
									{
										Convert.DiabloIIIAppToObj(files[j]);
									}
									catch(Exception exception)
									{
										Console.WriteLine(exception);
									}
								}
							}
							return;
						}
						Console.WriteLine(string.Format("Directory {0} does not exist!", path));
						return;
					}
					if(args == "-f")
					{
						string str2 = args[i + 1];
						if(File.Exists(str2))
						{
							Console.WriteLine(string.Format("Converting {0}", str2));
							try
							{
								Convert.DiabloIIIAppToObj(str2);
							}
							catch(Exception exception2)
							{
								Console.WriteLine(exception2);
							}
						}
						break;
					}
				}
			}
		}
	}
}
## Post #92
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-19T18:07:26+00:00
- Post Title: Re: Diablo III .app

I would say, we already should be capable to make this:

[http://www.diablowiki.com/Skeleton_Arch ... blo_III%29](http://www.diablowiki.com/Skeleton_Archer_%28Diablo_III%29)

1) as we have a converter, that makes .obj + .tex from app files
2) then we can convert the .tex to .dds
3) the away3D engine can open .obj files easily

I've already attached an away3d action script code (in this thread), which opens an obj, puts textures onto it, and then moves a light around the model.
I just don't know why it's not working with my .obj + .dds files.

Guys, we have the knowledge together ... come on!
## Post #93
- Username: InsaneXo
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Sep 12, 2011 3:21 am
- Post datetime: 2011-10-20T16:24:01+00:00
- Post Title: Re: Diablo III .app

-
## Post #94
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-21T14:20:37+00:00
- Post Title: Re: Diablo III .app

??
## Post #95
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-24T12:51:54+00:00
- Post Title: Re: Diablo III .app

Yeah, Monguron, do some work and add it together, cause I don not know how.

I don't seem to find a way to connect the 2 together, there is no reference to the data extracted from the app file that has any link to the material files...

T.
## Post #96
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-25T02:57:48+00:00
- Post Title: Re: Diablo III .app

Your source code in C# is very nice TaylorMouse, why don't just develop it by adding some function to display the 3d mesh. C#.NET can be easily added to website, too.
## Post #97
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-25T08:49:57+00:00
- Post Title: Re: Diablo III .app

Thnx, 

the code actually looks even nicer, because that code has been taken using Reflector.NET

the only problem is that I don't know how to easily display 3D models using C# :/

Any suggestions?

T.
## Post #98
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-25T18:56:31+00:00
- Post Title: Re: Diablo III .app

Hey Guys,

many days passed since I could check the forum... (perhaps 4 or 5 )

so ...

As I've said I could load a model in flash, but the texturing is a different story...

I try to do my best, and will tell you if I have any progress.
## Post #99
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-25T20:05:53+00:00
- Post Title: Re: Diablo III .app

I converted the Adria_A_diff.dds and Adria_A_spec.dds files to .png format, so there is an improvement, but it seems there are some texturing problems...

1) I'm using this code in away3d

		[Embed(source="/../embeds/adria/Adria_A_diff.png")]
		private var Albedo : Class;

		[Embed(source="/../embeds/adria/Adria_A_spec.png")]
		private var Specular : Class;


But It seems the spec.png is not on the object, and also the original diff.png is misaligned in some parts, or ....?

any idea?
[adria-02.png](https://xentaxbackup.github.io/file/4809_adria-02.png)
## Post #100
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-25T21:46:28+00:00
- Post Title: Re: Diablo III .app

When you convert them to png ? are they rotated by 360° , I ask this because some formats of dds have the nasty habit of being internally rotated up side down. :/

I know, I don't know why   


T.
## Post #101
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-26T07:47:07+00:00
- Post Title: Re: Diablo III .app

Well, if you use a decent 3D modeling program like 3DStudio in stead of some freeware   

then it builds the normals automatically   

T.
## Post #102
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-26T07:50:05+00:00
- Post Title: Re: Diablo III .app

Hmm perhaps you say something, but I think you wanted to write 180° and not 360° ... 

The situation with the model:
- When I load the model in Maya, it must be rotated by -90 degrees around both the Y and the Z axises
- When I load it in 3D studio, it's OK
- When I load it in the flash (away3D), it's misaligned as well, as in Maya

So I rotated the model in Maya and wanted to export it in .obj format, but Maya can make other formats 

Then I wanted to load the model in 3DS, but it was originally good. Or should I rotate it anyway, and then it will be improper in 3DS, but properly aligned in Maya and in flash (away3D).
## Post #103
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-26T07:56:37+00:00
- Post Title: Re: Diablo III .app

Anyway, as said before, the normals are not exported apperantly, and therefor in 3D Max it works just fine, since after the import, MAX does a recalc of the normals

T.
## Post #104
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-26T08:29:59+00:00
- Post Title: Re: Diablo III .app

> the only problem is that I don't know how to easily display 3D models using C# :/
>
> 
>
> Any suggestions?

Can we use Microsoft XNA, an engine game, written by C# to make the model viewer? 
You can see the tutorial here
[http://msdn.microsoft.com/en-us/library ... 31%29.aspx](http://msdn.microsoft.com/en-us/library/bb197293%28v=xnagamestudio.31%29.aspx)

XNA naturally support .fbx and .dds, so we need the plugin to read .obj
[http://www.roastedamoeba.com/blog/archi ... rs-for-xna](http://www.roastedamoeba.com/blog/archive/2010/11/20/ds-obj-and-nff-content-importers-for-xna)
## Post #105
- Username: npd2006
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Sep 13, 2011 4:15 pm
- Post datetime: 2011-10-26T08:33:14+00:00
- Post Title: Re: Diablo III .app

> But It seems the spec.png is not on the object, and also the original diff.png is misaligned in some parts, or ....?
>
> 
>
> any idea?
You get a wrong UV. May be you need to flip it.
## Post #106
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-26T09:50:40+00:00
- Post Title: Re: Diablo III .app

> Anyway, as said before, the normals are not exported apperantly, and therefor in 3D Max it works just fine, since after the import, MAX does a recalc of the normals

It was exported before by BoyC's converter, which makes porper normals... or not? 

With the other converter it was impossible to load the object in Maya or 3DS.
## Post #107
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2011-10-26T18:44:52+00:00
- Post Title: Re: Diablo III .app

use fixed TaylorMouse converter, thats work fine ...
models loading to maya and show correctly ...

P.S. 2TaylorMouse sorry for reflector - you are be offline ;(
## Post #108
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-10-26T19:07:01+00:00
- Post Title: Re: Diablo III .app

Hey no problem about the reflector, just don't claim it yours   

T.
## Post #109
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-10-27T07:16:52+00:00
- Post Title: Re: Diablo III .app

So it seems the texture is pulled onto the model upside down.

I was rotating the texture in photoshop by 180, but this didn't help --> still the same symptom.
So the 3D engines are getting this info somewhat different, but I have no idea about that...
## Post #110
- Username: Weeboss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 02, 2011 9:58 pm
- Post datetime: 2011-11-02T14:17:34+00:00
- Post Title: Re: Diablo III .app

Hello,

I'm trying to import some Models from D3 Beta into 3ds max.
I did everything as it's suppose to; I get the .obj file from the .app file via D3AppConvert2Obj.exe through cmd.exe but for some reason it Imports weirdly into 3ds max...

Here's screenshot:
[http://img39.imageshack.us/img39/4637/importfailjol.jpg](http://img39.imageshack.us/img39/4637/importfailjol.jpg)

I tried extracting other .app files from the MPQ but with the same result.

Any ideas as of what might be the cause?
## Post #111
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-11-04T13:17:58+00:00
- Post Title: Re: Diablo III .app

The cause: you might be using an older version of the exporter file. It had a bug: it didn'z export all the data of the object (v-normals).

I had the same problem.

On page 6 of this thread, Deltoone posted the latest version: d3app2obj.zip [4.17 KiB]. Try that, and give here a feedback.

My problem:
At the moment I cannot put the proper textures onto the model. Who has any idea, how to rotate the textures, as my eninge puts them upside down onto the model in flash, by using away3d (away3d.com).
## Post #112
- Username: Weeboss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 02, 2011 9:58 pm
- Post datetime: 2011-11-05T10:53:02+00:00
- Post Title: Re: Diablo III .app

Thank you for your reply, Monguron

I've already found a workaround for the problem by first importing the .obj file into Blender and then exporting it for 3ds Max.
It seems to work just fine in Blender.

Take care!
## Post #113
- Username: Monguron
- Rank: advanced
- Number of posts: 45
- Joined date: Fri Oct 07, 2011 3:03 am
- Post datetime: 2011-11-12T19:15:15+00:00
- Post Title: Re: Diablo III .app

Hey Guys,

I would need the best .app converter (from BoyC), cause the other .app files do not work for me.

Could you please link it? thanks!
## Post #114
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-12-19T17:58:52+00:00
- Post Title: Re: Diablo III .app

Hey Guys; it has been a while,

question though, I just downloaded the latest patch for Diablo III bèta, and tried to convert the textures again...

and only 20% of the lot has been able to convert to dds   

That Sucks any idea how I (or anyone) could/would update the texture convertor... please..


T.
## Post #115
- Username: BlackEternity
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jun 15, 2012 1:08 pm
- Post datetime: 2012-06-15T05:11:00+00:00
- Post Title: Re: Diablo III .app

Necrolis just uploaded an updated D3TexConv not too long ago, its version 1.09b
[http://www38.zippyshare.com/v/29977667/file.html](http://www38.zippyshare.com/v/29977667/file.html)
## Post #116
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2012-07-26T07:54:35+00:00
- Post Title: Re: Diablo III .app

sry for bumping...

this tool can import Diablo 3 app/ani/tex files an export them into another format (lizenz needed for export/save).

[http://www.unwrap3d.com/u3d/formats.aspx](http://www.unwrap3d.com/u3d/formats.aspx)
## Post #117
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-07-26T08:31:55+00:00
- Post Title: Re: Diablo III .app

> Reply from BlackEternity
>
> Necrolis just uploaded an updated D3TexConv not too long ago, its version 1.09b
http://www38.zippyshare.com/v/29977667/file.html

I don't think that works too well, at least for me upon dragging a dropping a texture onto the .exe the .exe deleted itself...
## Post #118
- Username: BlackEternity
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jun 15, 2012 1:08 pm
- Post datetime: 2012-08-07T17:34:15+00:00
- Post Title: Re: Diablo III .app

> Reply from LUBDAR
>
> I don't think that works too well, at least for me upon dragging a dropping a texture onto the .exe the .exe deleted itself...
Works just fine, try using a batch file to convert an entire folder.
## Post #119
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-28T22:02:04+00:00
- Post Title: Re: Diablo III .app

Hey guys, been pretty busy the last couple of days, certainly with the D3 Expansion coming along.

I've taken every piece of code I could find, dropped it into a max script and now I'm able to import the app files into max, completely rigged and skinned.

It took quit some time to figure out how to apply all these things in Max, cause exporting it to obj does not involve bones, vertex weights etc...

it's not completed yet, just a wip..

I need some way to find the texture/material 

in the code I took the example of Adria, so if you want to use the script ( as of Max 2011) you need to change the hard coded file of adria.app and here dds files to make it work

```
	Import Diablo III App format
	by Taylor Mouse (c) 12.2013
	
*/

/* CLEAN UP */
ClearListener()
max select all
max delete

/********************/
/* Helper functions */
/********************/
fn ReadBytes stream val =
(	
	for i=1 to val do ReadByte stream
)

fn ReadFixedString stream val =
(
	local str = ""
	for i=1 to val do
	(
		s= bit.IntAsChar(ReadByte stream)
		
		if(s!="\0") then str+=s
	)
	return str
)
/********************/
/* STRUCTS */
/********************/
struct AABB
(
	A,
	B
)

struct D3Bone
(
	ID,
	Name,
	ParentID,
	Position, 
	TheBone
	
)

struct GeoSet
(
	Name,
	theMesh,
	Verts,
	VertexWeights,
	Normals,
	UVWs,
	Indices,
	
	nVerts,
	ofVerts,
	sizeVerts,
	
	ofVertexWeights,
	sizeWeights,
	
	nIndices,
	ofIndices,
	sizeIndices
	
)

struct VertexWeight --> Influence
(
	BoneID1,Weight1,
	BoneID2,Weight2,
	BoneID3,Weight3
)
	
/********************/
/********************/

file = @"..\Exported\Appearance\Adria.app"
stream = fOpen file "rb"

-- Skip 36 bytes
ReadBytes stream 36

-- Bones
nBones = ReadLong stream
ofBones = ReadLong stream
sizeBones = ReadLong stream

-- Skip 120 bytes
ReadBytes stream 120

-- Subsets
nSubset = ReadLong stream
ofSubset = ReadLong stream
sizeSubset = ReadLong stream

-- Skip 36 bytes
ReadBytes stream 36

-- Collision Sphere
sph = sphere  pos:[ReadFloat stream , ReadFloat stream , ReadFloat stream]  radius:(ReadFloat stream) name:"CollisionSphere"
sph.xray = true

-- Colission Capsules
nCollCap = ReadLong stream
offCollCap = ReadLong stream
sizeCollCap = ReadLong stream

allBones = #()
/* BONES */
if(ofBones > 0 ) then 
(
	fSeek stream (ofBones + 16) #seek_set 
	
	for b=1 to nBones do
	(
		aBone = D3Bone()
		aBone.ID = b
		aBone.Name = ReadFixedString stream 64
		aBone.ParentID = (ReadLong stream) + 1 --> 0 is the root
		
		-- Bounding Boxes
		ab = AABB()
		ab.A = [ReadFloat stream , ReadFloat stream , ReadFloat stream] 
		ab.B = [ReadFloat stream , ReadFloat stream , ReadFloat stream]
		
		x = ab.A.X - ab.B.X
		y = ab.A.Y - ab.B.Y
		z = ab.A.Z - ab.B.Z
		
		-- Box length:x width:y height:z wirecolor:(color c 0 0)
		
		-- Bounding Spheres
		radius = ReadFloat stream
		position = [ReadFloat stream , ReadFloat stream , ReadFloat stream]
		
		-- Sphere radius:0.2 pos:position wirecolor:(Color 0 c 0)
		
		-- PRSTransform
		q1 = quat (ReadFloat stream) (ReadFloat stream) (ReadFloat stream) (ReadFloat stream) 
		v1 = Point3 (ReadFloat stream) (ReadFloat stream) (ReadFloat stream)
		
		aBone.Position = v1
		append allBones aBone
		
		ReadBytes stream 100 ---> not required,... yet
	)

	/* Build the bones*/
	for b=1 to nBones do
	(
		if( allBones[b].ParentID == 0 ) then
		(
			allBones[b].TheBone = BoneSys.CreateBone allBones[b].Position allBones[b].Position [0,0,1]
		)
		else
		(
			parentID = allBones[b].ParentID
				
			allBones[b].TheBone = BoneSys.CreateBone allBones[b].Position allBones[b].Position [0,0,1]
			allBones[b].TheBone.Parent = allBones[parentID].TheBone
		)
		allBones[b].TheBone.Name = allBones[b].Name
		allBones[b].TheBone.ShowLinks = true
		allBones[b].TheBone.Width = 0.05
		allBones[b].TheBone.Height = 0.05
		
	)
	
	
)

/* GEOSETS */
fSeek stream (ofSubset + 16) #seek_set 
geosets= #()
for	subset=1 to nSubset do
(
	g = GeoSet()
	
	ReadLong stream -- ?
	g.nVerts = ReadLong stream
	g.ofVerts = ReadLong stream
	g.sizeVerts = ReadLong stream
	ReadLong stream -- ?
	g.ofVertexWeights = ReadLong stream
	g.sizeWeights = ReadLong stream
	ReadLong stream -- ?
	g.nIndices = ReadLong stream
	g.ofIndices = ReadLong stream 
	g.sizeIndices = ReadLong stream
	
	ReadBytes stream 28
	
	g.name = ReadFixedString stream 128
	name2 = ReadFixedString stream 128
	
	ReadBytes stream 44
	
	append geosets g
)

/* GEO Data */
for i=1 to nSubset do
(
	verts = #()
	vertexWeights = #()
	normals = #()
	uvws = #()
	indices = #()
	
	/* Vertices, normals, texture coordinates */
	fSeek stream ( geosets[i].ofVerts + 16 ) #seek_set 
	for v=1 to geosets[i].nVerts do
	(
		-- vertex
		vert = [ ReadFloat stream, ReadFloat stream, ReadFloat stream ]
		append verts vert
		
		-- normal
		nx = ReadByte stream
		ny = ReadByte stream
		nz = ReadByte stream
		ReadBytes stream 9
		
		rnx = (nx - 127.0)/127.0
		rny = (ny - 127.0)/127.0
		rnz = (nz - 127.0)/127.0
		
		normal = [rnx, rny, rnz]
		
		append normals normal
		
		-- Texture Coordinate	
		texU = ReadShort stream #unsigned
		texV = ReadShort stream #unsigned
		ReadBytes stream 16
		
		tu = float
		tv = float
		tu = 32767.0 - texU
		tv = 32767.0 - texV
		tu /= 512.0
		tv /= 512.0
		tv +=1.0
		tu *=-1.0
		
		uv = [tu,  tv, 0.0]
		
		append uvws uv
	)
 
	/* Vertex Weights */
	fSeek stream ( geosets[i].ofVertexWeights + 16 ) #seek_set
	for v=1 to geosets[i].nVerts do
	(
		vw = VertexWeight()
		vw.BoneID1 = ReadLong stream
		vw.Weight1 = ReadFloat stream
		vw.BoneID2 = ReadLong stream
		vw.Weight2 = ReadFloat stream
		vw.BoneID3 = ReadLong stream
		vw.Weight3 = ReadFloat stream
		
		append vertexWeights vw
	)
	
	/* Indices */
	fSeek stream ( geosets[i].ofIndices + 16 ) #seek_set
	for f=1 to geosets[i].nIndices / 3  do
	(
		index = [ReadShort stream #unsigned +1 , ReadShort stream #unsigned + 1, ReadShort stream #unsigned + 1]
		
		append indices index
	)
	
	geosets[i].Verts = verts
	geosets[i].UVWs = uvws
	geosets[i].Normals = normals
	geosets[i].Indices = indices
	geosets[i].VertexWeights = vertexWeights
)

/* BUILD THE MESHES */
for i=1 to nSubset do
(
	-- Create the mesh
	theMesh = mesh vertices:geosets[i].Verts faces:geosets[i].Indices name:geosets[i].Name tverts:geosets[i].UVWs vnorms:geosets[i].Normals
	meshOp.setMapSupport theMesh 1 true
	for t = 1 to geosets[i].Verts.count do
		meshop.setMapVert theMesh 1 t geosets[i].UVWs[t]
	update theMesh
	
	
	
	-- create the materials
	meditMaterials[i] = Standard()
	meditMaterials[i].name = geosets[i].Name
		
	meditMaterials[i].diffuseMapEnable = on
	meditMaterials[i].selfillumMapEnable = on
	meditMaterials[i].useSelfIllumColor = on
	meditMaterials[i].opacityMapEnable = on
		
	meditMaterials[i].specularLevel = 50
	meditMaterials[i].selfIllumColor = color 255 255 255
		
	meditMaterials[i].diffuseMap  = Bitmaptexture fileName:"..\Adria_A_DiffCON.dds"
	meditMaterials[i].specularMap = Bitmaptexture fileName:"..\Adria_A_SpecCON.dds"
	meditMaterials[i].selfillumMap = Bitmaptexture fileName:"..\Adria_A_SpecCON.dds"
	meditMaterials[i].opacityMap = Bitmaptexture fileName:"..\Adria_A_DiffCON.dds"
	meditMaterials[i].opacityMap.monooutput = 1
	
	showTextureMap meditMaterials[i] true
	theMesh.material = meditMaterials[i]
	update theMesh
	
	
	geosets[i].theMesh = theMesh
	/*
	TODO:
	
	Find the matching texture using an algorithm
	
	
	*/
	
)

for i=1 to nSubset do
(
	msh = geosets[i].theMesh
	
	-- Apply skin modifier
	select msh
	max modify mode --> VERY IMPORTANT!!!
	modPanel.addModToSelection(skin())
	skinMod = msh.Modifiers["skin"]
	
	modPanel.setCurrentObject skinMod
		
	-- add all the bones
	for b=1 to nBones do
	(
		skinOps.addBone skinMod allBones[b].TheBone 0
	)
	update msh
		
	-- Apply vertex weights
	--disableSceneRedraw()
	
	select msh
	max modify mode

	bones_total_count = skinops.getnumberbones skinMod
	vertex_count = getNumverts msh 

	for v = 1 to vertex_count do
	(
		--vertex_bone_count = skinOps.GetVertexWeightCount msh.modifiers[#skin] v
		for b = 1 to bones_total_count do
		(

			boneId1 = geosets[i].VertexWeights[v].BoneId1 + 1
			weight1 = geosets[i].VertexWeights[v].Weight1
			boneId2 = geosets[i].VertexWeights[v].BoneId2 + 1
			weight2 = geosets[i].VertexWeights[v].Weight2
			boneId3 = geosets[i].VertexWeights[v].BoneId3 + 1 
			weight3 = geosets[i].VertexWeights[v].Weight3

			if (b == boneId1) then 
				skinOps.ReplaceVertexWeights skinMod v boneId1 weight1
			else if (b == boneId2) then 
				skinOps.SetVertexWeights skinMod v boneId2 weight2
			else if (b == boneId3) then 
				skinOps.SetVertexWeights skinMod v boneId3 weight3
			
		)
		-- apply the new bone weights
		
		update msh
	) 
	
	--enableSceneRedraw()
	update msh
	redrawviews()

)
/* Clean up */
fFlush stream
fClose stream
clearselection()
GC()
/* Zoom into the selected model */
max zoomext sel all


```


T.
## Post #120
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-01-11T04:30:59+00:00
- Post Title: Re: Diablo III .app

Thanks for the work on this script thus far.  I was wondering if you had any pointers on some of the models.  I've only tried a handful of the .app files and they work for the most part.  
I'm trying to import the Male Barbarian files and have found ones from the main clientmpq named

Barbarian_male.app
Barbarian_male_characterSelect.app
Barbarian_male_eaten.app
and Barbarian_male_oneBatch.app

but I can't import the barbarian_male.app. In fact it seems that any of the "class_gender".app files don't seem to import. Am I looking in the wrong mpq?

I'm trying to import the helms and shoulder pads to look at the models of the different armor tiers.

any suggestions?

Once again, thanks for all the work thus far...
## Post #121
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-03-24T19:21:29+00:00
- Post Title: Re: Diablo III .app

[out]
## Post #122
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-03-29T16:50:31+00:00
- Post Title: Re: Diablo III .app

Found a .bt-script for 010-editor ( interesting application, didn't know it) on diablo3dev.com. 

Updated that script to it also works for v260 .app files. Data looks good at first glance, but I only tried with the adria-model, so could be something is off still. Also changed the vertex-format so it matches the one from Taylor Mouse, so at least its clear where the normal and uv's are. 

Since that site seems rather inactive, but had a back-link to this thread as the source of information, I thought I'd post the updated one here in case someone finds it useful.
[diablo3app_260.bt.zip](https://xentaxbackup.github.io/file/7143_diablo3app_260.bt.zip)
## Post #123
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-03-31T19:47:39+00:00
- Post Title: Re: Diablo III .app

Hi guys, I'm working on a model viewer for Diablo, only problem is I don't know how to link the models with the textures :/

Anyone any idea, I know it can be done cause Cain's Aide app does that, but I don't seem to find any info anywhere about the matching ...

Some help would be appreciated

T.
## Post #124
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-03-31T20:02:44+00:00
- Post Title: Re: Diablo III .app

Check the .app file, material-structure. It contains a "TexAnimParams" block with i0 inside.
e.g. For Adria, the first one is 37626.

Check the .tex file, in the header the snoID (offset 16). these id's match.

Regards.
## Post #125
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-03-31T23:52:26+00:00
- Post Title: Re: Diablo III .app

[out]
## Post #126
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-04-01T19:36:50+00:00
- Post Title: Re: Diablo III .app

thnx kalmiya, I'll try that

the 37626, is that the offset?
and the snoID, you mean I need to check or read all the tex files before I actually find a match ??

hey Wobble, no you don't need to have diablo 3, it works in 2 ways
 1. select the top folder where you extracted your model to and it will build up a tree structure with all the models in it
 2. select a single model and it loads all the possible models in an array so you can browse thru it using a back and forward button, so that you don't need to select the model from the explorer every time

T.
## Post #127
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-02T08:51:06+00:00
- Post Title: Re: Diablo III .app

At offset 16 in the .tex file (=header.snoID) you have the value 37626 

If you look in the .app file, check the Material-block and specifically the TextureAnim-whatever-block - in the 4 bytes before the matrix (don't have the code in front of me) you have an i0 value which contains that exact same value. I'd say it's more then a "good guess" that that is the cross-reference you are looking for.

Basically I think that every asset has it's own unique id in the header, and files can reference other files with that id.
Which means you probably don't want to do this each time you start your viewer, but rather let it runs once through all assets and create a dictionary with <snoID, filename> for quick lookup ( probably d3 has such a table somewhere too ).

Question which I still have is if this id is globally unique, or unique per category of assets, i.e. 
- can we have a .app with id 1000 and a texture with id 1000 
- or would we have a model with id 1000 and a texture with id 1001. 
If I would have to guess I would guess it's globally unique, but I didn't verify that since I didn't need it yet.

How far are you with your viewer? and what language? 
Do you also intend to animate the models? I'm interested in that and wil probably give it a try myself soon(ish).

Regards
## Post #128
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-04-02T19:14:44+00:00
- Post Title: Re: Diablo III .app

Some sample images from my viewer, with a few models that have an easy find on the dds textures 

T.
## Post #129
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-04-02T21:49:10+00:00
- Post Title: Re: Diablo III .app

WHoa!!! 
Nice work!!!!
## Post #130
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-13T04:59:53+00:00
- Post Title: Re: Diablo III .app

Is there a new version of the d3app2obj.exe that will work with ROS .app files? I've tried to convert with no luck.

I wanted to make more Wanted Posters & Wallpapers

[http://danielbarras.deviantart.com/art/Diablo-383353031](http://danielbarras.deviantart.com/art/Diablo-383353031)
[http://danielbarras.deviantart.com/art/ ... -382784958](http://danielbarras.deviantart.com/art/Stygian-Crawler-382784958)
[http://danielbarras.deviantart.com/art/Beast-383974501](http://danielbarras.deviantart.com/art/Beast-383974501)
[http://danielbarras.deviantart.com/art/ ... -386945096](http://danielbarras.deviantart.com/art/The-Burning-Axe-of-Sankis-386945096)
## Post #131
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-13T15:02:51+00:00
- Post Title: Re: Diablo III .app

Here ya go - I extracted the parsing code from my little 3d-engine into a separate executable. It has really basic commandline-parameters and it was only tested it on 2-3 models, but it should be able to convert any reaper-of-soul .app file ( fileformat v260 ), just give it a try.

update: removed attachment, improved version follows a few posts later.
## Post #132
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-13T15:06:47+00:00
- Post Title: Re: Diablo III .app

Testing now; and a big Thank you.

Some of the models load correctly, others do not.. any help would be appreciated.

Loads Correctly:


Perfect:


Weird:


Adria:



zombie dog is great:


Westmarch hound is crazy:
## Post #133
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-13T17:07:51+00:00
- Post Title: Re: Diablo III .app

@TheRealMethuselah: PM'ed you with my contact details.
## Post #134
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-13T17:13:08+00:00
- Post Title: Re: Diablo III .app

Thank you for looking into this. I've sent the file.
[Adria.zip](https://xentaxbackup.github.io/file/7204_Adria.zip)
## Post #135
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-13T17:55:02+00:00
- Post Title: Re: Diablo III .app

Loading the .obj in blender works - loading it in 3dsmax fails. 

1. If you use blender to export from obj to obj and import that in 3dsmax it fails ( so blender does sth comparable to my exporter - would have been great if that worked, then I could have done a simple file-compare to see what's different).
2. If you use blender to export to collada ( dae ) and import that in 3dsmax, it works.
3. If you use blender and merge the two meshes, export that to .obj and import into 3dsmax, it also works.

It looks like 3dsmax doesn't like .obj's with more than 1 part - or at least handles it differently than blender does. So either you use one of the above work-arounds, or we need to figure out if there's some way to get 3dsmax to load multi-mesh .obj's (changing the obj text-export on my part shouldn't take much work - I only need to know what it should look like).
## Post #136
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-13T18:11:52+00:00
- Post Title: Re: Diablo III .app

Downloading Blender now. 
Tested.

Perfect!


You are the bomb dot com.

Hound


Glorious!
## Post #137
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-13T18:28:34+00:00
- Post Title: Re: Diablo III .app

Nicey!

I made some modifications, can you give this version a try ?
[d3rs_app2obj_101.zip](https://xentaxbackup.github.io/file/7206_d3rs_app2obj_101.zip)
## Post #138
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-13T18:30:26+00:00
- Post Title: Re: Diablo III .app

On it.

EDIT:
FLAWLESS VICTORY!


Re-converting all of my .app files now.


Thank you so much for your quick response to inquiries, [kalmiya](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=45041). I appreciate it, wholeheartedly.

Working perfectly.


Chests!


[http://danielbarras.deviantart.com/art/ ... -447397488](http://danielbarras.deviantart.com/art/Gyrfalcon-s-Foot-447397488)
## Post #139
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-04-17T02:42:38+00:00
- Post Title: Re: Diablo III .app

> Reply from TaylorMouse
>
> Hey guys, been pretty busy the last couple of days, certainly with the D3 Expansion coming along.

I've taken every piece of code I could find, dropped it into a max script and now I'm able to import the app files into max, completely rigged and skinned.

It took quit some time to figure out how to apply all these things in Max, cause exporting it to obj does not involve bones, vertex weights etc...

it's not completed yet, just a wip..

I need some way to find the texture/material 

in the code I took the example of Adria, so if you want to use the script ( as of Max 2011) you need to change the hard coded file of adria.app and here dds files to make it work
Code: Select all/*
	Import Diablo III App format
	by Taylor Mouse (c) 12.2013
	
*/

/* CLEAN UP */
ClearListener()
max select all
max delete

/********************/
/* Helper functions */
/********************/
fn ReadBytes stream val =
(	
	for i=1 to val do ReadByte stream
)

fn ReadFixedString stream val =
(
	local str = ""
	for i=1 to val do
	(
		s= bit.IntAsChar(ReadByte stream)
		
		if(s!="\0") then str+=s
	)
	return str
)
/********************/
/* STRUCTS */
/********************/
struct AABB
(
	A,
	B
)

struct D3Bone
(
	ID,
	Name,
	ParentID,
	Position, 
	TheBone
	
)

struct GeoSet
(
	Name,
	theMesh,
	Verts,
	VertexWeights,
	Normals,
	UVWs,
	Indices,
	
	nVerts,
	ofVerts,
	sizeVerts,
	
	ofVertexWeights,
	sizeWeights,
	
	nIndices,
	ofIndices,
	sizeIndices
	
)

struct VertexWeight --> Influence
(
	BoneID1,Weight1,
	BoneID2,Weight2,
	BoneID3,Weight3
)
	
/********************/
/********************/

file = @"..\Exported\Appearance\Adria.app"
stream = fOpen file "rb"

-- Skip 36 bytes
ReadBytes stream 36

-- Bones
nBones = ReadLong stream
ofBones = ReadLong stream
sizeBones = ReadLong stream

-- Skip 120 bytes
ReadBytes stream 120

-- Subsets
nSubset = ReadLong stream
ofSubset = ReadLong stream
sizeSubset = ReadLong stream

-- Skip 36 bytes
ReadBytes stream 36

-- Collision Sphere
sph = sphere  pos:[ReadFloat stream , ReadFloat stream , ReadFloat stream]  radius:(ReadFloat stream) name:"CollisionSphere"
sph.xray = true

-- Colission Capsules
nCollCap = ReadLong stream
offCollCap = ReadLong stream
sizeCollCap = ReadLong stream

allBones = #()
/* BONES */
if(ofBones > 0 ) then 
(
	fSeek stream (ofBones + 16) #seek_set 
	
	for b=1 to nBones do
	(
		aBone = D3Bone()
		aBone.ID = b
		aBone.Name = ReadFixedString stream 64
		aBone.ParentID = (ReadLong stream) + 1 --> 0 is the root
		
		-- Bounding Boxes
		ab = AABB()
		ab.A = [ReadFloat stream , ReadFloat stream , ReadFloat stream] 
		ab.B = [ReadFloat stream , ReadFloat stream , ReadFloat stream]
		
		x = ab.A.X - ab.B.X
		y = ab.A.Y - ab.B.Y
		z = ab.A.Z - ab.B.Z
		
		-- Box length:x width:y height:z wirecolor:(color c 0 0)
		
		-- Bounding Spheres
		radius = ReadFloat stream
		position = [ReadFloat stream , ReadFloat stream , ReadFloat stream]
		
		-- Sphere radius:0.2 pos:position wirecolor:(Color 0 c 0)
		
		-- PRSTransform
		q1 = quat (ReadFloat stream) (ReadFloat stream) (ReadFloat stream) (ReadFloat stream) 
		v1 = Point3 (ReadFloat stream) (ReadFloat stream) (ReadFloat stream)
		
		aBone.Position = v1
		append allBones aBone
		
		ReadBytes stream 100 ---> not required,... yet
	)

	/* Build the bones*/
	for b=1 to nBones do
	(
		if( allBones[b].ParentID == 0 ) then
		(
			allBones[b].TheBone = BoneSys.CreateBone allBones[b].Position allBones[b].Position [0,0,1]
		)
		else
		(
			parentID = allBones[b].ParentID
				
			allBones[b].TheBone = BoneSys.CreateBone allBones[b].Position allBones[b].Position [0,0,1]
			allBones[b].TheBone.Parent = allBones[parentID].TheBone
		)
		allBones[b].TheBone.Name = allBones[b].Name
		allBones[b].TheBone.ShowLinks = true
		allBones[b].TheBone.Width = 0.05
		allBones[b].TheBone.Height = 0.05
		
	)
	
	
)

/* GEOSETS */
fSeek stream (ofSubset + 16) #seek_set 
geosets= #()
for	subset=1 to nSubset do
(
	g = GeoSet()
	
	ReadLong stream -- ?
	g.nVerts = ReadLong stream
	g.ofVerts = ReadLong stream
	g.sizeVerts = ReadLong stream
	ReadLong stream -- ?
	g.ofVertexWeights = ReadLong stream
	g.sizeWeights = ReadLong stream
	ReadLong stream -- ?
	g.nIndices = ReadLong stream
	g.ofIndices = ReadLong stream 
	g.sizeIndices = ReadLong stream
	
	ReadBytes stream 28
	
	g.name = ReadFixedString stream 128
	name2 = ReadFixedString stream 128
	
	ReadBytes stream 44
	
	append geosets g
)

/* GEO Data */
for i=1 to nSubset do
(
	verts = #()
	vertexWeights = #()
	normals = #()
	uvws = #()
	indices = #()
	
	/* Vertices, normals, texture coordinates */
	fSeek stream ( geosets[i].ofVerts + 16 ) #seek_set 
	for v=1 to geosets[i].nVerts do
	(
		-- vertex
		vert = [ ReadFloat stream, ReadFloat stream, ReadFloat stream ]
		append verts vert
		
		-- normal
		nx = ReadByte stream
		ny = ReadByte stream
		nz = ReadByte stream
		ReadBytes stream 9
		
		rnx = (nx - 127.0)/127.0
		rny = (ny - 127.0)/127.0
		rnz = (nz - 127.0)/127.0
		
		normal = [rnx, rny, rnz]
		
		append normals normal
		
		-- Texture Coordinate	
		texU = ReadShort stream #unsigned
		texV = ReadShort stream #unsigned
		ReadBytes stream 16
		
		tu = float
		tv = float
		tu = 32767.0 - texU
		tv = 32767.0 - texV
		tu /= 512.0
		tv /= 512.0
		tv +=1.0
		tu *=-1.0
		
		uv = [tu,  tv, 0.0]
		
		append uvws uv
	)
 
	/* Vertex Weights */
	fSeek stream ( geosets[i].ofVertexWeights + 16 ) #seek_set
	for v=1 to geosets[i].nVerts do
	(
		vw = VertexWeight()
		vw.BoneID1 = ReadLong stream
		vw.Weight1 = ReadFloat stream
		vw.BoneID2 = ReadLong stream
		vw.Weight2 = ReadFloat stream
		vw.BoneID3 = ReadLong stream
		vw.Weight3 = ReadFloat stream
		
		append vertexWeights vw
	)
	
	/* Indices */
	fSeek stream ( geosets[i].ofIndices + 16 ) #seek_set
	for f=1 to geosets[i].nIndices / 3  do
	(
		index = [ReadShort stream #unsigned +1 , ReadShort stream #unsigned + 1, ReadShort stream #unsigned + 1]
		
		append indices index
	)
	
	geosets[i].Verts = verts
	geosets[i].UVWs = uvws
	geosets[i].Normals = normals
	geosets[i].Indices = indices
	geosets[i].VertexWeights = vertexWeights
)

/* BUILD THE MESHES */
for i=1 to nSubset do
(
	-- Create the mesh
	theMesh = mesh vertices:geosets[i].Verts faces:geosets[i].Indices name:geosets[i].Name tverts:geosets[i].UVWs vnorms:geosets[i].Normals
	meshOp.setMapSupport theMesh 1 true
	for t = 1 to geosets[i].Verts.count do
		meshop.setMapVert theMesh 1 t geosets[i].UVWs[t]
	update theMesh
	
	
	
	-- create the materials
	meditMaterials[i] = Standard()
	meditMaterials[i].name = geosets[i].Name
		
	meditMaterials[i].diffuseMapEnable = on
	meditMaterials[i].selfillumMapEnable = on
	meditMaterials[i].useSelfIllumColor = on
	meditMaterials[i].opacityMapEnable = on
		
	meditMaterials[i].specularLevel = 50
	meditMaterials[i].selfIllumColor = color 255 255 255
		
	meditMaterials[i].diffuseMap  = Bitmaptexture fileName:"..\Adria_A_DiffCON.dds"
	meditMaterials[i].specularMap = Bitmaptexture fileName:"..\Adria_A_SpecCON.dds"
	meditMaterials[i].selfillumMap = Bitmaptexture fileName:"..\Adria_A_SpecCON.dds"
	meditMaterials[i].opacityMap = Bitmaptexture fileName:"..\Adria_A_DiffCON.dds"
	meditMaterials[i].opacityMap.monooutput = 1
	
	showTextureMap meditMaterials[i] true
	theMesh.material = meditMaterials[i]
	update theMesh
	
	
	geosets[i].theMesh = theMesh
	/*
	TODO:
	
	Find the matching texture using an algorithm
	
	
	*/
	
)

for i=1 to nSubset do
(
	msh = geosets[i].theMesh
	
	-- Apply skin modifier
	select msh
	max modify mode --> VERY IMPORTANT!!!
	modPanel.addModToSelection(skin())
	skinMod = msh.Modifiers["skin"]
	
	modPanel.setCurrentObject skinMod
		
	-- add all the bones
	for b=1 to nBones do
	(
		skinOps.addBone skinMod allBones[b].TheBone 0
	)
	update msh
		
	-- Apply vertex weights
	--disableSceneRedraw()
	
	select msh
	max modify mode

	bones_total_count = skinops.getnumberbones skinMod
	vertex_count = getNumverts msh 

	for v = 1 to vertex_count do
	(
		--vertex_bone_count = skinOps.GetVertexWeightCount msh.modifiers[#skin] v
		for b = 1 to bones_total_count do
		(

			boneId1 = geosets[i].VertexWeights[v].BoneId1 + 1
			weight1 = geosets[i].VertexWeights[v].Weight1
			boneId2 = geosets[i].VertexWeights[v].BoneId2 + 1
			weight2 = geosets[i].VertexWeights[v].Weight2
			boneId3 = geosets[i].VertexWeights[v].BoneId3 + 1 
			weight3 = geosets[i].VertexWeights[v].Weight3

			if (b == boneId1) then 
				skinOps.ReplaceVertexWeights skinMod v boneId1 weight1
			else if (b == boneId2) then 
				skinOps.SetVertexWeights skinMod v boneId2 weight2
			else if (b == boneId3) then 
				skinOps.SetVertexWeights skinMod v boneId3 weight3
			
		)
		-- apply the new bone weights
		
		update msh
	) 
	
	--enableSceneRedraw()
	update msh
	redrawviews()

)
/* Clean up */
fFlush stream
fClose stream
clearselection()
GC()
/* Zoom into the selected model */
max zoomext sel all



T.

So theoretically any model I plug in to the line that defines what file I want to import should work, right?

Also, what's the workflow for getting the actual files? I feel kind of lost jumping into long threads like these.

EDIT: Just tried out that above script, doesn't seem to work with Max 2012, unfortunately, it throws errors about arrays being too large or something0. Hope taylormouse decides to update the script so we can get these out rigged with original bones.

EDIT EDIT: Just had a thought that maybe it's more the fact this script predates 2.0 and RoS that's the cause of the errors. In any case, hoping for someone to come through and get us rigged meshes.
## Post #140
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-21T00:42:37+00:00
- Post Title: Re: Diablo III .app

My workflow is:

1. Use MPQEditor to extract the .app files from ClientData.mpq


2. Use MPQEditor to extract the .tex files from Texture.mpq


3. Use xvi32 with a textures.xsc file (below) to convert the header of the .tex files

textures.xsc

```
REPLACE EF BE AD DE 2F BY EF BE AD DE 2B
```


batch file:

```
exit
```


4. Use D3TexConv to convert the .tex files to .dds files

```
@for /f "tokens=*" %%a in ('dir /b *.tex') do D3TexConv.exe "%%a"
```


5. Use nvconvert to convert the .dds files to .png

```
nconvert -out png *.dds
```


6. Use d3rs_app2obj to convert the .app to .obj files

```
REN *.app.obj ??????????????????????????????.obj
DEL *.app /q
```


7. Profit.


EDIT: [kalmiya](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=45041), in the previous iterations of the converter, I was able to select certain portions of it, be it wings, etc, and delete them. In this current version it looks as though it is simply one piece. Is there a way to extract the model with the pieces in tact?

EDIT 2: As [TehDave](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=7471) mentioned. If there is any way to extract WITH the bones, you would make us all very happy.

EDIT 3: You've been uber generous. I've been racking my brain on the animation thread, trying to figure out how you view the animations... would you PLEASE give me a heads up or step-by-step?
## Post #141
- Username: ibeckman671
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 16, 2014 10:16 am
- Post datetime: 2014-04-22T00:17:12+00:00
- Post Title: Re: Diablo III .app

I wish d3rs_app2obj converted some of the models correctly. It seems the main characters and Tyrael come out blotchy. Here is the Monk for example. What am I doing wrong?
[monk.jpg](https://xentaxbackup.github.io/file/7240_monk.jpg)
## Post #142
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-22T03:45:08+00:00
- Post Title: Re: Diablo III .app

You're doing nothing wrong. 

It seems that the models for the players have all of the items equipped, but that they are separate pieces.

That goes back to my question earlier. In previous iterations, you could remove those pieces. Now, it's just one big piece.

Same goes for Tyrael, there is some model pieces over his face. 


As for the Barbarian, he's got everything on him too.
## Post #143
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-23T22:06:11+00:00
- Post Title: Re: Diablo III .app

> Reply from TheRealMethuselah
>
> My workflow is:

EDIT: kalmiya, in the previous iterations of the converter, I was able to select certain portions of it, be it wings, etc, and delete them. In this current version it looks as though it is simply one piece. Is there a way to extract the model with the pieces in tact?

EDIT 2: As TehDave mentioned. If there is any way to extract WITH the bones, you would make us all very happy.

EDIT 3: You've been uber generous. I've been racking my brain on the animation thread, trying to figure out how you view the animations... would you PLEASE give me a heads up or step-by-step?

@1: The problem is with how 3dsmax imports it. Apparently 3dsmax only imports it correctly if the triangles are in 1 contiguous block. But that apparently broke the grouping. I might have an idea, will take a look. Update: Try the attachment ( completely untested ^^ )

@2: I can extract the bone-data in my parser, the problem is that the .obj fileformat is quite primitive (which makes it easy to export meshes) but it just does not support bone-information. I was looking for alternatives, only text-format I know is collada ( which is a real pain, and I was actually rewriting my engine to directly import .blend files instead of collada, before I got curious about the d3 fileformat ). 

@3: I don't know how to import it into 3dsmax - I'm a software developer, not a graphics-guy ^^ There are some max-scripts in the d3-threads - I think by TailorMouse and ZeroGravity - I guess it should be possible with those. I'd actually be interested in a step-by-step tutorial on how to load it into 3dsmax.

As a background:  I'm trying to use the bone-data to "magically" transform the vertices in my little sandbox engine. 
So here goes a question of my own: If I look in the .app file, there also is bone-information. What is it intended for? Should that be applied to the mesh-vertices first - to bring the model in the "t-pose" as the starting-point for applying a keyframe from the .ani ? 

For example, for the chest the .app contains the following info:

# model bone-structure
# [0] id=0 'Root_Joint' - parent-id=-1  (no parent)
# - q( 0.000, 0.000, 1.000, 0.000) p(-1.591, 0.000,-0.000) s(  1.00)
# - q(-0.000,-0.000, 1.000,-0.000) p( 1.591, 0.000, 0.000) s(  1.00)
# - q( 0.000, 0.000, 1.000, 0.000) p(-1.591, 0.000,-0.000) s(  1.00)
# - q( 0.000, 0.000, 1.000, 0.000) p(-1.591, 0.000,-0.000) s(  1.00)
# - q(-0.000,-0.000, 1.000,-0.000) p( 1.591, 0.000, 0.000) s(  1.00)
# [1] id=1 'Hinge - parent-id=0 ' (="Root_Joint")
# - q( 0.000, 0.000, 1.000, 0.000) p(-1.302,-0.052, 1.552) s(  1.00)
# - q(-0.000,-0.000, 1.000,-0.000) p( 1.302, 0.052,-1.552) s(  1.00)
# - q( 0.000, 0.000, 1.000, 0.000) p( 0.290,-0.052, 1.552) s(  1.00)
# - q( 0.000, 0.000, 1.000, 0.000) p(-1.302,-0.052, 1.552) s(  1.00)
# - q(-0.000,-0.000, 1.000,-0.000) p( 1.302, 0.052,-1.552) s(  1.00)
[d3rs_app2obj_102_experimental.zip](https://xentaxbackup.github.io/file/7251_d3rs_app2obj_102_experimental.zip)
## Post #144
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-23T22:50:41+00:00
- Post Title: Re: Diablo III .app

Ok, I see. I'll try a few things here and there.

Adria (Adria_idle_01     34 frames)


Adria new with animation frame. (Click to enlarge 1920x1080)
[](http://danielbarras.deviantart.com/art/Adria-449644050)

Mallet Lord with animation frame. (Click to enlarge 1920x1080)
[](http://danielbarras.deviantart.com/art/Mallet-Lord-449711048)
I think I've got enough data to animate to get some good model poses. Thank you again.
## Post #145
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-03T08:32:07+00:00
- Post Title: Re: Diablo III .app

I redid the script, you can download them from here:

[http://www.sc2mapster.com/assets/sc1-ra ... rt-script/](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/41-diablo-iii-reaper-of-souls-max-2011-import-script/)

Also, if you put them in your startup script, the first time you run them it could throw an error ( don't know why ) just re-evaluate the script and it should work

Animation script included

T.
## Post #146
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-03T20:08:32+00:00
- Post Title: Re: Diablo III .app

Btw TheRealMethuselah, where did you get the devil circle in the backgrounds from ?

T.
## Post #147
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-05-04T16:12:24+00:00
- Post Title: Re: Diablo III .app

Trying the new script (from 2 posts ago) - it does load the adria-rs-model, but when trying to load the adria-rs-run/walk-animation I get a messagebox displaying "Maxscript rollout handler exception: --type error: Call needs function or class, got: undefined"... ? Also tried with a rs-chest. Anyone else got that problem?

[Update]: Seems that 3dsmax doesn't like "echo".
## Post #148
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-05-06T03:52:18+00:00
- Post Title: Re: Diablo III .app

Here ya go, TaylorMouse:



Here's my new gallery.
[http://danielbarras.deviantart.com/gallery/](http://danielbarras.deviantart.com/gallery/)


Grotesque (Stitch)


Adria Animation run 

[Stitch.zip](https://xentaxbackup.github.io/file/7302_Stitch.zip)
## Post #149
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-08T18:16:46+00:00
- Post Title: Re: Diablo III .app

Thnx, don't forget to turn on the two sided faces for the texture

T.
## Post #150
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-05-09T00:08:11+00:00
- Post Title: Re: Diablo III .app

Got it! Fixed.


ibeckman, so there were a few pieces of Tyrael you had to get past:


A_restored_cloth
A_normal_mat
A_restored_mat
A_skeleton_mat

It now loads just fine.
## Post #151
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-05-15T19:23:34+00:00
- Post Title: Re: Diablo III .app

still getting an error from animation script(script called function got unidentified) or something along those lines, could it be that i didnt update to RoS? vanilla d3 models import perfectly tho
## Post #152
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-15T20:22:10+00:00
- Post Title: Re: Diablo III .app

Did you get my latest scripts from SC2Mapster, it has a change for RoS and Vanilla.

[http://www.sc2mapster.com/assets/sc1-ra ... rt-script/](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/41-diablo-iii-reaper-of-souls-max-2011-import-script/)

T.
## Post #153
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-05-15T20:36:32+00:00
- Post Title: Re: Diablo III .app

yeah and still getting the same error when trying to import anims on both 3ds max 09 and 11
## Post #154
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-05-16T17:36:17+00:00
- Post Title: Re: Diablo III .app

can anyone actually help me with this? maybe im using the scripts the wrong way? do i need to put the ani and app in the same files or anything like this?


EDIT: working now but with a slight weight problem in the demon hunter male run animation
## Post #155
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-05-17T04:18:44+00:00
- Post Title: Re: Diablo III .app

Had no problems here with DH Running...
## Post #156
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-18T20:31:58+00:00
- Post Title: Re: Diablo III .app

Finally gotten somewhere with my model viewer, you can download it from here:

[http://www.sc2mapster.com/assets/sc1-ra ... el-viewer/](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/42-diablo-iii-model-viewer/)






T.
## Post #157
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-05-18T23:08:00+00:00
- Post Title: Re: Diablo III .app

Very well done, TM.

Will we see animation selection soon?
## Post #158
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-19T19:11:50+00:00
- Post Title: Re: Diablo III .app

No, it is not on the planning to do, but I'm holding no-one back to implement it 



The reason I made this, is that I didn't want to import each model into max to look at it, and I wanted it to be browsable like you browse images, so you can see what the model is.

Also, I wanted to add functionality for SC2 models too, but it looks like I missed something cause multi-submeshes are completely screwed...


T.
## Post #159
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-05-20T16:35:37+00:00
- Post Title: Re: Diablo III .app

That sounds great. If you'd like to release the source code, I'd be happy to help in implementing multi-submeshes and animation.
## Post #160
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-05-22T21:19:17+00:00
- Post Title: Re: Diablo III .app

[out]
## Post #161
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2014-05-28T05:06:35+00:00
- Post Title: Re: Diablo III .app

thanks,this  is a greadtool!!
## Post #162
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-08-11T19:12:56+00:00
- Post Title: Re: Diablo III .app

Hey guys, I had need for the Diablo3 010 Template recently, so I grabbed what I believe to be the most recent one on this thread, titled diablo3app_260 (note that I'm working with the most recent patch of RoS). It was failing to execute in all cases because of a missing variable, and also lacking in some information that I needed for my own purposes, so I did a small amount of research and thought I'd share my findings with you guys since you're more the authority on Diablo3 stuff than I (I specialize in Dark Souls currently).

# In the SubObject struct, at the end should be 8 more bytes, which I added as int pad4b_260[2]; - this fixed things so the template could run properly.
# In the AppearanceMaterial struct, you calculate the number of SOAs by taking serSOAs.Size and dividing by 248. The number of SOAs is actually directly related to the number of looks in the file - every material will have a SOA for each look. Since each SOA is 248 bytes, from what I've been able to see, it's a happy coincidence that your calculation works out.
# In the UberMaterial struct, you calculate the number of MaterialTextureEntrys by taking serMatTexList.Size and dividing by 184 - the correct size in my files appears to be 160, which is supported in the next point.
# The TexAnimParams struct is too large. Removing FrameAnim fa0; and int i4 from the end puts it at the right size, but you obviously lose whatever information FrameAnim was supposed to have in it. It may just need to be moved elsewhere in the struct or something instead.
# I believe this was mentioned by somebody earlier, but I'll list it here again: In the TexAnimParams struct, the very first variable, marked i0, is actually the texture ID. As you probably know, these texture IDs can be obtained from the headers of the individual .TEX files themselves.
## Post #163
- Username: tesla
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 01, 2014 6:53 am
- Post datetime: 2014-09-30T22:57:47+00:00
- Post Title: Re: Diablo III .app

Good evening everyone, i'm kinda new to extracting stuff from .MPQs and I need to see if it's possible to extract the 3D model for the Black Soulstone!

Can anyone guide me or help me to get the model?

Sorry if i'm bothering!
Thanks in advance
## Post #164
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-10-01T06:43:45+00:00
- Post Title: Re: Diablo III .app

[out]
## Post #165
- Username: Amran
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 01, 2010 1:53 pm
- Post datetime: 2014-10-04T19:46:07+00:00
- Post Title: Re: Diablo III .app

The model viewer looks great, thanks for working on this!

I'm wondering if I'm missing something with setting up the textures. I've extracted the DDS files using TexConv, and then set the texture path in the config file (value="E:\DiabloTextures\"), but they don't seem to load when opening models. If anyone knows what I might be missing, that would be great!
## Post #166
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-10-09T20:05:51+00:00
- Post Title: Re: Diablo III .app

Hey Amran, there is not an actual implementation for apply the textures to the models, it is all guessing and stuff, so it is not your setup, just some models work,others don't

T.
## Post #167
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2014-10-20T19:45:51+00:00
- Post Title: Re: Diablo III .app

Sorry, I am a total noob when it comes to scripts and whatnot. I just wanted to find a working model viewer, which led me here.

TaylorMouse, I downloaded your program, but it just gives me an "Error Running Program" note when I try to start it. Do I need to have something else installed, do I need to put the program into my D3 directory, or what? Help please.
## Post #168
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-10-20T20:09:58+00:00
- Post Title: Re: Diablo III .app

Not really, do you have the .net framework 4.5 installed ? if you don't install it.

T.
## Post #169
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2014-10-20T21:42:29+00:00
- Post Title: Re: Diablo III .app

I tried, but appartently that only exist for Win 7 and above - I still use XP until I can get my new PC... So I only have Net Framework 4.0
## Post #170
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-10-21T21:07:34+00:00
- Post Title: Re: Diablo III .app

QuickBMS Script to fix headers in textures ( XVI32.exe annoyed with their GUI   ) ...

```
IDString "\xEF\xBE\xAD\xDE\x2F"
set MEMORY_FILE binary "\xEF\xBE\xAD\xDE\x2B"
append 1
log NAME 0 5 MEMORY_FILE

```


2TM
[http://www.sc2mapster.com/media/images/ ... reen01.jpg](http://www.sc2mapster.com/media/images/74/157/screen01.jpg)
How you create  model categories ? Manually ?
## Post #171
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2014-10-22T18:15:09+00:00
- Post Title: Re: Diablo III .app

OK, since I cannot get the viewer to run, I tried using your Import Script to import the APP files and anims. I can run the scripts, but... nothing happens. 3DsMax still does not accept the files when I try to import. Can someone please give me directions on what exactly needs to be done with the scripts?
## Post #172
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-10-22T19:12:07+00:00
- Post Title: Re: Diablo III .app

> Reply from deltaone
>
> QuickBMS Script to fix headers in textures ( XVI32.exe annoyed with their GUI   ) ...
Code: Select allget NAME filename
IDString "\xEF\xBE\xAD\xDE\x2F"
set MEMORY_FILE binary "\xEF\xBE\xAD\xDE\x2B"
append 1
log NAME 0 5 MEMORY_FILE

What is this for?

> Reply from deltaone
>
> 
2TM
http://www.sc2mapster.com/media/images/ ... reen01.jpg
How you create  model categories ? Manually ?

Yes, I have put some additional sub folders, else it sometimes takes too long to load the treeview, but you need to do that manually

T.
## Post #173
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-10-22T21:50:59+00:00
- Post Title: Re: Diablo III .app

> Reply from TaylorMouse
>
> deltaone wrote:QuickBMS Script to fix headers in textures ( XVI32.exe annoyed with their GUI   ) ...
Code: Select allget NAME filename
IDString "\xEF\xBE\xAD\xDE\x2F"
set MEMORY_FILE binary "\xEF\xBE\xAD\xDE\x2B"
append 1
log NAME 0 5 MEMORY_FILE



What is this for?

Is alternative for XVI32.exe script for fixing texture headers, can use D3TexConv_v0.9 texture converter ...

XVI32 script from board

```
REPLACE EF BE AD DE 2F BY EF BE AD DE 2B

```
## Post #174
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-11-15T16:20:03+00:00
- Post Title: Re: Diablo III .app

Alright I can't seem to figure out what I'm doing wrong here. I've tried using the d3rs_app2obj file to convert the app to obj files, but all it will do is open and close even if I try to do it through the cmd prompt. I tried to use the 3ds Max import script and after I select the model location and click the import button nothing shows. Tried to use the model viewer and it gave me the message of the program is not ready when I tried to import. What am I doing wrong?
## Post #175
- Username: hans80
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 16, 2014 10:51 pm
- Post datetime: 2014-11-16T15:01:31+00:00
- Post Title: Re: Diablo III .app

hi guys!

i downloaded d3 starter edition recently (15GB)
my plan: app->obj->3d program

i tried all the tools and scripts i found on here and on google...
nothing works 

i haven't tested the model viewer because i have xp32(!)

so my question is... SHOULD it work? will there be xp32 support for the viewer?
or is this just a waist of time for us average joes?

will be trying wow viewer in the meantime.

edit: no luck in wow either, new fileformat and all... oh well
looks like i'm too late   (or MUCH too early )


cheers
## Post #176
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-24T20:24:28+00:00
- Post Title: Re: Diablo III .app

damn TaylorMouse, this tool look great, many thanks for all your work do and time you spend in it, grateful and have a nice day.

PS: well the only problem with the model viewer is when I try load app, it say can't found the directory where are textures, so how I can do it if no have option to change the path?
## Post #177
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-07-24T10:57:59+00:00
- Post Title: Re: Diablo III .app

@CriticalError,

sorry I've been out from this for a while

I've been working on Heroes of the Storm and reverse engineering these models and animations, with success 

You can get these scripts here : [http://www.sc2mapster.com/assets/sc1-ra ... ure/files/](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/)

it holds the scripts to import M3 files, with SC2Art Tools and without the SC2 Art Tools installed

Yes that path is hard coded and it refers to my local g: drive... I need to check how this works again to make it work.

T.
## Post #178
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-07-24T13:52:45+00:00
- Post Title: Re: Diablo III .app

ohhh I see, ok anyway many thanks for the new release, you rock on man, keep working mate have a nice day and take care.
