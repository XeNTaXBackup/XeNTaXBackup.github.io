## Post #1
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-11-09T09:16:33+00:00
- Post Title: TGA map abnormal file

TGA地图是加密的，就像一个游戏引擎自定义格式。有人能解密它并将其转换成正常的图像格式吗？
[http://xxa.wanmei.com/](http://xxa.wanmei.com/)
样本文件：

[https://mega.nz/](https://mega.nz/)#！K34WnYgB！uqQS7lI2blHB.cltu7XGX08
## Post #2
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-11-09T14:37:02+00:00
- Post Title: TGA map abnormal file

Hi!

Did I understand correctly that the APK file of the game is called com.pwrd.xxajh.huawei and weighs about 2GB?
If so, this TGA is stored in .pak files inside "assets" folder, right?
## Post #3
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-11-09T15:07:21+00:00
- Post Title: TGA map abnormal file

> Reply from aspadm ↑Sat Nov 09, 2019 10:37 pm at Sat Nov 09, 2019 10:37 pm
>
> 
Hi!

Did I understand correctly that the APK file of the game is called com.pwrd.xxajh.huawei and weighs about 2GB?
If so, this TGA is stored in .pak files inside "assets" folder, right?

Hello, yes, so the files are stored in media2.PAk, media3.pak
## Post #4
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-11-09T15:35:02+00:00
- Post Title: TGA map abnormal file

For me it looks like this is the in-game texture format, just named ERA, but with TGA extension. At least, game library have some functions like "Texture::_parser_era" (in one row with "Texture::_parser_pvr" and "Texture::_parser_dds").

I'll try to write a decoder, but do not promise something.
## Post #5
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-11-09T15:43:27+00:00
- Post Title: TGA map abnormal file

> Reply from aspadm ↑Sat Nov 09, 2019 11:35 pm at Sat Nov 09, 2019 11:35 pm
>
> 
For me it looks like this is the in-game texture format, just named ERA, but with TGA extension. At least, game library have some functions like "Texture::_parser_era" (in one row with "Texture::_parser_pvr" and "Texture::_parser_dds").

I'll try to write a decoder, but do not promise something.

Thank you for your help and look forward to your good news.
## Post #6
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-11-11T16:18:30+00:00
- Post Title: TGA map abnormal file

> Reply from aspadm ↑Sat Nov 09, 2019 11:35 pm at Sat Nov 09, 2019 11:35 pm
>
> 
For me it looks like this is the in-game texture format, just named ERA, but with TGA extension. At least, game library have some functions like "Texture::_parser_era" (in one row with "Texture::_parser_pvr" and "Texture::_parser_dds").

I'll try to write a decoder, but do not promise something.

Hi friend, what's the latest
## Post #7
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-11-11T23:25:00+00:00
- Post Title: TGA map abnormal file

Hi!

After some research, I detected, that this is ASTC texture compression with custom header.
I'll polish the script and post it some hours later.
Main reason is that there are can be cubemap textures, so I want to support it.

Example of "c_257_cj_he.tga"
## Post #8
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-11-12T01:27:21+00:00
- Post Title: TGA map abnormal file

Hi, you're fantastic. Look forward to it!
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-11-13T02:13:52+00:00
- Post Title: TGA map abnormal file

here is a quick Noesis python script to open your samples until aspadm releases his complete solution.  


 tex_XiaoAoJiangHu_Android_tga.zip
(637 Bytes) Downloaded 38 times


supports astc 6x6, top level mip only
## Post #10
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-11-13T07:02:05+00:00
- Post Title: TGA map abnormal file

Thank you. It's amazing.
## Post #11
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-11-14T13:36:29+00:00
- Post Title: TGA map abnormal file

Sorry for make you waiting so long. This is the corrected version of Noesis python script, that supports texture with several layers (e.g. cubemaps) and with differrent block sizes.
[tex_XiaoAoJiangHu_Android_tga.zip](https://xentaxbackup.github.io/file/17055_tex_XiaoAoJiangHu_Android_tga.zip)
## Post #12
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-11-15T01:57:43+00:00
- Post Title: TGA map abnormal file

Thank you and acewell for helping me. Solved my big problem!
## Post #13
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2020-09-01T17:02:50+00:00
- Post Title: TGA map abnormal file

> Reply from Acewell ↑Wed Nov 13, 2019 10:13 am at Wed Nov 13, 2019 10:13 am
>
> 
here is a quick Noesis python script to open your samples until aspadm releases his complete solution.   
tex_XiaoAoJiangHu_Android_tga.zip
supports astc 6x6, top level mip only

Hi, there, Acewell. Could you take a look at this for me? This is an Android exported PNG map, but it doesn't display properly. It's probably encrypted. SAMPLE FILE: [https://mega.nz/file/72iwtcrl#g9orr1k68 ... as5yetqhyu](https://mega.nz/file/72iwtcrl#g9orr1k68mxtfhs0xdmvfjndwyliz1rypas5yetqhyu)
