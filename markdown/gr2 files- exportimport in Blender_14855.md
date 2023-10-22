## Post #1
- Username: Amfora
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 31, 2016 3:43 pm
- Post datetime: 2016-08-14T08:55:31+00:00
- Post Title: gr2 files- export/import in Blender

Hi guys,
I find plugin to Blender or gr2 files' converter, Uncle Google disappointed. 3d max is too expensive, Nexus Buddy is for Win10 and perhaps only for Civilization, links to grnreader98 aren't working. Maybe does someone have this last or something?
Dungeon lords and other games uses this format  This is unpopular theme in the net, you are the last hope
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-14T11:16:39+00:00
- Post Title: gr2 files- export/import in Blender

why not use search function of this forum?

[viewtopic.php?f=16&t=12374&p=101672&hil ... er#p101668](http://forum.xentax.com/viewtopic.php?f=16&t=12374&p=101672&hilit=grnreader#p101668)
(post as of dec. 12th, 2014, 12:00 am)
## Post #3
- Username: Amfora
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 31, 2016 3:43 pm
- Post datetime: 2016-08-14T12:30:34+00:00
- Post Title: gr2 files- export/import in Blender

Yeah, right, I forgot write about this way... Unfortunatetly Blender describe error, when I import the smd file. Maybe the problem is version of Blender(I have 2.72) or my smd plugin(or grn model is broken)... Could you open one smd file?
smd:
[http://www.mediafire.com/download/59wba ... GICIAN.smd](http://www.mediafire.com/download/59wba65qg77ajh2/MAGICIAN.smd)
smd from gr2:
[http://www.mediafire.com/download/ixo8e ... rn.gr2.smd](http://www.mediafire.com/download/ixo8edo3x5kuc48/grn.gr2.smd)
original version:
[http://www.mediafire.com/download/s13tp ... GICIAN.grn](http://www.mediafire.com/download/s13tpggoe3w6adp/MAGICIAN.grn)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-14T16:08:24+00:00
- Post Title: gr2 files- export/import in Blender

The Sourge Engine smd importer doesn't like extra blanks at lines' ends:
delete the blanks behind "end" and "skeleton" in the following lines and you're done.

80 "Spot01_shadow.Target" 77 
end
skeleton
time 0

You could try out Open Asset viewer which doesn't have the prob with the blanks (right side of app. picture).

Both smds load for me then:



Magican_smd.jpg (83 KiB) Viewed 278 times
## Post #5
- Username: Amfora
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 31, 2016 3:43 pm
- Post datetime: 2016-08-15T12:59:06+00:00
- Post Title: gr2 files- export/import in Blender

I'm sorry, I don't understand... Do you mean about Source SDK from the Steam(concretely smdimport.mel) or plugin to Blender(import_smd.py)? I didn't find the Open Asset viever, neither Asset viever. Open Asset open the smd, but doesn't export in this format
