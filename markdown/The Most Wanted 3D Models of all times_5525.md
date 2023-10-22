## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-10T21:41:14+00:00
- Post Title: The Most Wanted 3D Models of all times

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: enrique3
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 23, 2010 5:03 pm
- Post datetime: 2010-12-11T09:39:31+00:00
- Post Title: The Most Wanted 3D Models of all times

As far as I know, the files are encrypted and there isn't yet some converter.  
The files *.gai are models 3D, and textures are *.tm2.

Here some examples of the textures:



I hope that somebody may help with some plugin for .gai files for Noesis! It would be great!  

Do you ripped with an emulator or directly from the ISO?   

Regards.
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-11T11:08:01+00:00
- Post Title: The Most Wanted 3D Models of all times

> Reply from enrique3
>
> As far as I know, the files are encrypted and there isn't yet some converter.  
The files *.gai are models 3D, and textures are *.tm2.

Here some examples of the textures:



I hope that somebody may help with some plugin for .gai files for Noesis! It would be great!  

Do you ripped with an emulator or directly from the ISO?   

Regards.
According to [http://gameresearch.5d6d.com/thread-231-1-1.html](http://gameresearch.5d6d.com/thread-231-1-1.html)
*.gai -->ani file
*.gmi -->mesh file
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-11T17:52:24+00:00
- Post Title: The Most Wanted 3D Models of all times

A friend from china rip the models direct from the ISO and send me the whole content of the disc, Emulation rips pscsx2 and 3d ripper not works never, the overlay system of emulators flat the models because lost the Z coordenate. I hope some can decrypt this.
Also y sended a PM to chrrox and other to fatduck, i hope one of this boys or other can help with this format files.
Also the textures you show enrique3 are ripped with the emulator, but i really want see waht of this files are the textures original.
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-14T17:42:53+00:00
- Post Title: The Most Wanted 3D Models of all times

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-15T15:27:31+00:00
- Post Title: The Most Wanted 3D Models of all times

> Reply from Rimbros
>
> Any idea, i think because this its chinese files maybe its not posible decrypt the files.

link is for your reference.
[viewtopic.php?f=16&t=5013](http://forum.xentax.com/viewtopic.php?f=16&t=5013)
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-15T18:36:13+00:00
- Post Title: The Most Wanted 3D Models of all times

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-16T17:04:15+00:00
- Post Title: The Most Wanted 3D Models of all times

I try the codes with blender like .py files but nothing works, i hope any can tell me how this works.. thanks. Its a dream for me extract this amazing armors i am greath fan of this series, ato thanks to man can make a script to max to import textures and meshes from this models.

That its the link of the files

[http://www.megaupload.com/?d=AW4JS1U9](http://www.megaupload.com/?d=AW4JS1U9)
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-17T22:04:33+00:00
- Post Title: The Most Wanted 3D Models of all times

any news? something know the way?... thanks.
## Post #10
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-19T01:30:30+00:00
- Post Title: The Most Wanted 3D Models of all times

Maybe fatduck? he posted a models here [viewtopic.php?f=16&t=5013](http://forum.xentax.com/viewtopic.php?f=16&t=5013) but i not know how this codes works any idea?

This its the code fatducks paste, but i dont know how this works, i try with max but not works like a scrpit:

```
dword           GMIsize
dword           HeaderSize?
dword           padding?
word            numBones
word            numMesh
dword           ofsBones
dword           ofsMesh
dword           ??
dword           ??

struct Bone {                   //Base on parent coordinate
  float_16      Matrix4X4
  word          ParentID
  word          ??
  word          ??
  char[42]      BoneName
}

struct MeshInfo {
  word          MeshType?
  dword         numVerts
  dword         numFaceControl?
  word          padding
  dword         ofsVertCoord
  dword         ofsNormal
  dword         ??              //must be offset of something
  dword         ofsUV
  dword         ofsBoneIndices
  dword         ofsWeight
}

struct VertCoord {              //Base on Bone Transform
  float_3       CoordXYZ
  float         FaceControl     //1.0 = build Face
}

struct Normal {
  word_3        NormalXYZ
  word          Padding?
}

struct UV {
  float_2       TexUV
}

struct BoneIndices {
  byte          Index1
  byte          index2
  byte_2        Padding
}

struct Weight {
  float         Weight1
  float         Weight2 
}
```
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-20T17:40:59+00:00
- Post Title: The Most Wanted 3D Models of all times

Also i have this code from mr.adults but i dont know how this work

```
   int bidx;
   bidx = int(boneIdx.x);
   mt[0].xyzw = boneMats[bidx][0].xyzw * boneWgt.x;
   mt[1].xyzw = boneMats[bidx][1].xyzw * boneWgt.x;
   mt[2].xyzw = boneMats[bidx][2].xyzw * boneWgt.x;
   mt[3].xyzw = boneMats[bidx][3].xyzw * boneWgt.x;
   bidx = int(boneIdx.y);
   mt[0].xyzw += boneMats[bidx][0].xyzw * boneWgt.y;
   mt[1].xyzw += boneMats[bidx][1].xyzw * boneWgt.y;
   mt[2].xyzw += boneMats[bidx][2].xyzw * boneWgt.y;
   mt[3].xyzw += boneMats[bidx][3].xyzw * boneWgt.y;
   bidx = int(boneIdx.z);
   mt[0].xyzw += boneMats[bidx][0].xyzw * boneWgt.z;
   mt[1].xyzw += boneMats[bidx][1].xyzw * boneWgt.z;
   mt[2].xyzw += boneMats[bidx][2].xyzw * boneWgt.z;
   mt[3].xyzw += boneMats[bidx][3].xyzw * boneWgt.z;
   bidx = int(boneIdx.w);
   mt[0].xyzw += boneMats[bidx][0].xyzw * boneWgt.w;
   mt[1].xyzw += boneMats[bidx][1].xyzw * boneWgt.w;
   mt[2].xyzw += boneMats[bidx][2].xyzw * boneWgt.w;
   mt[3].xyzw += boneMats[bidx][3].xyzw * boneWgt.w;
   highp vec4 transPos = mt * position;
   gl_Position = mvpMatrix * transPos;
   mat3 m33 = mat3(mt[0].xyz,
               mt[1].xyz,
               mt[2].xyz);
   lowp vec3 transNrm = normalize(m33 * normal);
```
## Post #12
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-21T05:29:39+00:00
- Post Title: The Most Wanted 3D Models of all times

I am very interested in your post.
But, i'm sorry I cannot be of help.
## Post #13
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-27T21:01:56+00:00
- Post Title: The Most Wanted 3D Models of all times

Any idea?
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-31T18:01:28+00:00
- Post Title: The Most Wanted 3D Models of all times

Something script? i found a function iniside of the game to see the models in any position i want
## Post #15
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-06T23:44:40+00:00
- Post Title: The Most Wanted 3D Models of all times

I open the MPL files (ps2 ssh game) with text editor and i recognize something lines
maybe anyone can take a view of this files

Some idea how to convert this files or read the structure?
## Post #16
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2011-02-22T21:48:52+00:00
- Post Title: Re: The Most Wanted 3D Models of all times

> Reply from Rimbros
>
> I open the MPL files (ps2 ssh game) with text editor and i recognize something lines
maybe anyone can take a view of this files





Some idea how to convert this files or read the structure?

Links to download
http://rapidshare.com/files/441193965/MPLFORMAT.rar
http://www.megaupload.com/?d=2KGN1RMW
http://www.sendspace.com/file/ztqsn4
http://www.filefront.com/17759429/MPLFORMAT.rar

I hope anyone can help, also i try with the Mario Kart Guide, but is not mine area.

These MPL files are animation files and not the models themselves. Can you post other files of different extensions  from the same game.
## Post #17
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-22T21:54:10+00:00
- Post Title: Re: The Most Wanted 3D Models of all times

here samples of all the files separated.

[http://www.megaupload.com/?d=3KT2YU5U](http://www.megaupload.com/?d=3KT2YU5U)
## Post #18
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2011-03-09T00:20:57+00:00
- Post Title: Re: The Most Wanted 3D Models of all times

MPL files do not contain Models, they only contain Animations. GMI files contain models and here is an extraction guide you can use to get models from them:
[http://ps23dformat.wikispaces.com/file/ ... Ifiles.txt](http://ps23dformat.wikispaces.com/file/view/SSMODELextractionGMIfiles.txt)

Remember to download the guide and then open it as Internet browser might display some lines incorrectly. If you have any questions please contact me.
