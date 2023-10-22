## Post #1
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2010-10-26T21:42:20+00:00
- Post Title: Decompile/or Decrypt a Microsoft DirectX 9 compiled shader?

Hi   
Thank you for your research.
Im using QuickBMS for unpacking pack files. its great software 
After unpacking, i encountered with a microsoft DirectX 9.0 shader file that is compiled and i can not read it !
As you know, GPU Shaders are text (Shader is such as a C program)
But this file is encrypted. i did open it with HEXEditor and i did found that the encrypted file is result of compiling shader but im not sure yet. Its some days that im trying with no success.
Can anyone help me how can i decompile the shader file?

Thank you for your attention.
H.Ahmadi
[Character_cloth.rar](https://xentaxbackup.github.io/file/3557_Character_cloth.rar)
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-10-26T23:58:07+00:00
- Post Title: Decompile/or Decrypt a Microsoft DirectX 9 compiled shader?

Not possible to decompile a shader. It might be possible to disassemble a shader back into shader assembly though.

Shaders get compiled from HLSL (the shader programming language you refer to in your post) into shader bytecode by the Microsoft Shader Compiler.
It is this shader bytecode that gets fed to the GPU.
## Post #3
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2010-10-27T07:09:30+00:00
- Post Title: Decompile/or Decrypt a Microsoft DirectX 9 compiled shader?

> Reply from jfwfreo
>
> Shaders get compiled from HLSL (the shader programming language you refer to in your post) into shader bytecode by the Microsoft Shader Compiler.
It is this shader bytecode that gets fed to the GPU.
In my renderer engine(Ogre3D), i can use HLSL,CG,GLSL, Assembly shader.
Im familar only with CG,HLSL .

> Reply from jfwfreo
>
> It might be possible to disassemble a shader back into shader assembly though.
However it's not bad, Can you help me how can i do that? To i use the shader in RenderMonkey ?
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-10-28T21:18:49+00:00
- Post Title: Decompile/or Decrypt a Microsoft DirectX 9 compiled shader?

You could always try to find a reference paper about the assembler codes.
## Post #5
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2010-10-29T05:46:01+00:00
- Post Title: Decompile/or Decrypt a Microsoft DirectX 9 compiled shader?

> Reply from Rheini
>
> You could always try to find a reference paper about the assembler codes.
First, I must convert the compiled shader file to assembly! But how can i do that? Any tools?
## Post #6
- Username: shakotay
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 29, 2010 5:43 am
- Post datetime: 2010-11-09T09:39:34+00:00
- Post Title: Decompile/or Decrypt a Microsoft DirectX 9 compiled shader?

> Reply from Ahmadi
>
> Rheini wrote:You could always try to find a reference paper about the assembler codes.
First, I must convert the compiled shader file to assembly! But how can i do that? Any tools?

You could use [http://www.deep-shadows.com/hax/3DRipperDX.htm](http://www.deep-shadows.com/hax/3DRipperDX.htm) on a DirectX 9 game.
It creates psh files which contain assembly like this

```
    mov_pp r0.y, v4.w
    texld_pp r0, r0, s4
    texldp_pp r1, v1, s6
    dp4_sat_pp r0.w, r1, c5
    add_pp r0.w, -r0.w, -c37.y
    mul_sat_pp r0.y, r0.y, r0.w

```


(Or you might google for gpu shader analyzer. There is a tool from AMD: [http://developer.amd.com/gpu/shader/Pages/default.aspx](http://developer.amd.com/gpu/shader/Pages/default.aspx)
Did not test this - maybe you're lucky and there is a decompiler contained.)
## Post #7
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2010-11-15T11:04:03+00:00
- Post Title: Decompile/or Decrypt a Microsoft DirectX 9 compiled shader?

> Reply from shakotay
>
>  
(Or you might google for gpu shader analyzer. There is a tool from AMD: http://developer.amd.com/gpu/shader/Pages/default.aspx
Did not test this - maybe you're lucky and there is a decompiler contained.)
Hi
Thank you for your attention.
The AMD Shader Analyzer haven't any feature for decompiling shader (no luck).
I did very googling but no success to now 

[http://www.google.com/search?hl=en&clie ... er&spell=1](http://www.google.com/search?hl=en&client=opera&hs=gVx&rls=en&&sa=X&ei=FxLhTIaWC4yEhQenj_igDQ&ved=0CBAQBSgA&q=gpu+shader+decompiler&spell=1)

Fun : Almost all result of my google search is only this thread on this forum!   

Unfortunately 3DRipperDX only work with DirectX 9 and have some issues with some games.

Thanks
H.Ahmadi
