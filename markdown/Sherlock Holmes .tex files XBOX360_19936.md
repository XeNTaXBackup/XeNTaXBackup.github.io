## Post #1
- Username: cockafej
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Mar 31, 2018 3:14 am
- Post datetime: 2019-04-03T06:00:03+00:00
- Post Title: Sherlock Holmes *.tex files XBOX360

Hi,

Could someone help me?
I need a tool for tex files of Sherlock Holmes - Jack the ripper X360 game.
Tex to dds or png or jpg
and after modify, reconvert back to tex.

Sample tex files are here:
[https://www80.zippyshare.com/v/eQqxA3FF/file.html](https://www80.zippyshare.com/v/eQqxA3FF/file.html)

Thank you
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-04-03T07:56:59+00:00
- Post Title: Sherlock Holmes *.tex files XBOX360

> Reply from cockafej ↑Wed Apr 03, 2019 2:00 pm at Wed Apr 03, 2019 2:00 pm
>
> ...Tex to dds or png or jpg....
well here is Noesis python script to get you that far since modding is not my area.   
*script updated May 20, 2019*


 tex_SherlockHolmes_X360_tex.zip
(755 Bytes) Downloaded 54 times


supports dxt1, dxt5 and rgba8888
## Post #3
- Username: cockafej
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Mar 31, 2018 3:14 am
- Post datetime: 2019-04-03T12:21:11+00:00
- Post Title: Sherlock Holmes *.tex files XBOX360

Thank you! 

The export to tga is perfect, but able to import this script back to tex?
## Post #4
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-04-10T07:53:48+00:00
- Post Title: Sherlock Holmes *.tex files XBOX360

You can use NFS Shift Xtx to Tga to convert .tex to .tga. Then use .rdf file which is configured by xtx to tga.exe and Bundler.exe from Xbox 360 xdk to convert .tga to .xpr.

Drag rdf to bundler.exe -> copy texture data from created xpr from offset 0x80c with hex editor and paste it to .tex file (texture data starts from offset 0x34)

NFS Shift Xtx to Tga:
[http://veegie.com/tilfeldig/fotografier ... TO_TGA.exe](http://veegie.com/tilfeldig/fotografier/NFS_Shift_XTX_TO_TGA.exe)

Bundler.exe:
Just google it, I haven't permission to share it.
## Post #5
- Username: cockafej
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Mar 31, 2018 3:14 am
- Post datetime: 2019-04-10T14:36:17+00:00
- Post Title: Sherlock Holmes *.tex files XBOX360

Thank you, Beedy!
