## Post #1
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2011-10-11T13:27:07+00:00
- Post Title: Rage (idTech5) model format md6

Hello! Does anyone know how to open a model of Rage? Here are some examples of models:
## Post #2
- Username: Qartar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 10, 2011 12:12 pm
- Post datetime: 2011-10-12T05:17:42+00:00
- Post Title: Rage (idTech5) model format md6

Formats are proprietary and the game was just released a week ago, it may take some time. You provided four different formats, one is the animated mesh format .bmd6model, a static geometry format .bmodel, a collision model format .bcm, and I'm not sure what the .dmodel is without diving into the data. (Also the animation file .bmd6anim).
## Post #3
- Username: Toji
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 12, 2011 1:19 pm
- Post datetime: 2011-10-12T05:26:14+00:00
- Post Title: Rage (idTech5) model format md6

Thanks for posting those. I've been meaning to extract some and take a look at it.

Looking at hands.bmd6model I can tell you immediately that I can see some very clear blocks of data that look like they represent bone names, index data and vertex data. Interestingly, the hand model looks like it has two blocks of vertex+index data each followed by a what looks like a mesh name and material path, so I'm guessing that each material gets it's own data block in the file.

I don't know if I'll have any time to do much with this, but the basics of the format look pretty clear. I'll see if I can post a more detailed analysis later.

(Going to bed now, but a quick item of interest: every single ASCII string that I've seen in these files is preceded by an int32 that gives the string length. Makes reading them easy!)
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-16T07:50:04+00:00
- Post Title: Rage (idTech5) model format md6

format of vertices and index buffer are pretty clear. however, without more models it's impossible to tell where the data starts. thus, for now you gotta hard code offsets. i don't have $60 to spend on a game at the moment so maybe someone else can pick it up. here is code idea for the hand model. BE_ means big endian. Sample must be from PS3?



```
 if(!ifile) return error("Could not open file.");

 // use offset #1 = 0x0151C for arms
 // use offset #2 = 0x3C15F for gauntlet

 // open file
 ofstream ofile("output2.ls");
 ofile << "main" << endl;
 ofile << "{" << endl;
 ofile << " editbegin();" << endl;
 ofile << " uvmap = VMap(\"texture\", \"" << "texture" << "\", 2);" << endl;

 ifile.seekg(0x151C);
 size_t n_points = BE_read_uint16(ifile); // number of points (2524)
 BE_read_uint16(ifile);
 size_t n_triangles = BE_read_uint16(ifile); // number of triangles (4602)
 BE_read_float(ifile);
 BE_read_float(ifile);
 BE_read_float(ifile);
 BE_read_float(ifile);
 BE_read_float(ifile);
 BE_read_float(ifile);
 cout << endl;
 
 for(size_t i = 0; i < n_points; i++)
    {
     float x = BE_read_float(ifile);
     float y = BE_read_float(ifile);
     float z = BE_read_float(ifile);
     float u = BE_read_float(ifile);
     float v = BE_read_float(ifile);
     BE_read_uint16(ifile);
     BE_read_uint16(ifile);
     BE_read_uint16(ifile);
     BE_read_uint16(ifile);
     BE_read_uint16(ifile);
     BE_read_uint16(ifile);
     cout << endl;

     ofile << " pointlist[" << i + 1 << "]" << " = " << "addpoint(" << x << "," << y << "," << z << ");" << endl;
     ofile << " uvmap.setValue(pointlist[" << (i + 1) << "]," << "@" << u << "," << v << "@);" << endl;
    }

 // read triangles
 boost::shared_array<unsigned short> data(new unsigned short[n_triangles*3]);
 ifile.read((char*)&data.get()[0], n_triangles*3*sizeof(unsigned short));
 for(size_t i = 0; i < 3*n_triangles; i++) reverse_byte_order(&data.get()[i]);

 size_t index = 0;
 for(size_t i = 0; i < n_triangles; i++) {
     unsigned short a = data.get()[index++] + 1;
     unsigned short b = data.get()[index++] + 1;
     unsigned short c = data.get()[index++] + 1;
     ofile << " addtriangle(pointlist[" << a << "], pointlist[" << c << "], pointlist[" << b << "]);" << endl;
    }

 ofile << " editend();" << endl;
 ofile << "}" << endl;

```
## Post #5
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2011-10-16T09:26:52+00:00
- Post Title: Rage (idTech5) model format md6

> Reply from howfie
>
> format of vertices and index buffer are pretty clear. however, without more models it's impossible to tell where the data starts. thus, for now you gotta hard code offsets. i don't have $60 to spend on a game at the moment so maybe someone else can pick it up. here is code idea for the hand model. BE_ means big endian. Sample must be from PS3?

no, this is PC version

This is ALL models
[http://www.multiupload.com/FQYQXSR2RM](http://www.multiupload.com/FQYQXSR2RM)
## Post #6
- Username: Qartar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 10, 2011 12:12 pm
- Post datetime: 2011-10-16T18:46:50+00:00
- Post Title: Rage (idTech5) model format md6

-types in capital letters are big endian
-all floating point types are big endian
-by "always" I mean "I haven't seen any models where this isn't the case" so beware
-offsets are from the end of the main file header

```

File header:
0x00 - 0x04 : [ tag ] - file id
0x04 - 0x08 : [ -?- ] - unknown
0x08 - 0x20 : [FLOAT] - model bounds, [min3,max3]
0x20 - 0x24 : [ int ] - unknown, always '1'*
0x24 - 0x28 : [ -?- ] - unknown, always '0'
0x28 - 0x29 : [char ] - unknown, possibly version id, always '5'
0x29 - 0x2a : [SHORT] - unknown, always '0'
0x2a - 0x2d : [SHORT] - offset to joint names

```

*It's possible that the int at 0x20 is the beginning of an n-string with a length of 1, which would explain the odd length of the file header but n-strings don't generally contain a null-term. Could also be the number of sub-models in the file, but I've only seen values of 1. Caveat emptor.

```
0x2d - 0x2f : [SHORT] - offset to joint names again
0x2f - 0x31 : [SHORT] - number of joints*
0x31 - 0x33 : [SHORT] - unknown, always '0'
0x33 - 0x35 : [SHORT] - unknown, roughly points to the mesh data but is off by enough to be an unusable link
0x35 - 0x37 : [SHORT] - offset to default pose data
0x37 - 0x39 : [SHORT] - offset to joint hierarchy
0x39 - 0x5d : [SHORT] - more offsets, several joint channel structures, many repeats

```

*The number of joints is rounded up to the nearest multiple of 8 in all of the data structures.

Default Pose:
4 big endian floats for each joint as quaternions (xyzw). then:
3 big endian floats for each joint as scale data (possibly, almost all 1.0). then:
3 big endian floats for each joint as translation data (xyz).

Default pose is in joint local space.

Joint Hierarchy:
One big endian short for each joint indicating the index of its parent. -1 for root.
Following this is another set of short values for each joint, the meaning is unclear.

Joint Channels:
A series of bytes, either -1 or 0, for each joint indicating whether it belongs to a channel. Several channels. Until the header is better understood you should probably just skip to the joint names.

Joint Names:
A series of nstrings for each joint. That is a little endian int followed by that many characters, does not contain null termination.
Following that is a byte for each joint, again not sure what it represents.
Following that is a 3x4 joint matrix for each joint.
Following that is another set of bounds. (6 floats).

Following that is the surface data:

```
0x00 - 0x04 : [ INT ] - number of surfaces

ea. surface:
  [nstring] - surface name
  [nstring] - material name
  [char ] - flags, 1 appears to indicate deformable surface but does not change structure
  [ INT ] - number of vertices
  [ INT ] - number of triangles
  [bounds] - bounds for this surface (6 floats).

  ea. vertex:
    0x00 - 0x0c : [FLOAT] - vertex xyz
    0x0c - 0x14 : [FLOAT] - vertex tex coordinates
    0x14 - 0x20 : [ -?- ] - weight data, unknown format

  ea. triangle:
    0x00 - 0x06 : [SHORT] - vertex indices 

  following vertex and triangle data:
  0x00 - 0x04 : [ INT ] - unknown, always 0
  0x04 - 0x08 : [ INT ] - unknown, always numJoints
  0x08 - 0x09 : [char ] - unknown, always 0 or 1
  [4 bytes of data for each vertex] (only if previous field is 1!)
  0x09 - 0x0d : [ INT ] - unknown, always 0

(next surface)

```


At the very end of the file there is a footer with a list of materials, generally more materials than there are surfaces so I'm not sure what it represents. You should be able to parse any bmd6model file with what's here.



You can probably see I'm having problems with just a few of the quaternions, incorrect sign or something.

> This is ALL models
>
> http://www.multiupload.com/FQYQXSR2RM
Don't do that. You don't have the rights to distribute that content, even for 'academic' purposes.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-17T12:54:20+00:00
- Post Title: Rage (idTech5) model format md6

Cool, thanks for finishing the parts I couldn't figure out. Tool time now!

As a test, try this (must have visual studio 2010 distributables and lightwave):
1.) Put exe file in models root directory.
2.) Run it and it will process all bmd6model files in all directories and subdirectories.
3.) You will find a bunch of new .ls files.
4.) Load ls file into lightwave.

