## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-05-28T03:14:08+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

So I tried using the OpenSAGE Blender plugin as Westwood 3D/SAGE is based off SurRender 3D, but since it was heavily modified I wasn't surprised that it didn't work at all. So yeah, could anyone look into these formats?

Couldn't attach them here so here's some samples:
[https://www51.zippyshare.com/v/28Az6PEB/file.html](https://www51.zippyshare.com/v/28Az6PEB/file.html)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-28T11:51:02+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

> Reply from huckleberrypie ↑Sat May 28, 2022 11:14 am at Sat May 28, 2022 11:14 am
>
> 
here's some samples
using hex2obj



BADLANDS_RNDR03.MDL.png (38.28 KiB) Viewed 172 times
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-05-29T00:20:38+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

> Reply from Durik256 ↑Sat May 28, 2022 7:51 pm at Sat May 28, 2022 7:51 pm
>
> 
huckleberrypie wrote: ↑Sat May 28, 2022 11:14 am
here's some samples

using hex2obj
BADLANDS_RNDR03.MDL.png

How complex is the format tho?
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-29T13:22:22+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

> Reply from huckleberrypie ↑Sun May 29, 2022 8:20 am at Sun May 29, 2022 8:20 am
>
> 
How complex is the format tho?
hard for what?
I didn't even try to understand the format. just found vertex and faces.
## Post #5
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-05-29T13:58:05+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

> Reply from Durik256 ↑Sun May 29, 2022 9:22 pm at Sun May 29, 2022 9:22 pm
>
> 
huckleberrypie wrote: ↑Sun May 29, 2022 8:20 am
How complex is the format tho?

hard for what?
I didn't even try to understand the format. just found vertex and faces.

I presume the format's simple enough to decipher, yes?
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-29T17:28:32+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

> Reply from huckleberrypie ↑Sun May 29, 2022 9:58 pm at Sun May 29, 2022 9:58 pm
>
> 
I presume the format's simple enough to decipher, yes?
Yes it is. if you have minimal experience in this then it will not be difficult for you to make a plugin.

well, so far I have made plugin. (without parsing the format. keyword search)  

edit: add "fmt_MDL_HARLY_UVS.py" plugin with uvs.
[fmt_MDL_HARLY.zip](https://xentaxbackup.github.io/file/22277_fmt_MDL_HARLY.zip)
## Post #7
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-05-31T03:28:16+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

Here's hoping someone would make an export plugin for this and other SurRender 3D games lel. Especially as I wanted to see if it's worth modding it not.
## Post #8
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-06-07T01:27:38+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

Also, it appears as though the extracted files have all the materials condensed in one, and it would be a pain and a half to separate all of them UVs. Anyone willing to make a Blender plugin of some kind?
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-07T18:23:54+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

> Reply from huckleberrypie ↑Tue Jun 07, 2022 9:27 am at Tue Jun 07, 2022 9:27 am
>
> 
Also, it appears as though the extracted files have all the materials condensed in one, and it would be a pain and a half to separate all of them UVs.

textures should be one directory up in the "images" folder.
example:
path models >> "D:\Games\Harley-Davidson\bin"
path textures >> "D:\Games\Harley-Davidson\images"

[fmt_MDL_HARLY.zip](https://xentaxbackup.github.io/file/22334_fmt_MDL_HARLY.zip)
## Post #10
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-06-08T02:08:38+00:00
- Post Title: Harley-Davidson - Race Across America SurRender 3D formats (.ANM/.BSP/.CSP/.MDL)

> Reply from Durik256 ↑Wed Jun 08, 2022 2:23 am at Wed Jun 08, 2022 2:23 am
>
> 
huckleberrypie wrote: ↑Tue Jun 07, 2022 9:27 am
Also, it appears as though the extracted files have all the materials condensed in one, and it would be a pain and a half to separate all of them UVs.


textures should be one directory up in the "images" folder.
example:
path models >> "D:\Games\Harley-Davidson\bin"
path textures >> "D:\Games\Harley-Davidson\images"

Alright,thanks!
