## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-21T11:11:09+00:00
- Post Title: Puss in Boots (Xbox 360) Textures

Hi. I am looking at some textures from this xbox 360 game. Extensionless files are the headers and files with ".data" contain the actual image data. Color textures "_c" seem to be DXT1 but they are not coming out perfect. There are some artifacts. I don't know if this is a xbox thing, or something else. I hope someone with more experience can help with it. Samples are attached to the post.

This is what I got with TextureFinder :


[pib_360_texsamples.7z](https://xentaxbackup.github.io/file/17763_pib_360_texsamples.7z)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-03-21T18:18:49+00:00
- Post Title: Puss in Boots (Xbox 360) Textures

artifacts are shown in texture finder because X360 images are big endian.
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-21T19:25:45+00:00
- Post Title: Puss in Boots (Xbox 360) Textures

> Reply from Acewell ↑Sun Mar 22, 2020 2:18 am at Sun Mar 22, 2020 2:18 am
>
> 
artifacts are shown in texture finder because X360 images are big endian.

Oh yeah, makes perfect sense  Should have thought of that. I can just make a quick script for Noesis I guess. Thanks a lot.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-03-23T04:59:44+00:00
- Post Title: Puss in Boots (Xbox 360) Textures

here is a quick Noesis python script based on the small sample size.  


 tex_PussInBoots_X360_data.zip
(718 Bytes) Downloaded 24 times


supports big endian dxt1 and dxt5, top level mip only.
open the *.data file and the script will find the extensionless header file if
they are next to each other.
