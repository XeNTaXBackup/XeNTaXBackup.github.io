## Post #1
- Username: LostMC
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 15, 2010 5:17 am
- Post datetime: 2011-07-18T19:27:21+00:00
- Post Title: Star Wars The Force Unleashed II Endor DLC [X360]

Hello. 
Can someone help me with extracting .gto and .dds files from this DLC for TFU II?
HxD shows all files and directories, but I can't wrote .bms script by myself, and Dragon Unpacker even finds some .png with HyperRipper, but doesn't find any .dds, and doesn't support any .gto search.  
And, yeah, I tried just to open it with any .zip viewer. 
Here is one of three DLC files, the other two are too big to upload them with my internet connection (400MB and 1GB):
[http://www.mediafire.com/?aa5gbj344g32pwm](http://www.mediafire.com/?aa5gbj344g32pwm)
Thanks in advance.
## Post #2
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2011-07-19T00:05:10+00:00
- Post Title: Star Wars The Force Unleashed II Endor DLC [X360]

The pak file is a zip, so add a .zip extension to it. Then open it up and find a gto file and extract it. The gto file needs to be renamed to a .zip again. Now open it and take the file out and add the .gto extension to it. There's a tool with a plugin you can get on this site. [http://oasis.xentax.com/](http://oasis.xentax.com/)
## Post #3
- Username: LostMC
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 15, 2010 5:17 am
- Post datetime: 2011-07-19T10:12:33+00:00
- Post Title: Star Wars The Force Unleashed II Endor DLC [X360]

I tried... Adding ".zip" to archive doesn't works.
## Post #4
- Username: kukuasir
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 06, 2010 12:04 pm
- Post datetime: 2011-07-30T07:48:21+00:00
- Post Title: Star Wars The Force Unleashed II Endor DLC [X360]

Hi,LostMC
You can open this file with hex editor,
search "APak" (0xf000) ,form this offset to the EOF save as a new file(eg a.pak)!
look this topic
[viewtopic.php?f=10&t=6505&hilit=force+unleashed](http://forum.xentax.com/viewtopic.php?f=10&t=6505&hilit=force+unleashed)
you can use the aluigi's script to unpack the a.pak file.
but when I see the the unpacked file,all of file is different with the PC version file,may be these file have been encrypted.
You can unpack other big file and send the gto file to me,I will see it!
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-07-31T04:40:08+00:00
- Post Title: Star Wars The Force Unleashed II Endor DLC [X360]

@kukuasir
Thanks that worked to an extent, i was able to break down the original file into 2 pak files since there were 2 instances of APak within it, then i used [aluigi's BMS script](http://forum.xentax.com/viewtopic.php?p=53353#p53353) to pull the files from the pak files but the resulting file size didn't look correct.

The original file was 27.5 MB
The first instance of APak which i named APak.pak was 26.8 MB
The second instance of APak which i named APak2.pak was 568 KB
The total size of the files extracted from both pak files was 5.76 MB   

There were no models (gto) or textures (dds) extracted but gto files are present in the original file and can be found in a hex editor. 
In conclusion it looks like [aluigi's BMS script](http://forum.xentax.com/viewtopic.php?p=53353#p53353) didn't extract everything from the paks and it may need to be modified.

Updated version
[http://aluigi.altervista.org/papers/bms ... ars_lp.bms](http://aluigi.altervista.org/papers/bms/star_wars_lp.bms)
