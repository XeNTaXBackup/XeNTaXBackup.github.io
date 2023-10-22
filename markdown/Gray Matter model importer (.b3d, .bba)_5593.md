## Post #1
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-12-20T22:01:48+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

The contents of this post was deleted because of possible forum rules violation.
[graymatter.jpg](https://xentaxbackup.github.io/file/3704_graymatter.jpg)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-20T23:08:45+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

Nice job your on a roll
## Post #3
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-02T14:32:26+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

Sadly it appears this script is not working on the 360 version extractions just updated by bacter here: [viewtopic.php?f=10&t=5407&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=5407&start=15) 

Script fails on line 405 openfile('b3d') 

I've checked that I have the correct Python version # and that the script is in the directory with the extracted file (model)

[HERE is a sample file ](http://www.highendgames.net/Lee/sample.rar)that is failing the script:
## Post #4
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-02T15:13:32+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

Update for xbox360 version of this game. (reversed Endianness)
 - textures are in tex format, that not read script
 - animation are supported
[import-gray-matter-2010-12-19-x360.zip](https://xentaxbackup.github.io/file/3865_import-gray-matter-2010-12-19-x360.zip)
## Post #5
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-02T16:00:55+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

> Reply from Szkaradek123
>
> Update for xbox360 version of this game. (reversed Endianness)
 - textures are in tex format, that not read script
 - animation are supported

Wow, that was fast! Indeed it works! (at least the model part) Like you said, the textures are compressed though (.tex) vs. the PC version being straight .dds. I'll post samples on the appropriate forum for review.

Thanks again!
## Post #6
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:51:41+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

cool
## Post #7
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2011-04-02T12:01:50+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

Complete Blender noob here. I tried using this script but I have no idea how to get it to work. It just pops up some kind of error window that I can't get rid of, that says "Convert Game Engine script from 4.48 API to 2.49 API".

Anyone know how to solve this?
## Post #8
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-04-02T13:39:39+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

> Reply from gambit37
>
> Complete Blender noob here. I tried using this script but I have no idea how to get it to work. It just pops up some kind of error window that I can't get rid of, that says "Convert Game Engine script from 4.48 API to 2.49 API".

Anyone know how to solve this?

I think I know what the problem is...

You *MUST* use this version of blender AND Python only! 

Blender 249, Python 2.6


Completely uninstall any newer versions of both apps and download and install those versions specifically.
## Post #9
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2011-04-02T14:40:16+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

Thanks. I have Blender 2.49b and Python 2.6.6 -- does that little ".6" really make so much difference!?  

I'll try uninstalling anyway -- I'm using tyhe 64bit version of Blender which is not yet as robust as the 32-bit version.

EDIT: That worked  I removed 64bit blender and 64 bit python, and installed 32-bit Blender 2.49 and 32-bit Python 2.6.6. The script now imports the Gray Matter meshes 

Thanks for your help.
## Post #10
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-04-03T11:26:14+00:00
- Post Title: Gray Matter model importer (.b3d, .bba)

> Reply from gambit37
>
> Thanks. I have Blender 2.49b and Python 2.6.6 -- does that little ".6" really make so much difference!?  

I'll try uninstalling anyway -- I'm using tyhe 64bit version of Blender which is not yet as robust as the 32-bit version.

EDIT: That worked  I removed 64bit blender and 64 bit python, and installed 32-bit Blender 2.49 and 32-bit Python 2.6.6. The script now imports the Gray Matter meshes 

Thanks for your help.

Sorry, I should have specified it needed to be the 32bit version as well. Glad it worked out for you tho.
