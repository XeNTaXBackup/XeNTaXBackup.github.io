## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-10T23:52:00+00:00
- Post Title: XBM 360 model file

I usually don't do this but I am having a very slow brain day.
Please can anyone guide my mind into figuring out the rest of this structure
Thanks

```
struct KengoXBM
{
    struct Header
    {
        uint ID;
        uint unkn0;
        uint otherCount; //mesh? group?
        uint shapeCount;
//------------Line 2---------------
        uint unk1;
        uint unk2; //"Points" to address of first item. always 80
        uint addrs[12];
        uint addr;//Seems like a special section
        uint unkn3; //not 1
    }header;

    struct Other
    {
        char name[32];
        char data[160];
    }other[header.otherCount];

    struct Shape
    {
        char name[32];
        float matrix1[16];
        float chnk0[32]; //Vertices?
        char data[320];
    }shape[header.shapeCount];

    //Unknown chunks
    char un02[header.addrs[3]-header.addrs[2]];
    char un03[header.addrs[4]-header.addrs[3]];
    char un04[header.addrs[5]-header.addrs[4]];
    char un05[header.addrs[6]-header.addrs[5]];
    char un06[header.addrs[7]-header.addrs[6]];
    char un07[header.addrs[8]-header.addrs[7]];
    char un08[header.addrs[9]-header.addrs[8]];
    char un09[header.addrs[10]-header.addrs[9]];
    char un10[header.addrs[11]];
    char un11[header.addr-(header.addrs[11]+header.addrs[10])];
    //char un12[addrs[3]-addrs[2]];
    
    struct Unkn_str
    {
        uint one; //usually
        uint size;
        uint pad[6]; //usually zero
    }unknStr;
    char un12[unknStr.size];
    char remnants[32];
}xbm;

```

