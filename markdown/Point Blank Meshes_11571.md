## Post #1
- Username: ShinobiMao
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Sep 07, 2010 11:41 pm
- Post datetime: 2014-06-04T20:34:19+00:00
- Post Title: Point Blank Meshes

Howdy!

I’m interested in the model format for this free to play fps – Point Blank. 
All of the models have multiple sub objects, such as the character’s hat or helmet (which can be shot off GoldenEye style) as well as unique first person arm&hand models. Since there are no other correspondingly-named meshes in the archives, it leads me to believe that they are stored in the same model file as the character itself.

Further evidence of this fact is in the model file when viewed in a hex editor – just a forewarning, I am an absolute newbie to hex editing, and therefore what I’m about to say and show is probably useless information. I outright apologize for this if it is indeed a waste of your time, but it is all that I know. ツ I really am not seasoned in the field of hex editing, not in the slightest!

With that disclaimer at the forefront, let’s begin. When using this “data visualizer” tool with Hex Workshop I’ve been able to compare the data with well-documented model formats, and from preliminary viewing I can say almost certainly that the models contain almost all data, although another type of chunk is visible, and I can only assume it’s UV data. 

[](http://i.imgur.com/ZMlh2qa.jpg)

These patterns are repeated multiple times, which makes me think the other subobjects are contained inside as well (also considering the vertex blocks seem to have one very large chunk (pictured) and many smaller ones, which makes me think it’s the character, then their hat/head/arms.
And of course, here the sample model (can/will upload more at request!) [Link!](https://www.dropbox.com/s/xb5ai90ppuac9nj/REBEL_Female.I3S)

It is my hope that somebody can provide some insight into this format, and that together we may create a precedent so that those who may want models from future games that may use this engine will have a starting point! ツ
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-06-05T10:47:44+00:00
- Post Title: Point Blank Meshes

Big endian not aligned, multiple VBOs and facelists.

<VBO>
<Facelist>
<VBO>
<Facelist>

etc

I'm not sure if the verticies are packed or not couldn't seem to get anything decent plotting it out
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-06T15:05:20+00:00
- Post Title: Point Blank Meshes

[viewtopic.php?f=16&t=11454](http://forum.xentax.com/viewtopic.php?f=16&t=11454)

@ShinobiMao: concerning your PM: hex2obj was designed for users who "aren't sure how to use it". 
You don't need to know the exact face indices count at the beginning. Just start with 500 if you are unsure.
But don't forget to copy the max face index from the lower left listbox into the editbox for the vertices count.
Read the tutorial ("tut" button) once more.  
(Maybe you've advice how to improve it related to this model format?)



REBEL_female.JPG (35.93 KiB) Viewed 260 times
## Post #4
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-06-08T12:10:50+00:00
- Post Title: Point Blank Meshes

As I started to research this format, I noticed that there are some rotation-values that are targeting at bones etc.?

So, I'm not having enough skills to reverse bones etc., thats why I stopped researching this format. What I have so far is:

```
==================

BYTE { 4 } - Magic ID ("I3R2", no termination)
BYTE { 8 } - Unknown
DWORD { 4 } - Number of Entries in Nametable
DWORD { 4 } - Offset to the Nametable (Begin of file 0 + Offset)

BYTE { x } - Nametable
{
     for NumberOfEntries
          Filename = ReadByte( ) as long as there doesn't come 0x0D-termination
}

```

It could be possible, that the "NumberOfEntries" and "OffsetToNametable" are WORD { 2 }. So there would be some other information between them with 2 byte. But it should be correctly as I wrote above. I can say it savely to you, if I have seen other files.

Hope I could helped just a little bit   Good luck!
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2015-05-25T11:06:38+00:00
- Post Title: Point Blank Meshes

One solution is the 3D Object Converter for Windows (.i3s / .i3i support):
[http://3doc.i3dconverter.com](http://3doc.i3dconverter.com)

Second ones is the i3DConverter (OS X) (.i3s / .i3i  support):
[http://www.i3dconverter.com](http://www.i3dconverter.com)


If you open your .i3s file then you can add the .i3i texture file(s) to the material table by hand (in this case) using the following procedure:
- (Click on the textured view icon)
- click on the Object and Material selector on the toolbar (from right the first icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK


- After it use the Tools/Export the material table's textures to .bmp files function.
  (It converts the .i3i file to .bmp)

- Use the Tools/Set the default texture file extension in the material table function to .bmp

- Export the loaded model to Wavefront .obj format
  (You will have the .obj file that use the .bmp texture file.)
## Post #6
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-05-25T15:27:58+00:00
- Post Title: Point Blank Meshes

Your program is nice and all, but people won't be able to see how the format actually works (read: learn from it)
Though I doubt most people even care, lol.
