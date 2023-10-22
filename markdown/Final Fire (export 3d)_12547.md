## Post #1
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2015-01-27T15:44:04+00:00
- Post Title: Final Fire (export 3d)

New Chinese game in the mode closed beta test Final Fire ( 最后一炮 )
Resource pack in the format .pck I did not manage to open. Maybe someone or help?

The game has a lot of qualitative models of Chinese martial art:
[http://ff.zqgame.com/dataStation/index.html](http://ff.zqgame.com/dataStation/index.html)

Link to the game installer:
[https://cloud.mail.ru/public/1d1c5f2c8e ... 121all.exe](https://cloud.mail.ru/public/1d1c5f2c8e24/zhyp_online_v1.0.9678_20150121all.exe)
## Post #2
- Username: Ruyan
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Dec 11, 2014 3:05 am
- Post datetime: 2016-10-09T19:07:25+00:00
- Post Title: Final Fire (export 3d)

So, I was able to get open resources.

Earlier versions were open .dds and 3d models of .dts
[http://www.mediafire.com/file/u75t1et0s ... Fm_old.rar](http://www.mediafire.com/file/u75t1et0swpm57u/FFm_old.rar)

.dts opens program Ultimate Unwrap3D Pro with Plugin (download additional page) - Torque Game Engine (DTS, DSQ):
[http://www.unwrap3d.com/u3d/downloads.aspx](http://www.unwrap3d.com/u3d/downloads.aspx)
But this program is paid (see the demo version, which does not save).

Now the game encrypts .dds and .dts
[http://www.mediafire.com/file/kit368low ... Fm_new.rar](http://www.mediafire.com/file/kit368lowjig3b5/FFm_new.rar)

At the same time the content has expanded considerably. Maybe someone knows a withdrawal options for content?
[http://ff.zqgame.com/dataStation/index.html](http://ff.zqgame.com/dataStation/index.html)

[](http://itmages.ru/image/view/5001979/48b4914b)[](http://itmages.ru/image/view/5001980/6196c4f2)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-13T04:09:57+00:00
- Post Title: Final Fire (export 3d)

> Reply from Ruyan
>
> Now the game encrypts .dds ....
http://www.mediafire.com/file/kit368low ... Fm_new.rar
i made a Noesis python script to open your new dds texture samples  


 tex_FinalFire_dds.zip
(631 Bytes) Downloaded 18 times



supports dxt1 and dxt5

the image data is still dxt just with a custom header
the first 4 bytes of the header is the Xor key for the width at 0x18 and height at 0x14
