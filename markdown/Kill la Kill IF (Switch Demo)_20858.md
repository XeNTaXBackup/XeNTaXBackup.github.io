## Post #1
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2019-07-25T20:46:47+00:00
- Post Title: Kill la Kill IF (Switch Demo)

I wrote some python scripts for the Kill la Kill IF Switch Demo. These might not work on the final versions.
KLK_Switch decompresses and/or extracts PAC, LEV and TXB files (They are all the same type). Plus 2 Noesis scripts for models and animations (could probably make this one script but I don't know how). I might be doing something wrong but Noesis doesn't export normals when a model has bone weights. The Skin variable in the model script toggles bone weight loading.
[KilllaKill.zip](https://xentaxbackup.github.io/file/16526_KilllaKill.zip)
## Post #2
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-07-26T01:46:05+00:00
- Post Title: Kill la Kill IF (Switch Demo)

Got a error when I used one of the .mot files from the final version's files.

Here is some .mot files from the final version of the game.
[https://anonymousfiles.io/ERWJXO4X/](https://anonymousfiles.io/ERWJXO4X/)
The version of Noesis I used is 4.406.
## Post #3
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-07-26T05:59:17+00:00
- Post Title: Kill la Kill IF (Switch Demo)

> Reply from andree ↑Fri Jul 26, 2019 9:46 am at Fri Jul 26, 2019 9:46 am
>
> 
Got a error when I used one of the .mot files from the final version's files.

Can you upload the .mdl files as the script need them? Thanks
## Post #4
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-07-26T12:18:32+00:00
- Post Title: Kill la Kill IF (Switch Demo)

> Reply from andy97 ↑Fri Jul 26, 2019 1:59 pm at Fri Jul 26, 2019 1:59 pm
>
> 
andree wrote: ↑Fri Jul 26, 2019 9:46 am
Got a error when I used one of the .mot files from the final version's files.


Can you upload the .mdl files as the script need them? Thanks
[https://anonymousfiles.io/cOCbUh4H/](https://anonymousfiles.io/cOCbUh4H/)
Here is one of them.
## Post #5
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-07-26T12:45:19+00:00
- Post Title: Kill la Kill IF (Switch Demo)

> Reply from andree ↑Fri Jul 26, 2019 8:18 pm at Fri Jul 26, 2019 8:18 pm
>
> 
Here is one of them.

Try this one with a minor fix, worked well with your .mdl and .mot

[fmt_KilllaKill_MOT.zip](https://xentaxbackup.github.io/file/16529_fmt_KilllaKill_MOT.zip)
## Post #6
- Username: Rotock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 20, 2014 3:07 am
- Post datetime: 2019-07-26T15:40:42+00:00
- Post Title: Kill la Kill IF (Switch Demo)

hmm your script seams kinda to work on the steam version also. 
I could decompress a .pac file into more files and loaded with noesis42 the .mdl file.
But don't know about the textures and then i try to export it, to fbx, dae ,smd, etc., and importing it into Blender, it always seem to have no weights. Bones do nothing to the model.
[d57ko5dkos57o.jpg](https://xentaxbackup.github.io/file/16531_d57ko5dkos57o.jpg)
## Post #7
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2019-07-26T18:57:09+00:00
- Post Title: Kill la Kill IF (Switch Demo)

How do you decrypt pac files with your script? [Edited]. How to find textures for models?
## Post #8
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2019-07-26T20:09:12+00:00
- Post Title: Kill la Kill IF (Switch Demo)

> Reply from Rotock ↑Fri Jul 26, 2019 11:40 pm at Fri Jul 26, 2019 11:40 pm
>
> 
hmm your script seams kinda to work on the steam version also. 
I could decompress a .pac file into more files and loaded with noesis42 the .mdl file.
But don't know about the textures and then i try to export it, to fbx, dae ,smd, etc., and importing it into Blender, it always seem to have no weights. Bones do nothing to the model.

Yeah the PC format changed a bit so I updated it. This zip also has a regular python script to extract textures from CVTs (They're mostly just DDS files with 80 bytes of nonsense).

Thanks andy97 for catching that embarrassing bug.

Its worth pointing out in case I get asked, some animations will look weird and broken but they are actually correct. The game does a lot of perspective tricks to get the look they want. Except for the animation frame rate. Frames are numbered, not timed. I wasn't sure what to do about that so I just hacked something together.
[fmt_KilllaKill_mdl.zip](https://xentaxbackup.github.io/file/16534_fmt_KilllaKill_mdl.zip)
## Post #9
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-07-26T20:40:56+00:00
- Post Title: Kill la Kill IF (Switch Demo)

> Reply from Simguy ↑Sat Jul 27, 2019 4:09 am at Sat Jul 27, 2019 4:09 am
>
> 
Rotock wrote: ↑Fri Jul 26, 2019 11:40 pm
hmm your script seams kinda to work on the steam version also. 
I could decompress a .pac file into more files and loaded with noesis42 the .mdl file.
But don't know about the textures and then i try to export it, to fbx, dae ,smd, etc., and importing it into Blender, it always seem to have no weights. Bones do nothing to the model.


Yeah the PC format changed a bit so I updated it. This zip also has a regular python script to extract textures from CVTs (They're mostly just DDS files with 80 bytes of nonsense).

Thanks andy97 for catching that embarrassing bug.

Its worth pointing out in case I get asked, some animations will look weird and broken but they are actually correct. The game does a lot of perspective tricks to get the look they want. Except for the animation frame rate. Frames are numbered, not timed. I wasn't sure what to do about that so I just hacked something together.

Any of the dds-readable programs won't read the files I had converted from the switch version.
[viewtopic.php?f=18&t=20860](https://forum.xentax.com/viewtopic.php?f=18&t=20860)
## Post #10
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2019-07-26T21:11:09+00:00
- Post Title: Kill la Kill IF (Switch Demo)

In Noesis model loads with pink textures, but in blender or 3ds max model loading fine, bone=weight is working, thanks for script.
## Post #11
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2019-07-26T21:30:29+00:00
- Post Title: Kill la Kill IF (Switch Demo)

> Reply from andree ↑Sat Jul 27, 2019 4:40 am at Sat Jul 27, 2019 4:40 am
>
> 
Simguy wrote: ↑Sat Jul 27, 2019 4:09 am
Rotock wrote: ↑Fri Jul 26, 2019 11:40 pm
hmm your script seams kinda to work on the steam version also. 
I could decompress a .pac file into more files and loaded with noesis42 the .mdl file.
But don't know about the textures and then i try to export it, to fbx, dae ,smd, etc., and importing it into Blender, it always seem to have no weights. Bones do nothing to the model.


Yeah the PC format changed a bit so I updated it. This zip also has a regular python script to extract textures from CVTs (They're mostly just DDS files with 80 bytes of nonsense).

Thanks andy97 for catching that embarrassing bug.

Its worth pointing out in case I get asked, some animations will look weird and broken but they are actually correct. The game does a lot of perspective tricks to get the look they want. Except for the animation frame rate. Frames are numbered, not timed. I wasn't sure what to do about that so I just hacked something together.


Any of the dds-readable programs won't read the files I had converted from the switch version.
viewtopic.php?f=18&t=20860

Ah thats my bad. I forgot to say that the PC version has DDS textures, that script might not work with all Switch CVTs. The Switch version uses BNTX textures, change the extension to bntx after running the script and noesis will load it.
> Reply from pechenuxa ↑Sat Jul 27, 2019 5:11 am at Sat Jul 27, 2019 5:11 am
>
> 
In Noesis model loads with pink textures, but in blender or 3ds max model loading fine, bone=weight is working, thanks for script.

Actually that pink color are the Vertex Colors. Its very important for replicating the shading in the game.
## Post #12
- Username: Rotock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 20, 2014 3:07 am
- Post datetime: 2019-07-26T22:51:47+00:00
- Post Title: Kill la Kill IF (Switch Demo)

Testfile: MDL_C010_RYU.pac

Mesh: there is a strange split on the main body
UV: works
Bones/Weights: works
Texture Export: works

I can work with this now.

Thanks Simguy for the Tools/Scripts.




a456jiya6ikyas6aik.jpg (40.1 KiB) Viewed 975 times
## Post #13
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2019-07-26T23:34:35+00:00
- Post Title: Kill la Kill IF (Switch Demo)

the klk_switch.py gives me an error when i try to run it, is there an updated version
## Post #14
- Username: Unari
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jan 31, 2019 12:53 pm
- Post datetime: 2019-07-27T06:26:51+00:00
- Post Title: Kill la Kill IF (Switch Demo)

Is there a way to preserve the Normals when merging vertices? or rather export the from noesis already merged?
## Post #15
- Username: Blur
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 26, 2019 8:58 pm
- Post datetime: 2019-07-27T08:22:55+00:00
- Post Title: Kill la Kill IF (Switch Demo)

> Reply from Rotock ↑Fri Jul 26, 2019 11:40 pm at Fri Jul 26, 2019 11:40 pm
>
> 
hmm your script seams kinda to work on the steam version also. 
I could decompress a .pac file into more files and loaded with noesis42 the .mdl file.
But don't know about the textures and then i try to export it, to fbx, dae ,smd, etc., and importing it into Blender, it always seem to have no weights. Bones do nothing to the model.

Mind telling me what you used to unpack the pac file? Been curious.
## Post #16
- Username: Rotock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 20, 2014 3:07 am
- Post datetime: 2019-07-27T09:07:47+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from Blur ↑Sat Jul 27, 2019 4:22 pm at Sat Jul 27, 2019 4:22 pm
>
> 
Rotock wrote: ↑Fri Jul 26, 2019 11:40 pm
hmm your script seams kinda to work on the steam version also. 
I could decompress a .pac file into more files and loaded with noesis42 the .mdl file.
But don't know about the textures and then i try to export it, to fbx, dae ,smd, etc., and importing it into Blender, it always seem to have no weights. Bones do nothing to the model.


Mind telling me what you used to unpack the pac file? Been curious.

Just the stuff that was uploaded here from "Simguy" 
I have installed phyton for windows. 
And then i could just drag and drop the .pac file over the "KLK_Switch.py" so that the file has the filepath automaticly 
Then it exports the stuff into an EXT folder in the folder where "KLK_Switch.py" is located.

You can do the same with the .cvt files. just drag and drop onto the "KilllaKill_CVT.py" file. 
And it exports the texture file into the same folder with .dds ending. I had then converted this .dds file with XnConvert to png.
## Post #17
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-07-27T09:49:03+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

It seems like vertex colors break after exporting as fbx and importing into 3ds max, not sure if this can be solved or not..
## Post #18
- Username: Rotock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 20, 2014 3:07 am
- Post datetime: 2019-07-27T10:23:02+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

strange
I just have used all the newest scripts. but simguy also said something about the files are different between pc and switch version. 
Maybe you should use the first one if you have switch files and second version if its pc stuff. 
For me the normals seems fine, then i export it in xna format and then import it into blender with xps_tools. 
noessis export to an too old fbx version, that blender cannot open.
## Post #19
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-07-27T13:00:33+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

mmm well here's the thing, I'm not a blender user, and I hate the user interface with blender too, so I refuse to use that, it's far too complicated for me.
## Post #20
- Username: Rotock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 20, 2014 3:07 am
- Post datetime: 2019-07-27T15:13:11+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from demonslayerx8 ↑Sat Jul 27, 2019 9:00 pm at Sat Jul 27, 2019 9:00 pm
>
> 
mmm well here's the thing, I'm not a blender user, and I hate the user interface with blender too, so I refuse to use that, it's far too complicated for me.

Never said you should use blender.   

Only that the normals and vertexcolor looked ok in it. 
So maybe its not allready broken in noesis. maybe you should tryan  other export methots in noesis.

I did use an XNA exporter. because the fbx that noeses exports use an very old format.
## Post #21
- Username: cryrav
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 07, 2019 12:56 am
- Post datetime: 2019-07-27T17:05:30+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

Thanks Simguy tools work fine
## Post #22
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2019-07-27T21:34:47+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from Rotock ↑Sat Jul 27, 2019 5:07 pm at Sat Jul 27, 2019 5:07 pm
>
> 
Blur wrote: ↑Sat Jul 27, 2019 4:22 pm
Rotock wrote: ↑Fri Jul 26, 2019 11:40 pm
hmm your script seams kinda to work on the steam version also. 
I could decompress a .pac file into more files and loaded with noesis42 the .mdl file.
But don't know about the textures and then i try to export it, to fbx, dae ,smd, etc., and importing it into Blender, it always seem to have no weights. Bones do nothing to the model.


Mind telling me what you used to unpack the pac file? Been curious.


Just the stuff that was uploaded here from "Simguy" 
I have installed phyton for windows. 
And then i could just drag and drop the .pac file over the "KLK_Switch.py" so that the file has the filepath automaticly 
Then it exports the stuff into an EXT folder in the folder where "KLK_Switch.py" is located.

You can do the same with the .cvt files. just drag and drop onto the "KilllaKill_CVT.py" file. 
And it exports the texture file into the same folder with .dds ending. I had then converted this .dds file with XnConvert to png.

What did you do to run the .py to extract the .pac?
## Post #23
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2019-07-27T23:52:14+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

I use the Switch script in the OP to extract the *.pac file. Then the *.mdl files will then load in Noesis through the mdl script that TC posted later in the thread. However, the cvt script from that same post doesn't extract anything for me. I'm using python 36, do I need to install yet another version? 

I'm using command prompt to run these scripts. No error pops up.

Edit: Using PC game files.
## Post #24
- Username: cenjianneng
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 2:58 am
- Post datetime: 2019-07-28T09:10:56+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from cryrav ↑Sun Jul 28, 2019 1:05 am at Sun Jul 28, 2019 1:05 am
>
> 
Thanks Simguy tools work fine

how to import animation files in blender?
## Post #25
- Username: Blur
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 26, 2019 8:58 pm
- Post datetime: 2019-07-28T09:34:15+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

This is great!! Even the vertex normals are here just like in the game. Coould make a use out of these. Thanks Simguy and Rotock!!
[unknown.jpg](https://xentaxbackup.github.io/file/16542_unknown.jpg)
## Post #26
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2019-07-28T11:12:07+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from ssringo ↑Sun Jul 28, 2019 7:52 am at Sun Jul 28, 2019 7:52 am
>
> 
I use the Switch script in the OP to extract the *.pac file. Then the *.mdl files will then load in Noesis through the mdl script that TC posted later in the thread. However, the cvt script from that same post doesn't extract anything for me. I'm using python 36, do I need to install yet another version? 

I'm using command prompt to run these scripts. No error pops up.

Edit: Using PC game files.

I've tried that, keeps giving me an error, do I need a specific version of python?
## Post #27
- Username: cryrav
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 07, 2019 12:56 am
- Post datetime: 2019-07-28T12:28:22+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from cenjianneng ↑Sun Jul 28, 2019 5:10 pm at Sun Jul 28, 2019 5:10 pm
>
> 

how to import animation files in blender?

.smd format works quite well for importing animation into a blender.
## Post #28
- Username: cenjianneng
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 2:58 am
- Post datetime: 2019-07-28T14:27:15+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from cryrav ↑Sun Jul 28, 2019 8:28 pm at Sun Jul 28, 2019 8:28 pm
>
> 
cenjianneng wrote: ↑Sun Jul 28, 2019 5:10 pm

how to import animation files in blender?


smd. format works quite well for importing animation into a blender.

Thanks, It working
## Post #29
- Username: Rotock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 20, 2014 3:07 am
- Post datetime: 2019-07-28T17:09:19+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from Blur ↑Sun Jul 28, 2019 5:34 pm at Sun Jul 28, 2019 5:34 pm
>
> 
This is great!! Even the vertex normals are here just like in the game. Coould make a use out of these. Thanks Simguy and Rotock!!

lol i didn't do anything but ok. Just a traveler that ended up here and found some nice scripts.

Still not tested if all models work, because no time.
Also i find it funny that most of here used the exact same model for testing.   

And the ones with the errors, it would be maybe wise to post the error massage, so a wise guy can figures it out on the error message, to help.
## Post #30
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2019-07-28T17:45:41+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

Better add PC samples
## Post #31
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2019-07-28T18:49:51+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

I don't get error messages, the cvt extract/convert just closes and nothing else. I guess I misunderstood what was posted and thought everything was working for PC and Switch files. 

Here's a batch of Ryuko's models from the PC version. I can upload other characters later if needed.

[https://www.mediafire.com/file/jwszq3c8 ... s.rar/file](https://www.mediafire.com/file/jwszq3c8i34682d/Ryuko_models.rar/file)
## Post #32
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2019-07-28T22:31:18+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

explain how the script KLK_Switch works please
## Post #33
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2019-07-29T02:07:10+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

hey what version of python do i need for the script that extracts the pacs? its just kinda not working for me and all i can really think is that i have the wrong python version installed
## Post #34
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2019-07-29T03:22:19+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

Only problem i've had with the PC version so far is that weight paints arent saving when exported from noesis but everything else is fine. I did make a very basic quick bms script to split the pacs. It doesn't properly handle the illumination textures but everything else seems to be fine.




[KLK_Pac.zip](https://xentaxbackup.github.io/file/16544_KLK_Pac.zip)
## Post #35
- Username: Blur
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 26, 2019 8:58 pm
- Post datetime: 2019-07-29T06:51:39+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from Rotock ↑Mon Jul 29, 2019 1:09 am at Mon Jul 29, 2019 1:09 am
>
> 
Blur wrote: ↑Sun Jul 28, 2019 5:34 pm
This is great!! Even the vertex normals are here just like in the game. Coould make a use out of these. Thanks Simguy and Rotock!!


lol i didn't do anything but ok. Just a traveler that ended up here and found some nice scripts.

Still not tested if all models work, because no time.
Also i find it funny that most of here used the exact same model for testing.   

And the ones with the errors, it would be maybe wise to post the error massage, so a wise guy can figures it out on the error message, to help.

You did let me know how to use the scripts. Honestly, don't think I could've figured it out on my own.
## Post #36
- Username: Blur
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 26, 2019 8:58 pm
- Post datetime: 2019-07-29T10:23:47+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from Simguy ↑Sat Jul 27, 2019 5:30 am at Sat Jul 27, 2019 5:30 am
>
> 
andree wrote: ↑Sat Jul 27, 2019 4:40 am
Simguy wrote: ↑Sat Jul 27, 2019 4:09 am


Yeah the PC format changed a bit so I updated it. This zip also has a regular python script to extract textures from CVTs (They're mostly just DDS files with 80 bytes of nonsense).

Thanks andy97 for catching that embarrassing bug.

Its worth pointing out in case I get asked, some animations will look weird and broken but they are actually correct. The game does a lot of perspective tricks to get the look they want. Except for the animation frame rate. Frames are numbered, not timed. I wasn't sure what to do about that so I just hacked something together.


Any of the dds-readable programs won't read the files I had converted from the switch version.
viewtopic.php?f=18&t=20860


Ah thats my bad. I forgot to say that the PC version has DDS textures, that script might not work with all Switch CVTs. The Switch version uses BNTX textures, change the extension to bntx after running the script and noesis will load it.pechenuxa wrote: ↑Sat Jul 27, 2019 5:11 am
In Noesis model loads with pink textures, but in blender or 3ds max model loading fine, bone=weight is working, thanks for script.  


Actually that pink color are the Vertex Colors. Its very important for replicating the shading in the game.

I'm wondering if you know a way to export the vertex colors as well from Noesis.
## Post #37
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2019-07-29T11:15:30+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from ssringo ↑Sun Jul 28, 2019 7:52 am at Sun Jul 28, 2019 7:52 am
>
> 
I use the Switch script in the OP to extract the *.pac file. Then the *.mdl files will then load in Noesis through the mdl script that TC posted later in the thread. However, the cvt script from that same post doesn't extract anything for me. I'm using python 36, do I need to install yet another version? 

I'm using command prompt to run these scripts. No error pops up.

Edit: Using PC game files.

Can you please explain how to run the script in the CMD, im not familiar with the proper way to execute it, the script to .pac.
## Post #38
- Username: mikoamoy
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 11, 2014 6:34 pm
- Post datetime: 2019-07-29T13:46:20+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

Download python latest version, and drag the mdl into the KLKmdl.py
Make sure your python is installed properly in your PC.
You could use the pac.bms at above post.
## Post #39
- Username: ggnaarlyy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 28, 2019 8:06 am
- Post datetime: 2019-07-29T21:02:30+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

I was able to get the textures to load onto the model (from bntx to png) and the model is fine in noesis, but when I load it into blender I can't see any textures, exported it as an .obj, the textures load when I open the .obj in noesis but now in blender
## Post #40
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-07-29T21:48:00+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

neat samples. i'd guess the render engine is based on ggxrd. the ilm textures are really odd ball that doesn't work, but they don't contain alot of needed information. the rest works. good stuff.

the models are not my preferred type of body shape tho. nor are the faces any good, rather then flexing a blowjob tunnel. mmh.
## Post #41
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-11-18T21:25:29+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

[https://anonymousfiles.io/WgzRKFAF/](https://anonymousfiles.io/WgzRKFAF/)
[https://anonymousfiles.io/G2VUh9XZ/](https://anonymousfiles.io/G2VUh9XZ/)
Several .mot files aren't loaded properly, can anyone fix it?
## Post #42
- Username: Bettyaoi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 11, 2020 9:41 pm
- Post datetime: 2020-03-11T14:07:31+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from Rotock ↑Sat Jul 27, 2019 5:07 pm at Sat Jul 27, 2019 5:07 pm
>
> 
Blur wrote: ↑Sat Jul 27, 2019 4:22 pm
Rotock wrote: ↑Fri Jul 26, 2019 11:40 pm
hmm your script seams kinda to work on the steam version also. 
I could decompress a .pac file into more files and loaded with noesis42 the .mdl file.
But don't know about the textures and then i try to export it, to fbx, dae ,smd, etc., and importing it into Blender, it always seem to have no weights. Bones do nothing to the model.


Mind telling me what you used to unpack the pac file? Been curious.


Just the stuff that was uploaded here from "Simguy" 
I have installed phyton for windows. 
And then i could just drag and drop the .pac file over the "KLK_Switch.py" so that the file has the filepath automaticly 
Then it exports the stuff into an EXT folder in the folder where "KLK_Switch.py" is located.

You can do the same with the .cvt files. just drag and drop onto the "KilllaKill_CVT.py" file. 
And it exports the texture file into the same folder with .dds ending. I had then converted this .dds file with XnConvert to png.
It doesn't seem to work for me
## Post #43
- Username: Bettyaoi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 11, 2020 9:41 pm
- Post datetime: 2020-03-13T19:10:39+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

I get this when I launch Noesis, anyone has a fix for this ?
[i get this.PNG](https://xentaxbackup.github.io/file/17706_i get this.PNG)
## Post #44
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-03-17T12:42:45+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from Bettyaoi ↑Sat Mar 14, 2020 3:10 am at Sat Mar 14, 2020 3:10 am
>
> 
I get this when I launch Noesis, anyone has a fix for this ?

Did you put this into the right folder?
## Post #45
- Username: PuellaSins
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 03, 2020 2:46 am
- Post datetime: 2020-10-02T04:52:08+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

This topic is a bit old, but I seem to have issues getting the script to unpack the .pac files. I have Python installed, but when I drag the .pac file over KLK_Switch.py, nothing happens (Like it won't even let me drag it into the script). Anyone know why it's doing this?

Edit: I realized I was trying to use a 32 bit python instead of 64 bit, my bad. 

Do you think there is a way to repack .pac files for modding purposes?
## Post #46
- Username: RaikuFarts69
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 18, 2020 1:44 pm
- Post datetime: 2020-10-18T06:25:05+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from PuellaSins ↑Fri Oct 02, 2020 12:52 pm at Fri Oct 02, 2020 12:52 pm
>
> 
This topic is a bit old, but I seem to have issues getting the script to unpack the .pac files. I have Python installed, but when I drag the .pac file over KLK_Switch.py, nothing happens (Like it won't even let me drag it into the script). Anyone know why it's doing this?

Edit: I realized I was trying to use a 32 bit python instead of 64 bit, my bad. 

Do you think there is a way to repack .pac files for modding purposes?

you can use quickbms to unpack/repack .pac files using a .bms file. The one below should work for all of them in the PC version at least. I've made a few mods myself that i'll probably share on steam or something in the nearish future.


also has anyone figured out how to swap out models, so we can play as pajama ryuko??


```
get unknownValue long
get null long
get fileCount long
get unknownValue2 long
get null long
get null long
get null long

get null long
get null long
get null long
get null long

for i = 0 < fileCount
   get unknownidstring long
   get unknownValueLoop long
   get length long
   get pointer long
   getdstring name 0x20
   log name pointer length
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
next i
```
## Post #47
- Username: shockwave787
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 18, 2020 3:02 pm
- Post datetime: 2020-10-18T19:15:42+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

I know this is an old thread & all, but im just wondering how exactly would i go about getting animation files from all of this. im completely lost in that regard lol
## Post #48
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2021-01-10T19:32:44+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

Does this work for the PC (Steam) Version?
## Post #49
- Username: Puppet3747
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 01, 2022 9:44 pm
- Post datetime: 2022-01-07T14:34:52+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

i tried to extract the texture files from .pac > .cvt > .dds, i want to replace the second texture (the completely black one) of ryuko, but i don't know how to convert the file from .dds > .cvt, does anyone have any ideas?
## Post #50
- Username: RaikuFarts69
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 18, 2020 1:44 pm
- Post datetime: 2022-01-08T04:06:03+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

.cvt files are just .dds files with a unique header (different for each file), so to convert from .cvt > .dds, delete (not just null) everything before "DDS"(ie the first 50 bytes of the file), and to convert from .dds > .cvt, you just have to insert the stuff that was deleted.
## Post #51
- Username: RaikuFarts69
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 18, 2020 1:44 pm
- Post datetime: 2022-01-08T17:13:56+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

Also I made a modding guide
[https://drive.google.com/file/d/17QdQJP ... sp=sharing](https://drive.google.com/file/d/17QdQJPVabGCqwMXzeJeyX2rGdxrdpgt5/view?usp=sharing)
## Post #52
- Username: RuV9999
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 19, 2019 11:00 pm
- Post datetime: 2022-05-26T23:01:02+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

> Reply from RaikuFarts69 ↑Sun Oct 18, 2020 2:25 pm at Sun Oct 18, 2020 2:25 pm
>
> 
PuellaSins wrote: ↑Fri Oct 02, 2020 12:52 pm
This topic is a bit old, but I seem to have issues getting the script to unpack the .pac files. I have Python installed, but when I drag the .pac file over KLK_Switch.py, nothing happens (Like it won't even let me drag it into the script). Anyone know why it's doing this?

Edit: I realized I was trying to use a 32 bit python instead of 64 bit, my bad. 

Do you think there is a way to repack .pac files for modding purposes?


you can use quickbms to unpack/repack .pac files using a .bms file. The one below should work for all of them in the PC version at least. I've made a few mods myself that i'll probably share on steam or something in the nearish future.


also has anyone figured out how to swap out models, so we can play as pajama ryuko??

Code: Select allidstring "DGKP"
get unknownValue long
get null long
get fileCount long
get unknownValue2 long
get null long
get null long
get null long

get null long
get null long
get null long
get null long

for i = 0 < fileCount
   get unknownidstring long
   get unknownValueLoop long
   get length long
   get pointer long
   getdstring name 0x20
   log name pointer length
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
   get null long
   get null long
   get null long
   get null long
   
next i
so...how it works it drag and drop fmt Mdl py file into quickbms and then choose MDL pac and then choose the output right? but why im getting error by that? is there another way to do that?
## Post #53
- Username: epicminecrafter31
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 11, 2022 1:41 pm
- Post datetime: 2023-01-16T02:40:48+00:00
- Post Title: Re: Kill la Kill IF (Switch Demo)

Anyone know what this error is? It pops up after trying to load the MOT file with the Noesis script
[KLKerror.PNG](https://xentaxbackup.github.io/file/23303_KLKerror.PNG)
