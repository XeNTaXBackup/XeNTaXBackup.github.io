## Post #1
- Username: PockyWitch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 20, 2016 10:04 pm
- Post datetime: 2016-09-21T19:54:07+00:00
- Post Title: Dead Rising 1 (PC) Normal Maps

Hello everyone
over the last few days I managed to get most .tex files converted into either .dds or .bmp, but I cannot figure out in which format the normal maps are stored.
Most capcom games seem to use some sort of DXT, whereas DR1 seems to be NOT using DXT. Tried a lot of things.

Here's a description of the header of  the file
idstring "TEX\x00"
get VERSION short 
get PADDING byte # Most DXT1 files have this set
get MIPMAPS byte
get WIDTH long
get HEIGHT long
get null long
get SIGN long # "DXT1" "DXT5", basically the type of file. 

(All little endian)

Here's a zip with 2 normal maps in .tex format. Maybe one of you can figure out what kind of format it is. It's (I think) the only texture format I'm still missing.
[http://team-s4s.de/screens/DR1_Normalmaps.zip](http://team-s4s.de/screens/DR1_Normalmaps.zip)

If it's any help, if I extract it like a bmp with 16bit I can atleast get it to load in photoshop. Weird artifacts though, so not even toying around with the channels fixes it.

Regards,
Pocky
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-09-22T04:17:00+00:00
- Post Title: Dead Rising 1 (PC) Normal Maps

Capcom's TEX format is well known and used across a variety of their games including Resident Evil 5/6 or Devil May Cry 4. To my knowledge the files are always DDS with a custom header. I suggest looking at available Resident Evil tools as they should work.

Cheers.
## Post #3
- Username: PockyWitch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 20, 2016 10:04 pm
- Post datetime: 2016-09-22T11:51:01+00:00
- Post Title: Dead Rising 1 (PC) Normal Maps

They don't, I tried them already. And it's not always DDS, I already wrote scripts to handle both DXT1 and DXT5 and also the RGBA8888 files. It's the normal maps that seem to be using some sort of RGB format that I cannot comprehend.
## Post #4
- Username: PockyWitch
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-09-22T17:54:58+00:00
- Post Title: Dead Rising 1 (PC) Normal Maps

Try dump a texture from the vram and compare the data to the raw tex files.
## Post #5
- Username: PockyWitch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 20, 2016 10:04 pm
- Post datetime: 2016-09-22T23:46:52+00:00
- Post Title: Dead Rising 1 (PC) Normal Maps

I finally got one extracted. Just had to a 16bit (8.8, 2 channel) DDS header to it and it opens and looks perfectly fine in Photoshop. Just gotta figure out how to save these again, because saving it in 8.8 for some reason brightens them up, although this might be a bug in the nvidia plugin.

Thanks for the tip with the VRAM. Having the file from the ram helped me compare it.
