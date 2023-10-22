## Post #1
- Username: Sirusdark
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 26, 2016 1:21 pm
- Post datetime: 2016-01-26T07:16:43+00:00
- Post Title: How to export a model from Noesis to XNA/Blender

Hi!
I'm experimenting model extraction from Ghost in the Shell Stand Alone Complex First Assault Online and I'm now stuck at the Noesis level...
[http://www.mediafire.com/view/bugxzaqm7 ... us_001.jpg](http://www.mediafire.com/view/bugxzaqm7z8433x/gits-maven_a_extract-by-sirus_001.jpg)

I'm having a very hard time exporting the model from Noesis to something usable in either XNA or Blender:  it finds duplicate mesh names & bone names, the Material Library doesn't follow (XNA complains there's no mlt) and Blender show multiple duplicates of the model when imported. Oh, and definitely no textures so far. lol

Export log (here, an example for a .obj export):

```
.obj - WaveFront OBJ
Detected file type: Gamebryo NIF
NIF version: 30 2 0 3
User version: 0 0 0 0
WARNING: Duplicate mesh names detected.
Renaming meshes.
WARNING: Duplicate bone names, overriding.
Outputting to WaveFront obj.
Wrote file to D:\XNA Lara\Exports\t4.obj.
```

Any ideas what I'm doing wrong? Thanks!

Using Noesis v.4.165
## Post #2
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-01-26T14:49:41+00:00
- Post Title: How to export a model from Noesis to XNA/Blender

[http://bfy.tw/3vT3](http://bfy.tw/3vT3)
## Post #3
- Username: Sirusdark
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 26, 2016 1:21 pm
- Post datetime: 2016-01-26T16:07:27+00:00
- Post Title: How to export a model from Noesis to XNA/Blender

Very kind of you!

I was totally looking in the wrong direction. I used the Noesis to XNA export script from [http://xnalara.org/viewtopic.php?f=17&t=1139](http://xnalara.org/viewtopic.php?f=17&t=1139).
I'll report back as soon as I can! (compiled mesh isn't working, yet. I use GeMeshAsciiToBin.exe)
## Post #4
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2022-03-06T10:18:06+00:00
- Post Title: How to export a model from Noesis to XNA/Blender

What is the current best way of converting or loading the ascii? There is a model or two that the UVs are odd in the smd and want to check them via the ascii since it says that file is the only one with the multiple UV pairs.

edit: seems it loads fine in blender with the xna lara plugin if the plugin is edited to just skip textures since the ascii has null texture names. Doesnt seem to fix a certain uv issue with a character's sleeve though. It still gets exploded.
