## Post #1
- Username: eLTeh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 27, 2021 11:43 am
- Post datetime: 2023-01-17T03:09:25+00:00
- Post Title: Fire Emblem Engage Asset Ripping (.tex)

Need help with Fire Emblem Engage textures. They appear to be swizzled, and existing tools don't work on them. The format (according to AssetStudio) is ASTC_RGB_8x8. 

Tools I've tried:
- Raw Texture Cooker doesn't support the ASTC format
- UnityTexTool doesn't seem to decompress properly, throwing an error of "Got error:Non-negative number required. Parameter name: count". 

Attached below is one of the Albedo textures for Leif. Any help would be appreciated. If someone can tell me how the ASTC_RGB_8x8 format works, I can hopefully try coding something, but I have no idea where to start when it comes to swizzling.

Edit: uploaded the raw .tex file instead since it may contain more information
[oBody_Lei0AM_c532_Albedo.zip](https://xentaxbackup.github.io/file/23308_oBody_Lei0AM_c532_Albedo.zip)
## Post #2
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2023-01-18T18:36:08+00:00
- Post Title: Fire Emblem Engage Asset Ripping (.tex)

Maybe someone on reddit or serenesforest knows.

[https://www.reddit.com/r/fireemblem/com ... g_artwork/](https://www.reddit.com/r/fireemblem/comments/10dpgec/all_fe_engage_cg_artwork/)
[https://forums.serenesforest.net/index. ... lers-ahoy/](https://forums.serenesforest.net/index.php?/topic/97641-engage-leak-thread-caution-spoilers-ahoy/)
## Post #3
- Username: foulveins
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 7:19 am
- Post datetime: 2023-01-18T21:00:49+00:00
- Post Title: Fire Emblem Engage Asset Ripping (.tex)

i posted a python script by a friend on the fire emblem hacking discord: [https://discord.gg/CuHtq2aJFj](https://discord.gg/CuHtq2aJFj)

it does require manual editing of the .toml file for resolution & compression type, but other than that, it works flawlessly
## Post #4
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2023-01-19T18:58:35+00:00
- Post Title: Fire Emblem Engage Asset Ripping (.tex)

I made a quick Noesis script for these ASTC_8_8 textures, not going to support every format under the sun but it should be more than enough for all the character related ones. Just open the .bundles and if there are textures they'll get decoded/unswizzled [https://github.com/Joschuka/fmt_shovelw ... velware.py](https://github.com/Joschuka/fmt_shovelware/blob/main/fmt_shovelware.py)
## Post #5
- Username: nekoknight
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 31, 2018 10:27 am
- Post datetime: 2023-02-04T20:04:25+00:00
- Post Title: Fire Emblem Engage Asset Ripping (.tex)

> Reply from Joschka ↑Fri Jan 20, 2023 2:58 am at Fri Jan 20, 2023 2:58 am
>
> 
I made a quick Noesis script for these ASTC_8_8 textures, not going to support every format under the sun but it should be more than enough for all the character related ones. Just open the .bundles and if there are textures they'll get decoded/unswizzled https://github.com/Joschuka/fmt_shovelw ... velware.py

Unfortunately, this script does not seem to be able to extract the "multi" texture from the character bases/outfits. It extracts the head ones but not the body ones. This missing texture is to separate the different material types from what I can tell.
