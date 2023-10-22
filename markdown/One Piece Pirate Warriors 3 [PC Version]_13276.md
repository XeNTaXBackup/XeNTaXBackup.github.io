## Post #1
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2015-09-03T13:17:01+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

After playing the game for a week or something, i started playing around with the files yesterday, but i think i am stuck right now. Seems like the indices are not working quite well, but i can't figure out what is wrong. I am attaching some pics





Pretty much all the parts are good. This is happening on some of them and basically on the "large" ones. I've noticed no difference on the definition of the indices sections compared to the correct parts. I'm also taking care of the usual degenerates as the indices are defined in triangle strips.

Could those faces be degenerates as well? Could DirectX or OpenGL avoid rendering those ones? Maybe checking the area of the face, or the distance between the points. I can't think of something else.

i'm also attaching a sample from the indices section of this particular part.
[https://www.dropbox.com/s/gi6fmrpb1252b ... ample?dl=0](https://www.dropbox.com/s/gi6fmrpb1252bmd/oppw3_indices_sample?dl=0)

Any help is highly appreciated.
## Post #2
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2015-09-05T22:01:25+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

Case solved, i figured out what the problem was myself.
I also found the textures and how to read them properly (biggest pain in the ass than the indices), so i was able to construct some full models to get some decent renders.

Here we go
[](http://imgur.com/ojtFlWq)
[](http://imgur.com/LtAEzA6)
[](http://imgur.com/7RE9gnp)
[](http://imgur.com/LbOhXTS)
[](http://imgur.com/h2diFMx)


Some more dev info as well for anyone who is interested in the game

From what i found there are 2 ways that models are distributed within the game.

1) The embedded models are in LINKDATA_EU_OS_EUNA.A. This is how most of the models are distributed but there is a problem. Model files don't come together with the corresponding textures, and from what i found out, there is absolutely no correspondence bewtween them archivewise.
2) The DLC models. These are the .bin files that are located within the FILE_DX9/DLC folder. Whatever file starts with a COS its a costume. The good thing with those files is that they contain everything, geometry and textures (i did not have the time to check about skeletons yet). The file structure is EXACTLY the same with the way that the embedded files work, they are just packed together in a single file, and that of course makes the texture work much much easier.


I've also wrote a small python script which extracts the files from the large game archives. With some additional checks i can check if the files contain textures or not, but apart from that there is no way to know on which model they correspond. 


Anyway everything is still a WIP. I'll use this topic for more news on this.
## Post #3
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2015-09-08T04:53:14+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

First of all, i have no idea if there is a tool or a bms script already available for extracting the files out of the archives. Anyway i am sharing mine here. Simply drag n drop one of the LINKDATA_EU_OS_EUNA.X files on the executable, it will create a new folder and put all the extracted files in there. It may have some problems with some of the files, but i am not sure about what is wrong. On EUNA.A there is no error at all, and there are 3000+ files in there.

[Download](http://www.mediafire.com/download/ompdwxadjppucwq/oppw3_unpacker.7z)

I'm finishing the importer. I need to write the GUI still. I've found some material information but nothing more than that. So i am trying to organize it as much as possible.
## Post #4
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-09-08T06:45:53+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

Cool beans. Does this game have the same issue with "flappy" meshes that other "Warriors" games have (Hyrule Warriors for example) that collapses stuff like ponytails, cloaks and such?
## Post #5
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2015-09-08T13:23:56+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

> Reply from ssringo
>
> Cool beans. Does this game have the same issue with "flappy" meshes that other "Warriors" games have (Hyrule Warriors for example) that collapses stuff like ponytails, cloaks and such?

Yes thats still an issue, and i have no idea how to solve it. And the most weird part is that not all meshes are like that, for example, female breast model, ponytails or some hair parts are just out of place. You can place them correctly though with some very certain rotation (like 180 degrees Y and -90 on Z, stuff like that).
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-09-09T00:31:06+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

if you aren't afraid of shader model assembly, i can give you the vertex shader for the cloth.

this is what we know so far:

1. cloth control points are stored in NUNO and NUNV chunks.
2. cloth anchor points in the vertex buffer have lots of zeroes in them (anchor points = the cloth points that attach to model).
3. the NUNO and NUNV data is transformed and sent to the vertex shader (in a constant buffer, vCtrl, look at shader code).
4. and out poops your cloth.
5. all you need to do is write an interpreter for this code.

```
// Generated by Microsoft (R) HLSL Shader Compiler 9.29.952.3111
//
// Parameters:
//
//   float bMatIdx;
//   bool bSkin[2];
//   float4 mL2W[96];
//   float4x4 mW2P;
//   float4 vCtrl[96];
//
//
// Registers:
//
//   Name         Reg   Size
//   ------------ ----- ----
//   bSkin        b0       2
//   mL2W         c0      96
//   vCtrl        c96     96
//   mW2P         c192     4
//   bMatIdx      c196     1
//

    vs_3_0
    def c197, 0, 1, 0, 0
    def c198, -0, -3, -6, -9
    dcl_position v0
    dcl_blendweight v1
    dcl_binormal v2
    dcl_color1 v3
    dcl_blendindices v4
    dcl_psize v5
    dcl_fog v6
    dcl_texcoord5 v7
    dcl_normal v8
    dcl_texcoord v9
    dcl_position o0
    dcl_texcoord o1
    dcl_texcoord1 o2.xy
    dp4 r0.x, v5, v5
    slt r0.x, c197.x, r0.x
    mov r0.yzw, v4.xxyz
    mova a0.w, r0.z
    mul r1.xyz, v0.y, c96[a0.w].zxyw
    mova a0.w, r0.y
    mad r1.xyz, v0.x, c96[a0.w].zxyw, r1
    mova a0.w, r0.w
    mad r1.xyz, v0.z, c96[a0.w].zxyw, r1
    mov r1.w, v4.w
    mova a0.w, r1.w
    mad r1.xyz, v0.w, c96[a0.w].zxyw, r1
    mov r2, v5
    mova a0.w, r2.y
    mul r3.xyz, v0.y, c96[a0.w].zxyw
    mova a0.w, r2.x
    mad r3.xyz, v0.x, c96[a0.w].zxyw, r3
    mova a0.w, r2.z
    mad r3.xyz, v0.z, c96[a0.w].zxyw, r3
    mova a0.w, r2.w
    mad r3.xyz, v0.w, c96[a0.w].zxyw, r3
    mov r3.w, v6.x
    mov r4.x, v6.y
    mova a0.w, r4.x
    mul r4.yzw, v0.y, c96[a0.w].xzxy
    mova a0.w, r3.w
    mad r4.yzw, v0.x, c96[a0.w].xzxy, r4
    mov r5.xy, v6.zwzw
    mova a0.w, r5.x
    mad r4.yzw, v0.z, c96[a0.w].xzxy, r4
    mova a0.w, r5.y
    mad r4.yzw, v0.w, c96[a0.w].xzxy, r4
    mov r5.zw, v7.xyxy
    mova a0.w, r5.w
    mul r6.xyz, v0.y, c96[a0.w].zxyw
    mova a0.w, r5.z
    mad r6.xyz, v0.x, c96[a0.w].zxyw, r6
    mov r6.w, v7.z
    mova a0.w, r6.w
    mad r6.xyz, v0.z, c96[a0.w].zxyw, r6
    mov r7.x, v7.w
    mova a0.w, r7.x
    mad r6.xyz, v0.w, c96[a0.w].zxyw, r6
    mul r7.yzw, r3.xyzx, v1.y
    mad r7.yzw, v1.x, r1.xyzx, r7
    mad r7.yzw, v1.z, r4.xzwy, r7
    mad r7.yzw, v1.w, r6.xyzx, r7
    mul r3.xyz, r3, v3.y
    mad r1.xyz, v3.x, r1, r3
    mad r1.xyz, v3.z, r4.yzww, r1
    mad r1.xyz, v3.w, r6, r1
    mova a0.w, r0.z
    mul r3.xyz, v2.y, c96[a0.w].yzxw
    mova a0.w, r0.y
    mad r3.xyz, v2.x, c96[a0.w].yzxw, r3
    mova a0.w, r0.w
    mad r0.yzw, v2.z, c96[a0.w].xyzx, r3.xxyz
    mova a0.w, r1.w
    mad r0.yzw, v2.w, c96[a0.w].xyzx, r0
    mova a0.w, r2.y
    mul r3.xyz, v2.y, c96[a0.w].yzxw
    mova a0.w, r2.x
    mad r3.xyz, v2.x, c96[a0.w].yzxw, r3
    mova a0.w, r2.z
    mad r2.xyz, v2.z, c96[a0.w].yzxw, r3
    mova a0.w, r2.w
    mad r2.xyz, v2.w, c96[a0.w].yzxw, r2
    mova a0.w, r4.x
    mul r3.xyz, v2.y, c96[a0.w].yzxw
    mova a0.w, r3.w
    mad r3.xyz, v2.x, c96[a0.w].yzxw, r3
    mova a0.w, r5.x
    mad r3.xyz, v2.z, c96[a0.w].yzxw, r3
    mova a0.w, r5.y
    mad r3.xyz, v2.w, c96[a0.w].yzxw, r3
    mova a0.w, r5.w
    mul r4.xyz, v2.y, c96[a0.w].yzxw
    mova a0.w, r5.z
    mad r4.xyz, v2.x, c96[a0.w].yzxw, r4
    mova a0.w, r6.w
    mad r4.xyz, v2.z, c96[a0.w].yzxw, r4
    mova a0.w, r7.x
    mad r4.xyz, v2.w, c96[a0.w].yzxw, r4
    mul r2.xyz, r2, v1.y
    mad r0.yzw, v1.x, r0, r2.xxyz
    mad r0.yzw, v1.z, r3.xxyz, r0
    mad r0.yzw, v1.w, r4.xxyz, r0
    mul r2.xyz, r0.yzww, r1
    mad r0.yzw, r1.xzxy, r0.xzwy, -r2.xxyz
    mad r1.xyz, v8.w, r0.yzww, r7.yzww
    mov r1.w, c197.y
    lrp r2, r0.x, r1, v0
    mad r1, r0.x, -v4, v4
    lrp r3.xyz, r0.x, c197.yxxw, v1
    mov r0.x, c197.x
    slt r0.x, r0.x, c196.x
    add r1, r1, c198
    mul r0, r0.x, r1
    mova a0.w, r0.x
    dp4 r1.x, r2, c0[a0.w]
    mova a0.w, r0.x
    dp4 r1.y, r2, c1[a0.w]
    mova a0.w, r0.x
    dp4 r1.z, r2, c2[a0.w]
    mul r4.xyz, r3.x, r1
    if b1
      mova a0.w, r0.y
      dp4 r5.x, r2, c3[a0.w]
      mova a0.w, r0.y
      dp4 r5.y, r2, c4[a0.w]
      mova a0.w, r0.y
      dp4 r5.z, r2, c5[a0.w]
      mad r6.xyz, r3.y, r5, r4
      mova a0.w, r0.z
      dp4 r7.x, r2, c6[a0.w]
      mova a0.w, r0.z
      dp4 r7.y, r2, c7[a0.w]
      mova a0.w, r0.z
      dp4 r7.z, r2, c8[a0.w]
      mad r6.xyz, r3.z, r7, r6
      add r0.x, -r3.x, c197.y
      add r0.x, -r3.y, r0.x
      add r0.x, -r3.z, r0.x
      mova a0.w, r0.w
      dp4 r7.x, r2, c9[a0.w]
      mova a0.w, r0.w
      dp4 r7.y, r2, c10[a0.w]
      mova a0.w, r0.w
      dp4 r7.z, r2, c11[a0.w]
      mad r6.xyz, r0.x, r7, r6
      lrp r2.xyz, r3.x, r1, r5
    else
      mova a0.w, r0.y
      dp4 r5.x, r2, c3[a0.w]
      mova a0.w, r0.y
      dp4 r5.y, r2, c4[a0.w]
      mova a0.w, r0.y
      dp4 r5.z, r2, c5[a0.w]
      mad r0.xyw, r3.y, r5.xyzz, r4.xyzz
      add r1.w, -r3.x, c197.y
      add r1.w, -r3.y, r1.w
      mova a0.w, r0.z
      dp4 r3.x, r2, c6[a0.w]
      mova a0.w, r0.z
      dp4 r3.y, r2, c7[a0.w]
      mova a0.w, r0.z
      dp4 r3.z, r2, c8[a0.w]
      mad r6.xyz, r1.w, r3, r0.xyww
      mov r2.xyz, r1
    endif
    if b0
      mov r2.xyz, r6
    endif
    dp4 r0.x, r2, c192
    dp4 r0.y, r2, c193
    dp4 r0.z, r2, c194
    dp4 r0.w, r2, c195
    mov o0, r0
    mov o1, r0
    mov o2.xy, v9

// approximately 164 instruction slots used

```


For example, the last 7 lines is a matrix multiplication (the 4 dp4's mW2P c192 is the modelview-perspective matrix), followed by a copy of the vertex data to the output registers (the 3 mov's).



You can even have my entire G1M code (that works with many PS3 and XBox360 DW, SW, and OP/KM titles). Pay attention to the NUNO and NUNV stuff. The boob transform issue is located in the bone palette data, and you can figure that out by looking at chrrox's Hyrule Warriors script.


 x_dw_g1m.7z
(12.68 KiB) Downloaded 186 times
## Post #7
- Username: Milonex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 06, 2015 10:16 pm
- Post datetime: 2015-10-06T18:20:40+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

Hey !

How did you extract 3D Models ? I tried a lot of things, but never got the 3D Models, I've got texture, complete scene etc... but I cannot access 3DModels :/
## Post #8
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2015-11-26T11:49:15+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

> Reply from gregkwaste
>
> Case solved, i figured out what the problem was myself.
I also found the textures and how to read them properly (biggest pain in the ass than the indices), so i was able to construct some full models to get some decent renders.

Here we go







Some more dev info as well for anyone who is interested in the game

From what i found there are 2 ways that models are distributed within the game.

1) The embedded models are in LINKDATA_EU_OS_EUNA.A. This is how most of the models are distributed but there is a problem. Model files don't come together with the corresponding textures, and from what i found out, there is absolutely no correspondence bewtween them archivewise.
2) The DLC models. These are the .bin files that are located within the FILE_DX9/DLC folder. Whatever file starts with a COS its a costume. The good thing with those files is that they contain everything, geometry and textures (i did not have the time to check about skeletons yet). The file structure is EXACTLY the same with the way that the embedded files work, they are just packed together in a single file, and that of course makes the texture work much much easier.


I've also wrote a small python script which extracts the files from the large game archives. With some additional checks i can check if the files contain textures or not, but apart from that there is no way to know on which model they correspond. 


Anyway everything is still a WIP. I'll use this topic for more news on this.

Could you please post the tools and a tutorial for getting the 3d models please.
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-01-08T11:48:56+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

Hi
Here is a blend file for import models from this game.

How use:

1.install Blender 249 and Python 266
2.doubleclick Blender249.blend
3.in Blender Text Window press alt+p and select any file without extension like '1507' from unpacked archive  and wait until script find and rename all files with meshes.
4.one more time press alt+p and select any g1m file for importing meshes
5.models in Blender 3d View are original grouped . To see group select object like "1-armature" and move (press key G)
6.cloth meshes are not supported .
[Blender249[OnePiecePirateWarriors3][PC][g1m][2016-01-08].zip](https://xentaxbackup.github.io/file/10281_Blender249[OnePiecePirateWarriors3][PC][g1m][2016-01-08].zip)
## Post #10
- Username: fondly
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 30, 2016 12:59 pm
- Post datetime: 2016-07-02T00:18:31+00:00
- Post Title: One Piece Pirate Warriors 3 [PC Version]

> Reply from gregkwaste
>
> First of all, i have no idea if there is a tool or a bms script already available for extracting the files out of the archives. Anyway i am sharing mine here. Simply drag n drop one of the LINKDATA_EU_OS_EUNA.X files on the executable, it will create a new folder and put all the extracted files in there. It may have some problems with some of the files, but i am not sure about what is wrong. On EUNA.A there is no error at all, and there are 3000+ files in there.

Download

I'm finishing the importer. I need to write the GUI still. I've found some material information but nothing more than that. So i am trying to organize it as much as possible.

How to extract DLC *.BIN files?
