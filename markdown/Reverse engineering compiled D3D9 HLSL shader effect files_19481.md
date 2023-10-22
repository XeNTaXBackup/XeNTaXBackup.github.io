## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2019-02-11T20:26:30+00:00
- Post Title: Reverse engineering compiled D3D9 HLSL shader effect files?

I have a game that has a bunch of compiled shader effect files (that get loaded via D3DXCreateEffectFromFileA from d3dx9_27.dll). They say they were compiled with "Microsoft (R) D3DX9 Shader Compiler 9.08.299.0000".
Does anyone know of any tools or tutorials or other things I can use to decompile or reverse engineer these shader effect files (I have a need to make them work on a newer version of Direct3D for some stuff I am doing)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-03-12T17:33:27+00:00
- Post Title: Reverse engineering compiled D3D9 HLSL shader effect files?

Try: fxdis d3d1x
I'm using it for DX10/11 shaders.