[OBJ_GAN_KAREKI_A.zip](https://xentaxbackup.github.io/file/8242_OBJ_GAN_KAREKI_A.zip)
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-11T02:50:13+00:00
- Post Title: XBM 360 model file

I have updated the structure
Thanks to all who downloaded
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-11T06:42:47+00:00
- Post Title: XBM 360 model file

```
struct KengoXBM
{
    struct Header
    {
        uint ID;
        uint unkn0;
        uint otherCount; //mesh? group?
        uint shapeCount;
//------------Line 2---------------
        uint unk1;
        uint unk2; //"Points" to address of first item. always 80
        uint addrs[12];
        uint addr;//Seems like a special section
        uint unkn3; //not 1
    }header;

    struct Other
    {
        char name[32];
        int unkn[8];
        char data[128];
    }other[header.otherCount];

    struct Shape
    {
        char name[32];
        float matrix1[16];
        float chnk0[32]; //Vertices?
        float chnk1[4];
        int chunk2[12];
        struct ShapeChunk
        {
            int i0;
            int i1;
            int i2;
            int i3;
            int i4;
            int i5; //Constant -65536
            int i6;
            int i7; //268435554, 268435746, 268435458
        }sChnk[3];
        int addr[7];
        int chunk3[33];
    }shape[header.shapeCount];

    //Unknown chunks
    char un02[header.addrs[3]-header.addrs[2]]; //This is a structure of some sort
    char un03[header.addrs[4]-header.addrs[3]]; //shape related
    //shape related
    // 0 - might be an id/int or 2 shorts
    float un04[(header.addrs[5]-header.addrs[4])/4]; 
    float un05[(header.addrs[6]-header.addrs[5])/4]; 
    float un06[(header.addrs[7]-header.addrs[6])/4];  //shape related
    float un07[(header.addrs[8]-header.addrs[7])/4];  //shape related
    float un08[(header.addrs[9]-header.addrs[8])/4];  //shape related
    float un09[(header.addrs[10]-header.addrs[9])/4];  //shape related
    char un10[header.addrs[11]];
    char un11[header.addr-(header.addrs[11]+header.addrs[10])];
    //char un12[addrs[3]-addrs[2]];
    
    struct Unkn_str //un12's header
    {
        uint one; //usually
        uint size;
        uint pad[6]; //usually zero
    }unknStr;
    char un12[unknStr.size];
    //char remnants[32];
}xbm;

```

[WEP_DATA.zip](https://xentaxbackup.github.io/file/8243_WEP_DATA.zip)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-11T12:32:30+00:00
- Post Title: XBM 360 model file

why do u think .XBM is a model file?
For me it looks like a material file ("Xbox 360 Shader Compiler")

(while matWVPVS could be the abbreviation for "matrix World view projection" for example)
VS= VertexShader

I would search for such structures:
struct VS_OUTPUT
{
 	float4 Pos : POSITION;
	 float2 Tex : TEXCOORD0;
 	float3 Light : TEXCOORD1;
 	float3 View : TEXCOORD2;
};
## Post #5
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-11T16:54:19+00:00
- Post Title: XBM 360 model file

I believe it is a large container file with model and shader
Also in the game there are only 6 file type
And I have figure out every other one
Shaders are in a different file


```
    {
        char name[32];
        float matrix1[16];
        float chnk0[32]; //Bounding box??
        float chnk1[4];
        int chunk2[12];
        struct ShapeChunk
        {
            int i0;
            int i1;
            int i2;
            int i3;
            int i4;
            int i5; //Constant -65536
            int i6;
            int i7; //268435554, 268435746, 268435458
        }sChnk[3];
 
        //0 = -1s (random stuff)
        //1 = vertices floats
        //2 = Draw order? faces? shorts?
        //3 = addr in un02 header->(count,size,0,count)?
        //------------below are weird ints at the bottom of un03
        //4 =
        //5 =
        //6 =
        int addr[7];
        int chunk3[33];
    }shape[header.shapeCount];

```

//addr[3-6] points to what seems like vertex, normal etc.. I cant figure out size yet
## Post #6
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-12T06:58:59+00:00
- Post Title: XBM 360 model file

Progress!?!?!

So my guess was right to an extent
As you can see from the image I was able to read the bounding box and the object itself
[MagicBox.png](https://xentaxbackup.github.io/file/8253_MagicBox.png)
## Post #7
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-12T07:01:41+00:00
- Post Title: XBM 360 model file

The biggest problem was making sense of the triangles
There are many duplicate vertices (uses 24 vertices where 8 would suffice)
I haven't manually rendered an object since 2009 so this is insane to me
basically there is an chunk with vertex indices (shorts) that read in 4s (quads)
0,1,2,3,-1
4,5,6,7,-1
.......,
n-3,n-2,n-1, -1

Where n is the number of vertices

This would be a nightmare for non primitive objects

I did the rendering in unity3d and I had to modify things manually cos i could not make sense of this (triangle strip?)

Anyone willing to educate me?


Sorry! I'm an idiot Just remember Line and triangle strips
[VertOrder.png](https://xentaxbackup.github.io/file/8258_VertOrder.png)
## Post #8
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-12T08:10:26+00:00
- Post Title: XBM 360 model file

So this is what is looks like
I the object was called Magic Box and existed in a folder called effects
I can only imagine this is the reason for so many verts that cross each other inside the  mesh
I have also figure out how to automate the data reading
All I need now is u,v and normals
[triangle v line.png](https://xentaxbackup.github.io/file/8259_triangle v line.png)
## Post #9
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-15T12:59:53+00:00
- Post Title: XBM 360 model file

Why would a vertex weight come in x,y,z format and not just 1 floating point value per bone?
## Post #10
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-17T02:16:04+00:00
- Post Title: XBM 360 model file

Got everything but UVs
[model.png](https://xentaxbackup.github.io/file/8293_model.png)
## Post #11
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-18T13:42:49+00:00
- Post Title: XBM 360 model file

So I think I found the UV coordinates
Basically the only file section i havent touched so far.
And to my surprise it is something unreal

I think the uv's are stored as halves or shorts or am I Nuts?
Or maybe they aren't even uvs

Only files with textures have this section with data other than 0xFFFF

```
{
    int pad0;
    hfloat a;
    hfloat b;
} ud[number of verts];

```

[uv.png](https://xentaxbackup.github.io/file/8301_uv.png)
## Post #12
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-01-03T01:47:29+00:00
- Post Title: XBM 360 model file

I can't believe I am still stuck trying to figure out the UV for this game
I have Identified the data chunk but I still cannot understand how it is represented. It is really depressing
