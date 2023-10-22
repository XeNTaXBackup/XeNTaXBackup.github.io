## Post #1
- Username: hirosin237
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 02, 2022 11:49 am
- Post datetime: 2023-01-17T06:52:16+00:00
- Post Title: Fire Emblem Engage 2D Texture Glitch

I dumped the FE Engage rom, from there I extracted the files via UAE.
Unity version is 2020.3.18f1.

There is one problem, meshes and bones can be exported (FBX) normally, but the textures have glitches. I don't know which method to use.
check this file(Exported PNG file)
[https://drive.google.com/file/d/1_LiETc ... sp=sharing](https://drive.google.com/file/d/1_LiETcST6cdS0F_SEBrO52nLVoRZKR0p/view?usp=sharing)


 uhair_h103.zip
Extraction (137.12 KiB) Downloaded 17 times



I uploaded some files to Google Drive.

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1r6fXfQWQok870aHA3KS_wlMjWj6hjS2y?usp=sharing)
## Post #2
- Username: lcilmlp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 22, 2023 2:17 am
- Post datetime: 2023-01-21T18:40:36+00:00
- Post Title: Fire Emblem Engage 2D Texture Glitch

I had the same problem unpacking Engage resources, so I wrote a python script to handle it.
[https://github.com/CherishingWish/MyToo ... ain/Engage](https://github.com/CherishingWish/MyTool/tree/main/Engage)
here the texture you provide originally look like
[https://github.com/CherishingWish/MyToo ... Albedo.png](https://github.com/CherishingWish/MyTool/blob/main/Engage/new_uBody_Sdp0AF_c559_Albedo.png)
## Post #3
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2023-01-21T20:13:22+00:00
- Post Title: Fire Emblem Engage 2D Texture Glitch

> Reply from lcilmlp ↑Sun Jan 22, 2023 2:40 am at Sun Jan 22, 2023 2:40 am
>
> 
I had the same problem unpacking Engage resources, so I wrote a python script to handle it.
https://github.com/CherishingWish/MyToo ... ain/Engage
here the texture you provide originally look like
https://github.com/CherishingWish/MyToo ... Albedo.png

Tried using this with my extracted textures just to test it, but says...

```
Traceback (most recent call last):
  File "I:\Nintendo Rips\Switch\Fire Emblem Engage\Secure\Romfs\1.1.0\Engage_Tex_2048.py", line 2, in <module>
    import numpy as np
ModuleNotFoundError: No module named 'numpy'
```


Update: figured it out, now to figure out how to update it for smaller sized textures like 256 and 512
## Post #4
- Username: classyham
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 24, 2021 5:30 am
- Post datetime: 2023-01-22T00:26:25+00:00
- Post Title: Fire Emblem Engage 2D Texture Glitch

Dumb question, but what UAE are you talking about? Not found a tool matching that name that works with FEE.
## Post #5
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2023-01-22T04:12:33+00:00
- Post Title: Fire Emblem Engage 2D Texture Glitch

This is normal for switch games made in unity cause they are swizzled.

Lucky, there's just a solution here with this plugin for UABEA that can deswizzle them, toghether with this program.

[https://filechan.org/qeFbm2Tfy3/UABEA_7z](https://filechan.org/qeFbm2Tfy3/UABEA_7z)
[TexturePlugin.zip](https://xentaxbackup.github.io/file/23335_TexturePlugin.zip)
## Post #6
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2023-01-22T19:55:45+00:00
- Post Title: Fire Emblem Engage 2D Texture Glitch

> Reply from MrYouKnowItAll ↑Sun Jan 22, 2023 12:12 pm at Sun Jan 22, 2023 12:12 pm
>
> 
This is normal for switch games made in unity cause they are swizzled.

Lucky, there's just a solution here with this plugin for UABEA that can deswizzle them, together with this program.

https://filechan.org/qeFbm2Tfy3/UABEA_7zWell that came in handy big time! It just has issues with textures that's 64x4 sizes, but otherwise works as needed.
## Post #7
- Username: seteth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 17, 2022 11:06 am
- Post datetime: 2023-01-23T16:17:42+00:00
- Post Title: Fire Emblem Engage 2D Texture Glitch

[https://github.com/Joschuka/fmt_shovelware](https://github.com/Joschuka/fmt_shovelware) + [https://richwhitehouse.com/index.php?co ... project=91](https://richwhitehouse.com/index.php?content=inc_projects.php&showproject=91)

This has worked pretty well for me.
## Post #8
- Username: Neostatos4
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 18, 2015 10:55 pm
- Post datetime: 2023-01-28T16:17:44+00:00
- Post Title: Fire Emblem Engage 2D Texture Glitch

The plugin seem to work well with UABE but I don't see a batch process button to extract more than one at a time, it would be possible to adapt it for AS 0.16.47 ? AS extract the 3d model but with glitched textures yet, if it could do both, it would be very cool. 
It is really good already, not complaining, just asking if such convenient adaptation could be made to make it a hundred time faster.
