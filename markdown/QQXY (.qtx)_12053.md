## Post #1
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-10-06T00:32:54+00:00
- Post Title: QQXY (*.qtx)

Hello guys,

Someone can help me in unpack *.qtx files?
I'm want use models from this game.

Download: [https://mega.co.nz/#!MgFQyShJ!dQpLo60ws ... c667_Bkuo4](https://mega.co.nz/#!MgFQyShJ!dQpLo60wswea6R6pk8coMfzAYrR4d6f2Sc667_Bkuo4)
(included with a .qtx file and client.exe)

Thanks guys,
Good night!
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-11-22T11:06:38+00:00
- Post Title: QQXY (*.qtx)

The 3D Object Converter v6.0 supports the following formats:

Tales of Fantasy *.QTX texture format

Tales of Fantasy / QQXY *.SM (Load)
Tales of Fantasy / QQXY *.SKEM (Load)

The textured mode will load the .qtx file automatically if it exists in same place as the .sm or .skem file.
(If the model file is 123.skem it will search for the 123_d.qtx file automatically.)

You can export the loaded texture files (bitmap) using the Tools/Export the material table's textures to .bmp files function.


You can add the texture file to the material table by hand using the following procedure:
- open your model (in this case the !plane.obj file from the attached qtx.zip file)
- (Click on the textured view icon)
- click on the Object and Material selector on the toolbar (from right the first icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK
- Use the Tools/Export the material table's textures to .bmp files function.

(See the qtx2.jpg file form the qtx.zip file!)

[http://3doc.i3dconverter.com/](http://3doc.i3dconverter.com/)
[qtx.zip](https://xentaxbackup.github.io/file/8123_qtx.zip)
