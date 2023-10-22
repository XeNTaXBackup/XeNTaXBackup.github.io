## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-09-03T03:46:54+00:00
- Post Title: 3DS Max the unsolved mistery

I investigate in forums and inside of the program and i found one think incredible and ridiculous, this come since 3DS max first versions and the programers never solve this, for a program with value of $2500USD Licence i think its a joke, in lots of games the world coordinates axis its X= Deep, Y = Height and Z = width, but in 3ds Max the coordinates its X= Deep, Y = Width and Z = Height, the point its i need export a model, to do this i need rotate the model 90° degrees, but with this action i destroy the animation, also if i rotate with bones and animation active, 

VIDEO TEST
[http://www.youtube.com/watch?v=AxRWBywT ... e=youtu.be](http://www.youtube.com/watch?v=AxRWBywTp8U&feature=youtu.be)

Files in the Video
[http://www.mediafire.com/?f8tsh4g6s8jfg54](http://www.mediafire.com/?f8tsh4g6s8jfg54)

Here i get a idea, only changue the world coordinates of 3DS Max and then export, but ITS NOT POSIBLE!!!!, 1 million of menus and options, and this simple think its not enabled in the program, maybe i am wrong and the program have some option to rotate and not destroy the animation if somebody know why i really apreciate the help.

P.D. FBX format can changue this in export, u can switch Y and Z, but if u import to 3DS Max the exported FBX files (sucks filther) its back to normal position, and the plugin i have its to export from Max.
## Post #2
- Username: drunkenchipmunk
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 24, 2009 4:05 pm
- Post datetime: 2012-09-03T15:21:55+00:00
- Post Title: 3DS Max the unsolved mistery

Axis coordinate systems are a neccesary evil.

3dsMax was originally AutoDesk 3D Studio, and came along AutoDesk AutoCad, which uses X Y for surface coordinates, and Z for height... 3dsMax began being used for videogames much later.

Most videogames use DirectX or OpenGL axis coordinate systems, which use Z to front and Z to back respectively, so when converting from 3DS to DirectX or OpenGl, you need to "rotate" the scene 90 degrees forward or backwards.

Btw, you have a similar problem if you convert an asset from OpenGL to DirectX or the other way, you have to flip the Z from back to front ... it's not a problem related only to 3DSMax.

As far as I know, 3dsMax does not support using different axis coordinates, and I don't think it will support it anytime soon... I suspect a full, safe axis switch in 3ds would require all plugins to be aware of the change, because some plugins might be sensitive to such a switch. Putting the burden of handling axis switching on all Max plugin developers is probably too much.

FBX on the other hand, was designed since the very beginning to support axis switch, being one of its main features.

Mistery solved?
## Post #3
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-09-03T21:02:40+00:00
- Post Title: 3DS Max the unsolved mistery

Every company out there interpret the 3d space in a different way, you'll find this issue when you try to export-import models from one program to another every damn time
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-09-06T06:37:58+00:00
- Post Title: 3DS Max the unsolved mistery

Good answer thanks.
