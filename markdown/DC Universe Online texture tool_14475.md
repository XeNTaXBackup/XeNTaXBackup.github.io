## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-16T16:03:24+00:00
- Post Title: DC Universe Online texture tool

Beta version of the tool. I have some ideas how to extract only highest mips and get names, but for now, this is how it works.

Drag TFC file onto the EXE and it will extract all textures. They will have no names, but luckily, textures here are all organized, like NPC/characters/world and diffuse/normal/spec maps separated.


[DC_Universe_tfc.rar](https://xentaxbackup.github.io/file/11066_DC_Universe_tfc.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-16T16:03:57+00:00
- Post Title: DC Universe Online texture tool

Example of full-size image.
## Post #3
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-06-16T22:49:28+00:00
- Post Title: DC Universe Online texture tool

Great work, dude! Just gave it a whirl then! Already got a bunch I was hunting!
## Post #4
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2016-06-23T10:47:32+00:00
- Post Title: DC Universe Online texture tool

Thanks a lot man! superb work!
P.S Does this work on UI icons?
Edit: Yes,it works,but after i drag-n-drop UI1-4.tfc files i got programm crash,in a most cases.
+ All extracted images are strange a little...
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-24T04:06:33+00:00
- Post Title: DC Universe Online texture tool

ok i will look into that
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-28T15:12:51+00:00
- Post Title: DC Universe Online texture tool

I checked that. Most of UI textures are plain RGB, or exotic resolutions like 2048x64. So without a proper function to calculate the hash I can't detect compression type and image size. So this is currently impossible.
## Post #7
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2016-07-04T14:11:38+00:00
- Post Title: DC Universe Online texture tool

Thats pretty sad   but thanks for checking.
And can you make massive batch converter for tfc files? because convert only 1 file isn't comfortable
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-04T15:01:02+00:00
- Post Title: DC Universe Online texture tool

> Reply from Rutabaga
>
> Thats pretty sad   but thanks for checking.
And can you make massive batch converter for tfc files? because convert only 1 file isn't comfortable

you can make .bat file. google how to mass convert with batch files.
## Post #9
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2017-04-19T01:11:11+00:00
- Post Title: DC Universe Online texture tool

Thank you for making this tool. Sorry for bumping an old topic, I'm new to 3d modeling/skinning, and I wanted to know will a tool like this be incorporated into UModel one day?
I'm curious to know whether the UModel author has any knowledge of this, or maybe this is outside the program's primary function. 
I don't know the technical side of it, so my question maybe a bit naive.
I had to search quite a bit to discover this tool existed. 
Let's hope this tool gets more attention, because there are quite a few people who seemed to have given up on ripping the models, especially the somewhat new models 

```
http://orig08.deviantart.net/7906/f/2016/189/7/3/red_lantern___bleez_dcuo_3d_model_by_joeshouseofart-da960xw.jpg
```


Thanks again, for making life easier.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-21T19:44:02+00:00
- Post Title: DC Universe Online texture tool

> Reply from Curtain
>
> and I wanted to know will a tool like this be incorporated into UModel one day?

I dont think so. This is workaround tool. Umodel has no use for it.
## Post #11
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2017-12-06T20:37:40+00:00
- Post Title: DC Universe Online texture tool

I noticed a strange behavior in the Blender viewport when using these textures within Blender.

I did a little comparison test between the textures created by DC Universe Online Texture Tool and Ninja Ripper.

Textures Extracted by DC Universe Online Texture Tool:
Material Shading - Shows Image Texture
Texture Shading - Shows Image Texture
Rendered Shading - Pink Texture (usually means Blender can't locate texture file)
- The image texture will only render correctly after I click 'Pack All into .blend'

Textures Ripped by Ninja Ripper:
Material Shading - Shows Image Texture
Texture Shading - Shows Image Texture
Rendered Shading - Shows Image Texture
- Rendered correctly without needing to save/pack image into .blend

I'm wondering if all the textures from the DCUO texture tool have become partially corrupt.
--
For the test, I used Blender 2.79 Cycles renderer and used nodes for the material.
Image Texture --> Diffuse Shader --> Material Output
Both Ninja Ripper and DCUO texture tool are using .dds texture format.

EDIT - I opened up the image textures in xnview and noticed all the extracted textures from the DCUO texture tool were showing DXT1, not sure how important that is but it was the only other detail that was different from the Ninja Ripped textures.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-07T17:17:02+00:00
- Post Title: DC Universe Online texture tool

DC Universe Online Texture Tool has NO WAY to know the texture format or size. So it can be incorrect on any given texture.
## Post #13
- Username: DovahWolfVII
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 29, 2018 8:35 am
- Post datetime: 2020-08-03T04:22:40+00:00
- Post Title: DC Universe Online texture tool

i know this post is old AF but can anyone help me Rip the inside and outside of the Teen Titans Tower maps?
