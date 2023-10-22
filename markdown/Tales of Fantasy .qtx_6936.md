## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T02:38:58+00:00
- Post Title: Tales of Fantasy .qtx

The contents of this post was deleted because of possible forum rules violation.
[texitem.7z](https://xentaxbackup.github.io/file/4447_texitem.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-08T02:43:01+00:00
- Post Title: Tales of Fantasy .qtx

they are just dxt1 images without the header
[Caijt_I_Mamian02_M.qtx.png](https://xentaxbackup.github.io/file/4449_Caijt_I_Mamian02_M.qtx.png)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T02:43:25+00:00
- Post Title: Tales of Fantasy .qtx

lol that was quick. Thanks chrrox.
Where can I get the header from?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-08T02:45:31+00:00
- Post Title: Tales of Fantasy .qtx

any dds file here is the file i converted.
[Caijt_I_Mamian02_M.qtx.rar](https://xentaxbackup.github.io/file/4450_Caijt_I_Mamian02_M.qtx.rar)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T02:52:44+00:00
- Post Title: Tales of Fantasy .qtx

hmm I tried copying the header to this one and then convert to png, but it didn't work.
[Caijt_I_Fushi03_B.7z](https://xentaxbackup.github.io/file/4451_Caijt_I_Fushi03_B.7z)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-08T03:00:04+00:00
- Post Title: Tales of Fantasy .qtx

its just dxt5 and the header you made has the wrong dimensions
[sm.rar](https://xentaxbackup.github.io/file/4453_sm.rar)

[Caijt_I_Fushi03_B.qtx.png](https://xentaxbackup.github.io/file/4452_Caijt_I_Fushi03_B.qtx.png)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T04:11:31+00:00
- Post Title: Tales of Fantasy .qtx

Oh. How can I figure out the dimensions?
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-07-08T12:07:59+00:00
- Post Title: Tales of Fantasy .qtx

> Reply from finale00
>
> Oh. How can I figure out the dimensions?
You need guess.
Make several black textures in photoshop with different dimension (128x128, 256x256...) and look on the size of it.
Then compare the size of game texture and your new black textures. After that copy the header from black texture to game texture that have same size.
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-17T01:25:34+00:00
- Post Title: Tales of Fantasy .qtx

Tosyk but where the header start and finish in the .qtx files? cause its very encrypted, i see the files chroxxx posted but i see no only the header changue, all the structure of the files are changued from .qtx to .png.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T03:02:41+00:00
- Post Title: Tales of Fantasy .qtx

That was just one of the samples converted to png (since I wanted to convert to png but failed cause my header was wrong).

The first attachment shows a qtx file with a header inserted.
The original qtx file did not have a header.
## Post #11
- Username: jacquel
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 29, 2011 5:21 pm
- Post datetime: 2011-12-17T19:14:14+00:00
- Post Title: Tales of Fantasy .qtx

i find the solution.
thanks to chrrox and Tosyk for your help.  
cheers
jacque
## Post #12
- Username: troll1981
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 10, 2014 2:28 am
- Post datetime: 2014-06-27T10:19:35+00:00
- Post Title: Tales of Fantasy .qtx

sorry for questions, but how i open qtx Texture Files ?  its 2014!

In Noesis i see the mesh in white with no textures, the same texture has the same meshname but its .qtx File, how i can export in dds or tga  ?
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-11-22T11:09:26+00:00
- Post Title: Tales of Fantasy .qtx

The 3D Object Converter v6.0 supports the following formats:

Tales of Fantasy *.QTX texture format

Tales of Fantasy / QQXY *.SM (Load)
Tales of Fantasy / QQXY *.SKEM (Load)

The textured mode will load the .qtx file automatically if it exists in same place as the .sm or .skem file.
(If the model file is 123.skem it will search for the 123_d.qtx file automatically.)

You can export the loaded texture files (bitmap) using the Tools/Export the material table's textures to .bmp files function.


You can add the texture file to the material table by hand using the following procedure:
- open your model
- (Click on the textured view icon)
- click on the Object and Material selector on the toolbar (from right the first icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK
- Use the Tools/Export the material table's textures to .bmp files function.

[http://3doc.i3dconverter.com/](http://3doc.i3dconverter.com/)
