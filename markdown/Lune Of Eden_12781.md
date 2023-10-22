## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-20T22:32:35+00:00
- Post Title: Lune Of Eden

Hello guys, well some time ago somebody study this format as far remember, so my question is somebody can take a look into format because I can't load models, the format of files are:

mes and skinmesh=models
textures= edv: they are simple dds

ok many thanks to all support give this years and have a nice day guys.

Samples:

[https://cloud.mail.ru/public/5HzqAxsFqF ... Samples.7z](https://cloud.mail.ru/public/5HzqAxsFqF6N/Lune%20Of%20Eden%203D%20Samples.7z)
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-04-21T09:36:35+00:00
- Post Title: Lune Of Eden

Hm, as far as I remember this game was supported by FatImporter. Is this a newer version of the game?
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-21T13:35:52+00:00
- Post Title: Lune Of Eden

> Reply from zaramot
>
> Hm, as far as I remember this game was supported by FatImporter. Is this a newer version of the game?it won't load all models as far I know, I try a lot models and no load all.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2015-04-21T19:28:54+00:00
- Post Title: Lune Of Eden

One solution is the 3D Object Converter for Windows (.mes/.edv support):
[http://3doc.i3dconverter.com](http://3doc.i3dconverter.com)

Second ones is the i3DConverter (OS X) (.mes/.edv support):
[http://www.i3dconverter.com](http://www.i3dconverter.com)
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-21T19:45:33+00:00
- Post Title: Lune Of Eden

> Reply from Karpati
>
> One solution is the 3D Object Converter for Windows (.mes/.edv support):
http://3doc.i3dconverter.com

Second ones is the i3DConverter (OS X) (.mes/.edv support):
http://www.i3dconverter.comwell mes load fine, about edv no supported, it say me "Unrecognized or unsupported file type (or not valid object found)
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2015-04-22T05:06:04+00:00
- Post Title: Lune Of Eden

You can not open directly the .edv file, because my program is not a bitmap viewer. The program shows it on the loaded models only.

If you open your .mes file then you can add the .edv texture file to the material table by hand (in this case) using the following procedure:
- (Click on the textured view icon)
- click on the Object and Material selector on the toolbar (from right the first icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK
- Use the Tools/Export the material table's textures to .bmp files function.


If you open the !plane.obj from the attached .zip file and you add the .edv file to the material table, you will see the bitmap on the plane.
[!plane.zip](https://xentaxbackup.github.io/file/9082_!plane.zip)
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-22T13:54:04+00:00
- Post Title: Lune Of Eden

> Reply from Karpati
>
> You can not open directly the .edv file, because my program is not a bitmap viewer. The program shows it on the loaded models only.

If you open your .mes file then you can add the .edv texture file to the material table by hand (in this case) using the following procedure:
- (Click on the textured view icon)
- click on the Object and Material selector on the toolbar (from right the first icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK
- Use the Tools/Export the material table's textures to .bmp files function.


If you open the !plane.obj from the attached .zip file and you add the .edv file to the material table, you will see the bitmap on the plane.
yes I forget no support material dds via material attach, thats my fault but anyway thanks for that Karpati, grateful for your help.
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2015-04-22T19:01:27+00:00
- Post Title: Lune Of Eden

Unfortunately the .mes file has not reference to the texture file(s) as I know.
## Post #9
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2015-04-30T00:43:03+00:00
- Post Title: Lune Of Eden

Where can I get client? The service was stopped and there seems no client available anymore.
Can you share?
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-30T02:39:50+00:00
- Post Title: Lune Of Eden

> Reply from bluearms
>
> Where can I get client? The service was stopped and there seems no client available anymore.
Can you share?you can get from here:

[http://web-loe.gg.in.th/Download/download_client.aspx](http://web-loe.gg.in.th/Download/download_client.aspx)
## Post #11
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2015-05-03T12:08:34+00:00
- Post Title: Lune Of Eden

I've tested fatimporter from [viewtopic.php?f=33&t=7901&start=155](http://forum.xentax.com/viewtopic.php?f=33&t=7901&start=155)
It seems work ok with linked client. (*.MES for structure mesh, *.SKM for characters)

Though textures are not loaded.

P.S.
edv files are simplys dds. rename it and apply with hand then works.



snap0167.jpg (105.33 KiB) Viewed 182 times
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-05-03T21:12:03+00:00
- Post Title: Lune Of Eden

> Reply from bluearms
>
> I've tested fatimporter from viewtopic.php?f=33&t=7901&start=155
It seems work ok with linked client. (*.MES for structure mesh, *.SKM for characters)

Though textures are not loaded.
snap0167.jpgyep, because as say in the information of FatImporter and you can see too in picture, is beta script.
## Post #13
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2017-02-14T17:19:24+00:00
- Post Title: Lune Of Eden

can you reupload the client? thnks
## Post #14
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-07-19T22:06:32+00:00
- Post Title: Lune Of Eden

[There](http://forum.ragezone.com/f857/releases-loe-online-server-1003053/) is some sort of graveyard for this dead game (working links to clients in different languages).
