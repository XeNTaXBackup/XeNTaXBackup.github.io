## Post #1
- Username: TerrorMask
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 04, 2021 5:52 pm
- Post datetime: 2021-09-23T16:24:29+00:00
- Post Title: Final Exam 2013 .zwo / .geo file models.

The final exam 2013 game consists of models and bones packed in .geo file and the .zwo file possibly has the bones. the animations are in .ani files (the animation cursor files since being a 2D Side scrolling game) but the models are fully 3d implemented. I can't use a hex editor much and no experience related to it. I managed to get the textures from the .hvt file, but is there any way to get the model from inside the GEO / ZWO file ? here is sample. The sample file  contains the model of an unuseable character which was originally playable and is in game as well. the rar file contains her geo model and zwo too. is there any tool to open this model and use it?
[skins.rar](https://xentaxbackup.github.io/file/20873_skins.rar)
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-09-24T02:48:34+00:00
- Post Title: Final Exam 2013 .zwo / .geo file models.

At first glance with Hex2obj:



shannon.geo.png (62.93 KiB) Viewed 82 times


UV uses half-float.
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-10-05T17:22:26+00:00
- Post Title: Final Exam 2013 .zwo / .geo file models.

> Reply from TerrorMask ↑Fri Sep 24, 2021 12:24 am at Fri Sep 24, 2021 12:24 am
>
> 
Is there any tool to open this model and use it?

I have finished my Final Exam .geo and .hvt loader modules and I have released the following programs as web updates:

- 3D Object Converter v8.016	(Windows)
- i3DConverter v4.106		(macOS)
- i3DConverter v2.106		(Linux)

How to get the 3D Object Converter v8.016:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v8.016.

How to get the i3DConverter macOS v4.104:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v4.104.

How to get the i3DConverter Linux v2.104:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v2.104.




Final_Exam_Shannon.jpg (134.15 KiB) Viewed 69 times
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-10-05T17:24:01+00:00
- Post Title: Final Exam 2013 .zwo / .geo file models.

Here I attached the converted file.
[Final_Exam_Shannon.zip](https://xentaxbackup.github.io/file/20949_Final_Exam_Shannon.zip)
## Post #5
- Username: TerrorMask
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 04, 2021 5:52 pm
- Post datetime: 2021-10-06T21:42:59+00:00
- Post Title: Final Exam 2013 .zwo / .geo file models.

> Reply from Karpati ↑Wed Oct 06, 2021 1:24 am at Wed Oct 06, 2021 1:24 am
>
> 
Here I attached the converted file.

The bmp texture fil is missing in the zip you shared can you provide that too? thanks alot for this model.
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-10-07T16:56:27+00:00
- Post Title: Final Exam 2013 .zwo / .geo file models.

> Reply from TerrorMask ↑Thu Oct 07, 2021 5:42 am at Thu Oct 07, 2021 5:42 am
>
> 

The bmp texture fil is missing in the zip you shared can you provide that too? thanks alot for this model.

I have removed it from the .zip file, because of the attachment size.

Here I attached the shannon01_diff.bmp file.
[shannon01_diff.zip](https://xentaxbackup.github.io/file/20965_shannon01_diff.zip)
