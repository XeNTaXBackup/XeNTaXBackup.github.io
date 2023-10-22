## Post #1
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-07-07T18:47:55+00:00
- Post Title: CSI Scripting Help

Hey there, 

Finished up basically reversing an entire image (First one woohoo!) And a pretty simple one to begin with... The only issue is I'm having trouble with one pixel format's color arrangements. Any time it opens up a "RGB888" image it works fine, but when I attempt to open up ARGB32 it's colors are all messed up. I've been messing around with the channel order, but have not been able to fix it up at all. Could anyone take a look at this? It would help a lot! Provided down below is the import script, as well as "Logo1.csi and Logo2.csi"(the only files causing me issues), and then some random CSI's for comparison if needed. Overall, very happy about the learning experience I've gained so far, and hope to keep going further! If you look into the file you see that there's a clear identifier for the pixel order. Best part is that the images are all 256x256. Thanks in advance! Game is American Chopper from XBOX.

~Eric

[CSI](https://drive.google.com/open?id=1GC8ZNwqPS8vxO6FOeOuaJ2d4FUAMdk45)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-07-07T22:16:19+00:00
- Post Title: CSI Scripting Help

"b8 g8 r8 a8" looks okay to me for Logo1.csi and Logo2.csi
## Post #3
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-07-08T03:36:06+00:00
- Post Title: CSI Scripting Help

> Reply from AceWell
>
> "b8 g8 r8 a8" looks okay to me for Logo1.csi and Logo2.csi
Perfect. Finished official script added [here!](https://github.com/TheDeverEric/noesis-importers/blob/master/Eric%20Van%20Hoven/tex_AmericanChopper_csi.py)
