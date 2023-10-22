## Post #1
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2017-02-13T12:01:26+00:00
- Post Title: Super Runabout .MODL

Hello guys,

As the only way to rip a Dreamcast model is by running the game in demul 057 (which doesn't transform Z axis properly) and you get a skewed model that can be barely used, a friend of mine helped me crack the .MODL format used in Super Runabout 2000 for the Dreamcast. Here's what he figured out so far:

```
float x;
float y;
float z;
}Vector3;

typedef struct {
float x;
float y;
}Vector2;

typedef struct {
long chunkFileLength;
ushort chunkType;
ushort chunkLength;
if(chunkType == 4){
    byte junk[52];
    Vector3 vertices[chunkLength];
}else if(chunkType == 8){
    long unkshit;
    byte junk[20];
    Vector3 unk1;
    Vector3 unk2;
    byte moreJunk[8];
    ushort unk3;
    ushort unk4;
    byte evenMoreJunk[8];
    Vector2 vectorList[chunkLength];
    byte evenEvenMoreJunk[6];
}
}MODELCHUNK;

struct RunaboutModel {
char modelName[40];
Vector3 min;
Vector3 max;
float radius;
byte junk[8];

MODELCHUNK chunk1;
MODELCHUNK chunk2;


}RNBMDL;

```

He has a problem figuring out the data after the verticles. He says it is probably something simple, but he can't figure it out.

I also supplied the entire .CBN the .MODL files were extracted from. If needed I can send more samples. I have the textures ripped already too.


 CAR20_PATROL.zip
(37.72 KiB) Downloaded 15 times



Many thanks!
