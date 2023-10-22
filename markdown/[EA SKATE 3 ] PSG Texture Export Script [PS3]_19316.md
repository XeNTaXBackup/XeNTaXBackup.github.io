## Post #1
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-13T16:02:10+00:00
- Post Title: [EA SKATE 3 ] PSG Texture Export Script [PS3]

This script is for NOESIS and exports 99% of the Skate 3 .psg Textures without a problem.
Download is attached!
[tex_EA_Skate_3_psg_Fixed.zip](https://xentaxbackup.github.io/file/15471_tex_EA_Skate_3_psg_Fixed.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-15T01:26:53+00:00
- Post Title: [EA SKATE 3 ] PSG Texture Export Script [PS3]

cool, your height and width variables should be swapped though, 
and add this to the conditions too 

```
    elif imgFmt == 0xa5:
        texFmt = noesis.NOESISTEX_RGBA32

```
## Post #3
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-15T02:54:36+00:00
- Post Title: [EA SKATE 3 ] PSG Texture Export Script [PS3]

> Reply from Acewell
>
> cool, your height and width variables should be swapped though, 
and add this to the conditions too 
Code: Select all    #RGBA8888
    elif imgFmt == 0xa5:
        texFmt = noesis.NOESISTEX_RGBA32

Thanks!  I knew it was something haha. I'll fix it right away.
