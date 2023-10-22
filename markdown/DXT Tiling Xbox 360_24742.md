## Post #1
- Username: TKFRvision
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2021-11-16T17:30:09+00:00
- Post Title: DXT Tiling Xbox 360

Hey guys,
does anybody know how to tile and untile a dxt5 from the xbox 360?
Its working with noesis but I want to develop a standalone script for a number of reasons.
Thanks.
## Post #2
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-11-18T14:29:02+00:00
- Post Title: DXT Tiling Xbox 360

Don't know about tiling but to untile you can check Gildor's code here [https://github.com/gildor2/UEViewer/blo ... e.cpp#L519](https://github.com/gildor2/UEViewer/blob/86bd93f1dffba6c98a3acc8f08a59e662e32ccd6/Unreal/UnrealMaterial/UnTexture.cpp#L519)
## Post #3
- Username: TKFRvision
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2021-11-18T17:51:14+00:00
- Post Title: DXT Tiling Xbox 360

Thank you so much...
## Post #4
- Username: TKFRvision
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2021-11-19T08:21:05+00:00
- Post Title: DXT Tiling Xbox 360

> Reply from Joschka ↑Thu Nov 18, 2021 10:29 pm at Thu Nov 18, 2021 10:29 pm
>
> 
Don't know about tiling but to untile you can check Gildor's code here https://github.com/gildor2/UEViewer/blo ... e.cpp#L519

It does work with dxt5 tho? (I'm just asking because in noesis there is a difference between raw texture data and dxt)
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-11-19T11:58:51+00:00
- Post Title: DXT Tiling Xbox 360

@TKFRvision: UntileCompressedXbox360Texture will return untiled image (compressed or not), it's up to you to decide what to do with the result. Also, noesis supports untiling as well through the following functions:

```
{"imageUntile360DXT", Noesis_ImageUntile360DXT, METH_VARARGS, "returns untiled dxt pixel data. (Oiii)"}, //args=source image array, width, height, block size (e.g. 8 for dxt1, 16 for dxt5)
```

They are already available via api like this (example for DXT5):

```
rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
```