Let me know if it works. I only had one file to work with so no textures. Only model and UVs are currently supported. Going to buy the game next week (since it has coop).

I will add bones next and process bmodels if program works for you guys.
[test.7z](https://xentaxbackup.github.io/file/4779_test.7z)
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-17T15:39:44+00:00
- Post Title: Rage (idTech5) model format md6

works with bmodel now too.
[test.7z](https://xentaxbackup.github.io/file/4783_test.7z)
## Post #9
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2011-10-18T10:17:56+00:00
- Post Title: Rage (idTech5) model format md6

> Reply from howfie
>
> works with bmodel now too.
COOL!!! It's work!!!
But, don't work with level static meshes 
sample
[http://www.multiupload.com/GGZFEC4ZFJ](http://www.multiupload.com/GGZFEC4ZFJ)
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-18T16:35:47+00:00
- Post Title: Rage (idTech5) model format md6

ok i'll check it out. still seems like they use tristrips, just the data is moved around a little bit. is there a file that mentions where all the models are placed in a level so we can export levels?
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-19T02:44:01+00:00
- Post Title: Rage (idTech5) model format md6

There are 4 different bmodel types, some use tristrips and some use triangle lists. 2 down, 2 to go. After the material text, there is a 0x00000000 followed by three 4-byte values. The first two values are the number of points and number of indices. The third number appears to be the type of bmodel file. Types 0x0263 and 0x0277 use a strange vertex format that I cannot figure out just yet. They tend to contain a lot of 0x7FFFs in them.

EDIT: getting close I think. vertices appear to be normalized signed shorts. without having a sample texture I won't be able to tell if I am scaling the UV coordinates (which are also shorts) correctly though.
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-19T23:02:38+00:00
- Post Title: Rage (idTech5) model format md6

done. now try.
can't fix uv normalization or automatically apply texture maps until i get the game and rip the textures.
[template.7z](https://xentaxbackup.github.io/file/4792_template.7z)
## Post #13
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-10-20T01:24:11+00:00
- Post Title: Rage (idTech5) model format md6

hi.howfie,i got a problem,after i run the template.exe,the bmd6model file became a huge ls file,what's wrong with it?
[1.jpg](https://xentaxbackup.github.io/file/4793_1.jpg)
## Post #14
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-10-20T01:25:49+00:00
- Post Title: Rage (idTech5) model format md6

one more screenshot
[2.jpg](https://xentaxbackup.github.io/file/4794_2.jpg)
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-20T01:29:44+00:00
- Post Title: Rage (idTech5) model format md6

Ok.  I will look at it right now.
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-20T01:39:11+00:00
- Post Title: Re: Rage (idTech5) model format md6

I believe the samples were PC. Is yours from the PS3 because mines works fine.

```
offset1 = 416
n_strings_actual = 4
n_strings = 8
 surfaces = 1
 points = 652
 triangles = 822

```
## Post #17
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-20T01:43:06+00:00
- Post Title: Re: Rage (idTech5) model format md6

just in case i accidentally uploaded an old version in the last post....
[template.7z](https://xentaxbackup.github.io/file/4795_template.7z)
## Post #18
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2011-10-20T03:20:18+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from howfie
>
> I believe the samples were PC. Is yours from the PS3 because mines works fine.
Code: Select allProcessing file: g:\dev\projects\xentax\release\allragemodels\md6\weapons\colt45\colt45.bmd6model
offset1 = 416
n_strings_actual = 4
n_strings = 8
 surfaces = 1
 points = 652
 triangles = 822
exactly, PC version, you can be sure
## Post #19
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-10-31T03:55:38+00:00
- Post Title: Re: Rage (idTech5) model format md6

what about the texture?
## Post #20
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-31T05:36:00+00:00
- Post Title: Re: Rage (idTech5) model format md6

I haven't bought the game yet. Textures must be applied manually.
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-31T11:04:36+00:00
- Post Title: Re: Rage (idTech5) model format md6

here is source code if you or someone else wants... as it looks i probably won't be able to get the game anytime soon. i can't tell if UV's are normalized correctly without samples of textures for each model type. but if you have the game you can modify the code anywhere you see something like the following:

```
       for(size_t i = 0; i < n_points; i++) {
           reverse_byte_order(&points[i].x);
           reverse_byte_order(&points[i].y);
           reverse_byte_order(&points[i].z);
           reverse_byte_order(&points[i].w);
           reverse_byte_order(&points[i].u);
           reverse_byte_order(&points[i].v);
           float x = points[i].x/32767.0f;
           float y = points[i].y/32767.0f;
           float z = points[i].z/32767.0f;
           float u = points[i].u/65535.0f; // change these 65535.0f values to scale properly
           float v = points[i].v/65535.0f; // change these 65535.0f values to scale properly
           ofile << " pointlist[" << i + 1 << "]" << " = " << "addpoint(" << x << "," << y << "," << z << ");" << endl;
           ofile << " uvmap.setValue(pointlist[" << (i + 1) << "]," << "@" << u << "," << v << "@);" << endl;
          }
       ofile << " editend();" << endl;

```


your modeler should also be capable of scaling and transforming UVs as well.
[rage.7z](https://xentaxbackup.github.io/file/4819_rage.7z)
## Post #22
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2011-10-31T14:35:56+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from howfie
>
> here is source code if you or someone else wants... as it looks i probably won't be able to get the game anytime soon. i can't tell if UV's are normalized correctly without samples of textures for each model type. but if you have the game you can modify the code anywhere you see something like the following:
Code: Select all       ofile << " editbegin();" << endl;
       for(size_t i = 0; i < n_points; i++) {
           reverse_byte_order(&points[i].x);
           reverse_byte_order(&points[i].y);
           reverse_byte_order(&points[i].z);
           reverse_byte_order(&points[i].w);
           reverse_byte_order(&points[i].u);
           reverse_byte_order(&points[i].v);
           float x = points[i].x/32767.0f;
           float y = points[i].y/32767.0f;
           float z = points[i].z/32767.0f;
           float u = points[i].u/65535.0f; // change these 65535.0f values to scale properly
           float v = points[i].v/65535.0f; // change these 65535.0f values to scale properly
           ofile << " pointlist[" << i + 1 << "]" << " = " << "addpoint(" << x << "," << y << "," << z << ");" << endl;
           ofile << " uvmap.setValue(pointlist[" << (i + 1) << "]," << "@" << u << "," << v << "@);" << endl;
          }
       ofile << " editend();" << endl;


your modeler should also be capable of scaling and transforming UVs as well.
## Post #23
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-11-01T18:53:01+00:00
- Post Title: Re: Rage (idTech5) model format md6

For Blender249 users bmd6model importer(no work for more complex model):
-geometry with uv
-vertex groups , but no vertex weights(all vertex groups have 1.0)
-bones

Qartar: bravo for this "The number of joints is rounded up to the nearest multiple of 8 in all of the data structures."

[import-rage-2011-10-31.zip](https://xentaxbackup.github.io/file/4821_import-rage-2011-10-31.zip)
## Post #24
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-11-02T04:00:37+00:00
- Post Title: Re: Rage (idTech5) model format md6

some uv are overlapping,with LW&blender
## Post #25
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-02T07:18:41+00:00
- Post Title: Re: Rage (idTech5) model format md6

That should be ok as long as overlapping faces are assigned to different materials.
## Post #26
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-11-02T08:00:01+00:00
- Post Title: Re: Rage (idTech5) model format md6

is there a easy way to separate them in LW or blender? i mean like the max's material ID
## Post #27
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-02T08:49:13+00:00
- Post Title: Re: Rage (idTech5) model format md6

In lightwave, yes. Easy for me. Don't know about Blender. In game they are implemented as a single UV set interleaved with the vertex data so it is kind of a pain in the butt to code them as different maps separated by material. So to separate them manually....

1.) Select all polygons and unweld all vertices (Details > Unweld). This is important.
2.) Select surface (material) polygons by pressing W in Polygon mode and selecting surface you want to move from overlapping UV set to an empty UV set.
3.) Then go to Map > UV/Texture/More/Copy UVs. It will deselect the polygons you selected.
4.) Select surface again.
5.) Create a new blank UV map with no initial value.
6.) Then Map > UV/Texture/More/Paste UVs.
7.) Repeat 2.) - 6.) for other surfaces.
8.) Select all polygons and Details > Weld to weld vertices back together again.
## Post #28
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-11-02T09:43:43+00:00
- Post Title: Re: Rage (idTech5) model format md6

