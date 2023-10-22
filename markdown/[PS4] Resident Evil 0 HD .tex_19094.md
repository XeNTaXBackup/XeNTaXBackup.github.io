## Post #1
- Username: Crazy Potato
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 26, 2018 11:56 am
- Post datetime: 2018-11-20T22:22:16+00:00
- Post Title: [PS4] Resident Evil 0 HD .tex

[https://www.mediafire.com/file/c1x7p296 ... 0.rar/file](https://www.mediafire.com/file/c1x7p296p5eyaba/PS4_RE0.rar/file)

I'm not sure if it's the .tex (textures) or .arc that's different from the pc version's file format so I'm going to post in both sections here on XeNTaX.

No Matter what I do I can't seem to convert the .tex extension thought maybe one you guys have an idea as to why, The .rar contains ps4 .arc and two extracted from different bats which are PC and PS3 (Using FluffyQuack's ArcTool)
## Post #2
- Username: javurek91
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Feb 09, 2014 9:29 pm
- Post datetime: 2018-11-21T17:35:57+00:00
- Post Title: [PS4] Resident Evil 0 HD .tex

Hi, PS4 textures are swizzled, you must use RawTextureCooker. You must set 0xOFFSET at 68 a tick PS4 swizzle and BC1 (DXT1), then drag and drop .tex file at program and hit Try and convert. It generate viewable .DDS file  If you want know more send me PM
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-11-22T08:09:33+00:00
- Post Title: [PS4] Resident Evil 0 HD .tex

that offset will vary depending on how many mipmaps are stored in the file,
and not all of the images are dxt1, i have seen ati1 (bc4) also, there could be others.
i could make a Noesis script if i knew how the width and height was being calculated.  

edit
got it! i just borrowed from the MTFramework header specs by Zheneq here  
[https://raw.githubusercontent.com/Zhene ... 3ds_tex.py](https://raw.githubusercontent.com/Zheneq/Noesis-Plugins/master/fmt_mtframework_3ds_tex.py)

here is Noesis python script to open your PS4 tex samples  


 tex_ResidentEvil0HD_PS4_tex.zip
(1006 Bytes) Downloaded 120 times


supports PS4 swizzled dxt1, dxt5 and ati1
## Post #4
- Username: Crazy Potato
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 26, 2018 11:56 am
- Post datetime: 2018-11-23T15:22:18+00:00
- Post Title: [PS4] Resident Evil 0 HD .tex

> Reply from Acewell
>
> that offset will vary depending on how many mipmaps are stored in the file,
and not all of the images are dxt1, i have seen ati1 (bc4) also, there could be others.
i could make a Noesis script if i knew how the width and height was being calculated.  

edit
got it! i just borrowed from the MTFramework header specs by Zheneq here  
https://raw.githubusercontent.com/Zhene ... 3ds_tex.py

here is Noesis python script to open your PS4 tex samples  
tex_ResidentEvil0HD_PS4_tex.zip
supports PS4 swizzled dxt1, dxt5 and ati1
Thanks, With this I manged to mod the PS4 version
## Post #5
- Username: darkshirata
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 18, 2018 7:31 pm
- Post datetime: 2018-12-16T12:44:40+00:00
- Post Title: [PS4] Resident Evil 0 HD .tex

hi can you make the same thing for resident evil 6 ?
## Post #6
- Username: Big Boss
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 31, 2020 9:10 am
- Post datetime: 2020-05-20T06:09:50+00:00
- Post Title: [PS4] Resident Evil 0 HD .tex

Please help me, I have a problem, I extract the textures from the RE HD, and the RE0 HD Xbox 360 without problems, however, when I reimport, even without being edited, those with _MM.TEX, are buggy, that in the Xbox 360 version, they extract in .TGA, and are reimported without problems, with the exception of those with _MM.TGA, when they are reimported, they bug, break, and when you put them in the game, it gets buggy, or it extracts again it gets buggy, even if it doesn't edit them, extract them and reimport them, they bug, break, blur, I don't know what to do, .TXT file of them, when extracted are as follows:
TEX
Format = DXT5A
Mips = 8
Textype = 25
The sizes vary for each texture, how can I solve this problem? Can someone help me?
I'm just having problems with this type !, the others are normal, can someone help me?
