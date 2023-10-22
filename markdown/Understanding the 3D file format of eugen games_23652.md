## Post #1
- Username: darkmil935
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 29, 2021 11:42 pm
- Post datetime: 2021-03-29T16:23:05+00:00
- Post Title: Understanding the 3D file format of eugen games

Hi everyone !
Before I ask my question I want to make sure I'm not breaking any rules.
I cannot upload game files, but can I upload some excerpts as examples to support the discussion ? (I'll be doing this in the next post if it's okay if not, I won't)

The game I'm attempting to mod is Wargame Red Dragon, and uses the IRISZoom engine developed by Eugen Systems. Some part (quite extensive actually) of the file formatting of the game has already been reverse engineered by others more talented than me. And some part of the file that contains the 3D models already is understood.
My goal is to edit the models (the texture are already editable and in another file).

The models are most probably contained in a .spk file (Of course file format is proprietary). This file contains the name of the files as, some informations about the bounding boxes and of course the vertex/edge/face/normal and I suppose UV information.
The part of the file that most probably contains the vertex informations is divided in several subsection beginning with a header beginning by the bytes VBUF most probably meaning vertex buffer, each of this subsection is itself divided in subsection with a header beginning with the bytes SUBP (4 or 6 of those subsection following a VBUF header)(a file resulting from the investigation of another player is available [here](https://docs.google.com/document/d/1H_esEcCmYAZqdk5u_DnB-PE2S2Fyn3Lt7LSxbepMyWQ/edit?usp=sharing) with more details, for the current matter only the J section is relevant)

We also know that the 3D file format which is used by the studio and imported in the game is ASE2NDFBIN, NDFBin being one of the file formatting used by the studio and being well understood. Those files are basicly  [.ASE files](http://www.solosnake.com/main/ase.htm) but formatted in NDFBin  

If I had to guess the VBUF subsection are associated with a given model and SUBP subsubsection represent different type of information (vertices, faces, edges, normals, UV, and empties would be my best guess) but so far I was unable to understand how the data are stored in those sections since I doesn't seem to be able to find float supposed to represent 3D coordinates and the data section of the subparts doesn't seem to be a mutliple of 3 (as I would except for the x, y and z coordinates)

As a note, I know how to use an Hex editor, I am quite proficient in Python and am familiar with 3D modeling using blender. 

As I am new at this game research business some advice are welcome to help me in my endeavour ! (I have more precise questions but sharing some excerpts of the file would be necessary so it'll wait for my next post if that's possible)

Have a nice day !

Darkmil
## Post #2
- Username: molotov6844
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 23, 2022 4:56 pm
- Post datetime: 2022-11-23T09:02:21+00:00
- Post Title: Understanding the 3D file format of eugen games

Hello, where are the 3d files stored? Eugene Systems provided us with plugins for 3ds max that lets us edit the Ane2NDF files. I was wondering if the same plugin would also work for wargame 3d models as theoretically it should have the same file structure. I have 3ds max and I can get the plugins and try to edit the models.
