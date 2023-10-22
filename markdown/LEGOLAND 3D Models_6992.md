## Post #1
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2011-07-17T06:49:25+00:00
- Post Title: LEGOLAND 3D Models

I am looking for a way to render and view the 3D models from the game LEGOLAND. Any help is greatly appreciated. 

Download LEGOLAND 3D Models: [http://www.multiupload.com/1A3EO3FNRW](http://www.multiupload.com/1A3EO3FNRW)
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-17T19:36:25+00:00
- Post Title: LEGOLAND 3D Models

> Reply from gaming1233
>
> I am looking for a way to render and view the 3D models from the game LEGOLAND. Any help is greatly appreciated. 

Download LEGOLAND 3D Models: http://www.multiupload.com/1A3EO3FNRWthis is quickbms extractor for PC Version.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get OFFSET long
get SIZE asize
math SIZE -= OFFSET
log MEMORY_FILE OFFSET SIZE
set NAME string ""
set PATH string ""
callfunction EXTRACT

startfunction EXTRACT
    string PATH += NAME
    string PATH += /
    for
        padding 4 MEMORY_FILE
        get ENTRY1 long MEMORY_FILE
        get ENTRY2 long MEMORY_FILE
        get TYPE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get OFFSET long MEMORY_FILE
        get NAME string MEMORY_FILE
        if TYPE == 0
            set FNAME string PATH
            string FNAME += NAME
            log FNAME OFFSET SIZE
        else
            if ENTRY1 != -1
                goto ENTRY1 MEMORY_FILE
                callfunction EXTRACT
            endif
        endif
        if ENTRY2 == -1
            break
        endif
        goto ENTRY2 MEMORY_FILE
    next
endfunction
```


about importer to blender,max I trying search but can't found it yet, not sure somebody release or not, the mesh format is .3D right? ok anyway I still looking for it too.
## Post #3
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2011-07-21T09:09:17+00:00
- Post Title: LEGOLAND 3D Models

I had a closer look at the 3D files. Looks like they contain short
3d animation sequences for lego figures. The files are in little endian.

The first dword in the file is the number of frames. For each frame there 
are x vertices and y unknown additional tripel of floats (maybe normals, etc), 
but I didnt check. 

x != n*y n element of integer
n(fileA) != n(fileB)

After the frames there are the indices that define the triangles. Each index
is used for each frame!

At the end of the file there is some meta data for the triangles. I think
there are colors and uv-values deposed.

```
{
  dword           dwCntFrames;
  struct frame    sFrames[dwCntFrames];
  dword           dwCntTriangles;
  dword           dwCntUnknown;
  struct triangle sTriangles[dwCntTriangles];
  struct meta     sMeta[dwCntTriangles];
};

struct frame
{
  dword           dwCntVerices;
  struct vertex   sVertices[dwCntVerices];
  dword           dwCntUnknown;
  struct vertex   sUnknown[dwCntVerices];
};

struct triangle
{
  dword           dwI1;
  dword           dwI2;
  dword           dwI3;
};

struct meta
{
  dword           dwUnknown;
  byte            bRed;
  byte            bGreen;
  byte            bBlue;
  byte            bUnknown; //FF
  dword           dwUnknown;
  struct uv       sUV[3];
};

struct vertex
{
  float           fX;
  float           fY;
  float           fZ;
};

struct uv
{
  dword           dwU;
  dword           dwV;
};

```
