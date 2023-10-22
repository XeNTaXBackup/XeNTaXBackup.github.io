## Post #1
- Username: MaxBOOST
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 07, 2023 10:20 am
- Post datetime: 2023-08-07T02:34:49+00:00
- Post Title: Can someone help me convert these files to .bmp

So, I managed to extract the assets of an unpopular game (Moorhuhn Adventure 2: Der Fluch des Goldes), but I can't seem to get the files opened.

Can someone help me convert them to some sort of common format like a png or a bmp ?

i have attached a link to a zip containing said assets.
[https://drive.google.com/file/d/1001vId ... sp=sharing](https://drive.google.com/file/d/1001vId_FjGlY9IgWyHcHIzkzLTpRNHjh/view?usp=sharing)
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-08-21T00:54:32+00:00
- Post Title: Can someone help me convert these files to .bmp

The data in "g/img/in_All.img" starting at 2F2D1h looks like RGB triplets (8-bits per component) with some RLE or back reference compression, since the rows do not align, but  you'll probably have to debug through the decompression code to figure it out...
[Moorhuhn-Adventure-2-Der-Fluch-des-Goldes-inv_All.png](https://xentaxbackup.github.io/file/24254_Moorhuhn-Adventure-2-Der-Fluch-des-Goldes-inv_All.png)
## Post #3
- Username: MaxBOOST
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 07, 2023 10:20 am
- Post datetime: 2023-08-21T06:58:20+00:00
- Post Title: Can someone help me convert these files to .bmp

> Reply from piken ↑Mon Aug 21, 2023 8:54 am at Mon Aug 21, 2023 8:54 am
>
> 
The data in "g/img/in_All.img" starting at 2F2D1h looks like RGB triplets (8-bits per component) with some RLE or back reference compression, since the rows do not align, but  you'll probably have to debug through the decompression code to figure it out...

you're probably correct, but you did get close. The image you got strongly resembles one of the game assets in there, just miscolored.
## Post #4
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-08-22T08:40:29+00:00
- Post Title: Can someone help me convert these files to .bmp

Some images appear uncompressed using 8-bit indices with 32-bit RGBX palette (e.g. invApfel._img), and others appear to have multiple images contained in them (e.g. inv_Lf._img), and some have names in them (e.g. "Small Font, Gray" in fntGray._img). In invApfel._img, it appears the dimensions 50x50 are stored early in the header, as 0x32 (01 00 00 00 01 00 00 00 32 00 00 00 32 00 00 00) plus 2 bytes of row-stride padding (probably to round up to 32-bits). Overall the format doesn't appear that consistent, except for the reliable "FF 00 FF 00 FF FF FF FF FF FF FF FF" pattern at 0x0016. I'd start with the uncompressed ones, like invApfel._img and invAbacus._img first. Good luck .
[Moorhuhn-Adventure-2-Der-Fluch-des-Goldes-invApfel.png](https://xentaxbackup.github.io/file/24256_Moorhuhn-Adventure-2-Der-Fluch-des-Goldes-invApfel.png)
## Post #5
- Username: MaxBOOST
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 07, 2023 10:20 am
- Post datetime: 2023-08-22T21:18:42+00:00
- Post Title: Can someone help me convert these files to .bmp

> Reply from piken ↑Tue Aug 22, 2023 4:40 pm at Tue Aug 22, 2023 4:40 pm
>
> 

thanks a million man, will credit you for all of this
## Post #6
- Username: MaxBOOST
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 07, 2023 10:20 am
- Post datetime: 2023-08-25T05:54:55+00:00
- Post Title: Can someone help me convert these files to .bmp

> Reply from piken ↑Tue Aug 22, 2023 4:40 pm at Tue Aug 22, 2023 4:40 pm
>
> 

what do you suggest i do for the files that have multiple images in them
