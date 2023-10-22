## Post #1
- Username: guardianlamppost
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 02, 2022 8:09 pm
- Post datetime: 2022-08-02T13:46:01+00:00
- Post Title: Requiem: Avenging Angel

I found this 2 decades old post about the subject and decided not to necro it. [viewtopic.php?f=10&t=847](https://forum.xentax.com/viewtopic.php?f=10&t=847)

I've been reverse engineering this old forgotten gem a couple of days now and have found some useful stuff. 

Models3.txt contains offsets for ReqArt3D.dat which in turn contains offsets to the compressed textures in ReqArt3D.art. 

A texture entry in ReqArt3D.art is structured as follows:

```
    u64  lenDecompressed;
    u32  lenCompressed;
    u8   compressedData[lenCompressed]; //(PKWARE DCL compression scheme)
};
```


The texture entry can be decompressed with [http://www.exelana.com/techie/c/ttdecomp.html](http://www.exelana.com/techie/c/ttdecomp.html). The decompressed data contains an 18 byte header containing the texture dimensions, among other things. Then follows a 256x32bpp color palette, which is finally followed by 8bpp pixel data.

I don't know how many people are interested in modding this game, but I thought I'd publish my findings somewhere at least.
## Post #2
- Username: guardianlamppost
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 02, 2022 8:09 pm
- Post datetime: 2022-08-04T19:17:28+00:00
- Post Title: Requiem: Avenging Angel

I made an application to extract all compressed textures into .bmp-files. Some of the textures are corrupted. I haven't looked further into this (I suspect animated textures?). 

The source code, written in rust, is available at: [https://github.com/NibbleOfAnOctet/ReqArt3DExtractor](https://github.com/NibbleOfAnOctet/ReqArt3DExtractor)
