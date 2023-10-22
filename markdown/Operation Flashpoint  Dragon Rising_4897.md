## Post #1
- Username: templargfx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2009 4:46 pm
- Post datetime: 2010-08-18T04:28:25+00:00
- Post Title: Operation Flashpoint : Dragon Rising

Hi all, Hopefully someone here can help me, because I have no idea where to even start!

Operation Flashpoint dragon rising was a for-the-lack-of-a-better-word badly made game, there are many issues, which myself and others in the game's community are slowly finding ways to fix!

the next challange, and by far the biggest in end-effect is textures, until this morning I have not been able to extract the textures properly, I have attached an example STF texture file from the game, from what little I have been able to glean from CM themselves, this file format is a relatively simple "container" and should be easy for someone with the knowhow to make a converter of some type

[http://filebeam.com/6e3b9961af631b365be94d93c2a4b307](http://filebeam.com/6e3b9961af631b365be94d93c2a4b307)
C_BODY_SHARED_DIF.STF (IN RAR)

this particular image is extremely important to get editing access too. Int he game, any unit passed 300m from the player uses the same texture, this one. FOR BOTH ARMIES. meaning you cant tell good from bad at a distance, if I can make 2 hue's of this file, I can then edit the asset file to have the game use a different texture for each army on this "shared" level of detail. I have tried using another texture already int he game, and it works, but the UV mapping is different
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-08-18T08:01:54+00:00
- Post Title: Operation Flashpoint : Dragon Rising

If this attachment resembles what you think is the actual texture then i have some very good news for you. 
Its DDS/DXT1 data with an own header. so in other words, my mom could do this.
[c_body_shared_dif.JPG](https://xentaxbackup.github.io/file/3347_c_body_shared_dif.JPG)
## Post #3
- Username: templargfx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2009 4:46 pm
- Post datetime: 2010-08-18T08:19:54+00:00
- Post Title: Operation Flashpoint : Dragon Rising

Could you explain to me what I need to do to get photoshop to load it? is it as simple as installing Nvidia's DDS plugin?  (will try that now)
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-08-18T08:30:12+00:00
- Post Title: Operation Flashpoint : Dragon Rising

First, Yes, you need Nvidia DDS Plugins.
Secondly, open the STF file in a hexeditor and delete their header until you reach the DDS data.
the DDS data starts at 2048, so delete everything before that, then recreate a DDS header (example in the zip) before the DDS data,
and save. this should now be openable as a DDS image. both the finished DDS and DDS header only are included in the zip
for you to try for yourself.
[files.zip](https://xentaxbackup.github.io/file/3348_files.zip)
## Post #5
- Username: templargfx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2009 4:46 pm
- Post datetime: 2010-08-18T08:57:13+00:00
- Post Title: Operation Flashpoint : Dragon Rising

thanks heaps, it works wonders!

would you have any idea what format the DDS image is in? If I edit the DDS and export using DXT3 or 5 it shows as black (even though its mostly white as a test)

I'll keep playing!
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-08-18T09:00:09+00:00
- Post Title: Operation Flashpoint : Dragon Rising

Ahhhhh, for exporting into the game you would need to copy over the header of the first STF file, and then instead remove the DDS header from your manipulated DDS file,
and put the original header back again, that should work
## Post #7
- Username: templargfx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2009 4:46 pm
- Post datetime: 2010-08-18T09:05:02+00:00
- Post Title: Operation Flashpoint : Dragon Rising

I tried that, but when in-game, the units are black (accept for a small section on the leg, which is completely white)

I have tried DXT1 (like in the header) but that needs to be a multiple of 4, which the image is not. DXT3 and 5 both show as black in-game. If I attempt to export to the "palette" option but that crashes photoshop

EDIT

got those the wrong way around.

DXT1 and 3 export, but DXT5 reports the x4 error
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-08-18T09:43:56+00:00
- Post Title: Operation Flashpoint : Dragon Rising

You know what? I just noticed something, its not 128x64 in size. the DDS header is wrong hahahaha, the image seems to be 128x128,
so half of the imagedata gets lost with that DDS header.
