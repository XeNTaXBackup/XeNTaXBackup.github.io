## Post #1
- Username: FallenAngelRiku
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 30, 2011 1:28 pm
- Post datetime: 2011-11-30T07:30:04+00:00
- Post Title: [Request] Dark Cloud Model Converter

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-11-30T17:11:50+00:00
- Post Title: [Request] Dark Cloud Model Converter

i looked into it,
*.chr = archive for other files, someone else with better PS2 3D Model knowledge can maybe finish this quickly

[](http://www.imagebanana.com/view/m7m5fxkr/export.jpg)

here a quickbms script to unpack:

```
savepos ftemp

GetDString Name 64
get Offset long
get Size long
get NOffset long
get unk1 long

if Offset = 0xFFFFFFFF
CleanExit
endif

if Size = 0xFFFFFFFF
CleanExit
endif

math Offset += ftemp
math NOffset += ftemp

Log Name Offset Size

goto NOffset
while Offset <> 0xFFFFFFFF

CleanExit
```


3D Model = *.mds
texture = *.img
cloth = *.clo (txt file)
animation = *.mot + *.bbp + *.wgt
model info = info.cfg

*.img is an archive for *.tm2 files

incomplete MDS format:

```
//--- 010 Editor v3.1.2 Binary Template
//
// File: Dark Cloud *.mds
// Author: Falo
//--------------------------------------

struct{
    char magic[4];
    int unk1; // Version ?
    int numBones;
    int numModels;
    struct{
        struct BONE bone[numBones]<optimize=false>;
    }Bones;
    struct{
        struct MDT mdt[numModels+1]<optimize=false>;
    }Models;
}MDS;

struct MDT{
    local int ftemp;
    ftemp = FTell();

    char magic[4];
    int unk1;
    int szMDT;
    int numVerts;
    int ofsVerts;
    int numVerts2;
    int ofsVerts2;

    int numUnk1;
    int ofsUnk1;
    int numUnk2;
    int ofsUnk2;
    int numUV;
    int ofsUV;
    int numUnk3;
    int ofsUnk3;

    ubyte unk4[4];

    if(numVerts)
    {
        struct{
            FSeek(ftemp + ofsVerts);
            struct VERTEX vertex[numVerts]<optimize=false>;
        }Vertices;
    }

    if(numUnk1)
    {
        FSeek(ftemp + ofsUnk1);
        ubyte data1[numUnk1];
    }

    if(numUnk2)
    {
        FSeek(ftemp + ofsUnk2);
        int data2[numUnk2/4];
    }

    if(numVerts2)
    {
        struct{
            FSeek(ftemp + ofsVerts2);
            struct NORMAL normal[numVerts2]<optimize=false>;
        }Normals;
    }

    if(numUV)
    {
        struct{
            FSeek(ftemp + ofsUV);
            struct TEXUV texuv[numUV]<optimize=false>;
        }UVs;
    }

    if(numUnk3)
    {
        FSeek(ftemp + ofsUnk3);
        struct UNK3 dataUnk3[numUnk3]<optimize=false>;
    }
};


struct BONE{
    int unk1;
    int unk2;
    char name[36];
    int id;
    float data[16];
};

struct VERTEX{
    float x;
    float y;
    float z;
    float w;
    Printf("v %f %f %f\n",x,y,z);
};

struct NORMAL{
    float x;
    float y;
    float z;
    float w;
    //Printf("vn %f %f %f\n",x,y,z);
};

struct TEXUV{
    float u;
    float v;
    float z;
    float w;
    //Printf("vt %f %f\n",u,v);
};

struct UNK3{
    ubyte data[96];
};
```
## Post #3
- Username: FallenAngelRiku
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 30, 2011 1:28 pm
- Post datetime: 2011-12-31T06:10:56+00:00
- Post Title: [Request] Dark Cloud Model Converter

thanks for your help Falo, hope someone help me with this.
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-01-11T21:54:30+00:00
- Post Title: [Request] Dark Cloud Model Converter

I have figured out how the Face Index works (for some of the meshes, others use a different type of face index). I was working on a file from the demo version of Dark Cloud, but it looks similar if not exactly the same as the full version (which I had seen, but I deleted the file since then)

I assume your script above can get to the face index, as it begins after the last vertex. Here is the Type 1 Face Index Section:
4ByteUnknown (this might always be zero)
4ByteInteger this appears to be always 0x10
4Byte#NumberofSubIndexes
4ByteUnknown (this might always be zero)

For Each SubIndex:
1ByteIntegerStyleofIndex (I have seen this as 0x03 and 0x04 and still be type 1)
1ByteIntegerTypeofIndex (Appears to be be 0x01 for Type 1 Indexes)
2ByteUnknown (probably not used/always 0x0000)
4ByteInteger#NumberofVertexes
4ByteInteger (Proabably not used/always zero)
Now there are exactly #NumberofVertexes, and each vertex forms a tristrip and each vertex has associated data in the following way:
{4ByteIntegerVertexInStripReferenced+4ByteInteger(NormalMapping/orTexutureMapping/or BoneMapping someone tell me which one these are) +4ByteInteger(NormalMapping/orTexutureMapping/or BoneMapping) +4ByteInteger(NormalMapping/orTexutureMapping/or BoneMapping )}
If there is more then one SubIndex the next one will begin right away.
So to summarize unlike standard games which might have a face index, this game, uses references to the Normal/Texture/Bone maps, so instead of a face index, it is a Face/Normal/Texture/Bone reference list Which is why many meshes in this game have a different number of vertexes then the number of normal Mappings and TextureMappings, as NormalMaps/TextureMaps can be referenced  more then once.
Here is the image of a mesh:
## Post #5
- Username: FallenAngelRiku
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 30, 2011 1:28 pm
- Post datetime: 2012-01-24T02:20:01+00:00
- Post Title: [Request] Dark Cloud Model Converter

interesting, looks like some sort of gem from the game

thanks for your help FurryFan!

offtopic:
Im a Furry Fan too!
## Post #6
- Username: RAWTalent
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 08, 2011 8:39 pm
- Post datetime: 2012-02-26T15:59:11+00:00
- Post Title: [Request] Dark Cloud Model Converter

Any progress on this?
## Post #7
- Username: Xeeynamo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jan 07, 2011 6:25 pm
- Post datetime: 2012-04-06T13:17:32+00:00
- Post Title: [Request] Dark Cloud Model Converter

Interesting stuff! 
@Falo: If I remember well, IMG format is used also in KH2 with the IMZ (an archive with more IMG stuff). There is a IMG/TM2 tool around here?

EDIT: I tried to load a TM2 with Photoshop and I get weird images like this:
## Post #8
- Username: InnocentSam2
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Apr 05, 2012 9:06 pm
- Post datetime: 2012-04-22T16:03:56+00:00
- Post Title: [Request] Dark Cloud Model Converter

Compressed? Usually compressed files spurt out things like that.
## Post #9
- Username: 1jn14r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 27, 2013 6:42 am
- Post datetime: 2013-08-23T21:14:51+00:00
- Post Title: [Request] Dark Cloud Model Converter

Hi has anyone had any luck extracting the TM2 files from an img archive. I've tried using TextER but I am getting a read only error. Btw this I'm new to this forum so lay off any n00b comments
## Post #10
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-10-04T19:02:09+00:00
- Post Title: [Request] Dark Cloud Model Converter

Here is a quickbms script that converts all of the models in Dark Cloud 2 (and will work on some of the models in Dark Cloud 1). Use the script on the Data.dat

[http://ps23dformat.wikispaces.com/file/ ... tTo3DS.bms](http://ps23dformat.wikispaces.com/file/view/DarkCloud2PS2datadatTo3DS.bms)
See this page on how to use the script:
[http://ps23dformat.wikispaces.com/Dark+Cloud+2](http://ps23dformat.wikispaces.com/Dark+Cloud+2)

```
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE4 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;


Get Q ASIZE 0 ;
Math number = 0 ;
For T = 0 < Q ;
Math number += 1 ;
findloc OFFSET string "\x4D\x44\x53\x00\x01\x00\x00\x00" 0 0 ;
If OFFSET = 0 ;
Math T = Q ;
Math T += 1 ;
ELSE ;
GoTo OFFSET 0 ;
SavePos start 0 ;
Math start -= 0x50 ;
GoTo start 0 ;
Put start Long MEMORY_FILE4 ;
GoTo start 0 ;
GoTo 0x48 0 SEEK_CUR ;
Get size Long 0 ;
Put size Long MEMORY_FILE4 ;
GoTo OFFSET 0 ;
Get d Long 0 ;
SavePos OFFSET 0 ;
EndIF ;
Next T ;


Get ssk ASIZE MEMORY_FILE4 ;
Math ssk /= 8 ;
Math deersun = 0 ;
For qmk = 1 To ssk ;


GoTo deersun MEMORY_FILE4 ;
Get deerstart Long MEMORY_FILE4 ;
Get deersize Long MEMORY_FILE4 ;
SavePos deersun MEMORY_FILE4 ;
log MEMORY_FILE 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
Math chick = deerstart ;
Math chick += deersize ;

GoTo deerstart 0 ;
GetDString name 16 0 ;

Math Qprime = 0 ;
Math Qprimeprime = 0 ;
Math GG = 0 ;
Math YFYF = 0 ;
GoTo deerstart 0 ;
GoTo 0x50 0 SEEK_CUR ;
SavePos base 0 ;
GoTo 0x08 0 SEEK_CUR ;
Get bones Long 0 ;
GoTo 0x04 0 SEEK_CUR ;
SavePos base 0 ;
Math bones *= 0x70 ;
GoTo bones 0 SEEK_CUR ;
SavePos base 0 ;
Math ctest = 0 ;
Math vulpine = 0 ;
Math vplus = 0 ;

Do ;
GoTo base 0 ;
SavePos gold 0 ;
GoTo 0x08 0 SEEK_CUR ;
Get ctest Long 0 ;
Math ctest += base ;
Math base = ctest ;
Math ctest += 1 ;


Math vplus += vulpine ;
GoTo gold 0 ;
GoTo 0x0c 0 SEEK_CUR ;
Get vulpine Long 0 ;

GoTo gold 0 ;
GoTo 0x40 0 SEEK_CUR ;
SavePos kitkit 0 ;
For vixvix = 1 To vulpine ;
GoTo kitkit 0 ;
Get type1 Long 0 ;
Get type2 Long 0 ;
Get type3 Long 0 ;
Get type4 Long 0 ;
SavePos kitkit 0 ;
GoTo Qprime MEMORY_FILE2 ;
Put type1 Long MEMORY_FILE2 ;
Put type2 Long MEMORY_FILE2 ;
Put type3 Long MEMORY_FILE2 ;
SavePos Qprime MEMORY_FILE2 ;
Next vixvix ;
Math tigertest = 0 ;
Math typetiger1 = 0 ;
Math typetiger2 = 0 ;
Math typetiger3 = 0 ;
Math typetiger4 = 0 ;


GoTo gold 0 ;
GoTo 0x28 0 SEEK_CUR ;
Get jump Long 0 ;





GoTo gold 0 ;
GoTo 0xC 0 SEEK_CUR ;
Get typetiger1 Long 0 ;
If typetiger1 > 0 ;
Math tigertest += 1 ;
EndIF ;




GoTo gold 0 ;
GoTo 0x1C 0 SEEK_CUR ;
Get typetiger2 Long 0 ;
If typetiger2 > 0 ;
Math tigertest += 1 ;
EndIF ;



GoTo gold 0 ;
GoTo 0x2C 0 SEEK_CUR ;
Get typetiger3 Long 0 ;
If typetiger3 > 0 ;
Math tigertest += 1 ;
EndIF ;


GoTo gold 0 ;
GoTo 0x4C 0 SEEK_CUR ;
Get typetiger4 Long 0 ;
If typetiger4 > 0 ;
Math tigertest += 1 ;
EndIF ;






GoTo gold 0 ;
GoTo jump 0 SEEK_CUR ;
GoTo 0x8 0 SEEK_CUR ;
Get numa Long 0 ;
Get d Long 0 ;


SavePos gold 0 ;
For car = 1 To numa ;
GoTo gold 0 ;
Get d1 byte 0 ;
Get d2 byte 0 ;
Get d3 byte 0 ;
Get d4 byte 0 ;



Get nc Long 0 ;
Math facetest = 0 ;
Math faceface = 0 ;
Get d Long 0 ;
SavePos tin 0 ;
If d1 > 15 ;
Math adjj = 100 ;
Else ;
Math adjj = 0 ;
EndIf ;
Math d2 += adjj ;


GoTo d1 0 ;
Padding 16 ;
SavePos gyh 0 ;
Math gyh -= d1 ;
Math yyy = 16 ;
Math yyy -= gyh




Math tigerbeast = 0 ;



If tigertest = 2 ;
If d2 = 2 ;
Math tigerbeast = 1 ;
EndIF ;
EndIF ;

If tigertest = 2 ;
If d2 = 100 ;
Math tigerbeast = 2 ;
EndIF ;
EndIF ;


If tigertest = 2 ;
If d2 = 102 ;
Math tigerbeast = 1 ;
EndIF ;
EndIF ;



If tigertest = 3 ;
If d2 = 0 ;
Math tigerbeast = 3 ;
EndIF ;
EndIF ;



If tigertest = 3 ;
If d2 = 1 ;
Math tigerbeast = 2 ;
EndIF ;
EndIF ;



If tigertest = 3 ;
If d2 = 2 ;
Math tigerbeast = 2 ;
EndIF ;
EndIF ;




If tigertest = 3 ;
If d2 = 102 ;
Math tigerbeast = 1 ;
EndIF ;
EndIF ;




If tigertest = 4 ;
If d2 = 0 ;
Math tigerbeast = 3 ;
EndIF ;
EndIF ;


If tigertest = 4 ;
If d2 = 1 ;
Math tigerbeast = 4 ;
EndIF ;
EndIF ;


If tigertest = 4 ;
If d2 = 3 ;
Math tigerbeast = 3 ;
EndIF ;
EndIF ;






Math tintin = nc ;
Math tintin *= 0x4 ;
Math tintin *= tigerbeast ;
Math dragongold = 0x4 ;
Math dragongold *= tigerbeast ;
Math dragongold -= 4 ;




Math tintin += tin ;
Math gold = tintin ;
Math fy = 0 ;
log MEMORY_FILE6 0 0 ;
For carcar = 1 To nc ;
GoTo tin 0 ;
Get type1 Long 0 ;
GoTo dragongold 0 SEEK_CUR ;
SavePos tin 0 ;
Math type1 += vplus ;
GoTo fy MEMORY_FILE6 ;
Put type1 Short MEMORY_FILE6 ;
SavePos fy MEMORY_FILE6 ;
Next carcar ;
Math kc = nc ;
Math kc -= 2 ;

Math oldfox = 0 ;
For venven = 1 To kc ;
If yyy = 4 ;
GoTo oldfox MEMORY_FILE6 ;
Get type1 Short MEMORY_FILE6 ;
SavePos oldfox MEMORY_FILE6 ;
Get type2 Short MEMORY_FILE6 ;
Get type3 Short MEMORY_FILE6 ;
GoTo YFYF MEMORY_FILE3 ;
Put type1 Short MEMORY_FILE3 ;
Put type2 Short MEMORY_FILE3 ;
Put type3 Short MEMORY_FILE3 ;
Put 00 Short MEMORY_FILE3 ;


Put type1 Short MEMORY_FILE3 ;
Put type3 Short MEMORY_FILE3 ;
Put type2 Short MEMORY_FILE3 ;
Put 00 Short MEMORY_FILE3 ;









SavePos YFYF MEMORY_FILE3 ;
EndIF ;
Next venven ;











Math kc += 2 ;
Math kc /= 3 ;
Math oldfox = 0 ;
For venvenfox = 1 To kc ;
If yyy = 3 ;
GoTo oldfox MEMORY_FILE6 ;
Get type1 Short MEMORY_FILE6 ;
Get type2 Short MEMORY_FILE6 ;
Get type3 Short MEMORY_FILE6 ;
SavePos oldfox MEMORY_FILE6 ;
GoTo YFYF MEMORY_FILE3 ;
Put type1 Short MEMORY_FILE3 ;
Put type2 Short MEMORY_FILE3 ;
Put type3 Short MEMORY_FILE3 ;
Put 00 Short MEMORY_FILE3 ;
Put type1 Short MEMORY_FILE3 ;
Put type3 Short MEMORY_FILE3 ;
Put type2 Short MEMORY_FILE3 ;
Put 00 Short MEMORY_FILE3 ;
Put type2 Short MEMORY_FILE3 ;
Put type1 Short MEMORY_FILE3 ;
Put type3 Short MEMORY_FILE3 ;
Put 00 Short MEMORY_FILE3 ;
Put type2 Short MEMORY_FILE3 ;
Put type3 Short MEMORY_FILE3 ;
Put type1 Short MEMORY_FILE3 ;
Put 00 Short MEMORY_FILE3 ;
SavePos YFYF MEMORY_FILE3 ;
EndIF ;
Next venvenfox ;















Next car ;




While ctest < chick ;












Get Zw3 ASIZE MEMORY_FILE3 ;
Math Zf3 = Zw3 ;
Math Zf3 /= 8 ;
Get Zw2 ASIZE MEMORY_FILE2 ;
Math Zf2 = Zw2 ;
Math Zf2 /= 12 ;
Math FaceNumber = Zf3 ;
Math VertexNumber = Zf2 ;
Math Snake = VertexNumber ;
Math Snake *= 12 ;
Math Dragon = FaceNumber ;
Math Dragon *= 8 ;
Math Sum = Dragon ;
Math Sum += Snake ;
Math QQQ = 60 ;
Math QQQ += Snake ;
Math QQ = 52 ;
Math qaz = 0 ;
Math wsx = 0 ;
log MEMORY_FILE5 0 QQQ ;
For Vertex = 0 < Zw2 ;
GoTo qaz MEMORY_FILE2 ;
Get D byte MEMORY_FILE2 ;
SavePos qaz MEMORY_FILE2 ;
GoTo QQ MEMORY_FILE5 ;
Put D Byte MEMORY_FILE5 ;
SavePos QQ MEMORY_FILE5 ;
Next Vertex ;
For Face = 0 < Zw3 ;
GoTo wsx MEMORY_FILE3 ;
Get D byte MEMORY_FILE3 ;
SavePos wsx MEMORY_FILE3 ;
GoTo QQQ MEMORY_FILE5 ;
Put D Byte MEMORY_FILE5 ;
SavePos QQQ MEMORY_FILE5 ;
Next Face ;
GoTo 0 MEMORY_FILE5 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE5 ;
Math M = Sum ;
Math M += 60 ;
Put M Long MEMORY_FILE5 ;
set M Byte 0x02 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x0A ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x03 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE5 ;
Math M = Sum 
Math M += 44 ;
Put M Long MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE5 ;
Math M = Sum 
Math M += 38 ;
Put M Long MEMORY_FILE5 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x72 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x67 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x6F ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x6A ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE5 ;
Math M = Sum 
Math M += 22 ;
Put M Long MEMORY_FILE5 ;
Set M Byte 0x10 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE5 ;
Math M = Snake ;
Math M += 8 ;
Put M Long MEMORY_FILE5 ;
Math M = VertexNumber ;
Put M Short MEMORY_FILE5 ;
Math JumpJump = Snake ;
Math JumpJump += 52 ;
GoTo JumpJump MEMORY_FILE5 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE5 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE5 ;
Math M = FaceNumber ;
Math M *= 8 ;
Math M += 8 ;
Put M Long MEMORY_FILE5 ;
Math M = FaceNumber ;
Put M Short MEMORY_FILE5 ;
string name += .3ds ;
Get purpledragon ASIZE MEMORY_FILE5 ;
Log name 0 purpledragon MEMORY_FILE5 ;
Next qmk ;
```
