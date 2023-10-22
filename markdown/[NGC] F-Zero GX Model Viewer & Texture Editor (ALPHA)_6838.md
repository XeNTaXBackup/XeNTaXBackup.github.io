## Post #1
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2011-06-23T20:11:11+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

[DOWNLOAD CURRENT VERSION (r2)](http://www.mediafire.com/download.php?ioo1loc1odt9b9v)
download old version (r1)

First you need to unpack the files you want to view with the [F-Zero GX Unpacker and Packer (LZ and ARC)](http://forum.xentax.com/viewtopic.php?f=32&t=6812)

When you launch the program, it'll ask you for a GMA file, then a TPL file. Just select a pair of those and you'll see the model (unless it's one of the models that doesn't work yet. Some models don't work yet. Remember this is an alpha!).

Remember to read COPYING (GPL v3) and CREDITS!

Questions

I don't see anything meaningful.
You're inside the model. Use the mouse wheel to get out.
OR
Hold the middle button and double click with the right button.

How can I explore the model?
Press H for help.

Why are textures messed up in some models?
Short answer: Because I don't know how to handle them correctly.
Long answer: In the model format, there are between 1 and 3 referenced materials for each "section". I don't know what should be choosen in each case, so I just choose the one that's always set. That's usually right, but of course not always   

Also, there does seem to be some way to "rotate" textures. In the init/ folder, there are some objects called ring, which I believe that are supposed to make a circle, but they're displayed as 4 quarters of circumference. The non-drivable side of the roads also appears to suffer from the same issue.


The model I've just loaded looks like the intersection of various models.
OR
Why is the map diagram on the origin of coordinates?
A GMA file isn't really a single model, but a model container. For most files, the models are from the same scene, so rendering all models gives the complete scene, but that's not guaranteed. The game can load any model individually.

Currently the built-in model viewer doesn't support displaying individual parts. However, you can export the model to .OBJ, and control which parts of the .OBJ file you want to see in your favourite editor.

I've exported the models to .OBJ, but when I try to see the model without textures, some faces are black.
This is something related to vertex normals (I don't know if it's OK or it's a bug). In the case of GLC-Player, my model viewer, I have to disable Two-Sided Lighting. You may have a similar option in your program.

There are some .tpl files without any model associated. How can I see them?
When you're asked for the .gma file, hit cancel (it'll not close the program). Then export the model, and you'll find the textures in the output directory./

Compilation instructions
Windows
- Install the Qt SDK (use MinGW, because I used a few C++0x features).
- Install libQGLViewer. There's an installer on the web page, but it didn't seem to include the required libraries, so I compiled it (don't worry, it's very simple).
- Open the project in Qt Creator (or you can use the command line tools).
- Open the .pro file and replace the INCLUDEPATH and LIBS with the right paths.
- Compile.

Linux
- Install the Qt and libQGLViewer packages (of course, make sure you have the development files).
- Open the file in Qt creator (or you can use the command line tools).
- Compile.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-07-28T20:56:46+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

Posting it at the tools blog now. Do you have examples of such models?
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2011-08-22T18:13:28+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

Here's a pretty big update. I still haven't fixed the majority of the model loading problems, and there's still some bugs, but I just want to release something  

Improvements:

 Texture viewer and editor
 Option to show / hide specific models
 Performance improvements
 Quality improvements
 All TPL files are now supported.
 A few more GMA files are now supported.
 Fixed a HUGE bug in the model exporter, which exported all textures upside down.
## Post #4
- Username: molton
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 27, 2011 9:04 pm
- Post datetime: 2011-12-27T13:10:18+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

GameZelda, excellent work on the model viewer and exporter.  I have been trying to modify the models in super monkey ball 2, specifically the monkey target 2 boards for a long time now, and this application is so close to being complete enough to allow me to do that, is it possible to make an import button that does the opposite of the export function and puts the files back into the the .gma .tpl packaging?  I tried myself but got nowhere.  Thanks
## Post #5
- Username: YakuzaDemon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 22, 2013 7:28 am
- Post datetime: 2013-06-22T00:35:14+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

The technique doesn't seem entirely clear to me.  Is this more efficient than using 3d ripper x with a dolphin emulator?  I know you have to play through the game and then "capture" the models and then later clean them up.  Does this method allow us to see the protected file structure on the gamecube mini dics and directly download the game's assets?  Or would we also have to play through it?  Do we need an emulator as well?

Any tips would be greatly appreciated!  Thanks.  I play on making a 3d animated fan project about F-zero.
## Post #6
- Username: StarkNebula
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 24, 2013 12:06 pm
- Post datetime: 2014-03-19T20:20:47+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

I was looking through the source code of gma.cpp and I noticed this line:

```
	for (size_t i = 0; i < materials.size(); i++)
		materials[i].read(input);

	headerBlob = input.read<uint8_t>(headerBlobCount * 0x30); // TODO figure out

	if (input.base().tellg() != baseOffset + endHeaderOffset)
		throw invalid_binary_data("Gcmf [End Header Offset] mismatch.");
```

This error is thrown when opening a Super Monkey Ball GMA despite the fact they (appear) to be formatted the same way. I'm no programmer, but I want to say that you can use 0x00000006 to define the endHeaderOffset size (a 2 byte value that indicates the line on which "GCMF" appears. If 0x06 = 0500, GCMF flag is on 0x000000500.)
I just checked again and it works for most GMAs. I should of taken note of what it didn't work with. All I know is that it does not function character models, probabably due to rotation points and whatnot.



The 0x0098 Flag on 0x00 seems present in the SMB GMAs as well. I'm assuming that defines the data type?

```
enum GcmfDataType
{
	GcmfDataType_Float = 0x98,
	GcmfDataType_Uint16 = 0x99
};
```

If you have a document with your observations on GMA files, would you mind sharing it? I managed to define the TPL format using HxD observations, YAGCD and some of your tpl.cpp source code: [https://i.cloudup.com/BiPM9pgn3x-3000x3000.png](https://i.cloudup.com/BiPM9pgn3x-3000x3000.png). (However, if you have TPL notes spare, could you share it as well?) I'm working my way up to C++ but can't parse source code well at this point.
## Post #7
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2016-08-29T03:41:45+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

broken link
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-29T04:17:39+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

fear not, its on the tools blog   
[blog/?p=310](http://forum.xentax.com/blog/?p=310)
## Post #9
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2016-08-29T17:51:07+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

> Reply from AceWell
>
> fear not, its on the tools blog   
blog/?p=310
File does not exist. Make sure you specified correct file name.  

[blog/wp-content/plugins/download-protec ... 7%CC%9A%D8](http://forum.xentax.com/blog/wp-content/plugins/download-protect/downloader.php?d=%93%E9%C5%D3%9A%9D%EA%D8b%AF%CF%B3%AA%AB%D7%A2%DC%C6%D9%9A%D4%D9a%9C%D6%B1f%9D%D3%E5%D9%CE%9A%88%DF%D0%9Ah%DE%B4d%9A%D3%E1%D8%C6%D9%9A%A2%D6%A3%A5%D6%A5%9B%AA%93%DA%DC%C8%D8%87%A1%98%AD&v=%D4%E5%CD%D7%CC%9A%D8)
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-29T22:52:40+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

its not just that file, it looks like most or all files on the blog are missing
you will have to get Mr.Mouse to see what problem is and hope for a fix
## Post #11
- Username: Aethr
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 26, 2017 3:19 am
- Post datetime: 2017-01-31T21:57:00+00:00
- Post Title: [NGC] F-Zero GX Model Viewer & Texture Editor (ALPHA)

When you say texture editor, does this allow for editing the existing textures on the iso?  I'm very interested in breaking this game apart to figure out how it works. It'd be fantastic to work out how to edit level models and collisions.
