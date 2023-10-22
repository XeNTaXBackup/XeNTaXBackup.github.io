## Post #1
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2012-10-18T13:21:35+00:00
- Post Title: Of Orcs and Men

Hi,

I have figured out how to get the models and textures out, but the rigging and bones is still unsolved. Perhaps there is already a solution for it, the game uses the The Silk Engine (Built upon the Sony Phyre Engine). Content is packed in .pssg

-I unzipped the .spk packs
-Renamed the .pgz to .pssg
-Extracted the textures with [http://devtechsource.com/site/tools/vie ... /6/22.html](http://devtechsource.com/site/tools/viewdownload/6/22.html)
-Extracted the models with this [http://www.sim-garage.co.uk/3DSimED3/3DSimED3_Beta.html](http://www.sim-garage.co.uk/3DSimED3/3DSimED3_Beta.html)

If anyone is interested in taking a look at the rigging and animation perhaps, give me a shout.

Best Regards
joqqy
## Post #2
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-10-18T22:01:55+00:00
- Post Title: Of Orcs and Men

Tried to follow the methods for extraction with the links but with no success. Renaming the files doesnt seem to work. 
Can you elaborate what you have done?
## Post #3
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2012-10-19T13:23:04+00:00
- Post Title: Of Orcs and Men

Hi Matreco,

First unzip the game packs. Then unzip again. In the textures folders you have the texture files without an extension, but they are .dds files inside .pssg files. Use the PSSG editor to save them out.

As for the model files, they are also .pssg files, and they contain the skeleton and skin weights also. However not all av them will import with 3DSimED. The PSSG Database structure I haven't figured out.



joqqy
## Post #4
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-10-19T18:13:21+00:00
- Post Title: Of Orcs and Men

Hi Joqqy. 

That worked well, I missed the double extract, which was causing the files to still be zipped.
## Post #5
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2012-10-29T21:38:10+00:00
- Post Title: Of Orcs and Men

I am writing a Max Script importer.

Work in progress for the .pssg database importer for Max:



Geometry and UV solved, currently working on the bones and skinweight structure.

Best regards
joqqy
## Post #6
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-11-02T15:13:52+00:00
- Post Title: Of Orcs and Men

Looking fwd to the script, great work so far.
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-11-15T09:17:19+00:00
- Post Title: Of Orcs and Men

This is nice!!

Share the max script man 

like please...

T
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-11-20T22:53:37+00:00
- Post Title: Of Orcs and Men

unpacked the first spk with WinRar, the sli.spk 
apparently they are all valid xml files 

T.
## Post #9
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-13T13:28:34+00:00
- Post Title: Of Orcs and Men

hi all i'am looking for information about pgz  sounds thanks
## Post #10
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2017-01-10T15:56:24+00:00
- Post Title: Of Orcs and Men

> Reply from joqqy
>
> I am writing a Max Script importer.

Work in progress for the .pssg database importer for Max:



Geometry and UV solved, currently working on the bones and skinweight structure.

Best regards
joqqy

can you share this script
## Post #11
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2017-02-10T18:31:55+00:00
- Post Title: Of Orcs and Men

Sorry for necro, any chance on releasing the script albeit unfinished?
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-10T21:32:33+00:00
- Post Title: Of Orcs and Men

maybe you can try Szkaradek123's Blender importer
[viewtopic.php?f=16&t=12473](http://forum.xentax.com/viewtopic.php?f=16&t=12473)

says it supports

> -Of Orcs and Men PS3
or maybe upload some samples for anyone interested to look at
