## Post #1
- Username: rickomax
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 07, 2008 11:17 am
- Post datetime: 2016-10-03T22:38:22+00:00
- Post Title: PSXPrev (PSX Model/Texture Viewer)

I'm releasing today PsxPrev, a TMD/TIM PlayStation file scanner.
This tool uses:
GLMNet - https://github.com/dwmkerr/glmnet
SharpGL - https://github.com/dwmkerr/sharpgl
Daniele de Santis Playstation Icons - http://www.danieledesantis.net/

You'll need to run it:
An OpenGL 2.0 compatible video card
.NET Framework 4.5

Treat it as an experimental release and use this tool as your own risk!

The tool can use a big ammount of memory to scan the files, so,
I recommend you close all your work before starting the tool.

To launch the application, run "PsxPrevLauncher.exe"
First of all, select the Folder where are the files you want to scan.

You can specify a filter, to scan individual file/files.

You have option boxes to:
Scan for TMD models
Scan for TIM textures
Generate a log file at the application folder
Output scan messages to the console window

To start scanning, click at the "Scan" button.

A console window will appear, the application will scan each byte of the files inside the folder/filter you specified trying to find the files types you specified, so, it can take a bit of time for this process to end.

After the scan has been completed, a new window will open, with the tabs:
Models: This is where you see the models that has been found on the scan
Textures: This is where you see the textures that has been found on the scan
VRAM Preview: This is where you have a replica of PSX Video RAM, which consist of 32 256x256 textures. You can use these pages to compose the final textures applied to the models.

Usage tips:
To Apply a Texture to a Model, first you have to look at the VRAM Page property of the Model you want to apply the Texture.After that have to draw the textures (at the VRAM Tab, called Draw to VRAM) on the desired VRAM Page (which is pre-defined in the Texture Properties area). After that, if you come back to the Model Tab, you may see your Model textured, if it has Uvs property enabled (True).
To Export a Model or Multiple Models,  tick their checkboxes at the Model Tab, click at Export Selected button, select the desired Output Format and the Output Folder. (Textures and materials will be automatically exported)
To Export a Texture or Multiple Textures, select them at the Texture Tab, click at Export Selected button and select the desired Output Folder.

Known issues/limitations:
The two 3D exportable file formats has disadvantages, .OBJ files cannot have vertex color information, and .PLY files will group all the sub-models in one single model. I'm looking for a better format for the exporter. An experimental .OBJ exporter option with Vertex Color is available.
The tool will only find files that are explicitly conformant to the file formats it's looking for. Any compressed file cannot be scanned.

Download link:
[http://ricardoreis.net/psxprev/psxprev.zip](http://ricardoreis.net/psxprev/psxprev.zip)

The tool may be a bit unstable, so please report any bug here.
## Post #2
- Username: aaro4130
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 23, 2011 10:01 am
- Post datetime: 2016-10-04T00:01:51+00:00
- Post Title: PSXPrev (PSX Model/Texture Viewer)

Unofficial specifications for OBJ state that the vertex statement is as follows:

v x y z cx cy cz 

I've noticed that some importers will actually import this color information.
## Post #3
- Username: rickomax
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 07, 2008 11:17 am
- Post datetime: 2016-10-04T03:19:29+00:00
- Post Title: PSXPrev (PSX Model/Texture Viewer)

Tool updated.
Added an experimental .OBJ Exporter with Vertex Color (works on MeshLab).
Fixed .OBJ and .PLY coordinate system.
