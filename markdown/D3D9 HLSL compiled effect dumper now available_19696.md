## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2019-03-22T07:55:29+00:00
- Post Title: D3D9 HLSL compiled effect dumper now available

I have taken the source code to the ReactOS d3dx9_36.dll (which is based on the Wine d3d9_36.dll and contains code that parses D3D9 HLSL compiled effect files) and added some code that dumps the information contained therein into a text file. I then wrote a tool to use the new code.
[https://github.com/jonwil/reactos/](https://github.com/jonwil/reactos/) contains my modified version of the ReactOS source code.
this [https://mega.nz/#!y4diUCDY!uj7RnecLbYFU ... 7ryi5xMiCI](https://mega.nz/#!y4diUCDY!uj7RnecLbYFUHPW-XHztR6VqNqDnfWzMF7ryi5xMiCI)
contains binaries of the needed compiled ReactOS dlls (d3dx9_36.dll and d3dwine.dll), the fxdump exe file and the various bits needed to compile fxdump.

To use the tool to dump a D3D9 HLSL effect file (which may have a .fx or .fxo extention) you put the dlls, exe and the fx shader file into a folder, then go there in a command prompt and type fxdump fxfile outfile where fxfile is the name of the compiled effect file and outfile is the name of a text file you want the output to go into. It has successfully dumped the .fx shader files from The Lord of the Rings: Battle For Middle Earth 2, Command & Conquer 3 Tiberium Wars and Red Alert 3.

It doesn't currently decode/dump the actual contents of preshaders, vertex shaders or pixel shaders but it will decode all the variables, structures, passes, techniques, samplers, annotations and states (provided there was an example of that exact set of data in one of the compiled shader files I tested with). This will only work with D3D9 compiled HLSL effects and not other things.

Anyone interested in setting more about what's inside compiled HLSL shader files, please have a play with this. And let me know if you encounter any files that make the program crash (which indicates either a bug in my code or a file containing data my tool doesn't handle yet) or any other issues or if you have any questions about this. If you find a shader that isn't working please send it my way so I can figure out why and fix it/improve the program.

Support for decoding/disassembling the actual shader code is something I want to do but since ReactOS/Wine doesn't have an implementation of D3DXDissassembleEffect or D3DXDisassembleShader I would have to do a lot more reverse engineering to figure out how to parse that data.

If you want to see the actual disassembled shader code for your shader, you can use fxc.exe from the Microsoft DirectX SDK (should be able to find a copy on Google, if not, I can point you in the right direction)

Hopefully this tool is of use to other people who want to poke around inside compiled D3D9 HLSL shader effect files.
## Post #2
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2021-03-16T12:27:04+00:00
- Post Title: D3D9 HLSL compiled effect dumper now available

Do you think it's possible to decompile Xbox 360 .fxo shaders (EA NHL). I tried to decompile NHL and command and conquer ([https://www.moddb.com/mods/chronoshaders](https://www.moddb.com/mods/chronoshaders)) fxo with fxdump, but nothing happened. Do you have example fx file which can be decompiled using fxdump?

Fxo from NHL (X360) in attachment.
[default.fxo.zip](https://xentaxbackup.github.io/file/19730_default.fxo.zip)
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2021-03-22T03:44:40+00:00
- Post Title: D3D9 HLSL compiled effect dumper now available

> Reply from Beedy ↑Tue Mar 16, 2021 8:27 pm at Tue Mar 16, 2021 8:27 pm
>
> 
Do you think it's possible to decompile Xbox 360 .fxo shaders (EA NHL). I tried to decompile NHL and command and conquer (https://www.moddb.com/mods/chronoshaders) fxo with fxdump, but nothing happened. Do you have example fx file which can be decompiled using fxdump?

Fxo from NHL (X360) in attachment.
You can disassemble them with D3DXDisassembleShader (The X360 variant).
