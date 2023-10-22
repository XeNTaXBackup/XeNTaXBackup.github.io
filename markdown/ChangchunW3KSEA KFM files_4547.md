## Post #1
- Username: Yelü Dashi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 03, 2010 3:30 am
- Post datetime: 2010-06-02T22:28:58+00:00
- Post Title: Changchun/W3KSEA KFM files

I've managed to convert the texture files from this Asian MMO, as explained [here](http://forum.xentax.com/viewtopic.php?f=10&t=4408&p=37707&hilit=ygj#p37707) but I having problems with model files, the folder contain what I think are compressed KFMs. When opening with Nifskope I get ""failed to load kfm file (33554443)""(asume this is an invalid header due to compression ? ). Here's an example of one [KFM file](http://www.sendspace.com/file/7nk0p4) if someone wouldn't mind having a look. 

Quite new to this all this, it was first time using a BMS script today to batch convert the textures, and it worked   So I hope the models can also be accessed   Any pointers would be most appreciated.
## Post #2
- Username: Yelü Dashi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 03, 2010 3:30 am
- Post datetime: 2010-06-13T23:07:34+00:00
- Post Title: Changchun/W3KSEA KFM files

Anyone willing to help me out in this one ?

Cheers.
## Post #3
- Username: Yelü Dashi
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-14T00:57:29+00:00
- Post Title: Changchun/W3KSEA KFM files

its not compressed and its not a nif file they must just use the same extension it looks like a plain model file common in pc mmo's
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-10T16:29:26+00:00
- Post Title: Changchun/W3KSEA KFM files

Started with the easy stuff:

[](http://i.imgur.com/48PwR.jpg) [](http://i.imgur.com/rLSyP.jpg)

I've gotten the items that have bones and items that don't have bones.
The material section confuses me, and the bone section I don't know much about.

```
dword ???
dword ??? (always E8 03 00 00 so far)
dword numBones
dword unk4 (maybe bones related)
dword numMeshes
dword total verts
dword total faces
float_12 ??? (just skipping it)
char_28 model name (read bytes until null, then skip the leftover bytes)
dword ???
float ???
dword ???
dword ???

numBones bone {
   172 bytes
}

numMesh material {
   44 bytes
   Get name by reading bytes until you get a null byte, then just skip the other bytes to the next section
}

numMesh mesh {
   dword numVerts
   dword numFaces

   numVerts vertex {
      float_3 coords
      float_3 normals?
      float_4 ???
      float_2 uv
      float_6 ???
   }

   numFaces face {
      short_3 face indices
   }
}
dword_2 ???

```


EDIT: revised. seems to work for all models and it covers the entire file, so now just need to fill in the unknowns.

Note: the materials are stored in the same order that the meshes appear, so mat1 = mesh1, mat2 = mesh2, etc. Just pass the mesh# when assigning material.

Note: Need a better way to deal with names, because right now I'm just skipping important information lol

Some samples attached:
[changchun2.7z](https://xentaxbackup.github.io/file/4462_changchun2.7z)
## Post #5
- Username: Yelü Dashi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 03, 2010 3:30 am
- Post datetime: 2011-07-21T19:09:12+00:00
- Post Title: Changchun/W3KSEA KFM files

Wow - took a while but it's awesome that you've cracked it. What else needs to be sorted ?
