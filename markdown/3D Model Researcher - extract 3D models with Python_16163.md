## Post #1
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-04-18T18:02:24+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

3D Model Researcher is a program for studying binary files of 3D models. Model Researcher allows to display and visualize the data read from the file with the specified parameters, and also save them in the 3D Obj format. The program is a great help with the search for vertex data, faces, texture coordinates and normal vectors in an unknown 3D format. The main feature of the program is the support of the scripts in the programming language Python, which allows to extract models from almost any format.





Opportunities
- Analyze the 3D model files, search of vertices, faces, texture coordinates, normal vectors
- Data output is presented textually
- Data visualization in 3D format
- Visualization of texture coordinates
- Highlight data structure in the built-in Hex-Viewer
- Applying textures to the model
- Support of Python scripts
- Normals vectors
- System of submeshes
- Loading and saving templates with form values
- Data export in Obj format

Video:
[Work of the program](https://youtu.be/mM37ITBOMCw)

Page of the program:
[http://mr.game-viewer.org/](http://mr.game-viewer.org/)

Guide:
[http://mr.game-viewer.org/tutorial.php](http://mr.game-viewer.org/tutorial.php)
Scripts usage:
[http://mr.game-viewer.org/tutorial.php? ... mr_scripts](http://mr.game-viewer.org/tutorial.php?name=tut_mr_scripts)
Description of API functions:
[http://mr.game-viewer.org/tutorial.php?name=API](http://mr.game-viewer.org/tutorial.php?name=API)

Thanks to herbert3000 for developing the program [Model Inspector](http://forum.xentax.com/viewtopic.php?f=33&t=14648). The interface was copied from it.
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-04-18T23:24:38+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

amazing! I will stay tuned to your tool for new updates.
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2017-04-19T06:20:40+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

I was going to code something like this but never got around to it.
Thankyou!
## Post #4
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-04-21T16:55:03+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

Updated the program.
Now the program has all the functions that I planned to add.
## Post #5
- Username: flipdark95
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 08, 2016 12:24 pm
- Post datetime: 2017-06-11T14:14:11+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

So just wondering, is there a basic guide for using this? Do I use it directly on model files?
## Post #6
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-07-03T13:27:19+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

> Reply from flipdark95
>
> So just wondering, is there a basic guide for using this? Do I use it directly on model files?
Yes, such a guide will be published on the program page. The new version of the program will support texture!
## Post #7
- Username: Ronny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 09, 2017 10:33 pm
- Post datetime: 2017-07-05T06:35:55+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

Will it support animations in near future.
## Post #8
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-07-05T09:39:52+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

I already thought about it, it would be great. But with animation, everything is much more complicated: there are already bones, matrices, weights. It's not so easy to add support.
## Post #9
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-07-06T20:40:43+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

A new version has been released! Added support for textures. The guide will soon be translated into English.
## Post #10
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-07-12T21:02:48+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

Update
The guide is translated into English!
[http://lazov.ru/mr/tutorial.php](http://lazov.ru/mr/tutorial.php)

What changed?
- Now the program supports Half-Float and Short
- A grid is drawn when UVs is displayed
- In the 3D View tab, added a small button - the function of centering the camera on the model.
- Changing the height and zoom of the camera
- You can change the background color, grid color, polygon color, vertex color. Saving settings.

The new version does not support Windows XP. If you need support for this operating system, write to me.
[trtянный.png](https://xentaxbackup.github.io/file/13098_trtянный.png)
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-15T12:06:15+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> The new version does not support Windows XP. If you need support for this operating system, write to me.
If you could just add support for half-float and shorts and skip FF bytes in face indices to the previous version that would suffice.
## Post #12
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-07-15T13:31:24+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

AceWell,The type of half-float appeared in new versions of Python, which do not support Windows XP.
What are the FF bytes? I heard about it, but I did not see such models. Can you give an example?
## Post #13
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-15T14:45:15+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> AceWell,The type of half-float appeared in new versions of Python, which do not support Windows XP.
What are the FF bytes? I heard about it, but I did not see such models. Can you give an example?

FF bytes are used to indicate a triangle strip reset normally.
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-15T15:51:35+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> What are the FF bytes? I heard about it, but I did not see such models. Can you give an example?
there is a sample attached (si00bobj006_01_1.xfbin) to the bottom of this post that has the "FF FF" bytes in the face indices
[viewtopic.php?p=80935#p80935](http://forum.xentax.com/viewtopic.php?p=80935#p80935)
## Post #15
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-07-15T16:52:31+00:00
- Post Title: 3D Model Researcher - extract 3D models with Python

Thanks guys!
Update the program. In the old version, there was a large memory leak in the text output of the data.
## Post #16
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-07-15T16:57:24+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

> Reply from Lazov
>
> AceWell,The type of half-float appeared in new versions of Python, which do not support Windows XP.
What are the FF bytes? I heard about it, but I did not see such models. Can you give an example?
[https://www.khronos.org/opengl/wiki/Vertex_Rendering](https://www.khronos.org/opengl/wiki/Vertex_Rendering)
See primitive restart section
## Post #17
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2017-07-17T14:53:00+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

Thanks for sharing! Awesome tool, man! Thanks again and keep up the good work!
## Post #18
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-07-19T20:01:17+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

RedBear, Thank you!

The program has been updated!
- Now the textures with different height and width are correctly displayed.
- Added scrollbar for large textures.
- Added Triangle Strip (Tri Strip FF) format. (If you select this format in the "Count" field, you need to specify the number of elements, not the segments.)
--------------------------------------------------
Does anyone have a file with a model that uses "Triangle Strip" without 0xffff?
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-20T04:01:19+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

> Reply from Lazov
>
> Does anyone have a file with a model that uses "Triangle Strip" without 0xffff?
there is one attached to the post here
[viewtopic.php?p=128749#p128749](http://forum.xentax.com/viewtopic.php?p=128749#p128749)
A004_Ojama_Yellow_b.pc.model
## Post #20
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-08-25T19:47:58+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

A small update.
Now the Offset field supports hexadecimal numbers.
## Post #21
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2017-10-01T14:58:56+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

Super nice app! I like it already 
Tried on binary data, but got some noobish trouble, could you help me? main post is here:
[viewtopic.php?f=16&t=10812&p=134144#p134144](http://forum.xentax.com/viewtopic.php?f=16&t=10812&p=134144#p134144)
## Post #22
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-10-01T17:40:41+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

> Reply from Sparagas
>
> Super nice app! I like it already 
Tried on binary data, but got some noobish trouble, could you help me? main post is here:
viewtopic.php?f=16&t=10812&p=134144#p134144
Thank you!
I looked at the format. I think, with the help of this program the model is not exported. The format is quite complicated.
## Post #23
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-11-26T08:46:19+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

Update v2.3

 - Added support for Triangle Strip without FF.
 - Now the program does not crash when drawing a texture map at a nan.

The Pro version of the program was released

 - Support of Python scripts
 - System of submeshes
 - Normals vectors

With the support of scripts, you can extract a 3D model from a file with any structure.

About Pro version:
[http://lazov.ru/mr/about_pro.php](http://lazov.ru/mr/about_pro.php)
## Post #24
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2017-12-29T20:27:12+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

Please, tell how to run this program on Windows 7 x64? When I tried to run it, it required  api-ms-win-crt-runtime-l1-1-0.dll. I downloaded these Dlls for both Win32 and Win64 versions, copied them in system\win32 and system\WoW64 folders, but it doesn't help. Now the program shows the error message 0xc000007b and I cannot run it. What to do to fix that issue?
## Post #25
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-12-29T22:49:48+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

> Reply from Ditta
>
> Please, tell how to run this program on Windows 7 x64? When I tried to run it, it required  api-ms-win-crt-runtime-l1-1-0.dll. I downloaded these Dlls for both Win32 and Win64 versions, copied them in system\win32 and system\WoW64 folders, but it doesn't help. Now the program shows the error message 0xc000007b and I cannot run it. What to do to fix that issue?
Try installing:
[https://yadi.sk/d/RQFGFsrw3R6tb4](https://yadi.sk/d/RQFGFsrw3R6tb4)

Also install the latest updates for Windows 7.
## Post #26
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-01-03T17:19:57+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

Ditta
Your files with models contain very little information. I did not find there any necessary data for building a model in the program.
## Post #27
- Username: Ditta
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 13, 2015 11:07 pm
- Post datetime: 2018-01-03T18:00:37+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

> Reply from Lazov
>
> Ditta
Your files with models contain very little information. I did not find there any necessary data for building a model in the program.

Oh, sorry, these were the original sources of this model, and so the other sources for other models should be structured similarly. Although in WebGL all them are shown as actual geometry. Couldn't you tell which data exactly are missing to reconstruct the model? Is the file.osgys usable at all as a guide to get the right offsets and counts for mesh chunks or it contains the wrong description of the models' inner structure? I tested several models but have the same problems with generating faces. So I suspect that this varint encoding in the bin. files prevents to get the full info about faces. But your tool should work for more stable formats, purposed for Direct X, especially for game models, so thank you for your work.
## Post #28
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-01-07T13:27:47+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

Ditta
Indeed, in a text file there is information about the types of data, offsets and the amount of data. I did not manage to build a model, but this does not mean that there is no data. Perhaps you need to get somehow different.
Yes, you can get it from the games of the model. If the structure is complicated, you can use scripts.
## Post #29
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-03-22T15:55:47+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

Soon a new version of the program will be released. I added a very useful hex-viewer widget. For a full viewer, it is not very good, but there is a pattern coloring on the data from the forms. The widget will appear in two versions. =)
## Post #30
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-03-25T19:48:01+00:00
- Post Title: Re: 3D Model Researcher - mesh viewer

The program is updated! You can download the new version on the website.

Update v2.4

- The program does not freeze when resizing on other tabs
- Added a Hex-Viewer.

The big drawback of the program was the lack of a built-in hex-viewer. Now he has appeared! =) Moreover, it has the highlighting of the model data: vertices (red color), faces (green), texture coordinates (yellow). When changing the parameters of forms, you can immediately see what data will be read. Probably, it will be very useful for beginners.
## Post #31
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-04-07T10:35:25+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

The program has been updated.

Update v2.4.2

- Finalized Hex-viewer.
- In the "3D View" tab, a button is added to return the camera to its initial position (useful if you centered on the object with incorrect coordinates).
- There was a version for Windows XP

Pro version:
- Added a Hex-Viewer.
- Added data inspector to Hex-viewer
- Fixed minor bugs

Video:
[https://youtu.be/Gzh1i8Dp9Q4](https://youtu.be/Gzh1i8Dp9Q4)
## Post #32
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-04-16T21:57:59+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

A very nice tool, actually the best if coupled with TextureFinder !

I bought the Pro version, and started to learn using python with this tool !

( Already reversed a game with it (project gotham racing 2))
## Post #33
- Username: JohnCS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 19, 2018 8:01 am
- Post datetime: 2018-08-13T00:14:54+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi - your program has been a great help to me in extracting models from 'Inquistor - Martyr'

Could you provide a suggestion on how to read strings from the file using the BufferFile API.  Every approach I try converts it to a numeric array or gives an error.  My closest attempt is:

def getstring(fp,count):
    new=""
    strname=""

    for x in range(count):
        strname="{0}".format(fp.reads("s"))
        new+=strname
        fp.read(1)
    return new

but it gives the following output for short word format strings with EBCDIC encoding:

Black_Legion_Marine_v17b_lamb_hitbox:

b'B',)(b'l',)(b'a',)(b'c',)(b'k',)(b'_',)(b'L',)(b'e',)(b'g',)(b'i',)(b'o',)(b'n',)(b'_',)(b'M',)(b'a',)(b'r',)(b'i',)(b'n',)(b'e',)(b'_',)(b'v',)(b'1',)(b'7',)(b'_',)(b'l',)(b'a',)(b'm',)(b'b',)(b'_',)(b'h',)(b'i',)(b't',)(b'b',)(b'o',)(b'x',)

any tips?  I'm a novice at Python

thanks!
## Post #34
- Username: JohnCS
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-13T01:53:53+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

bs.readBytes(4).decode("ASCII").rstrip("\0")
## Post #35
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-08-13T21:22:20+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

import mrp
f = mrp.get_bfile()
b = f.read(count).decode("utf-8")

Something like this)
## Post #36
- Username: JohnCS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 19, 2018 8:01 am
- Post datetime: 2018-08-14T03:34:29+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

perfect - worked a charm.  Thanks!
## Post #37
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-15T17:10:56+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi, I'm now working on Planet Hot Wheels files (.mxs) with the Model Researcher, but only half of they are decoded well, and they've got this first string: "*3DSMAX_ENGINE1EXPORTB2	200"

The other half, that I can't understand why, show like this, with the same method:

[https://www.dropbox.com/s/3r5iwqftk3f6c ... 6.jpg?dl=0](https://www.dropbox.com/s/3r5iwqftk3f6cbn/Immagine6.jpg?dl=0)

and they have got, as first string, this: "*3DSMAX_ENGINE1EXPORTFP	200".

Lazov, can you help me, please  

P.s. I leave the 63corvette.mxs in attached:
[https://www.dropbox.com/s/3gcb6psczawhz ... e.MXS?dl=0](https://www.dropbox.com/s/3gcb6psczawhzle/63corvette.MXS?dl=0)
## Post #38
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-08-16T08:39:13+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Fiammanera628, so what is the problem?
## Post #39
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-16T08:46:04+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> Fiammanera628, so what is the problem?

The problem is when with the files .mxs with "*3DSMAX_ENGINE1EXPORTB2	200" show perfect on MR, despite the files .mxs with "*3DSMAX_ENGINE1EXPORTFP	200" (Like the 63corvette.mxs) show like a tangled cube, and the parametres are more or less the same.



All files must be cars, not half of this cubes.
## Post #40
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-08-17T20:39:56+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

When the vertices are in Short, they are divided by 256. But in fact they can be transformed differently.
## Post #41
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-17T20:49:06+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> When the vertices are in Short, they are divided by 256. But in fact they can be transformed differently.

For example?
(sorry, but I never studied computer programming, so can you explain simply?)
## Post #42
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-09-20T13:11:07+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Update v2.5

- Added the ability to make a screenshot and a screenshot with information
- Fixed minor bugs

I will try to add the normal vectors in the next update.

Fiammanera628, Short is an integer data type that takes 2 bytes. The program divides vertices in this type by 256.
[screen_info.png](https://xentaxbackup.github.io/file/14888_screen_info.png)
## Post #43
- Username: alex0809
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 21, 2018 11:38 pm
- Post datetime: 2018-09-21T15:45:35+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

A simple question for you guys - My boss gave me 30 days (not working days) to learn Python to transfer to the Data Science team. What is the best approach to learn as much as possible?
## Post #44
- Username: Honkasumi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 09, 2018 3:36 pm
- Post datetime: 2018-12-09T07:47:10+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi, can i extract models from apps from programs like nox or BlueStacks programs.
## Post #45
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-12-10T04:51:21+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Honkasumi
>
> Hi, can i extract models from apps from programs like nox or BlueStacks programs.
The ability to export depends on the format structure.
## Post #46
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2018-12-27T20:16:21+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

where am i wrong ?? Why it cant be
[https://drive.google.com/drive/u/0/fold ... C?ogsrc=32](https://drive.google.com/drive/u/0/folders/1a4sYOl7tydJHnQAG2up1UIpU8X8dUNxC?ogsrc=32)
[1.png](https://xentaxbackup.github.io/file/15390_1.png)
## Post #47
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-14T06:58:40+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

There is a bug in Xp version of Model Researcher v2.4.2. My model is big endian and vertices is half-float and faces is short. Trying to toggle endian there is no effect and values doesn't change. Setting type to float endian change works properly. I don't know how it works in latest version v2.5 because win7/win8/win10 version of Model Researher doest't work with Wine on Mac.

Edit. Endian change works with faces but it doesn't work with half-float vertices.
## Post #48
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-14T12:03:11+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Beedy
>
> There is a bug in Xp version of Model Researcher v2.4.2. My model is big endian and vertices is half-float and faces is short. Trying to toggle endian there is no effect and values doesn't change. Setting type to float endian change works properly. I don't know how it works in latest version v2.5 because win7/win8/win10 version of Model Researher doest't work with Wine on Mac.

Edit. Endian change works with faces but it doesn't work with half-float vertices.
Thank you! Bug fixed. Other byte reading errors were also fixed.
The update will appear in the coming days on the site.
## Post #49
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-15T10:29:29+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Would it be possible to get the skeleton of a character out of the mesh by hand or with the tool in the future?
if there is a way to do it by hand with time and a hex editor? I am more than willing to do it right now.

/GHFear
## Post #50
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-15T19:45:25+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

GHFear, I am going to add animation support in the future. But everything is much more complicated there, a lot of data.

I updated the version for Windows XP.
## Post #51
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-16T11:53:29+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

hello,

I was wondering if there was someone that knows about using 3d model researcher and extracts games model. I'm not really familiar with hex code, and there are some models that I would like to obtain (ps2 game models). I'm prepared to pay for your time and would very much appreciate your help.

Thanks
## Post #52
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-16T17:21:44+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

adroduke
It is probably better to write about this in this topic, attaching the model file:
[viewforum.php?f=16](http://forum.xentax.com/viewforum.php?f=16)
## Post #53
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-17T14:22:16+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> I updated the version for Windows XP.
Thank you! My last question is about uv’s. I can’t get right values with type Short_sign in MR Xp version. Is short_sign same type than WordUV or Short All in Hex2Obj which I can get right values for Uvs?

My model information
Big Endian
Vertices:
Offset: 0x800 
Type: Half-float
Count: 692
Padding 26

Faces: 0x5e80
Count 1536
Type: Short
Format: Tri Strip FF

UVs
Offset: should be 0x810 (Hex2Obj: FVFsize 32, UV pos 16)
Count: 692
Padding: 28

First uv values should be vt 0.753769 0.968872 (Hex2Obj) but I got vt -0,4992 -0,0623 in MR.

I tried to set Vertices type short_sign in MR and ShortALL in Hex2Obj and got same values for vertices. So I think WordUV and Short_sign is same.

What is wrong with uvs?
Model in attachmet if you want to take a look.
[hand_0.rx2.zip](https://xentaxbackup.github.io/file/15500_hand_0.rx2.zip)
## Post #54
- Username: adroduke
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 16, 2019 7:46 pm
- Post datetime: 2019-01-18T13:09:13+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> adroduke
It is probably better to write about this in this topic, attaching the model file:
viewforum.php?f=16
Cheers
## Post #55
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-18T15:45:15+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Beedy
>
> Lazov wrote:I updated the version for Windows XP.
Thank you! My last question is about uv’s. I can’t get right values with type Short_sign in MR Xp version. Is short_sign same type than WordUV or Short All in Hex2Obj which I can get right values for Uvs?

My model information
Big Endian
Vertices:
Offset: 0x800 
Type: Half-float
Count: 692
Padding 26

Faces: 0x5e80
Count 1536
Type: Short
Format: Tri Strip FF

UVs
Offset: should be 0x810 (Hex2Obj: FVFsize 32, UV pos 16)
Count: 692
Padding: 28

First uv values should be vt 0.753769 0.968872 (Hex2Obj) but I got vt -0,4992 -0,0623 in MR.

I tried to set Vertices type short_sign in MR and ShortALL in Hex2Obj and got same values for vertices. So I think WordUV and Short_sign is same.

What is wrong with uvs?
Model in attachmet if you want to take a look.

They do not show up correctly on Windows 10 either. I tried for the last 2 hours to get the UVs to show up correctly on that one and it doesn't seem like the correct format for those UVs is supported yet.
## Post #56
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-18T20:50:16+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Beedy
>
> Lazov wrote:I updated the version for Windows XP.
Thank you! My last question is about uv’s. I can’t get right values with type Short_sign in MR Xp version. Is short_sign same type than WordUV or Short All in Hex2Obj which I can get right values for Uvs?

First uv values should be vt 0.753769 0.968872 (Hex2Obj) but I got vt -0,4992 -0,0623 in MR.

I tried to set Vertices type short_sign in MR and ShortALL in Hex2Obj and got same values for vertices. So I think WordUV and Short_sign is same.
Update

Apparently, unsigned Short is used in Hex2Obj when reading textural coordinates. I added a new type to the block UVs - Short. Thanks for finding bugs and flaws!
New versions are available on the site. The update for the Pro version will be released later.
## Post #57
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-18T21:51:44+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> Beedy wrote:Lazov wrote:I updated the version for Windows XP.
Thank you! My last question is about uv’s. I can’t get right values with type Short_sign in MR Xp version. Is short_sign same type than WordUV or Short All in Hex2Obj which I can get right values for Uvs?

First uv values should be vt 0.753769 0.968872 (Hex2Obj) but I got vt -0,4992 -0,0623 in MR.

I tried to set Vertices type short_sign in MR and ShortALL in Hex2Obj and got same values for vertices. So I think WordUV and Short_sign is same.

Update

Apparently, unsigned Short is used in Hex2Obj when reading textural coordinates. I added a new type to the block UVs - Short. Thanks for finding bugs and flaws!
New versions are available on the site. The update for the Pro version will be released later.

Thank you Lazov!  This is just what I need for Skate 1, 2 and 3 world/ level models. They use that type.
## Post #58
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-19T06:11:00+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> 

Update

Apparently, unsigned Short is used in Hex2Obj when reading textural coordinates. I added a new type to the block UVs - Short. Thanks for finding bugs and flaws!
New versions are available on the site. The update for the Pro version will be released later.
 Thanks for the quick response. This is a great tool.
## Post #59
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-26T14:15:47+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hey Lazov, much thanks for this great tool, made sure to grab the Pro version to support this!

I'm experiencing seemingly random crashes however, and it's always when i'm prompted to load something like a file or a texture. Sometimes it's fine for a while, and sometimes it crashes within minutes. It can even happen when trying to save something.

If it helps, i'm using Windows 10 Home 64-bit.
## Post #60
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-26T19:18:44+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Nega, maybe the RAM is not enough? Which version crashes? Pro only?
## Post #61
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-27T12:05:34+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> Nega, maybe the RAM is not enough? Which version crashes? Pro only?

I have 16GB RAM, so I doubt it could be that.

The version I have is 3.1.1 (07-04-2018). And i'll let you know if the normal version does this too.
## Post #62
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-27T12:44:29+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Nega, It is difficult to say what is the reason. Need more information about your actions that lead to this.
## Post #63
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-27T12:59:49+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> Nega, It is difficult to say what is the reason. Need more information about your actions that lead to this.

For example, opening this window multiple times can crash the program.



The window will still open, but no files will show up and then it will close entirely.

Maybe it's a problem with my Windows? I was thinking of trying Windows 7 again and using Model Researcher on that.
## Post #64
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-27T13:21:00+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Nega, please check the free version.
## Post #65
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-01-27T13:46:13+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

I can confirm it also happens on the free version.
## Post #66
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-01-28T04:24:30+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Nega
I updated the program. Added logging.
Download the latest version from the site and run the program using the "-log" option:
C:\%path_to_MR%\ModelResearcher.exe -log

After launch, the out.log file will appear in the program folder. After the program crashes, check the log.
## Post #67
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-02-11T17:52:50+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

I found one more option that MR doesn't have but Hex2O has. There is no option "noStr FFFF" for faces, only "Triangles", "Tri Strip FF" and "Tri Strip". I Think it's not necessary for most of models, but I have the only one which that option does matter.
## Post #68
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-02-11T21:23:39+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Beedy
Can you give an example of a model with a template for Hex2Obj?
## Post #69
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-02-12T07:25:45+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov
>
> 
Can you give an example of a model with a template for Hex2Obj?
Here is H2O sample and template files. In MR faces doesn't look correct.
[sample.zip](https://xentaxbackup.github.io/file/15712_sample.zip)
## Post #70
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-02-12T08:40:18+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

I did not find the difference.
## Post #71
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-02-12T09:55:21+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Thanks! I tried with option Tri Strip or Try Strip FF and that's why faces didn't displayed correctly. I tried Triangles with count 2754 and thats why I got error but when divide faces count by three (918) faces seems to be correct.
## Post #72
- Username: rudi246
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 11, 2019 5:29 pm
- Post datetime: 2019-06-11T14:05:48+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

I'm trying to extract the levels from a PS1 skateboarding game called Grind Session. I found the models inside the level files but they always have missing triangles. I have attatched a rar file that contains the level files for one of the levels as well as some of my templates for different models within the TRACK.DAT file.

[https://zenhax.com/download/file.php?id ... 84443f7d43](https://zenhax.com/download/file.php?id=6932&sid=4ff7cb44805bc46fe7dd1d84443f7d43)
## Post #73
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-06-24T12:15:08+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from rudi246 ↑Tue Jun 11, 2019 10:05 pm at Tue Jun 11, 2019 10:05 pm
>
> 
I'm trying to extract the levels from a PS1 skateboarding game called Grind Session. I found the models inside the level files but they always have missing triangles. I have attatched a rar file that contains the level files for one of the levels as well as some of my templates for different models within the TRACK.DAT file.

https://zenhax.com/download/file.php?id ... 84443f7d43

I second this. 
Also looking to get the models extracted from this game and would like to request adding whatever face-format is required to make the models work properly.
## Post #74
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-07-25T20:48:43+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi Lazov,

I am trying to use your API using visual studio 2019, i tried import mrp and refrenced to file location but it keeps saying moudle dosent exist.
i dont know if this is do to it being .pyd file?? or something else.

any help would be appriciated, Thanks
## Post #75
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-07-26T11:35:54+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

jayn23
Why do you need it? It is hardly possible.

rudi246
I looked at the files with the models. Unfortunately, I did not understand how to extract the model.
## Post #76
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-07-26T14:17:09+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi,

Mostly for debugging my code and i am just used to scripting in visual studio   
And since i am new to python i checked online and it said that you should be able to import .pyd files.

Great tool by the way!
## Post #77
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-07-30T21:29:48+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi Lazov, 

I'm having problems getting the faces of a model. 

There's 8 submeshes but only a small part of the model renders and even that doesn't look right

Could you tell me what i'm doing wrong? i'm using 3D Model Researcher Pro

Thanks!!

P.S i'm loving the tool by the way, keep up the good work



1.png (130.04 KiB) Viewed 200 times
## Post #78
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-07-31T02:36:51+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

EDXZ23
It is necessary to watch the model itself, a screenshot does not give any information. Some models can not be opened using standard functionality. But with the help of scripts you can extract any models.
## Post #79
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-07-31T11:32:18+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Wed Jul 31, 2019 10:36 am at Wed Jul 31, 2019 10:36 am
>
> 
EDXZ23
It is necessary to watch the model itself, a screenshot does not give any information. Some models can not be opened using standard functionality. But with the help of scripts you can extract any models.

Hi again Lazov, thanks for the reply!!

I've tried to use a script from a youtube video and the same thing happens. but this time i get an error message "MRError: Invalid data - cannot reshape array of size 1000 into shape (3)"

the hex values for a face is 00 00 01 00 02 and i use the first instance of these as my face offset



error.png (92.44 KiB) Viewed 182 times
## Post #80
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-07-31T16:04:33+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

EDXZ23
The readByte function returns a single value, and a tuple is needed.
Try this:
fc = (f.readByte (), f.readByte (), f.readByte ())
faces.append (fc)

But it will not help to extract the model. Need to somehow convert the data.
## Post #81
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-07-31T18:51:09+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Thu Aug 01, 2019 12:04 am at Thu Aug 01, 2019 12:04 am
>
> 
EDXZ23
The readByte function returns a single value, and a tuple is needed.
Try this:
fc = (f.readByte (), f.readByte (), f.readByte ())
faces.append (fc)

But it will not help to extract the model. Need to somehow convert the data.

Hi Lazov thanks again for the help!!

your code worked the error message is no longer occurring! but you were right about it not helping extract the model.
You said i have to convert the data. any ideas how or to what? the file is currently in .dat extension

P.S i'm really new to all of this, sorry if all my questions are basic and annoying
## Post #82
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-05T02:27:16+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Thu Aug 01, 2019 12:04 am at Thu Aug 01, 2019 12:04 am
>
> 
EDXZ23
The readByte function returns a single value, and a tuple is needed.
Try this:
fc = (f.readByte (), f.readByte (), f.readByte ())
faces.append (fc)

But it will not help to extract the model. Need to somehow convert the data.

could you elaborate on convert data?
## Post #83
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-08-05T13:16:08+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

EDXZ23
Unfortunately, there is nothing I can help. I almost do not extract models. But there are people who know this subject very well. Try to ask a question on the forum:
[viewforum.php?f=16](https://forum.xentax.com/viewforum.php?f=16)
## Post #84
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-08-07T10:42:14+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Mon Aug 05, 2019 9:16 pm at Mon Aug 05, 2019 9:16 pm
>
> 
EDXZ23
Unfortunately, there is nothing I can help. I almost do not extract models. But there are people who know this subject very well. Try to ask a question on the forum:
viewforum.php?f=16

Hello Lazov,
What do you do in the backend to calculate the UVs from Signed and Unsigned Short?
## Post #85
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-07T12:19:05+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from GHFear ↑Wed Aug 07, 2019 6:42 pm at Wed Aug 07, 2019 6:42 pm
>
> 
Lazov wrote: ↑Mon Aug 05, 2019 9:16 pm
EDXZ23
Unfortunately, there is nothing I can help. I almost do not extract models. But there are people who know this subject very well. Try to ask a question on the forum:
viewforum.php?f=16


Hello Lazov,
What do you do in the backend to calculate the UVs from Signed and Unsigned Short?

Hi GHFear,

Your skate extraction videos is what I've been using as a guide.

I've been told that the faces in my file can't be read as a single array and that there may be many start and stop offsets 

I've successfully found the first one, but how do I find the others? the file has a similar structure to .rax files in SWBF3 by Free Radical



progress.png (109.31 KiB) Viewed 126 times
## Post #86
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-08-09T07:17:51+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from EDXZ23 ↑Wed Aug 07, 2019 8:19 pm at Wed Aug 07, 2019 8:19 pm
>
> 
GHFear wrote: ↑Wed Aug 07, 2019 6:42 pm
Lazov wrote: ↑Mon Aug 05, 2019 9:16 pm
EDXZ23
Unfortunately, there is nothing I can help. I almost do not extract models. But there are people who know this subject very well. Try to ask a question on the forum:
viewforum.php?f=16


Hello Lazov,
What do you do in the backend to calculate the UVs from Signed and Unsigned Short?


Hi GHFear,

Your skate extraction videos is what I've been using as a guide.

I've been told that the faces in my file can't be read as a single array and that there may be many start and stop offsets 

I've successfully found the first one, but how do I find the others? the file has a similar structure to .rax files in SWBF3 by Free Radical
progress.png

Hello
You would have to upload the file so I can look at it.

/GHFear
## Post #87
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-09T09:37:12+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from GHFear ↑Fri Aug 09, 2019 3:17 pm at Fri Aug 09, 2019 3:17 pm
>
> 
EDXZ23 wrote: ↑Wed Aug 07, 2019 8:19 pm
GHFear wrote: ↑Wed Aug 07, 2019 6:42 pm


Hello Lazov,
What do you do in the backend to calculate the UVs from Signed and Unsigned Short?


Hi GHFear,

Your skate extraction videos is what I've been using as a guide.

I've been told that the faces in my file can't be read as a single array and that there may be many start and stop offsets 

I've successfully found the first one, but how do I find the others? the file has a similar structure to .rax files in SWBF3 by Free Radical
progress.png


Hello
You would have to upload the file so I can look at it.

/GHFear

heres the file dude!


 6118.zip
(194.61 KiB) Downloaded 20 times



the file was extracted to .dat but i know now that its a .rax file
## Post #88
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-08-09T12:13:45+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from EDXZ23 ↑Fri Aug 09, 2019 5:37 pm at Fri Aug 09, 2019 5:37 pm
>
> 
GHFear wrote: ↑Fri Aug 09, 2019 3:17 pm
EDXZ23 wrote: ↑Wed Aug 07, 2019 8:19 pm


Hi GHFear,

Your skate extraction videos is what I've been using as a guide.

I've been told that the faces in my file can't be read as a single array and that there may be many start and stop offsets 

I've successfully found the first one, but how do I find the others? the file has a similar structure to .rax files in SWBF3 by Free Radical
progress.png


Hello
You would have to upload the file so I can look at it.

/GHFear


heres the file dude!
6118.zip

the file was extracted to .dat but i know now that its a .rax file

I can not for the life of me figure this format out.
sorry.
## Post #89
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-08-09T20:00:17+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

GHFear
All coordinates are divided by 0xffff.

EDXZ23
Try using meshes. If it turned out to build part of the model, this is already good.
By the way, I can not open the archive with your model.
## Post #90
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-08-10T02:41:33+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Sat Aug 10, 2019 4:00 am at Sat Aug 10, 2019 4:00 am
>
> 
GHFear
All coordinates are divided by 0xffff.

EDXZ23
Try using meshes. If it turned out to build part of the model, this is already good.
By the way, I can not open the archive with your model.

Hi Lazov.

Thanks for the answer.

The UV coordinates are in hexadecimal:  0x107 and 0x20A8 Big Endian.
The value shown in the .OBJ file is 0.0083 and 0.2568.

Dividing 0x107 (263) by 0xffff (65535) = 0,00401312275883115892271305409323
Dividing 0x20A8 (8360) by 0xffff (65535) = 0,12756542305638208590829327840085‬

So there must be something else being done to the coordinates to get 0.0083 and 0.2568.
Or maybe I am completely missing something.


Edit (Solution): If anyone has the same problem converting short / 16bit Int UVs to floats,
my solution is this:

If you're using python and rounding,

rounded UVs Multiplier:

short U / 31869
short V / 32553

If you don't want to round and just accept some tiny variance:

raw UVs Multiplier:

short U / 31868
short V / 32555

/GHFear
## Post #91
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-10T21:44:43+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from GHFear ↑Fri Aug 09, 2019 8:13 pm at Fri Aug 09, 2019 8:13 pm
>
> 
EDXZ23 wrote: ↑Fri Aug 09, 2019 5:37 pm
GHFear wrote: ↑Fri Aug 09, 2019 3:17 pm


Hello
You would have to upload the file so I can look at it.

/GHFear


heres the file dude!
6118.zip

the file was extracted to .dat but i know now that its a .rax file


I can not for the life of me figure this format out.
sorry.

that's cool dude i appreciate the response
## Post #92
- Username: Jamal al dambali
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 17, 2017 12:00 am
- Post datetime: 2019-08-17T12:59:26+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi Lazov! Please tell me how to find uv.



screenshots.jpg (165.7 KiB) Viewed 366 times


file link: [https://yadi.sk/d/UTleab58Y6cF6w](https://yadi.sk/d/UTleab58Y6cF6w)
## Post #93
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-19T11:20:51+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Jamal al dambali ↑Sat Aug 17, 2019 8:59 pm at Sat Aug 17, 2019 8:59 pm
>
> 
Hi Lazov! Please tell me how to find uv.
screenshots.jpg
file link: https://yadi.sk/d/UTleab58Y6cF6w

You need to find the correct start address for the UV’s which vary for different files  what file type are you working with?
## Post #94
- Username: Jamal al dambali
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 17, 2017 12:00 am
- Post datetime: 2019-08-20T13:55:32+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from EDXZ23 ↑Mon Aug 19, 2019 7:20 pm at Mon Aug 19, 2019 7:20 pm
>
> 
You need to find the correct start address for the UV’s which vary for different files  what file type are you working with?

If I knew, I would have done it myself. But I dont know 
And I left a link to the file.
## Post #95
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-22T05:15:47+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Jamal al dambali ↑Tue Aug 20, 2019 9:55 pm at Tue Aug 20, 2019 9:55 pm
>
> 
EDXZ23 wrote: ↑Mon Aug 19, 2019 7:20 pm
You need to find the correct start address for the UV’s which vary for different files  what file type are you working with?


If I knew, I would have done it myself. But I dont know 
And I left a link to the file.

I'm super busy at the moment with my own project, but if I have time I'll take a look at the file and see if can help you  !

In the mean time try doing some research about the game and its file types. 

You can also use trial and error to find the UV's by pasting the starting offset in DEC and increasing it by 1, then clicking the "View UV's" button until the UV's look correct. However, it may or may not work depending on the file type as you may need to find the padding. Hence why I suggest extensive research into game and the file type
## Post #96
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-10-07T12:28:09+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

The program has been updated.

Update v2.6

- Added support for normal vectors!
- Template format is now compatible with the Pro version.
- The algorithm for calculating normal vectors has been changed. Now the model looks better.
- Added TStrip, TStripFF formats for texture coordinate indices and normal indices. Perhaps this is never used in models.
## Post #97
- Username: Aterbust
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 31, 2018 7:06 am
- Post datetime: 2019-10-28T10:28:13+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from rudi246 ↑Tue Jun 11, 2019 10:05 pm at Tue Jun 11, 2019 10:05 pm
>
> 
I'm trying to extract the levels from a PS1 skateboarding game called Grind Session. I found the models inside the level files but they always have missing triangles. I have attatched a rar file that contains the level files for one of the levels as well as some of my templates for different models within the TRACK.DAT file.

https://zenhax.com/download/file.php?id ... 84443f7d43

Hello.
I think that version 2.6 of 3D Model Researcher does not work well.
I loaded the file 'TRACK.DAT' and I got an error message. "Mismatch of faces and vertices!"
In the text section, when I check info, all the table for the faces disappeared.
## Post #98
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-10-28T15:30:46+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Thanks, Aterbust!
I updated the program.
## Post #99
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-11-01T16:56:57+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Big Update v2.7

- Added support Quads!
- The output of data in text form has been changed: texture coordinate indices and normal indices are now displayed in separate blocks with the literals "fvt" and "fvn", 1 is not added to the indices. The old output can be enabled in the menu "View" -> "Print as OBJ";
- Added highlighting of texture coordinate indices and normal indices in the hex-viewer;

- New template format!
Templates have become more compact. Now they have the following format:

```
v [offset] [count] [padding] [padding inter] [type] [format] // vertices
f [offset] [count] [padding] [padding inter] [type] [format] // faces
vt [offset] [count] [padding] [padding inter] [type] [format] // uvs
fvt [offset] [count] [padding] [padding inter] [type] [format] // uvs indices
vn [offset] [count] [padding] [padding inter] [type] [format] // normals
fvn [offset] [count] [padding] [padding inter] [type] [format] // normals indices
inv [x] [y] [z] // invert (0 or 1)
bo [byte order] // byte order (< - Little Endian, > - Big Endian)
```


It is not necessary that the template contains data of all forms or all parameters of one form. Omitted parameters and forms will be replaced with default values. The sample templates below are correct:
v 0x997 3214 0 0 Float XZY
f 100 826 64 0 Integer Triangles
v 15 3015
f 0x48a 826 64 0 Integer
bo >
v 0x5487 720 0 0 Float XZY
inv 0 0 1
However, support for old templates will remain.

- Added function to copy template to clipboard ("Tools" -> "Copy Template") and
function for loading a template using the form ("Tools" -> "Paste Template");
- Polygons on the texture in the Texture tab are now drawn without filling;
- Added "Copy-Paste" menu when clicking on a text field in the "Text" tab;
- Returned support for templates of previous versions of the program;
- Small bugs fixed.

Pro version will be updated later.
## Post #100
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-11-02T13:51:02+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Thank you for the work you're doing, Lazov 
I really appreciate it. I have had much good use of this tool.
## Post #101
- Username: MadTucker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 12, 2020 11:58 pm
- Post datetime: 2020-04-12T16:25:16+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi there Lazov. I purchased the Pro ver. of your software a while ago and it seems like I still haven't recieved an e-mail with activation-key. I didn't write you earlier, because I really didn't need the pro features very urgently, just wanted to fool around with it a little and try them out. I don't know if you are still active right now, but if you are, then it would be neat if you can send me the key, if you are not active anymore, then I don't really mind also, because I still had good use of the free version of the tool, so then I'd just see it as a 'lil donation for your efforts
## Post #102
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-04-12T20:53:40+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

MadTucker
Write to me in the PM. The message may be in the spam folder.
## Post #103
- Username: Segal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 03, 2020 6:25 am
- Post datetime: 2020-05-02T22:30:13+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi Mr. Lazov, thanks a lot for 3D Model Researcher, it's a great software.
I had extracted some models and I save them to obj, everything working good.
But I want to edit those models, and convert them from obj to hex or binary (reversing 3D Model Researcher obj-->hex), and replacing the game models by the new models, is this possible?
For this function I had made some codes woking only for vertices in short_signed, but they doesn't work with float or UVs.
This image explain vertices short_signed conversion:
Edited:
I found some websites can do the calculation for vetices from obj to float or short_signed, I do this operation manually, and it's so tiring, and it gives not exact values in some cases.
Here is the websites links:
obj to hex [[Float]]: [https://gregstoll.com/~gregstoll/floattohex/](https://gregstoll.com/~gregstoll/floattohex/)  "this site do the conversion called "IEEE 754" you can search it in google, check Swap endianess for little endian".
obj to hex [[Short_signed]]: [https://www.binaryhexconverter.com/deci ... -converter](https://www.binaryhexconverter.com/decimal-to-hex-converter)  "this site do only the conversion form decimal to hexadecimal, and this is the short_signed convertion"
The problem now is the UVs, I had them in short_signed in game models, they vary between 0 and 1, so when I put 0.710583 for example, it's always converted to 0 in the short_signed website, I try a lot of attempts but always 0.
Please can you give a website or a calculator or a software or you can make a script or a partition in 3D Model Resercher for converting the obj to hex in all forms (short_signed or float and UVs) to hex, and upload it in new vesrion v2.8 , this will creates a big buzz in 3D modeling.
This is my email: [johnsegal613@gmail.com](mailto:johnsegal613@gmail.com)
Thanks in advance  .
## Post #104
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-05-07T22:42:07+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Segal, learn the basics of Python and create this converter.

```
import struct
struct.pack("f",0.154).hex()

```

The fact is that all models have a different format, and it is impossible to create a converter for all formats.
## Post #105
- Username: Segal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 03, 2020 6:25 am
- Post datetime: 2020-05-07T23:56:58+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Thanks Mr. Lazov recently I found a method that can convert the models to float in vertices, normals and UVs.
Please can you tell me how can I convert this vertices, normals and UVs from float to short_signed, or another models format that convert obj vertices, normals and UVs to short_signed, or just how to convert 4 bytes of hex to 2 bytes to make it short?
## Post #106
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-05-08T16:31:00+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

To convert shor_signed to float, the program seems to divide the number by 256 or 0xffff.
## Post #107
- Username: Segal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 03, 2020 6:25 am
- Post datetime: 2020-05-08T23:55:23+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Please tell me how to do this calculation, this is an example:

Float ------> Short_signed

Vertices in float:
X = 34 80 45 C2 ----short_signed----> xx xx 
Y = C1 F9 65 42 ----short_signed----> xx xx
Z = 94 F6 76 41 ----short_signed----> xx xx

UVs in float:
X = AD 69 0E 3F ----short_signed----> xx xx
Y = 5D FE 63 3F ----short_signed----> xx xx

Normals in float:
X = 66 96 66 BF ----short_signed----> xx xx
Y = 56 66 DE 3E ----short_signed----> xx xx
Z = 00 00 80 3F ----short_signed----> xx xx

Recently, I found a method called "Narrowing Primitive Conversion", it can convert the float to short_signed, but I don't know how to calculate it?
[https://docs.oracle.com/javase/specs/jl ... #jls-5.1.3](https://docs.oracle.com/javase/specs/jls/se7/html/jls-5.html#jls-5.1.3)

Please if you know a model format with short_signed in vertices, UVs and normals, and we can convert the model to it, I think is better than this calculation.
Thanks in advance  .
## Post #108
- Username: Segal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 03, 2020 6:25 am
- Post datetime: 2020-05-21T17:51:11+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi Mr. Lazov, thank you very much for your efforts, finally I found it!   it's a simple way to convert any model to float or short_signed in all vertices, normals and UVs coordinates, and reimport him to the game again.
## Post #109
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-05-21T18:00:48+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi,

Perhaps is possible do extract something from these old MDL files? Because I found some verticles, but idk how to do with the faces and UVs  

[https://www.dropbox.com/s/3jf2kgw3f8nu28t/A10.mdl?dl=0](https://www.dropbox.com/s/3jf2kgw3f8nu28t/A10.mdl?dl=0)
## Post #110
- Username: Segal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 03, 2020 6:25 am
- Post datetime: 2020-05-22T00:55:41+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Fiammanera628 ↑Fri May 22, 2020 2:00 am at Fri May 22, 2020 2:00 am
>
> 
Hi,

Perhaps is possible do extract something from these old MDL files? Because I found some verticles, but idk how to do with the faces and UVs  

https://www.dropbox.com/s/3jf2kgw3f8nu28t/A10.mdl?dl=0
Hi, Mr. Fiammanera628, I found on this file 55 models, I was extracted them to obj, also I saved all Model Resercher .tmr templates, for helping to extract other models.
Note before each vertices, normals and UVs, also the faces you will find a hex number convert it to decimal, and thats was the count.
You can find all files in this link:
[https://drive.google.com/open?id=1CM3Cl ... rJyGJMRJbm](https://drive.google.com/open?id=1CM3ClBJtqAiFPCQpJUwcqNrJyGJMRJbm)
## Post #111
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-05-22T11:32:34+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Segal ↑Fri May 22, 2020 8:55 am at Fri May 22, 2020 8:55 am
>
> 
Fiammanera628 wrote: ↑Fri May 22, 2020 2:00 am
Hi,

Perhaps is possible do extract something from these old MDL files? Because I found some verticles, but idk how to do with the faces and UVs  

https://www.dropbox.com/s/3jf2kgw3f8nu28t/A10.mdl?dl=0

Hi, Mr. Fiammanera628, I found on this file 55 models, I was extracted them to obj, also I saved all Model Resercher .tmr templates, for helping to extract other models.
Note before each vertices, normals and UVs, also the faces you will find a hex number convert it to decimal, and thats was the count.
You can find all files in this link:
https://drive.google.com/open?id=1CM3Cl ... rJyGJMRJbm

Thank you very much!

But is only a thing I don't understand: the UVs. How do you find the start address?  

Because I tried to open 3 models into another file, and only one has got (more or less) the correct UVs
## Post #112
- Username: Segal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 03, 2020 6:25 am
- Post datetime: 2020-05-23T01:06:33+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Fiammanera628 ↑Fri May 22, 2020 7:32 pm at Fri May 22, 2020 7:32 pm
>
> 
Segal wrote: ↑Fri May 22, 2020 8:55 am
Fiammanera628 wrote: ↑Fri May 22, 2020 2:00 am
Hi,

Perhaps is possible do extract something from these old MDL files? Because I found some verticles, but idk how to do with the faces and UVs  

https://www.dropbox.com/s/3jf2kgw3f8nu28t/A10.mdl?dl=0

Hi, Mr. Fiammanera628, I found on this file 55 models, I was extracted them to obj, also I saved all Model Resercher .tmr templates, for helping to extract other models.
Note before each vertices, normals and UVs, also the faces you will find a hex number convert it to decimal, and thats was the count.
You can find all files in this link:
https://drive.google.com/open?id=1CM3Cl ... rJyGJMRJbm


Thank you very much!

But is only a thing I don't understand: the UVs. How do you find the start address?  

Because I tried to open 3 models into another file, and only one has got (more or less) the correct UVs
If you knew the right vertices offsets and count, usually come after them the normals with float or short_signed and with the same vertices count, and after the normals comes the UVs also with float or short_signed and with the same vertices and normals count, like in the .tmr examples that I gave you. If you had a problem to find UVs, you can put a link for these models, I can help you to find them.
## Post #113
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-05-23T09:57:41+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> If you knew the right vertices offsets and count, usually come after them the normals with float or short_signed and with the same vertices count, and after the normals comes the UVs also with float or short_signed and with the same vertices and normals count, like in the .tmr examples that I gave you. If you had a problem to find UVs, you can put a link for these models, I can help you to find them.

Ok, I link to you also my .tmr, so you check what I mistake, because I don't understand what I am wrong 
the model (+ texture) and the template:
[https://www.dropbox.com/s/lf53gnssadc4qvj/B1B.zip?dl=0](https://www.dropbox.com/s/lf53gnssadc4qvj/B1B.zip?dl=0)
## Post #114
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-05-23T10:53:20+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Segal ↑Sat May 09, 2020 7:55 am at Sat May 09, 2020 7:55 am
>
> 
Please tell me how to do this calculation, this is an example:

Float ------> Short_signed

Vertices in float:
X = 34 80 45 C2 ----short_signed----> xx xx 
Y = C1 F9 65 42 ----short_signed----> xx xx
Z = 94 F6 76 41 ----short_signed----> xx xx

It depends on the program that uses this data format. Model Researcher divides by 256. It turns out that this formula should work:
float * 256 = short_s.
## Post #115
- Username: Segal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 03, 2020 6:25 am
- Post datetime: 2020-05-24T01:12:30+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Fiammanera628 ↑Sat May 23, 2020 5:57 pm at Sat May 23, 2020 5:57 pm
>
> 
If you knew the right vertices offsets and count, usually come after them the normals with float or short_signed and with the same vertices count, and after the normals comes the UVs also with float or short_signed and with the same vertices and normals count, like in the .tmr examples that I gave you. If you had a problem to find UVs, you can put a link for these models, I can help you to find them.

Ok, I link to you also my .tmr, so you check what I mistake, because I don't understand what I am wrong 
the model (+ texture) and the template:
https://www.dropbox.com/s/lf53gnssadc4qvj/B1B.zip?dl=0

In .tmr template that you gave me all vertices, normals and UVs is right, but Model Researcher shows unorganized UVs, why?
Because they are outside the image bounds, just save the obj and open it with any 3D software, for example I use Blender. And you will see the full UVs.
## Post #116
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-05-24T12:29:37+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Oooooh, that's why... Thank you once again Segal!
## Post #117
- Username: aquaamann333
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 15, 2020 12:57 pm
- Post datetime: 2020-06-18T01:58:42+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

If anyone knows how to extract models well, can you extract the models from Ben 10 Vilgax Attacks and Ben 10 Cosmic Destruction and send them to me? Specifically Chromastone, Alien X, Jetray, and Amphibian
## Post #118
- Username: donaldregal1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 27, 2020 1:57 pm
- Post datetime: 2020-06-27T05:59:57+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Ditta ↑Sat Dec 30, 2017 4:27 am at Sat Dec 30, 2017 4:27 am
>
> 
Please, tell how to run this program on Windows 7 x64? When I tried to run it, it required  api-ms-win-crt-runtime-l1-1-0.dll. I downloaded these Dlls for both Win32 and Win64 versions, copied them in system\win32 and system\WoW64 folders, but it doesn't help. Now the program shows the error message 0xc000007b and I cannot run it. What to do to fix that issue?
Hi ,

Surely I am here to help you.

Follow these steps.

Firstly check your windows whether it”s updated or not

If Windows is updated and everything looks fine, try re-installing the particular program that is reverting [https://dll.one/how-to-fix-api-ms-win-c ... ing-error/](https://dll.one/how-to-fix-api-ms-win-crt-runtime-l1-1-0-dll-is-missing-error/)
Repair installed Visual C++ 2015 Redistributable package[/b]

if you already have the Visual C++ 2015 Redistributable package installed on your computer and still getting the error, there’s a high chance that it can be fixed by repairing the program.

﻿﻿Install Microsoft Visual C++ Redistributable Update.

Register the DLL file:

Copy-paste the api-ms-win-crt-runtime-l1-1-0.dll file

﻿﻿﻿﻿Next, plug the drive on your computer and copy that file and head over to C:\Windows\System32\downlevel and paste it there, and that’s it.﻿﻿﻿﻿﻿

Hope your problem get solved by following these steps.

Donald Regal Toss
## Post #119
- Username: Beebster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 11, 2020 7:17 am
- Post datetime: 2020-08-24T04:30:04+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hello, I was wondering, is 3d model researcher expecting certain file formats for the textures?
I currently have a .tga file I am importing but seem to be having some issues. 
Figured I would ask, though am guessing it is an error on my side.
## Post #120
- Username: an90dy905909
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 30, 2018 3:02 am
- Post datetime: 2020-09-20T02:45:08+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hy there friends, i have a problem finding normals address for one model, so i was wondering if could someone help
with finding normals for the model, i found vertices and polygons, just need to find normals?

i would be very grateful for little help.
Thanks!

Here is the link with model file and tamplate file.

[https://drive.google.com/file/d/1csfUxh ... sp=sharing](https://drive.google.com/file/d/1csfUxhhFd7ScXmqPpsaTeXXGoJA8vjTO/view?usp=sharing)
## Post #121
- Username: AMDFreak2006
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 18, 2020 1:26 am
- Post datetime: 2020-10-04T18:18:46+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hello Lazov,

at first thanks for your great program. It allowed me to analyze the 3D format of an old game.
I was able to correctly get vertices, faces, normals as well as uv-maps within your program.

Sadly I have some small problem left:

When the FLIP Button is switched ON (standard setting) in 3D Model Researcher, I get a wrong placing of the UV map within the texture picture file.
The UV-map is shown vertically flipped around the center of the texture picture.

FLIP Button switched ON (standard setting):


This of course results in a wrong rendering too:


By switching the FLIP button OFF, 3D Model Researcher correctly flips the UV and shows the correct location in the texture picture:

FLIP Button switched OFF:


Of course the rendering is then also correct:


When I now save the file as OBJ and open it in any other 3D model editor, for example Blender or even a simple viewer as Microsofts Windows 10 built-in 3D-Viewer, the model is textured as if the Button FLIP has never been switched to OFF.

Looking at the UV-Map in Blender, it shows that it is located as if the FLIP button has been set to ON.

Blender:


Is this a bug in 3D Model Researcher? It neither seems to save the flip button state within the OBJ file nor does it change any of the UV map coordinates, etc.

How can I get a correctly textured OBJ model export?

Thanks and best regards
## Post #122
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-10-05T21:48:30+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

AMDFreak2006
Yes, the program does not take into account the position of the texture when saving the model. I will try to fix it in the new version.
Thanks for reporting the issue.
## Post #123
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2020-10-25T06:29:13+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Update - Pro version
- Added all features from update v2.7
- Unpacking Zlib data [Video](https://youtu.be/-syZDMtmkCo). Zlib is often used to compress models. Usually the beginning of such data is byte 0x78.
## Post #124
- Username: AMDFreak2006
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 18, 2020 1:26 am
- Post datetime: 2020-11-25T15:46:41+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Tue Oct 06, 2020 5:48 am at Tue Oct 06, 2020 5:48 am
>
> 
AMDFreak2006
Yes, the program does not take into account the position of the texture when saving the model. I will try to fix it in the new version.
Thanks for reporting the issue.

Hi Lazov,

is there any chance for an update or a new version this year? 
Do you need any support, for example some files to test if it's working correctly? I'll be happy to help.

Best Regards
## Post #125
- Username: AngleLeX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 08, 2020 11:04 am
- Post datetime: 2021-02-05T19:18:02+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hello! Here is a model that is very strange. I can't open it. I don't know if I can open it in Python.
## Post #126
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2021-02-17T03:12:27+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Sun Oct 25, 2020 2:29 pm at Sun Oct 25, 2020 2:29 pm
>
> 
Update - Pro version
- Added all features from update v2.7
- Unpacking Zlib data Video. Zlib is often used to compress models. Usually the beginning of such data is byte 0x78.

Hello? I've paid for the Pro version on your website then where is my key code? Don't tell me this is a trap  

Can't get connection with you.

Is this software already dead?
## Post #127
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2021-02-17T09:58:09+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from DeeepLonE ↑Wed Feb 17, 2021 11:12 am at Wed Feb 17, 2021 11:12 am
>
> 
Lazov wrote: ↑Sun Oct 25, 2020 2:29 pm
Update - Pro version
- Added all features from update v2.7
- Unpacking Zlib data Video. Zlib is often used to compress models. Usually the beginning of such data is byte 0x78.


Hello? I've paid for the Pro version on your website then where is my key code? Don't tell me this is a trap  

Can't get connection with you.

Is this software already dead?
The site has a feedback form. Check the spam folder in your mailbox.
## Post #128
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2021-02-19T05:34:28+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Wed Feb 17, 2021 5:58 pm at Wed Feb 17, 2021 5:58 pm
>
> 
DeeepLonE wrote: ↑Wed Feb 17, 2021 11:12 am
Lazov wrote: ↑Sun Oct 25, 2020 2:29 pm
Update - Pro version
- Added all features from update v2.7
- Unpacking Zlib data Video. Zlib is often used to compress models. Usually the beginning of such data is byte 0x78.


Hello? I've paid for the Pro version on your website then where is my key code? Don't tell me this is a trap  

Can't get connection with you.

Is this software already dead?

The site has a feedback form. Check the spam folder in your mailbox.

Nope. There's nothing in my mailbox spam folder   Can't receive any e-mail from your website.

Do I have to offer another e-mail address ?
## Post #129
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2021-02-19T10:07:07+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from DeeepLonE ↑Fri Feb 19, 2021 1:34 pm at Fri Feb 19, 2021 1:34 pm
>
> 
Do I have to offer another e-mail address ?
Write to me in PM or through the form on the website. I am not aware of the email address you provided. I don't even know when you bought the program. Give me more information.
## Post #130
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2021-02-20T12:31:26+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Fri Feb 19, 2021 6:07 pm at Fri Feb 19, 2021 6:07 pm
>
> 
DeeepLonE wrote: ↑Fri Feb 19, 2021 1:34 pm
Do I have to offer another e-mail address ?

Write to me in PM or through the form on the website. I am not aware of the email address you provided. I don't even know when you bought the program. Give me more information.

I've sent you my gmail address and you've confirmed my bill, now what? No reply again?
## Post #131
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2021-02-22T00:19:49+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from DeeepLonE ↑Sat Feb 20, 2021 8:31 pm at Sat Feb 20, 2021 8:31 pm
>
> 
I've sent you my gmail address and you've confirmed my bill, now what? No reply again?
I replied
## Post #132
- Username: DeeepLonE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 31, 2017 3:33 pm
- Post datetime: 2021-02-23T04:44:07+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Mon Feb 22, 2021 8:19 am at Mon Feb 22, 2021 8:19 am
>
> 
DeeepLonE wrote: ↑Sat Feb 20, 2021 8:31 pm
I've sent you my gmail address and you've confirmed my bill, now what? No reply again?

I replied

Oh, yes!! Thank you very much, sir. I apologize for my rudeness and lousy English
## Post #133
- Username: AMDFreak2006
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 18, 2020 1:26 am
- Post datetime: 2021-05-09T14:37:12+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from AMDFreak2006 ↑Wed Nov 25, 2020 11:46 pm at Wed Nov 25, 2020 11:46 pm
>
> 
Lazov wrote: ↑Tue Oct 06, 2020 5:48 am
AMDFreak2006
Yes, the program does not take into account the position of the texture when saving the model. I will try to fix it in the new version.
Thanks for reporting the issue.


Hi Lazov,

is there any chance for an update or a new version this year? 
Do you need any support, for example some files to test if it's working correctly? I'll be happy to help.

Best Regards

Hi Lazov,

is there any chance of an update in 2021?

Best Regards
## Post #134
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2021-05-12T11:59:51+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hello,

Is possible to open these .sb3d and .sba files from Need For Speed: No Limits, or, at least, understand the model structure?

I bring a BMW M3 E46 GTR as example.

[https://www.dropbox.com/s/6zgfvatbljfe4 ... 6.rar?dl=0](https://www.dropbox.com/s/6zgfvatbljfe4dr/bmw_m3_gtr_e46.rar?dl=0)

Thank you.

UPDATE:

I found that the .sb3d file is compressed, and I have extracted the chunk files thanks to a script from "DKDave" on Discord, but now I'm not sure where the 3d models are; I think there are stored in the most heavy file, but Idk where to find the start offset of the vertices ... I'm not good to read the hex code  

Here the sample: [https://www.dropbox.com/s/4lmr5haze130d ... s.rar?dl=0](https://www.dropbox.com/s/4lmr5haze130dhw/BMW_M3_GTR_Extracted_chunks.rar?dl=0)
## Post #135
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2021-08-28T08:49:04+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Update v2.8

- Replaced the Offset field widget with Spinbox. Spinbox allows you to increase and decrease the field value by one using small buttons or <Up> / <Down> keys;
- Added editing history (Undo / Redo) for Offset, Count, Padding, Pad Inter fields. Called by the keyboard shortcut <Ctrl + Z> / <Ctrl + Y> when the focus is on a field;
- Added number converter Hex / Dex / Oct / Bin ("Tools" -> "Converter");
- Small bugs fixed.

Pro version will be updated later.
## Post #136
- Username: spur868
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 31, 2021 4:39 pm
- Post datetime: 2021-08-31T08:43:33+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

hey man, I am just wondering, is model researcher safe?
## Post #137
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2021-09-02T07:01:27+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from spur868 ↑Tue Aug 31, 2021 4:43 pm at Tue Aug 31, 2021 4:43 pm
>
> 
hey man, I am just wondering, is model researcher safe?
Safe in what sense? It's just a small program.
## Post #138
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2021-11-09T00:47:26+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Greetings. Skeletal animation support is still in development or is it not worth waiting for?
## Post #139
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-05T09:19:02+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from RedBear ↑Tue Nov 09, 2021 8:47 am at Tue Nov 09, 2021 8:47 am
>
> 

I also bought the professional version, but I'm not familiar with the usage. I also tried to analyze some simple but complex ones. The big brother is very busy and doesn't reply to my case email...
## Post #140
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2021-12-10T22:02:52+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from RedBear ↑Tue Nov 09, 2021 8:47 am at Tue Nov 09, 2021 8:47 am
>
> 
Greetings. Skeletal animation support is still in development or is it not worth waiting for?

You should expect the Pro version update, which will include new features from the free version update.  I'm not working on support for skeletal animation yet. I only worked with one type of skeletal animation format from one game. More examples are needed to add support.
## Post #141
- Username: Epii12
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 06, 2021 3:03 am
- Post datetime: 2022-03-15T23:20:05+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi, i really need help i try learn the program but its to complicated for my, i read the tutorial form de page, i view the video tutorials buts whit the archive to i try to extrat its not work, i really need help   

[https://www.mediafire.com/file/t8uk0mbo ... 1.pmf/file](https://www.mediafire.com/file/t8uk0mbokcfjfyl/triad_gangbanger1.pmf/file)

if can explain me how use, with that archive i really appreciate it very much   

Sorry for my bad english
## Post #142
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-06-02T19:33:23+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

It looks like Yoomoney is blocking payments for the Pro version.
## Post #143
- Username: gpktm
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 4:58 am
- Post datetime: 2022-09-10T16:56:46+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

If I select Integer or Short I am getting a "Mismatch of Faces and Vertices". Is there still a possibility of a combination between the Padding and Pad Inter to solve this or does it mean that automatically I need to choose "Bytes" for my faces?
## Post #144
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2022-09-17T18:48:15+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Greg ↑Fri Jun 03, 2022 3:33 am at Fri Jun 03, 2022 3:33 am
>
> 
It looks like Yoomoney is blocking payments for the Pro version.

Unfortunately, due to the global situation, I can no longer sell the Pro version of the program. I removed all links from the site.

Will the Pro version be free? Most likely yes, because the situation will not change in the near future.
In addition, I now have very little free time that I can devote to the development of the program.
## Post #145
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2022-09-18T21:58:36+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Sun Sep 18, 2022 2:48 am at Sun Sep 18, 2022 2:48 am
>
> 
Greg wrote: ↑Fri Jun 03, 2022 3:33 am
It looks like Yoomoney is blocking payments for the Pro version.


Unfortunately, due to the global situation, I can no longer sell the Pro version of the program. I removed all links from the site.

Will the Pro version be free? Most likely yes, because the situation will not change in the near future.
In addition, I now have very little free time that I can devote to the development of the program.

If you are really gona do it free and don't have free time, maybe you could make it open source and post it in GitHub? Maybe someone will try to improve it.
## Post #146
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-09-18T22:19:55+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

That would be certainly interesting. I would totally be interested in learning how the program works and if possible work on few things, had been using the program for quite some time and i find it one of the most versatile when working with 3d models....

If made open source that would allow for many interesting developments and features.
## Post #147
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2022-09-21T14:56:30+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Sparagas ↑Mon Sep 19, 2022 5:58 am at Mon Sep 19, 2022 5:58 am
>
> 
If you are really gona do it free and don't have free time, maybe you could make it open source and post it in GitHub? Maybe someone will try to improve it.

Maybe in the future. This would be useful if some developers would like to work on the project.
What would you like to improve?

Recently, I figured out one format of models from animations. So I'm thinking of adding skeletal animation support. In addition, part of the work is already done.
## Post #148
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2022-09-21T21:04:38+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Wed Sep 21, 2022 10:56 pm at Wed Sep 21, 2022 10:56 pm
>
> 
What would you like to improve?
Well, Pro version is not up to date with Free version. Version numbering for Free/Pro is inconsistent.
There are no release/update notes. I have to look in the forums, what's new was added.
Rename data types. Like Half-Float and Short_Signed. One with "-" and the other with "_". Preferably it should be with " ". Also, it Should be Singed Short and not Short Signed. And what TStripFF means?

Silent Hill 1 has a weird buffer: the first buffer is XYXYXYXYXYXY... and then there is a buffer ZZZZZZ...1
It would be awesome to add a way to read it here.

A way to read info from separate files.

Add vertex colors.

Maybe add export to other file formats, like glTF.
## Post #149
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-09-22T09:47:21+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

well... ideas, i have been talking with another friend that also uses mrp for researching 3d models from games and have compiled a set of things we think might be important, ill mark with bold the most important ones though. here i go:

-multi uvs in containers and support for the python api to auto generate the content(this means that when saving as a .obj that every uv channel gets saved into a new mesh, because .obj has no support for multi-uvs)
-add more information in comments for 3d models from either the python api or the program import(mainly stuff like data of save and origin of the file would be a plus, many times working on long worked projects id like to know the original place and it be hard to recall 100 files)
-autogenerate faces in the program and also automethod for the python api(similar to how hex2obj and AXE)
-vertex color/vertex weights(as said from the other guy, being able to see the vertex color is a very important part given so many games use vertexcolor as a way to split the meshes, and having to code a full python script just to test be a bit annoying)
-(probably hard to implement but would be najs to have: vertex numbering in render; this would be useful to debug how face indexes work)
-interface editor for color, specially the text/hex; moreover being able to save the settings into a specific file that would work as a theme file that could be interchangable and shareable(themes pls?)
-Struct tab where to put information regarding all the different parts and make a bit of a structure before tackling any file(where you can asign colors sizes and padding for different stuff, how to read the header, where the pieces of information regarding sizes offsets and all the other stuff is)
-More colors, more forms to mark stuff in the hex viewer(if there is gonna be stuff like more uvs, also if possible being able to see what is x,y,z, what is u,v and all the other stuff the better, or at least have the possibility to check such stuff if you wanted to)
-Hex viewer rezising tool with different strides(very important to check on how stride pattern works without needing to check every single time in hxd)
-non blocking files, but maybe doing something like cache'ing the data or just making a prompt if the file gets edited by other application(this be important cause sometimes when working on a file from different editor at a time mrp always creates a conflict and requires cloning the file only for the purpose of being able to use the same information at the same time)
-being able to work with more information than just 2 windows at a time, changing the tabs to docking mode if possible(being able to read hex and inputing the places while checking the 3d at the same time would be great, same goes for the pipeline when working on uvs)
-being able to save into other formats(this will be specially hard given how stuff works regading FBX, but maybe CSV would be nice to have; moreover as said before there are many other file formats that could be nice to at least leat people implement)
-multi file working for separated vertexes from faces or any other data(as said before from the other user, not all games have the formats where all the information is stored in 1 file, many use multi file and its a bit annoying when you dont know exactly which file is the one that matches to copy paste, reopen mrp test and do it over and over again, in cases like PGR it could be around 100 files for 1 model...)
-more data types, and also a rework of the existing ones; first of all, many of them, as the guy before said, have bad naming, i dont remember now if the different shorts have been fixed, but at the time there was some problem with uvs using shorts, not to mention many games use formats that are not even here or even possible to read, like for instance int10 that is to be found in xbox360 games, also formats like bit jumps for faces(yes in ps2 in some games you can find that the sequence for the faces might be defined by using a bit to declare if there is a jump or not; although this one might be kinda hard cause its not as simple as if its a 1 is okay and 0 jump... but i guess if there is a way to implement something that can be scripted would be nice); btw, what is that in UVS tab that there is "invert X Y Z"??? if something needs to be corrected to U and V...
-regarding the data read there are also something more that can be really important is both scaling and positioning, not all games give you the information directly where it is suposed to be or the scaling factor, bear in mind that scaling is not always uniform in all the coordinates, so having a scaling factor for each xyzuv would be best to have, in UVS is quite normal to find scalling values in 6th/7th gen consoles. Position probably having 1 set of of XYZ like 1 vertex that translates the pivot of the mesh should be okay, also normal to be found in meshes that are super big(like maps).
-Texture render tab, here there are a lot of things that need fixing, first of all, everything rendered does not go over 1,1 which means it overlaps other stuff and doesnt help visualize how tiled textures work properly, besides that, why not make the whole window 1 uniform color? adding a grid to understand the size of things would also be great, and being able to pan around and zooming if possible
-turn the "flip" function off as default, it is quite common to do things wrong because that thing is on from default and specially for new users that are not accostumed to it might find it problematic at first
-zlib decomping method needs a proper rework, either that you are able to unpack inside the file itself the compressed values or just being able to duplicate the file with a proper decomped segment while keeping the header and other stuff, if possible to add a "scan" for 78 01/78 5E/78 9C/78 DA/78 20/78 7D/78 BB/78 F9 would be great mainly cause for many people that are not that used to working with compressed files might find it hard to even see where the compressed values begin
-auto save option both for python and the current data; there have been sooo many times that i have been working for hours on some file for the program to hang and break without even a warning that i cannot save what i was working on and gotta do it all back again from memory, not even loading mrp in ram helps snipeting the code
-the open file dialog not in mrp folder but last opened(save direction to some variable in a sheet in the mrp folder)
-also a language translation file by doing a database with all the information regarding the variables would be nice to have
-in real time connection between data from mrp and python api for being able to call both of them from one another; many times i have this trouble where i need to know the name of a file or the directory it is in while working on python script while i was testing on mrp, yeah i know i can use open(file.dat, 'r') and then call the directory using glob.glob() and all that shit, but why not just let it all be called through mrp.get_bfile()???; moreover, if i am testing a file and i cannot find faces and need to do some code snippet, why cant i not just go and call the vertexes already rendered in mrp through mrp.get_mesh(root) or something like that? would be nice to have
-input() from python being allowed with a prompt in windows, also a key interrupt escape would be so welcomed, not everyone that works on this is a programer and making mistakes like infinite whiles or reading stuff wrong makes some scripts hang in the run process, thus having a way to stop the code like how in python ctrl + C stops it
## Post #150
- Username: cod2enthusiast2132
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 14, 2021 5:52 am
- Post datetime: 2022-09-27T18:49:27+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hello everybody I am just wondering if anybody can help me extract the meshes from call of duty 2 big red one. I am working on the panzer model right now, and I have succeeded at finding the vertices at 0x3000 but the faces however I cannot find in the model itself. If anybody can please look at this mesh and see if it's even possible for me to extract it. luxox18 probably used the same method with call of duty 3 but i don't know
[panzermesh.zip](https://xentaxbackup.github.io/file/22862_panzermesh.zip)
## Post #151
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-10-03T22:06:21+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

At least you're finally responding, I thought you got drafted or just hated foreigners.
## Post #152
- Username: tianjiegao
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 02, 2021 9:40 pm
- Post datetime: 2022-12-04T11:10:30+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Buy 3D Model Researcher Pro
It is currently not possible to purchase the program.
## Post #153
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2022-12-17T12:18:35+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Machinedramon ↑Mon Sep 19, 2022 6:19 am at Mon Sep 19, 2022 6:19 am
>
> 
That would be certainly interesting. I would totally be interested in learning how the program works and if possible work on few things, had been using the program for quite some time and i find it one of the most versatile when working with 3d models....

If made open source that would allow for many interesting developments and features.

Are you a programmer?
## Post #154
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-12-17T13:14:32+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Sat Dec 17, 2022 8:18 pm at Sat Dec 17, 2022 8:18 pm
>
> 
Machinedramon wrote: ↑Mon Sep 19, 2022 6:19 am
That would be certainly interesting. I would totally be interested in learning how the program works and if possible work on few things, had been using the program for quite some time and i find it one of the most versatile when working with 3d models....

If made open source that would allow for many interesting developments and features.


Are you a programmer?

I wish, no, im more of an aficionado, i probably started learning to program in a more serious fashion ever since i started using MRP, but also in the process i found many things about the program i would rather do in other ways, i have been trying to replicate the same ideas i posted by creating my own program, so far i have tried doing interfaces with C# and winforms, but mostly im having a lot of trouble with the 3d rendering using openGL, thats why id love to see MRP go open source, there i would totally try and and replicate and anylize what the structure of the code is in your program. It would probably take me a lot of tinkering and try and failure, but i'd be really happy to work with it.
## Post #155
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2023-03-25T11:45:59+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

The PRO version of the program has become free. Thanks to everyone who supported the development.
Download:
[http://mr.game-viewer.org/download.php](http://mr.game-viewer.org/download.php)
## Post #156
- Username: UndeadFrankie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 25, 2019 2:24 am
- Post datetime: 2023-04-30T16:25:50+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Thanks for this program Lazov, it's incredibly helpful! Do you mind sharing the formula that tstrip uses for short indices? I'm trying to write my own model converter for a specific series of games but most of the documentation I've seen about tri-strips is involving the vertices instead of the indices. If it ever releases publicly I could credit you for the tstrips.
## Post #157
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2023-05-01T09:22:45+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from UndeadFrankie ↑Mon May 01, 2023 12:25 am at Mon May 01, 2023 12:25 am
>
> 
Thanks for this program Lazov, it's incredibly helpful! Do you mind sharing the formula that tstrip uses for short indices? I'm trying to write my own model converter for a specific series of games but most of the documentation I've seen about tri-strips is involving the vertices instead of the indices. If it ever releases publicly I could credit you for the tstrips.

I'm not lazov but maybe i can help, TStrip or triangle strip is just a way to generate a list of indices that relate to the vertex count/numeration in the sense that you will be able to generate triangles using a compact format in binaries; that is, lets say that for example for a model that has 10 vertexes in total you have the following tstrip:
0 1 2 2 3 4 5 6 6 7 8 9 (this is a normal tstrip, there is also the FF tstrip that does include jumps using FF instead)

here the logic for the faces is:
0 1 2; repeated 2 = jump to new part; 2 3 4; 4 3 5; 4 5 6; repeated 6 means jump; 6 7 8; 8 7 9.

see how from A B C we switch every second to B A C; thats how it defines the faces:
(the reason why it changes is because faces originally only have 1 orientation (what we call the culling be the back part, not rendere, and the side of the face that has normal, which gets rendered), this is defined by how the generation works using the clockwise direction here the example of how that looks schematically:
## Post #158
- Username: UndeadFrankie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 25, 2019 2:24 am
- Post datetime: 2023-05-01T19:11:12+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Machinedramon ↑Mon May 01, 2023 5:22 pm at Mon May 01, 2023 5:22 pm
>
> 
UndeadFrankie wrote: ↑Mon May 01, 2023 12:25 am
Thanks for this program Lazov, it's incredibly helpful! Do you mind sharing the formula that tstrip uses for short indices? I'm trying to write my own model converter for a specific series of games but most of the documentation I've seen about tri-strips is involving the vertices instead of the indices. If it ever releases publicly I could credit you for the tstrips.


I'm not lazov but maybe i can help, TStrip or triangle strip is just a way to generate a list of indices that relate to the vertex count/numeration in the sense that you will be able to generate triangles using a compact format in binaries; that is, lets say that for example for a model that has 10 vertexes in total you have the following tstrip:
0 1 2 2 3 4 5 6 6 7 8 9 (this is a normal tstrip, there is also the FF tstrip that does include jumps using FF instead)

here the logic for the faces is:
0 1 2; repeated 2 = jump to new part; 2 3 4; 4 3 5; 4 5 6; repeated 6 means jump; 6 7 8; 8 7 9.

see how from A B C we switch every second to B A C; thats how it defines the faces:
(the reason why it changes is because faces originally only have 1 orientation (what we call the culling be the back part, not rendere, and the side of the face that has normal, which gets rendered), this is defined by how the generation works using the clockwise direction here the example of how that looks schematically:

No worries I really appreciate the help! When you say "repeated 2 = jump to new part" do you mean skipping bytes or is that just where the next set of indices starts? I'm confused because lets say I read your example into Model Researcher as short tstrip (00 00 01 00 02 00 02 00 03 00 04 00 05 00 06 00 06 00 07 00 08 00 09 00). I get this:
0 1 2 = A B C
4 3 2 = C B A
3 4 5 = Reversed Previous and Added 1 to each?
6 5 4 = Reversed Previous and Added 1 to each?
6 7 8 = A B C?
9 8 7 = C B A?
Either way it has more bytes and indices then the initial input which is throwing me off. 
In my example I think it's counterclockwise but I'm not sure if I calculated them properly because in larger files there's some variation to the pattern. Thanks for taking the time to write the initial reply it's definitely explained a few things I wasn't understanding
## Post #159
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2023-05-05T18:13:58+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

I would say that you gotta be careful with the output and processing from MRP; for all the documentation regarding triangle strips its regarded as the second series being flipped around, then you restart the count after each jump so it keeps the same orientation for the faces, im not sure if its a bug of MRP or that im totally understanding things wrongly, given so many models from PS2 games i have treated have a problem with faces being flipped im inclined to think its a MRP bug where it goes ABC -> CAB instead of ABC -> BAC

for more information regarding how OpenGL Triangle strips work: (extracted from [https://www.learnopengles.com/tag/triangle-strips/](https://www.learnopengles.com/tag/triangle-strips/))

> Let’s look at our index buffer again:
>
> 
>
> indexBuffer = {
>
>     1, 6, 2, 7, 3, 8, 4, 9, ...
>
> }
>
> When drawing with GL_TRIANGLE_STRIP, OpenGL will build triangles by taking each set of three vertices, advancing by one vertex for each triangle. Every subsequent triangle shares two vertices with the previous triangle. For example, here are the sets of vertices that would be grouped into triangles:
>
> 
>
> Triangle 1 = 1, 6, 2
>
> Triangle 2 = 6, 2, 7
>
> Triangle 3 = 2, 7, 3
>
> Triangle 4 = 7, 3, 8
>
> Triangle 5 = 3, 8, 4
>
> Triangle 6 = 8, 4, 9
>
> …
>
> OpenGL also maintains a specific order, or winding when building the triangles. The order of the first 3 vertices determines the order for the rest. If the first triangle is counter-clockwise, the rest will be counter-clockwise, too. OpenGL does this by swapping the first two vertices of every even triangle (swapped vertices are in bold):
>
> 
>
> Triangle 1 = 1, 6, 2
>
> Triangle 2 = 2, 6, 7
>
> Triangle 3 = 2, 7, 3
>
> Triangle 4 = 3, 7, 8
>
> Triangle 5 = 3, 8, 4
>
> Triangle 6 = 4, 8, 9
>
> …

here how MRP Renders the file using those parameters


here a comparison between how it should be rendered vs how its rendered(the one with 2 different normal values is the one that MRP outputs)


and lastly the output text from MRP, like you said, its the same series you get.


both files as well as the binary i upload here in a .rar file
[test.rar](https://xentaxbackup.github.io/file/23775_test.rar)
## Post #160
- Username: UndeadFrankie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 25, 2019 2:24 am
- Post datetime: 2023-05-08T16:10:35+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

That link was really helpful for understanding it better, it's a pretty complex topic. Now that you mention it I've noticed flipped faces on some of my models too. 

> and lastly the output text from MRP, like you said, its the same series you get.
I didn't realize at first but the text output in MRPF and MR v2.8 displays differently then it exports. With the exact same parameters that sequence displays as 

```
f  4 3 2
f  3 4 5
f  6 5 4
f  6 7 8
f  9 8 7
```

but in the paid pro version and in the pro demo it displays as:

```
f  5 4 3
f  4 5 6
f  7 6 5
f  7 8 9
f  10 9 8
```

both seem to export it as 1 2 3 though so it's no big deal. Originally I was just going off what it displayed in MRPF but now I know I gotta export it first then read the faces / indices. Thanks again for all the help its made it way easier to understand though. Those sample files have been helpful for testing stuff out too.
## Post #161
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-05-09T19:35:57+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Generally in computers counting starts from 0, but in .OBJ files counting starts from 1.
It is probably just an oversight in these two versions.
## Post #162
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2023-05-11T13:08:34+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi all!
What am I doing wrong?
Example 3d model:
[https://www.mediafire.com/file/i8vtrz1b ... r.rar/file](https://www.mediafire.com/file/i8vtrz1bbcfybh9/peugeot_3008_dkr.rar/file)

I continue to study 3D Model Researcher. I use the Pro version.
I use the guide from the program website. I am currently receiving an error (
Traceback (most recent call last):
File "MR", line 27, in
mesh.set_uvs(uvs)
MRError: The form of the matrix should be Nx2)
I have no idea what it is, but there is no model. If you remove the mesh.set_uvs string (uvs), the model appears.
## Post #163
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2023-05-12T12:23:47+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from micro777 ↑Thu May 11, 2023 9:08 pm at Thu May 11, 2023 9:08 pm
>
> 
Hi all!
What am I doing wrong?
Example 3d model:
https://www.mediafire.com/file/i8vtrz1b ... r.rar/file

I continue to study 3D Model Researcher. I use the Pro version.
I use the guide from the program website. I am currently receiving an error (
Traceback (most recent call last):
File "MR", line 27, in
mesh.set_uvs(uvs)
MRError: The form of the matrix should be Nx2)
I have no idea what it is, but there is no model. If you remove the mesh.set_uvs string (uvs), the model appears.

What the code is telling you is that you are trying to give some UVS to the mesh that dont use the format (u, v); print the uvs and see what are you trying to give to the mesh and you will see why its not working; simply add print(uvs) before you do it, i would suggest not doing it with a full 100 k vertexes xD
## Post #164
- Username: Peakzz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2022 2:03 am
- Post datetime: 2023-05-14T16:38:01+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Lazov ↑Sat Mar 25, 2023 7:45 pm at Sat Mar 25, 2023 7:45 pm
>
> 
The PRO version of the program has become free. Thanks to everyone who supported the development.
Download:
http://mr.game-viewer.org/download.php
Is it possible to get the version shown in this video ?
[https://www.youtube.com/watch?v=Y951j875Xak&t=1s](https://www.youtube.com/watch?v=Y951j875Xak&t=1s)
because the file format that im trying to research has skeletons + animations
## Post #165
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2023-05-15T20:46:53+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Peakzz ↑Mon May 15, 2023 12:38 am at Mon May 15, 2023 12:38 am
>
> 
Lazov wrote: ↑Sat Mar 25, 2023 7:45 pm
The PRO version of the program has become free. Thanks to everyone who supported the development.
Download:
http://mr.game-viewer.org/download.php

Is it possible to get the version shown in this video ?
https://www.youtube.com/watch?v=Y951j875Xak&t=1s
because the file format that im trying to research has skeletons + animations

This is a demo video. Skeletal animation is not yet supported.
## Post #166
- Username: an90dy905909
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 30, 2018 3:02 am
- Post datetime: 2023-06-13T14:49:24+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hy there,

just one question about 3d model researcher and faces type, is there any way to  render-print (export mesh) as quads
but not triangles?

Thanks.
## Post #167
- Username: Oszkarosv
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 01, 2023 4:06 pm
- Post datetime: 2023-07-01T08:19:02+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Good morning from Vienna,

first of all thank you very much for this excellent tool, Mr. Lazov.
One question would refer to Tracebacks. Is it possible to retrieve the contents (source code ) of files
mentioned in those error messages in order to analyze what is going wrong?
For example , I got this when trying to visualize texture polygons:

Traceback (most recent call last):
  File "MR", line 55, in 
    mrp.view_uvs("Root")
  File "mrp.py", line 103, in mrp.view_uvs (mrp.c:4108)
  File "\mainh.py", line 1483, in mr_pro.e2429d5a23.on_preview_uvs (mainh.c:33202)
UnboundLocalError: local variable 'conf' referenced before assignment

So it would be great to have a look into "mrp.py" or "\mainh.py" (by the way, the directory structure is also invisible)

Rendering works for me only visualising 3d models without textures, if I attempt to display materials, the program crashes.

Any support is appreciated.
Kind regards, Oszkar
## Post #168
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2023-07-03T09:46:02+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Oszkarosv
Thanks for reporting the bug. Indeed, this is a bug. I'll fix it soon and update the version on the site.
an90dy905909
Yes, quads should be supported
## Post #169
- Username: AMDFreak2006
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 18, 2020 1:26 am
- Post datetime: 2023-09-07T16:20:50+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from AMDFreak2006 ↑Mon Oct 05, 2020 2:18 am at Mon Oct 05, 2020 2:18 am
>
> 

Hello Lazov,

thanks for making the Pro version now for free.
However the bug I described around 3 years ago is still there. As already said 3 years ago I'm willing to help here with example files, testing, describing my analysis mehod, etc. if that is helpful.

The bug:
There is still no way to export the OBJ-file in a way that the coordinates (UV) for the textures are correct (see quoted screenshots and text above).

I managed to flip the texture image file itself for example in Blender (or an external tool) but I don't think thats the correct way to go due to quality losses, or is it the only way?
Is there any way to correct the UV coordinates to map to the correct texture image coordinates without flipping the image file itself?

If not, how can the corresponding texture image file be automatically flipped? Is there some kind of parameter in the OBJ or MTL file?


Besides that question: Does anyone know how the texture files in my screenshots above got created in the first place? The game manages to read the texture information of 4 different cars from this one texture TGA file. And as seen especially in the last screenshot the textures/cars are quite distorted in the texture image file due to the shape of the UV-polygons. I don't think the game devs draw this distortion manually so how did they create those texture files in the first place?
How can I create such a distorted texture file myself? In Blender I wasn't able to correctly paint the exported model in the 3D view (it just works correctly in 2D view, but that doesnt't help much since I could do this better in GIMP, Photoshop etc, then.) Are there any other tools which are able to do it or what am I doing wrong?

Thanks in advance.
## Post #170
- Username: JanB23
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 19, 2023 12:17 am
- Post datetime: 2023-09-26T23:23:34+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

Hi, i'm sorry but i'm having an issue, when i runs an script MRP gave this:

Traceback (most recent call last):
  File "MR", line 3, in 
    from nines import *
ModuleNotFoundError: No module named 'nines'

Can you help me? Please

Thanks in advance

P.D.: i used the search in this theme but not results about my issue
## Post #171
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-09-27T21:20:57+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

You are trying to import nines module. What is it? If you didn't wrote the script, or don't know what I am talking about, try deleting this line from your script:

```
from nines import *
```

If it doesn't help, then you need to learn Python programming language. Or import nines module. It should be places in the same folder, as program, or in documents folder or "your user name" folder. Can't remember witch one. Try them all.
## Post #172
- Username: JanB23
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 19, 2023 12:17 am
- Post datetime: 2023-09-27T23:15:15+00:00
- Post Title: Re: 3D Model Researcher - extract 3D models with Python

> Reply from Sparagas ↑Thu Sep 28, 2023 5:20 am at Thu Sep 28, 2023 5:20 am
>
> 
You are trying to import nines module. What is it? If you didn't wrote the script, or don't know what I am talking about, try deleting this line from your script:
Code: Select allfrom nines import *
If it doesn't help, then you need to learn Python programming language. Or import nines module. It should be places in the same folder, as program, or in documents folder or "your user name" folder. Can't remember witch one. Try them all.

Thanks for answer, i followed your advice; finally runs, and you are totally right i don't wrote the script, and i'm looking for all data about python modules.

I'm looking for other ways to extract my model but looks little tricky.

Anyway, thanks a lot for your answer cheers and long live
