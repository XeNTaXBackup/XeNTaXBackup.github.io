## Post #1
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2014-12-23T03:49:37+00:00
- Post Title: Request Shining Resonance extract or view .MLX format

Has anyone know open or veiw .MLX format? 
I search all .MLX related thread. But found few information or The contents of this post was deleted because of possible forum rules violation. 
And noesis support .MLX?  I'm using 4.1.2 ver
## Post #2
- Username: ativsp
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Sep 16, 2012 5:48 pm
- Post datetime: 2014-12-25T03:09:10+00:00
- Post Title: Request Shining Resonance extract or view .MLX format

It seems the tools for Valkyria Chronicle is not working for this game.
I tried mlx import plugin for Blender, but error.
Maybe we have to wait until someone makes new tools for it.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-26T15:50:29+00:00
- Post Title: Request Shining Resonance extract or view .MLX format

> Reply from ativsp
>
> It seems the tools for Valkyria Chronicle is not working for this game.depends on.
At least you can get the textures and an HMDL file:



face.JPG (24.94 KiB) Viewed 340 times



Reading parts of IZCA file.
start      size       type
Section 0
0x00000040 0x00000050 MLX0
Section 1
0x000000a0 0x00165de0 HMDL
0x00165ea0 0x001e09e0 HTEX
0x003468a0 0x000001f0 DCOL

Opening HTEX file: J:\tmp\blender_a03044\s01_f001.HTEX
Loading image: J:\tmp\blender_a03044\00-3c3245cc.dds
Loading image: J:\tmp\blender_a03044\01-4ba1af5f.dds
Loading image: J:\tmp\blender_a03044\02-c10389e1.dds
Loading image: J:\tmp\blender_a03044\03-87b9fa25.dds
Loading image: J:\tmp\blender_a03044\04-6113c515.dds
Loading image: J:\tmp\blender_a03044\05-fc5b56d9.dds
Loading image: J:\tmp\blender_a03044\06-854c2bf7.dds
Loading image: J:\tmp\blender_a03044\07-d3a70199.dds
Loading image: J:\tmp\blender_a03044\08-63d3daad.dds
Loading image: J:\tmp\blender_a03044\09-fb413c52.dds
Loading image: J:\tmp\blender_a03044\10-ecd5cbac.dds
Loading image: J:\tmp\blender_a03044\11-fed62a53.dds
Loading image: J:\tmp\blender_a03044\12-174a91ae.dds
Loading image: J:\tmp\blender_a03044\13-ec3876be.dds
Loading image: J:\tmp\blender_a03044\14-d056fb7f.dds
Loading image: J:\tmp\blender_a03044\15-af445982.dds
Loading image: J:\tmp\blender_a03044\16-4a21263f.dds
Loading image: J:\tmp\blender_a03044\17-dfaf2bf4.dds
Loading image: J:\tmp\blender_a03044\18-dce4b7e4.dds
Opening HMDL file: J:\tmp\blender_a03044\s01_f000.HMDL
Reading parts of HMDL file: J:\tmp\blender_a03044\s01_f000.HMDL
start      size       type
0x00000020 0x000cc1d0 KFMD
0x00000040 0x00012390 KFMS
0x00011e50 0x00000390 POF1
0x00012200 0x00000130 ENRS
0x00012350 0x00000020 CCRS
0x00012390 0x00000020 MTXS
0x000123d0 0x00000000 EOFC
0x000123f0 0x000b9de0 KFMG
0x000cc100 0x00000040 ENRS
0x000cc160 0x00000020 CCRS
0x000cc1a0 0x00000010 WIRS
0x000cc1d0 0x00000000 EOFC
0x000cc1f0 0x00000000 EOFC
0x000cc210 0x00099bb0 KFMD
0x000cc230 0x00011fe0 KFMS
0x000ddca0 0x00000380 POF1
0x000de040 0x00000130 ENRS
0x000de190 0x00000020 CCRS
0x000de1d0 0x00000020 MTXS
0x000de210 0x00000000 EOFC
0x000de230 0x00087b70 KFMG
0x00165ce0 0x00000030 ENRS
0x00165d30 0x00000020 CCRS
0x00165d70 0x00000010 WIRS
0x00165da0 0x00000000 EOFC
0x00165dc0 0x00000000 EOFC

Then there's an error, yes.

But for me it's not worth solving this since chrrox seems to be working on Shining Resonance.MLX.
## Post #4
- Username: lovemarin
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Sep 14, 2014 10:40 am
- Post datetime: 2015-04-04T09:26:06+00:00
- Post Title: Request Shining Resonance extract or view .MLX format

> Reply from ativsp
>
> It seems the tools for Valkyria Chronicle is not working for this game.
I tried mlx import plugin for Blender, but error.
Maybe we have to wait until someone makes new tools for it.
I wonder whether a mlx import plugin for neosis exsits
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-05T14:44:55+00:00
- Post Title: Request Shining Resonance extract or view .MLX format

I'm pretty sure it does - on a forum member's harddrive.  

Here's an obj file where the submeshes were created using hex2obj (a really tedious task, will try to improve it):


 DL020A._obj.zip
(188.45 KiB) Downloaded 58 times


(cut her finger, sry, some SMes had to be scaled up manually)
## Post #6
- Username: lovemarin
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Sep 14, 2014 10:40 am
- Post datetime: 2015-04-07T11:59:22+00:00
- Post Title: Request Shining Resonance extract or view .MLX format

> Reply from shakotay2
>
> I'm pretty sure it does - on a forum member's harddrive.  

Here's an obj file where the submeshes were created using hex2obj (a really tedious task, will try to improve it):
DL020A._obj.zip
(cut her finger, sry, some SMes had to be scaled up manually)

WoW, thanks for uploading it   This is indeed a tough work
