## Post #1
- Username: Spyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 07, 2012 10:21 pm
- Post datetime: 2012-01-07T14:40:26+00:00
- Post Title: Arc Rise Fantasia Texture Editing

Hi.  I'm trying to edit some textures from arc rise fantasia and put them back in the game and play it but it freezes the game whenever it gets to where it would load the edited texture.  I've edited the PNG files and put them back in the .bress then back in the .vol then back in the .iso.  I've also tried making the edited PNG file the same size(bytes) as the original.  So I imagine there must be something somewhere telling the game that the texture doesn't match up.  Does anyone know anything about this?  Thanks.
## Post #2
- Username: Spyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 07, 2012 10:21 pm
- Post datetime: 2012-01-07T19:24:04+00:00
- Post Title: Arc Rise Fantasia Texture Editing

Nevermind.  After a lot of trial and error, I got it.  Exporting the texture as .tga and importing as .tga did the trick.
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-01-12T11:44:36+00:00
- Post Title: Arc Rise Fantasia Texture Editing

how did you exported/imported it as tga?
## Post #4
- Username: Spyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 07, 2012 10:21 pm
- Post datetime: 2012-01-14T13:27:26+00:00
- Post Title: Arc Rise Fantasia Texture Editing

I used Brawlbox v.65 to export/import the textures.  The actual wii doesn't seem to like having stuff changed as 99% of the time it freezes for me.  But the Dolphin emulator runs it fine even with changes to the textures.
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-01-16T17:24:43+00:00
- Post Title: Arc Rise Fantasia Texture Editing

Do you recalculated the offsets of the vol file after reinsterting something? VOLs contain size and offsets which needs to be changed accordingly.
This program will do the job: [http://www.romhacking.net/utilities/815/](http://www.romhacking.net/utilities/815/)
## Post #6
- Username: Spyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 07, 2012 10:21 pm
- Post datetime: 2012-01-17T13:28:26+00:00
- Post Title: Arc Rise Fantasia Texture Editing

Yeah thats the program i've been using for the .vol files.
## Post #7
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-01-18T19:44:30+00:00
- Post Title: Arc Rise Fantasia Texture Editing

I just tried to edit the texture of a model and it worked fine on my Wii. Here is how I did it (in an overly detailed explanation):
Used Wiiscrubber140 to extract the vol-file of the character (under \Char)
Extracted all files of the vol with ARFX (was too lazy to rightclick the right one^^).
Opened the brres file with BrawlBox v0.65b, clicked the texturefolder and right clicked the texturefile to export it as PNG.
Edited the exported PNG in mspaint (any other iamgeeditor should work too) and saved it.
Opened the brres file in Brawlbox again and choose replace this time (rightclick on texture), selected the edited PNG and saved the brres file (File->Save).
Reinserted the file into the vol with ARFX (rightclick the corresponding file and choose insert, select the edited brres and hit ok)
Inserted the edited vol with Wiiscrubber again.

The only mistake you could have done is inserting into a different file than you edited.

PS: You can use brresviewer to verify your changes.
## Post #8
- Username: Spyder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 07, 2012 10:21 pm
- Post datetime: 2012-01-20T05:18:24+00:00
- Post Title: Arc Rise Fantasia Texture Editing

Thats pretty much the same exact thing I've been doing except I used Gimp to edit the textures instead of Paint and I found that exporting/importing as .tga worked for the wii sometimes.  I also preview them in brresviewer too and they look fine.  I appretiate you taking the time to help me out.  Maybe when I'm saving them the layers or color counts are changing or something.
