## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-05T00:31:08+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

Since the game just ran on a windows computer, the files are very easy accesable.
The model format is .X and can be converted with this online converter:
[https://www.meshconvert.com/de.html](https://www.meshconvert.com/de.html)

However this is quiet a nasty process and the website only allows files up to 18mb.
So I wanted to know if you guys know of any noesis or quickbms scripts that work with these files.
I've uploaded an example for Silent Hill Arcade .X - files here:


 Silent_Hill_Arcade_Model-File.zip
DirectX .X-File from Silent Hill the Arcade (2.8 KiB) Downloaded 19 times



Heres some results i archieved with the online mesh converter:





Heres a video that even shows a character thats been extracted with skeleton and animations:
[https://www.youtube.com/watch?v=EOf-0DsO7GE](https://www.youtube.com/watch?v=EOf-0DsO7GE)

Anything that lets me batchconvert the .x files helps!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-05T12:46:17+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from Henchman800 ↑Thu Mar 05, 2020 8:31 am at Thu Mar 05, 2020 8:31 am
>
> Anything that lets me batchconvert the .x files helps!Since assimp (viewer) is open source it should be possible to add a command line option (my version crashes when called with param elbotan_huta.X)
.



assimp_viewer.png (104.83 KiB) Viewed 211 times
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-05T14:51:49+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from shakotay2 ↑Thu Mar 05, 2020 8:46 pm at Thu Mar 05, 2020 8:46 pm
>
> Since assimp (viewer) is open source it should be possible to add a command line option (my version crashes when called with param elbotan_huta.X)
.
assimp_viewer.png
So you are saying that i could add a line that lets me batchconvert .x files?
I've read about a noesis plugin, but i wasnt able to find it
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-05T15:37:52+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from Henchman800 ↑Thu Mar 05, 2020 10:51 pm at Thu Mar 05, 2020 10:51 pm
>
> So you are saying that i could add a line that lets me batchconvert .x files?Having the source you can do almost everything - if you are a coder.  
(And you'll need to add/change more than one line only, I guess.)

Search for "assimp command line".

This is a converter using commandline parameters, but it converts to .json only:
[https://github.com/cdave1/assimp2json](https://github.com/cdave1/assimp2json)
## Post #5
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-03-08T17:17:43+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

3D Object Converter has a batch convert and opens the .X files
[http://3doc.i3dconverter.com/](http://3doc.i3dconverter.com/)

I have a registered version so updates are free for life.
Well worth the small price.
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-08T17:24:47+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from shakotay2 ↑Thu Mar 05, 2020 11:37 pm at Thu Mar 05, 2020 11:37 pm
>
> 
Having the source you can do almost everything - if you are a coder.

This is the Problem....im a video Editor/cameraman  
Imma check that .json converter though...maybe i can find something to batchconvert them aswell
## Post #7
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-08T17:26:16+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from 05SpeedMaster ↑Mon Mar 09, 2020 1:17 am at Mon Mar 09, 2020 1:17 am
>
> 
3D Object Converter has a batch convert and opens the .X files
http://3doc.i3dconverter.com/

Awesome!!!
Imma check that out tonight
## Post #8
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-03-08T17:27:35+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

It supports over 700 formats!
And like the People that created SweetScape 010 Hex Editor, you can send information on new formats and he might add it to 3D Object Converter.
## Post #9
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-09T18:57:04+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

This tool works fine in general....very intuitiv and I love the batch-convert function!
However, some stuff imports incorrectly. A lot of triangles seem to be missing:


Could this be the program itself handling to many files?
It crashed onme once...


Edit:
Nevermind.....I think I "found" it haha
## Post #10
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-10T00:08:03+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

the issue being is that the characters seem to have a different format other than the level files. its still supposed to be a different version of directx.
The Files are called .xab


 Silent Hill Arcade Models.zip
(46.04 KiB) Downloaded 15 times



Could you guys check if thats right?
Maybe im wrong.....

Edit:
But it looks about right....

```
template XSkinMeshHeader {
 <3cf169ce-ff7c-44ab-93c0-f78f62d172e2>
 WORD nMaxSkinWeightsPerVertex;
 WORD nMaxSkinWeightsPerFace;
 WORD nBones;
}

template VertexDuplicationIndices {
 <b8d65549-d7c9-4995-89cf-53a9a8b031e3>
 DWORD nIndices;
 DWORD nOriginalVertices;
 array DWORD indices[nIndices];
}

template SkinWeights {
 <6f0d123b-bad2-4167-a0d0-80224f25fabb>
 STRING transformNodeName;
 DWORD nWeights;
 array DWORD vertexIndices[nWeights];
 array FLOAT weights[nWeights];
 Matrix4x4 matrixOffset;
}

template Camera {
 <1228c381-9a21-41a5-93d1-591c17fdea86>
 Vector Position;
 Vector Direction;
 FLOAT FovY;
}

template Light {
 <a83aa5c3-b69d-4af5-9a20-af23bf545d9c>
 DWORD Type;
 ColorRGBA Diffuse;
 ColorRGBA Specular;
 ColorRGBA Ambient;
 Vector Position;
 Vector Direction;
 FLOAT Range;
 FLOAT Falloff;
 FLOAT Attenuation0;
 FLOAT Attenuation1;
 FLOAT Attenuation2;
 FLOAT Theta;
 FLOAT Phi;
}

template SilentLight {
 <28448950-847d-4d15-8d82-707d0fd0d7f4>
 DWORD Type;
 ColorRGBA Color;
 Vector Position;
 Vector Direction;
 FLOAT RangeNear;
 FLOAT RangeFar;
 FLOAT ConeInside;
 FLOAT ConeOutside;
 DWORD Shadow;
}


Frame _V__________g {
 

 FrameTransformMatrix {
  1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000;;
 }

 Frame Dum_numb_acid {
  

  FrameTransformMatrix {
   1.000000,-0.000000,-0.000000,0.000000,0.000000,1.000000,-0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,-0.000000,0.000000,0.000000,1.000000;;
  }

  Frame numb_acid {
   

   FrameTransformMatrix {
    -1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,-0.000000,0.000000,-1.000000,0.000000,0.000000,0.000000,0.000000,1.000000;;
   }

   Frame {
    

    FrameTransformMatrix {
     -1.000000,0.000000,0.000000,0.000000,0.000000,-0.000000,1.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,0.000000,1.000000;;
    }

    Mesh {
     4;
     -0.062039;-0.000001;-0.061564;,
     0.062039;0.000000;-0.061564;,
     -0.062039;-0.000000;0.061564;,
     0.062039;0.000001;0.061564;;
     2;
     3;0,3,1;,
     3;3,0,2;;

     MeshNormals {
      4;
      -0.000009;1.000000;-0.000002;,
      -0.000009;1.000000;-0.000002;,
      -0.000009;1.000000;-0.000002;,
      -0.000009;1.000000;-0.000002;;
      2;
      3;0,3,1;,
      3;3,0,2;;
     }

     MeshTextureCoords {
      4;
      0.000000;1.000000;,
      1.000000;1.000000;,
      0.000000;0.000000;,
      1.000000;0.000000;;
     }

     MeshMaterialList {
      1;
      2;
      0,
      0;

      Material {
       1.000000;1.000000;1.000000;1.000000;;
       9.999999;
       0.000000;0.000000;0.000000;;
       0.000000;0.000000;0.000000;;

       TextureFilename {
        "tx_numbody_sp.dds";
       }
      }
     }
    }
   }
  }
 }
}                

AnimationSet {
 

 Animation {
  

  AnimationKey {
   4;
   2;
   0;16;1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000;;,
   1760;16;1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000;;;
  }
  { _V__________g }
 }

 Animation {
  

  AnimationKey {
   4;
   2;
   0;16;-1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,-0.000000,0.000000,-1.000000,0.000000,0.000000,0.000000,0.000000,1.000000;;,
   1760;16;-1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,-0.000000,0.000000,-1.000000,0.000000,0.000000,0.000000,0.000000,1.000000;;;
  }
  { numb_acid }
 }
}
```
## Post #11
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-10T10:31:22+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from Henchman800 ↑Tue Mar 10, 2020 8:08 am at Tue Mar 10, 2020 8:08 am
>
> 
But it looks about right....

Check this out:
You just have to rename the "___.xab" to "___.x" and [https://www.meshconvert.com/de.html](https://www.meshconvert.com/de.html) will convert it to a format of your choice!


Sadly 3D-Object_Converter doesn't support this renaming method and simply says "STREAM READ ERROR"

But I guess we now have everything we need to convert and extract "Silent Hill The Arcade" 3D-models
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-10T13:03:46+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from Henchman800 ↑Tue Mar 10, 2020 6:31 pm at Tue Mar 10, 2020 6:31 pm
>
> Sadly 3D-Object_Converter doesn't support this renaming method and simply says "STREAM READ ERROR"Because the xab are ASCII-.x files while elbotan_huta.X is binary version.

(I have a deja vue of a DirectX tool which could convert ASCII version to binary but can't remember which one it was...)

btw: good old Blender's (2.49) directX importer gets your xab directly.
## Post #13
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-03-11T10:41:22+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from shakotay2 ↑Tue Mar 10, 2020 9:03 pm at Tue Mar 10, 2020 9:03 pm
>
> 
btw: good old Blender's (2.49) directX importer gets your xab directly.
Du kluger Kopf..... 
I didn't even think about that!
The next problem was vertex-groups for multiple textures...
Online Mesh converter does not create a .mtl :-/
Imma give blender 2.49 a try today   
Thx shakotay2!
## Post #14
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-03T13:41:29+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

> Reply from shakotay2 ↑Tue Mar 10, 2020 9:03 pm at Tue Mar 10, 2020 9:03 pm
>
> 
btw: good old Blender's (2.49) directX importer gets your xab directly.

I just tried with blender 2.49b and it doen't import the .xab, nor the regular .x files of the levels :-/
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-03T14:00:44+00:00
- Post Title: Very common directx .X-file (Silent Hill Arcade)

I was referring to the .xab files in the zip of your post as of Tue Mar 10, 2020 1:08 am (which need to be renamed to .x for successful blender2.49b import).
(If you want to avoid confusion just don't switch between level files and other static models here.)
## Post #16
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-03T22:32:28+00:00
- Post Title: Re: Very common directx .X-file (Silent Hill Arcade)

> Reply from shakotay2 ↑Fri Apr 03, 2020 10:00 pm at Fri Apr 03, 2020 10:00 pm
>
> 
I was referring to the .xab files in the zip of your post as of Tue Mar 10, 2020 1:08 am (which need to be renamed to .x for successful blender2.49b import).

Ooops....my fault 

However, I tested other files and yet again it looks like it only works on some of the files...others like this boss don't:

FILE DOWNLOAD:
[https://cdn.discordapp.com/attachments/ ... tub_no.xab](https://cdn.discordapp.com/attachments/628005960471805972/695760598381887568/m70_tub_no.xab)

Ref:
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-04T07:11:30+00:00
- Post Title: Re: Very common directx .X-file (Silent Hill Arcade)

It's the difference in file format (binary/ASCII) as I wrote before.
## Post #18
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-04T10:24:19+00:00
- Post Title: Re: Very common directx .X-file (Silent Hill Arcade)

> Reply from shakotay2 ↑Sat Apr 04, 2020 3:11 pm at Sat Apr 04, 2020 3:11 pm
>
> 
It's the difference in file format (binary/ASCII) as I wrote before.

Would this be helpful to convert the files then?
[https://www.rapidtables.com/convert/num ... inary.html](https://www.rapidtables.com/convert/number/ascii-to-binary.html)

Imma try this one with the different filetypes aswell:
[https://products.aspose.app/3d/conversion/x-to-fbx](https://products.aspose.app/3d/conversion/x-to-fbx)

Maybe this noesis plugin works:
[https://github.com/Techokami/noesis-plu ... tX_xbin.py](https://github.com/Techokami/noesis-plugins-official/blob/master/finale00/fmt_DirectX_xbin.py)
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-04T17:56:18+00:00
- Post Title: Re: Very common directx .X-file (Silent Hill Arcade)

no, no and no.
finale00's DirectX_xbin plugin requires a "bin " in the .x file which is "bzip" in m70_tub_no.xab(.x)

What you need is MeshConvert.exe (parameters *.x /xt) from Microsoft DirectX SDK (June 2010) to convert a compressed binary .x  file to ASCII .x:
.



m70_tub_no.xab ASCII-x.png (76.77 KiB) Viewed 116 times



see 
> Reply from shakotay2 ↑Fri May 09, 2014 3:20 am at Fri May 09, 2014 3:20 am
>
>
## Post #20
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-05T20:00:06+00:00
- Post Title: Re: Very common directx .X-file (Silent Hill Arcade)

> Reply from shakotay2 ↑Sun Apr 05, 2020 1:56 am at Sun Apr 05, 2020 1:56 am
>
> 
What you need is MeshConvert.exe (parameters *.x /xt) from Microsoft DirectX SDK (June 2010) to convert a compressed binary .x  file to ASCII .x

Thanks for the help!
However when I use meshcnvert via CMD i get this:

I tried to rename the file, but I'm pretty sure it's me....
so it would be awesome if you could push me once again in the right direction.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-05T21:02:39+00:00
- Post Title: Re: Very common directx .X-file (Silent Hill Arcade)

binary .x files are converted to ASCII .x files. The original file is destroyed/modified. File size is increased, that's the only hint. (Most people don't understand the process and try to convert the already converted file again.  )
## Post #22
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-04-06T12:46:33+00:00
- Post Title: Re: Very common directx .X-file (Silent Hill Arcade)

> Reply from shakotay2 ↑Mon Apr 06, 2020 5:02 am at Mon Apr 06, 2020 5:02 am
>
> 
binary .x files are converted to ASCII .x files. The original file is destroyed/modified. File size is increased, that's the only hint. (Most people don't understand the process and try to convert the already converted file again.  )

....I could've paid attention to that.......file went from 4mb to 0.5mb....
Thank you once again man! Your solution works like a charm!


Danke für deine Geduld mit mir man
