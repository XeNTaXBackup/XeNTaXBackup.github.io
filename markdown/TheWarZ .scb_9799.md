## Post #1
- Username: x0rh4x
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 06, 2011 2:46 am
- Post datetime: 2012-10-28T15:19:07+00:00
- Post Title: TheWarZ .scb

Hello,

iam currently trying to load .scb files from WarZ.
I attached a .zip file with some model files. If someone could take a look at the file i would be more then thankful.

Heres everything i found for now(i never did something like that before):
[4 Bytes] magic [0x38 0x00 0xDC 0xFA]
[4 Bytes] null
[4 Bytes] Length of ObjectName (objLen)
[objLen] ObjectName

After that i have no clue whats going on 
Well, would be nice if someone could help me getting behind that format.

- x0rh4x.
[files.zip](https://xentaxbackup.github.io/file/5937_files.zip)
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-10-28T18:04:18+00:00
- Post Title: TheWarZ .scb

> Reply from x0rh4x
>
> Hello,
I attached a .zip file with some model files. If someone could take a look at the file i would be more then thankful.

Do you have a full game?
Unfortunately I did not find the demo version of this game on the Net.

I attached the converted files in Wavefront .obj/mtl format.
Unfortunately your package does not contain the texture files to check out the texture datas on the models.
[The_WarZ_scb_to_obj.zip](https://xentaxbackup.github.io/file/5938_The_WarZ_scb_to_obj.zip)
## Post #3
- Username: x0rh4x
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 06, 2011 2:46 am
- Post datetime: 2012-10-28T18:43:03+00:00
- Post Title: TheWarZ .scb

Yes i got the full game.
The game does not have a demo. But there is TheWarInc which is based on the same engine as far i know and its f2p.

I will send the textures via PM.

- x0rh4x.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-10-31T19:50:30+00:00
- Post Title: TheWarZ .scb

Vertex Size=44

[4 bytes] unknown
[4 bytes] unknown
[4 bytes] unknown
[4 bytes] Number of Vertices
Vertices*(X,Y,Z) position  //3 floats
Vertices*(U,V)    texture  //2 floats 
Vertices*(44-12-8 bytes)
Vertices*1 byte

[4 bytes] Number of Indices
Indices*(4 bytes)    

[4 bytes] Number of Face Groups
Face Groups* (4 bytes Indices from
                    4 bytes Indices Count
                   4 bytes Length of Material name  (without '.mat' file extension !)
                   String Material name)
## Post #5
- Username: Shizapp
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 13, 2012 1:21 am
- Post datetime: 2012-11-12T18:19:42+00:00
- Post Title: TheWarZ .scb

I'm trying to convert the hundreds of .scb files to .obj. I've tried using the scb2obj command-line converter but it is about 2 years old and doesn't work. I've also tried a maya plugin I found out there called the RiotFileTranslator and that doesn't work. How exactly did you convert these files and is there a way to do this in bulk?

Thanks!
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-11-12T18:42:54+00:00
- Post Title: TheWarZ .scb

> Reply from Shizapp
>
> How exactly did you convert these files and is there a way to do this in bulk?

I used the 3D Object Converter v5.0 developer version from [http://3dconverter.webege.com/develop_x86](http://3dconverter.webege.com/develop_x86)
