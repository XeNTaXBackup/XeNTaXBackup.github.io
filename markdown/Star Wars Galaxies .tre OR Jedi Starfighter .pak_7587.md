## Post #1
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-10-29T05:16:44+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

I've been burning my head up for a few days trying to get my hands on the model of the Havoc/Scurrg H-6 Prototype Bomber from one of the following Star Wars games:
-Star Wars: Galaxies
-Star Wars: Starfighter
-Star Wars: Jedi Starfighter

My attempts have been... Less than fruitful so far. I would just try to make the model, but my 3d modeling skills are nowhere near good enough to re-make such a wonderful ship to any degree of accuracy...

I've found that Star Wars: Galaxies' .tre files are impossible to open starting at patch 18, at least for me they are... Maybe you guys found something out that I didn't find on this message board. From what I could find, the ship is probably in the .tre for patch 20, but I'm not entirely sure.

The .pak files from the second and third seem to be impossible to open. I opened one in a hex editor and the first words I saw were "Europa Pack File", tried doing searches on that and other with no helpful information found... I also found the file names for what I was looking for, but didn't know what to do with those names... Most of what I found on my web searches were message board threads from 2004-2007 that were full of dead links, tools exclusively for extracting audio, and/or tools for making copies of PS2 games without actually extracting the files I was trying to get. I found one tool that seemed like it was what I needed, but I didn't understand it and couldn't find instructions on how to use it.

The tool is called the "Ultimate Extractor" and it makes no sense to me because I can't find any sites with the info I need. The program needs something called an "Address Table" and a "Name Table", 8 character hex address for each field. All attempts to figure this program out have resulted in said program crashing because I have no idea what I'm doing.

I'm not asking someone to pop open the archive files and e-mail me what I need (though that would be nice, wouldn't it?), I just want to know if anyone can explain to me how to open either the .pak files from Star Wars Starfighter or Jedi Starfighter or open the ERT6000 .tre files from Star Wars Galaxies so I can extract the files myself. Preferably the Galaxies one though, as that has the newest model and texture.

This is really frustrating, I don't plan to make a hobby of these skills, I just need to get my hands on the Scurrg H-6 model for a personal project then I'm done poking into these archives... Too stressful trying to deal with all of these strange formats. I seem to always pick things that are impossible to get and don't realize it until it's too late.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-10-29T08:01:06+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

