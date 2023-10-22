## Post #1
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2021-12-23T11:20:41+00:00
- Post Title: Harry Potter Magic Awakened DAT file

Hello, anyone willing to have a look at some model files from the Harry Potter game? Its available on mobile and PC (Taiwan) in the east. Yet to be released in the West. 
The character models are in .dat file however I am not able to find any scripts to extract the model data. Anyone willing to help? 

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/17yq1R2y0ICPy906Li7lBVBntRC8HcsXx?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-23T13:50:52+00:00
- Post Title: Harry Potter Magic Awakened DAT file

.dat: textures? (You may need to modify the header)
.



dat-tex.png (69.34 KiB) Viewed 231 times
## Post #3
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2021-12-23T14:35:41+00:00
- Post Title: Harry Potter Magic Awakened DAT file

Thanks a lot for having a look! TBH I have limited knowledge of using HEX2OBJ tools. On extracting the .npk archive I get a bunch of these dat, xml and raw files. In the character folder for e.g. I am assuming the dat files have both texture and model information and the xml has animation information. 

Looking at ....00000000aa.dat it has skeletal and mesh info. However I am struggling to figure out the structure. I am following your tutorials, but this might be beyond my capabilities! 
Appreciate it if you can have a look!




> Reply from shakotay2 ↑Thu Dec 23, 2021 9:50 pm at Thu Dec 23, 2021 9:50 pm
>
> 
.dat: textures? (You may need to modify the header)
.
dat-tex.png
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-23T16:30:07+00:00
- Post Title: Harry Potter Magic Awakened DAT file

well, you'll need to fiddle around a little bit to get the full mesh correctly:
.



00aa-dat.png (85.88 KiB) Viewed 226 times

(There's many holes and overlaps when using a face index count of 5863.)
## Post #5
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-12-23T17:51:19+00:00
- Post Title: Harry Potter Magic Awakened DAT file

You can see models with akderebur's RMA Viewer in this [topic](https://forum.xentax.com/viewtopic.php?f=16&t=17982).



RMAViewer.png (62.29 KiB) Viewed 223 times
## Post #6
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-12-23T17:52:18+00:00
- Post Title: Harry Potter Magic Awakened DAT file

Rename texture files from .dat to .ktx
To see these textures, you can use [ImageViewer](https://github.com/kopaka1822/ImageViewer/releases).



pintktx.png (100.29 KiB) Viewed 214 times
## Post #7
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2021-12-23T21:51:33+00:00
- Post Title: Harry Potter Magic Awakened DAT file

Thanks a ton shakotay2 and reh! Will have a look post Christmas 

Wishing you a merry Christmas and thanks for being so helpful!
## Post #8
- Username: tachiban
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 18, 2021 2:09 pm
- Post datetime: 2022-03-29T17:53:52+00:00
- Post Title: Harry Potter Magic Awakened DAT file

> Reply from reh ↑Fri Dec 24, 2021 1:51 am at Fri Dec 24, 2021 1:51 am
>
> 
You can see models with akderebur's RMA Viewer in this topic.
RMAViewer.png
Can it be exported to animation?
