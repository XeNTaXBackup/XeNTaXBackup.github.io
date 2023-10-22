## Post #1
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-02-22T18:35:01+00:00
- Post Title: Deception IV Blood Ties [PS3]

Hi
Here is unpacker and importer for models from this game.
It requires Blender version 249b and Python 2.6.6.
How use:
1.click Blender249.blend
2.in Blender Text Window press alt+p and select:
- lfm_order.bin - for unpacking archive00.bin
- FILE_PS3==>ACTION==>MODEL - "_mdl.bin" - for importing textured and rigged models.

Script decompress _mdl.bin and *.g1t files with offzip. [http://aluigi.altervista.org/mytoolz.htm](http://aluigi.altervista.org/mytoolz.htm).
All decompressed files are move to folder ,where is blend file.
[Blender249[Deception4BloodTies][PS3][bin][2015-02-22].zip](https://xentaxbackup.github.io/file/8738_Blender249[Deception4BloodTies][PS3][bin][2015-02-22].zip)
## Post #2
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-02-24T05:02:23+00:00
- Post Title: Deception IV Blood Ties [PS3]

Thanks for this! I had a little trouble getting it to work and wanted to share it here in case anyone else was having the same issues. 

-If you have an archive00.lnk (shortcut) instead of archive00.bin then rename it or it won't extract properly. I had to use the command prompt rename mine.
-No spaces in the folder names! While I was able to extract the .bin file with spaces in a folder name, it wouldn't when trying to extract/load the models. Removing the space fixed it. 

Probably a couple of "no shit..." fixes but just in case, there's the fixes! Again, big thanks to Szkaradek123 for this script (and that Unwritten Tales script I still need to check out). Once I figured out the issues I loaded a few models and all was well.
## Post #3
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2015-11-01T21:18:38+00:00
- Post Title: Deception IV Blood Ties [PS3]

> Reply from Szkaradek123
>
> Hi
Here is unpacker and importer for models from this game.
It requires Blender version 249b and Python 2.6.6.
How use:
1.click Blender249.blend
2.in Blender Text Window press alt+p and select:
- lfm_order.bin - for unpacking archive00.bin
- FILE_PS3==>ACTION==>MODEL - "_mdl.bin" - for importing textured and rigged models.

Script decompress _mdl.bin and *.g1t files with offzip. http://aluigi.altervista.org/mytoolz.htm.
All decompressed files are move to folder ,where is blend file.
[http://www.mediafire.com/download/0s1bc ... 0/AS0A.zip](http://www.mediafire.com/download/0s1bcwac1um4hy0/AS0A.zip)
How to extract the model file
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-02T11:04:19+00:00
- Post Title: Deception IV Blood Ties [PS3]

offzip just splits C_AS0A_0A_MDL.BIN up into about 20 near to useless 16k .dat files.

> You'll have to find means to cure this, as simple as that -
maybe concatenate the dats in the order given by the address in their names, dunno.



C_AS0A_0A_MDL.JPG (32.16 KiB) Viewed 198 times
## Post #5
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2015-11-02T16:57:57+00:00
- Post Title: Deception IV Blood Ties [PS3]

This is the Deception IV:Another Princess model file 
Different file format cannot unpack？
## Post #6
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2015-11-02T17:03:02+00:00
- Post Title: Deception IV Blood Ties [PS3]

> Reply from shakotay2
>
> offzip just splits C_AS0A_0A_MDL.BIN up into about 20 near to useless 16k .dat files.

> You'll have to find means to cure this, as simple as that -
maybe concatenate the dats in the order given by the address in their names, dunno.
C_AS0A_0A_MDL.JPG
[viewtopic.php?f=16&t=13379](http://forum.xentax.com/viewtopic.php?f=16&t=13379)
How to extract the model file
