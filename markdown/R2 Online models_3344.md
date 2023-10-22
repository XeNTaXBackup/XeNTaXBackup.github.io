## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-05T16:16:06+00:00
- Post Title: R2 Online models

Hi!

In another thread we found tools to open the protected archives for this game. Now I want to know if someone could take a look at the file structure for models to see if we can convert to something useful. Thanks in advance

Here is the thread:

[viewtopic.php?f=10&t=3255](http://forum.xentax.com/viewtopic.php?f=10&t=3255)
## Post #2
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-06T16:21:32+00:00
- Post Title: R2 Online models

Only had a small time to look at it but this is what I got so far using the same file from the thread posted above:

```
DWORD unknown1[6]; // sample file had the first 24 bytes set to 0
DWORD textureCount; // (?) value was 1 - total count for all model/objects in file?
DWORD modelCount; // (?) value was 1 - total count for all model/objects in file?
DWORD boneCount; // value was 9 and matches the number of "Bone##" entries in the .rab file. also position 0x1C had the value of 9 in the .rab file so I'm assuming this is correct. 
DWORD dataOffset; // this should be correct as well.
char textureFilename[260]; // file name is 0 terminated and then padded to fit at least 260 bytes (which is the maximum length for a path in Windows)
DWORD unknown2[2]; // no idea what this means, could be file padding, file had the following values: 0x00000000 and 0xFFFFFFFF

// file position: 0x130, contains the word "Box03", will get back to this later since I'm currently at work
char objName[64]; // name/reference or something, 64 bytes long, mainly filled with 0's
char name[64]; // same as above, has the name 'root' but that appears multiple times up to the dataOffset value
DWORD unknown3[2]; // (?) could be the modelCount/textureCount like above for this model/object?
DWORD vertexCount; // should be correct as well
DWORD indexCount; // should be correct

// position 0x1C0 to 0x670 is filled with zeros (no idea why or what this means)
DWORD indexCouint; // again the value is here...

// next 396 bytes are all 0 as well...
DWORD vertexCount; // again the value is here...

// 400 bytes later we get to a value of 0xFFFFFFFF
// now at position 0x998
DWORD count; // no idea. file had the value of 4
DWORD values[count]; // assuming the previous 'count' value means the number of values in some kind of DWORD array. file contained the following values: 1, 2, 5, 8

// 64 bytes later...
// file position 0x9EC
// Bone information!
struct Bone[boneCount] {
    char name[64]; // name of bone
    char parent[64]; // name of parent
    float4x4 matrixInfo[3]; // 3 4x4 matrix structures (pos, scale, rot?)
    DWORD childCount; // ?, possible... or index
    DWORD childrenIndex[]; // something like this
} // this structure is still a bit confusing to me, but I do see some patterns



```


As mentioned, I'm at work and will get back to this later. I will skip this part though, for now, and start at the data offset position.
## Post #3
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-06T16:57:52+00:00
- Post Title: R2 Online models

Opps..think I got the vertex/index count switched...have a meeting will fix later
## Post #4
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-06T19:51:44+00:00
- Post Title: R2 Online models

Ok, fixed the order for the vertex/index count. I've been looking over the data for the vertex data and, although they are floats, the values don't make much sense to me. I haven't found an order for position, uv coords or anything like that yet. The size is 56 bytes in length which consists of 14 float values; based on the data I saw.

```
    float data[14]; // I don't know the exact structure. yet...
} 

vertex vertices[vertexCount]; 
```
 

Immediately following the vertex data is what I believe is the bone weight list. Seems to be a group of 4 floats for each vertex. In the sample file, there were 140 vertex. 140 * 4 * 4 = 2240 bytes, which works out well for this file. 

```
    float weights[4]; // bone weights? only saw 3 values: 0, 1, 0.5
}

boneWeights weights[vertexCount];

```


After this seems to be another list of data for each vertex. It's either a list of 2 DWORD values or 4 WORD values. I do not know what this represents. 

This brings us to the last 1032 bytes of the file, which represent the index values. Which fits nicely since this file had a value of 516 for indexCount, which gives us 516 WORD pair values totaling 1032 bytes. 

```
WORD indices[indexCount]; 
```
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-07T01:01:48+00:00
- Post Title: R2 Online models

hm, I am very glad that you started to look at these files. I can in no way help you out when it comes to hexing this so I just hold my thumbs. I looked at the archives and there is no other file format then the ones i provided.

I wish you good luck and hope to see some results

Thanks
## Post #6
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-07T04:22:13+00:00
- Post Title: R2 Online models

Ya, I'll take a look at it this weekend now that I have more files to look at.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-07T08:14:46+00:00
- Post Title: R2 Online models

Nice going, Theran!
## Post #8
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-09T02:25:23+00:00
- Post Title: R2 Online models

So I had a thought earlier today while looking at a different file from R2. I'm thinking the vertex data section is in itself in sections. Meaning that the first section is all the position elements (vertexCount * 3 * 4), then follows normals (vertexCount * 3 * 4), uv coords, etc...

I'm still taking a look at them but having it in this way makes a bit more sense with the values. Now I could be wrong on the order since I haven't had a chance to put any of the values into a simple 3d application. 

Will need to test this out a bit more, but this layout makes some sense.
## Post #9
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-09T18:29:33+00:00
- Post Title: R2 Online models

Ok, does seem to be in a format like I mentioned. Vertex positional data is first, but after that I don't know. It could be normals, followed by the uv's, but I need to get the texture for it so that'll be something I'll do tonight. 

I'm attaching some images for what I got so far. The first image is using what I believe to be the normal values. The second image is using computed normals. 
Images rendered with OpenGL

Edit: Seems I can only do one attached file at a time, so next post will have the second image.
[file1.JPG](https://xentaxbackup.github.io/file/1865_file1.JPG)
## Post #10
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-09T18:30:25+00:00
- Post Title: R2 Online models

And here's the second:
[file2.JPG](https://xentaxbackup.github.io/file/1866_file2.JPG)
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-09T18:47:18+00:00
- Post Title: R2 Online models

Wow that is great news you are so close to having a model viewer.
Thanks for all your hard work on this project.
## Post #12
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-09T19:44:57+00:00
- Post Title: R2 Online models

It's definitely a good start, but there's still a lot of info in there that we still don't know yet but we'll get there.
## Post #13
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-09T20:52:39+00:00
- Post Title: R2 Online models

Yeah definitly cool! I saw that objects in game have another format. .r3m

I wonder if a model + texture of a static object would make things easier?

I provide the easist i can see:

R_danger_Alpha.r3m 2kb
R_danger_Alpha.dds 1kb
[r2 objects.rar](https://xentaxbackup.github.io/file/1867_r2 objects.rar)
## Post #14
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-09T22:08:19+00:00
- Post Title: R2 Online models

Ya, I saw some of those as well. I will check tomorrow since I'm getting attacked by my allergies today and heading home.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-09T22:16:33+00:00
- Post Title: R2 Online models

Offtopic: Your allergies? What up? I've got all kinds, though, basically allergic to all kinds of stuff, what are yours?
## Post #16
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-10T18:48:00+00:00
- Post Title: Re: R2 Online models

OK! Made some progress with the model/texture provided by pixellegolas:

@Mr.Mouse: I'm allergic to lots of stuff: dust, pollens, food, etc... Weather seems to affect me the most so when it changes or is about to rain, I get all crappy. 

Pic 2 in next post
[file1.JPG](https://xentaxbackup.github.io/file/1869_file1.JPG)
## Post #17
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-10T18:50:00+00:00
- Post Title: Re: R2 Online models

Pic 2:

Also pixellegolas, since I'm still at work right now, can you package any more model/texture (the r3m is fine) files so that I could test? Something with a better texture since the one used by the file you gave me is kinda hard to tell if I'm using the right values.

Edit: This pictures are of the same layout I'm testing, pic 1 is from the "front", pic 2 is from the "back".
[file2.JPG](https://xentaxbackup.github.io/file/1870_file2.JPG)
## Post #18
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-10T20:30:30+00:00
- Post Title: Re: R2 Online models

Hi!

Really hard to find model + texture that have a match in name so i just grab something here that seems to belong 

[http://rapidshare.de/files/45127498/merman.rar.html](http://rapidshare.de/files/45127498/merman.rar.html)


Good luck!
## Post #19
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-10T21:19:24+00:00
- Post Title: Re: R2 Online models

Thanks. Also can you post NSFW on those links to offsite file hosts, that link had some 'adult content' in them, good thing I'm in a cube
## Post #20
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-10T22:01:09+00:00
- Post Title: Re: R2 Online models

NSFW?

Of course i can post to another site with the next files  Didn't know it had stuff like that. I sometimes turn off pictures in internet explorer when stuff like that pops up
## Post #21
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-10T22:36:59+00:00
- Post Title: Re: R2 Online models

NSFW = Not Safe For Work

Hehe, it's cool. They were just banners and such, but just caught me off guard a bit. But on a good note, I think I understand the layout now. I haven't tried yet with the .rmb files, but it should be similar to the .r3m files, at least for the vertex data. 

They seem to follow this pattern:
position
normals
uv
unknown1 (3 floats/vertex)
unknown2 (3 floats/vertex)

The latest files provided by pixellegolas really helped as they had something that is more real looking. There's still tons of stuff that needs to be figured out but I've made some good progress. 

The attached image is from the file 'R1_OB_mermanhome_T2.r3m'. It's a pillar type object with 1 texture.
[file1.JPG](https://xentaxbackup.github.io/file/1871_file1.JPG)
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-10T22:37:54+00:00
- Post Title: Re: R2 Online models

The contents of this post was deleted because of possible forum rules violation.
[m00025_1.JPG](https://xentaxbackup.github.io/file/1872_m00025_1.JPG)
## Post #23
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-11T06:53:04+00:00
- Post Title: Re: R2 Online models

Well still needs a bit of work, but it's coming along fine.
[file1.jpg](https://xentaxbackup.github.io/file/1873_file1.jpg)
## Post #24
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-11T07:24:57+00:00
- Post Title: Re: R2 Online models

Made a minor change to the format. Looks like it's the texture count first, then the mesh count next. Rest seems the same for the rmb files. The r3m files don't contain some of the extra data though.

Also, can anyone confirm the above picture to the ingame model?
## Post #25
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-11T09:25:50+00:00
- Post Title: Re: R2 Online models

hm, sorry, can't confirm, is that a .rmb file? I can maybe get you a model later on that i have a ingame screenshot of
## Post #26
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-11T15:53:59+00:00
- Post Title: Re: R2 Online models

Yes, it's a rmb file. It's from the packages chrrox posted. I'll try to work on it a bit today as there's still more model information in the file from the image I posted. And ya, if you can get any ingame shots that'd be perfect.
## Post #27
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-11T16:07:52+00:00
- Post Title: Re: R2 Online models

ok, i can do it in 2 hours, but did he post normal and specular maps too? many objects seem to have those also
## Post #28
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-11T16:28:14+00:00
- Post Title: Re: R2 Online models

> Reply from pixellegolas
>
> ok, i can do it in 2 hours, but did he post normal and specular maps too? many objects seem to have those also

Yep, but that's still a long way away for now. I just want to see how things match up.
## Post #29
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-11T22:29:42+00:00
- Post Title: Re: R2 Online models

[http://rapidshare.com/files/196968941/r2_girl.rar.html](http://rapidshare.com/files/196968941/r2_girl.rar.html)

This is

Girl body

Girl Head

Girl Hair

Textures + model + image from ripped character in max showing all views
## Post #30
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-12T01:50:57+00:00
- Post Title: Re: R2 Online models

> Reply from pixellegolas
>
> http://rapidshare.com/files/196968941/r2_girl.rar.html

This is

Girl body

Girl Head

Girl Hair

Textures + model + image from ripped character in max showing all views

The girl minus her head. There's still a few minor things that cause my loader to fail, but I now have files that have that so it'll be a bit easier to debug.
[file1.jpg](https://xentaxbackup.github.io/file/1874_file1.jpg)
## Post #31
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-12T01:54:43+00:00
- Post Title: Re: R2 Online models

Here's the correct goblin thingy from a few posts back. I had an error with loading the texture that was flipping the image. I noticed it on the in game image of the girl and found that I didin't need to flip it.
[file1.jpg](https://xentaxbackup.github.io/file/1875_file1.jpg)
## Post #32
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-12T02:54:15+00:00
- Post Title: Re: R2 Online models

That looks much better you are doing a great job and a great speed also 
If you want any more models i will post some for you and in game screens if needed.
## Post #33
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-12T03:12:37+00:00
- Post Title: Re: R2 Online models

> Reply from chrrox
>
> That looks much better you are doing a great job and a great speed also 
If you want any more models i will post some for you and in game screens if needed.

Thanks! I always thought these models were really nice looking. But I have all the 'character' models and textures extracted so I can view/test them all easily now; well except at work. 

I also got alpha textures working so they'll look a bit nicer now.
## Post #34
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-12T06:57:00+00:00
- Post Title: Re: R2 Online models

impressive!
## Post #35
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-13T13:39:29+00:00
- Post Title: Re: R2 Online models

I am updating this thread all the time, waiting for more info. A real cliffhanger  R2 has very beautiful models. Hope to get models and animations later on to analyze them totally
## Post #36
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-13T16:16:00+00:00
- Post Title: Re: R2 Online models

Ya, sorry I haven't been able to update it recently. I did try to play around with what I believe is the bone data for the model. By default, as many 3d models are, the given vertex data is in a standard pose; in the case of R2, they are in a standing with their arms slightly fanned out from the side. However my attempt was not successful and it really messed up the model lol. 

So if anyone has any good links to any kind of helpful info please let me know. I will also update the model format for the "rmb" files. I'd say it's about 85% complete with the last 15% in the "I have no idea" or "I think it's formatted like this" category. So expect this sometime this weekend. 

I will also release the code I have for viewing the models that I posted. It's built in C# (though it should be easily ported to C++ or other languages) and runs using OpenGL for it's graphics using sample code from NeHe Productions ([http://nehe.gamedev.net/](http://nehe.gamedev.net/) which is a great site). 

Hoping to have this by Saturday.
## Post #37
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-02-15T13:07:49+00:00
- Post Title: Re: R2 Online models

Excellent, looking forward to it!
## Post #38
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-15T20:20:49+00:00
- Post Title: Re: R2 Online models

Note that this applies to only RMB files. 

```
DWORD unknown[4];
DWORD textureCount;
DWORD meshCount;
DWORD boneCount;
DWORD dataOffset;

struct string {
  char filename[260];
} textures [textureCount];

struct mesh {
  DWORD index; // 0?
  DWORD unknown1; // -1?
  char meshName[64]; / name of mesh
  char parent[64]; // name of parent bone
  DWORD extraFlag;
  DWORD unknown2; // 1?
  DWORD vertexCount; // number of vertices
  DWORD indexCount; // number of indices

  //no idea what the next 2000 bytes are, so just skip it, sure it's relevant somehow...
  byte data[2000];
} meshes[meshCount];

// next area is the bone information which I left I work...though it's still mostly incomplete, will add this in tomorrow
// for now, can skip to the dataOffset location
struct meshData {
  floatx3 pos[meshes[index].vertexCount];
  floatx3 nomral[meshes[index].vertexCount];
  floatx2 uv[meshes[index].vertexCount];
  floatx3 unknown1[meshes[index].vertexCount];
  floatx3 unknown2[meshes[index].vertexCount];
  if (mesh[index].extraFlag == 1) {
    floatx4 boneWeights[meshes[index].vertexCount];
    WORDx4 boneMatrixIndex[meshes[index].vertexCount];
  }
  WORD indices[meshes[index].indexCount];
} meshData[meshCount];
```


That's basically it...rather messy I know but it's enough to display/render the mesh in it's default pose. When reading the mesh data it's laid out like so:
positional data (3 floats x,y,z)
vertex normal data (3 floats nx,ny,nz)
texture coords (2 floats u,v)
unknown data (3 floats)
unknown data (3 floats)
*It's possible that this could be some kind of translational or rotational values.
if (extraFlag == 1) 
  bone weight data (4 floats x,y,z,w)
  bone matrix data (4 WORD values)
end if


I'm off to do some rock climbing so I will post my source later today.
## Post #39
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-15T20:44:12+00:00
- Post Title: Re: R2 Online models

Very nice work i look forward to playing around with the source code.
## Post #40
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-16T19:49:29+00:00
- Post Title: Re: R2 Online models

OK! Here's the C# project I've been using to render the loaded meshes. It's fairly simple to use. It runs on OpenGL so make sure you have that which most should. The project is a Visual Visual C# Express 2008 (express editions are free to download from Microsoft's website) project but can/should be easily converted to different languages/versions. 

The majority of the code is in the TestGL.cs file and the important methods are:
readRMB (loads the rmb file)
loadImage (loads the dds files and generates the OpenGL textures for them)
loaded (called when the form is done loading, which is after the rmb file is loaded, so that it knows when to load the textures)
OnPaint (does the rendering)

the "readRMB" method has the filename hard coded into it like so:

```
        private void readRMB() {
            string meshFile = path + "p070000.rmb";
            ...
        }
```

This line just points to the location of the extracted rmb files

```
const string path = "C:\\models\\";
```

And it assumes that the extracted textures are located a directory inside this folder and is named "texture"
So the full path to the rmb file would be as such:

```
C:\\models\\p070000.rmb
```

And the texture folder would be:

```
C:\\models\\texture\\
```

Not very elegant but it works. Ideally the code should work smarter but I just kept it like this because I was lazy and it was easy   

If anyone wishes to expand on what I got and make the animations/skinning work, by all means do so. I have limited knowledge on that subject but I'm gonna research it a bit more and update if necessary.
[NeHeCS.rar](https://xentaxbackup.github.io/file/1884_NeHeCS.rar)
## Post #41
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-16T21:13:07+00:00
- Post Title: Re: R2 Online models

Very nice work works great. I will try to implement a drag and drop method for loading the files and if i can figure it out hopefully a way to control the camera with the mouse.
## Post #42
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-02-16T22:19:03+00:00
- Post Title: Re: R2 Online models

great work! Alot of thumbs up and star ratings for you. Let's hope someone with skills can pick this up and expand
## Post #43
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-17T02:13:06+00:00
- Post Title: Re: R2 Online models

I found a c# tutorial for loading animations from milk shape 3d files which could be applied here as it is just a different file format.
[http://www.sichbo.ca/Free_Code/Milkshap ... and_OpenGL](http://www.sichbo.ca/Free_Code/Milkshape_3D_Animation_using_C_Sharp_and_OpenGL)

I almost got drag and drop working but it does not load the textures ill figure it out.
edit "doh i think I will get this working soon i am a fool lol"
## Post #44
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-02-19T16:20:06+00:00
- Post Title: Re: R2 Online models

Today I released the 3D Object Converter v4.221 update at 17:10.

You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates).


My program currently supports 8 different uncompressed types of the DirectDraw Surface *.dds texture format. The R2: Reign of Revolution uses the compressed .dds format.

When I wrote and tested my .rmb loader module I used the following procedure to get the texture shaded view (in my program):

- Convert the .dds files into .jpg files using the Irfanview's batch converter module.
- Run the 3D O.C.
- Check out the Options/Import/Default texture file extension (.jpg)
- Turn on the 'Options/Import/Set the default texture file extension in the material table after load'
  (This will replace the .dds file extension to .jpg automatically after load your object)

  (Or you can use the 'Tools/Set the default texture file extension in the material table after every load if you would like...)

- Save settings.
- Apply settings.
- Load the .rmb file.


[http://web.t-online.hu/karpo](http://web.t-online.hu/karpo)
## Post #45
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-02-20T16:20:27+00:00
- Post Title: Re: R2 Online models

Very nice.
## Post #46
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-23T19:46:00+00:00
- Post Title: Re: R2 Online models

I added the keys e, d , r, f to add more movement freedom.
I am going to work on mouse movement I feel I am close to getting it down.
I am also trying out some ideas for menu selection in another form to set the directory
then get lists of all the models and separate them into categories based on names ex head parts, npc, items.
[NeHeCS.rar](https://xentaxbackup.github.io/file/1890_NeHeCS.rar)
## Post #47
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-03-10T21:15:12+00:00
- Post Title: Re: R2 Online models

Made some progress with the r3m files loaded in the Objects.rfs (static objects) file. 

Most share a common name, w1_monster_001.r3m, w1_monster_002.r3m, ..., w1_monster_006.r3m, which make up complete model. So far, having good luck with getting them to view properly. Each r3m file can contain a number of sub objects in them, usually 1 object per texture. So a complete model consists of multiple r3m files (meshes), each with a multiple number of sub objects (1 per texture?). 

I haven't gotten the textures to work just yet, but I'll try to get that in the next day or so. So for now, here's a screen shot of what I got:

Model uses the following files:
R1_OB_bridge_rargon_01.r3m
R1_OB_bridge_rargon_02.r3m
R1_OB_bridge_rargon_03.r3m
R1_OB_bridge_rargon_04.r3m
R1_OB_bridge_rargon_05.r3m
[file.JPG](https://xentaxbackup.github.io/file/1913_file.JPG)
## Post #48
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-10T21:54:13+00:00
- Post Title: Re: R2 Online models

Very nice work on the static meshes.
Do you know of any open source obj exporters out there i can try to add that export option if I can find an example.
## Post #49
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-03-10T22:10:18+00:00
- Post Title: Re: R2 Online models

> Reply from chrrox
>
> Do you know of any open source obj exporters out there i can try to add that export option if I can find an example.

No I do not, but this site has the basic structure for OBJ files:
[http://www.fileformat.info/format/wavefrontobj/egff.htm](http://www.fileformat.info/format/wavefrontobj/egff.htm)
## Post #50
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-03-10T22:30:55+00:00
- Post Title: Re: R2 Online models

this is getting really interesting! just hoping for animation and all that glory too
## Post #51
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-03-11T07:35:20+00:00
- Post Title: Re: R2 Online models

Got textures working, it's looking pretty good!
[file.jpg](https://xentaxbackup.github.io/file/1915_file.jpg)
## Post #52
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-03-11T12:00:34+00:00
- Post Title: Re: R2 Online models

it sure does  Is it also specular and such?
## Post #53
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-03-11T16:16:52+00:00
- Post Title: Re: R2 Online models

> Reply from pixellegolas
>
> it sure does  Is it also specular and such?

Maybe? lol   

I'm still learning the basics of doing lighting and such with OpenGL. Currently it does ambient and diffuse lighting, but that's about it. Though I believe you're referring to specular textures ya? If so, I believe for this particular model, all the textures are normal kind (sorry if that doesn't make sense, I'm still learning the lingo).
## Post #54
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-03-11T16:38:03+00:00
- Post Title: Re: R2 Online models

most models are like this:

Diffuse map: the normal map that you refer to. It is the models texture to give it color

Normal map: Is like a bump-map that makes certain parts stick out or in to add detail without actually adding polygons. Used in example gears of war alot

Specular map: Special map that tells the engine where to add specularity when a light hits the surface. Instead of using a engine specific specularity all over a model you decide how the specularity will look on a model.

If you have a model that has clothes on like jeans you don't want the jeans to reflect like it would be metal, but you want the belt to, then you add specularity to belt only

Glow map: Makes certain areas of model glow. If you have helmet and want to make visor glow, you add a map where you only add color where visor is, that area will glow

These are the most used ones
## Post #55
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-03-11T17:00:27+00:00
- Post Title: Re: R2 Online models

Ah, then no, it only uses diffuse maps. Got a bit of work to do today but I'm adding in some options for changing the lighting of the model (giving it diffuse, ambient, specular, shininess properties) to make it look more real like. So I'll get that done by tonight. So by this weekend I'll release another app for just r3m files as well as the overall format of the file which is about 80% done. 

Think I only need to check the rfs files for any kind of XML format so I can tell which files to load for a specific model, the one pictured is a combination of 5 r3m files. I know the rmb files had something similar so I'm hoping these do as well.
## Post #56
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-03-17T18:16:38+00:00
- Post Title: Re: R2 Online models

So I totally forgot I had to go out of town this weekend so I wasn't able to upload any files but I'm back today and I bring files!

Sample was built using Microsoft Visual C# 2008 Express Edition and CsGL ([http://csgl.sourceforge.net/](http://csgl.sourceforge.net/)). You'll need to download the CsGL package and run the batch file to install the necessary files. 

As for the format, here's the basic structure:

```
dword nTextureCount; // number of textures used by this model
dword unk2; 
floatx3 max; // bounding box max pos
floatx3 min; // bounding box min pos
// note the source file I updated has these switched for some reason...correct order is max, then min.

string textureNames[nTextureCount]; // array of texture names used by this file, string names are variable length, null terminated.
// some data is contained after the string name but I never found any solid info from it, so I just skipped it, about 50/50 it's either random data or empty data
dword nFlag; // describes the type of model layout, values (271, 1295, 1311)
dword nObjCount; // number of objects in this model, generally nTextureCount = nObjCount
dword nVertexCount; // number of total vertices
dword nIndexCount; number of indices

// meshInfo describes the way how many vertices and indices are used by the current object/texture as well as their offsets
struct meshInfo {
    dword nVertextCount; // number of vertices used
    dword nIndexCount; // number of indices used
    dword nVertexStart; // starting offset for vertices
    dword nIndexStart; // starting offset for indices
} info[nObjCount];

floatx3 pos[nVertexCount];
floatx3 normal[nVertexCount];
dword color[nVertexCount]; // color perhaps? only used when nFlag = 1311
floatx2 uv[nVertexCount];
flaotx2 uv2[nVertexCount]; // second set of uv coords? used when nFlag = 1295 & 1311
floatx3 unk1[nVertexCount];
floatx3 unk2[nVertexCount]; // both unk1 and unk2 are in all layouts, like rmb files, no idea what it represents

short indices[nIndexCount]; // index layout
```

[R2Online.rar](https://xentaxbackup.github.io/file/1922_R2Online.rar)
## Post #57
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-03-17T20:25:07+00:00
- Post Title: Re: R2 Online models

Realized I forgot to mention how the app works. 

Keys: 1-8, 0 (changes lighting)
Uses the movement keys defined by chrrox with some minor modifications. 

Since I've been unable to find any kind of file that lists which files create an entire model, I was simply just coping the ones that had similar names into a directory (defined by 'path' in the application). Likewise, I had all the textures from the Objects.rfs (in the texture/Object folder, defined in 'tpath' in the application). 

I choose this since I could easily copy/paste tested files over to a sample directory and the application would just load them all. 

Every now and then there will be a file that cannot be loaded, generally has an "_L" or "_light" in the file name, this refers to what I believe is a lighting file (still with r3m extension) and is structured like so:

```
struct light {
    floatx3 pos; // light position
    floatx3 color; // color? diffuse maybe?
    float f1; // float value: ranges from 1-5, power? 
    float f2; // float value: range? attenuation?
    float f3; // float value: range? attenuation? (I think always greater then f2) 
} lights[count];
```


If anyone can help with this let us know. 

I think that explains the application as far as I can tell. I think I got everything now.
## Post #58
- Username: jarrro
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 02, 2017 5:30 pm
- Post datetime: 2017-10-02T13:39:51+00:00
- Post Title: Re: R2 Online models

guys, how do you export the model from .rmb?
## Post #59
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-10-02T17:23:23+00:00
- Post Title: Re: R2 Online models

> Reply from jarrro
>
> guys, how do you export the model from .rmb?

One solution is the 3D Object Converter for Windows
[http://3doc.i3dconverter.com](http://3doc.i3dconverter.com)

Second ones is the i3DConverter (macOS)
[http://www.i3dconverter.com](http://www.i3dconverter.com) 


I am using the XNALara Binary .mesh export format as a 'gateway' to transfer the fully textured objects (with Bone information) to the 3D Studio Max.

You can download the Importer/Exporter script from this web page:
[http://www.tombraiderforums.com/showthread.php?t=181251](http://www.tombraiderforums.com/showthread.php?t=181251)


Procedure:
1. First time you must copy the "XnaLara Converter.ms" file into your installed 3D Studio Max Scripts folder.
2. Run your 3D Studio MAX

3. Open your .mgm file with 3D O.C.
4. Export the loaded object as XNALara Binary .mesh format.

5. Run your "XnaLara Converter.ms" script using the MAXScript/Run Script... menuitem.
6. Press the Import button on the XNALara Converter window.
7. Browse the converted .mesh file.
[R2_to_mesh.zip](https://xentaxbackup.github.io/file/13371_R2_to_mesh.zip)
## Post #60
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-10-02T17:25:31+00:00
- Post Title: Re: R2 Online models

To avoid the forum message: Cannot add another attachment, 1 is the maximum
[R2_3DOC.jpg](https://xentaxbackup.github.io/file/13372_R2_3DOC.jpg)
## Post #61
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-10-02T17:27:11+00:00
- Post Title: Re: R2 Online models

To avoid the forum message: Cannot add another attachment, 1 is the maximum
[R2_3DSMax.jpg](https://xentaxbackup.github.io/file/13373_R2_3DSMax.jpg)
## Post #62
- Username: kazhuki01
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Jun 19, 2012 1:46 am
- Post datetime: 2018-02-13T21:12:02+00:00
- Post Title: Re: R2 Online models

how to get models from this game? no available unpackers for .rfs format
## Post #63
- Username: simaggin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 16, 2016 7:50 am
- Post datetime: 2019-09-10T14:46:27+00:00
- Post Title: Re: R2 Online models

> Reply from kazhuki01 ↑Wed Feb 14, 2018 5:12 am at Wed Feb 14, 2018 5:12 am
>
> 
how to get models from this game? no available unpackers for .rfs format

.rfs format it is archive.
Use WinRAR or another archivators for unarchiving this file.

Password: 4a3408a275b0343719ae2ab7250a8cab0c03b2178a58f2de
## Post #64
- Username: AkselRus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2022 6:27 am
- Post datetime: 2022-08-25T22:42:22+00:00
- Post Title: Re: R2 Online models

How to save a new model to .rmb?
