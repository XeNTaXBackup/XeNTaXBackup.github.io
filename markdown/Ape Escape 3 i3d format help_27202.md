## Post #1
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2023-09-14T18:25:57+00:00
- Post Title: Ape Escape 3 i3d format help

Hi,

I've been wanting to extract some models from the game but I've been having trouble converting the game's .i3d files into .obj format. I've tried using cmd.exe to run the Rule of Rose python script from murugo on the files and I've also tried dragging and dropping the files on the script like the creator said you can do, but nothing seems to work.

A user from models resource managed to extract and convert two models and they said "I modified a .mdl file from Rule of Rose to replace one of it's .i3d files with the .i3d file from Ape Escape 3 and I then used Murugo's mdl2obj.py to convert it to .obj."

I've tried using the Rule of Rose python script on the i3d files but I cannot get the script to work at all. Am I missing something here? Would anyone be able to look at the files and help out?

[https://www.mediafire.com/file/rf2dq4kt ... s.zip/file](https://www.mediafire.com/file/rf2dq4ktmnvmbbb/AE3%252Bscripts.zip/file)

I've put inside the zip the necessary scripts to convert (I hope that's not against the rules), and a sample file of the model I'd like to convert. Model should be pl_b_nin.i3d and the rest are a mix of texture files and animations I believe.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-15T05:21:44+00:00
- Post Title: Ape Escape 3 i3d format help

> Reply from Ayuvir ↑Fri Sep 15, 2023 2:25 am at Fri Sep 15, 2023 2:25 am
>
> 
Hi,Hi,

first things first: the py scripts you've uploaded contain rubbish (saved html data, whatever).
WHY not give the link to the original files?  
[https://github.com/Murugo/Misc-Game-Res ... 0of%20Rose](https://github.com/Murugo/Misc-Game-Research/tree/main/PS2/Rule%20of%20Rose)

> A user from models resource managed to extract and convert two models and they said "I modified a .mdl file from Rule of Rose to replace one of it's .i3d files with the .i3d file from Ape Escape 3 and I then used Murugo's mdl2obj.py to convert it to .obj."This user's idea is very clever!  

Tried it with pl_b_nin_child.i3d and...it works:
.



pl_b_nin_child-i3d.png (190.62 KiB) Viewed 137 times



Inserted said .i3d file into dia.mdl using a hex editor (overwrite existing I3D_BIN block).

How to use the script with python 3.0 (or above)::
- open console window (by executing cmd.exe).

- change dir to folder with python.exe and patched .mdl sample, then type
python mdl2obj.py dia-patched.mdl
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-09-15T10:15:47+00:00
- Post Title: Ape Escape 3 i3d format help

> Reply from Ayuvir ↑Fri Sep 15, 2023 2:25 am at Fri Sep 15, 2023 2:25 am
>
> 
.i3d files

just replace lines 241-243 in the original script with this: (and then dragndrop on  script your *.i3d or *.mdl)

```
    data = f.read()#ReadRpkFile(f, 1)[0x10:]
    f.close()
    
    startFile = data.find(b'I3D_BIN')
    if startFile == -1:
        err('file not have I3D_BIN!')
    buf = data[startFile+0x10:]

```

this will read the entire file and look for the I3D_BIN line, and if it is there it will build obj, *(note that not all provided *i3ds have this line, some I3D_I3M)


**I also made a quick adaptation for Noesis,( EDIT fix position mesh)
[fmt_i3dg.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_i3dg.py)



pl_b_nin.i3d.png (58.55 KiB) Viewed 88 times
## Post #4
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2023-09-15T20:35:32+00:00
- Post Title: Ape Escape 3 i3d format help

> **I also made a quick adaptation for Noesis,( EDIT fix position mesh)
>
> fmt_i3dg.py
>
> pl_b_nin.i3d.png

I can't thank you enough for this script, thanks a billion! It works wonders on Noesis
## Post #5
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2023-09-19T21:05:07+00:00
- Post Title: Ape Escape 3 i3d format help

Anyone looking to add support for bones and skinning yet? 
There's at least a bone reader here: [viewtopic.php?p=179144#p179144](https://forum.xentax.com/viewtopic.php?p=179144#p179144)
