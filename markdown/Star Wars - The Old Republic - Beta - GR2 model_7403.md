## Post #1
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-09-23T14:00:11+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-09-24T10:42:56+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

i have test granny 3D viewer for GR2 format .. don't work
## Post #3
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-09-25T21:54:44+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

SWTOR uses a highly modified version of "HeroEngine" ( [http://en.wikipedia.org/wiki/HeroEngine](http://en.wikipedia.org/wiki/HeroEngine) ). I dont have time to look into it right now but that should at least be helpful as a starting point. Cant wait til December 20th  (SWTOR release)
## Post #4
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-09-27T17:28:18+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

The model and animation system used is radgametool's "Granny 3D" ( [http://www.radgametools.com/granny.html](http://www.radgametools.com/granny.html) ), however using the Granny3D demo I was unable to open the files. The model format could be very modified like the engine is, or the Granny3D demo is just too limited or old a version to open SWTOR's model version. I'll try to get my hands on a new version and see if they can be opened, feel free to beat me to it if anyone already has a newer version.
## Post #5
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-09-30T07:39:51+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

original model done with 3dmax, with a script converter to .GR2 format ... information from dev news group
## Post #6
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-09-30T20:55:52+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

--removed
## Post #7
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-09-30T22:26:40+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

Can you tell us what version the old sdk is please?
## Post #8
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-09-30T23:11:55+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

> Reply from XHD
>
> Can you tell us what version the old sdk is please?
2.8.49.0
## Post #9
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-10-01T03:41:28+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

Well I found the only link to the version of the SDK you're referring to, on a german site. However it appears the download is currently down, host site is under maintenance or something :/
## Post #10
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-01T09:05:36+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

> Reply from delium
>
> i tried to load the model with an old granny sdk. but the textures are missing and animations won´t work.
here is a wireframe screen of your uploaded sample

don´t ask after source, if you know c++ google the sdk and try yourself

thx for your reply , but if i post here for help .. that's clear i don't know C++
i will search the SDK and see 

by the way, thx for your sharing
## Post #11
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-10-01T12:50:17+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

--removed
## Post #12
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-01T14:01:37+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

thx alot !!

work fine for me at this time ...



the texture isn't store into .gr2 file, just coordonates for mapping

edit: after try much more gr2 files, i see some wrong vertex orientation and some .ms crash
## Post #13
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-10-01T19:30:33+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

how are you managing to extract files from the .tor files? using the bms script as well as easyMYP from this thread [viewtopic.php?f=10&t=7186](http://forum.xentax.com/viewtopic.php?f=10&t=7186) , I'm only enable to extract certain files correctly, such as .dds, however they dont have correct file names either.
## Post #14
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-10-01T23:36:42+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

Just want to point out that you can probably use the granny2.dll located in the "Star Wars - The Old Republic\he601\retailclient" folder.
Also some models cause max to crash if you try to import them, usualy if they're 5mb or larger (after being converted to.ms files of course). I'm not sure if its max having an issue with these larger files or if its Delium's converter. Just something to look into, heres a few files I had issues with:
veh_imp_friggate.gr2 (3mb GR2, 45mb MS)
veh_rep_troop_transport_landed_wingsdown.gr2 (1.2mb GR2, 36mb MS)
veh_neu_tat_sandcrawler.gr2 (1.7mb GR2, 14mb MS)
As you can see there is a huge size difference between the GR2 files and their MS counterparts, so I dunno if thats causing an issue.
I would upload them but the forum is having issues with attachments. Thanks for all the work so far though Delium
## Post #15
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-02T06:20:56+00:00
- Post Title: Star Wars - The Old Republic - Beta - GR2 model

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-10-02T20:06:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

yeah I've been using debug3.2 (easyMYP) with the hash list, just didnt know if there was another tool out there.
## Post #17
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-04T08:06:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

XHD look on your PM

other tool, i don't know too
## Post #18
- Username: Nightstorm1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 12, 2011 4:18 am
- Post datetime: 2011-10-07T22:58:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Has anyone identified or been able to extract audio?  Specifically the Lightsaber sound effects?
## Post #19
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-08T08:04:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Nightstorm1
>
> Has anyone identified or been able to extract audio?  Specifically the Lightsaber sound effects?

i will look this week end .. but only 17% of the files are identified ... we wait an update of the hashlist
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-10-08T18:09:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Does anyone have a release build of EasyMYP 3.2 for those of us who don't have Visual Studio products installed? With debug3.2 i can open the *.tor archives for viewing the list but the contents can't be extracted without JIT errors disrupting the process.

Source:
[http://code.google.com/p/easymyp/source ... vn%2Ftrunk](http://code.google.com/p/easymyp/source/browse/?r=71#svn%2Ftrunk)

EDIT
Nevermind, the JIT errors only seem to occur when trying to extract single files from the tor archive, when extracting all files it works as expected.  




> Reply from XHD
>
> delium wrote:here is a very simple converter from gr2 to maxscript ... but without granny2.dll, i think it´s not legit to share it...
..you can probably use the granny2.dll located in the "Star Wars - The Old Republic\he601\retailclient" folder...
Yes this works, thank you!
## Post #21
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-09T06:44:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

thx Acewell
test with all granny2.dll, same function
my pb of vertex corruption come from the conversion to .obj into 3dmax 2010
works fine to .3ds
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-10-15T03:36:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> ...some models cause max to crash if you try to import them, usualy if they're 5mb or larger (after being converted to.ms files of course). I'm not sure if its max having an issue with these larger files or if its Delium's converter. Just something to look into...
mariokart64n addressed this same issue in [THIS](http://forum.xentax.com/viewtopic.php?p=46279#p46279) post. He created an .ms script that opens the *.gr2.ms script files which imports the objects one at a time to work around the memory/crash problem but i have not had success with it yet, maybe it needs to be tweaked a little to work with these newer gr2.ms files.
## Post #23
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-15T06:43:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Nightstorm1
>
> Has anyone identified or been able to extract audio?  Specifically the Lightsaber sound effects?

i have see some .wav and .ogg files .. 
.wav files aren't into the hashlist at this time

both files, every times i tried to play them, crash ...
## Post #24
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-17T15:07:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from AceWell
>
> ...some models cause max to crash if you try to import them, usualy if they're 5mb or larger (after being converted to.ms files of course). I'm not sure if its max having an issue with these larger files or if its Delium's converter. Just something to look into...
mariokart64n addressed this same issue in THIS post. He created an .ms script that opens the *.gr2.ms script files which imports the objects one at a time to work around the memory/crash problem but i have not had success with it yet, maybe it needs to be tweaked a little to work with these newer gr2.ms files.

script tested...

under 8 Mo MS, the gr2convert work ..
the other script works betwen 8 Mo and 11 Mo MS
after upper  ... crash
## Post #25
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-10-19T03:32:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Has there been any luck with this? Possibly with getting any of the Sith exported to OBJ or 3DS yet?
## Post #26
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-10-26T11:23:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I've had partial success. I can get some models to export (mostly) intact, others though - like Malgus - end up with a bunch of completely missing polygons. That's using grnreader98, which so far has been the only way I could get meshes into Max. It converts to both MS and SMD. For some models the MS script works fine, for others it crashes Max. In those cases, the SMD is the only option, but they are the ones missing the polys. Interestingly, it seems like those are the ones that also pop up a warning in grnreader98 saying "indices don't start at zero". I've tried to use the script linked to in this thread to load the MS versions, but it doesn't work. It complains about undefined variables and about being unable to convert undefined values to floats.

I also tried evegr2toobj.2, but that resulted in a bunch of verts with one co-ord value listed as "-1.#QNAN0", which results in a non-usable mesh.
## Post #27
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-10-26T12:02:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

can anyone upload a npc/player model with animations? i don´t have access to the beta client
## Post #28
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-10-26T12:43:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

You don't actually need to be in the beta to download the client - just to play and have it download patches.

It doesn't seem like we have the filename hashes for much in the way of animations yet. All I'm seeing are a couple of JBA and MPH files and a few XML files.
## Post #29
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-10-26T13:59:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Hmm if you can get Malgus exported to OBJ in any way, I can go in with Meshlab and Milkshape and remodel the missing polys. Is it just little spots or whole sections missing though?
## Post #30
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-10-26T14:11:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Half (or more) of his face is missing, not to mention various other areas. It's not really practical to remodel.

[](http://i.imgur.com/5bOvI.jpg)
## Post #31
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-10-26T15:43:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Hmm I'd be willing to give it a shot, does'nt look that bad to me. I've fixed worse. Much worse.
## Post #32
- Username: Dionix187
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 28, 2011 4:40 pm
- Post datetime: 2011-10-28T08:56:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The contents of this post was deleted because of possible forum rules violation.
## Post #33
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-10-28T11:19:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Thanks for the updated hash list. The one I had only produced about 72,000 named files in the Resources folder. Re-extracting now to see what goodies I've been missing out on. I already know I was missing certain textures for some models.

Oh and an updated EasyMYP too. I'm still using the TOR 3.3 version.
## Post #34
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-10-28T16:52:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I know Malgus and one of the Havok Troopers would be real nice to have 3D Models for, maybe a Acolyte as well. Hopefully with this new program it might have better results ripping from the game.
## Post #35
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-10-29T05:53:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The problem is not the extraction from the game files, it's the conversion of the GR2s to a usable format.
## Post #36
- Username: Dionix187
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 28, 2011 4:40 pm
- Post datetime: 2011-10-29T07:43:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Tutorial: Converting Models / Importing to Milkshape

This tutorial covers converting the games model files into a format usable by Milkshape, as well 
as importing and applying a texture.

Assumptions:
I'm writing this based on the assumption that you already have the beta client and have extracted 
the archives using the newest hash file. If you don't know what that even means then head over to the Datamining the Beta-Client thread and start reading 

Tools/Files Needed:
Milkshape - [download here](http://chumbalum.swissquake.ch/ms3d/download.html) - This program isn't free, but there's a 30-day trial to get you started.
grnreader98 - [download here](http://tatooinebase.star-fleet.org/UPLOAD/grnreader98.v1.4.0.3.debug.rar) - extract this into it's own dir somewhere that you can get to easily (ex. c:\grnreader98)
3ds Max (Optional) - If you already have 3ds Max you should be able to use it instead of Milkshape, but you'll need an importer plugin ([download here](http://www.chaosincarnate.net/cannonfodder/cftools.htm)). Applying textures looks more complicated in 3ds Max though, but if you have it you probably already know that.

Finding The Model/Texture Files
And of course you'll need the actual model and texture files. To find these look in the folder you extracted the game archives to, then go to \resources\art\dynamic (there's some in other places, like \static, but the bulk of them are in \dynamic). The models are .gr2 files and the textures are .dds files.  

Find one of each that have matching filenames. *Note*: The dds filenames will have something like v01 or v02 after the model name, this usually means it's a different colour variation. Also look for textures that end in d, like "_d.dds". That d is important.

For this tutorial I used battledroid_m14x_a03.gr2 and battledroid_m14x_a03_v01_d.dds

Converting The Model For Milkshape

Copy your gr2 and dds files to the same directory as grnreader98. Then drag & drop the gr2 file onto grnreader98.exe (you can also run it from the cmd line, there might be more options that way). You'll get a few pop-ups asking if you want to export various things, just answer Yes to everything. When it's finished you'll now have a .ms file and a .smd file with the same name as your model.

Importing To Milkshape And Applying The Texture
*Click thumbnails for full size images.

[](http://nightrunnersguild.com/tutorials/1.jpg)
In Milkshape click File > Import > Halflife SMD. Browse to where your model is located and open the .smd file.


You'll get an SMD Import Box. Leave all the boxes checked and click OK. Milkshape will now start importing and loading your model. Some models can take a minute to load.

[](http://nightrunnersguild.com/tutorials/3.jpg)
You should now see your model and a few wireframe shots from different angles. You may have to move/rotate your model if it loads sideways or upside down. To rotate click & drag. To move the model around Ctrl+click & drag. To zoom in or out shift+click & drag. I haven't figured out how to rotate in a way to see the model from the side yet.

[](http://nightrunnersguild.com/tutorials/4.jpg)
When you have the model loaded and positioned where you want, click on the Groups tab on the control panel. Select your model in the list, then click the Select button.

[](http://nightrunnersguild.com/tutorials/5.jpg)
When you clicked Select your models wireframe should have turned from white to red.

[](http://nightrunnersguild.com/tutorials/6.jpg)
Now click the Materials tab. Select your model in the list. Below that you'll see a model of a grey sphere appear. I don't know what that's for so just ignore it. Below that you'll see 4 rectangular boxes, 3 say None and 1 has the name of your model. Click the box with your models name. My description sucks so look at the picture above if you're not sure. Browse to where your texture is located and open it. Now back on the control panel click Assign.

[](http://nightrunnersguild.com/tutorials/7.jpg)
If everything worked you should now have a fully textured model. If your model is still just a grey featureless blob then right-click it and make sure Textured is selected instead of Smooth Shaded. You can also click Maximize to display the model in a full size window.

Advanced Procedures & Other Topics
Although this tutorial ends here, there are other things to cover. Some models have extra textures for lights, glowing eyes etc. Some models aren't mapped properly and will look messed up . And on and on.

The hope is the end-user won't have to deal with all this stuff and we'll just have a self-contained model viewer that can read directly from the games archive files (ala Wow Model Viewer), but until someone makes such a program we're stuck with doing it by hand. I wouldn't expect to see a model viewer until after launch.

Finally, if you have any questions or comments, feel free to post them. All I ask is you please don't quote this whole post, just quote the relevant bits. Also try not to quote the thumbnails since that's just wasted bandwidth
## Post #37
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-10-29T08:31:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Yeah as I posted before, grnreader98 is not a 100% solution. For a large number of models it does not correctly convert them, resulting in all sorts of issues like missing polys, etc. Even for those it does convert correctly at first blush often have small errors if you go over the mesh with a fine tooth comb. A custom exporter is really required - there's no way around it.
## Post #38
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-10-29T16:20:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I use 3 programs to fix models. For game models I import them into Milkshape, which is'nt exactly free for 30 days, you can't export or save until you get a license. Which I have. Tehn I export to OBJ. Once I have the OBJ, I import it into Meshlab, export it to a STL File, then open it into NetFabb and the program will automatically fix models, For example if one side of the model has holes, it looks at the other side, and repairs the holes by copying what the opposite side of the mesh looks like. There has not been a 3D Model I can't fix in one way or another. 5+ years of experience working on 3D Models. If someone can get me a example SMD file that's broken or the Malgus SMD I'll show you that I can fix them.
Unfortunatly I don't have the SW:TOR Beta otherwise I would have already been working on this. But if I can get the SMDs I can fix them and upload the repaired models.
## Post #39
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-10-30T03:08:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

It's not about whether a model is fixable. I could do that myself, or hell even model some from scratch if I was so inclined, as no doubt could many people here. If people were interested in doing that they wouldn't be chasing an extractor in the first place.
## Post #40
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-10-31T02:46:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Part of the problems with the GR2 files is that the CRC is not correct for the file so GrannyViewer will not open it.
Unless you run a program that will correct the CRC.
This program will not open the file yet but it will correct the CRC so you can view it in the GrannyViewer.
[http://www.subsim.com/radioroom/showthread.php?t=188290](http://www.subsim.com/radioroom/showthread.php?t=188290)
It will ask for the SH5 folder but you can just pick anything for now.
All you want to do is correct the CRC and file size at this point.

If someone would be so kind as to give me a link to those GR2's that show missing or messed up verts on export?
I have several Beta Tools that do a very good job of exporting as obj files.

Regards.
## Post #41
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-10-31T03:13:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Test extracts send for evaluation.
## Post #42
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-10-31T05:59:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Well this was a lengthy process but i finally got it!   


I fixed the CRC with TheDarkWraith's GR2 Editor/Viewer
loaded the .gr2 into GrannyViewer
captured it from GrannyViewer with 3DVIA Printscreen
imported the 3dxml into 3ds Max 9 with KoichiSenada's importer
i hate working in 3ds Max so I exported as .xsi 
applied the textures then rotated/translated and welded the model in XSI Mod Tool

A big thanks to all the guys here writing programs and sharing info etc!  

I can't wait for a gr2 to obj/dae utility!
## Post #43
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-31T08:49:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The contents of this post was deleted because of possible forum rules violation.
## Post #44
- Username: jcsmith
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 11, 2009 3:02 am
- Post datetime: 2011-10-31T10:56:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Yeah looks like the link is dead.
## Post #45
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-10-31T12:52:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

--removed
## Post #46
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-10-31T13:37:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The contents of this post was deleted because of possible forum rules violation.
## Post #47
- Username: mvanderw
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 31, 2011 10:44 pm
- Post datetime: 2011-10-31T14:49:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from CZW
>
> 
link not working
anyone have a new link  ???
thx

Since it's such a cool tool I'll put it up until Dionix187 sees this.  

[http://holocron.so/files/tormyp.tar.bz2](http://holocron.so/files/tormyp.tar.bz2)
## Post #48
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-10-31T21:42:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The contents of this post was deleted because of possible forum rules violation.
## Post #49
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-11-01T00:01:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

How do you use the .gr2 converter to .obj tool, it does nothing but quickly bring up the cmd window? I tried running it to convert the gr2 model found in this thread and nothing is exported.
## Post #50
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-01T00:40:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Do a drag and drop.
Just drag the GR2 file you want exported onto the program.

Or you can try this one
[http://www.mediafire.com/?2hd9vje40v2z2fd](http://www.mediafire.com/?2hd9vje40v2z2fd)
## Post #51
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-01T01:36:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Something you might also want to keep in mind.
The Granny Sytem allows modifications as the Devs see fit to code them.
An Exporter for one Games GR2 files may not work for other Games GR2 files.
It's a very modifiable system if the Devs aren't confused by it all.
## Post #52
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-01T09:36:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The contents of this post was deleted because of possible forum rules violation.
## Post #53
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-01T22:49:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

PM sent.
## Post #54
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-01T23:39:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Privateer, pm receive ...

same problem ...
i use Deep exploration to open it ..
screen on the brigde

[](http://www.hostingpics.net/viewer.php?id=646643Sanstitre.jpg)
## Post #55
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-02T00:13:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

OK. I missed that section.
I saw something else that looked weird.

Anyone have the textures for this Unit?
I'd like to see it textured but I'll look at the GR2 data itself and compare to exported information.
Does anyone have an 'in Game' shot also?

In many Games? Somethings look all screwed up on exporting but how the Engine uses the Meshes explains alot of why things appear screwed.
As an example, You can find the Open Bunker I did for SH5.
You'll see many mistakes in the Sub Bunker but you were never supposed to be able to go there!
I edited the GR2 file and now you can.
## Post #56
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-02T07:55:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The contents of this post was deleted because of possible forum rules violation.
## Post #57
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-11-02T11:47:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

It's the low LOD model for long distance stuff. Chances are the errors could exist in the original model, as often times game devs will generate lower LODs automatically through something like Optimize, or much more likely a specialist poly reduction plugin/script. Those sorts of operations tend to result in all sorts of mesh errors, particularly if the reduction is aggressive. Usually in-game it's a non-issue, as you can't see it from the distances the game uses the model at.
## Post #58
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-02T11:53:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Hairless Wookiee
>
> It's the low LOD model for long distance stuff. Chances are the errors could exist in the original model, as often times game devs will generate lower LODs automatically through something like Optimize, or much more likely a specialist poly reduction plugin/script. Those sorts of operations tend to result in all sorts of mesh errors, particularly if the reduction is aggressive. Usually in-game it's a non-issue, as you can't see it from the distances the game uses the model at.

the hashlist is partial at this time, yes ..
the name refered to the LOD, ok, but the model is fully fonctionnal
but into this model, you have the model and the LOD inside
here it's present the model, not the LOD
the LOD01 in any case, is the model very close ...

wait and see the specialist ^^
## Post #59
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-11-02T12:54:13+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

For veh_imp_capital_destroyer I am seeing veh_imp_capital_destroyer_lod02 and veh_imp_capital_destroyer_lod03, so presumably LOD01 is just the first LOD graduation and thus still contains a fairly reasonable amount of detail.

Speaking of the Imp Destroyer, I noticed that processing the Voidstar variant of the model (veh_imp_capital_destroyer_voidstar) with Privateer's app results in the following message for all textures in the MTL files:

No Materials, Invisible part, or texture Name located in Extended Data Block.
Extended Data Block access Code in progress.

It looks to be just the base destroyer meshes with an additional set of bridge meshes to make it look unique, but presumably they did something different with the structure of that particular file. Judging by the message, this will need to wait for an update of the app.
## Post #60
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-02T14:08:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Hairless Wookiee
>
> For veh_imp_capital_destroyer I am seeing veh_imp_capital_destroyer_lod02 and veh_imp_capital_destroyer_lod03, so presumably LOD01 is just the first LOD graduation and thus still contains a fairly reasonable amount of detail.

Speaking of the Imp Destroyer, I noticed that processing the Voidstar variant of the model (veh_imp_capital_destroyer_voidstar) with Privateer's app results in the following message for all textures in the MTL files:

No Materials, Invisible part, or texture Name located in Extended Data Block.
Extended Data Block access Code in progress.

It looks to be just the base destroyer meshes with an additional set of bridge meshes to make it look unique, but presumably they did something different with the structure of that particular file. Judging by the message, this will need to wait for an update of the app.

i haven't find it ...
share a pack ..
i see only one scare in character selection folder, it seems a background picture
## Post #61
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-02T22:03:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Hairless Wookiee
>
> Speaking of the Imp Destroyer, I noticed that processing the Voidstar variant of the model (veh_imp_capital_destroyer_voidstar) with Privateer's app results in the following message for all textures in the MTL files:

No Materials, Invisible part, or texture Name located in Extended Data Block.
Extended Data Block access Code in progress.

It looks to be just the base destroyer meshes with an additional set of bridge meshes to make it look unique, but presumably they did something different with the structure of that particular file. Judging by the message, this will need to wait for an update of the app.

This app was coded for other Games GR2 files.
The textures are called differently with the GR2 files here.
I'll adjust that along with another correction on the Name numbering.
I was extracting from a GR2 that had 4 meshes all named the same.
So I threw in the quick numbering.
I'll code it to check for duplicate names and add the number only if it's true.

I should add drag and drop someday also. 

The LOD model is messed up in the GR2 file so the exports are correct.
## Post #62
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-11-04T22:27:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

So does anyone have a link for all the extracted .gr2 models now that we have a converter to use for converting them from .gr2 to .obj?
## Post #63
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-05T10:03:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Nintendude
>
> So does anyone have a link for all the extracted .gr2 models now

NO .. and only 47% of files are decoded

> Reply from Nintendude
>
>  a converter to use for converting them from .gr2 to .obj?

please read all posts before ... all is done and link post
## Post #64
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-11-05T14:24:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from CZW
>
> NO .. and only 47% of files are decoded

Is it possible to decode the other files?
## Post #65
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-11-05T15:44:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Eventually no doubt. Might need to wait until the game goes live though possibly, if capturing packets from the server is required.
## Post #66
- Username: Scalion
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 10, 2011 11:41 pm
- Post datetime: 2011-11-10T15:48:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I have now access to the file because of the beta test week (11 november 2011)

It like i cannot "see" any .tor file, all i see is.. well :


C:\Games\Star Wars-The Old Republic\Assets\green_main_1.tor
## Post #67
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-11T01:55:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Many of the files with the .txt extension are WWise soundbanks.
The correct extension should be .bnk
The header is easy to recognize in a hex editor.

42 4B 48 44 10 00 00 00 38 00 00 00 35 A2 3C 69
0C 00 00 00 00 00 00 00 44 49 44 58


There's also alot of files with the .txt extension that are GR2 files.
I found 562 in the assets_main_22\txt folder alone.
(I have an alpha program that scans all files in a folder and subfolders and tells you if they are GR2 files)
## Post #68
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-11-11T15:11:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Yeah generating a hash list in EasyMYP only gets names for about a third of the files. It does seem like it correctly identifies file type for DDS files that it it has no filename for at least, but everything else pretty much gets generically assigned as a text file.
## Post #69
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-11T22:52:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The Quick GR2 Finder program was coded for a different Game that uses files with no extensions and a number identifier as a name.
It will soon be coded to rename files like that on the fly.
(Hopefully this weekend)

The Exporter is drag and drop now and exports a proper mtl file.
I only need to clean up the code a bit to remove things that are not needed for SWTOR.

I've used Ravioli Game Tools to extract some wav files from the SoundBanks.
I just need to find a tool (or write one) that will convert them as they do not play at this time.
## Post #70
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-12T03:35:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I'd look at the source for EasyMYP but it's done in C#
Such a waste of resources and slow motion.
I only code in C or sometimes C++
## Post #71
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-14T01:26:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I've got the Exporter nearly finished now.
It does the Drag and Drop and also allows browseing or typeing in the path with auto-complete,
Checks for duplicate mesh names and only renames if found true,
writes proper MTL files.
I've also removed non-needed code for SWTOR reducing the .exe size.

I'm thinking of adding the ability to copy the texture files to the exported folder or setting the path in the MTL so no copy or move is needed.
What would you prefer in this case?
## Post #72
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-11-14T06:28:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> I'm thinking of adding the ability to copy the texture files to the exported folder or setting the path in the MTL so no copy or move is needed.
What would you prefer in this case?
While copying the textures to the exported folder would be more convenient, i think this would be a waste of harddrive space since you would have the same textures in different locations. I'd just go with including the path in the *.mtl file to avoid duplicate files.

Your work here is appreciated very much, thank you.
## Post #73
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-14T07:37:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I'll check what I can do to adjust the file path in the mtl.
I also hate duplicate files burning HD space.
## Post #74
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-15T05:36:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I've started an options ability that will allow you to set a few functions.
It will allow you to put the exported files where you wish.
It will allow copying or moveing texture files to the exported files folder if you wish.
I'm adding this feature because I usually save to an external drive or a networked drive to save local HD space.
Defaults are save in currently created folder with mtl adjustment pointed to the original tex folder.
It's saved as an .ini file as I hate messing with the register settings.

Once I get this done (and fix a few things I broke messing around) I'll post a link to it.
After that I will implement a mass export so you can drag/drop a folder on it and export all GR2's in one shot.

After that I'll implement:
Find and rename GR2's that are not yet identified by the EasyMYP program and extract them also.
That may be a plug-in DLL as the main program was written in MS Visual C++ and the program that finds GR2 files was written in CodeBlocks C.
## Post #75
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-11-15T08:12:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Sounds good. I look forward to trying it out. It would be especially good if you get that unnamed GR2 finder working.

I don't think moving/copying textures is necessary. I guess it would be handy feature to have some time in the future, but for now I'm sure people would rather see a release sooner with the aforementioned basic functionality tweaks/changes.
## Post #76
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-16T01:17:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Will do a release of a new version soonish saveing the extras for later.
Like many GR2 files? it uses textures inverted so I need to flip the tex coords so you won't need to flip the actual textures.
The file path for the textures in the mtl is set to the texture folder in the EasyMYP folder.
You can move the exported files all you wish and they will still find the textures.
## Post #77
- Username: jcsmith
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 11, 2009 3:02 am
- Post datetime: 2011-11-16T16:05:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Sounds great.
## Post #78
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-17T04:56:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

This does not have the new GUI with drag and drop but has the MTL and texcoord flip fixes.
Give it whirl and let me know of any problems.

[http://www.mediafire.com/?idga997sercfurm](http://www.mediafire.com/?idga997sercfurm)
## Post #79
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-17T21:17:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

If you use 010 Hex Editor?
Here's a script that corrects the CRC of GR2 files.
[http://www.mediafire.com/?v8r6dgmkicw2069](http://www.mediafire.com/?v8r6dgmkicw2069)
## Post #80
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-11-18T02:24:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Haven't had time to do an in-depth test, but at first blush the new version seems to work fine.

By the way, for anyone that wants to try out TOR, they are giving away beta keys to all and sundry for an upcoming weekend. They said they will invite everyone that has ever signed up for testing on the main site before November 11, plus they have given a bunch of keys to some of the big game sites to give away. More details here - [http://www.swtor.com/news/news-article/20111111-0](http://www.swtor.com/news/news-article/20111111-0)
## Post #81
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-18T20:42:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Thanks for the Heads up on the free keys thing.
 

I grabbed one this morning and am off to get it registered.
I'd like to see the actual files!


All signed up and awaiting a Go E-Mail.
## Post #82
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-11-22T09:58:59+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> 

After that I'll implement:
Find and rename GR2's that are not yet identified by the EasyMYP program and extract them also.
That may be a plug-in DLL as the main program was written in MS Visual C++ and the program that finds GR2 files was written in CodeBlocks C.

a good work ... thx


have you some news to extract GR2 unidentified by EastMYP ????
## Post #83
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-22T15:41:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> have you some news to extract GR2 unidentified by EastMYP ????
The finder program can spot the gr2 files that are extracted with a .txt extension and no true name, Yes.
I need to code the program to rename them yet.

I also found that some .dat files contain a file name along with the path where it should go.
I'm looking at grabbing that info and compareing the found GR2 files so the program renames and moves them to the proper place.
## Post #84
- Username: XHD
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 01, 2009 4:31 pm
- Post datetime: 2011-11-22T18:06:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Just an FYI, the new SWTOR beta build has redone .TOR's, they're now organized by area, armor, etc. So the current EasyMYP wont always work with them anymore. I think in the long run we're going to need a tool that either parses the .TOR hashes when you launch the program, or completely skips the hash list and can tell whats contained. This would be because of client patches, etc.
## Post #85
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-22T19:51:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I've noticed that now that I have the newest Beta.
Many files listed as GR2's are not.
I don't understand the EasyMYP thing well enuff to do anything about the wrong extensions.
And I'm wondering if the models are now compressed somehow?
## Post #86
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-22T20:17:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Thanks for the heads-up, HXD! It is bad news indeed that they changed the assets format again but maybe it will help us in guessing the filenames if the files are better grouped.
In case you didn't notice, [we have a topic going on](http://forum.xentax.com/viewtopic.php?f=10&t=7186) in the Game Archive Research subforum where we discuss about all The Old Republic files, while this topic is only about the gr2 model files.
## Post #87
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-12-03T20:40:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

hazballs posted [HERE](http://forum.xentax.com/viewtopic.php?p=63011#p63011) that the header of the gr2 files has changed:

> Reply from hazballs
>
> ...the gr2 files now have the GAWB "magic number" instead of )ÞlÀ and cannot be converted...
The current conversion tools do not work with these. I compared the file sizes of some old and new gr2 files and it looks like they are compressing them now(as Privateer suspected). Maybe decompressing them will reveal the exact same gr2 file as the old and will still work with the gr2 to obj exporter. We now need a solution to this compression.



EasyMYP Tip:
if you only want to extract a/few file/s from a tor archive then switch to the Archive File List tab and make a selection then go to File>Extract Selected
## Post #88
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-04T01:07:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Looking at the GAWB files (for lack of a better name at this time), it's clear they are not compressed but are also not standard GR2 files.
I have spotted the data needed to export the meshes.

Each mesh is a seperate section with the postional data listed first.
I'd suspect all the other information to follow in the same way but have not verfied that at this point.

You won't even need the granny2.dll to read this file format.
## Post #89
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-04T18:59:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Some quick information on the GAWB file 'veh_neu_shuttle'

80h = # of verts in the first mesh
84h = # of indices in the first mesh
88h = start address of verts in first mesh

A8h = # of verts in the second mesh
ACh = # of indices in the second mesh
B0h = start address of verts in second mesh

Looking at other GAWB files I see the same basic pattern for the mesh information.
Still going through the format to fully understand it but it seems fairly easy to figure out.
## Post #90
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-12-05T08:25:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> Some quick information on the GAWB file 'veh_neu_shuttle'

80h = # of verts in the first mesh
84h = # of indices in the first mesh
88h = start address of verts in first mesh

A8h = # of verts in the second mesh
ACh = # of indices in the second mesh
B0h = start address of verts in second mesh

Looking at other GAWB files I see the same basic pattern for the mesh information.
Still going through the format to fully understand it but it seems fairly easy to figure out.
Does this theoretically imply that a new extractor can be written fairly easily?
## Post #91
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-05T13:59:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from mazor
>
> 
Does this theoretically imply that a new extractor can be written fairly easily?
For the most part Yes.
I've gotten most of the pointers to the important information pinned down now.
How to grab the model/mesh name and the texture information, model/mesh count, etc.
There's a few things to figure out yet but I should have that all sorted soon.

There will be no need to use the granny2.dll to extract the meshes with this format.
## Post #92
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-12-06T06:28:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Btw testing is now over. Early access starts late next week (15th), so the retail client should go live by Mon/Tue (12/13) next week I would think. From comments made by devs it would seem that little is likely to change content-wise, but I'm unsure how things will change on the file system/format side of things.
## Post #93
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-06T13:05:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I'd think this late in the date format should be pretty much set for the 3D meshes anyway.
I'll start a python script for Noesis to work the meshes exporting today.
Most of the information is easy to grab and what I have not figured out yet should fall into place as I work on it.

Edit:
Seems the Normals and TexCoords are shuffled in some way?
Not compressed but encrypted some how.
The rest of the information is very easy to extract as far as where in the file it is.
## Post #94
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2011-12-08T02:29:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The retail client is now available for pre-load by those that have registered their pre-order code. They have also extended the early access period to 7 days (was previously 5) which now starts on Dec 13.

[http://swtor.com/download](http://swtor.com/download)
## Post #95
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-12-08T05:14:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

If you participated in the last 2 Beta Weekends then you won't need to uninstall your Game Client.

> If you participated in The Old Republic Game Testing Program, but did not participate in the November 25th-28th or December 2nd-4th Beta Weekends, first uninstall the Game Testing Client before moving on to the next step. If you did participate in either of these Beta Weekends, there is no need to uninstall your Game Client. Visit the FAQ for instructions on how to uninstall your Game Testing Client.
Source:
[http://www.swtor.com/early-access](http://www.swtor.com/early-access)

It looks like they're done tweaking their model format for now.
## Post #96
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-10T01:05:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The files are pretty easy to work except for the texcoords and what I think are the normals.
Those are encrypted somehow that I'm still trying to figure out.
It's not in the Granny2.dll (Which is a custom build for SWTOR)
## Post #97
- Username: Jokkocze
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 05, 2011 12:48 am
- Post datetime: 2011-12-11T15:06:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Great job so far guys! I'm really looking forward to a working solution so I can get my hands on the XS Freighter model and make me some 2D-blueprints off it.
## Post #98
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-12-12T04:20:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

@Privateer:im also looking into these files, have you looked to see if maybe the UVs are done as uint32s that are divided by a constant value? ive seen other games do that alot
## Post #99
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-12T04:35:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from nicoli_s
>
> @Privateer:im also looking into these files, have you looked to see if maybe the UVs are done as uint32s that are divided by a constant value? ive seen other games do that alot
 I've been running different things to try to find the 'magic' mixture but have not found it yet.
I have a few thoughts to try next but have been busy fixing a few systems for people.
And sometimes a few days away from a problem helps clear the mind.

I do know that the collision objects do not have the messed up 'normals' entries.
They have no 'normals' entries infact.
Those would be useless as the mesh is not rendered anyway.
## Post #100
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-12-12T05:15:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

do you mind posting your structure so far? ive got the first geoset rendered(without uvs and nromals) but havent figured out the geoset count yet
## Post #101
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-12T05:35:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from nicoli_s
>
> do you mind posting your structure so far? ive got the first geoset rendered(without uvs and nromals) but havent figured out the geoset count yet
I have not coded the structures yet so I can't 'show' you anything at this time.
The number of meshes in a given file is found at 1Ah 
The files are a modified GR2 format. That I am sure of as I see many of the same pointers used in standard GR2 files.
I also compared earlier versions of the granny2.dll file to the last version I have and they are not changed.
That kind of tells me a few things after running stuff through IDA Pro.
## Post #102
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-12-13T00:09:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

it doesnt seem like that is the mesh count, as im finding meshes with a value of 0 there, that have values in the other spots you mentioned and i have imported the first mesh and its def valid
## Post #103
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-13T00:44:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I should have put a ? mark after the 1Ah
It seems to hold true on the ones I cross compared but I did not check all the files.
What file has the 0 at 1ah?
## Post #104
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2011-12-22T04:18:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

so any progress on making it easier to find .GR2 models, i have a beta build from back this September and the last beta build, i happen to install 2 beta builds and i didn't buy the game since i don't have the money to keep paying on it and i've tried both build and can only get the weapons and ships and props and skeletons.gr2s out of the files, can you tell me where i can find the characters like this and the droid on the other pages cause they are more use to me thin the props since i'm converting and animating them to another star wars game for a mod
## Post #105
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-23T00:59:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from JakeGreen
>
> so any progress on making it easier to find .GR2 models, i have a beta build from back this September and the last beta build, i happen to install 2 beta builds and i didn't buy the game since i don't have the money to keep paying on it and i've tried both build and can only get the weapons and ships and props and skeletons.gr2s out of the files, can you tell me where i can find the characters like this and the droid on the other pages cause they are more use to me thin the props since i'm converting and animating them to another star wars game for a mod
The GR2 files are extracted but many are listed as .txt files as the MYP extraction stuff is not perfect.
Open the .txt files in a hex editor and look at the file header and rename as needed.
I'd like to get the time to finish a program I have started that finds and renames gr2 files.
You drag and drop a folder on it and hit OK. It searches every file in every subfolder and does the dirty work.
## Post #106
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-12-23T09:29:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> JakeGreen wrote:so any progress on making it easier to find .GR2 models, i have a beta build from back this September and the last beta build, i happen to install 2 beta builds and i didn't buy the game since i don't have the money to keep paying on it and i've tried both build and can only get the weapons and ships and props and skeletons.gr2s out of the files, can you tell me where i can find the characters like this and the droid on the other pages cause they are more use to me thin the props since i'm converting and animating them to another star wars game for a mod

The GR2 files are extracted but many are listed as .txt files as the MYP extraction stuff is not perfect.
Open the .txt files in a hex editor and look at the file header and rename as needed.
I'd like to get the time to finish a program I have started that finds and renames gr2 files.
You drag and drop a folder on it and hit OK. It searches every file in every subfolder and does the dirty work.

take your  time ... it look great !!
## Post #107
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-23T18:56:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> take your  time ... it look great !!

This is a quick Script for SweetScape's 010 Hex Editor.
It will search all files in a folder and all subfolders for the GAWB used in the new SWTOR GR2 files and list them.
*EDIT------
--- Added a command to save the OutPut to a text file.
--- Edited to better work with the Renameing script.
--- Added a check to only name files with one occurence of the search found at the start of the file.
     This is a quick work around for now.
You'll have a list of all files that are actually GR2 files.

Copy the code and save as FindAllGR2.1sc
Edit the C:\\temp to whatever folder you have your extracts saved in.

```
//--- 010 Editor v3.2.2 Script File
//
// File:     FindAllGR2.1sc
// Revision: 1.0
// Purpose: Opens all files, looks for GAWB.
//You must have Version 3.1.0 or higher If you have an older version?
// Remove the RequiresVersion line and OutputPaneSave line then you can select all in the output pane and copy.
//Create a new txt file and then paste.
//----------------------------------------------------------------------------------
RequiresVersion(3, 1, 0);

 int i, j;
    TFindInFilesResults r = FindInFiles( "GAWB", "C:\\temp", "*.*" );   
      for( i = 0; i < r.count; i++ )
    {
        for( j = 0; j < r.file[i].count; j++ )
          { 
            if(r.file[i].start[j] == 0 &&  r.file[i].count == 1)
            Printf( "%Ls\n", r.file[i].filename );
           }
    }

    OutputPaneSave("GR2List.txt");

```


This is a quick working Script until I get the main application finished.



On the plugin for Noesis, 
I've sent python code and information to convert the texcoords to nocoli_s
Hopefully he'll have something for us real soon.
## Post #108
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-12-24T21:51:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Will this script work with the old GR2 beta files as well? It would be awesome if you could write something to identify and rename those deadbeef text files. Thanks for your efforts.
## Post #109
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-24T21:55:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from mazor
>
> Will this script work with the old GR2 beta files as well? It would be awesome if you could write something to identify and rename those deadbeef text files. Thanks for your efforts.

Just change the GAWB to )ÞlÀ and it should do the job.

I'll get a script out that will read the output list and do the renameing of the extensions soonish.
It will only change the extension, not the first part with all the numbers for now.
So 0AE02A76_325D6DA9AEB4F9A8.txt will become 0AE02A76_325D6DA9AEB4F9A8.gr2 as an example.
If someone finds a list or something that could be cross referenced to do a full rename?
That would be great.
## Post #110
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-26T03:51:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Here's the renameing script for 010.
Feel free to edit it as you wish as it can be used to rename other file types if you also edit the script I posted above.
I suggest you recopy the above script as I did edit it to work better with this script.
Merry Christmas all!

```
//   010 Editor v3.2.2 Script File
//
// File:     SWTORBatchRename.1sc
// Revision: 1.0
// Purpose: Takes as input a text file containing a list of file names, one per line. 
//          Opens each file in the list, performs processing on the file name  
//          (in this case renames the actual files)
//          and then closes the file.
//-----------------------------------
// Define variables
int64 out;
int   len, listfile, i, pos;
char  filename[512], listfilename[512], filerenamed[512], ext[5];
ext = ".gr2";

// Input text file containing a list of files to process
listfilename = InputOpenFileName( "Choose File with list of Files to Rename", 
    "Text Files (*.txt)|*.txt|All Files (*.*)|(*.*)" );
if( Strlen( listfilename ) == 0 )
    return -1;

// Open text file containing a list of files
if( FileOpen( listfilename ) < 0 )
    return -1;
MessageBox(idOk, "DON'T BLINK!", "I'm Going to Rename the files...");

//strip the first line from the file and such

SetCursorPos(0);
out += Replace("202020,h", "");

int Replace(const string sstr,const string dst)
{
   int i=0;
   int out=0;

 do
  {
    i=ReplaceAll( sstr, dst, true, false, false, 0.0, 1, 0, 0, false );
  }
 while (i>0);
 return(out>0?out:0);
}
 filename = ReadLine( FTell() );
    len = Strlen( filename );
    FSkip( len );
    if( len > 0 && filename[len-1] == 0xA && filename[len-2] == 0xD  && filename[len-3] == 0x2E && filename[len-4] == 0x2E && filename[len-5] == 0x2E)
         DeleteBytes( pos, len );
//End of stripping

listfile = GetFileNum();

// Read the list file for a set of file names, each file on a different line

while( !FEof()  )
{
    // Get file name from list - remove end of line characters
    filename = ReadLine( FTell() );
    len = Strlen( filename );
    FSkip( len );
    if( len > 0 && filename[len-1] == 0xA )
         filename[len-1] = 0;
    if( len > 1 && filename[len-2] == 0xD )
         filename[len-2] = 0;
 //change the file extension
    Strcpy(filerenamed, filename );
    filerenamed = StrDel(filerenamed, Strstr( filerenamed, "." ), 4 );
    Strcat(filerenamed, ext );

 // Rename the files
    RenameFile(filename, filerenamed );

   // Close file
    FileSelect( listfile );
}

// Close original list file
FileClose();
    // Print out results
MessageBox(idOk, "POOF!", "Done Renameing files.");
```
## Post #111
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-26T14:53:52+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Great job on writing the scripts, Privateer! 

I do not know the format of the 010 templates but I believe there is a small error in your renaming script:

> if( len > 0 && filename[len-1] == 0xA && filename[len-1] == 0xD  && filename[len-3] == 0x2E && filename[len-4] == 0x2E && filename[len-5] == 0x2E)
The red letter has to be a "2", otherwise the if condition will never return true.

Also, I believe your first script is searching through the whole content of the files and not just the first four bytes. Because of this there may be some false positives, but if you have it correct in your main application this will do for the moment.
## Post #112
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-26T15:05:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Good spotting Mate!
Error corrected in the second script.
Even with that error it only catches and removes the first line 010 adds to the output txt file.
That's why it slipped by me when I was cutting and pasteing things.

1st script edited to print names of files with the occurrence found ONLY at the beginning of the file.
If further occurrences are found, the file is ignored.
If you find a file that does have more then one occurrence and is a valid file your searching for?
Give me a link to them and I'll adjust the script.
## Post #113
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-12-26T17:34:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Excellent work! I'll give these scripts a whirl and see what happens. Thanks.
## Post #114
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-12-26T19:16:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

hey so im still working on getting my extractor done, but i can post that Privateer helped me figure out the tex coords, and if you use C#, the XNA class HalfSingle handles them just fine. The main thing im working on now is that some models have different lengths for the vertex block, some are 32 bytes, while others are just 24, theres some flag controlling it that im looking for. Also it looks like some material info is in the files still so im tracking that down, but expect to have a way to see these models online sometime soon
## Post #115
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-26T21:29:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from nicoli_s
>
> hey so im still working on getting my extractor done, but i can post that Privateer helped me figure out the tex coords, and if you use C#, the XNA class HalfSingle handles them just fine. The main thing im working on now is that some models have different lengths for the vertex block, some are 32 bytes, while others are just 24, theres some flag controlling it that im looking for. Also it looks like some material info is in the files still so im tracking that down, but expect to have a way to see these models online sometime soon
Good to hear Mate! 
MrAdults also guided me to the correct way to extract those texcoords in Noesis.
noesis.getFloat16 does the job.

I also have a good idea on how the Normals are compressed now thanks to some reading in the 
Forza Motorsport Resource Extraction (.carbin) thread.
I'm hopeing for some samples of those files and an extracted mesh from same to examine.

Just so you all know.....
I'll be takeing a few days to do some 3D modeling work for a Mate doing a Mod for Silent Hunter 3 this week.
I've been Modding Silent Hunter Games for a few years and mostly assist others with thier projects now days.
I'll probably be adjusting the scripts above to better aid in searching/renameing the different file types but that will be on the back burner
unless it's an important fix that needs done right away.
## Post #116
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-12-27T03:53:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I ran the script and all seems to be running well, but no txt file was generated in the output. I specified the correct path for C:\\temp. Did I do something wrong?
## Post #117
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-27T04:08:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Were the actual extracted files in the folder you searched?
Check the folder the script is in for the output file.
You were searching an older Beta that exported actual GR2's correct?
The easiest way to run the script is to double click it with 010 closed.
Once everything opens, hit the F7 key.
If your path is correct and the files are there it should work properly and show a list in the Output window.
If you changed the search string and are searching the later Beta? You won't find anything.
## Post #118
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2011-12-27T04:30:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

if possible can someone give a way to use this script i'm kinda dumb when it comes to hex editors, i downloaded the program but how do i use it with your script?
## Post #119
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-27T04:35:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The easiest way to run the script is to double click it with 010 closed.
Once everything opens, hit the F7 key.
If your path is correct and the files are there it should work properly and show a list in the Output window
and save the txt file to the same folder the script is in.
(I keep the script on my desktop)
Create a temp folder on the root of C: and copy the extracted SWTOR stuff there if you don't want to edit the search path.

I'll probably add pop up boxes so you can type in the search phrase and path to search.
The output could do that also but 2 boxes is enuff and the output is always saved to the same folder as the script unless you change that in the script.

This is mostly a way to quick test things before I re-code the stand alone app.
It's done in pure C as is most of the scripting.
## Post #120
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-12-27T04:43:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> Were the actual extracted files in the folder you searched?
Check the folder the script is in for the output file.
You were searching an older Beta that exported actual GR2's correct?
The easiest way to run the script is to double click it with 010 closed.
Once everything opens, hit the F7 key.
If your path is correct and the files are there it should work properly and show a list in the Output window.
If you changed the search string and are searching the later Beta? You won't find anything.
The extracted text files were in the folder I searched and yes I am searching an older beta. I'll try it again with a different path.
## Post #121
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-27T04:48:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Open 010 by double clicking the script and then hitting F7.
I saw in your image it seemed to have searched the script itself?
## Post #122
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2011-12-27T04:50:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> The easiest way to run the script is to double click it with 010 closed.
Once everything opens, hit the F7 key.
If your path is correct and the files are there it should work properly and show a list in the Output window
and save the txt file to the same folder the script is in.
(I keep the script on my desktop)
Create a temp folder on the root of C: and copy the extracted SWTOR stuff there if you don't want to edit the search path.

I'll probably add pop up boxes so you can type in the search phrase and path to search.
The output could do that also but 2 boxes is enuff and the output is always saved to the same folder as the script unless you change that in the script.

This is mostly a way to quick test things before I re-code the stand alone app.
It's done in pure C as is most of the scripting.

thanks i did all that and it generated a .txt file on my desktop, which is suppose to work with quickbms right? cause when i try and open a .tor file it says error: invalid command "executing" or arguments -1 at line 1

also the only thing inside my .txt it generated was Executing script 'C:\Users\Derrick\Desktop\FindAllGR2.1sc'... is that suppose to be like that?
## Post #123
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-27T04:55:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

No it does not work with QuickBMS.
You run my second script next.
It reads the file and then renames the files it found that should be gr2 instead of txt

All the tor files MUST be extracted with the EasyMYP BEFORE you run my scripts.
swtor_main_art_vehicle_1.tor alone has something like 130 gr2 files named as .txt files after extracting!
## Post #124
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2011-12-27T05:06:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> No it does not work with QuickBMS.
You run my second script next.
It reads the file and then renames the files it found that should be gr2 instead of txt

All the tor files MUST be extracted with the EasyMYP BEFORE you run my scripts.
swtor_main_art_vehicle_1.tor alone has something like 130 gr2 files named as .txt files after extracting!

o ok well i don't seem to have gotten it but all my .tors files are named assets_main_16 and so on, but if it's possible can't someone make a video tutorial on how this works i can follow that 10 times more thin words
## Post #125
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-27T05:15:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Yes, those are the older Beta .tor files.
Those will have somewhat standard gr2 files with screwed up CRC's that GrannyViewer will not open unless you use the CRC script I posted earlier in this thread.
But even extracted there's a whole boat load that are still listed as .txt files.
## Post #126
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-27T06:30:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

If your script is still not working, you may want to check your search term. If I see it from the screenshot correctly, you are missing the opening paranthesis. The correct term is: ")ÞlÀ"
However, with special characters like these it is even better to specify their byte values than the actual chars, so 0xC06CDE29 should work for gr2 files.
## Post #127
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-12-27T17:55:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

After correcting the terms, a txt file was generated, but it only contained the same results as the ouput pane. I examined some of the extracted text files from the .tor archive and identifed some GR2 files just by opening them up in the 010 editor. Any ideas of how to proceed from here?
## Post #128
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-27T18:29:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Post a copy of your edited script.
And the path to where the extracted files are.
## Post #129
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-12-27T18:59:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Here's the script I used.

```
//--- 010 Editor v3.2.2 Script File
//
// File:     FindAllGR2.1sc
// Revision: 1.0
// Purpose: Opens all files, looks for GAWB.
//You must have Version 3.1.0 or higher If you have an older version?
// Remove the RequiresVersion line and OutputPaneSave line then you can select all in the output pane and copy.
//Create a new txt file and then paste.
//----------------------------------------------------------------------------------
RequiresVersion(3, 1, 0);

int i, j;
    TFindInFilesResults r = FindInFiles( ")ÞlÀ", "C:\Users\public\Documents\11123\assets_main_6", "*.*" );   
      for( i = 0; i < r.count; i++ )
    {
        for( j = 0; j < r.file[i].count; j++ )
          { 
            if(r.file[i].start[j] == 0 &&  r.file[i].count == 1)
            Printf( "%Ls\n", r.file[i].filename );
           }
    }

    OutputPaneSave("GR2List.txt");



```
## Post #130
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-27T19:32:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Make a temp folder on the root of C: copy a few of the text files to it and run it.
The Path you have listed can be a problem. I know it is on Windows 7 Ultimate.

Also make sure it's 
C:\\
you need the double \
## Post #131
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2011-12-27T23:30:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Good call. I did what you said and the script worked fine. The list exported the filenames and the second script renamed them. Except instead of the "." there was a "t" before the GR2 extension. Also, when I used your GR2 Exporter the deadbeef.txt was renamed to the proper file name. Good work!
## Post #132
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-28T03:35:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Fixed the 't' not getting cut out.
## Post #133
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-30T08:05:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

GAWB = BWAG = BioWare Austin Geometry
## Post #134
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-30T22:23:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Rick
>
> GAWB = BWAG = BioWare Austin Geometry
Thanks for the correct term Rick.
I was thinking 
BioWare Asset Geometry,
BioWare Adjusted Granny,
and all sorts of silly stuff.
## Post #135
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-01-12T15:57:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Hey guys,

I have been reading through these posts and the old republic beta posts and I am just looking to find out how to get the actual gr2 models and dds files?

I downloaded and installed Easy_MYP which can open the archives, but from there I am totally stuck. The archive does not list the files in there and am unsure how to export them to file formats everyone is talking of.

I cannot programmer at all, I am 3d person, and love to see how other things are built, so am a bit clueless when it comes to this, so apologies in advance......
## Post #136
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-02-26T13:14:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

It seems like the person behind knotor.com has found a way to view the .gr2 model files with their textures (see his blog post [here](http://knotor.com/articles/4-knotor-s-guide-to-patch-1-1)).
Right now I am focussing on reading the client.gom file for the game mechanics but I am really curious to get the models as well.
## Post #137
- Username: Lamron333
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 29, 2012 8:11 am
- Post datetime: 2012-02-29T00:23:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Hello, just wanted to know if this topic was dead & if not maybe a re-post of all needed links & info on the first post could bring this back.
I wanted to use it to upload a crap-load of item & NPC images to [http://www.torhead.com](http://www.torhead.com) & other sites like it to help the sites have more content for displaying the info they are providing free. Anyway, get back to me
## Post #138
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-20T20:42:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Sorry I was away so long.
Real life gets in the way of haveing fun sometimes you know?
 

I can re-upload whatever I have if wanted and I'm working on a few different additions also.
The new stuff may be far inbetween releases as I now have changed what I do for a living.
I travel all over the U.S.A. now and don't have a NoteBook to take with me.
Last trip out I was gone for a month!!
 

Once I get some cash saved up I'll buy a new NoteBook and work on stuff in Motels.

I did some studying of the Forza MotorSports thread and I'm pretty sure of what I suspected.
The Normals/Tangents in the new GR2 files are compressed.
Been working on those for weeks now.
## Post #139
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-20T22:10:13+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Traveling salesman?
## Post #140
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-20T22:27:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from MrAdults
>
> Traveling salesman?
 

If ONLY life was that easy!!
I do Construction work in many areas. My newest WTF job is installing floors in Commercial buildings.
I do stuff like this.............



Then it looks like this when I'm done..............
## Post #141
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-20T23:23:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I'm discussing an option with a few people on the Normals compression issue.
I have some Python code that re-computes the Normals and Tangents for the vertices.
I can adapt that code for Noesis so Normals and Tangets can be computed on the fly when loading a file if one just skips them in Noesis.

I have 2 reasons that I tihink it's a good way to go.
1) Many programs do a crap job of doing the math in Game as the Engine is OK with that.
2) As most of the extracts are "only" for render reasons? They do look better in most cases I've seen.
I used quotes as I suspect there's other reasons to snatch meshes.
 

Opinions?
## Post #142
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-03-21T00:01:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

AM really curious to get hte game models too. I also would be very interested to see the textures..... I am designer normally so don't have a clue how to get textures out at all..... I have looked through the forum posts a few times and its not clear....

Could anyone give me a step by step guide on how to get the textures out if they have time please? (into a format like dds or tga or something....)

Thanks if u can help!
## Post #143
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-21T00:26:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

If you have the Latest release of SWTOR?
Get the hash file SWTOR_fan posted.
Use EasyMyp and extract all the files.
Should only take a day or 3
## Post #144
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-03-21T00:29:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> If you have the Latest release of SWTOR?
Get the hash file SWTOR_fan posted.
Use EasyMyp and extract all the files.
Should only take a day or 3

where is the hash file SWTOR_fan released? i can't seem to find it
## Post #145
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-21T00:34:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

This thread, Last posting.
[viewtopic.php?f=10&t=7186&start=120](http://forum.xentax.com/viewtopic.php?f=10&t=7186&start=120)
## Post #146
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-03-21T01:00:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Privateer
>
> This thread, Last posting.
viewtopic.php?f=10&t=7186&start=120

thanks dude your awesome lol  

EDIT: also is there anyway to convert the GR2 models into say obj, i got the GR2 converter but when i go to select a model to convert it, it says I have no idea why
## Post #147
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-21T16:42:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from JakeGreen
>
> Privateer wrote:This thread, Last posting.
viewtopic.php?f=10&t=7186&start=120

thanks dude your awesome lol  

EDIT: also is there anyway to convert the GR2 models into say obj, i got the GR2 converter but when i go to select a model to convert it, it says I have no idea why

You're trying to open one from the retail release it sounds like.
Those use a different format then a standard GR2 file.
No one has finished/released an exporter for the new format. 
Yet.
## Post #148
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-03-21T17:17:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Thanks for your help privateer... got the archives loaded and stuff, having problems with extracting, but have posted in the other page,

Cheers!
## Post #149
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-03-21T18:57:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from Marky
>
> Thanks for your help privateer... got the archives loaded and stuff, having problems with extracting, but have posted in the other page,

Cheers!
Not sure what your problem may be.
You have .NET Framework 3.5 installed?
Did you put it in the Program Files folder? 
Some programs won't run worth crap from them so I run from my E:\ drive.

A little speed boost for EasyMYP I use............
Game Booster! I run it in Game mode and EasyMYP works roughly 10X faster!
## Post #150
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-03-21T19:23:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

its running from my desktop, so will give program folders a go.... its under win7 which has .network 3, 4 and beyond I believe installed. I tried to install .net framework 3.5 but windows doesn't let it run....

Will give it a go from my program files

---- update

Tried it on 2 pc's on win7 x64 in the program folder  and the x86 folder. Still no luck......
## Post #151
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-04-13T19:34:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I'm wondering why I get PM's about custom programs to view the files?
Noesis is perfectly able to handle the release versions yet people want to write stand alone stuff?
Then you all ask for info and not give me a working example of your program but want more help.
My only purpose is to see you get what you want but I'm getting a little ticked that nothing is released in even a beta form.
Do I need to showboat you all and waste time programming while doing the reverse work for you?
## Post #152
- Username: OroMatoko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 27, 2012 4:58 pm
- Post datetime: 2012-04-27T10:00:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Greetings all, firstly I'd like to thank everyone for their hard work especially SWTOR Fan, Privateer and Dionix187 (and everyone else contributing!).

I've managed to extract my TOR files using EasyMYP with the updated hash lists perfectly fine but when it comes to extracting the GR2 using "grnreader98.v1.4.0.3.debug" I get nothing but errors, first grnreader98 refused to stay open when clicked it would pop up the command window for a split second and close, so I did run, cmd and used the command prompts there as dragging the GR2 onto grnreader98 did nothing at all.

So my process was "Run -> CMD -> A:\grnreader98.v1.4.0.3.debug\grnreader98.exe <filename> -a -> Enter"

But I just get errors, I've tried several files and several methods all result in failure, am I doing something wrong?

Here's a screenshot of the error....


Any help would be greatly appreciated.
## Post #153
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-04-27T12:12:13+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Hi OroMatoko!

It seems like you are using a program to convert the standard .gr2 Granny files from RAD game tools.
During the beta, SW:TOR was using the Granny format, and if you still have those beta files, you can convert the models with your tool.
However, in the release version, they developed a new, custom format that is completely different to the Granny format but they kept file extension .gr2 the same.

Together with Privateer's help I was able to figure out the new format and am currently writing a specification of the format; this may take a few more days.
If you know a little bit of programming, you will be able to write a tool from the specification that can read the new .gr2 files and convert them into another format like .obj.
Otherwise, you'll have to wait until such a tool is created. The best way would probably be a plugin for [Noesis](http://oasis.xentax.com/index.php?content=downloads) but since I do not know Python very well, I do not think I will be able to do it. But of course, anyone who feels up to the task can write such a plugin, and with the specification, that should be fairly easy to do.
## Post #154
- Username: OroMatoko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 27, 2012 4:58 pm
- Post datetime: 2012-04-27T16:18:13+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from SWTOR fan
>
> It seems like you are using a program to convert the standard .gr2 Granny files from RAD game tools.
During the beta, SW:TOR was using the Granny format, and if you still have those beta files, you can convert the models with your tool.
However, in the release version, they developed a new, custom format that is completely different to the Granny format but they kept file extension .gr2 the same.

Together with Privateer's help I was able to figure out the new format and am currently writing a specification of the format; this may take a few more days.
If you know a little bit of programming, you will be able to write a tool from the specification that can read the new .gr2 files and convert them into another format like .obj.
Otherwise, you'll have to wait until such a tool is created. The best way would probably be a plugin for Noesis but since I do not know Python very well, I do not think I will be able to do it. But of course, anyone who feels up to the task can write such a plugin, and with the specification, that should be fairly easy to do.

Ah thanks for the information I think you nailed it on the head, I separated my beta install from a fresh release install but it somehow updated both folders, so I guess I'm out of luck as I'm completely useless at coding (I believe I have some form of code specific dyslexia). So unless someone could PM me with a location for beta files I'll have to wait for amazing people like yourself before I can start my project.

If there's anything I can do to help ease the load let me know, I have no problem sorting through long lists of data for organising if needed.

Anyway thanks again SWTOR fan you're a legend keep up the great work!
## Post #155
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-04-27T20:18:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

The last Beta release was a standard GR2 format with the CRC messed up.
All releases since use a custom GR2 format.

RAD Games allows you to adjust the format as you want and many Games are now starting to use a custom format.
Every custom one I've seen is fairly easy to figure out so far.

I expect that to change as time goes on.
## Post #156
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-05-06T09:18:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

I have good news: The .gr2 file format specification is done! 
Click here: .gr2 file format specification

This is, without a doubt, the biggest file format specification I have written so far.

The formatting is not cleaned up yet and a few things are missing, but it should contain all of the important information now. I will probably update it over time, but at least now you have something to work with.

As I said, feel free to write a .gr2 plugin for Noesis, and if you find an error in the specification, feel free to correct it or ask me if you have any questions.
## Post #157
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-05-06T20:54:53+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Nice work Mate!
## Post #158
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-05-07T01:05:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

awesome work, i really hope someone makes a Noesis plugin now
## Post #159
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2012-05-18T16:01:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

> Reply from SWTOR fan
>
> I have good news: The .gr2 file format specification is done! 
Click here: .gr2 file format specification

the link is not working, do you have a mirror for the spec?
## Post #160
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2012-05-21T18:18:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta - GR2 model

Any news on a Noesis plugin? Thanks to everyone's hard work on this by the way, glad that there's so many people willing to help others for free in these corporate world ruled by money.
