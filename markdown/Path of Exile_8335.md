## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T20:44:56+00:00
- Post Title: Path of Exile

[http://www.progamercity.net/game-files/ ... #post22723](http://www.progamercity.net/game-files/2143-info-path-exile-ggpk-resources.html#post22723)

Would someone like to grab some files and upload them? Learn something new while you're at it.
## Post #2
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-05-25T21:11:58+00:00
- Post Title: Path of Exile

Just reviving this topic:

SkeletonKnight1

I'll post the current script in a few days when I have some free time to improve it.

Those willing to help can pm me for it, the rest of you won't benefit from it for now and it seems a lot of people never read past the first page and keep asking why scripts don't work.
## Post #3
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-05-26T21:14:10+00:00
- Post Title: Path of Exile

Edit: Removed script: Grinding Gear Games has asked not to release this.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-05-27T03:59:49+00:00
- Post Title: Path of Exile

well maybe this can be help.
[Path of Exile GGPK Extractor + Source by BrahminRamen.zip](https://xentaxbackup.github.io/file/5467_Path of Exile GGPK Extractor + Source by BrahminRamen.zip)
## Post #5
- Username: dnmnbg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 14, 2010 4:22 am
- Post datetime: 2013-01-21T06:00:09+00:00
- Post Title: Path of Exile

how to use the extractor? the game goes live in 2days
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-01-28T19:42:49+00:00
- Post Title: Path of Exile

Just use the Visual GGPK program, it has a graphics interface.
(After it you can use the 3D Object Converter v5.001)
[VisualGGPK.zip](https://xentaxbackup.github.io/file/6150_VisualGGPK.zip)
## Post #7
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2013-11-06T14:56:14+00:00
- Post Title: Path of Exile

By the way, Object Convertor does not open models from the last versions of the client, seems that they changed something since beta.
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-11-06T17:35:17+00:00
- Post Title: Path of Exile

> Reply from Axolotl
>
> By the way, Object Convertor does not open models from the last versions of the client, seems that they changed something since beta.

When I wrote and released the .smd loader module (Jan 28, 2013) the game was in the Open Beta stage and was released some days ago.
[http://en.wikipedia.org/wiki/Path_of_Exile](http://en.wikipedia.org/wiki/Path_of_Exile)

Unfortunately they changed the .smd file formats. I rewrote the .smd loader module based on the new .smd files a week ago.

I uploaded the v5.302 version to my web page:
[http://3doc.i3dconverter.com/downloads/ ... rtable.zip](http://3doc.i3dconverter.com/downloads/3doc_v5.302_portable.zip)
## Post #9
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-11-27T12:41:47+00:00
- Post Title: Path of Exile

Has anyone studied the new .smd format?

here template for [http://www.sweetscape.com/010editor/](http://www.sweetscape.com/010editor/)

```
    wchar_t data[size/2];
} STRING_BLOCK <read=ReadBlockBytes>;

string  ReadBlockBytes(STRING_BLOCK &block) {
    local string s;
    SPrintf(s, "%s",  block.data);
    return s;
};

struct FILE {
    struct HEADER{
        byte version <format=hex>;
        uint numIdx;
        uint numVert;
        byte prop_0;
        byte numMeshes;
        byte prop_2;
        uint totalStringLength;
        float boundingBox[6];
        struct MESH {
            uint meshNameLen;
            uint meshUnkProp;
        } mesh[numMeshes];
    } header;
    // SetBackColor (0xB0B090);
    struct STRINGS {
        local int i <hidden=true>;
        for ( i = 0 ; i < header.numMeshes; i++ )
        {
            STRING_BLOCK data(header.mesh[i].meshNameLen) <open=suppress>;
        }
    } strings;
    
    ushort indexBuffer[header.numIdx * 3];  

    struct VERTEX{
        float x <bgcolor=0xC0F0C0>, y <bgcolor=0xC0F0C0>, z <bgcolor=0xC0F0C0>;  // 0-12 rapi.rpgBindPositionBufferOfs
        byte unk0[8]; // 12-20
        hfloat u <bgcolor=0xA0D0A0>,v <bgcolor=0xA0D0A0>; // 20-24 rapi.rpgBindUV1BufferOfs
        byte boneIndex[4] <bgcolor=0xF0D0A0>; // 24-28 rapi.rpgBindBoneIndexBufferOfs
        byte unk1[4] <bgcolor=0xA0D0F0>; // 28-32
    } vertex[header.numVert]; // 32

} file;

```


if anyone can help with byte unk0[8] and byte unk1[4], i would be grateful ...

Samples here - [http://rghost.net/59294501](http://rghost.net/59294501)

Extractor here (bin) - [http://rghost.net/59294616](http://rghost.net/59294616)
Extractor here (src) - [https://github.com/MuxaJIbI4/libggpk](https://github.com/MuxaJIbI4/libggpk)
