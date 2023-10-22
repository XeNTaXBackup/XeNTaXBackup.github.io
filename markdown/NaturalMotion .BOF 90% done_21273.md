## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-10-21T01:31:29+00:00
- Post Title: NaturalMotion .BOF 90% done

Guys I am losing my mind here
I don't know how to explain just how  I am going wrong. It seems I can read single entities but  when there are multiple meshes I fail
The file contains, textures, mesh, skinned mesh(and weight), bones and shaders
Multiple textures are manageable but multiple meshes always fail


```

typedef struct 
{
    int size;
    if(size > 0)
        char text[size];
}SString<read=ReadSString, optimize=false>;
string ReadSString( SString &str)
{
    return str.text;
}

typedef struct
{
    string text;
}xString<read=ReadxString, optimize= false>;
string ReadxString( xString &str)
{
    return str.text;
}


typedef struct(int count)
{
    local int _count = count;
    if(count > 0)
    {
        local int bac = FTell();
        int size;
        xString _text[count]<optimize=false>;
    
        FSeek(bac+4);
        if(size > 0)
            char text[size];
    }

}StringArray<read=ReadStringArray, optimize=false>;
string ReadStringArray( StringArray &str)
{
    string s = "";

    local int i =0;
    for(i = 0; i < str._count; ++i)
    {
        //Printf("\n%s", str._text[i].text);
        SPrintf(s, "%s%s ", s, str._text[i].text);
    }
    return s;
}


typedef struct 
{
    float x,y;
}Vec2<read=ReadVec2>;
string ReadVec2( Vec2 &v)
{
    string s = "";
    SPrintf(s, "(%f, %f)", v.x, v.y);
    return s;
}

typedef struct 
{
    float x,y,z;
}Vec3<read=ReadVec3>;
string ReadVec3( Vec3 &v)
{
    string s = "";
    SPrintf(s, "(%f, %f, %f)", v.x, v.y, v.z);
    return s;
}

typedef struct 
{
    float w,x,y,z;
}Vec4<read=ReadVec4>;
string ReadVec4( Vec4 &v)
{
    string s = "";
    SPrintf(s, "(%f, %f, %f, %f)", v.w, v.x, v.y, v.z);
    return s;
}


typedef struct 
{
    int x,y;
}Vec2I<read=ReadVec2I>;
string ReadVec2I( Vec2I &v)
{
    string s = "";
    SPrintf(s, "(%d, %d)", v.x, v.y);
    return s;
}

typedef struct 
{
    int x,y,z;
}Vec3I<read=ReadVec3I>;
string ReadVec3I( Vec3I &v)
{
    string s = "";
    SPrintf(s, "(%d, %d, %d)", v.x, v.y, v.z);
    return s;
}

typedef struct
{
    int size;
    if(size > 0)
        byte data[size]<optimize=false>;
}ByteData<optimize=false>;


typedef struct(int count)
{
    if(count > 0)
    {
        byte data[count]<optimize=false>;
    }

}ByteChunk;

typedef struct(int count)
{
    if(count > 0)
    {
        int data[count]<optimize=false>;
    }

}IntChunk;

typedef struct(int count)
{
    local int _count = count;
    if(count > 0)
    {
        ByteData data[count]<optimize=false>;
    }

}ByteArray<optimize=false>;

typedef struct
{
    byte r,g,b,a;
}_Color<read=Read_Color>;
string Read_Color(_Color &c)
{
    string s = "";
    SPrintf(s, "%d, %d, %d, %d", c.r, c.g, c.b, c.a);
    return s;
}   

typedef struct 
{
    int count;
    if(count > 0)
        _Color c[count/4];
}ColorData;

typedef struct(int count)
{
    local int _count = count;
    if(count > 0)
    {
        ColorData data[count]<optimize=false>;
    }
}ColorArray<optimize=false>;



int count0;
StringArray names0(count0); //main textures

int count1;
StringArray names1(count1); //meshes??

//c[0]
int count2;
StringArray names2(count2); //Bones
//c[1]
int count3;
StringArray names3(count3); //
//c[2]
int count4;
StringArray names4(count4); //Extra Textures

//d[0]
int count5;
StringArray names5(count5); //meshes??
//d[1]
int count6;
StringArray names6(count6); //Shaders / materials

//extras
int count7;
StringArray names7(count7); //overlay decals?


int count8;
StringArray names8(count8); //animated bones?


int count9;
ByteArray data0(count9);


typedef struct
{
    int index;
    int b;
    int width, height;
    int c; //3 = rgb?
    
    //sheet count?
    int _count; //mips?
    int colType;
    //ByteArray data(_count0)<bgcolor=cLtRed>;
    if(colType == 1)
        ByteArray data(_count)<bgcolor=cLtRed>;
    else
        ColorArray data(_count)<bgcolor=cLtRed>;
}TexData<optimize=false>;

//texture data from namess0
//int unknI[7];
typedef struct
{
    int count; //same as names0, total tex count?
    TexData data[count]<optimize=false>;
}TextureSec<optimize = false>;


typedef struct
{
    Vec3 pos<bgcolor=cLtRed>;
    Vec3 norm<bgcolor=cLtBlue>;
    Vec2 uv<bgcolor=cLtGreen>;
}MeshVert<read=ReadMeshVert>;
string ReadMeshVert(MeshVert &d)
{
    string s = "";
    SPrintf(s, "%s", ReadVec3(d.pos));
    SPrintf(s, "%s, %s", s, ReadVec3(d.norm));
    SPrintf(s,"(%s, %s)", s, ReadVec2(d.uv));
    return s;
} 

typedef struct (int count)
{
    if(count > 0)
        MeshVert verts[count]; //<optimize=false>
}VertArray<optimize=false>;   


typedef struct
{
    int index;
    int b; //??
    int vertCount;
    int indices;

    int _count; //lod?
    int unkn;

    IntChunk c(b)[_count]<optimize=false>;
    VertArray verts(vertCount)[_count]<optimize=false>;
    int triList[indices*(_count>0)]<optimize=false>;


}MeshData<optimize=false>;

typedef struct
{
    int count; //same as names0, total tex count?
    if(count > 0)
        MeshData data[count];
}MeshSec<bgcolor=cLtPurple>;


//0 color
if(count0 > 0)
    TextureSec texSec0<optimize=false>;

//1 mesh
if(count1 >0)
    MeshSec meshSec0;

//skinning or submesh
//list of vertices influenced by?
if(count2 > 0)
{
    ByteArray indices(count2)<optimize=false>;
}

if(count3 > 0)
{
}

if(count4 >0)
    MeshSec meshSec1;
if(count5 >0)
    ByteArray bDataUnkn(count5);


if(count6 > 0) //lambert/axis
{
    int unknI2[6];
}

if(count7 > 0) //difuse
{
    float unknF0[8];
}


if(count8 > 0) //difuse
{
}



if(count9 > 0) //difuse
{
}
Exit(0);


```



 3d.zip
(9.01 KiB) Downloaded 19 times
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-08-02T10:24:59+00:00
- Post Title: NaturalMotion .BOF 90% done

This tool can be used for .bof files
[viewtopic.php?t=19078](https://forum.xentax.com/viewtopic.php?t=19078)