only the small item can display uv,way the others can't?
[1.jpg](https://xentaxbackup.github.io/file/4823_1.jpg)
## Post #29
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-02T15:28:19+00:00
- Post Title: Re: Rage (idTech5) model format md6

Would you rather have obj export instead? I'll be switching from lightwave to obj and mel on future projects anyways, as I can't stand the fact that lightwave does not directly support DDS even though OpenGL has supported S3TC textures for like forever now.
## Post #30
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-02T15:55:40+00:00
- Post Title: Re: Rage (idTech5) model format md6

Actually, looking at it again, you are correct; I just noticed the face UVs overlapping with other upper-body stuff, and all in the same surface/material too so what I said three posts up won't help anyways. Without the textures, I cannot do much. Skykila, are the UV maps right?  You seem to know what you are doing. Is the texture for the amazon players contain face, upper-body, and belt all together?
## Post #31
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-11-02T17:36:00+00:00
- Post Title: Re: Rage (idTech5) model format md6

Update for Blender249:
-add materials with correct uv (no the face UVs overlapping )
[import-rage-2011-11-02.zip](https://xentaxbackup.github.io/file/4824_import-rage-2011-11-02.zip)
## Post #32
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-02T17:38:38+00:00
- Post Title: Re: Rage (idTech5) model format md6

was there a bug in our code szkaradek123?
## Post #33
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-11-02T17:54:48+00:00
- Post Title: Re: Rage (idTech5) model format md6

Qartar wrote: "At the very end of the file there is a footer with a list of materials, generally more materials than there are surfaces so I'm not sure what it represents."

This part is important for reading correct textures:

File format for this section:

dword[1] - nMaterials
nMaterials x {
dword[1] - long
string[long] - name of the material
dword[1] - get object id 
dword[1] - get vertex id from object id - id_min
dword[1] - get vertex id from object id - id_max
id_max = id_max+1
}
## Post #34
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-02T22:10:30+00:00
- Post Title: Re: Rage (idTech5) model format md6

cool, thx. fixed!
[rage.7z](https://xentaxbackup.github.io/file/4826_rage.7z)
## Post #35
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-11-03T00:47:43+00:00
- Post Title: Re: Rage (idTech5) model format md6

u guys really amazing!thanks
## Post #36
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2011-11-03T08:33:37+00:00
- Post Title: Re: Rage (idTech5) model format md6

This is a very very very cool! But what about animation?
## Post #37
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-03T09:41:20+00:00
- Post Title: Re: Rage (idTech5) model format md6

anim files don't look that difficult, it's just a matter of having enough time. there are so many anim files all over the place (many shared animations). i provided source code so if anyone else who has the time wants to try... be my guest .
## Post #38
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2011-11-24T16:22:51+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Skykila
>
> 

This is ALL models
http://www.multiupload.com/FQYQXSR2RM

Do you have the textures decompiled? If so, I've got the Blender importer working for the models and believe I could manually apply the textures now.

Or, can you tell me what tools I would need to decompile the textures myself?
## Post #39
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2011-11-24T21:22:39+00:00
- Post Title: Re: Rage (idTech5) model format md6

RAGE uses 4 megatextures for whole game so good luck using that with models, unless you cut it.
For reference, Megatexture is what Google Maps uses for example, from afar it's nice and dandy but from up close it's horridly blured, it's 1 texture of giant proportions that covers everything or almost everything in software it was used in. Very bad idea for games really.
## Post #40
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2011-11-24T21:39:01+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Panzah
>
> RAGE uses 4 megatextures for whole game so good luck using that with models, unless you cut it.
For reference, Megatexture is what Google Maps uses for example, from afar it's nice and dandy but from up close it's horridly blured, it's 1 texture of giant proportions that covers everything or almost everything in software it was used in. Very bad idea for games really.

I have no problem cutting it. The UV map of the models appears to be preserved with the import script linked above, and I don't mind the work. I just need the files themselves.

EDIT: Here's a view from Blender of the models:
## Post #41
- Username: rev3n4nt
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 15, 2011 7:49 am
- Post datetime: 2011-12-17T02:36:26+00:00
- Post Title: Re: Rage (idTech5) model format md6

Alright!  You guys are amazing! It would be awesome if there is a way to grab those textures out of the game 
P.S
By the way..I made my own doomguy model  just a few month before the game "Rage" out..and it's too sad that some modeller from Id software made it already  ..just want it to check
## Post #42
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-02-20T19:03:54+00:00
- Post Title: Re: Rage (idTech5) model format md6

was able to unpack the bmodel, bcm, and use the rage.exe to create the ls files...
Blender (2.49b) import script errors out when trying to import the bmodel file - (or bcm)
Traceback (most recent call last):
 File rage.py line 365 in importer
 File rage.py line 282 in parser
 File rage.py line 116 in Bf
struct.error: unpack requires a string argument of length 4

Tried importing the .ls files using Lightwave 3D 9, but no luck there.
Lightwave files are .lwo, the .ls file opens in lsed.exe (script editor) but only as text,
how do I get it loaded as a model? (lightwave noob here - work mostly with 3dsmax, maya, and daz/poser)

any help greatly appreciated.
## Post #43
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-20T19:58:17+00:00
- Post Title: Re: Rage (idTech5) model format md6

Open Modeler.
Select Utilities tab.
Select LScript > LScript from menu.
Find ls file.
Click Open.
Done.

As for textures, hooking the OpenGL API is still on my TODO list. If anyone wants to try, I can give you my replacement core OpenGL 1.2 header and source file. All you gotta do is modify the glTexImage2D function (which still applies in OpenGL 3.3), compile it as a DLL, place the new OpenGL32.dll in the game directory and hopefully Rage doesn't contain code to prevent people from hooking the OpenGL API. It will forward calls to the system OpenGL32.dll if necessary.

If you don't know how to compile a DLL, don't even bother trying he he he.
[opengl.7z](https://xentaxbackup.github.io/file/5093_opengl.7z)
## Post #44
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-02-21T04:58:59+00:00
- Post Title: Re: Rage (idTech5) model format md6

Thanks for quick reply, imports work now - uv maps don't seem to always work though.
Not really a problem since we don't have textures ^0^

Blender import is supposed to have the UV mapping but still can't get that script to work. 



and I was so happy when I got the Red Faction models out too...
## Post #45
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-02-22T23:47:40+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from rmezatang
>
> Thanks for quick reply, imports work now - uv maps don't seem to always work though.
Not really a problem since we don't have textures ^0^

Blender import is supposed to have the UV mapping but still can't get that script to work. 



and I was so happy when I got the Red Faction models out too...

Which Red Faction game? I own Armageddon but I've been unable to figure out anything for its models. 

As for RAGE, I still hope that it gets figured out sometime. Howfie--I have no idea how to do the things you described. I learn more modding tricks everyday, but I think you're well over my head at the moment.

And while I'm talking about models that haven't been figured out yet, if anyone gets the chance to work on Brink, I would be overjoyed. There's the gibbed trunk thing, but I can't figure that out. I'm not even sure it unpacks the files to a usable format.
## Post #46
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-02-23T00:33:01+00:00
- Post Title: Re: Rage (idTech5) model format md6

Guerrilla and Armageddon

```
http://forum.xentax.com/viewtopic.php?f=16&t=3309&p=66385&hilit=red+faction#p66385
```
## Post #47
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-02-24T04:34:53+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Szkaradek123
>
> Update for Blender249:
-add materials with correct uv (no the face UVs overlapping )

ok, so I can finally get the blender script working and the models come in (mostly) - still some memory errors on a few but it doesn't crash Blender.

Not sure if I understand the UV Map here, I can't get it to export anything meaningful for the UV Texture Map (either FBX or OBJ export)

Still, I suppose it's a moot point until someone figures out how to unpack the Textures
Been playing around with the OPEN Gl Capture programs but they don't use the most current OPENGL functions so that's not happening (GLIntercept and GLXtractor) 

Anyone still following this thread?
## Post #48
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-02-24T06:20:27+00:00
- Post Title: Re: Rage (idTech5) model format md6

Cupertino Exploded View



next step, create new textures...
## Post #49
- Username: rev3n4nt
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 15, 2011 7:49 am
- Post datetime: 2012-02-24T23:54:24+00:00
- Post Title: Re: Rage (idTech5) model format md6

Pictures of doom bobblehead model using blender script & colored in Zbrush 4 - Spotlight
## Post #50
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-02-25T01:13:04+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from rev3n4nt
>
> Pictures of doom bobblehead model using blender script & colored in Zbrush 4 - Spotlight
 

Does this mean you've been able to extract usable RAGE textures? Or is that a custom texture?
## Post #51
- Username: rev3n4nt
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 15, 2011 7:49 am
- Post datetime: 2012-02-25T01:26:38+00:00
- Post Title: Re: Rage (idTech5) model format md6

Blender script get the model itself & UV coordinates, i just put that model into Zbrush and put in spotlight these pics and painted over 
It's just speed way to get a diffuse map before the texture problem is solved 
Here is the pics from net which i used in spotlight:
## Post #52
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-02-25T01:41:29+00:00
- Post Title: Re: Rage (idTech5) model format md6

OK, so which script got you the usable UV Coordinates, there are a couple here and I'm no Blender expert.  I got the models, but where can you see the UV Map?
## Post #53
- Username: rev3n4nt
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 15, 2011 7:49 am
- Post datetime: 2012-02-25T01:55:34+00:00
- Post Title: Re: Rage (idTech5) model format md6

When you using the script, open the model, for example:
D:\Works\Rage\scientist\md6\vehicles\class2\*.bm6model
when the model loads,change from object mode to edit mode in 3d view, and in the UV\Image Editor you can see the UV coordinates 
just save the model in some format..hope you know whot ot do next
## Post #54
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-03-01T13:00:21+00:00
- Post Title: Re: Rage (idTech5) model format md6

Thanks, I actually worked out some of that my searching the blender manual.
Get some strange results if you play with the UV Map buttons though, you can quickly get new UV Maps generated, replacing the old ones. Now I need time to look at them both and see which one is more usable.
It would be great if the meshes, in general, consisted of more individual meshes, not just one big one, easier to break up into several UV Maps and assign textures, imho.
Some, like the character armor sets, are set up this way.

Just got my Dynasty Warriors 7 models extracted, and ME 3 is downloading, so lots to do over the next couple of weeks, waiting for the umodel update for ME3 too.
## Post #55
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-04-30T01:11:05+00:00
- Post Title: Re: Rage (idTech5) model format md6

yeah, most have moved on.
Firstly, you'll need to move back to Blender 249b (not 263), that's the more stable one most people use. Be sure and get the accompanying Python code or nothing will work properly.
I had all the same problems so you may go back through this thread and re-read my posts/replies I received as I finally got it working...
## Post #56
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-04-30T07:59:13+00:00
- Post Title: Re: Rage (idTech5) model format md6

you said..."convert the .bmodel files into .ls but i cant get over the last hurdle "

this may be the problem

From top of .blend code...
#2011-11-02 Glogow Poland Mariusz Szkaradek
#Rage game bmd6model importer
#press alt+p and select file

you need to select the .bmd6model file (not the .bmodel or .ls file)

for ease of import, I deleted all the other files from my extracts, makes it easier to find them

can you verify which file you tried to import?


p.s. I get an annoying beeping on some imports and it crashes, on others it beeps but still imports ok.
Just get it exported to your preferred file type and move to the next model.
## Post #57
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-05-01T01:49:32+00:00
- Post Title: Re: Rage (idTech5) model format md6

you're welcome. I did try the lightwave imports (really annoying) and just about everything else, all the script versions, all the other model files.
I finally read the code and found the developer comments - made me feel like such a noob for trying the wrong files too.
## Post #58
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2013-08-10T23:18:26+00:00
- Post Title: Re: Rage (idTech5) model format md6

too bad the game sucks and the models are all shit
## Post #59
- Username: dragbody
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-11T05:47:24+00:00
- Post Title: Re: Rage (idTech5) model format md6

Harsh, bro.
## Post #60
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-12-20T03:36:43+00:00
- Post Title: Re: Rage (idTech5) model format md6

I am sorry to bump this but I am at my wits end.

 Bought Rage for 3 bucks off steams more recent sales.

 used the tool kits to extract most of the meshes in the game (large amount of files there.)

 so I have loads of the md6model files I want. got blender and I downloaded the scripts off this listing. the problem for a dum dum like me is the import/export scripts are in .blend format rather then .py format.

 I've tried google for hours and it doesn't seem to have any more information this this posting.

 I downloaded the last tool set called "Rage.7z" which has a Rage.exe file. so I dragged on of the Md6 models into it and got a .ls file.

 I don't seem to have a .ls script with blender 2.49b so I am totally lost. can anyone tell me how to import these models into blender cause nothing seems to be working and I am pulling my hair out on this. thank you for your help.
## Post #61
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2013-12-20T05:28:52+00:00
- Post Title: Re: Rage (idTech5) model format md6

If you bought it on steam, you should also be able to download the Rage Tool Kit.  That contains most of the models in md6mesh and lightwave .lwo files.  The real "bonus" though is the textures in .tga format which no one has been able to extract from the game.
You can open these up in lightwave and export obj, fbx, etc. for further editing.
## Post #62
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-12-20T15:52:28+00:00
- Post Title: Re: Rage (idTech5) model format md6

I didn't see the tool kit but I'll look it up on steam.that said I have the models out thanks to Quickbms but getting them to play well or at all with blender has not made me like blender when compared to my native program of 3d max. anyways thanks for the suggestion of the tool kit.
## Post #63
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2014-04-15T18:26:33+00:00
- Post Title: Re: Rage (idTech5) model format md6

Huge thanks to all contributors who made it possible!

Need a little advise here. I never used Blender untill today. 3ds max is my main tool, Maya and zBrush sometimes as well.

So i tryed to use that import script Szkaradek123 wrote. First i installed the latest atm version - 2.70. Script didnt worked due to syntax errors. So i deleted that version and installed 2.49 (i've seen this version has been mentioned in this thread already). And i still getting error, different one this time:



I am not sure but i thinks it's because i have a wrong version of python. So, which versions of Blender and Python i have to sue to get this script working?
## Post #64
- Username: BjornBear
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 17, 2014 3:47 pm
- Post datetime: 2014-04-17T22:57:20+00:00
- Post Title: Re: Rage (idTech5) model format md6

I've got the exact same issue as Artmancarver. Using Blender 2.49b, getting the same error. I've tried a bunch of different things to get it wokring, nothing seems to be helping.
## Post #65
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2014-04-17T23:08:54+00:00
- Post Title: Re: Rage (idTech5) model format md6

Before the toolkit was released, a xentax user uploaded all RAGE models. The blender script for them was written based on these files. However, I know the script does NOT work on the files with the same name and extensions that come in the toolkit. I don't remember for sure, but i believe the .RESOURCES BMS script still unpacks the archive so that the b6models can be imported to blender. (I think that's the file extension. You'll need to make sure.)

I can double check this information when I'm at my PC. Blender 2.49b is the correct version.
## Post #66
- Username: BjornBear
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 17, 2014 3:47 pm
- Post datetime: 2014-04-17T23:12:08+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from dragbody
>
> Before the toolkit was released, a xentax user uploaded all RAGE models. The blender script for them was written based on these files. However, I know the script does NOT work on the files with the same name and extensions that come in the toolkit. I don't remember for sure, but i believe the .RESOURCES BMS script still unpacks the archive so that the b6models can be imported to blender. (I think that's the file extension. You'll need to make sure.)

I can double check this information when I'm at my PC. Blender 2.49b is the correct version.

I've tried both. I used the BMS script to pull the files from the original game and also tried the ones from the Toolkit. Both produce the same error for me. Need a string argument of 4. I don't even know what that means lol.
## Post #67
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2014-04-17T23:13:21+00:00
- Post Title: Re: Rage (idTech5) model format md6

What file extension are you trying to import?
## Post #68
- Username: BjornBear
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 17, 2014 3:47 pm
- Post datetime: 2014-04-17T23:15:24+00:00
- Post Title: Re: Rage (idTech5) model format md6

.BMD6MODEL file
## Post #69
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-04-18T02:44:59+00:00
- Post Title: Re: Rage (idTech5) model format md6

That error usually means your python version is incorrect. I use 2.6 and 3.2 SDKs and Mariusz's scripts work fine. I see you have 2.5. Sometimes updating your python makes a difference.
## Post #70
- Username: BjornBear
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 17, 2014 3:47 pm
- Post datetime: 2014-04-18T06:23:23+00:00
- Post Title: Re: Rage (idTech5) model format md6

I've been using Python 2.6. I'll take a look later tonight at some of the later versions. Thanks.

Edit: Using Python 2.7.6 and the 3.4 versions didn't work. Same exact error.

There isn't anything like this script for 3ds Max is there? Blender and Python just seems like a bit of a headache.
## Post #71
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-04-18T08:43:11+00:00
- Post Title: Re: Rage (idTech5) model format md6

Does it occur for all BMD6MODEL files, including ones from an unupdated game? I looked at mariusz's code and line 116 is fine pretty much no matter python 2 or 3. Only thing I can think of is that these extractors were written 2 1/2 years ago and were based off some sample files somebody posted on here (probably from a pirated version of the game). Line 116 is trying to read 4 bytes and convert it into a floating-point number, but it is failing (most likely due to reaching end of the file). So python is fine. File format changed during an update maybe? Also, I think mariusz said it didn't work for complex models as well.

Upload a sample, I deleted the files a LONG time ago.
## Post #72
- Username: BjornBear
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 17, 2014 3:47 pm
- Post datetime: 2014-04-18T09:01:52+00:00
- Post Title: Re: Rage (idTech5) model format md6

Ah, that's probably what it is. Mine's a Steam game. I think I'll just call it quits lol. I don't feel like downloading the massive 32 gigs or whatever this game is through a torrent or something for the original version.
## Post #73
- Username: Ganonmaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 29, 2013 3:11 am
- Post datetime: 2014-05-23T22:40:02+00:00
- Post Title: Re: Rage (idTech5) model format md6

I've been trying the importer with bmd6model files extracted from Wolfenstein: The New Order using the bms script found [here](http://forum.xentax.com/viewtopic.php?p=94802#p94802). Same error as artmancarver and BjornBear mentioned. In case anyone wants to take a look and fix up the blender importer, it would be very much appreciated! [Here's two example files](http://www.sendspace.com/file/61cdrt). Hope it helps!
## Post #74
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-24T14:01:13+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Ganonmaster
>
> I've been trying the importer with bmd6model files extracted from Wolfenstein: The New OrderIf you need the mesh only try this tool: [http://www.uploadmb.com/dw.php?id=1400939640](http://www.uploadmb.com/dw.php?id=1400939640)
(quick hack only)



deathsheat.JPG (200.29 KiB) Viewed 370 times
## Post #75
- Username: Ganonmaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 29, 2013 3:11 am
- Post datetime: 2014-05-24T23:50:06+00:00
- Post Title: Re: Rage (idTech5) model format md6

Thanks, that seems to be working!
## Post #76
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-05-25T00:18:09+00:00
- Post Title: Re: Rage (idTech5) model format md6

So meshes are fine, but how are we supposed to get textures? iirc there was never a way to get textures for Rage models and we had to wait until the toolkit got released before we could get them in tga. A toolkit seems highly unlikely for this game.
## Post #77
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-06T18:34:04+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Ganonmaster
>
> I've been trying the importer with bmd6model files extracted from Wolfenstein: The New Order using the bms script found here. Same error as artmancarver and BjornBear mentioned. In case anyone wants to take a look and fix up the blender importer, it would be very much appreciated! Here's two example files. Hope it helps!

shakotay's tool works on smaller models, but it breaks on the larger ones (over 65535 verts). Which is sad since so many Wolfenstein models are larger than that.

I looked into this, the main problem seems to be that MachineGames changed the bmd6model container so the skeletal data is separated out into a file pointed to (usually with extension *.bmd6skel) while before the skeletal data was included.  They also added a bit more padding. I was able to hack up a workaround that can extract the full models into blender 2.49b but it's a two step process.

First you have to run this QuickBMS script on your bmd6model, choose 'Y'es when it asks to overwrite (it's just appending to a file), and it will produce a file by the same name called "*.bmd6model.new".  This is basically just tacking on a Rage header with a 1 bone skeleton.


Then use this modified Python Script in the Blend file to import the "*.bmd6model.new" file, and it will import all models, past the 65536 vertice limit.  The only thing lost is the skeleton.
[Wolfenstein Convert.zip](https://xentaxbackup.github.io/file/7553_Wolfenstein Convert.zip)
## Post #78
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-06T18:35:35+00:00
- Post Title: Re: Rage (idTech5) model format md6

Had to do second post for the Blender file.
[import-Wolfenstein-2014.zip](https://xentaxbackup.github.io/file/7554_import-Wolfenstein-2014.zip)
## Post #79
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-09T22:33:06+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #80
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-10T17:50:02+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Wobble
>
> I'm just looking at these MD6 formats, and I don't understand why some of these values are stored as Big-endian,
while other values are completely reversed in memory, like a 4-byte float.  This is neither little-endian
or Big-Endian, and easily confused for a  Big-Endian WORD or SHORT (which a 4-byte float is obviously not).
These RAGE programmers really screwed up this format, imho.

Yes I noticed they go back and forth between Big and Little a lot. Makes things much harder.
## Post #81
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-10T23:37:09+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #82
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-11T03:59:28+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Wobble
>
> Also, in the .bmd6model file, there's a list of bytes after the skeleton string.  Without knowing the bone count,
I don't see how it's possible to continue parsing the file.  It's just an odd dependency that seems sloppy.

Yes for my parser I did a bit of guess work. From what I have seen the format is always like this:



7 long inteters, with the last one value 0x01. Then a byte (alignment I guess) which is usually 0. Then a series of single byte bone numbers, which as you say you can't know for sure how long it is. But, for most models, it's well below 0xC0, and so far with every model I've seen, a value of 0xC0 or greater directly follows the end of the bone list. So I just keep reading bone numbers until I read a value that is 0xC0 or greater.  It's could possibly break on some models if they have enough bones, but so far I've not found one that breaks that pattern. It may be necessary to back up a byte as the 0xCX number may be part of a different value. But it's still a pretty good indicator of where the bone list ends.
## Post #83
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-11T10:08:17+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #84
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-11T18:47:44+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Wobble
>
> Yeah, it looks like the older bmd6model files had the skeleton data embedded in the file,
but then later, it was ripped out to an external skeleton file for the newer models.

So, for the newer models, if you read in the skeleton file first to get the bone count, 
you can continue parsing the bmd6model file without problems.

Have you figured out how bone-vertex assignment works?  I assumed this list of bytes 
was a bone remap list, but even after remapping them, the vertices are still not 
assigned to the correct bone.  The original bone indices are not correct either, so
I assume they must be remapped somehow.

btw, I think long_thing1 to long_thing6 is the model bounding box:
Code: Select allfloat min[3];	// big-endian, reversed floats
float max[3];	// big-endian, reversed floats


And the byte list is equal to the bone count, aligned to 8-bits:
Code: Select all#define ALIGNED8(bits)		(((bits) + 7) & ~7)

Well, using the format originally suggested for Rage, it seems to be working, almost. 


the model reconstructs fine, and the vertices are weighted in what does look to be proper weight groups. But I do see a lot of flaws. And of course the actual weights are not given.

But I do think there was one thing missed when suggesting the orignal format. I think the last 5 bytes are bone assignments, not the last 4.



On models that have no weights, the last 5 bytes are always zero, not just the last 4. It's not a bone number, but is somehow related.

But it still doesn't explain why when using these bytes as bone IDs, there's some apparent corruption of the weight groupings, or why like in the example above, bone '02' is referenced 3 times, that makes no sense really. So clearly there's still something missing.
## Post #85
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-11T20:47:38+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #86
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-11T22:03:04+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #87
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-11T23:23:06+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Wobble
>
> I'm looking at a model called commander60_01, and if I use the 4 bone indices found in the vertex,
they don't assign to the correct bone.  For example, I see his "head" bone is mapped to his left leg vertices,
which is not correct.
Code: Select allname1: "head_02_msh"
name2: "models/characters/standard/commanders/commander60/commander60_head01"

MESH: 4
[ 0] (p: -3.652265, 1.268753, 87.789482),  (uv: 0.945047, 0.509531)  (08AA, 7200, 550A, 984E)  (bone:  16,  11,   8,  16)
[ 1] (p: -2.892268, 2.717173, 88.365829),  (uv: 0.888635, 0.461807)  (2BDA, 6500, 2230, A21A)  (bone:  16,  11,  16,  16)
[ 2] (p: -3.813759, 1.290491, 88.655296),  (uv: 0.945763, 0.469497)  (0BA4, 5C00, 550B, 9C18)  (bone:  16,  11,  16,  16)
[ 3] (p: -2.829458, 2.659876, 87.597191),  (uv: 0.889502, 0.503089)  (28DD, 7900, 242A, 9749)  (bone:  16,  11,  16,  16)
[ 4] (p: -2.774626, 2.734160, 86.362488),  (uv: 0.879250, 0.578442)  (2BDE, 8920, 232A, 8D65)  (bone:  11,  16,   8,  11)
[ 5] (p: -1.714629, 3.216272, 87.410271),  (uv: 0.851318, 0.501059)  (58F9, 7E00, 0958, 9249)  (bone:  16,  11,  16,  16)
...

BONE_COUNT: 122
...
[ 4] name: "spine2"
[ 5] name: "neck"
[ 6] name: "head"
[ 7] name: "leftshoulder"
[ 8] name: "leftarm"		-> bone 8 is not head!
[ 9] name: "leftforearm"
[10] name: "lefthand"
[11] name: "lefthandthumb1" 	-> bone 11 is not head!
[12] name: "lefthandthumb2"
[13] name: "lefthandthumb3"
[14] name: "lefthandindex1"
[15] name: "lefthandindex2"
[16] name: "lefthandindex3"    -> bone 16 is not head!
[17] name: "lefthandmiddle1"
...

The bone byte list is not correct either, if I try to use it as a remap list:

BYTE_COUNT: 128
...
[ 4] bindex:  8  (leftarm)          -> reverse mapping does not remap to head!
[ 8] bindex: 17  (lefthandmiddle1)  -> index 8 does not remap to head!
...


After the triangle list, there are 3 DWORDs:
Code: Select allDWORD dw1;			// 0, 16, or 32
DWORD mesh_bone_count;
DWORD mesh_weight_flag;


Do you know what the first DWORD is used for?  It is always 0, 16, or 32.
I first assumed it might be related to bone remapping (count, offset, starting index?), but it may also 
appear to be bit flags.

I don't know what those 3 DWORDS are, But I do know I encountered at least one mesh that had a flag in that area to indicate it had a secondary UV map (seems to be hair, so double sided transparent faces). 

```
Faces Data[26160]		
DWORD unknown1		16	
DWORD unknown2		1	
DWORD unknown3		1	
BYTE  Extra_UV_Flag	1	
Secondary UV[11080]		
DWORD unknown4		
BYTE Onebyte_End	0

next model or end.
```


I assume the 3 DWORDS you m ean are unknown1 thru unknown3. Not sure their purpose. But the single Byte directly after is a flag. If it's present, additional UV data is present. Will be the same as the original, two floats per vertice.
## Post #88
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-12T00:06:41+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #89
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-12T01:11:02+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #90
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-12T03:31:27+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Wobble
>
> Also, some of the older ID/Doom formats (MD5,etc..) don't store things like vertex normals, binormals, tangents, for lighting.
I think these values are pre-calculated.  So, if they don't store this info, then what remains?  Bone weights?

That is a lot of room for just bone weights.  These don't look like simple byte weights either (0-255).
Compressed SHORT floats don't make sense.  Nor do they add up to 1.0.  Negative weights don't make sense either.

Yes, that's been the real mystery, i can't figure out where they would be placing the bone weights or the normals, unless it's somehow in that 7 bytes of 'unknown' data in the vertex definitions. I think though it's not that unusual for game models to have no normals. But bone weights, a must have.

There is another file associated with each model, with a *.BCM extention. Usually in "Generated\templates\c01\" for instance. Since these files are named the same as various models, it could be they also contain model data. But I haven't yet explored their format.
## Post #91
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-12T11:35:11+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #92
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-11-10T08:05:57+00:00
- Post Title: Re: Rage (idTech5) model format md6

Since I had posted the Wolfenstein:NO bmd6model importer for blender in this thread previously, I figured i'd post the static bmodel importer here as well. Since i had done some work in Tech5 for Evil Within, figured i'd apply that to Wolfenstein as well.  

So this will load Wolfenstein *.bmodel static files to blender 2.49. Much as stated in the Evil Within thread, i've only implemented the most common mesh decoding types, so if something doesn't decode, let me know, there's other formats I didn't implement as they don't seem to be used (so far as I know).
[importStatic-WolfensteinTech5-2014-11-09.zip](https://xentaxbackup.github.io/file/8058_importStatic-WolfensteinTech5-2014-11-09.zip)
## Post #93
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-06-28T22:49:34+00:00
- Post Title: Re: Rage (idTech5) model format md6

Has anyone tinkered with Wolfenstein Old Blood a bit? The bms extraction script works fine, so does the vtex method. The W-TNO tool works too, but there's still the 65535 vertices limit. The model-converting bms script (Wolfenstein convert2.bms) on the other hand doesn't work, and neither does the Ultimate Unwrap 3D plugin.
## Post #94
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-06-29T01:08:30+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #95
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-06-29T01:14:56+00:00
- Post Title: Re: Rage (idTech5) model format md6

Thanks for having a look.

[http://www.file-upload.net/download-107 ... e.rar.html](http://www.file-upload.net/download-10726173/bolt_action_rifle.rar.html)
## Post #96
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-06-29T03:12:39+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #97
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-06-29T14:35:21+00:00
- Post Title: Re: Rage (idTech5) model format md6

No problem
[http://www.file-upload.net/download-107 ... i.rar.html](http://www.file-upload.net/download-10727299/rudi.rar.html)
## Post #98
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-06-29T20:16:37+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #99
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-06-29T22:25:38+00:00
- Post Title: Re: Rage (idTech5) model format md6

That would actually be most helpful.
Its the Wolfenstein: The New Order (BMD6MODEL) plugin for Ultimate Unwrap 3D Pro (x86) v3.x (32-bit)

[http://www.unwrap3d.com/u3d/downloads.aspx](http://www.unwrap3d.com/u3d/downloads.aspx)
## Post #100
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-06-30T01:03:50+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #101
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-06-30T01:45:42+00:00
- Post Title: Re: Rage (idTech5) model format md6

Thanks a lot!
Some files still don't work, i've included those i found so far.
Only if you still have the motivation of course.

[http://www.file-upload.net/download-107 ... f.rar.html](http://www.file-upload.net/download-10728875/wolf.rar.html)
## Post #102
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-30T05:31:16+00:00
- Post Title: Re: Rage (idTech5) model format md6

updated the tool - tested with XP only:


 W-TNO_OB.zip
(55.38 KiB) Downloaded 264 times
## Post #103
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-06-30T12:03:33+00:00
- Post Title: Re: Rage (idTech5) model format md6

[out]
## Post #104
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-06-30T15:31:48+00:00
- Post Title: Re: Rage (idTech5) model format md6

I can confirm that both tools work on everything i tested. Which was pretty much all the characters, weapons, vehicles and most of the items. 
Thank you both very much for your work.
## Post #105
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-16T22:23:00+00:00
- Post Title: Re: Rage (idTech5) model format md6

Sorry for necro-ing the thread, but did anyone eventually figured out how to get skeletons/rigged skeletons? Or is it just impossible?
## Post #106
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-17T10:21:28+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from Portugalotaku
>
> Or is it just impossible?I wouldn't know why it should.
Maybe it's just the large number of face bones which scares scripters away from dealing with the skeleton (ignore number after bonename string):

```
1 "origin" 115
2 "hips" 105
3 "spine" 104
4 "spine1" 112
5 "spine2" 105
6 "neck" 105
7 "head" 110
8 "leftshoulder" 104
9 "leftarm" 108
10 "leftforearm" 116
11 "lefthand" 101
12 "lefthandthumb1" 104
13 "lefthandthumb2" 117
14 "lefthandthumb3" 117
15 "lefthandindex1" 117
16 "lefthandindex2" 100
17 "lefthandindex3" 100
18 "lefthandmiddle1" 100
19 "lefthandmiddle2" 100
20 "lefthandmiddle3" 100
21 "lefthandring1" 100
22 "lefthandring2" 105
23 "lefthandring3" 105
24 "lefthandpinky1" 105
25 "lefthandpinky2" 110
26 "lefthandpinky3" 110
27 "leftweapon" 110
28 "leftforearmroll" 97
29 "leftarmroll" 114
30 "rightshoulder" 114
31 "rightarm" 108
32 "rightforearm" 116
33 "righthand" 101
34 "righthandthumb1" 104
35 "righthandthumb2" 117
36 "righthandthumb3" 117
37 "righthandindex1" 117
38 "righthandindex2" 100
39 "righthandindex3" 100
40 "righthandmiddle1" 100
41 "righthandmiddle2" 100
42 "righthandmiddle3" 100
43 "righthandring1" 100
44 "righthandring2" 105
45 "righthandring3" 105
46 "righthandpinky1" 105
47 "righthandpinky2" 110
48 "righthandpinky3" 110
49 "rightweapon" 110
50 "rightforearmroll" 97
51 "rightarmroll" 114
52 "leftupleg" 114
53 "leftleg" 112
54 "leftfoot" 116
55 "lefttoebase" 102
56 "rightupleg" 98
57 "rightleg" 112
58 "rightfoot" 116
59 "righttoebase" 102

60 "cheekmid_rt" 98
61 "cheekmid_lt" 100
62 "ear_rt" 100
63 "ear_lt" 114
64 "ulip3_rt" 114
65 "ulip3_lt" 51
66 "nose_rt" 51
67 "nasolabial_rt" 101
68 "ulipmid_rt" 108
69 "ulip_rt" 100
70 "mouthcrnr_rt" 112
71 "buccinator_rt" 114
72 "cheek_rt" 114
73 "ulip2_rt" 107
74 "cheektop_rt" 50
75 "nosewrinkler_rt" 112
76 "eye_rt" 114
77 "squint_rt" 101
78 "leyelidouter_rt" 116
79 "leyelid_rt" 114
80 "ueyelidouter_rt" 100
81 "ueyelid_rt" 114
82 "eyebrowinnerfat_rt" 100
83 "eyebrowouterfat_rt" 116
84 "eyebrowouter_rt" 116
85 "eyebrowmid_rt" 114
86 "eyebrowinner_rt" 100
87 "leyelidouter_lt" 114
88 "ueyelidouter_lt" 114
89 "eyebrowinnerfat_lt" 114
90 "eyebrowouterfat_lt" 116
91 "buccinator_lt" 116
92 "jaw" 114
93 "llip_lt" 0
94 "llipmid_lt" 112
95 "llip2_lt" 100
96 "chin" 50
97 "tonguea" 99
98 "tongueb" 103
99 "llip_rt" 103
100 "llip2_rt" 112
101 "llipmid_rt" 50
102 "llip" 100
103 "chin_lt" 108
104 "chin_rt" 110
105 "cheek_lt" 110
106 "mouthcrnr_lt" 107
107 "ulipmid_lt" 114
108 "ulip_lt" 100
109 "ulip2_lt" 112
110 "nasolabial_lt" 50
111 "nosetip" 108
112 "nose_lt" 101
113 "nosewrinkler_lt" 101
114 "cheektop_lt" 114
115 "squint_lt" 112
116 "leyelid_lt" 116
117 "ueyelid_lt" 100
118 "eye_lt" 100
119 "midbrows" 101
120 "eyebrowmid_lt" 114
121 "eyebrowinner_lt" 100
122 "eyebrowouter_lt" 114
123 "squintinner_lt" 114
124 "ulip" 114
125 "squintinner_rt" 117
126 "facedata_eyeslookleft" 114
127 "facedata_eyeslookright" 108
128 "facedata_eyeslookup" 105
129 "facedata_eyeslookdown" 111
130 "facedata_eyescrossed" 100
131 "facedata_l_eyelidsclose" 115
132 "facedata_r_eyelidsclose" 108
133 "facedata_l_eyelidsopen" 108
134 "facedata_r_eyelidsopen" 111
135 "facedata_l_eyelidstighten" 111
136 "facedata_r_eyelidstighten" 104
137 "facedata_l_outerbrowraise" 104
138 "facedata_r_outerbrowraise" 97
139 "facedata_l_innerbrowraise" 97
140 "facedata_r_innerbrowraise" 97
141 "facedata_l_innerbrowlower" 97
142 "facedata_r_innerbrowlower" 111
143 "facedata_l_outerbrowlower" 111
144 "facedata_r_outerbrowlower" 111
145 "facedata_l_browsqueeze" 111
146 "facedata_r_browsqueeze" 101
147 "facedata_l_squint" 101
148 "facedata_r_squint" 117
149 "facedata_l_nosewrinkle" 117
150 "facedata_r_nosewrinkle" 110
151 "facedata_l_nasolabialfurrow" 110
152 "facedata_r_nasolabialfurrow" 114
153 "facedata_mouthopen" 114
154 "facedata_stickylips" 111
155 "facedata_c_upperlipraise" 108
156 "facedata_l_upperlipraise" 97
157 "facedata_r_upperlipraise" 97
158 "facedata_c_lowerlipdepress" 97
159 "facedata_l_lowerlipdepress" 114
160 "facedata_r_lowerlipdepress" 114
161 "facedata_upperlipdown" 114
162 "facedata_lowerlipup" 100
163 "facedata_upperlipbite" 105
164 "facedata_lowerlipbite" 98
165 "facedata_upperlipfunnel" 98
166 "facedata_lowerlipfunnel" 110
167 "facedata_l_lipcornerup" 110
168 "facedata_r_lipcornerup" 101
169 "facedata_l_lipcornerpull" 101
170 "facedata_r_lipcornerpull" 112
171 "facedata_l_lipstretch" 112
172 "facedata_r_lipstretch" 101
173 "facedata_l_lipcompress" 101
174 "facedata_r_lipcompress" 114
175 "facedata_l_lipcornerdepress" 114
176 "facedata_r_lipcornerdepress" 114
177 "facedata_l_dimpler" 114
178 "facedata_r_dimpler" 112
179 "facedata_lippucker" 112
180 "facedata_liptighten" 99
181 "facedata_chinraise" 104
182 "facedata_cheekpuff" 97
183 "facedata_cheeksuck" 112
184 "facedata_nostrildilate" 115
185 "facedata_l_jawsideways" 108
186 "facedata_r_jawsideways" 119
187 "facedata_jawforward" 119
188 "facedata_jawclench" 119
189 "facedata_jawback" 101
190 "facedata_tongueout" 98
191 "facedata_tongueup" 101
192 "facedata_tongueback" 117
193 "facedata_tongueleft" 98
194 "facedata_tongueright" 108
```
(where "facedata xxx" might be no bones at all)
## Post #107
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-17T12:12:19+00:00
- Post Title: Re: Rage (idTech5) model format md6

Facedata seem to be animation presets, but even barring that the number facial bones is insane. I guess this is where most of Rage's budget went.
## Post #108
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-17T13:27:42+00:00
- Post Title: Re: Rage (idTech5) model format md6

Isn't new DOOM using same format? There you can get models with bones and weights. So, here it's possible too. I did script for DOOM with bones, but weights were aouto-generated, since there are other guys which did awesome job with extractors/converters I actually stopped working on DOOM. As I understand you could ask in DOOM topic about supporting Evil Within and other games too, with rigged stuff xD
## Post #109
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-17T23:56:06+00:00
- Post Title: Re: Rage (idTech5) model format md6

I tried doomresex but it crashed on the resource files. I will give the proper extractor tools another go, thanks for the tip.
## Post #110
- Username: GENTEK
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 26, 2015 12:22 pm
- Post datetime: 2018-03-01T04:35:40+00:00
- Post Title: Re: Rage (idTech5) model format md6

Hey guys!  I would like to use the .bmd6anim with the .bmd6model files... someone know tools or informations about that ? 
.bmd6model
[https://cdn.discordapp.com/attachments/ ... .bmd6model](https://cdn.discordapp.com/attachments/220242494250549259/417507949070778379/sentrybot.bmd6model)
.bmd6anim  
[https://cdn.discordapp.com/attachments/ ... e.bmd6anim](https://cdn.discordapp.com/attachments/220242494250549259/417508076074041354/idle.bmd6anim)
## Post #111
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2018-03-01T10:00:43+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from GENTEK
>
> Hey guys!  I would like to use the .bmd6anim with the .bmd6model files... someone know tools or informations about that ? 
.bmd6model
https://cdn.discordapp.com/attachments/ ... .bmd6model
.bmd6anim  
https://cdn.discordapp.com/attachments/ ... e.bmd6anim
You can try using the tool in this thread: [viewtopic.php?f=16&t=17302](http://forum.xentax.com/viewtopic.php?f=16&t=17302)
The second file you have there is the animation data, not the skeleton. Make sure you have the corresponding .bmd6skl file instead. Rename it to .md6skl and drop the model file on the tool. It should convert the model to .smd.
Extracting textures from .bmd6model files don't have an easy method to extract yet. I've heard that daemon1 was working on a tool that could extract textures from Wolfenstein: The New Order and other idtech5 games , but it never got released (except for The Evil Within).
## Post #112
- Username: GENTEK
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 26, 2015 12:22 pm
- Post datetime: 2018-03-04T22:59:34+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from SecretAgent2001
>
> Make sure you have the corresponding .bmd6skl file instead.How to extract these files from RAGE!  .Bmd6Skel ?
## Post #113
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-03-11T00:30:18+00:00
- Post Title: Re: Rage (idTech5) model format md6

is there any way to get to the scenery? They have a tow truck that isn't useable but I think is cool but it isn't an md6model format.
## Post #114
- Username: GENTEK
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 26, 2015 12:22 pm
- Post datetime: 2018-06-20T14:46:09+00:00
- Post Title: Re: Rage (idTech5) model format md6

Sorry to bump but how to extract .bmd6Skel files from RAGE! ?  My extractor seem only extract .bmd6model & .bmd6anim
## Post #115
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-06-20T16:01:46+00:00
- Post Title: Re: Rage (idTech5) model format md6

> Reply from GENTEK
>
> Sorry to bump but how to extract .bmd6Skel files from RAGE! ?  My extractor seem only extract .bmd6model & .bmd6anim

you can't. those are just skeleton files.
## Post #116
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2018-10-10T15:45:57+00:00
- Post Title: Re: Rage (idTech5) model format md6

This is ALL models
[http://www.multiupload.com/FQYQXSR2RM](http://www.multiupload.com/FQYQXSR2RM)

Update the reference please.
## Post #117
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2018-12-06T20:05:36+00:00
- Post Title: Re: Rage (idTech5) model format md6

^^ link isn't working, care to reupload somewhere?
