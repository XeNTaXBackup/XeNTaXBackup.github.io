## Post #1
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2016-04-07T05:41:29+00:00
- Post Title: [PC] Quantum Break .RMDP

Can anyone come up with a tool to extract the files? Here are a few files from the game - [https://yadi.sk/d/EGcT63GyqoJaB](https://yadi.sk/d/EGcT63GyqoJaB)
I tried to use the [Alan Wake Tool](http://forum.xentax.com/viewtopic.php?f=33&t=8411), but the program showed errors.
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-04-07T05:52:21+00:00
- Post Title: [PC] Quantum Break .RMDP

is it possible to modify files anyhow ? We would like to do localization. If so i will have a look on files..
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-07T12:52:35+00:00
- Post Title: [PC] Quantum Break .RMDP

The format looks fairly simple. Fortunately, the .xml file contains all information needed so we pretty much know exactly what the header is for the .bin file.

So the toc is located in the .bin file, the actual file data is stored within the .rmdp file.
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2016-04-10T17:59:03+00:00
- Post Title: [PC] Quantum Break .RMDP

It is in alpha/beta stage, but I can unpack texts, and files.
I'll release soon, after I fixed some bug.
[QBText.jpg](https://xentaxbackup.github.io/file/10754_QBText.jpg)
## Post #5
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-04-10T21:00:28+00:00
- Post Title: [PC] Quantum Break .RMDP

> Reply from evin
>
> It is in alpha/beta stage, but I can unpack texts, and files.
I'll release soon, after I fixed some bug.

its Will be really nice if there any tools to edit .binfnt
## Post #6
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2016-04-11T20:00:12+00:00
- Post Title: [PC] Quantum Break .RMDP

The beta tool: [viewtopic.php?f=32&t=14214](http://forum.xentax.com/viewtopic.php?f=32&t=14214)

Sajjad Rahim
Open the .binfnt with hex editor, search the "DDS" string, and before DDS, delete everything. And rename .binfnt to .dds. Now you have the font file.
This tool can handle the container file, not the fonts.
## Post #7
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2016-04-12T03:32:43+00:00
- Post Title: [PC] Quantum Break .RMDP

> Reply from evin
>
> It is in alpha/beta stage, but I can unpack texts, and files.
I'll release soon, after I fixed some bug.

string table .bin Missing?
## Post #8
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2016-04-12T05:03:35+00:00
- Post Title: [PC] Quantum Break .RMDP

> Reply from MuratG
>
> evin wrote:It is in alpha/beta stage, but I can unpack texts, and files.
I'll release soon, after I fixed some bug.

string table .bin Missing?

You should read the info.rtf first: No text extractor function in the tool, to avoid the steeling of unofficial translations!
You loaded the text .bin file!

Also About button in the Tool: 
"What is missing or need to fix:... - text file handler ..."
I'll attach to the tool the unpacked text file, after I fixed the text handler functions.
## Post #9
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2016-04-14T05:14:09+00:00
- Post Title: [PC] Quantum Break .RMDP

The tool is updated, but it is still NOT the final version! [viewtopic.php?f=32&t=14214](http://forum.xentax.com/viewtopic.php?f=32&t=14214)
If you want to translate the game, you can start it now, every details in the package. Maybe you cannot test it because the game maybe won't accept the new bin/rmdp file. I couldn't test is, because I don't have the game yet. But I'll fix it until the final version.
## Post #10
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2016-04-16T21:56:00+00:00
- Post Title: [PC] Quantum Break .RMDP

> Reply from evin
>
> The beta tool: viewtopic.php?f=32&t=14214

Sajjad Rahim
Open the .binfnt with hex editor, search the "DDS" string, and before DDS, delete everything. And rename .binfnt to .dds. Now you have the font file.
This tool can handle the container file, not the fonts.

How to edit binfnt to dds files..
## Post #11
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-04-20T04:47:22+00:00
- Post Title: [PC] Quantum Break .RMDP

Can we edit engine files for graphics yet?
## Post #12
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2016-04-23T00:01:38+00:00
- Post Title: [PC] Quantum Break .RMDP

yeah would like to extract textures.
## Post #13
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2016-04-23T00:02:52+00:00
- Post Title: [PC] Quantum Break .RMDP

yeah would like to extract textures.
## Post #14
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-04-27T22:51:08+00:00
- Post Title: [PC] Quantum Break .RMDP

Attached is version 1.0 alpha of my *.wedmsh blender plugin for Quantum break.

Currently should import any mesh as a static object with UVs and in-game normals. if the file has multiple meshes (LODs or whatever), it will import all.

I will continue to do more work to add support for bone weights and materials, depending on what data I can uncover. if you run into any files that don't load properly, please let me know the filename/directory name. Thanks.

EDIT: new version released in subsequent post.
## Post #15
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2016-04-28T20:20:05+00:00
- Post Title: [PC] Quantum Break .RMDP

> Reply from volfin
>
> Attached is version 1.0 alpha of my *.wedmsh blender plugin for Quantum break.

-snip-

So the character models are in .wedmsh format too? 

Thank you for making the plugin by the way, I thought no one would bother.
## Post #16
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-04-28T21:27:49+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from meganmi
>
> volfin wrote:Attached is version 1.0 alpha of my *.wedmsh blender plugin for Quantum break.

-snip-

So the character models are in .wedmsh format too? 

Thank you for making the plugin by the way, I thought no one would bother.

I'm not sure about that yet, I have yet to find a character model. but there was a lot of unused records in the static mesh file, So I don't see why not. I plan to start looking for a char model today to find out.

And you're welcome.  

EDIT: yes seems characters are in wedmsh as well, as I suspected.



This model mostly loaded but crashed my script, I have a some work ahead it seems
## Post #17
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-04-29T02:12:30+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> Attached is version 1.0 alpha of my *.wedmsh blender plugin for Quantum break.

Currently should import any mesh as a static object with UVs and in-game normals. if the file has multiple meshes (LODs or whatever), it will import all.

I will continue to do more work to add support for bone weights and materials, depending on what data I can uncover. if you run into any files that don't load properly, please let me know the filename/directory name. Thanks.
Hello there this is amazing. So it has all UV mapping but what about textures and such? And placements? I might port this to some games if it has what i need.
## Post #18
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-04-29T03:27:05+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from d875j
>
> volfin wrote:Attached is version 1.0 alpha of my *.wedmsh blender plugin for Quantum break.

Currently should import any mesh as a static object with UVs and in-game normals. if the file has multiple meshes (LODs or whatever), it will import all.

I will continue to do more work to add support for bone weights and materials, depending on what data I can uncover. if you run into any files that don't load properly, please let me know the filename/directory name. Thanks.

Hello there this is amazing. So it has all UV mapping but what about textures and such? And placements? I might port this to some games if it has what i need.

I think it may be doable, but will take some time. Right now it looks like the associated textures are in folders with similar names to the model. I've already got materials definition working, which is an important part. right now puzzling out bone weights and indexes. I'm pretty close to finishing that part I think.
## Post #19
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-04-29T08:29:28+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Ok here's version 1.1

- Material groups are properly assigned to faces now, and named with the original ingame material names.
- Materials will be randomly colored if the option is enabled on the importer options. (enabled by default)
- Vertex colors are imported if present and the option is enabled on the importer options.
- Bone weights and indexes are assigned if present, and named with the original ingame bone names.
- Rigged meshes are now imported correctly in addition to static meshes.

Couple big notes:

   It has come to light this game engine allows up to 8 bone influences per vertex. I have imported all 8 just as it is ingame. But many other game engines only support 4 weight influences per vertex. So be aware.

There are a lot of bones. The one model I used as an example below has over 800 bones. So have fun with that. 





What's missing at this point is skeleton, and linking to related textures. I'll continue on to see what I can accomplish in regard to those two pieces.

Enjoy.  

EDIT: new version below.
## Post #20
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2016-04-29T12:51:24+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> -snip-

You are literally amazing!  

edit: Figured out where textures were.
## Post #21
- Username: kangmin
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 17, 2012 4:38 pm
- Post datetime: 2016-04-30T08:20:40+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

hi, curious where can i extract the sfx of the game? i really like the time stop/stuttering slowmo shockwave sound effects! thank you!
## Post #22
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-04-30T17:58:34+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from kangmin
>
> hi, curious where can i extract the sfx of the game? i really like the time stop/stuttering slowmo shockwave sound effects! thank you!
SFX are in the "soundbanks" directory, named *.wem 

These are WWise audio format, convert fine with the "ww2ogg" utility you can find on the forums or elsewhere on the internet. They use the alternate codebook, so command line would be like:

ww2ogg WHATEVER.WEM --pcb packed_codebooks_aoTuV_603.bin
## Post #23
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-01T00:13:20+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

I've made a some progress on the Skeleton:



But I still need to work on getting it oriented right and scaled to match the body. So not ready for release yet.  Soon
## Post #24
- Username: kangmin
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 17, 2012 4:38 pm
- Post datetime: 2016-05-01T05:04:49+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> kangmin wrote:hi, curious where can i extract the sfx of the game? i really like the time stop/stuttering slowmo shockwave sound effects! thank you!
SFX are in the "soundbanks" directory, named *.wem 

These are WWise audio format, convert fine with the "ww2ogg" utility you can find on the forums or elsewhere on the internet. They use the alternate codebook, so command line would be like:

ww2ogg WHATEVER.WEM --pcb packed_codebooks_aoTuV_603.bin

hi thanks for the reply.. im sorry , im kinda new to these stuff , if it doesn't bother you may i request a detailed instructions /program to use? , ive tried using quickbms before but only download codes from the net.. by the way i can see the .wem files is it inside the .rmdp file? im really sorry  i just really want those time stuttering soundfx  thanks again!
## Post #25
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-01T07:21:59+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Ok, 1.2 is released. And the final release I think. 

in this version:
- Added skeleton import. The importer opens the *.skel file with the same name as the *wedmsh file, this *.skel file must be in the same directory as the *.wedmsh.
- There is now an import option to put each LOD mesh on separate layers (see bottom of image).  This is enabled by default.
- There is now an import option to change import scale (3.0X normal by default, the default model is pretty tiny).  The armature is also scaled to match.
- I fixed a bug with the UV maps, they were coming in Upside-down.

 
Waving Hello

As far as I know this works with everything now. The only thing I wasn't really able to do was match Textures with materials. There doesn't seem to be any consistent naming between game files and material names in the mesh files. However, the material names are named specifically enough that finding the texture for it shouldn't be a huge problem.

If any problems are found, or suggestions for improvements, please let me know. Enjoy.  

EDIT: New version below.
## Post #26
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-01T07:25:56+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from kangmin
>
> volfin wrote:kangmin wrote:hi, curious where can i extract the sfx of the game? i really like the time stop/stuttering slowmo shockwave sound effects! thank you!
SFX are in the "soundbanks" directory, named *.wem 

These are WWise audio format, convert fine with the "ww2ogg" utility you can find on the forums or elsewhere on the internet. They use the alternate codebook, so command line would be like:

ww2ogg WHATEVER.WEM --pcb packed_codebooks_aoTuV_603.bin

hi thanks for the reply.. im sorry , im kinda new to these stuff , if it doesn't bother you may i request a detailed instructions /program to use? , ive tried using quickbms before but only download codes from the net.. by the way i can see the .wem files is it inside the .rmdp file? im really sorry  i just really want those time stuttering soundfx  thanks again!

Well nobody said anything about QuickBMS. If you read this thread, you'll see Evin made a program to unpack the game files. And then I already explained about the program called ww2ogg, you're just going to have to find it. Try google if you can't find it by searching here. That's all there is to it. Unpack game files with Evin's program, convert *.wem files with ww2ogg, Play ogg file to enjoy sound. Profit.
## Post #27
- Username: mrjosheyhalo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 01, 2016 11:46 am
- Post datetime: 2016-05-03T06:10:42+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

EDIT: Managed to solve it, beth wilders(betwil) model imported flipped was able to fix by mirroring it on x, texture issues were from not using the couhop shared textures.

Not sure if i am doing something wrong, but after importing with the blender plugin, the textures wont appear correctly after i add them.



Top is flipped on x and face doesnt show right, might be the wrong head texture but couldnt find another. Have tried hair as well and that doesnt work either.

Ive tried the option to flip x and y of texture but that doesnt help.

edit: was using wrong face texture, still cant fix the shirt texture.

edit 2: the spot on the model for the emblem is on right side as well, is the model flipped?
## Post #28
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-03T17:53:24+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from mrjosheyhalo
>
> EDIT: Managed to solve it, beth wilders(betwil) model imported flipped was able to fix by mirroring it on x, texture issues were from not using the couhop shared textures.

Not sure if i am doing something wrong, but after importing with the blender plugin, the textures wont appear correctly after i add them.



Top is flipped on x and face doesnt show right, might be the wrong head texture but couldnt find another. Have tried hair as well and that doesnt work either.

Ive tried the option to flip x and y of texture but that doesnt help.

edit: was using wrong face texture, still cant fix the shirt texture.

edit 2: the spot on the model for the emblem is on right side as well, is the model flipped?

It's possible the model is flipped. That's very hard to detect unless you find something like that shirt texture to tell you.   I'll look into it and if so put out an update.

EDIT: based on this in-game image, seems the X should be on the left arm, so appears only the UV is flipped ( I guess it was flipped on both axis, not just one like I thought).  Will fix shortly



no you're right, it's not UV, it's the model. darn, will take a bit more work.
## Post #29
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-03T19:21:09+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Got it finally. Flipping the model was easy, but Flipping the skeleton to match as I constructed it, was a bit more tricky. gotta love quaternions.   



All is good now. Sorry about that.  

Edit: newer version here: [viewtopic.php?p=126734#p126734](http://forum.xentax.com/viewtopic.php?p=126734#p126734)
## Post #30
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-05-03T21:23:23+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Any more progress on map? I still looking forward to convert the map.
## Post #31
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-03T21:39:09+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from d875j
>
> Any more progress on map? I still looking forward to convert the map.
I'm not sure what map you mean. All meshes appear to be in wedmsh format. if there's a wedmsh that's not loading properly, please give name and location.
If you mean something else, please elaborate.
## Post #32
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-05-04T03:33:02+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> d875j wrote:Any more progress on map? I still looking forward to convert the map.
I'm not sure what map you mean. All meshes appear to be in wedmsh format. if there's a wedmsh that's not loading properly, please give name and location.
If you mean something else, please elaborate.
Like for instance do the models have placements embedded? And what about textures. Also i really like a 3ds max plugin i really dislike blender i really don't know how to work blender.
## Post #33
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-04T03:40:47+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from d875j
>
> volfin wrote:d875j wrote:Any more progress on map? I still looking forward to convert the map.
I'm not sure what map you mean. All meshes appear to be in wedmsh format. if there's a wedmsh that's not loading properly, please give name and location.
If you mean something else, please elaborate.
Like for instance do the models have placements embedded? And what about textures. Also i really like a 3ds max plugin i really dislike blender i really don't know how to work blender.

well, I really like blender, so that's what I spend my freely donated time creating plugins for. You're free to convert my plugin to another application if you like. or simply save the mesh from blender as FBX or other format, then load it into 3ds Max. Nobody says you have to use blender beyond converting the mesh to a usable format.

As stated earlier, textures are in named folders, you have to find them and match them up yourself. For example, if the material name in blender is "amyfer_tops_chest_amyfer_chest", then chances are the texture you need will be in the 'tops' directory and be named 'amyfer_chest" or something close to that. you just need to apply a little logic, and trial and error.

As for trying to recreate the whole level layout, you're likely going to have to do that by hand. not only do I have no idea where that kind of data is stored, I have zero motivation to try to do that. But every single piece of mesh for every level, is available, as a wedmsh. think of it as a jigsaw puzzle.
## Post #34
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-05-04T03:52:45+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> 
well, I really like blender, so that's what I spend my freely donated time creating plugins for. You're free to convert my plugin to another application if you like. or simply save the mesh from blender as FBX or other format, then load it into 3ds Max. Nobody says you have to use blender beyond converting the mesh to a usable format.

As stated earlier, textures are in named folders, you have to find them and match them up yourself. For example, if the material name in blender is "amyfer_tops_chest_amyfer_chest", then chances are the texture you need will be in the 'tops' directory and be named 'amyfer_chest" or something close to that. you just need to apply a little logic, and trial and error.

As for trying to recreate the whole level layout, you're likely going to have to do that by hand. not only do I have no idea where that kind of data is stored, I have zero motivation to try to do that. But every single piece of mesh for every level, is available, as a wedmsh. think of it as a jigsaw puzzle.
I was afraid you were gonna say that. I really need them not to be jigsawed up. I need them to have the coordinates and such. So how do i use your plugin on blender so i can import some stuff and take a look around?
## Post #35
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-04T20:11:00+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from d875j
>
> I was afraid you were gonna say that. I really need them not to be jigsawed up. I need them to have the coordinates and such. So how do i use your plugin on blender so i can import some stuff and take a look around?

I posted a brief tutorial on how to install a blender plugin here:  [viewtopic.php?p=103131#p103131](http://forum.xentax.com/viewtopic.php?p=103131#p103131)

most info is the same, except for that game, my skeleton importer was separate. just ignore everything about hkx_cvt.exe and valve's SMD importer.
## Post #36
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-05-04T22:46:18+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> d875j wrote:I was afraid you were gonna say that. I really need them not to be jigsawed up. I need them to have the coordinates and such. So how do i use your plugin on blender so i can import some stuff and take a look around?

I posted a brief tutorial on how to install a blender plugin here:  viewtopic.php?p=103131#p103131

most info is the same, except for that game, my skeleton importer was separate. just ignore everything about hkx_cvt.exe and valve's SMD importer.
Thank you. But yeah it needs coordinates and such for map related to work. But still useful to get player models. I seriously think you should give it a shot at map related more tho. I would do myself but i'm not experience in this field of cracking it.
## Post #37
- Username: mrjosheyhalo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 01, 2016 11:46 am
- Post datetime: 2016-05-07T12:54:50+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Not sure if anyone noticed but the .binfbx.meta for a model contains a list of texture locations, i asume its for when the game is running as its doesnt match the normal file stucture but the last folder name and file name looks to be its location.

example

file says "sourcedata\\textures\\characters\\shared\\male_aidgil\\male_aidgil_tongue_d.tga"

its in "male_aidgil\male_aidgil_tongue_d.dds"

Not sure if its right for all files but its looks to be right so far, it doesn't need to be added to the plugin but it would be nice if it was looking for textures.
## Post #38
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-05-07T17:04:42+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from mrjosheyhalo
>
> Not sure if anyone noticed but the .binfbx.meta for a model contains a list of texture locations, i asume its for when the game is running as its doesnt match the normal file stucture but the last folder name and file name looks to be its location.

example

file says "sourcedata\\textures\\characters\\shared\\male_aidgil\\male_aidgil_tongue_d.tga"

its in "male_aidgil\male_aidgil_tongue_d.dds"

Not sure if its right for all files but its looks to be right so far, it doesn't need to be added to the plugin but it would be nice if it was looking for textures.

That's the folder they sourced the DDS from before conversion. but there's still no way to tie that to any particular material on any particular model in a reliable way. If someone can show me a way to to *reliably* tie model materials to textures, I'll implement it.
## Post #39
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-05-08T09:30:25+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from mrjosheyhalo
>
> Not sure if anyone noticed but the .binfbx.meta for a model contains a list of texture locations, i asume its for when the game is running as its doesnt match the normal file stucture but the last folder name and file name looks to be its location.

example

file says "sourcedata\\textures\\characters\\shared\\male_aidgil\\male_aidgil_tongue_d.tga"

its in "male_aidgil\male_aidgil_tongue_d.dds"

Not sure if its right for all files but its looks to be right so far, it doesn't need to be added to the plugin but it would be nice if it was looking for textures.
It's not really too hard to manually do it. But i'm certain in future he could add it in.
## Post #40
- Username: mrjosheyhalo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 01, 2016 11:46 am
- Post datetime: 2016-05-08T10:45:05+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Ive been trying to get a script to get texture locations, ive got it to get just the file names and im trying to get it to have a option for dirty versions, are there only dirty versions for face, jacket, pants and shoes or do some have for others as well.

edit: ive got it to start searching for textures but it gives up after one



edit2: im not even sure what im doing wrong

all of the [:-1] are to get rid of \n

```
    print filename[:-1]  
    for ddslocation in ddslocations:                              
        if os.path.basename(ddslocation[:-1]) == filename[:-1]:
            print ddslocation[:-1]
            outfile.write(ddslocation)
            continue

```
## Post #41
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2016-05-14T22:58:49+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Anything new on this?
## Post #42
- Username: mrjosheyhalo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 01, 2016 11:46 am
- Post datetime: 2016-05-15T04:33:41+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from d875j
>
> Anything new on this?

I`ve got my script showing all locations now but noticed a few files that dont always get found, havnt felt like working on it.
[My script so far](https://gist.github.com/JoshuaWierenga/07edf036c03e2dfec5ec84d0254d9567) if anyone wants to take a look.
## Post #43
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-07-01T06:05:49+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Out of curiosity -- I've got this game from the Windows App store -- where abouts do I find the files to go rooting around through them??
## Post #44
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-07-01T06:15:43+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from trexjones
>
> Out of curiosity -- I've got this game from the Windows App store -- where abouts do I find the files to go rooting around through them??
[http://www.fixedbyvonnie.com/2013/12/wh ... installed/](http://www.fixedbyvonnie.com/2013/12/where-are-apps-in-the-windows-store-installed/)

This article explains where windows apps are stored, and what you have to do to gain access to the folder. Microsoft by default tries to keep people from poking around in there.
## Post #45
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-07-01T09:02:59+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Thanks Volfin! And thanks for doing the hard yards on this! I'm forever grateful for your work on getting the Alien: Isolation models bones, and looking forward to poking around with these!

Out of curiosity, could this same tool be applied to Alan Wake models? Or are they already available with their rigging?
## Post #46
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-07-01T16:30:43+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from trexjones
>
> Thanks Volfin! And thanks for doing the hard yards on this! I'm forever grateful for your work on getting the Alien: Isolation models bones, and looking forward to poking around with these!

Out of curiosity, could this same tool be applied to Alan Wake models? Or are they already available with their rigging?

Thanks 

I think there should be some tools out for Alan Wake already, the game has been out for so many years now. I doubt this tool would work with it.
## Post #47
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2016-07-01T19:29:18+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

hi everyone.
I want to translate this game.
I know font is in binfnt format and I can search for dds,
But that is not enough.
I need to change other things too.
things like x, y, height, width and...
Does anyone know how I can change this sort of things?

sorry for my bad English and thanks.

[http://www.mediafire.com/download/snkno ... _Fonts.zip](http://www.mediafire.com/download/snknow5m2wvfvty/Quantum_Break_Fonts.zip)
## Post #48
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2016-07-16T18:00:55+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

how come there is an "invalid header file" error when trying to load the normal maps to 3dmaxs unreal engine or anyother photo app or even attempting to convert it fails. the only thing that can open it is the nvidia dds viewer which is kinda pointless.
## Post #49
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2016-07-22T11:20:37+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

is it possible to rip the animation file (the AAA file i believe)?
## Post #50
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2016-07-25T23:25:46+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

i made an application that automatically attaches every model with their texture files. but i need help with the animation file. please someone help.
## Post #51
- Username: paulscottttt
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Jan 25, 2016 8:34 am
- Post datetime: 2016-08-29T14:18:28+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

is this game moddable yet?
## Post #52
- Username: markem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 03, 2017 10:44 am
- Post datetime: 2017-01-03T02:47:51+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Hey guys,

I'm looking for that Alan Wake chalk board from the beginning of the game.

I'm running into issues because I've gone through a ton of the textures and couldn't find it - could it possibly be a different file that's not actually a texture?

Any info on it would help greatly!

Thanks
## Post #53
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-03T18:25:32+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from markem
>
> Hey guys,

I'm looking for that Alan Wake chalk board from the beginning of the game.

I'm running into issues because I've gone through a ton of the textures and couldn't find it - could it possibly be a different file that's not actually a texture?

Any info on it would help greatly!

Thanks

The furthest I can trace it is, the lecture hall meshes are in the folder "batch16"
the "blackboard_blackboard.binfbx.meta" points to a texture in "sourcedata\\textures\\ringtail\\batch16\\blackboard.tga"

However, there's no "batch16" folder in the "ringtail" folder, so it appears to be missing...  perhaps it's packaged in the language-specific packages.
## Post #54
- Username: markem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 03, 2017 10:44 am
- Post datetime: 2017-01-03T18:49:53+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> markem wrote:Hey guys,

I'm looking for that Alan Wake chalk board from the beginning of the game.

I'm running into issues because I've gone through a ton of the textures and couldn't find it - could it possibly be a different file that's not actually a texture?

Any info on it would help greatly!

Thanks

The furthest I can trace it is, the lecture hall meshes are in the folder "batch16"
the "blackboard_blackboard.binfbx.meta" points to a texture in "sourcedata\\textures\\ringtail\\batch16\\blackboard.tga"

However, there's no "batch16" folder in the "ringtail" folder, so it appears to be missing...  perhaps it's packaged in the language-specific packages.

Smart. I'll keep searching - thank you!
## Post #55
- Username: markem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 03, 2017 10:44 am
- Post datetime: 2017-01-03T21:00:26+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Curses. I loaded the game in spanish language and speech and it turns out the board is still in english... hm.

I have a strange feeling that much like the video monitors, there's a good chance it's all sitting in one place to be called from on different monitors or, like this it's reused in two versions of the same room. hmm.

edit: two hours later

I've kept poking around, so there must be more packages that contain the files with the file i'm looking for >_<
## Post #56
- Username: markem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 03, 2017 10:44 am
- Post datetime: 2017-01-05T05:21:21+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

I'm a jerk so I put out a request in a new post - and someone had it!
[http://www.mediafire.com/file/7t6r5gayt ... _a.tex.dds](http://www.mediafire.com/file/7t6r5gaytdgq7pz/alan_wake_board_a.tex.dds)

I'm going to continue to be confused as to where it came from!

...did another search and it's sitting right there in "noises". Case solved...
## Post #57
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-05T06:56:09+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

yeah that's crazy because first thing I did was search for 'alan'.  Don't know how I missed it.
## Post #58
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-01-24T21:04:19+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

First problem I have, is I'm using Blender 2.66 and using the Quantum Break WedMsh Importerscript version 1.21. When I load QuantumBreak\d_\data\objects\characters\intermediate\malene_striker_publish.wedmsh

It shows the bones below the mesh, and it's not attached to the mesh and their is no weights applied. In the console is the following error:

File "C:\Users\anand\AppData\Roaming\Blender Foundation\Blender\2.66\scripts\addons\io_scene_QuantumBreak\__init__.py", line 80, in execute
    result=import_WedMsh.import_WedMsh(self.filepath, bpy.context,self.randomize_colors,self.import_vertcolors,self.skip_blank,self.use_layers,self.mesh_scale)
  File "C:\Users\anand\AppData\Roaming\Blender Foundation\Blender\2.66\scripts\addons\io_scene_QuantumBreak\import_WedMsh.py", line 700, in import_WedMsh
    poseRig(rig, Pose_Table,use_layers,mesh_scale)
  File "C:\Users\anand\AppData\Roaming\Blender Foundation\Blender\2.66\scripts\addons\io_scene_QuantumBreak\import_WedMsh.py", line 473, in poseRig
    rig.data.transform(matrix_basis)
AttributeError: 'Armature' object has no attribute 'transform'
[QuantumBreak_Error_01.jpg](https://xentaxbackup.github.io/file/12283_QuantumBreak_Error_01.jpg)
## Post #59
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-24T22:21:30+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

I think your blender is just too old.  2.66 was released in 2013, 4 years ago.

I tried it on the oldest blender I have installed, 2.70 (from 2014), and it worked fine:



So I recommend upgrading your blender. But thanks for letting me know, I didn't realize armatures functionality had changed along the line. I'll have to stop saying it is compatible back to 2.63 (not that I really expected anyone to be using such an old blender lol)
## Post #60
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2017-01-25T23:08:17+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from Bladers
>
> i made an application that automatically attaches every model with their texture files. but i need help with the animation file. please someone help.

Snip
Can you upload the app that be great than manually applying textures and such.
## Post #61
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-01-25T23:59:16+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> I think your blender is just too old.  2.66 was released in 2013, 4 years ago.

I tried it on the oldest blender I have installed, 2.70 (from 2014), and it worked fine:

So I recommend upgrading your blender. But thanks for letting me know, I didn't realize armatures functionality had changed along the line. I'll have to stop saying it is compatible back to 2.63 (not that I really expected anyone to be using such an old blender lol)

Thanks, it worked, I never know which version of blender to use with scripts. I'm not a blender guy. I perfer Max or Maya. I had to manually flip the normal's. I Successful imported him into UE4. The major pain was scale. I used my Max trusty Rescale World Units to about 27 and that did the trick.

Now I'm trying to figure out how to get some textures, and hopefully some day animation. Any suggestions would be great.
[malene_striker_publish.jpg](https://xentaxbackup.github.io/file/12290_malene_striker_publish.jpg)
## Post #62
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-26T00:16:14+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

if you used version 0.2 of the QuantumBreak tool to unpack, it should have converted the textures to DDS for you.

With the model selected, you can see the material names on the right:


those are clues to the texture names.
So if I search  the extract folder, I see a folder named "male_jonova" and it has the face, eyelashes, and eye textures.
if I search "striker_helmet", I see a folder named "malene_striker\accessories" and there's textures.
if I search "striker_bottom", I find that in "-Textures\bottoms" folder. And so on and so on.

P.S. you're correct about the flipped normals. I'm going to fix that and tweak a few things I've learned over the last 8 months since I released this, And post a new version.
## Post #63
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-26T01:25:55+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Ok, new version of the importer.

Not a lot changed, I did fix the normal being flipped inside out. Bone groups are now sorted by skeleton hierarchy, And if you use blender 2.75 or newer, it loads normal in as the new split normal type. rest is general tweaks.

Enjoy.

Edit: Newer version below
## Post #64
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2017-01-26T02:26:07+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> Ok, new version of the importer.

Not a lot changed, I did fix the normal being flipped inside out. Bone groups are now sorted by skeleton hierarchy, And if you use blender 2.75 or newer, it loads normal in as the new split normal type. rest is general tweaks.

Enjoy.

But you still did not done the map model's coordinates? It be nice still to have that supported. It might be a good idea to do it as it will help importing maps into the game aswell.
## Post #65
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-26T18:47:49+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from d875j
>
> volfin wrote:Ok, new version of the importer.

Not a lot changed, I did fix the normal being flipped inside out. Bone groups are now sorted by skeleton hierarchy, And if you use blender 2.75 or newer, it loads normal in as the new split normal type. rest is general tweaks.

Enjoy.

But you still did not done the map model's coordinates? It be nice still to have that supported. It might be a good idea to do it as it will help importing maps into the game aswell.

I have no idea what you mean by "map model's coordinates". If you mean placing all the objects as arranged on the map, that's never going to happen. I don't have that kind of time to spend on that kind of thing.
## Post #66
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2017-01-26T21:25:40+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> d875j wrote:volfin wrote:Ok, new version of the importer.

Not a lot changed, I did fix the normal being flipped inside out. Bone groups are now sorted by skeleton hierarchy, And if you use blender 2.75 or newer, it loads normal in as the new split normal type. rest is general tweaks.

Enjoy.

But you still did not done the map model's coordinates? It be nice still to have that supported. It might be a good idea to do it as it will help importing maps into the game aswell.

I have no idea what you mean by "map model's coordinates". If you mean placing all the objects as arranged on the map, that's never going to happen. I don't have that kind of time to spend on that kind of thing.

Yes that. And shame hope someone does it on here.
## Post #67
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-01-26T23:11:37+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

After hours of working with both plugins I found a solution.

I use Blender 2.70
I use plugin 1.21
I tried using the new plugin but couldn't get it to reliably work. version 1.30. 
What it does is, when the mesh is exported as fbx and imported to max all the bones are
small in a ball, even if the mesh is rescaled. That's why I use 1.21

I make sure to delete all lights, camera from blender.
I manually flip the normals.

Then in Max I rescale the mesh with Rescale World Units to 90 to better match Unreal Engine.
Then everything works. except. When you then load another mesh with the plugin in Blender there
are errors, so I close out blender and reload the mesh, and it will re-load without errors. I don't know
why the errors happen when I load the second mesh. Here is the error:

Traceback (most recent call last):
  File "C:\Users\anand\AppData\Roaming\Blender Foundation\Blender\2.70\scripts\addons\io_scene_QuantumBreak\__init__.py", line 80, in execute
    result=import_WedMsh.import_WedMsh(self.filepath, bpy.context,self.randomize_colors,self.import_vertcolors,self.skip_blank,self.use_layers,self.mesh_scale)
  File "C:\Users\anand\AppData\Roaming\Blender Foundation\Blender\2.70\scripts\addons\io_scene_QuantumBreak\import_WedMsh.py", line 700, in import_WedMsh
    poseRig(rig, Pose_Table,use_layers,mesh_scale)
  File "C:\Users\anand\AppData\Roaming\Blender Foundation\Blender\2.70\scripts\addons\io_scene_QuantumBreak\import_WedMsh.py", line 482, in poseRig
    mod.object = rig
AttributeError: 'NoneType' object has no attribute 'object'

Also, all the LODS are currently unusable, I just delete them, They are not bound to the skeleton/armature so they import into max or may laying flat. I guess if I wanted to I could re-rotate them and re-bind them and copy the weights to the mesh, but the plugin doesn't seem to correctly do this for me.

I hope this was useful, and thank you so much for your plugin. These meshes are crazy amazing, and I think they wen't overkill on the bones. It would be amazing if we could have animation, if possible. It would be great to have it implemented.
## Post #68
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-26T23:52:08+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Well so many of your problems are because you're sticking with such an old version of blender. there's been so many bug fixes to blender between 2.70 and 2.78 it would literally fill a book. 

But I have another version here, which will fix a couple of the issues you see with 2.70. I still recommend you upgrade to at least 2.77 or better yet 2.78

Edit: newer below
## Post #69
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-01-27T01:08:36+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> Well so many of your problems are because you're sticking with such an old version of blender. there's been so many bug fixes to blender between 2.70 and 2.78 it would literally fill a book. 

But I have another version here, which will fix a couple of the issues you see with 2.70. I still recommend you upgrade to at least 2.77 or better yet 2.78

Sorry, I can upgrade to any version you'd like. I couldn't get the other latest version to work with version blender-2.78a-windows64. If you'd like I can, and let you know what happens.
## Post #70
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-27T01:39:05+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from UberBlack
>
> volfin wrote:Well so many of your problems are because you're sticking with such an old version of blender. there's been so many bug fixes to blender between 2.70 and 2.78 it would literally fill a book. 

But I have another version here, which will fix a couple of the issues you see with 2.70. I still recommend you upgrade to at least 2.77 or better yet 2.78

Sorry, I can upgrade to any version you'd like. I couldn't get the other latest version to work with version blender-2.78a-windows64. If you'd like I can, and let you know what happens.

Well I tested 1.30 against 2.77 and 2.78, So I know it works with those. 2.77 is generally the version I use on a daily basis, so it's probably the most 'safe' version.  1.31 I fixed to work with 2.70 (and all versions above that likely). But it's not going to have 100% of the features since it's old API doesn't support some things, and also, bugs.

But here's the facts about Blender and versions:
Blender 2.49b was the last version of what I call 'Gen 1' Blender.  As of Blender 2.5, they completely rewrote blender from the ground up, so that's why a lot of olds scripts were stuck using 2.49b.  

Then blender entered what I call the "Dark Ages" because they kept changing the API every new revision.  From 2.5 to 2.62 was a nightmare.

Then in Blender 2.63, they added a new mesh system, called BMesh.  So more API changes. it wasn't until around 2.70 that things really settled down.

So now from 2.70 on, Things are pretty stable. The 'Dark Ages' are over. But, they do continue to add new features every version. And that's what you're seeing, I'm starting to use some of the newer features blender has to offer.  
Split normals didn't appear until Blender 2.73, but it was broken until 2.75. 
It seems some Armature features didn't get added until Blender 2.72
And so on and so on. So it's just always best to use the newest blender these days. There' nothing that's going to be missing or removed as new versions as put out, only new things added. (at least until some day they decide to rewrite it from scratch again). 

You can always have multiple versions of blender on your system, for cases where some plugin demands a specific version of blender. But I guess I need to start being more vigilant with version testing. I haven't really paid it much mind til now. I'll have to go through all of the plugins I wrote and put a minimum supported blender version on them. I just assume people will keep upgrading blender when a new version comes out.
## Post #71
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-01-27T02:07:11+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> UberBlack wrote:volfin wrote:Well so many of your problems are because you're sticking with such an old version of blender. there's been so many bug fixes to blender between 2.70 and 2.78 it would literally fill a book. 

But I have another version here, which will fix a couple of the issues you see with 2.70. I still recommend you upgrade to at least 2.77 or better yet 2.78

Sorry, I can upgrade to any version you'd like. I couldn't get the other latest version to work with version blender-2.78a-windows64. If you'd like I can, and let you know what happens.

Well I tested 1.30 against 2.77 and 2.78, So I know it works with those. 2.77 is generally the version I use on a daily basis, so it's probably the most 'safe' version.  1.31 I fixed to work with 2.70 (and all versions above that likely). But it's not going to have 100% of the features since it's old API doesn't support some things, and also, bugs.

But here's the facts about Blender and versions:
Blender 2.49b was the last version of what I call 'Gen 1' Blender.  As of Blender 2.5, they completely rewrote blender from the ground up, so that's why a lot of olds scripts were stuck using 2.49b.  

Then blender entered what I call the "Dark Ages" because they kept changing the API every new revision.  From 2.5 to 2.62 was a nightmare.

Then in Blender 2.63, they added a new mesh system, called BMesh.  So more API changes. it wasn't until around 2.70 that things really settled down.

So now from 2.70 on, Things are pretty stable. The 'Dark Ages' are over. But, they do continue to add new features every version. And that's what you're seeing, I'm starting to use some of the newer features blender has to offer.  
Split normals didn't appear until Blender 2.73, but it was broken until 2.75. 
It seems some Armature features didn't get added until Blender 2.72
And so on and so on. So it's just always best to use the newest blender these days. There' nothing that's going to be missing or removed as new versions as put out, only new things added. (at least until some day they decide to rewrite it from scratch again). 

You can always have multiple versions of blender on your system, for cases where some plugin demands a specific version of blender. But I guess I need to start being more vigilant with version testing. I haven't really paid it much mind til now. I'll have to go through all of the plugins I wrote and put a minimum supported blender version on them. I just assume people will keep upgrading blender when a new version comes out.

Thanks for that. I have been just loading the models and extracting FBX to 3ds Max where I can scale them. The problem has never been with blender, It's when the meshes are exported to 3ds max via fbx. 

Now with Blender 2.70 with plugin 1.3.1 it works perfect. I have included a Max Picture. I scaled both models to 90 so you can see the mesh better, because there are tons of bones. If you look you can tell the all the meshes are now in the correct orientation. i checked also they are bound.

If you look at the picture I took with Blender 2.78 using 1.3.1 you will notice that the LODs are not at the correct orientation.


Exported FBX with Blender 2.70 using plugin version 1.3.1 Imported to 3DSMax 2017 x64
Works Perfect!


Exported FBX with Blender 2.78 using plugin version 1.3.1 Imported to 3DSMax 2017 x64
Not Perfect, LODs are not matching up with Skeleton.


Thanks for your help, and we appreciate the plugin you've made.
## Post #72
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-27T03:23:25+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

I see. So they look fine in blender, but it's the FBX Export when the LOD models are changing.  I think I know why, on the LODs, I didn't apply the rotational changes. Seems in 2.78 they no longer do that for you. Let me take a stab at fixing that.

Edit: try this version, I think it should work properly with 2.78 (and older down to 2.70)
[io_scene_QuantumBreak.zip](https://xentaxbackup.github.io/file/12312_io_scene_QuantumBreak.zip)
## Post #73
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-01-27T19:48:46+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> I see. So they look fine in blender, but it's the FBX Export when the LOD models are changing.  I think I know why, on the LODs, I didn't apply the rotational changes. Seems in 2.78 they no longer do that for you. Let me take a stab at fixing that.

Edit: try this version, I think it should work properly with 2.78 (and older down to 2.70)

Thanks I really appreciate you're speed in fixing it. I have tried the new version. This is what I noticed.

I got to remember to turn off leaf in FBX export.

1. Smoothing groups are not kept when exporting to FBX

2. Not that it's a biggie but the scaling is much different, the default is 3 which is now huge. I put it back to 1 and it's a better size for unreal.

the bones seem correct in that they are not in a ball anymore when I export it to UE4.
It also doesn't crash when I load a new mesh in Blender. 

So it's working Thanks again
## Post #74
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2017-01-28T03:25:41+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Thanks for all your hard work vfolin. Especially for the normals fix. I made several scenes and the normals issue was giving me problems. Even when i flipped them, they never looked right. Lastly if we could get animation to work it would be heaven!

UberBlack, were you able to get unreal engine default animations applied to the models.
I tried that and i kept running into issues when re-targeting the animations.

d875j, the tool, though it exists in GUI form is really not user friendly but i will look at cleaning it up and releasing it. But concerning the map, you would have to arange it yourself, there is no coordinates. Although based on the new update, something similar is already being done.
## Post #75
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2017-01-30T12:06:43+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from Bladers
>
> Thanks for all your hard work vfolin. Especially for the normals fix. I made several scenes and the normals issue was giving me problems. Even when i flipped them, they never looked right. Lastly if we could get animation to work it would be heaven!

UberBlack, were you able to get unreal engine default animations applied to the models.
I tried that and i kept running into issues when re-targeting the animations.

d875j, the tool, though it exists in GUI form is really not user friendly but i will look at cleaning it up and releasing it. But concerning the map, you would have to arange it yourself, there is no coordinates. Although based on the new update, something similar is already being done.

Alrighty
## Post #76
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2017-02-02T01:05:25+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

I got an request on blender script can you add batch model import? Importing 1 by 1 sorta slow. Until Bladers guy releases his tool i will uses blender script.
## Post #77
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-02T01:50:00+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

This was never meant to be some kind of bulk import tool or mass converter. And I can't turn it into that. Sorry.

You can look at a guy's post here:  [viewtopic.php?p=125912#p125912](http://forum.xentax.com/viewtopic.php?p=125912#p125912)
He made a script to import in 1000 files in one go for this game. but that game is a lot lower poly meshes. Frankly I think after 10 blender will crash. So use at your own risk, I won't offer support on this type of thing.
## Post #78
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2017-02-02T07:04:17+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> This was never meant to be some kind of bulk import tool or mass converter. And I can't turn it into that. Sorry.

You can look at a guy's post here:  viewtopic.php?p=125912#p125912
He made a script to import in 1000 files in one go for this game. but that game is a lot lower poly meshes. Frankly I think after 10 blender will crash. So use at your own risk, I won't offer support on this type of thing.

Yes i saw that but unfortunately i can't do that as not skilled in Blender Script making. If he adds support for this game then sure.. As of the moment i am porting the map manually into an GTA Style it be fully explorable. I did research and have a rough idea how to get placements from .META files from each file in separate placement type files and have an 3DS Max script to place them objects. Every .META file contains coordinates of X,Y,Z and Rotations. Me and a few buds going to get it possible.

Examples:

Bounding Box:

```
"r::BoundBox",
"objectVersion": 
1,
"m_vMin": "-2.9424445629119873 -4.3495821952819824 18.573249816894531",
"m_vMax": "0.11948671191930771 4.5004186630249023 28.464319229125977"
```


Few other interesting things i found in the .META files. Hope this sparks some interest as it can be used to re-import new maps in Quantum Break aswell.
## Post #79
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2017-07-28T04:16:37+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Can anyone tell me why this plugin doesn't import the skeleton bones anymore in blender. Also when i export to fbx and import to MAX they don't show up..
## Post #80
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-07-28T16:10:12+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

it still does, nothing has changed. You must be doing something wrong.
## Post #81
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2017-07-28T19:59:35+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> it still does, nothing has changed. You must be doing something wrong.

using blender 2.78 and 2.27 and max 2016 and 2018.
maybe being out the game for over a year has made me rusty. but it doesn't look right. the bones are not available in 3ds max.
here's a pic of my process below.
## Post #82
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-07-28T20:19:57+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

oh I don't know about 3ds max, but it should still work for blender. I only made the blender plugin.
## Post #83
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2017-07-28T20:24:43+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin
>
> oh I don't know about 3ds max, but it should still work for blender. I only made the blender plugin.

the skeletons used to show up using the older version of the plugin when i export FBX from blender and import into 3d max.

now i wonder how UberBlack got the latest version to work when he export FBX from blender and import FBX into max.
## Post #84
- Username: fredihaberg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 20, 2014 7:20 am
- Post datetime: 2017-09-26T00:41:03+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Hey there,
Every time I try to import a wedmesh into Blender, it says "the signature of (...) is invalid:0". Do you know what that means or how to fix it @volfin?

EDIT: I'm using Blender 2.77
## Post #85
- Username: udkultimate
- Rank: beginner
- Number of posts: 29
- Joined date: Thu May 25, 2017 6:11 am
- Post datetime: 2017-11-17T20:43:24+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Hello guys.

Sorry for bumping an old thread, but I would like to know if is possible to extract animations from Quantum Break game.

Thanks.
## Post #86
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-11-21T20:20:30+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

I can not find Kate Ogawa model
i extract ep999-000 but it's not there
## Post #87
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-08-27T19:28:49+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

I wonder if this extract tool will work on Control?
## Post #88
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2019-08-27T21:47:39+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

works with control

[http://aluigi.org/bms/quantum_break.bms](http://aluigi.org/bms/quantum_break.bms)
## Post #89
- Username: blenux
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jan 25, 2019 5:06 pm
- Post datetime: 2019-08-28T13:37:25+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

How does one use this with Control and import into Blender (possibly Blender 2.80)?
## Post #90
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2019-08-28T23:53:40+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Looks like we'll need a new model importer. Relevant file formats seem to be .binfbx and .binskeleton. I uploaded some character samples: [https://www23.zippyshare.com/v/YmPEVAtb/file.html](https://www23.zippyshare.com/v/YmPEVAtb/file.html)
## Post #91
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2019-08-29T06:31:14+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from evin ↑Tue Apr 12, 2016 1:03 pm at Tue Apr 12, 2016 1:03 pm
>
> 
MuratG wrote:evin wrote:It is in alpha/beta stage, but I can unpack texts, and files.
I'll release soon, after I fixed some bug.

string table .bin Missing?


You should read the info.rtf first: No text extractor function in the tool, to avoid the steeling of unofficial translations!
You loaded the text .bin file!

Also About button in the Tool: 
"What is missing or need to fix:... - text file handler ..."
I'll attach to the tool the unpacked text file, after I fixed the text handler functions.

Thanks! Could you share some information about glyphs data for font?
Are datas from head of binfnt, they are glyphs data? Thanks a lot!
## Post #92
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2019-08-29T08:04:49+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from shadowlonely1989 ↑Thu Aug 29, 2019 2:31 pm at Thu Aug 29, 2019 2:31 pm
>
> 
Thanks! Could you share some information about glyphs data for font?
Are datas from head of binfnt, they are glyphs data? Thanks a lot!
I have not information about the structure of this file.
I just edited the texture file inside it, nothing more.
## Post #93
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2019-08-29T08:24:25+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from evin ↑Thu Aug 29, 2019 4:04 pm at Thu Aug 29, 2019 4:04 pm
>
> 
shadowlonely1989 wrote: ↑Thu Aug 29, 2019 2:31 pm
Thanks! Could you share some information about glyphs data for font?
Are datas from head of binfnt, they are glyphs data? Thanks a lot!

I have not information about the structure of this file.
I just edited the texture file inside it, nothing more.

Thanks a lot! Hope anyone can share infor about the structure of this file!
## Post #94
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-08-29T12:16:34+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from YourImaginaryFriend ↑Thu Aug 29, 2019 7:53 am at Thu Aug 29, 2019 7:53 am
>
> 
Looks like we'll need a new model importer. Relevant file formats seem to be .binfbx and .binskeleton. I uploaded some character samples: https://www23.zippyshare.com/v/YmPEVAtb/file.html

Anyone?
## Post #95
- Username: rootshaper
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 29, 2019 10:01 pm
- Post datetime: 2019-08-29T14:07:45+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Hey there! Is it possible to somehow reconfigure this tool for Control? It just came out and I already washed away by it's sound design and I really need those samples stored inside the same archives as Alan Wake or Quantum Break.

I have tried to use this extractor but on the VO samples (I guess those are VO samples) it just shut down after I chose the BIN file and to extract only .wem files and then if I hit Extract, the app is killed and it only creates some gibberish folders without content.

It can extract however some other .wem and .bnk files, but with them are other problems sadly. If I try the good old ww2ogg and revorb combo to extract .bnk files and fix them on the way it usually telling me Parse error: missing RIFF. It is a common error as far as I know because I have spent 5 hours figuring this out now and I know how to google. But I am stuck now, I need some advices.

I do managed to extract and make playable some samples but it's only the quarter of what the game originally contains. I need ALL 

Thanks for your help in advance!
## Post #96
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-08-30T14:16:57+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from volfin ↑Thu Apr 28, 2016 6:51 am at Thu Apr 28, 2016 6:51 am
>
> 
Attached is version 1.0 alpha of my *.wedmsh blender plugin for Quantum break.

Currently should import any mesh as a static object with UVs and in-game normals. if the file has multiple meshes (LODs or whatever), it will import all.

I will continue to do more work to add support for bone weights and materials, depending on what data I can uncover. if you run into any files that don't load properly, please let me know the filename/directory name. Thanks.

EDIT: new version released in subsequent post.

> Reply from YourImaginaryFriend ↑Thu Aug 29, 2019 7:53 am at Thu Aug 29, 2019 7:53 am
>
> 
Looks like we'll need a new model importer. Relevant file formats seem to be .binfbx and .binskeleton. I uploaded some character samples: https://www23.zippyshare.com/v/YmPEVAtb/file.html

Hey @volfin i know you made the plugin for wedmsh. You think you can write one for .binfbx?
## Post #97
- Username: Gamson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 01, 2019 7:06 am
- Post datetime: 2019-08-31T23:15:31+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from rootshaper ↑Thu Aug 29, 2019 10:07 pm at Thu Aug 29, 2019 10:07 pm
>
> 
Hey there! Is it possible to somehow reconfigure this tool for Control? It just came out and I already washed away by it's sound design and I really need those samples stored inside the same archives as Alan Wake or Quantum Break.

I have tried to use this extractor but on the VO samples (I guess those are VO samples) it just shut down after I chose the BIN file and to extract only .wem files and then if I hit Extract, the app is killed and it only creates some gibberish folders without content.

It can extract however some other .wem and .bnk files, but with them are other problems sadly. If I try the good old ww2ogg and revorb combo to extract .bnk files and fix them on the way it usually telling me Parse error: missing RIFF. It is a common error as far as I know because I have spent 5 hours figuring this out now and I know how to google. But I am stuck now, I need some advices.

I do managed to extract and make playable some samples but it's only the quarter of what the game originally contains. I need ALL 

Thanks for your help in advance!

Yep, can confirm that this tool doesn't work on Control. Maybe if we had source code we could do something about that
## Post #98
- Username: szefons
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 08, 2015 2:38 am
- Post datetime: 2019-09-02T12:36:28+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Look here 

[viewtopic.php?f=33&t=21047&p=155806#p155806](https://forum.xentax.com/viewtopic.php?f=33&t=21047&p=155806#p155806)
## Post #99
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-02T14:59:35+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from szefons ↑Mon Sep 02, 2019 8:36 pm at Mon Sep 02, 2019 8:36 pm
>
> 
Look here 

viewtopic.php?f=33&t=21047&p=155806#p155806

Its not extracting it is the problem. its rewriting the Blender model import script to work with Control (binfbx).
For example the file record signature is different and it crashes there. I'm trying to look into it but alas..
## Post #100
- Username: szefons
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 08, 2015 2:38 am
- Post datetime: 2019-09-02T16:24:00+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

I was answering to the initial issue of crashing by rootshaper, so we have at least a new app, up to date, Northlight Tool, that works with Control, it doesn't crash when extracting, its a start.
## Post #101
- Username: rootshaper
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 29, 2019 10:01 pm
- Post datetime: 2019-09-06T10:01:22+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

> Reply from szefons ↑Tue Sep 03, 2019 12:24 am at Tue Sep 03, 2019 12:24 am
>
> 
I was answering to the initial issue of crashing by rootshaper, so we have at least a new app, up to date, Northlight Tool, that works with Control, it doesn't crash when extracting, its a start.

wow thanks! I'll check this out and report if the files are exported correctly and useable in a music production tool after that because some files was "corrupt" after the export with the quantum break and alan wake tool.
## Post #102
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-09-06T16:29:40+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

Control model import is discussed here: [viewtopic.php?p=155960#p155960](https://forum.xentax.com/viewtopic.php?p=155960#p155960)

Importer will be for blender 2.70 thru 2.79 like all my importers.  After it's done i'll look at maybe making a version for blender 2.80.  but plugin conversion is a nightmare, I've successfully converted one simple plugin and about had a stroke in the process.
## Post #103
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2021-12-31T19:26:09+00:00
- Post Title: Re: [PC] Quantum Break .RMDP

.binfnt can now be created or edited   
See here: [viewtopic.php?f=33&t=24901](https://forum.xentax.com/viewtopic.php?f=33&t=24901)
