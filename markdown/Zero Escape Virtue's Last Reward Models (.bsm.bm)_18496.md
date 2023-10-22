## Post #1
- Username: mikoamoy
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 11, 2014 6:34 pm
- Post datetime: 2018-07-26T05:20:56+00:00
- Post Title: Zero Escape Virtue's Last Reward Models (.bsm/.bm)

Can someone help me converting Zero Escape Virtue's Last Reward Models (.bsm/.bm) files?
texture are in dds but model files are in bsm/bm files. (any noesis script or blender script)

[http://www.mediafire.com/file/xckk3a6j1 ... k.zip/file](http://www.mediafire.com/file/xckk3a6j1sfbpa0/quark.zip/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-26T06:58:23+00:00
- Post Title: Zero Escape Virtue's Last Reward Models (.bsm/.bm)

no time for providing a script, sorry
using hex2obj (view link in my sig):



md_helmetShape-skin-bsm.jpg (217.15 KiB) Viewed 130 times
## Post #3
- Username: mikoamoy
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 11, 2014 6:34 pm
- Post datetime: 2018-07-26T09:55:45+00:00
- Post Title: Zero Escape Virtue's Last Reward Models (.bsm/.bm)

Thanks!
but Im really having a hard time try to learn hex2obj ><
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-26T10:59:15+00:00
- Post Title: Zero Escape Virtue's Last Reward Models (.bsm/.bm)

> Reply from mikoamoy
>
> Thanks!
but Im really having a hard time try to learn hex2obj ><this format and especially this model is quite simple. So it would be the best chance to get a clue now. 

All you need to find is the start address of face index block, and the face index count (start of vertices is 0x14, maybe for most of the bsm files?)



md_arm_LShape-skin-bsm.jpg (163.33 KiB) Viewed 119 times
## Post #5
- Username: mikoamoy
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 11, 2014 6:34 pm
- Post datetime: 2018-08-01T04:58:09+00:00
- Post Title: Zero Escape Virtue's Last Reward Models (.bsm/.bm)

> Reply from shakotay2
>
> mikoamoy wrote:Thanks!
but Im really having a hard time try to learn hex2obj ><this format and especially this model is quite simple. So it would be the best chance to get a clue now. 

All you need to find is the start address of face index block, and the face index count (start of vertices is 0x14, maybe for most of the bsm files?)
md_arm_LShape-skin-bsm.jpg

Thanks
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2018-08-01T18:19:59+00:00
- Post Title: Zero Escape Virtue's Last Reward Models (.bsm/.bm)

mikoamoy,

I added the .bsm loader module to the 3D Object Converter v6.538, but I have a question.

The md_coatShape-skin.bsm file has references to the following external files:
scenes/chara/quark/tex/quark_costume1.etc
scenes/chara/quark/tex/quark_cuff.etc

Can you attach these files to a post?

I think the .etc file has references to the real texture files, in this case to the:
quark_costume1.dds
quark_cuff.dds


Unfortunately, I did not find a demo version of the game to get more sample files.
Can you send me some other sample files to me ([i3dc@i3dconverter.com](mailto:i3dc@i3dconverter.com))?
[BSM_multiple.jpg](https://xentaxbackup.github.io/file/14691_BSM_multiple.jpg)
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2018-08-17T09:48:02+00:00
- Post Title: Zero Escape Virtue's Last Reward Models (.bsm/.bm)

I have added the .bm and .bsm loader modules to my program and released the 3D Object Converter v6.538 as a web update.
(Just copy the .dds texture files to the same folder where the .bm/.bsm files exist to get the textured view automatically.)

How to get the 3D Object Converter v6.538:
Please download the 3D Object Converter from [http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it
or download the portable version and extract it into a folder.

Run the program and use the Help/check for updates function to get it.

I have released the updated i3DConverter for Mac and Linux versions also.
[http://www.i3dconverter.com](http://www.i3dconverter.com)