> Reply from Arvex
>
> -Star Wars: Galaxies
Use Tre Explorer:
[http://code.google.com/p/swgemu-visual- ... e&can=2&q=](http://code.google.com/p/swgemu-visual-reconstruction/downloads/detail?name=TRE%20Explorer.exe&can=2&q=)
[http://forum.modsource.org/index.php?topic=33.0](http://forum.modsource.org/index.php?topic=33.0)
Update:
 http://www.modthegalaxy.com/forums/thre ... all-update
https://github.com/MTGUli/TREExplorer

If you can't get into a *.tre file directly then you should be able to get into it indirectly through the *.toc files then extract what you need. You'll be extracting model formats that need to be converted to usable ones.

The max script in this post supposedly imports *.mgn model files and has been confirmed to work with 3ds Max 8 but i have not tried it.
[viewtopic.php?p=16587#p16587](http://forum.xentax.com/viewtopic.php?p=16587#p16587)

fatduck also created a max script for importing the *.msh and *.mgn model files:
[viewtopic.php?p=20914#p20914](http://forum.xentax.com/viewtopic.php?p=20914#p20914)

Unwrap 3d is not free but can import the model files(*.msh,*.mgn) from this game too.
[http://www.unwrap3d.com/u3d/index.aspx](http://www.unwrap3d.com/u3d/index.aspx)

There's also a *.msh import/export plugin for Blender(tested with version 2.57) which imports geometry only(no UVs)
[https://github.com/apathyboy/SWGANHBlenderAddons](https://github.com/apathyboy/SWGANHBlenderAddons)
[http://www.swganh.com/anh_community/vie ... =21&t=1001](http://www.swganh.com/anh_community/viewtopic.php?f=21&t=1001) 



> Reply from Arvex
>
> -Star Wars: Starfighter
-Star Wars: Jedi Starfighter
Extract files from *.pak with sfdepak-1.0:
[viewtopic.php?p=23730#p23730](http://forum.xentax.com/viewtopic.php?p=23730#p23730)
usage:
sfdepak.exe resource.pak

Use the same utility to extract the model parts etc from *.pmdl
usage:
sfdepak.exe somename.pmdl

3d Object Converter can import *.pmdl files directly but not accurately.
(this project should really be revived since the model's UVs aren't read)
[http://web.axelero.hu/karpo/](http://web.axelero.hu/karpo/)


Local backup of sfdepak-1.0 since the website is down:


 sfdepak-1.0.zip
(16.58 KiB) Downloaded 40 times



If you run into *.tex files that need converting to *.tga the utility here will do the job:
[viewtopic.php?p=20278#p20278](http://forum.xentax.com/viewtopic.php?p=20278#p20278)
## Post #3
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-10-29T14:03:58+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

Thank you, I saw a thread on the Starfighter unpacker, but the links on it were both dead... The backup link really helped. Now I just need to figure out what I'm going to do now that I have the mesh... That 3d object converter has a price tag way too steep for me and the trial won't convert models, only view them. Also, the tool seems to work on the PS2 version of Jedi Starfighter, as I used it on my copy of Jedi Starfighter and got everything, just not sure if these files are valid yet.

As for TRE Explorer. I already tried that program, won't open anything past 17 and I'm fairly certain the model I need is in update 20. What's a TOC file and how do I make/get one? I don't see any in my SWG install.

After a search of the Star Wars Galaxies directory for ".toc," I found two TOC files:
-sku0_client.toc
-sku1_client.toc

Are these supposed to help me open all of the .tre files? Or are these two each linked to a .tre file of similar naming?
## Post #4
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-10-29T15:01:10+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

Managed to get the 3d object converter tool to save them in .3ds format... but I can't seem to import them into Blender for some reason.
## Post #5
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-10-29T21:06:28+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

Progress so far: (if it can be called that)

Galaxies:
-Can't get to any files related to the Havoc.

Jedi Starfighter:
-I have a copy of the .msh, .pmdl, and .mdl files for the Havoc and even got 3D Object Converter to convert to .3ds files, but the .3ds files are unreadable by any program I own.
-I opened them in Unwrap3d and got an error saying: "Not a 3DS model file. Primary ID not found"
-I have successfully converted the texture and have recolored and added the decal I wanted to it. Next step is acquiring the textures to the parts I'm adding. (a LOT easier because most of those ships aren't in SWG's ERT6000 files)

Thanks for your help, here's a preview of what I'm working on.
[http://i74.photobucket.com/albums/i271/ ... rg-256.png](http://i74.photobucket.com/albums/i271/the_peacemaker/Jurris-Scurrg-256.png)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-10-29T22:31:14+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-10-29T23:10:15+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

Wait... You mean someone else made one and I just couldn't find it? WHAAAAT?!!!! ALL THIS SEARCHING AND DATA MINING HAS BEEN POINTLESS!?

Okay, done raging.

There's supposed to be a flyable H-6 (called the "Havoc Starfighter", which is wrong) in the data files. The one on the pedestal is not the one I'm looking for, but it might work. I was hoping to get the flyable one because it has higher resolution textures and a more detailed model.

I suppose the community made one would probably be better because then I can ask permission to use it. It's for private use, but I don't think any game company likes data mining... Even if it was for another Star Wars game. I was going to see about putting this ship into Star Wars: X-wing Alliance and making a modified version for another project.

Never mind, I just looked at the file resolution on the texture on the "Nym's Starfighter Model" (the name of the in-game item that's to)... It's actually the same. In fact, it looks like the exact same texture file just re-arranged. I just have to remake my modifications on that texture file and I think I'll be set.
## Post #8
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-02T15:50:52+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-11-02T19:06:55+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

Wow, that is a better model. I seem to be having trouble getting the texture to load, though... It also seems to be missing textures around the cockpit. Thank you, though.

[http://i74.photobucket.com/albums/i271/ ... er/Huh.png](http://i74.photobucket.com/albums/i271/the_peacemaker/Huh.png)
Not sure what's going on here.

Also, my original plan for the top gun seems to have backfired along with two back up plans... I was trying to get the turret from the YT-1300 for it, but the model is proving difficult to extract as TRE Explorer crashes when I do an "Export File Chain" on anything and TRE Archiver doesn't seem to want to do anything I want it to in the first place.

EDIT: Okay, I got it to use my already made texture and it looks pretty good this way.
## Post #10
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-02T22:25:31+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

the .DDS use an alpha channel .. the invisible part is the alpha channel ^^
convert it in .jpg if you want
## Post #11
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-11-02T23:42:18+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

What tool would you recommend for that? I tried one and it was useless. It closed every time I selected a .dds file for it to convert.
## Post #12
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-03T06:42:26+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

> Reply from Arvex
>
> What tool would you recommend for that? I tried one and it was useless. It closed every time I selected a .dds file for it to convert.

i will convert them for you as soon as i'm back at home ....
the alpha channel could be use as gradient to insert the red color with photoshop




your picture ...



for the canopy , it's just a basic texture with reflexion .. a glass
## Post #13
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-11-03T13:15:47+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

I might be able to convert it myself, I found a plugin for Gimp 2.6 that should allow me to open .DDS files. However, it doesn't seem to work for me. I don't know what it is, but I seem to follow instructions and things still don't work.

As for the canopy, I know why that loaded plain white and already fixed that, it didn't have a valid texture mapped to it at all. It's supposed to be mapped to a separate texture file for starship glass, but it couldn't find that file as it isn't there. I just mapped that to a black spot on the texture for now. If I suddenly am not fine with a pitch black canopy in the future, I'll retrieve the SWG glass texture and use that. I know what it's called and can find it pretty quickly. What's the resolution on that texture you sent anyways? The file size seems to suggest it's a higher resolution texture.
## Post #14
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-06T16:33:53+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-11-09T13:10:37+00:00
- Post Title: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

Thank you. Looks like I'll have to download it later, Sendspace's servers are acting silly right now.

I think I got it to read the texture finally, but I can't edit it since the .DDS plug in for GIMP isn't working.

Can you recommend a .DDS converter that actually works? Preferably one that can convert into .PNG.
## Post #16
- Username: Arvex
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Oct 29, 2011 6:44 am
- Post datetime: 2011-11-11T21:57:06+00:00
- Post Title: Re: Star Wars: Galaxies .tre OR Jedi Starfighter .pak

Alright! I got the plugin to work. I opened the texture files you sent me in Gimp. The file has all of the red parts of the ship's texture, but nothing else. It also has several "mipmap" layers that are just smaller versions of the red parts of the texture.

Not sure if this is just because I don't understand the .DDS format or if there is another texture file that is supposed to go with it?
