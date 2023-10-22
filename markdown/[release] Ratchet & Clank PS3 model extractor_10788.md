## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-19T15:39:40+00:00
- Post Title: [release] Ratchet & Clank PS3 model extractor

For discussion I kindly beg to use this thread: [viewtopic.php?f=16&t=10761&p=88357&sid= ... 91a#p88357](http://forum.xentax.com/viewtopic.php?f=16&t=10761&p=88357&sid=c25bd5675574e15daa390a00d9f3891a#p88357)
and leave this release thread for updates and other contributions.

[Rachet&Clank_extractor.zip](http://www.uploadmb.com/dw.php?id=1379604770)

Simple models can be converted using the 'go' button.

For others use the multimodel button ('MM').
For mobyload3.ps3 (1.41 MB) this will create 5 separate obj model files.

IMPORTANT: for multimodels you may have to comment out some faces at the end of the obj files.
(View comment_out_orange_faces.JPG in the zip file.)
If you don't do that so well, don't blame me some models having errorness faces.

Smoothing doesn't work on MM models in blender, textured view showing holes.

In Noesis you can simply press F4 (toggle face culling) and then File Export from preview.
In 3dsmax face culling seems to be preset. Have a look at Nefarious_.jpg

If you try the 'go' button on (nefarious)mobyload3 you'll get the robot (crank?).
With Multimodel button ('MM') you'll get Nefarious, too. (As a separate model.)

shak-otay, Sept. 2013

[](http://www.pic-upload.de/view-20770669/Nefarious_.jpg.html)

[](http://www.pic-upload.de/view-20770674/uvs_3dsmax_versa_blender.jpg.html)


edit: for level terrains you might try using hex2obj from this thread:
[viewtopic.php?f=16&t=10761&hilit=ratchet&start=45](http://forum.xentax.com/viewtopic.php?f=16&t=10761&hilit=ratchet&start=45)
post as of Sun Sep 07, 2014 2:04 pm
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-01T09:36:23+00:00
- Post Title: [release] Ratchet & Clank PS3 model extractor

Some models from rac1engine.ps3:

[](http://www.pic-upload.de/view-20883984/rac1_level.jpg.html)

[](http://www.pic-upload.de/view-20883980/rac1engine_1st_model.jpg.html) [](http://www.pic-upload.de/view-20883981/rac1_Model_atEnd.jpg.html)
[](http://www.pic-upload.de/view-20883983/rac1engine_model.jpg.html)[](http://www.pic-upload.de/view-20883982/rac1_-glider-.jpg.html)

Don't have this game. But I think these models (except the sphere level, maybe) exist as separate files, too?
So it doesn't seems worth to waste time on a universal engine file extractor.
## Post #3
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-10-02T04:43:55+00:00
- Post Title: [release] Ratchet & Clank PS3 model extractor

In R&C1 the models can only be found in those engine.ps3 files, except for ratchet's ships. His 4 ships are the only models that can be found in separate smaller files.
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-02T10:13:03+00:00
- Post Title: [release] Ratchet & Clank PS3 model extractor

> Reply from shakotay2
>
> Some models from rac1engine.ps3:



 


Don't have this game. But I think these models (except the sphere level, maybe) exist as separate files, too?
So it doesn't seems worth to waste time on a universal engine file extractor.

See if you can find the level geometry from what I have read and quoting Insomniac before the ps3 era 

> Intermediate file format –previously we had used Maya files directly.This helps us isolate our dependence on Maya while also improving performance
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-23T00:48:18+00:00
- Post Title: [release] Ratchet & Clank PS3 model extractor

I made a mesh extractor for simple formats, hex2obj (view link in my sig):

This is a result for one of the models in racengine.ps3:
[](http://www.pic-upload.de/view-21103325/racEngine.ps3.jpg.html)
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-08-09T08:11:40+00:00
- Post Title: [release] Ratchet & Clank PS3 model extractor

> Reply from shakotay2
>
> Rachet&Clank_extractor.zipcan you reupload it somewhere?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-09T09:09:02+00:00
- Post Title: [release] Ratchet & Clank PS3 model extractor

well, I need to check the exe file before. Virustotal tells me there's two threats:
Bkav W32.HfsIemusi.CA2C 	20180807
Qihoo-360 HEUR/QVM02.0.Malware.Gen 20180809 

The later is known to me for giving me false positives on some of my codeblock created exes.
But two alarms is one too many, I guess.
