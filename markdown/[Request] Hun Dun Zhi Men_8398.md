## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-23T23:50:28+00:00
- Post Title: [Request] Hun Dun Zhi Men

Ok after aluigi help me for unpack PAK files here I get DDS and some models files I think, in folder Alset_female have different formats like .bbf, .adf, .bmf and .aif.

PD: good matching files seems obvious that the information is concentrated more in the archives ADF.

ADF Header



BBF Header



BMF Header



[Hun Dun Zhi Men 2D-3D Models](http://www.mediafire.com/download.php?kfjvjgev63gvb7v)
## Post #2
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-24T18:33:16+00:00
- Post Title: [Request] Hun Dun Zhi Men

.aif is the material file??
.adf is the character model file
.bbf is the animation file
.bmf is the model file for each character part

.bmf format is real simple

EDIT: got it wrong....

corrected

```
long + numvert + numtri + numbones?? + numobj?? + dunno(4) + duno(byte) + long + long + long

verts
4 floats + x,y,z +  u,v + n1,n2,n3 + 4 floats + long

triangles -> numtri / 3
t1,t2,t3

bones
????

```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T00:24:15+00:00
- Post Title: [Request] Hun Dun Zhi Men

Nice. Were the filenames figured out?
## Post #4
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-25T01:43:49+00:00
- Post Title: [Request] Hun Dun Zhi Men

No idea.
The zip contained the correct names for the model files (.bmf) pointed at by the .adf, but the texture names in the zip doesn't seem to have the correct names.
No hair or belt textures, just body+face.
Hair on model is from metasequoia folder 

EDIT: Noesis script - no materials or bones, UVs work though.
[http://pastebin.com/hu5ttz5H](http://pastebin.com/hu5ttz5H)
Hopefully finale00 can finish it, it's his script
