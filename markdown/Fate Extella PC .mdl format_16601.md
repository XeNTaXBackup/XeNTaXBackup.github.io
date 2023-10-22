## Post #1
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-07-27T02:47:18+00:00
- Post Title: Fate Extella PC *.mdl format

Posting this to request model/skeleton tools for this game. [chrrox was kind enough to post a working script for extracting the archives](http://forum.xentax.com/viewtopic.php?p=132438#p132438) which kicked out everything into mostly neat folders. I've uploaded a couple character samples and their weapons. I can post more if needed. 

The models have a *.mdl extension but do not open with existing tools. There is a clearly named "skeleton" .mdl file separate from what I assume to be the actual meshes. I included what I hope are all associated textures for completion's sake (ALL textures are in a couple big ass folders but they seem to be named according to their associated models). They're in a *.mds format but renaming them to *.dds seems to work just fine. 

A final note about the models: I looked at them in a hex editor and they looked to be largely in plain text with "Collada Mesh File" being among the first bits of text in the file as well as texture names and such. Unfortunately I don't really know what to do with any of that. Just posting it in case it helps/entices someone to take a look. 

[https://www.mediafire.com/?ujep8kx9zfddqcs](https://www.mediafire.com/?ujep8kx9zfddqcs)
## Post #2
- Username: shakotay2
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-27T08:46:06+00:00
- Post Title: Fate Extella PC *.mdl format

Its using the model format from the nier games on xbox 360
## Post #3
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-07-27T21:22:46+00:00
- Post Title: Fate Extella PC *.mdl format

Woah, that is one heavy script. Caused my entire computer to crash. The Blender script Szkaradek123 posted doesn't load the mdls either. Its saying something about mdp.dec, and I tried to use your BMS script on the mdl's but that doesn't work.
## Post #4
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-07-27T21:45:10+00:00
- Post Title: Fate Extella PC *.mdl format

Was just about to post the same anime663. [I assume this is the Nier thread and tools you tried.](http://forum.xentax.com/viewtopic.php?f=16&t=5621) Changed filename extensions and I also ran the decryption bms script from that thread but it also errors out. Either something is changed causing those tools to not work or we're missing something in the process. 

I neglected to try running the game with only extracted files to see if texture modding would be simple (since textures seem to just be .dds files). Will have to give that a try when I get home.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-27T22:57:40+00:00
- Post Title: Fate Extella PC *.mdl format

They changed some things about it but its near identical ill try to look at it this weekend.
## Post #6
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-07-28T10:55:18+00:00
- Post Title: Fate Extella PC *.mdl format

Here is my WIP Noesis plugin (only loads mesh data for now): [link](https://github.com/kotcrab/fate-explorer/releases/tag/mdl-v0.1)

Edit: Updated link to more permanent one
## Post #7
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-29T00:00:16+00:00
- Post Title: Fate Extella PC *.mdl format

Can you send me all the files? i dont know how to extract, if you cant send me can you show me how to do it myself?
## Post #8
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-07-29T00:20:17+00:00
- Post Title: Fate Extella PC *.mdl format

> Reply from Kenzato
>
> Can you send me all the files? i dont know how to extract, if you cant send me can you show me how to do it myself?

Not uploading/sharing gigabyte's worth of models and textures.

-obtain game
-download quickbms from [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm) 
-copy the script text I linked in the OP and paste it into a new text file
-run quickbms, select the text file you created, then select the file you want to extract and then select where you want to extract
-wait for chrrox and/or kotkrab to release their script(s)
## Post #9
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-29T02:59:56+00:00
- Post Title: Fate Extella PC *.mdl format

Alright extracting everything. how many gigs should i end up with btw?

Thanks
## Post #10
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-07-29T10:14:54+00:00
- Post Title: Fate Extella PC *.mdl format

~5.8 GB from main archive. I am currently working on custom extractor and repackager, will post it in archive thread when ready.
## Post #11
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-29T15:19:11+00:00
- Post Title: Fate Extella PC *.mdl format

> Reply from Kotcrab
>
> ~5.8 GB from main archive. I am currently working on custom extractor and repackager, will post it in archive thread when ready.
So how far are you on it?

il have to wait for that until i can rip the textures right? or am i missing something
## Post #12
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-07-29T15:35:03+00:00
- Post Title: Fate Extella PC *.mdl format

Extracting part is done. You don't have to wait for me if all you want to do is rip textures. QuickBMS script posted here works just as well.
## Post #13
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-29T17:36:07+00:00
- Post Title: Fate Extella PC *.mdl format

that only works for the hud and backgrounds. not the textures to the models themselves which i believe is in mdltex and mdltex12 which are a format i dont know how to open
## Post #14
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-07-29T18:42:48+00:00
- Post Title: Fate Extella PC *.mdl format

They are all DDS even though file extension is different.
## Post #15
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-29T18:59:11+00:00
- Post Title: Fate Extella PC *.mdl format

> Reply from Kotcrab
>
> They are all DDS even though file extension is different.

well how am i supposed to open them then?

changing the name dosent work
## Post #16
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-07-29T19:34:22+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Changing 'sv0000_body_a.mds' to 'sv0000_body_a.dds' does work. You need a program that can actually view dds files because Windows (I believe) doesn't by default. [Noesis is one such program.](http://www.richwhitehouse.com/index.php?content=inc_projects.php)

However, changing the filename from 'sv0000_body_a' to 'sv0000_body_a.dds' will not work because you're just renaming the file and not changing the file extension. If you're looking at the file and only see something like 'sv0000_body_a' then you need to tell Windows to show file extensions. If you don't know how to do that then google the steps.
## Post #17
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-29T19:45:10+00:00
- Post Title: Re: Fate Extella PC *.mdl format

I am not dumb i know how to change the extension, and i do have programs that can read dds files.

It just dosent work every program gives a error when you open the changed ones
## Post #18
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-07-29T19:47:51+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Noesis works. Or Visual Studio if you want to install that hog. VS generates thumbnails in file explorer.
## Post #19
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-07-29T19:48:05+00:00
- Post Title: Re: Fate Extella PC *.mdl format

> Reply from Kenzato
>
> I am not dumb i know how to change the extension, and i do have programs that can read dds files.

It just dosent work every program gives a error when you open the changed ones
Use Noesis to open them.
## Post #20
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-29T19:49:48+00:00
- Post Title: Re: Fate Extella PC *.mdl format

i did and everything is just a big white square.

and other programs just get errors
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-30T01:12:22+00:00
- Post Title: Re: Fate Extella PC *.mdl format

> Reply from Kenzato
>
> i did and everything is just a big white square.

and other programs just get errors

update noesis
## Post #22
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-30T01:21:25+00:00
- Post Title: Re: Fate Extella PC *.mdl format

i downloaded it today ;8
## Post #23
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-30T01:30:52+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Nvm fixed it
## Post #24
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-07-30T19:09:18+00:00
- Post Title: Re: Fate Extella PC *.mdl format

So these models cant actually be textured can they? i tried to apply textures but it seems the models havent been uv mapped or something like that

also theres a wide range of Tags that i dont understand like M and A
## Post #25
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-07-31T09:39:47+00:00
- Post Title: Re: Fate Extella PC *.mdl format

> Reply from Kotcrab
>
> I am currently working on custom extractor and repackager, will post it in archive thread when ready.

A couple days late on this but in case you didn't know/test it yourself, the game does run on extracted files. Just have to move the extracted files into the appropriate folders.
## Post #26
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-07-31T13:29:30+00:00
- Post Title: Re: Fate Extella PC *.mdl format

> Reply from ssringo
>
> Kotcrab wrote:I am currently working on custom extractor and repackager, will post it in archive thread when ready.

A couple days late on this but in case you didn't know/test it yourself, the game does run on extracted files. Just have to move the extracted files into the appropriate folders.
I haven't tried it actually, good to know. At least I haven't started working on repackager yet.

> Reply from Kenzato
>
> So these models cant actually be textured can they? i tried to apply textures but it seems the models havent been uv mapped or something like that
Not yet but [I'm working on it](https://i.imgur.com/Pe3YM8G.png).
## Post #27
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-08-03T21:00:37+00:00
- Post Title: Re: Fate Extella PC *.mdl format

So how's progress coming? I finished up Fate/Extella earlier this week but my interest in modeling script/tools hasn't waned   

Umu
## Post #28
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-08-03T21:09:17+00:00
- Post Title: Re: Fate Extella PC *.mdl format

I've got textures to automatically load in Noesis when you open model and now I'm working on importing skeleton data.
## Post #29
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-08-05T18:35:46+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Here's the updated version. This one will load textures if you open file from game folder or when you have .dds/.mds textures in the same folder as model file. Normal/specular textures makes it look way to shiny, it might be the lighting, I don't know. Anyway, you can edit the script and change False to True at the top to only load basic textures. 
Skeleton is loaded but vertices are not assigned to bones, I can't figure it out how it's mapped.

[Download loader v0.2](https://github.com/kotcrab/fate-explorer/releases/download/mdl-v0.2/data_fate_extella.py)
## Post #30
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-08-05T19:19:03+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Good stuff mate. Hope you can figure out/get help on the last bit (maybe chrrox?). 

Speaking of, have you checked out chrrox's maxscript for Nier that I linked to earlier in the thread? He said they're nearly identical so maybe it can give you some direction.
## Post #31
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-08-10T13:18:38+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Took some time but I've figured it out.

[Download](https://github.com/kotcrab/fate-explorer/releases/download/mdl-v1.0/data_fate_extella.py)


> Reply from ssringo
>
> Speaking of, have you checked out chrrox's maxscript for Nier that I linked to earlier in the thread? He said they're nearly identical so maybe it can give you some direction.
Yeah it helped with some stuff but not everything is similar.
## Post #32
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-08-10T22:49:29+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Thank you for the all your work Kotcrab. Ran through a couple models and everything seems to be working fine. 

As an aside, Noesis did crash when I tried exporting the model AND textures at the same time but that might be because I'm on my crappy laptop atm and it can't handle that much work   . Exporting the model by itself and the textures through a separate batch process worked fine.
## Post #33
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-08-11T00:46:30+00:00
- Post Title: Re: Fate Extella PC *.mdl format

What I've checked so far seems to be fine except the DLC Saber's face isn't properly rigged to her face rig. The bones are useless, since all the mesh is attached to the head bone only. Theyre still there, but they dont move any of the mesh. I don't know if shes meant to be that way or not. Her skirt armor plates also aren't attached to her bones.
## Post #34
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-08-11T01:06:19+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Which DLC specifically? I assume you're talking about Nero. I know it'll sound anal but Nero, Artoria and Altera are all "Saber" (their servant class). 

Anyways, I did have some issues if I converted the models directly into mesh.ascii but going fbx to mesh.ascii has produced no skeleton issues in my tests.
## Post #35
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-08-11T01:09:20+00:00
- Post Title: Re: Fate Extella PC *.mdl format

> Reply from ssringo
>
> Which DLC specifically? I assume you're talking about Nero. I know it'll sound anal but Nero, Artoria and Altera are all "Saber" (their servant class). 

Anyways, I did have some issues if I converted the models into mesh.ascii but going fbx to mesh.ascii has produced no skeleton issues in my tests.

Yeah sorry Im not overly familiar with the series. xD I just like some of the designs. I mean Artoria's Fate Stay DLC. The one thats anime-like.
## Post #36
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-08-11T01:14:04+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Gave it a quick test and I had the same issues. Noesis gives the following in the debug log

Detected file type: Fate Extella
Model name: SV1560_PS4
WARNING: VXBF count > IXBF count, some data not processed
Reading 'modeling\fate\Artoria\\'...Failed.
Reading 'modeling\fate\Artoria\\'...Failed.
Reading 'modeling\fate\Artoria\\'...Failed.
Reading 'modeling\fate\Artoria\\'...Failed.
Reading 'modeling\fate\Artoria\\'...Failed.


Guessing the skeleton issue stems from there.
## Post #37
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-08-11T01:20:41+00:00
- Post Title: Re: Fate Extella PC *.mdl format

I see I see. I would normally just do a simple face swap, but from what it looks like I'm pretty sure the face from the regular model isn't the same as this DLC's face. 
I hope you can fix this Kotcrab. It would be much appreciated! I'm really dumb when it comes to hex so I'm sorry I cannot be of any help.

EDIT: Another thing I noticed is that some characters have full finger bones, like 3 for every finger whereas others do not. They only have 2 bones per 2 fingers. Example Tamamo No Mae has full finger bones and Elizabeth Bathory doesn't. I don't know if that's game intentional or not I just thought it was weird that some have full and others don't so thought I'd mention it! Probably game intentional I'm assuming, depending on the characters weapon?
## Post #38
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-08-11T13:00:45+00:00
- Post Title: Re: Fate Extella PC *.mdl format

[Download v1.1](https://github.com/kotcrab/fate-explorer/releases/download/mdl-v1.1/data_fate_extella.py)

This only fixes issue with loading SV1310.mdl and SV0803.mdl.
Elizabeth skeleton is slightly moved up (and maybe scaled) but that's probably easy to fix after exporting.

> Reply from anime663
>
> What I've checked so far seems to be fine except the DLC Saber's face isn't properly rigged to her face rig. The bones are useless, since all the mesh is attached to the head bone only. Theyre still there, but they dont move any of the mesh. I don't know if shes meant to be that way or not. Her skirt armor plates also aren't attached to her bones.
Well I was going to check this but I opened up the game first and her face doesn't move either. She doesn't even blink. 
Don't know what's going on with skirt armor plates though. It is clearly using vertex stride of 32 which do not has bone info.

> Reading 'modeling\fate\Artoria\\'...Failed.
That's only related to textures. If texture is not assigned Noesis tries to load texture based on mesh name (I think). To load DLC models with textures, you can simply copy DLC files into extracted main archive.

> WARNING: VXBF count > IXBF count, some data not processed
There are some meshes that has vertex data without indices. I don't know how to parse it but I don't think it's something major. It's not like any big part of model is missing. Anyway, it wouldn't cause skeleton or rig issues.

> Reply from anime663
>
> EDIT: Another thing I noticed is that some characters have full finger bones, like 3 for every finger whereas others do not. They only have 2 bones per 2 fingers. Example Tamamo No Mae has full finger bones and Elizabeth Bathory doesn't. I don't know if that's game intentional or not I just thought it was weird that some have full and others don't so thought I'd mention it! Probably game intentional I'm assuming, depending on the characters weapon?
Looks like that's intentional, there are no more bones for fingers in model file.
## Post #39
- Username: Kenzato
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 29, 2017 7:58 am
- Post datetime: 2017-08-11T13:13:03+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Yeah i imagine the finger stuff might be related to the armor or weapons.

Some weapons are more rough and only needs the fingers to bend in two locations while others need you to grip around it
## Post #40
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-08-14T09:36:42+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Edit: If you read this before I edited, ignore what I said. Further testing revealed that it was happening with all models (even ones I had previously messed with) and it was actually just blender acting up for some reason. Loading the models into XNALara revealed no actual issues.

Also, scaling Elizabeth's skeleton (in blender at least) to .9 lines the skeleton up with the meshes nicely.
## Post #41
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2017-08-23T23:59:26+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Any fix for elizabeths skeleton yet?
## Post #42
- Username: Shakes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 12, 2016 4:46 am
- Post datetime: 2017-11-09T10:20:39+00:00
- Post Title: Re: Fate Extella PC *.mdl format

While importing the files of the UBW scenery to make a video I found that one of the model files containing the gears in the background gives a "VXBF count < IXBF count" error, and can't be previewed nor exported. Can you please take a quick look and check if it's something quick to fix?
[mdl file](https://drive.google.com/open?id=1SYvOjCQF-R0dd2I2p7PKE1en7R4ZK7fB)
## Post #43
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2017-11-09T12:36:33+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Yeah, use this [version 1.1.1](https://github.com/kotcrab/fate-explorer/releases/download/mdl-v1.1.1/data_fate_extella.py).
It's pretty much the same as GIM_SP_SV03_GEAR_01.mdl but the gears are all in single place.
## Post #44
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-01-03T14:31:30+00:00
- Post Title: Re: Fate Extella PC *.mdl format

Hello. Can anyone help on this?

I tried to export gae bolg effect, but the exported files isn't poseable even though it has armature.
There is "VXBF count > IXBF count, some data not processed" message when I opened the .mdl file in Noesis.
[gae bolg effect error.png](https://xentaxbackup.github.io/file/13754_gae bolg effect error.png)
