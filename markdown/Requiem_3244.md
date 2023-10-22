## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-08T11:45:09+00:00
- Post Title: Requiem

Another request. This time it is the online game REQUIEM ONLINE.

I don't know what files to post really. There is a DATA folder with a bunch of .VDK files. I will post one called dat.vdk that is 6590kb

There is another called object.vdk that is 419mb. I guess this is the one with 3d models and stuff in it.

[http://www.sendspace.com/file/lf3oec](http://www.sendspace.com/file/lf3oec)

Random pics from game:

[](http://img259.imageshack.us/my.php?image=krux2ho6.jpg)

[](http://img150.imageshack.us/my.php?image=krux1kt6.jpg)

[](http://img211.imageshack.us/my.php?image=mxenoadarknessmu8.jpg)

These pics are from files i have ripped with 3d ripper but still want to catch all models with extractor if possible
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-08T12:13:05+00:00
- Post Title: Requiem

Well what do you know! Some simple googling took me to this page with some more info and even an extractor  Don't know though if possible to get 3d models yet

[http://www.elitepvpers.de/forum/requiem ... ile-2.html](http://www.elitepvpers.de/forum/requiem/137591-vdk-file-2.html)

Seems the 3d models are .nif format witch is a gamebryo file format. There are plguins for 3ds max for it. Gonna check it out
## Post #3
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2008-12-08T15:24:18+00:00
- Post Title: Requiem

The models used in Requiem are .nifs, which can be viewed/editied with niftools ([http://niftools.sourceforge.net/wiki/NifTools](http://niftools.sourceforge.net/wiki/NifTools))

The textures are imbedded right in the .nif files, but can be removed with the Blender nif import plugin.

Good luck!
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-08T16:35:23+00:00
- Post Title: Requiem

i am at work now but manages to import it into max at my luncbreak  Didnt have textures though but probably easy to add. In the game there are some really nifty specular maps i want to have. I wonder if i can get them too. Are they also baked?
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-08T21:22:49+00:00
- Post Title: Requiem

How can i take the textures that are baked? When i import the model in max i see the object but no texture. And i can't find it. There should be an option to extract them somewhere.

I have googled now for hours and i find alot about oblivion and how to put in your own textures but nothing about how to extract baked textures
## Post #6
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2008-12-09T14:00:35+00:00
- Post Title: Requiem

Per my post above, you can get the embedded textures out of the nif by installing blender, installing the blender nif import plugin, then clicking on the option to "Save Embedded texture as DDS" when importing the nif.  It will save the texture in the same folder as your .nif as image00x.dds.

The Requiem nifs don't seem to import into blender very well, but I don't care as I use 'max most of the time. I just used blender to get the textures for the models, which you can't do when using 'max.

I have extracted all of the monster models and most of the textures from the game so far, and there have only been a few textures which won't extract nicely, notably M_Bansn and M_Blacksean.  I'm working on the Character models as we speak.

I think the specular maps are in the alpha channel of the .dds. I'm not very knowledgeable about that subject, but that's what it seems like to me.
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-09T16:35:40+00:00
- Post Title: Requiem

Thank you for that info. I was guessing something like it but first i thought that the blender plugin would be exactly the same. Does it extract normals too?

Specular maps sorta looks like alphamaps so could be correct. I remember so other guy once said he was impressed of the technique that bakes in specular 

I have a hard time separating all the .nif files to get complete characters. In some there are only arms, some only heads, some a t-posed character with a head i don't want  Seems to be alot of working with it.

But i got the GIONT in max, textures with a rip i once made and animated with bones, flawless!
## Post #8
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-11T18:22:59+00:00
- Post Title: Requiem

Ripping the models was pretty easy actually. The VDK Extractor worked like a charm.

Here's a small vid of Kruxena woman walking 

[http://rapidshare.com/files/172458720/requiem.rar](http://rapidshare.com/files/172458720/requiem.rar)
## Post #9
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2009-01-11T12:07:35+00:00
- Post Title: Requiem

Dude, which Niftools version you use? Mine is failed on all of those nif file, even DDS file can not open (it said wrong data)
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-12T03:21:00+00:00
- Post Title: Requiem

Just grab the latest version. you need blender to extract the textures.
## Post #11
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2009-01-12T12:01:38+00:00
- Post Title: Requiem

I'm used lastest version NifSkope 1.0.17.4329. it said ""failed to load file header (version 335544324)"". WTF happen Y_Y
I'm used evilfs.exe to extract because VDK_extract.exe is not running, any problem?
## Post #12
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-12T15:42:14+00:00
- Post Title: Requiem

i have only used VDK extractor and works perfectly with new nifskope and nif importer in max and in blender
## Post #13
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2009-01-13T11:58:55+00:00
- Post Title: Requiem

Mine stupid VKD extractor not running, it say Comdialog is wrong version
Can you upload or send me and VB distribution dll you use? I'm used version from forum above but don't work T_T
