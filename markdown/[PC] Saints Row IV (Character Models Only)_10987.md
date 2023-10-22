## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-11-24T00:07:23+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

Same shit different day; you know the drill.
Sorry, too lazy to upload pic or instructions; I've been sick for a month and antibiotics made me worse and now I gotta go see doc again.

Bones + weights; sorry, no morphs, as I can't figure out the morph format.
If you want to help me decode the morph format, [more information is located here](http://www.saintsrowmods.com/forum/threads/morph-target-clues.5131/), where I asked the developers if they could give me hints on the morph format but no luck. Positions are stored as shorts and every fixed-point format I could think of didn't work.
[saintsrow4.7z](https://xentaxbackup.github.io/file/6796_saintsrow4.7z)
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-09-12T18:00:17+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

File "npc_basehead.ccmesh_pc"  is  for base head mesh.

Cmorph_pc file  has  new vertex position of base head mesh by adding  dx,dy,dz for each vertex from base head mesh,
where:
dx = uint16 * 2^scale 
dy = uint16 * 2^scale
dz = uint16 * 2^scale

scale = -20,-21,sometimes -22

so dx,dy,dz are very small.

Here is example for playing with scale for saints_female_shaundifuture head.

[http://www.mediafire.com/view/so89kvbo9 ... future.jpg](http://www.mediafire.com/view/so89kvbo9osxa1u/future.jpg)

cmorph_pc importer for Blender249:

Update: 2014-09-13
[http://www.mediafire.com/download/ahf1j ... 9-13%5D.7z](http://www.mediafire.com/download/ahf1j4cjtoaj7ln/Blender249%5BSaintsRow4%5D%5Bccmesh_pc%5D%5Bcmorph_pc%5D%5B2014-09-13%5D.7z)

How use:
-install Blender 249 and Python 26
-unpack importer
-click Blender249.blend

-in Text Window press alt+p and select:
cmesh_pc for skinned mesh with skeleton
cmorph_pc for shape morph

 If something wrong, please send me console error or file.

After importing it must manual set scale,position and rotation for head mesh.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-09-12T22:10:05+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

wow, very nice mariusz. how did you figure out the 2^scale thingy lol? did you peek in the EXE?
## Post #4
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-09-13T09:43:25+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

How does the cmorph_pc importer work? I get errors on the newGameLib parts of the script :/
## Post #5
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-09-13T17:38:26+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

Noticed you had posted some instructions, it was the same thing i did though, I got this error:
## Post #6
- Username: RoxasKennedy
- Rank: beginner
- Number of posts: 21
- Joined date: Tue May 17, 2011 6:39 pm
- Post datetime: 2014-09-13T18:30:10+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

You need to have the Python Imaging Library installed for this script to work   

You can download it here: [http://www.pythonware.com/products/pil/](http://www.pythonware.com/products/pil/) (there is a version for Python 2.6)
## Post #7
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-09-13T19:01:30+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

Thanks that worked
## Post #8
- Username: RoxasKennedy
- Rank: beginner
- Number of posts: 21
- Joined date: Tue May 17, 2011 6:39 pm
- Post datetime: 2014-09-14T21:04:36+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

I tried the importer, and it works great, but for some reason it imports female morphed heads even for male characters.
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-09-15T04:02:35+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

Importer use only one base mesh - npc_basehead.ccmesh_pc file
Maybe there is another base head?
Please import as first npc_basehead.ccmesh_pc from importer folder, and then cmorph file .
 if no difference between two meshes it fault my script, else try to change value SCALE=21 at the beginning of the script.
What model did you import?

 here are some heads from game

[http://www.mediafire.com/download/cv85a ... /heads.zip](http://www.mediafire.com/download/cv85a2aaedn55so/heads.zip)
## Post #10
- Username: RoxasKennedy
- Rank: beginner
- Number of posts: 21
- Joined date: Tue May 17, 2011 6:39 pm
- Post datetime: 2014-09-15T13:01:00+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

Changing the size to 20 worked on the model I tried to import. XD

I guess you have to change sizes on SOME models, because other sizes give a wrong head shape.

Thanks once again
## Post #11
- Username: Harmalarm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 10, 2015 10:02 pm
- Post datetime: 2017-08-27T18:50:03+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

Hi Guys, I'm bumping this topic just in the hope of finding an answer to my questions about the morph files for saints row III. I know they have a similar setup as SRIV because I have managed to get it working. What I don't get though is where these scale values for X Y and Z are located. I cannot find them anywhere in the character files. Not the CCMESH, GCMESH, morph file or even the rig file. They just seem to be hidden somewhere out of sight. Does anyone know where I could possible find them?

I've been working on an import script for 3ds max, and I've come a long way. But these morph values are giving me a headache! 
For my work, check out this topic:
[https://www.saintsrowmods.com/forum/thr ... rmat.1020/](https://www.saintsrowmods.com/forum/threads/decoding-the-saints-row-3-mesh-format.1020/)
## Post #12
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2019-03-17T04:45:55+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

I'm having some trouble with a specific mesh. It's bizarre, most other meshes I have work with this blender script, but this one causes a 'memory error' when I try to import it. It's the only one I've seen that does it so far. [https://www.dropbox.com/s/iuso58umanejl ... s.zip?dl=0](https://www.dropbox.com/s/iuso58umanejlcx/cm_demon_wings.zip?dl=0)
## Post #13
- Username: aknologia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 12, 2019 7:59 pm
- Post datetime: 2019-05-29T11:12:48+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

Is there some way to get in Blender the "surface" geometry, not only matcap?
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-06-24T19:47:38+00:00
- Post Title: [PC] Saints Row IV (Character Models Only)

> Reply from Szkaradek123 ↑Sat Sep 13, 2014 2:00 am at Sat Sep 13, 2014 2:00 am
>
> 
File "npc_basehead.ccmesh_pc"  is  for base head mesh.

Cmorph_pc file  has  new vertex position of base head mesh by adding  dx,dy,dz for each vertex from base head mesh,
where:
<...>
hi, can you look into this files of SR3 Remastered?
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1Apo06pQVUY1KEg5PQQNYi6XgeO1fXhvM?usp=sharing)
